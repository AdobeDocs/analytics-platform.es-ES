---
title: Vinculación basada en campos
description: Explica el concepto y el trabajo de la vinculación basada en el campo.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 2e2620bdc6875b13492013f4ec108bae0302a25a
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 9%

---

# Vinculación basada en el campo

En la vinculación basada en el campo, se especifica un conjunto de datos de evento, así como el ID persistente (cookie) y el ID de persona para ese conjunto de datos. La vinculación basada en campos intenta que la información del ID de persona esté disponible para el análisis de datos de Customer Journey Analytics en cualquier evento anónimo que venga con un ID persistente específico.  Esa información se recupera de las filas que tienen un ID de persona para ese ID persistente específico.

Si no se puede recuperar la información de ID de persona para un evento, se usa el ID persistente en su lugar para ese evento *unstitched*. Como resultado, en una [vista de datos](/help/data-views/data-views.md) asociada a una [conexión](/help/connections/overview.md) que contiene el conjunto de datos habilitado para la vinculación, el componente de ID de persona contiene el valor de ID de persona o el valor de ID persistente en el nivel de evento.

Puede utilizar la vinculación basada en el campo al utilizar Customer Journey Analytics como solución independiente (sin acceso al servicio de identidad de Experience Platform y al gráfico de identidades asociado). O bien, cuando no desee utilizar el gráfico de identidad disponible.

![Vinculación basada en el campo](/help/stitching/assets/fbs.svg)


## IdentityMap

La vinculación basada en campos admite el uso del grupo de campos [`identityMap` &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) en los siguientes casos:

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


- Uso del espacio de nombres `identityMap` para definir el ID persistente, el ID de persona o ambos:
   - Si se encuentran varios valores para el identificador persistente o el identificador de persona en un área de nombres `identityMap`, se utiliza el primer valor lexicográfico disponible.
   - Las áreas de nombres para ID persistente e ID de persona deben ser mutuamente excluyentes.

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

## Cómo funciona la vinculación basada en el campo

La vinculación realiza un mínimo de dos pasadas de datos en un conjunto de datos determinado.

- **Vinculación en tiempo real**: intenta vincular cada visita (evento) conforme se va produciendo. Las visitas de dispositivos que son *nuevos* al conjunto de datos (nunca se han autenticado) generalmente no se vinculan en este nivel. Las visitas de dispositivos ya reconocidos se vinculan inmediatamente.

- **Reproducir vinculación**: *reproduce* datos basados en identificadores únicos (ID de persona). En esta fase es en la que las visitas de dispositivos anteriormente desconocidos (ID persistentes) se vinculan (a ID de persona). Dos parámetros determinan la reproducción: **frequency** y **lookback window**. Adobe ofrece las siguientes combinaciones de estos parámetros:
   - **Retrospectiva diaria en una frecuencia diaria**: Los datos se reproducen todos los días con una ventana retrospectiva de 24 horas. Esta opción ofrece la ventaja de que las reproducciones son mucho más frecuentes, pero los perfiles no autenticados deben autenticarse el mismo día que visitan el sitio.
   - **Retrospectiva semanal de una frecuencia semanal**: los datos se reproducen una vez a la semana con una ventana retrospectiva semanal (consulte [opciones](overview.md#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de una semana de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.
   - **Retrospectiva quincenal con una frecuencia semanal**: Los datos se reproducen una vez por semana con una ventana retrospectiva quincenal (consulte [opciones](overview.md#)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de dos semanas de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.
   - **Retrospectiva mensual de una frecuencia semanal**: los datos se reproducen cada semana con una ventana retrospectiva mensual (consulte [opciones](overview.md#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de un mes de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.

- **Privacidad**: cuando se reciben solicitudes relacionadas con la privacidad, además de eliminar la identidad solicitada, se debe deshacer cualquier vinculación de esa identidad entre eventos no autenticados.

  >[!IMPORTANT]
  >
  >El proceso de desvinculación, como parte de las solicitudes de privacidad, cambia a principios de 2025. El proceso actual de desvinculación revincula los eventos con la última versión de identidades conocidas. Esta reasignación de eventos a otra identidad podría tener consecuencias legales indeseables. Para solucionar estos problemas, a partir de 2025, el nuevo proceso de desvinculación actualiza los eventos que están sujetos a la solicitud de privacidad con el ID persistente.
  > 


Los datos que están más allá de la ventana retrospectiva no se reproducen. Un perfil debe autenticarse dentro de una ventana retrospectiva determinada para que una visita no autenticada y una visita autenticada se identifiquen juntas. Una vez que se reconoce un dispositivo, ese dispositivo se vincula en vivo a partir de ese momento.

### Paso 1: Vinculación en tiempo real

La vinculación en tiempo real intenta vincular cada evento tras la recopilación con los dispositivos y canales conocidos.

+++ Detalles

Preste atención al siguiente ejemplo, en el que Bob registra diferentes eventos como parte de un conjunto de datos de eventos.

*Datos tal como aparecieron el día en que se recopilaron:*

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID de la persona | ID resultante (después de la unión activa) |
|---|---|---|---|---|
| 1 | 12/12/05/2023:01 | `246` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 12/12/05/2023:02 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 12/12/05/2023:03 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) |
| 4 | 12/12/05/2023:04 | `246` | - | **`Bob`** |
| 5 | 12/12/05/2023:05 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 12/12/05/2023:06 | `246` | - | **`Bob`** |
| 7 | 12/12/05/2023:07 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 12/12/05/2023:03 | `3579` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 12/12/05/2023:09 | `3579` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 12/12/05/2023:02 | `81911` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 12/12/05/2023:05 | `81911` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) |
| 12 | 12/12/05/2023:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivos** | | **4 personas**:<br/>`246`, `Bob`, `3579`, `81911` |

Tanto los eventos no autenticados como los autenticados en los nuevos dispositivos se cuentan como personas independientes (temporalmente). Los eventos no autenticados en dispositivos reconocidos se vinculan en tiempo real.

La atribución funciona cuando la variable personalizada de identificación está vinculada a un dispositivo. En el ejemplo anterior, todos los eventos, excepto los eventos 1, 8, 9 y 10, se vinculan en tiempo real (todos utilizan el identificador `Bob`). La vinculación en tiempo real &quot;resuelve&quot; el ID resultante para los eventos 4, 6 y 12.

Los datos con retraso (datos con una marca de tiempo de más de 24 horas) se gestionan con el &quot;mejor esfuerzo&quot;, a la vez que se prioriza la vinculación de los datos actuales para obtener la máxima calidad.

+++ 

### Paso 2: Reproducción de la vinculación

A intervalos regulares (una vez a la semana o una vez al día, en función de la ventana retrospectiva seleccionada), la vinculación de reproducción vuelve a calcular los datos históricos en función de los dispositivos que ahora reconoce. Si un dispositivo envía inicialmente datos sin autenticarse y luego inicia sesión, la reproducción de la vinculación vincula esos eventos sin autenticar con la persona correcta.

+++ Detalles

La siguiente tabla representa los mismos datos que arriba, pero muestra números diferentes basados en la reproducción de los datos.

*Los mismos datos después de la reproducción:*

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID de la persona | ID resultante (después de la unión activa) | ID resultante (después de la reproducción) |
|---|---|---|---|---|---|
| 1 | 12/12/05/2023:01 | `246` | - | `246` | **`Bob`** |
| 2 | 12/12/05/2023:02 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Flecha arriba](/help/assets/icons/ArrowUp.svg) |
| 3 | 12/12/05/2023:03 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 12/12/05/2023:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 12/12/05/2023:05 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 12/12/05/2023:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 12/12/05/2023:07 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 12/12/05/2023:03 | `3579` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 12/12/05/2023:09 | `3579` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 12/12/05/2023:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 12/12/05/2023:05 | `81911` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) | `Bob` ![Flecha arriba](/help/assets/icons/ArrowUp.svg) |
| 12 | 12/12/05/2023:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivos** | | **4 personas**:<br/>`246`, `Bob`, `3579`, `81911` | **2 personas**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

La atribución funciona cuando la variable personalizada de identificación está vinculada a un dispositivo. En el ejemplo anterior, los eventos 1 y 10 se vinculan como resultado de la reproducción, dejando solo el evento 8 y 9 sin vincular. Y reduciendo la métrica de personas (acumulativa) a 2.

+++ 

### Paso 3: Solicitud de privacidad

Cuando recibe una solicitud de privacidad, cualquier información de identificador establecida por el proceso de vinculación al valor de ID de persona se actualiza en todos los registros a un valor de ID persistente para el sujeto del usuario de la solicitud de privacidad.

+++ Detalles

La siguiente tabla representa los mismos datos que los que hemos visto anteriormente, pero muestra el efecto que una solicitud de privacidad para Bob tiene en los datos después de procesarlos. Se quitan las filas en las que Bob está autenticado (2, 3, 5, 7 y 11) junto con la eliminación de Bob como ID de persona para otras filas.

*Los mismos datos después de una solicitud de privacidad para Bob:*

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID de la persona | ID resultante (después de la unión activa) | ID resultante (después de la reproducción) | ID de la persona | ID resultante (después de la solicitud de privacidad) |
|---|---|---|---|---|---|---|---|
| 1 | 12/12/05/2023:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 12/12/05/2023:02 | `246` | Bob ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![flecha arriba](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 12/12/05/2023:03 | `246` | Bob ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) | `Bob` | ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 12/12/05/2023:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 12/12/05/2023:05 | `246` | Bob ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) | `Bob` | ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 12/12/05/2023:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 12/12/05/2023:07 | `246` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 12/12/05/2023:03 | `3579` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 12/12/05/2023:09 | `3579` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 12/12/05/2023:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 12/12/05/2023:05 | `81911` | `Bob` ![FlechaDerecha](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flecha abajo](/help/assets/icons/ArrowDown.svg) | `Bob` ![Flecha arriba](/help/assets/icons/ArrowUp.svg) | ![QuitarCírculo](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 12/12/05/2023:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivos** | | **4 personas**:<br/>246, `Bob`, `3579`, `81911` | **2 personas**:<br/>Bob, `3579` |  | **3 personas**:<br/>`246`, `3579`, `81911` |

+++ 

## Requisitos previos

Los siguientes requisitos previos se aplican específicamente a la vinculación basada en el campo:

- El conjunto de datos de evento de Adobe Experience Platform al que desee aplicar la vinculación debe tener dos columnas que ayuden a identificar perfiles:

   - **ID persistente**, un identificador disponible en cada fila. Por ejemplo, un ID de visitante generado por una biblioteca AppMeasurement de Adobe Analytics o un ECID generado por el servicio de identidad de Adobe Experience Platform.
   - Un **ID de persona**, un identificador disponible solo en algunas filas. Por ejemplo, un nombre de usuario o una dirección de correo electrónico con hash una vez que un perfil se autentica. Puede utilizar prácticamente cualquier identificador que desee. La vinculación tiene en cuenta este campo para contener la información de ID de persona real. Para obtener los mejores resultados de vinculación, se debe enviar un ID de persona dentro de los eventos del conjunto de datos al menos una vez por cada ID persistente. Si planea incluir este conjunto de datos dentro de una conexión de Customer Journey Analytics, es preferible que los demás conjuntos de datos también tengan un identificador común similar.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Limitaciones

Las siguientes limitaciones se aplican específicamente a la vinculación basada en el campo:

- Las capacidades actuales de regeneración de claves están limitadas a un paso (ID persistente a ID de persona). No se admite la regeneración de claves de varios pasos (por ejemplo, ID persistente a ID de persona y, a continuación, a otro ID de persona).
- Si varias personas comparten un dispositivo y el número total de transiciones entre usuarios supera las 50 000, Customer Journey Analytics deja de vincular datos para ese dispositivo.
- No se admiten los mapas de ID personalizados utilizados en su organización.
- La vinculación distingue entre mayúsculas y minúsculas. Para los conjuntos de datos generados mediante el conector de origen de Analytics, Adobe recomienda revisar cualquier regla VISTA o de procesamiento que se aplique al campo de ID de persona. Esta revisión garantiza que ninguna de estas reglas introduzca nuevos formularios del mismo ID. Por ejemplo, debe asegurarse de que ninguna regla VISTA o de procesamiento introduce minúsculas en el campo ID de persona solo en una parte de los eventos.
- La configuración no combina ni concatena campos.
- El campo ID de persona debe contener un solo tipo de ID (ID de un solo área de nombres). Por ejemplo, el campo de ID de persona no debe contener una combinación de ID de inicio de sesión e ID de correo electrónico.
- Si se producen varios eventos con la misma marca de tiempo para el mismo ID persistente, pero con valores diferentes en el campo ID de persona, la vinculación selecciona el ID en función del orden alfabético. Por lo tanto, si el ID persistente A tiene dos eventos con la misma marca de tiempo y uno de los eventos especifica Bob y el otro Ann, al vincular se selecciona Ann.
- Tenga cuidado con los escenarios donde los ID de persona contienen valores de marcador de posición, por ejemplo `Undefined`. Consulte las [preguntas frecuentes](faq.md) para obtener más información.
- No puede utilizar el mismo área de nombres tanto para el ID persistente como para el ID de persona, las áreas de nombres deben ser mutuamente excluyentes.
