---
title: Datos de resumen
description: Detalles e información sobre cómo utilizar y configurar datos de resumen en una vista de datos.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 98%

---

# Datos de resumen

Datos de series temporales que no están vinculadas a un ID de persona individual. Los datos de resumen representan datos agregados en un nivel diferente de agregación, por ejemplo campañas. Puede utilizar estos datos en Customer Journey Analytics para admitir varios casos de uso. Por ejemplo, datos que contengan una fecha y un único valor de métrica, o datos que contengan varias dimensiones y métricas.

A continuación, estos datos de resumen se pueden utilizar para presentar indicadores de rendimiento de alto nivel o realizar análisis. Algunos ejemplos de datos de resumen pueden ser impresiones publicitarias, aperturas de correo electrónico, el gasto en publicidad, el coste de un producto vendido, índices de S&amp;P, etc. También puede utilizar datos de resumen para cargar objetivos o metas por hora o por día.

>[!NOTE]
>
>Los datos de resumen son datos de series temporales de un conjunto de datos de resumen. Ese conjunto de datos de resumen se basa en un esquema que utiliza la clase Métricas de resumen XDM como clase base.
>Solo se admiten datos de series temporales basados en horas o días.

>[!TIP]
>
>Puede configurar una conexión, una vista de datos y, posteriormente, elaborar un informe **solo** sobre los datos de resumen. No es necesario tener datos de evento, perfil o consulta adicionales como parte de la configuración.


## Ejemplo

Un ejemplo del uso de datos de resumen es la combinación de datos de campañas de publicidad resumidos con datos del flujo de navegación en el sitio para la creación de informes.

### Datos de resumen

Los datos del resumen contienen los siguientes datos sobre campañas publicitarias.

| Código de campaña | Impresiones | Coste |
|---|---:|---:|
| abc123 | 1250 | 1500 USD |
| def456 | 775 | 650 USD |
| ghi789 | 500 | 500 USD |


### Datos de evento

Los datos del flujo de navegación en el sitio contienen los eventos siguientes.

| Código de seguimiento | Clics | Ingresos |
|---|---:|---:|
| abc123 | 1250 | 7200 USD |
| def456 | 775 | 1250 USD |
| ghi789 | 500 | 750 USD |

### Datos combinados

Tal como se explica en [Conjunto de datos de eventos combinados](/help/connections/combined-dataset.md), al definir una conexión, Customer Journey Analytics crea un conjunto de datos de eventos combinados general. Al configurar la vista de datos para dimensiones que se originan en un conjunto de datos de resumen, hay opciones disponibles para agrupar y ocultar dimensiones como preparación para la creación de informes en Workspace. Específicamente para los datos de resumen, los datos de resumen se combinan con los datos de evento, según la configuración de [componente de grupo de datos de resumen](component-settings/summary-data-group.md).

| Código de seguimiento | Código de campaña | Impresiones | Coste | Clics | Ingresos |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1250 | 1500 USD | 1250 | 7200 USD |
| def456 | def123 | 775 | 650 USD | 775 | 1250 USD |
| ghi789 | ghi789 | 500 | 500 USD | 500 | 750 USD |



### Creación de informes

La combinación de los datos de evento resumidos y los datos del flujo de navegación en el sitio le permite informar en Workspace sobre la rentabilidad de la inversión en publicidad (ROAS).

| Código de seguimiento | Impresiones | Coste | Clics | Ingresos | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1250 | 1500 USD | 1250 | 7200 USD | 4,80 |
| def456 | 775 | 650 USD | 775 | 1250 USD | 1,92 |
| ghi789 | 500 | 500 USD | 500 | 750 USD | 1,50 |


### Datos de búsqueda

Si desea crear un informe con una dimensión definida en un conjunto de datos de búsqueda adicional (por ejemplo, el nombre de la campaña), debe seguir estos pasos adicionales:

1. Cree un nuevo campo derivado que utilice la función [Búsqueda](/help/data-views/derived-fields/derived-fields.md#lookup) para buscar el nombre de campaña del conjunto de datos de búsqueda. En la definición de la función [Búsqueda](/help/data-views/derived-fields/derived-fields.md#lookup) se usa la coincidencia entre el código de campaña y el código de seguimiento para buscar el nombre de la campaña.
1. Añada el campo derivado recién creado como un componente de dimensión a la vista de datos.
1. Configure el componente de dimensión de nombre de campaña (del conjunto de datos de búsqueda) para que tenga una agrupación de datos de resumen con el campo derivado recién creado.

Consulte el caso de uso [Ingesta e informe de datos de resumen](/help/use-cases/data-views/summary-data.md) para ver un artículo detallado sobre cómo usar, informar y analizar datos de resumen en Customer Journey Analytics.


## Requisitos previos

Para utilizar correctamente los datos de resumen en los informes y análisis, se aplican una serie de requisitos previos. Las secciones siguientes detallan estos requisitos previos.

### Granularidad y zona horaria

Al configurar el conjunto de datos que contiene los datos de resumen en Customer Journey Analytics, observa que la granularidad se deriva automáticamente de los datos. Las selecciones para **[!UICONTROL Marca de tiempo]** y el menú desplegable **[!UICONTROL Zona horaria]** están deshabilitadas porque ambas se derivan de la definición del esquema.

#### Granularidad

No puede combinar y hacer coincidir la granularidad horaria y diaria de los datos de resumen en un conjunto de datos (o con diferentes conjuntos de datos), utilizando un esquema de datos de resumen. Por ejemplo, si tiene datos de resumen granulares diarios y horarios para los datos de campañas publicitarias, necesita dos esquemas: uno para los datos de resumen diario y otro para los datos de resumen horario. A continuación, cargue los datos granulares relevantes en conjuntos de datos asociados con el esquema adecuado (por ejemplo, cargue datos por hora en un conjunto de datos asociado con el esquema de datos de resumen por hora).

#### Zona horaria

La zona horaria de los datos de resumen se define en el nivel de esquema de resumen en Experience Platform. La zona horaria solo se aplica a los datos granulares por hora.

- Para la granularidad diaria, Experience Platform supone UTC, a menos que se incluya un desplazamiento de zona horaria en la marca de tiempo. Al añadir el conjunto de datos de resumen que contiene los datos de resumen diarios, Customer Journey Analytics ignora el conjunto de definiciones de zona horaria establecido en el esquema y respeta el día asociado a la marca de hora de los datos del conjunto de datos.
- Para la granularidad horaria, Customer Journey Analytics respeta la zona horaria configurada en el esquema de datos de resumen en Experience Platform al interpretar la marca de tiempo. En la tabla que figura a continuación se proporcionan algunos ejemplos de esta interpretación.

  | Datos de origen de marca de tiempo <br/> | Esquema de zona horaria<br/> | Marca de tiempo<br/>Experience<br/>Platform | Vista de <br/>datos de zona horaria<br/> | Marca de tiempo<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 29-07-2024T01:00:00 | *GMT predeterminado* | 29-07-2024T01:00:00 | GMT | 29-07-2024T01:00:00 |
  | 29-07-2024T01:00:00 | *GMT predeterminado* | 29-07-2024T01:00:00 | PST | 28-07-2024T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predeterminado* | 30-07-2024T06:00:00 | GMT | 30-07-2024T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predeterminado* | 2024-07-30T06:00:00 | PST | 29-07-2024T23:00:00 |
  | 02-08-2024 | *GMT predeterminado* | 02-08-2024-02T00:00:00 | IST | 02-08-2024-02T05:00:00 |
  | 29-07-2024-29T01:00:00 | `America/`<br/>`Los_Angeles` | 28-07-2024-T18:00:00 | PST | 28-07-2024T18:00:00 |
  | 30-07-2024-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 30-07-2024-30T17:00:00 | CET | 30-07-2024-30T08:00:00 |

  Para las zonas horarias con una diferencia de 30 minutos (por ejemplo, IST, hora estándar de India), la diferencia de 30 minutos se elimina al informar sobre datos de resumen. Por ejemplo: 12:30 se notifica como 12:00.


Para garantizar que se utiliza la zona horaria adecuada para los datos de resumen granular por hora, debe asegurarse de que el esquema utilizado para los datos de resumen tenga configurada la zona horaria adecuada.

Para configurar la granularidad y la zona horaria del esquema de datos de resumen, debe utilizar la siguiente llamada API, ya que no hay una interfaz de usuario equivalente disponible.

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Consulte [Autenticar y acceder a las API de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/landing/platform-apis/api-authentication) para obtener más información sobre cómo especificar valores para estas variables. |
| `$SCHEMA_ID` | Puede encontrar el ID de su esquema en la interfaz de usuario de Experience Platform. Seleccione su esquema de resumen de la lista de esquemas y busque **[!UICONTROL Uso de API]** > **[!UICONTROL ID de esquema]** en el panel derecho. Utilice ese ID como valor. |
| `$GRANULARITY` | Especifique `hour` o `day` como valor. |
| `$TIMEZONE` | Especifique el valor adecuado del identificador de zona horaria en la columna del identificador de TZ en la [Lista de zonas horarias de la base de datos tz](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Por ejemplo: `America/Los_Angeles`. |

## Configuración de componentes

Asegúrese de que la configuración de los componentes de un grupo de datos de resumen sea la misma. Consulte [Configuración del componente de grupo de datos de resumen](component-settings/summary-data-group.md#same-component-settings) para obtener más información.

>[!MORELIKETHIS]
>
>- Consulte el artículo [Uso de datos de resumen](/help/use-cases/data-views/summary-data.md) para ver un ejemplo de caso de uso detallado sobre cómo utlizar los datos de resumen e informar sobre ellos.
>- Blog: [Los datos de resumen favorecen los conjuntos de datos de Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635?profile.language=es)

