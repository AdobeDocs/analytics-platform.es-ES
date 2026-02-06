---
title: Vinculación basada en gráficos
description: Explica el concepto y el trabajo de la vinculación basada en gráficos.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 4cb54c684c76c2581b1f3f9aa00fcb743d7c6387
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 4%

---

# Vinculación basada en gráficos

En la vinculación basada en gráficos, se especifica un conjunto de datos de evento, el ID persistente (cookie) de ese conjunto de datos y el área de nombres de ID de persona deseada desde el gráfico de identidad. La vinculación basada en gráficos intenta que la información del ID de persona esté disponible para el análisis de datos de Customer Journey Analytics en cualquier evento. El ID persistente se utiliza para consultar el gráfico de identidad del servicio de identidad de Experience Platform y obtener el ID de persona del área de nombres especificada.

Si no se puede recuperar la información de ID de persona para un evento, se usa el ID persistente en su lugar para ese evento *unstitched*. Como resultado, en una [vista de datos](/help/data-views/data-views.md) asociada a una [conexión](/help/connections/overview.md) que contiene el conjunto de datos habilitado para la vinculación, el componente de vista de datos de ID de persona contiene el valor de ID de persona o el valor de ID persistente en el nivel de evento.


![Vinculación basada en gráficos](/help/stitching/assets/gbs.svg)

## IdentityMap

La vinculación basada en gráficos admite el uso del grupo de campos [`identityMap` &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) en los siguientes casos:

- Uso de la identidad principal en `identityMap` áreas de nombres para definir el persistentID:
   - Si se encuentran varias identidades principales en diferentes áreas de nombres, las identidades de las áreas de nombres se ordenan lexicográficamente y se selecciona la primera identidad.
   - Si se encuentran varias identidades principales en un solo área de nombres, se selecciona la primera identidad principal lexicográfica disponible.

  En el ejemplo siguiente, las áreas de nombres e identidades generan una lista de identidades principales ordenada y, finalmente, la identidad seleccionada.

  <table style="table-layout:auto">
     <tr>
       <th>Espacios de nombres</th>
       <th>Lista de identidades</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Lista de identidades ordenadas</th>
      <th>Identidad seleccionada</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- Uso del espacio de nombres `identityMap` para definir el persistentID:
   - Si se encuentran varios valores para persistentID en un área de nombres `identityMap`, se utiliza la primera identidad lexicográfica disponible.

  En el ejemplo siguiente, ha seleccionado ECID como el área de nombres que debe utilizar. Esa selección genera una lista de identidades ordenadas y, finalmente, la identidad seleccionada.

  <table style="table-layout:auto">
     <tr>
       <th>Espacios de nombres</th>
       <th>Lista de identidades</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Lista de identidades ordenadas</th>
      <th>Identidad seleccionada</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## Funcionamiento de la vinculación basada en gráficos

La vinculación realiza un mínimo de dos pasadas de datos en un conjunto de datos determinado.

- **Vinculación en tiempo real**: intenta vincular cada visita (evento) conforme se va produciendo, utilizando el ID persistente para buscar el ID de persona para el área de nombres seleccionada consultando el gráfico de identidad. Si el ID de persona está disponible desde la búsqueda, este ID de persona se vincula inmediatamente.

- **Reproducir vinculación**: *reproduce* datos basados en identidades actualizadas del gráfico de identidades. En esta fase es en la que las visitas de dispositivos anteriormente desconocidos (ID persistentes) se vinculan a medida que el gráfico de identidad ha resuelto la identidad de un área de nombres. Dos parámetros determinan la reproducción: **frequency** y **lookback window**. Adobe ofrece las siguientes combinaciones de estos parámetros:
   - **Retrospectiva diaria en una frecuencia diaria**: Los datos se reproducen todos los días con una ventana retrospectiva de 24 horas. Esta opción ofrece la ventaja de que las reproducciones son mucho más frecuentes, pero los perfiles no autenticados deben autenticarse el mismo día que visitan el sitio.
   - **Retrospectiva semanal de una frecuencia semanal**: los datos se reproducen una vez a la semana con una ventana retrospectiva semanal (consulte [opciones](overview.md#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de una semana de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.
   - **Retrospectiva quincenal con una frecuencia semanal**: Los datos se reproducen una vez por semana con una ventana retrospectiva quincenal (consulte [opciones](overview.md#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de dos semanas de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.
   - **Retrospectiva mensual de una frecuencia semanal**: los datos se reproducen cada semana con una ventana retrospectiva mensual (consulte [opciones](overview.md#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de un mes de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.

- **Privacidad**: cuando se reciben solicitudes relacionadas con la privacidad, además de quitar la identidad solicitada del conjunto de datos de origen, se debe deshacer cualquier vinculación de esa identidad entre eventos no autenticados. Además, la identidad debe eliminarse del gráfico de identidad para evitar una vinculación futura basada en gráficos para esa identidad específica.

  >[!IMPORTANT]
  >
  >El proceso de desvinculación, como parte de las solicitudes de privacidad, cambia a principios de 2025. El proceso actual de desvinculación revincula los eventos con la última versión de identidades conocidas. Esta reasignación de eventos a otra identidad podría tener consecuencias legales indeseables. Para solucionar estos problemas, a partir de 2025, el nuevo proceso de desvinculación actualiza los eventos que están sujetos a la solicitud de privacidad con el ID persistente.
  > 

Los datos que están más allá de la ventana retrospectiva no se reproducen. Un perfil debe autenticarse dentro de una ventana retrospectiva determinada para que una visita no autenticada y una visita autenticada se identifiquen juntas. Una vez que se reconoce un dispositivo, se vincula en vivo a partir de ese momento.

Considere las dos actualizaciones siguientes del gráfico de identidad a lo largo del tiempo para el visitante A (con ID persistente `246`) y el visitante B (con ID persistente `3579`), y cómo estas actualizaciones afectan a los pasos de la vinculación basada en gráficos.

![Gráfico de identidad 3579](assets/identity-graphs.svg)

Puede ver un gráfico de identidad a lo largo del tiempo para un perfil específico mediante el [Visor de gráficos de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulte también [Lógica de vinculación del servicio de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) para comprender mejor la lógica utilizada al vincular identidades.

### Paso 1: Vinculación en tiempo real

La vinculación en tiempo real intenta vincular cada evento, tras la recopilación, con la información conocida en ese momento del gráfico de identidad.

+++ Detalles

| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID resultante (después de la unión activa) |
|--:|---|---|---|---|
| 1 | 11:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) *sin definir* | `246` |
| 2 | 14:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 15:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 17:00, 12-05-2023 | `3579` | `3579` ![Rama1](/help/assets/icons/Branch1.svg) *sin definir* | `3579` |
| 5 | 19:00, 12-05-2023 | `3579` | `3579` ![Rama1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 13-05-2023 15:00 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 16:30, 13-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Puede ver cómo se resuelve el ID resultante para cada evento. En función del tiempo, el ID persistente y la búsqueda del gráfico de identidades para el área de nombres de ID de persona especificada.
Cuando la búsqueda responde a más de un ID resultante (como en el caso del evento 7), se selecciona el primer ID lexicográfico devuelto por el gráfico de identidades (`a.b@yahoo.co.uk` en el ejemplo).

+++

### Paso 2: Reproducción de la vinculación

A intervalos regulares (en función de la ventana retrospectiva seleccionada), la vinculación de reproducción vuelve a calcular los datos históricos en función de la versión más reciente del gráfico de identidad, en el momento del intervalo.

+++ Detalles

Con una vinculación de reproducción que se produce el 13 de mayo de 2023 a las 16 :30, con una configuración de ventana retrospectiva de 24 horas, algunos eventos de la muestra se vuelven a vincular (indicado por ![Reproducir](/help/assets/icons/Replay.svg)).

| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Id. resultante <br/>(después de la unión activa) | Id. resultante <br/>(después de la reproducción 24 horas) |
|---|---|---|---|---|---|
| 2 | 14:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 15:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Reproducir](/help/assets/icons/Replay.svg) 4 | 17:00, 12-05-2023 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Reproducir](/help/assets/icons/Replay.svg) 5 | 19:00, 12-05-2023 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Reproducir](/help/assets/icons/Replay.svg) 6 | 13-05-2023 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](/help/assets/icons/Replay.svg) 7 | 16:30, 13-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Con la vinculación de reproducción que se produce el 13 de mayo de 2023 a las 16 :30, con una configuración de ventana retrospectiva de 7 días, todos los eventos de la muestra se vuelven a vincular.


| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Id. resultante <br/>(después de la unión activa) | Id. resultante <br/>(después de 7 días de reproducción) |
|---|---|---|---|---|---|
| ![Reproducir](/help/assets/icons/Replay.svg) 1 | 11:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) *sin definir* | `246` | `a.b@yahoo.co.uk` |
| ![Reproducir](/help/assets/icons/Replay.svg) 2 | 14:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](/help/assets/icons/Replay.svg) 3 | 15:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](/help/assets/icons/Replay.svg) 4 | 17:00, 12-05-2023 | `3579` | `3579` ![Rama1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Reproducir](/help/assets/icons/Replay.svg) 5 | 19:00, 12-05-2023 | `3579` | `3579` ![Rama1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Reproducir](/help/assets/icons/Replay.svg) 6 | 13-05-2023 15:00 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](/help/assets/icons/Replay.svg) 7 | 16:30, 13-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Paso 3: Solicitud de privacidad

Cuando recibe una solicitud de privacidad, el ID resultante se elimina en todos los registros del asunto del usuario en la solicitud de privacidad.

+++ Detalles

La siguiente tabla representa los mismos datos que los que hemos visto anteriormente, pero muestra el efecto que tiene una solicitud de privacidad (por ejemplo, en 2023-05-13 18:00) en los eventos de ejemplo.

| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID resultante (después de la solicitud de privacidad) |
|--:|---|---|---|---|
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 1 | 11:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 2 | 14:00, 12-05-2023 | `246` | `246`![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 3 | 15:00, 12-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 4 | 17:00, 12-05-2023 | `3579` | `3579` ![Rama1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 5 | 19:00, 12-05-2023 | `3579` | `3579` ![Rama1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 6 | 13-05-2023 15:00 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) 7 | 16:30, 13-05-2023 | `246` | `246` ![Rama1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Rama1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Requisitos previos

Los siguientes requisitos previos se aplican específicamente a la vinculación basada en gráficos:

- El conjunto de datos de evento de Adobe Experience Platform al que desea aplicar la vinculación debe tener una columna que identifique un perfil en cada fila, la **ID persistente**. Por ejemplo, un ID de visitante generado por una biblioteca AppMeasurement de Adobe Analytics o un ECID generado por el servicio de identidad de Experience Platform.
- El gráfico de identidad del servicio de identidad de Experience Platform debe configurarse en el nivel de zona protegida antes de habilitar la vinculación basada en gráficos.
   - El gráfico de identidad debe tener un área de nombres (por ejemplo `Email` o `Phone`) que desee usar durante la vinculación para resolver el ID de persona.
   - El gráfico de identidad debe rellenarse con información de identidades de cualquier conjunto de datos relevante (de tipo *event* o *profile* y que contenga al menos dos áreas de nombres útiles con valores de ID).
   - Todos los conjuntos de datos que contienen estas identidades relevantes deben estar [habilitados para la ingesta de datos del gráfico de identidades](faq.md#enable-a-dataset-for-the-identity-service). Esta habilitación garantiza que las identidades entrantes se añadan al gráfico a lo largo del tiempo desde todas las fuentes necesarias.
   - Si ya utiliza el Perfil de datos del cliente en tiempo real o Adobe Journey Optimizer durante un tiempo, el gráfico debería estar configurado hasta cierto punto.<br/>Si también se requiere relleno de vinculación histórica para el conjunto de datos habilitado con la vinculación basada en gráficos, el gráfico ya debe contener identidades históricas para todo el período a fin de obtener los resultados de vinculación deseados.
- Si desea utilizar la vinculación basada en gráficos y prevé que el conjunto de datos de evento contribuirá al gráfico de identidad, debe [habilitar el conjunto de datos para el servicio de identidad](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).
- El ID persistente y el ID de persona se pueden usar con [identityMap](#identitymap). O el ID persistente y el ID de persona pueden ser campos del esquema XDM, en cuyo caso los campos deben estar [definidos como una identidad](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity?lang=en) en el esquema.

>[!NOTE]
>
>No necesita **not** una licencia de Real-time Customer Data Platform para la vinculación basada en gráficos. El paquete **Prime** o superior de Customer Journey Analytics incluye los derechos necesarios del servicio de identidad de Experience Platform.


## Limitaciones

Las siguientes limitaciones se aplican específicamente a la vinculación basada en gráficos:

- Las marcas de tiempo no se tienen en cuenta al consultar el ID de persona mediante el área de nombres especificada. Por lo tanto, es posible que un ID persistente se vincule con un ID de persona de un registro que tenga una marca de tiempo anterior.
- En escenarios de dispositivos compartidos, donde el área de nombres del gráfico contiene varias identidades, se utiliza la primera identidad lexicográfica. Si los límites y prioridades del área de nombres se configuran como parte de la publicación de reglas de vinculación de gráficos, se utiliza la última identidad del usuario autenticado. Consulte [Dispositivos compartidos](/help/use-cases/stitching/shared-devices.md) para obtener más información.
- Hay un límite estricto de tres meses para rellenar identidades en el gráfico de identidades. Para rellenar el gráfico de identidades, debe utilizar identidades de relleno en caso de que no utilice una aplicación de Experience Platform, como Real-time Customer Data Platform.
- Se aplican las [protecciones del servicio de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails). Vea, por ejemplo, los [límites estáticos](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits) siguientes:
   - Número máximo de identidades en un gráfico: 50.
   - Número máximo de vínculos a una identidad para una sola ingesta por lotes: 50.
   - Número máximo de identidades en un registro XDM para la ingesta de gráficos: 20.
   - Cantidad mínima de identidades en un registro XDM para la ingesta de gráficos: 2.
