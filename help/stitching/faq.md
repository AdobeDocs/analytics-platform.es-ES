---
title: Preguntas frecuentes sobre la vinculación
description: Obtenga información acerca de las preguntas más frecuentes acerca de la vinculación.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 1bba52c332f1594b0b07466b499e24b5c62726fd
workflow-type: tm+mt
source-wordcount: '2219'
ht-degree: 81%

---

# Preguntas frecuentes

Estas son algunas de las preguntas recuentes sobre la vinculación:

## Desplazamiento entre canales

+++ ¿Cómo puedo usar la vinculación para ver cómo se mueve la gente de un canal a otro?

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Inicie sesión en [Customer Journey Analytics](https://analytics.adobe.com) y cree un proyecto de Workspace en blanco.
2. Seleccione la pestaña **[!UICONTROL ** Visualizaciones **]** en el lado izquierdo y arrastre la visualización de **[!UICONTROL **&#x200B; Flujo &#x200B;**]** al lienzo situado a la derecha.
3. Seleccione la pestaña **[!UICONTROL ** Componentes **]** en el lado izquierdo y arrastre la dimensión **[!UICONTROL ** ID de conjunto de datos **]** a la ubicación del centro etiquetada como **[!UICONTROL **&#x200B; Dimensión o elemento &#x200B;**]**.
4. Este informe de flujo es interactivo. Para expandir los flujos a páginas posteriores o anteriores, seleccione cualquiera de los valores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Puede utilizar un conjunto de datos de búsqueda si desea cambiar el nombre de los elementos de la dimensión de ID de conjunto de datos.

+++

## Reproducción

+++ ¿Hasta cuándo se remontan los perfiles de reproducción de la vinculación?

El período de retroactividad para el renombramiento de claves depende de la frecuencia deseada de la reproducción de los datos. Por ejemplo, si configura la vinculación para que reproduzca los datos una vez por semana, el período de retroactividad para el renombramiento de claves será de siete días. Si configura la vinculación para que reproduzca datos todos los días, el período de retroactividad para el renombramiento de claves será de un día.

+++

+++ ¿Cuándo se ejecuta exactamente el proceso de reproducción?

* La reproducción **semanal** comienza cada **sábado** por la noche (zona horaria del cliente) y los datos se actualizarán en los informes de Customer Journey Analytics el lunes por la mañana.
* La reproducción de **daily** se ejecuta alrededor de las **3 a.m.** (zona horaria del cliente) y los datos se actualizan en los informes de Customer Journey Analytics por la mañana.

>[!IMPORTANT]
>
>El día de la reproducción semanal y la hora de la reproducción diaria no se pueden cambiar mediante una solicitud personalizada.
>

+++

## Dispositivos compartidos

+++ ¿Cómo se gestionan los dispositivos compartidos?

En algunas situaciones, es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID de persona anula el ID persistente, por lo que los dispositivos compartidos se consideran usuarios independientes (incluso si se originan en el mismo dispositivo).

Consulte el caso de uso [Dispositivos compartidos](/help/use-cases/stitching/shared-devices.md) para obtener más información.

+++

## Muchos ID persistentes

+++ ¿Cómo gestiona la vinculación las situaciones en las que un solo usuario tiene muchos ID persistentes?

En algunas situaciones, un usuario individual puede asociarse con muchos ID persistentes. Un ejemplo es una persona que borra con frecuencia las cookies del explorador o que utiliza el modo privado/de incógnito del explorador.

En el caso de la vinculación basada en campos, el número de ID persistentes es irrelevante en favor del ID de persona. Un solo usuario puede pertenecer a cualquier número de dispositivos sin que ello afecte a la posibilidad de que Customer Journey Analytics se vincule entre diferentes dispositivos.

Para la vinculación basada en gráficos, una sola persona puede tener muchos ID persistentes en el gráfico de identidades. La vinculación basada en gráficos utiliza el ID persistente en función del espacio de nombres especificado. En caso de que haya ID más persistentes para el mismo área de nombres, se utiliza el primer ID persistente lexicográfico.

+++

## Proceso de vinculación

+++ Tras contactar con el equipo de cuentas de Adobe y proporcionarle la información deseada, ¿cuánto tarda en estar disponible el conjunto de datos cuya clave se ha vuelto a generar?

La vinculación en tiempo real está disponible aproximadamente una semana después de que Adobe habilite la vinculación. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1000 millones de eventos por día) pueden tardar una semana o más.

+++

## Análisis entre dispositivos frente al análisis en canales múltiples

+++ ¿Cuál es la diferencia entre el análisis entre dispositivos (una función de Analytics tradicional) y el análisis en canales múltiples?

El [análisis entre dispositivos](https://experienceleague.adobe.com/es/docs/analytics/components/cda/overview) es una función específica de la versión tradicional de Adobe Analytics que le permite comprender cómo interactúan las personas a través de distintos dispositivos. Ofrece dos flujos de trabajo para vincular datos de dispositivos: vinculación basada en el campo y el gráfico del dispositivo.

El análisis en canales múltiples es un caso de uso específico de Customer Journey Analytics que le permite comprender cómo interactúan las personas a través de distintos dispositivos y distintos canales. Vincula el ID de persona de un conjunto de datos, lo que permite que ese conjunto de datos se combine sin problemas con otros conjuntos de datos. Esta característica funciona de forma similar a cuanto al diseño que la vinculación basada en campos de Analytics, pero la implementación es distinta debido a la diferente arquitectura de datos entre Analytics tradicional y Customer Journey Analytics. Consulte [Vinculación](overview.md) y el caso de uso de [análisis en canales múltiples](../use-cases/cross-channel/cross-channel.md) para obtener más información.

+++

## Privacidad

+++ ¿Cómo gestiona la vinculación las solicitudes de privacidad?

Adobe gestiona las solicitudes de privacidad de acuerdo con las leyes locales e internacionales. Adobe ofrece el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/es/docs/experience-platform/privacy/home) para enviar solicitudes de acceso a datos y de eliminación. Las solicitudes se aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.

>[!IMPORTANT]
>
>El proceso de desvinculación, como parte de las solicitudes de privacidad, cambia a principios de 2025. El proceso actual de desvinculación revincula los eventos con la última versión de identidades conocidas. Esta reasignación de eventos a otra identidad podría tener consecuencias legales no deseadas. Para solucionar estos problemas, a partir de 2025, el nuevo proceso de desvinculación actualiza los eventos que están sujetos a la solicitud de privacidad con el ID persistente.
> 

Para ilustrarlo, imagine los siguientes datos para identidades y eventos antes y después de la vinculación.

| Mapa de identidad | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos de eventos | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos vinculado | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona | ID resultante | espacio de nombres vinculado |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Proceso actual para solicitudes de privacidad**

Cuando se recibe una solicitud de privacidad para un cliente con CustID Bob, se eliminan las filas con las entradas tachadas. Otros eventos se vuelven a vincular mediante el mapa de identidad. Por ejemplo, el primer ID vinculado del conjunto de datos vinculado se actualiza a **Alex**.

| Mapa de identidad | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona |
|:---:|---|---|---|---|---|---|
| ![EliminarDiseño](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos de eventos | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![EliminarDiseño](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos vinculado | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona | ID resultante | espacio de nombres vinculado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![EliminarDiseño](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Nuevo proceso para la solicitud de privacidad**

Cuando se recibe una solicitud de privacidad para un cliente con CustID Bob, se eliminan las filas con las entradas tachadas. Otros eventos se vuelven a vincular con el ID persistente. Por ejemplo, el primer ID vinculado del conjunto de datos vinculado se actualiza a **123**.

| Mapa de identidad | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona |
|:---:|---|---|---|---|---|---|
| ![EliminarDiseño](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos de eventos | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![EliminarDiseño](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos vinculado | Id | marca de tiempo | ID persistente | espacio de nombres persistente | ID de persona | espacio de nombres de persona | ID resultante | espacio de nombres vinculado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![EliminarDiseño](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Valores de ID persistentes en blanco

+++ ¿Qué sucede si está en blanco el campo de ID persistente de uno o varios eventos?

Si el campo de ID persistente está en blanco en un evento de un conjunto de datos que se está vinculando, el ID resultante para ese evento se determina de una de las dos maneras siguientes:

* Si el campo ID de persona no está en blanco, Customer Journey Analytics utiliza el valor en ID de persona como ID resultante.
* Si el campo de ID de persona está en blanco, Customer Journey Analytics también deja en blanco el ID resultante. En este caso, el ID persistente, el ID de persona y el ID resultante están en blanco en el evento. Estos tipos de eventos se pierden de cualquier conexión de Customer Journey Analytics usando el conjunto de datos que se está vinculando, donde el ID resultante se eligió como ID de persona.

+++


## Valores de ID de persona no definidos

+++ ¿Qué sucede si el campo ID de persona de uno o varios eventos tiene valores de marcador de posición como `Undefined`?

Tenga cuidado con la &#39;contracción de personas&#39;, que se produce cuando se aplica la vinculación a datos que utilizan valores de marcador de posición para ID transitorios. En la tabla de ejemplo siguiente, los ID de persona no definidos que se originan en un conjunto de datos procedente de un sistema CRM se rellenan con el valor &#39;No definido&#39;, lo que se traduce en una representación incorrecta de las personas.

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID transitorio | ID resultante (después de la reproducción) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | No definido | **No definido** |
| 4 | 2023-05-12 12:04 | 456 | - | **No definido** |
| 5 | 12/05/2023 12:05 | 789 | No definido | **No definido** |
| 6 | 2023-05-12 12:06 | 012 | No definido | **No definido** |
| 7 | 2023-05-12 12:07 | 012 | - | **No definido** |
| 8 | 2023-05-12 12:03 | 789 | No definido | **No definido** |
| 9 | 2023-05-12 12:09 | 456 | - | **No definido** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **Cuatro dispositivos** | **Dos personas**:<br/>se eliminaron los eventos uno, cuatro, siete, nueve, diez | **Dos personas**:<br/>Cory, sin autenticar (se ha contraído a una persona) |

+++

## Comparación de métricas

+++ ¿En qué se parecen las métricas de los conjuntos de datos vinculados de Customer Journey Analytics con métricas similares en los conjuntos de datos no vinculados de Customer Journey Analytics y con las de Adobe Analytics?

Determinadas métricas de Customer Journey Analytics son similares a las métricas de Analytics tradicional, pero otras son bastante diferentes, según lo que esté comparando. La siguiente tabla compara varias métricas comunes:

| **Datos vinculados de Customer Journey Analytics** | **Datos no vinculados de Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Personas** = Recuento de ID de persona diferentes donde el ID resultante se elige como ID de persona. **Las personas** pueden ser superiores o inferiores a los **visitantes únicos** en Adobe Analytics tradicional, según el resultado del proceso de identificación entre dispositivos. | **Personas** = Recuento de ID de persona diferentes según la columna seleccionada como ID de persona. **Las personas** en los conjuntos de datos del conector de origen de Analytics son similares a los **visitantes únicos** en Adobe Analytics tradicional, si `endUserIDs._experience.aaid.id` se utiliza como ID de persona en Customer Journey Analytics. | **Visitantes únicos** = Recuento de ID de visitantes diferentes. **Visitantes únicos** pueden no ser los mismos que el recuento de **ECID** distintos. | Consulte [Personas](https://experienceleague.adobe.com/es/docs/analytics/components/metrics/people). |
| **Sesiones**: se define en función de la configuración de sesiones en la vista de datos de Customer Journey Analytics. El proceso de identificación entre dispositivos puede combinar sesiones individuales de varios dispositivos en una sola sesión. | **Sesiones**: se define en función de la configuración de sesiones especificada en la vista de datos de Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/es/docs/analytics/components/metrics/visits). | **Visitas**: se define en función de la configuración de sesiones especificada en el [grupo de informes virtuales de CDA](https://experienceleague.adobe.com/es/docs/analytics/components/cda/setup). |
| **Eventos** = recuento de filas en los datos enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. No obstante, tenga en cuenta las preguntas frecuentes anteriores sobre las filas con un ID persistente en blanco. | **Eventos** = recuento de filas en los datos no enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. Sin embargo, tenga en cuenta que si algún evento tiene un ID de persona en blanco en los datos no vinculados en el lago de datos de Experience Platform, estos eventos no se incluirán en Customer Journey Analytics. | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/es/docs/analytics/components/metrics/occurrences). | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/es/docs/analytics/components/metrics/occurrences). |

Otras métricas pueden ser similares en Customer Journey Analytics y en Adobe Analytics Analytics. Por ejemplo, el recuento total de [eventos personalizados](https://experienceleague.adobe.com/es/docs/analytics/components/metrics/custom-events) de Adobe Analytics 1-100 se puede comparar entre Adobe Analytics tradicional y Customer Journey Analytics (se hayan vinculado o no). Las [diferencias en las capacidades](/help/getting-started/aa-vs-cja/cja-aa.md)), como la deduplicación de eventos entre Customer Journey Analytics y en Adobe Analytics tradicional, puede causar discrepancias entre ambos productos.

+++

## Mapa de identidad

+++ ¿Puede Customer Journey Analytics utilizar los campos del mapa de identidad?

Sí, Customer Journey Analytics puede usar los campos del mapa de identidad para la vinculación [basada en campos](/help/stitching/fbs.md#identitymap) y [basada en gráficos](/help/stitching/gbs.md#identitymap).

+++

## Cambiar a la vinculación basada en gráficos

+++ ¿Será necesario volver a ingerir los datos para cambiar de la vinculación basada en campos a la basada en gráficos?

No es necesario volver a ingerir los datos en Experience Platform. Sin embargo, es necesario volver a configurar los datos en Customer Journey Analytics. Siga estos pasos:

1. Configure el nuevo conjunto de datos vinculado basado en gráficos mediante la vinculación basada en gráficos.
1. Cree una nueva conexión temporal con un período de tiempo muy corto de datos.
1. Configure el nuevo conjunto de datos basado en gráficos como parte de esta conexión temporal.
1. Verifique con esta nueva conexión temporal si la vinculación basada en gráficos funciona correctamente.
1. Si la vinculación basada en gráficos funciona según lo esperado, solicite cualquier relleno adicional para el conjunto de datos basado en gráficos y, a continuación, intercambie el conjunto de datos basado en campos en su conexión original con el nuevo conjunto de datos basado en gráficos.
1. Quite la conexión temporal.

+++

## Interrupción en el sistema de informes

+++ ¿Se produciría alguna interrupción en los informes existentes?

No, si sigue los pasos descritos anteriormente. De lo contrario, solicite asistencia adicional a Adobe Consulting.

+++

## Habilitación de un conjunto de datos para el servicio de identidad

+++ ¿Cómo se habilita un conjunto de datos solo para el servicio de identidad? 

Asegúrese de que haya un conjunto de datos habilitado para que el servicio de identidad utilice el conjunto de datos en la vinculación basada en gráficos.

No es necesario tener licencia para que la plataforma de datos de clientes en tiempo real utilice la vinculación basada en gráficos. La vinculación basada en gráficos se basa en un gráfico de identidad disponible y no en perfiles de clientes en tiempo real.

Para comprobar un conjunto de datos existente y habilitar el conjunto de datos solo para el servicio de identidad, use una solicitud `PATCH` para el extremo `/datasets` que solo use la etiqueta `unifiedIdentity`. Por ejemplo:

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

Cualquier uso de la etiqueta `unifiedProfile` en la solicitud, aunque no tenga licencia para el perfil de datos de clientes en tiempo real, devuelve un error.

Consulte [Creación de un conjunto de datos habilitado para el perfil y la identidad](https://experienceleague.adobe.com/es/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset) para obtener más información.

+++ 


## Valores de área de nombres enlazados

+++ ¿Por qué los valores de área de nombres enlazados no siempre coinciden con el valor de área de nombres de identidad que podría utilizar en otro conjunto de datos dentro de la conexión de CJA?

De forma predeterminada, los valores de área de nombres enlazados están en minúsculas. Así, `custEmail` se convierte en `custemail`. Si tiene otro conjunto de datos con un valor de área de nombres de identidad de `custEmail`, los dos valores no coinciden. Para evitar este comportamiento en los informes, podría usar la función de campo derivada [lowercase()](/help/data-views/derived-fields/derived-fields.md#lowercase) para hacer coincidir los valores del área de nombres de identidad.

+++
