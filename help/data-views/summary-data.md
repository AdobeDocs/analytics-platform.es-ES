---
title: Datos de resumen
description: Detalles e información sobre cómo utilizar y configurar datos de resumen en una vista de datos.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 9517d698acf41a25fa972ced32faa75de540a080
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 4%

---


# Datos de resumen

{{release-limited-testing}}

Los datos de resumen son datos de series temporales que no están vinculados a un ID de persona individual. Los datos de resumen representan datos agregados en un nivel diferente de agregación, por ejemplo campañas. Puede utilizar estos datos en Customer Journey Analytics para admitir varios casos de uso. Por ejemplo, datos que contengan una fecha y un único valor de métrica, o datos que contengan varias dimensiones y métricas.

Estos datos de resumen se pueden utilizar para presentar indicadores de rendimiento de alto nivel o realizar análisis. Algunos ejemplos de datos de resumen pueden ser impresiones publicitarias, aperturas de correo electrónico, gasto en publicidad, coste del bien vendido, índices de S&amp;P y mucho más. También puede usar datos de resumen para cargar objetivos por hora o por día.

>[!NOTE]
>
>Los datos de resumen son datos de series temporales de un conjunto de datos de resumen. Ese conjunto de datos de resumen se basa en un esquema que utiliza la clase Métricas de resumen de XDM como clase base.
>Solo se admiten datos de series temporales basados en horas o días.

>[!TIP]
>
>Puede configurar una conexión, una vista de datos y, posteriormente, un informe sobre **solo** datos de resumen. No es necesario tener datos de evento, perfil o búsqueda adicionales como parte de la configuración.


## Ejemplo

Un ejemplo del uso de datos de resumen es la combinación de datos de campañas de publicidad resumidos con datos del flujo de navegación en el sitio para la creación de informes.

### Datos de resumen

Los datos del resumen contienen los siguientes datos sobre campañas publicitarias.

| Código de campaña | Impresiones | Costo |
|---|---:|---:|
| abc123 | 1.250 | 1.500 $ |
| def456 | 775 | 650 $ |
| ghi789 | 500 | 500 $ |


### Datos de evento

Los datos del flujo de navegación en el sitio contienen los eventos siguientes.

| Código de seguimiento | Pulsaciones | Ingresos |
|---|---:|---:|
| abc123 | 1.250 | 7.200 $ |
| def456 | 775 | 1.250 $ |
| ghi789 | 500 | 750 $ |

### Datos combinados

Como se explica en [Conjunto de datos de evento combinado](/help/connections/combined-dataset.md), al definir una conexión, el Customer Journey Analytics crea un conjunto de datos de evento combinado general. Al configurar la vista de datos para dimensiones que se originan de un conjunto de datos de resumen, hay opciones disponibles para agrupar y ocultar dimensiones como preparación para la creación de informes en Workspace. Específicamente para los datos de resumen, los datos de resumen se combinan con los datos de evento, según la configuración de [componente de grupo de datos de resumen](component-settings/summary-data-group.md).

| Código de seguimiento | Código de campaña | Impresiones | Costo | Pulsaciones | Ingresos |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | 1.500 $ | 1.250 | 7.200 $ |
| def456 | def123 | 775 | 650 $ | 775 | 1.250 $ |
| ghi789 | ghi789 | 500 | 500 $ | 500 | 750 $ |



### Creación de informes

La combinación de los datos de evento resumidos y los datos del flujo de navegación en el sitio le permite informar en Workspace sobre la rentabilidad de la inversión en publicidad (ROAS).

| Código de seguimiento | Impresiones | Costo | Pulsaciones | Ingresos | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | 1.500 $ | 1.250 | 7.200 $ | 4,80 |
| def456 | 775 | 650 $ | 775 | 1.250 $ | 1,92 |
| ghi789 | 500 | 500 $ | 500 | 750 $ | 1,50 |


Consulte el caso de uso [Ingesta e informe de datos resumidos](/help/use-cases/data-views/summary-data.md) para ver un artículo detallado sobre cómo usar, informar y analizar datos resumidos en Customer Journey Analytics.


## Requisitos previos

Para utilizar correctamente los datos de resumen en los informes y análisis, se aplican una serie de requisitos previos. Las secciones siguientes detallan estos requisitos previos.

### Granularidad y zona horaria

Al configurar el conjunto de datos que contiene los datos de resumen en Customer Journey Analytics, observa que la granularidad se deriva automáticamente de los datos. Las selecciones para **[!UICONTROL Marca de tiempo]** y el menú desplegable **[!UICONTROL Zona horaria]** están deshabilitadas porque ambas se derivan de la definición del esquema.

#### Granularidad

No puede combinar y hacer coincidir la granularidad horaria y diaria de los datos de resumen en un conjunto de datos (o con diferentes conjuntos de datos), utilizando un esquema de datos de resumen. Por ejemplo, si tiene datos de resumen granulares diarios y horarios para los datos de campañas publicitarias, necesita dos esquemas: uno para los datos de resumen diario y otro para los datos de resumen horario. A continuación, cargue los datos granulares relevantes en conjuntos de datos asociados con el esquema adecuado (por ejemplo, cargue datos por hora en un conjunto de datos asociado con el esquema de datos de resumen por hora).

#### Zona horaria

La zona horaria de los datos de resumen se define en el nivel de esquema de resumen en Experience Platform. La zona horaria solo se aplica a los datos granulares por hora.

- Para la granularidad diaria, el Experience Platform supone UTC, a menos que se incluya un desplazamiento de zona horaria en la marca de tiempo. Al agregar el conjunto de datos de resumen que contiene los datos de resumen diarios, Customer Journey Analytics ignora la definición de zona horaria establecida en el esquema y respeta el día asociado a la marca de tiempo de los datos del conjunto de datos.
- Para la granularidad horaria, Customer Journey Analytics respeta la zona horaria configurada en el esquema de datos de resumen en Experience Platform al interpretar la marca de tiempo. En el cuadro que figura a continuación se proporcionan algunos ejemplos de esta interpretación.

  | Datos de origen de marca de tiempo <br/> | Timezone<br/>esquema | Marca de tiempo<br/>Experience<br/>Platform | Vista de <br/>datos de zona horaria<br/> | Marca de tiempo<br/>Cliente<br/>Recorrido<br>Analytics |
  |---|---|---|:---|---|
  | 29-07-2024:00:00 | *GMT predeterminado* | 29-07-2024:00:00 | GMT | 29-07-2024:00:00 |
  | 29-07-2024:00:00 | *GMT predeterminado* | 29-07-2024:00:00 | PST | 28-07-202418:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predeterminado* | 30-07-2024:00:00 | GMT | 30-07-2024:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predeterminado* | 30-07-2024:00:00 | PST | 29/07/2024 T23:00:00 |
  | 02-08-2024 | *GMT predeterminado* | 02-08-2024 T00:00:00 | LISTA | 02-08-2024 T05:00:00 |
  | 29-07-2024:00:00 | `America/`<br/>`Los_Angeles` | 28-07-202418:00:00 | PST | 28-07-202418:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 30-07-202417:00:00 | CET | 30-07-2024:00:00 |

  En el caso de las zonas horarias con un desplazamiento de 30 minutos (por ejemplo, IST, Hora estándar de India), el desplazamiento de 30 minutos se pierde al realizar informes con datos de resumen. Por ejemplo: 12:30 aparece como 12:00.


Para asegurarse de que se utiliza la zona horaria adecuada para los datos de resumen granulares por hora, debe asegurarse de que el esquema utilizado para los datos de resumen tenga configurada la zona horaria adecuada.

Para configurar la granularidad y la zona horaria de su esquema de datos de resumen, debe utilizar la siguiente llamada de API, ya que no hay una interfaz de usuario equivalente disponible.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variable | Valor |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Consulte [Autenticar y obtener acceso a las API de Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication) para obtener más información sobre cómo especificar valores para estas variables. |
| `$SCHEMA_ID` | Puede encontrar el ID del esquema en la interfaz de usuario de Experience Platform. Seleccione el esquema de resumen de la lista de esquemas y busque **[!UICONTROL Uso de API]** > **[!UICONTROL ID de esquema]** en el panel derecho. Utilice ese ID como valor. |
| `$GRANULARITY` | Especifique `hour` o `day` como valor. |
| `$TIMEZONE` | Especifique el valor del identificador de zona horaria adecuado en la columna de identificador TZ de la [Lista de zonas horarias de base de datos tz](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Por ejemplo: `America/Los_Angeles`. |

## Configuración de componentes

Asegúrese de que la configuración de los componentes de un grupo de datos de resumen sea la misma. Consulte [Configuración del componente de grupo de datos de resumen](component-settings/summary-data-group.md#same-component-settings) para obtener más información.

>[!MORELIKETHIS]
>
>Consulte el artículo [Ingesta y uso de datos de resumen](/help/use-cases/data-views/summary-data.md) para ver un ejemplo de uso detallado sobre cómo usar y crear informes sobre datos de resumen.
