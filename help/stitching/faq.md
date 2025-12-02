---
title: Preguntas frecuentes sobre vinculación
description: Preguntas frecuentes sobre la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2069'
ht-degree: 23%

---

# Preguntas frecuentes

Estas son algunas de las preguntas más frecuentes sobre la vinculación:

## Desplazamiento entre canales

+++ ¿Cómo puedo usar la vinculación para ver cómo se mueve la gente de un canal a otro?

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Inicie sesión en [Customer Journey Analytics](https://analytics.adobe.com) y cree un proyecto de Workspace en blanco.
2. Seleccione la pestaña **[!UICONTROL ** Visualizaciones **]** de la izquierda y arrastre una visualización de **[!UICONTROL ** Flujo **]** al lienzo de la derecha.
3. Seleccione la ficha **[!UICONTROL ** Componentes **]** de la izquierda y arrastre la dimensión **[!UICONTROL ** ID de conjunto de datos **]** a la ubicación central denominada **[!UICONTROL ** Dimension o Elemento **]**.
4. Este informe de flujo es interactivo. Para expandir los flujos a páginas posteriores o anteriores, seleccione cualquiera de los valores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Puede utilizar un conjunto de datos de búsqueda si desea cambiar el nombre de los elementos de la dimensión de ID de conjunto de datos.

+++

## Reproducir

+++ ¿Hasta dónde llega la vinculación de perfiles de reproducción?

La ventana retrospectiva para la regeneración de claves depende de la frecuencia deseada de reproducción de los datos. Por ejemplo, si configura la vinculación para que reproduzca los datos una vez por semana, la ventana retrospectiva para la regeneración de claves será de siete días. Si configura la vinculación para que reproduzca datos todos los días, la ventana retrospectiva para la regeneración de claves será de un día.

+++

## Dispositivos compartidos

+++ ¿Cómo se gestionan los dispositivos compartidos?

En algunas situaciones, es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID de persona anula el ID persistente, por lo que los dispositivos compartidos se consideran personas independientes (incluso si se originan en el mismo dispositivo).

Consulte el caso de uso [Dispositivos compartidos](/help/use-cases/stitching/shared-devices.md) para obtener más información.

+++

## Muchos ID persistentes

+++ ¿Cómo gestiona la vinculación las situaciones en las que una sola persona tiene muchos ID persistentes?

En algunas situaciones, un usuario individual puede asociarse con muchos ID persistentes. Un ejemplo es una persona que borra las cookies del explorador con frecuencia o que utiliza el modo privado/de incógnito del explorador.

Para la vinculación basada en el campo, el número de ID persistentes es irrelevante en favor del ID de persona. Un solo usuario puede pertenecer a numerosos dispositivos sin que ello afecte a la capacidad de Customer Journey Analytics para crear vínculos entre los distintos dispositivos.

Para la vinculación basada en gráficos, una sola persona puede tener muchos ID persistentes en el gráfico de identidades. La vinculación basada en gráficos utiliza el ID persistente en función del área de nombres especificada. En caso de que haya ID más persistentes para el mismo área de nombres, se utiliza el primer ID persistente lexicográfico.

+++

## Proceso de vinculación

+++ Tras contactar con el equipo de cuentas de Adobe y proporcionarle la información deseada, ¿cuánto tarda en estar disponible el conjunto de datos cuya clave se ha vuelto a generar?

La vinculación en tiempo real está disponible aproximadamente una semana después de que Adobe active la vinculación. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1000 millones de eventos por día) pueden tardar una semana o más.

+++

## Análisis entre dispositivos y análisis entre canales

+++ ¿Cuál es la diferencia entre el análisis entre dispositivos (una función tradicional de Analytics) y el análisis entre canales?

[Análisis entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=es) es una característica específica de la versión tradicional de Adobe Analytics que te permite comprender cómo funcionan las personas entre dispositivos. Ofrece dos flujos de trabajo para vincular datos de dispositivos: vinculación basada en el campo y el gráfico del dispositivo.

El análisis en canales múltiples es un caso de uso específico de Customer Journey Analytics que le permite comprender cómo funcionan las personas en ambos dispositivos y canales. Vincula el ID de persona de un conjunto de datos, lo que permite que ese conjunto de datos se combine sin problemas con otros conjuntos de datos. Esta función funciona de forma similar al de la vinculación basada en el campo de análisis entre dispositivos, pero la implementación es diferente debido a la diferente arquitectura de datos entre Analytics tradicional y Customer Journey Analytics. Consulte [Vinculación](overview.md) y el caso de uso de [análisis en canales múltiples](../use-cases/cross-channel/cross-channel.md) para obtener más información.

+++

## Privacidad

+++ ¿Cómo gestiona la vinculación las solicitudes de privacidad?

Adobe gestiona las solicitudes de privacidad de acuerdo con las leyes locales e internacionales. Adobe ofrece el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) para enviar solicitudes de acceso a datos y de eliminación. Las solicitudes se aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.

>[!IMPORTANT]
>
>El proceso de desvinculación, como parte de las solicitudes de privacidad, cambia a principios de 2025. El proceso actual de desvinculación revincula los eventos con la última versión de identidades conocidas. Esta reasignación de eventos a otra identidad podría tener consecuencias legales indeseables. Para solucionar estos problemas, a partir de 2025, el nuevo proceso de desvinculación actualiza los eventos que están sujetos a la solicitud de privacidad con el ID persistente.
> 

Para ilustrar, imagine los siguientes datos para identidades, eventos antes y después de la vinculación.

| Mapa de identidad | Id | timestamp | ID persistente | espacio de nombres persistente | E/S de persona | área de nombres de persona |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos de eventos | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos vinculado | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona | ID vinculado | espacio de nombres vinculado |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Proceso actual para solicitud de privacidad**

Cuando se recibe una solicitud de privacidad para un cliente con CustID Bob, se eliminan las filas con entradas tachadas. Otros eventos se vuelven a vincular mediante el mapa de identidad. Por ejemplo, el primer ID vinculado del conjunto de datos vinculado se actualiza a **Alex**.

| Mapa de identidad | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona |
|:---:|---|---|---|---|---|---|
| ![EliminarEsquema](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~ID de cliente~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos de eventos | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![EliminarEsquema](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~ID de cliente~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos vinculado | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona | ID vinculado | espacio de nombres vinculado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![EliminarEsquema](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~ID de cliente~~ | ~~Bob~~ | ~~ID de cliente~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Nuevo proceso para solicitud de privacidad**

Cuando se recibe una solicitud de privacidad para un cliente con CustID Bob, se eliminan las filas con entradas tachadas. Otros eventos se vuelven a vincular con el ID persistente. Por ejemplo, el primer ID vinculado en el conjunto de datos vinculado se actualiza a **123**.

| Mapa de identidad | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona |
|:---:|---|---|---|---|---|---|
| ![EliminarEsquema](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~ID de cliente~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos de eventos | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![EliminarEsquema](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~ID de cliente~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de datos vinculado | Id | timestamp | ID persistente | espacio de nombres persistente | ID de persona | área de nombres de persona | ID vinculado | espacio de nombres vinculado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![EliminarEsquema](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~ID de cliente~~ | ~~Bob~~ | ~~ID de cliente~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Valores de ID persistentes en blanco

+++ ¿Qué sucede si el campo de ID persistente de uno o varios eventos está en blanco?

Si el campo de ID persistente está en blanco en un evento de un conjunto de datos que se está vinculando, el ID vinculado para ese evento se determina de una de las dos maneras siguientes:

* Si el campo de ID transitorio no está en blanco, Customer Journey Analytics utiliza el valor de ID transitorio como ID vinculado.
* Si el campo de ID transitorio está en blanco, Customer Journey Analytics también deja en blanco el ID vinculado. En este caso, el ID persistente, el ID transitorio y el ID vinculado están en blanco en el evento. Estos tipos de eventos se pierden de cualquier conexión de Customer Journey Analytics usando el conjunto de datos que se está vinculando, donde el ID vinculado se eligió como ID de persona.

+++


## Valores de ID de persona no definidos

+++ ¿Qué sucede si el campo de ID de persona de uno o varios eventos tiene valores de marcador de posición, como `Undefined`?

Tenga cuidado con el &quot;colapso de persona&quot;, que se produce cuando se aplica la vinculación a datos que utilizan valores de marcador de posición para ID transitorios. En la tabla de ejemplo siguiente, los ID de persona no definidos procedentes de un conjunto de datos procedentes de un sistema CRM se rellenan con el valor &quot;No definido&quot;, lo que da como resultado una representación incorrecta de las personas.

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID transitorio | ID vinculado (después de la reproducción) |
|---|---|---|---|---|
| 1 | 12/12/05/2023:01 | 123 | - | **Cory** |
| 2 | 12/12/05/2023:02 | 123 | Cory | **Cory** |
| 3 | 12/12/05/2023:03 | 456 | No definido | **Sin definir** |
| 4 | 12/12/05/2023:04 | 456 | - | **Sin definir** |
| 5 | 12/12/05/2023:05 | 789 | No definido | **Sin definir** |
| 6 | 12/12/05/2023:06 | 012 | No definido | **Sin definir** |
| 7 | 12/12/05/2023:07 | 012 | - | **Sin definir** |
| 8 | 12/12/05/2023:03 | 789 | No definido | **Sin definir** |
| 9 | 12/12/05/2023:09 | 456 | - | **Sin definir** |
| 10 | 12/12/05/2023:02 | 123 | - | **Cory** |
| | | **4 dispositivos** | **2 personas**:<br/>Se perdieron los eventos 1, 4, 7, 9, 10 | **2 personas**:<br/>Cory, sin autenticar (se ha contraído a una persona) |

+++

## Comparación de métricas

+++ ¿En qué se parecen las métricas de los conjuntos de datos enlazados de Customer Journey Analytics y las de los conjuntos de datos no enlazados de Customer Journey Analytics y las de Adobe Analytics?

Ciertas métricas en Customer Journey Analytics son similares a las métricas en la versión tradicional de Analytics, pero otras son diferentes, según lo que esté comparando. La siguiente tabla compara varias métricas comunes:

| **Datos vinculados de Customer Journey Analytics** | **Datos no vinculados de Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Personas** = Recuento de ID de persona diferentes donde el ID vinculado se elige como ID de persona. **Las personas** pueden ser superiores o inferiores a los **visitantes únicos** en Adobe Analytics tradicional, según el resultado del proceso de identificación entre dispositivos. | **Personas** = Recuento de ID de persona diferentes según la columna seleccionada como ID de persona. **Personas** en los conjuntos de datos del conector de origen de Analytics es similar a **Visitantes únicos** en la versión tradicional de Adobe Analytics si `endUserIDs._experience.aaid.id` se usa como ID de persona en Customer Journey Analytics. | **Visitantes únicos** = Recuento de ID de visitantes diferentes. **Visitantes únicos** pueden no ser los mismos que el recuento de **ECID** distintos. | Consulte [Personas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=es). |
| **Sesiones**: se define en función de la configuración de sesiones en la vista de datos de Customer Journey Analytics. El proceso de identificación entre dispositivos puede combinar sesiones individuales de varios dispositivos en una sola sesión. | **Sesiones**: se define en función de la configuración de sesiones especificada en la vista de datos de Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=es). | **Visitas**: se define en función de la configuración de sesiones especificada en el [grupo de informes virtuales de CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=es). |
| **Eventos** = recuento de filas en los datos enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. Sin embargo, tenga en cuenta las preguntas más frecuentes anteriores sobre las filas con un ID persistente en blanco. | **Eventos** = recuento de filas en los datos no enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. Sin embargo, tenga en cuenta que si algún evento tiene un ID de persona en blanco en los datos no enlazados en el lago de datos de Experience Platform, estos eventos no se incluyen en Customer Journey Analytics. | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es). | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es). |

Otras métricas pueden ser similares en Customer Journey Analytics y Adobe Analytics. Por ejemplo, el recuento total de [eventos personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=es) 1-100 de Adobe Analytics es comparable entre Adobe Analytics tradicional y Customer Journey Analytics (ya se haya vinculado o no). [Diferencias en las capacidades](/help/getting-started/aa-vs-cja/cja-aa.md)), como la deduplicación de eventos entre Customer Journey Analytics y Adobe Analytics, puede causar discrepancias entre los dos productos.

+++

## Mapa de identidad

+++ ¿Customer Journey Analytics puede utilizar los campos del mapa de identidad?

Sí, Customer Journey Analytics puede usar los campos del mapa de identidad para la vinculación [basada en campos](/help/stitching/fbs.md#identitymap) y [basada en gráficos](/help/stitching/gbs.md#identitymap).

+++

## Cambiar a vinculación basada en gráficos

+++ ¿Será necesario volver a ingerir los datos para cambiar de la vinculación basada en el campo a la basada en gráficos?

No es necesario volver a ingerir los datos en Experience Platform, pero deberán reconfigurarse en Customer Journey Analytics. Siga estos pasos:

1. Configure el nuevo conjunto de datos vinculado basado en gráficos mediante la vinculación basada en gráficos.
1. Cree una nueva conexión temporal con un período de tiempo muy corto de datos.
1. Configure el nuevo conjunto de datos basado en gráficos como parte de esta conexión temporal.
1. Compruebe con esta nueva conexión temporal si la vinculación basada en gráficos funciona correctamente.
1. Si la vinculación basada en gráficos funciona según lo esperado, solicite cualquier relleno adicional para el conjunto de datos basado en gráficos y, a continuación, intercambie el conjunto de datos basado en campos en su conexión original con el nuevo conjunto de datos basado en gráficos.
1. Quite la conexión temporal.

+++

## Interrupción en la creación de informes

+++ ¿Se produciría alguna interrupción en los informes existentes?

No si sigue los pasos descritos anteriormente. De lo contrario, solicite asistencia adicional a Adobe Consulting.

+++

## Habilitar un conjunto de datos para el servicio de identidad

+++ ¿Cómo se habilita un conjunto de datos solo para el servicio de identidad? 

Debe asegurarse de que haya un conjunto de datos habilitado para que el servicio de identidad utilice el conjunto de datos en la vinculación basada en gráficos.

No es necesario tener licencia para que Real-Time Customer Data Platform utilice la vinculación basada en gráficos. La vinculación basada en gráficos se basa en un gráfico de identidad disponible y no en perfiles de clientes en tiempo real.

Para habilitar un conjunto de datos solo para el servicio de identidad, use una solicitud `POST` para el extremo `/datasets` que solo use la etiqueta `unifiedIdentity`. Por ejemplo:

```shell
curl -X POST \
  https://platform.adobe.io/data/foundation/catalog/dataSets \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
    "schemaRef": {
        "id": "https://ns.adobe.com/{TENANT_ID}/schemas/31670881463308a46f7d2cb09762715",
        "contentType": "application/vnd.adobe.xed-full-notext+json; version=1"
    },
    "tags": {
       "unifiedIdentity": ["enabled:true"]
    }
  }'
```

Cualquier uso de la etiqueta `unifiedProfile` en la solicitud, aunque no tenga licencia para el perfil de datos del cliente en tiempo real, devuelve un error.

Consulte [Crear un conjunto de datos habilitado para Perfil e Identidad](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#create-a-dataset-enabled-for-profile-and-identity) para obtener más información.

+++ 
