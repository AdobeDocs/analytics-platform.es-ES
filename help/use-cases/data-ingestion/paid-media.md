---
title: Ingesta De Datos De Medios De Pago En Customer Journey Analytics
description: Obtenga información sobre cómo introducir datos de medios de pago a través de los conectores de origen de Adobe Experience Platform y preparar conexiones, vistas de datos y métricas en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '1198'
ht-degree: 0%
---

# Ingesta y uso de datos de medios de pago

Los datos de medios de pago incluyen el rendimiento de la publicidad y los metadatos de plataformas como [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok] y [!DNL LinkedIn]. En esta guía se explica cómo introducir esos datos en Adobe Experience Platform y ponerlos a disposición en Customer Journey Analytics para la creación de informes y análisis.

Los datos de medios de pago suelen pasar por tres etapas:

1. Las plataformas Advertising proporcionan datos de campaña, publicidad, recursos y rendimiento.
1. Adobe Experience Platform ingiere esos datos a través de un conector de origen y los almacena en los conjuntos de datos de medios de pago estándar.
1. Customer Journey Analytics expone los conjuntos de datos a través de una conexión y una vista de datos para que pueda analizar los datos en Workspace.

Los datos de medios de pago se incorporan mediante conectores de origen de Experience Platform. Por ejemplo, puede utilizar el conector [!DNL Meta Ads] en la categoría Advertising. Cuando conecta una fuente compatible, Adobe aprovisiona los conjuntos de datos de medios de pago estándar en función del esquema de medios de pago global y los grupos de campos.

## Requisitos previos

Asegúrese de tener el siguiente acceso en Experience Platform:

* Permiso para ver y administrar orígenes.
* Permite crear esquemas, conjuntos de datos y flujos de datos.
* Una zona protegida seleccionada para funcionar en. Elija la zona protegida antes de continuar con los pasos de configuración.

Si usa [!DNL Meta Ads] como origen, asegúrese de que también cumple los siguientes requisitos previos:

* Cuenta de [!DNL Meta Business Manager] con al menos una cuenta de anuncios activa que contenga campañas, conjuntos de anuncios, anuncios y recursos.
* Una aplicación [!DNL Meta] autorizada para [!DNL Graph API] y [!DNL Marketing API], configurada en la consola de desarrollador de [!DNL Meta] y vinculada a [!DNL Business Manager].
* Se aprobaron `ads_read` y `ads_management` ámbitos para la aplicación.
* Acceso de nivel de anunciante o superior para el usuario que autoriza la conexión.
* Acceso verificado a las cuentas de publicidad deseadas en la interfaz de usuario de [!DNL Meta].

La autenticación al conector usa [!DNL OAuth 2.0]. Durante la configuración, inicie sesión y conceda acceso al conector. Dado que los tokens de acceso caducan, debe prepararse para volver a autorizar la conexión si se revoca la concesión.

## Modelo de datos

La [configuración automática de medios pagados de Content Analytics](/help/content-analytics/config/paid-media.md) explica en detalle el modelo de datos de medios pagados. Esa configuración automática crea y configura los conjuntos de datos y componentes necesarios en general y para analizar contenido específicamente.

Para comprender el modelo de datos de medios de pago, consulte esta documentación. Utilícelo para decidir qué conjuntos de datos utilizar en Customer Journey Analytics. Los conectores de origen configurados generan estos conjuntos de datos.

## Ingesta de datos de medios de pago

Utilice el siguiente proceso para conectar un origen e introducir datos de medios de pago en Experience Platform:

1. Compruebe que tiene los permisos de origen de Experience Platform y el acceso a la plataforma de publicidad necesarios.
1. En Experience Platform, vaya a **[!UICONTROL Sources]** > **[!UICONTROL Catalog]** > **[!UICONTROL Advertising]**.
1. Asegúrese de que está en la zona protegida que contiene los conjuntos de datos de medios de pago.
1. Seleccione el conector que desee utilizar, como **[!DNL Meta Ads]**. Seleccione **[!UICONTROL Configurar]** para crear una nueva conexión o seleccione **[!UICONTROL Agregar datos]** para agregar más datos a una conexión existente.
1. Autentique con [!DNL OAuth 2.0] iniciando sesión con un usuario que tenga el acceso requerido de nivel de anunciante.
1. Seleccione las cuentas de publicidad, las entidades y los datos de insight que desee introducir.
1. Compruebe que los conjuntos de datos de búsqueda y el conjunto de datos de métricas de resumen estén aprovisionados correctamente.
1. Introduzca la configuración del flujo de datos, confirme los conjuntos de datos de destino y configure la programación de ingesta.
1. Guarde el flujo de datos y supervise las ejecuciones en **[!UICONTROL Orígenes]** > **[!UICONTROL Flujos de datos]**.
1. Compruebe que existen los conjuntos de datos de medios de pago estándar y que contienen datos.

Antes de pasar a Customer Journey Analytics, valide los datos introducidos:

* Confirme que los valores de la entidad `GUID` y el ID nativo se rellenan de manera consistente en las métricas de resumen y los conjuntos de datos de búsqueda.
* Confirme que cada fila de métricas de resumen incluya una marca de tiempo.
* Confirme que los campos clave de los informes, como las dimensiones (por ejemplo: `channel`, `adNetwork`) y las métricas (por ejemplo: `impressions`, `clicks`, `spend`), contengan valores. Tenga en cuenta que no todas las plataformas de origen rellenan algunos campos como `region`.
* Confirme que los valores de moneda y zona horaria son coherentes en todas las cuentas relevantes.

## Usar datos de medios de pago

Customer Journey Analytics no informa directamente sobre los conjuntos de datos de Experience Platform. En su lugar, se exponen los conjuntos de datos a través de una conexión y, a continuación, se crea una vista de datos que define las dimensiones, las métricas y la lógica que se utilizan en los informes.

### Crear o actualizar una conexión

Utilice el siguiente proceso para crear o actualizar una conexión:

1. En Customer Journey Analytics, [cree o edite una conexión existente](/help/connections/create-connection.md).
1. Asegúrese de seleccionar la zona protegida que contiene los conjuntos de datos de medios de pago como parte de la configuración de conexión.
1. Añada los conjuntos de datos de métricas de resumen como datos de resumen. Si hay varios conjuntos de datos de métricas de resumen disponibles, use [search](/help/connections/create-connection.md#add-datasets) para filtrar por las clases `Paid Media` e identificar los conjuntos de datos correctos.
1. Agregue cada conjunto de datos de búsqueda como un conjunto de datos de búsqueda. Una el conjunto de datos de búsqueda a los datos de resumen utilizando los identificadores GUID de entidad correspondientes (las claves globales generadas por Adobe) para cuenta, campaña, grupo de publicidad, publicidad, recurso y experiencia. Algunas plataformas de origen también admiten uniones en valores de ID nativos.
1. Opcionalmente, agregue datos de evento de flujo de navegación si desea relacionar datos de medios pagados agregados con metadatos compartidos como ID, códigos de seguimiento o parámetros `UTM`.
1. Revise la [configuración específica del conjunto de datos](/help/connections/create-connection.md#dataset-settings) para cada conjunto de datos.
1. Guarde la conexión y confirme que la conexión comienza a rellenar los datos.

Los datos de medios de pago son datos acumulados y no dependen de la vinculación de identidad a nivel de persona. Los identificadores de entidad de la tabla de resumen se utilizan para combinar identidades similares en las tablas de búsqueda.

### Creación de una vista de datos

Una vez que la conexión esté lista, debe crear o editar una o más vistas de datos para la conexión:


1. En Customer Journey Analytics, [cree o edite una o más vistas de datos](/help/data-views/create-dataview.md):
1. Defina la configuración predeterminada, como la zona horaria y la moneda.
1. Añada los componentes que necesita para el análisis de medios de pago.

Incluir componentes, como los siguientes:

* **Dimensiones**: campaña, canal, red de publicidad, grupo de publicidad, anuncio, recurso, cuenta, región y tipo de dispositivo.
* **Métricas**: impresiones, clics, tasa de pulsaciones, gasto, conversiones, valor de conversión, participaciones y métricas relevantes de uso compartido de impresiones o vídeos.
* **Campos derivados**: normalice o clasifique dimensiones utilizando la lógica [parsing](/help/data-views/derived-fields/derived-fields.md#url-parse), [expresiones regulares](/help/data-views/derived-fields/derived-fields.md#regex-replace) o [lookup](/help/data-views/derived-fields/derived-fields.md#lookup) para producir valores de canal y campaña coherentes en las redes de anuncios.
* **Agrupación de resumen**: [combina valores relacionados de varios conjuntos de datos en una sola dimensión de informes](/help/data-views/component-settings/summary-data-group.md), como una dimensión de canal de pago unificada.
* **Métricas calculadas**: define métricas de eficiencia reutilizables como CPC, CPM, CPA, CTR y tasa de conversión.

### Crear un proyecto

Para informar y analizar los datos de medios de pago, cree un proyecto en Analysis Workspace.

## Validación

Utilice la siguiente lista de comprobación para validar la implementación.

### Comprobaciones de Adobe Experience Platform

* Confirme que los permisos de origen y el acceso a la plataforma de publicidad estén implementados.
* Confirme que el conector está autenticado y que el flujo de datos se está ejecutando según lo programado.
* Confirme que todos los conjuntos de datos de medios de pago están presentes y rellenados.
* Confirme que los esquemas utilizan las clases de medios pagados globales y los grupos de campos.
* Confirme que los campos de claves de unión, marcas de tiempo y generación de informes de claves se hayan rellenado.

### Comprobaciones de Customer Journey Analytics

* Confirme que la conexión incluye el conjunto de datos de métricas de resumen y los seis conjuntos de datos de búsqueda.
* Confirme que la vista de datos incluye las dimensiones de publicidad necesarias y las métricas de medios de pago.
* Confirme que los campos derivados normalizan los valores de canal y campaña según lo esperado.
* Confirme que la agrupación de resumen consolida los datos de varias redes donde sea necesario.
* Confirme que las métricas calculadas están definidas para las proporciones que utiliza su organización.
* Confirme que los informes de Workspace se alinean con los informes de origen y de plataforma.


>[!MORELIKETHIS]
>
>[Conector de origen de Meta Ads](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>[Configuración automática de medios pagados de Content Analytics](/help/content-analytics/config/paid-media.md)
