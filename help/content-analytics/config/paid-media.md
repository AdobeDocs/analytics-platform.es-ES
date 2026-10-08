---
title: Configuración automática de medios de pago de Content Analytics
description: Obtenga información acerca de la configuración automática de conjuntos de datos, conexiones, vistas de datos y mucho más.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 2727dce145b996192ac873dd43d5106b011ff736
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 4%
---
# Configuración automática de medios de pago

Al habilitar el canal de medios de pago en Content Analytics y guardar la configuración, Adobe actualiza la conexión seleccionada y las vistas de datos con la configuración de creación de informes para los conjuntos de datos de medios de pago. No es necesario que vuelva a crear las dimensiones, métricas, lógica de búsqueda o grupos de datos de resumen predeterminados.

Se crean tres capas de objetos:

| Objetos | Contiene | Finalidad |
| --- | --- | --- |
| Conjuntos de datos resumidos | Datos de rendimiento de la red de Advertising a nivel de anuncio, ubicación de experiencia o recurso, con desgloses demográficos y geográficos independientes cuando se admite. | Le permite medir la entrega, los clics, los gastos y los resultados de los informes de la red de publicidad |
| Conjuntos de datos de búsqueda de metadatos y atributos | Detalles de cuenta, campaña, grupo de publicidad, publicidad, experiencia y recursos; atributos creativos de Content Analytics. | Permite crear informes con nombres reconocibles, detalles creativos, miniaturas y atributos de contenido en lugar de utilizar identificadores. |
| Configuración y componentes de vista de datos | Dimensiones, métricas, métricas calculadas, campos derivados y grupos de datos de resumen. | Permite generar análisis de Workspace sin reconstruir manualmente las relaciones entre estos conjuntos de datos. |

Al habilitar los medios de pago, no se conectan automáticamente los datos de medios de pago a los pedidos, las reservas o los ingresos del sitio. La correlación entre los datos del evento de experiencia y los datos de medios de pago requiere una asignación de claves de seguimiento y una configuración de informes específicas del cliente.

## Conjuntos de datos resumidos

La siguiente ilustración muestra cómo se generan los conjuntos de datos de resumen al habilitar el canal de medios de pago en Content Analytics para una o varias de las redes de anuncios. Las API relevantes de las redes de publicidad disponibles se utilizan para descargar y transformar datos de experiencia, recursos y publicidad en potencialmente seis conjuntos de datos de resumen.

![Generación de medios de pago de conjuntos de datos de resumen](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

Los conjuntos de datos de resumen que se crean están determinados por la red de publicidad específica. No todas las redes de anuncios para las que se ha configurado un conector de origen generan los seis conjuntos de datos de resumen posibles. Consulte la tabla siguiente para obtener una descripción general de los conjuntos de datos de resumen con la siguiente información:

* Nombre del conjunto de datos de resumen, tipo de evento y sufijo de componente
* Entidad
* Desgloses
* Qué conjuntos de datos se han rellenado ![Marca de verificación](/help/assets/icons2/Checkmark.svg) para las siguientes redes:
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat y TikTok se encuentran en la fase de prueba limitada de su versión y es posible que aún no estén disponibles en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Customer Journey Analytics, consulte [lanzamientos de características de Customer Journey Analytics](/help/release-notes/releases.md)
    >


* lo que representa cada fila de un conjunto de datos de resumen.

| Conjunto de datos de resumen<br/>Tipo de evento<br/>Sufijo de componente | Entidad | Desglose | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Cada fila representa |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Publicidad | ninguna | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de un anuncio sin desgloses demográficos o geográficos. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Publicidad | edad, sexo | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de un anuncio desglosado por edad y sexo. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Publicidad | país, región | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de un anuncio desglosado por país y región. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experiencia | plataforma, posición | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario asociado a la experiencia creativa de un anuncio, desglosado por plataforma y posición. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Activo | ninguna | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | Rendimiento diario de nivel de recurso en su contexto de publicidad/campaña, sin desglose demográfico o geográfico. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Activo | edad, sexo | ![Marca de verificación](/help/assets/icons2/Checkmark.svg) | | | | | Rendimiento diario a nivel de recurso en su contexto de publicidad/campaña, desglosado por edad y sexo. |


En esta tabla se describe la cobertura del conjunto de datos, no se garantiza que cada métrica o campo de metadatos esté rellenado por una red determinada. Compruebe los campos necesarios para el análisis. Un campo no disponible o un desglose no admitido no es lo mismo que un valor cero medido para un campo.

Los conjuntos de datos de búsqueda independientes describen Cuenta, Campaña, Grupo de publicidad, Publicidad, Experiencia y Recurso. Proporcionan nombres y metadatos mediante GUID de entidad. No existe un emparejamiento uno a uno entre los conjuntos de datos de resumen y los seis conjuntos de datos de búsqueda.

La agrupación de datos de resumen reúne dimensiones equivalentes; la agrupación no suma los seis totales de métricas de rendimiento.

## Componentes

El canal de medios de pago de Content Analytics, una vez activado, también genera una serie de componentes de vista de datos. Estos componentes se proporcionan con un sufijo de componente a componentes con nombres similares distintos entre sí.

### Métricas

Las distintas redes de anuncios devuelven desgloses de rendimiento diferentes. Content Analytics conserva esas distinciones en lugar de tratar cada versión de una métrica como intercambiable.

Por ejemplo:

| Componente | Significado | Análisis inicial adecuado |
| --- | --- | --- |
| Clics \| Resumen de publicidad | Clics notificados en el nivel sin desglose de anuncios | Rendimiento de la campaña o del anuncio |
| Clics \| Resumen de recursos | Clics notificados en el nivel de recurso | Rendimiento de recursos de Creative |
| Clics \| Información geográfica del anuncio | Clics del informe de ubicación geográfica de la publicidad | Rendimiento por país o región |
| Clics \| Ubicación de la experiencia | Clics del informe de ubicación de la experiencia | Rendimiento de Creative por ubicación |

Cada componente de métrica de clics sirve para un contexto de informe diferente. No puede simplemente sumar estos componentes de métricas en un total general. La misma actividad publicitaria subyacente se puede representar en más de un conjunto de datos de resumen.

### Dimensiones

Cada conjunto de datos de resumen contiene ID y GUID. El identificador es la identidad (de cuenta, campaña, grupo de anuncios, anuncio, experiencia y recurso) proporcionada por la red de anuncios y es único **en** los datos de la red de anuncios. El GUID es una identidad proporcionada por Adobe (para cuenta, campaña, grupo de anuncios, anuncio, experiencia y recurso) y es único **en** redes de anuncios. Los identificadores y GUID se utilizan para buscar los nombres y metadatos correspondientes.

### Campos derivados

Los campos derivados forman parte de la configuración automática de creación de informes. Los campos derivados traducen los identificadores en nombres y metadatos, exponen atributos creativos y admiten dimensiones equivalentes utilizadas en las fuentes de informes. No crean actividad publicitaria adicional ni atribuyen automáticamente una conversión de sitio web.

Utilice el mismo desglose para las métricas de un análisis y las dimensiones que admite ese desglose. Tenga en cuenta que los totales demográficos y geográficos no son necesariamente iguales a los totales sin desglose de una red de publicidad y no implican un error de ingesta.

## Informes y análisis

Una vez que haya terminado la configuración y la ingesta de medios de pago de Content Analytics, puede empezar con los informes y análisis. Consulte la tabla siguiente para ver algunos ejemplos. Utilice las dimensiones agrupadas canónicas cuando estén disponibles y elija las métricas en el nivel de sistema de informes correspondiente.

| Pregunta empresarial | Nivel inicial | Filas y desgloses | Inicio de métricas | Límite importante |
| --- | --- | --- | --- | --- |
| ¿Qué rendimiento tienen mis campañas y anuncios? | Resumen de publicidad | Nombre de campaña, Nombre de grupo de publicidad, Nombre de publicidad; opcionalmente Red de publicidad y Nombre de cuenta | Impresiones \| Resumen de publicidad, Clics \| Resumen de publicidad, Gasto \| Resumen de publicidad, CTR y CPC coincidentes | Utilice un nivel para los totales de envío/gasto; valide la moneda antes de combinar cuentas |
| ¿Qué recursos creativos obtienen la respuesta más sólida? | Resumen de recursos | Nombre del recurso (medios de pago), identidad del recurso; red de publicidad opcional | Impresiones \| Resumen de recursos, Clics \| Resumen de recursos, Tasa de pulsaciones \| Resumen de recursos | Se trata del rendimiento de los recursos informado por la red, no una prueba de una conversión in situ posterior |
| ¿Qué características de imagen están asociadas con el rendimiento? | Resumen de recursos | Etiquetas de recursos, objetos de recursos, categorías de personas de recursos, escenas de recursos u otros atributos de recursos disponibles | Impresiones, clics y CTR del resumen de recursos | La extracción de atributos debe estar disponible; las categorías de atributos multivalor pueden superponerse |
| ¿Qué características de mensajería están asociadas con el rendimiento de pago? | Ubicación de experiencia | Palabras clave de experiencia, tonos de experiencia, estrategias de persuasión de experiencia u otros atributos de experiencia disponibles; opcionalmente, Plataforma y ubicación | Impresiones \| Ubicación de la experiencia, Clics \| Ubicación de la experiencia, CTR coincidente | Requiere atributos de experiencia rellenados; los resultados son específicos de la ubicación y describen la asociación, no el impacto causal |
| ¿Qué ubicaciones funcionan mejor? | Ubicación de experiencia | Nombre de experiencia, plataforma, ubicación | Impresiones \| Ubicación de la experiencia, Clics \| Ubicación de la experiencia, CTR coincidente | Las definiciones de ubicación y los valores disponibles varían según la red de publicidad |
| ¿En qué se parecen los anuncios, activos y experiencias de Meta y Google? | Resumen de anuncio, Resumen de recursos o Ubicación de experiencia, seleccionados para la pregunta | Agregar una red con la campaña, el recurso o la dimensión de experiencia adecuados | El mismo nivel y definición de métrica para ambas redes | Comparar solo los campos rellenados por ambas redes; Google no rellena los tres resúmenes demográficos/geográficos en este modelo |

Estos informes pueden revelar asociaciones entre atributos creativos y rendimiento, no probar que un atributo haya causado un resultado.

Evitar combinaciones incompatibles: El nombre del recurso (medios de pago) con las métricas de resumen de publicidad no sustituye a un informe de recursos. Utilice las métricas de Resumen de recursos para las métricas de Análisis de recursos y Geografía de anuncios para el análisis de regiones. Las celdas vacías o nulas de un emparejamiento incompatible no deben interpretarse como prueba de que no hay actividad.

### Ejemplo de rendimiento de campaña de publicidad

Desea informar sobre el rendimiento de la campaña en el nivel de anuncio. En Analysis Workspace, utilice el nombre de la campaña como dimensión (filas) y utilice las métricas como se describe en la tabla siguiente. Cada métrica tiene el mismo sufijo de componente.

| Métricas | Nivel de informes |
| --- | --- |
| Impresiones | Resumen de publicidad |
| Clics | Resumen de publicidad |
| Gastar | Resumen de publicidad |
| Tasa de clics | Resumen de publicidad |
| Costo por clic | Resumen de publicidad |

Si lo desea, puede desglosar Nombre de campaña por Nombre de anuncio, pero mantener las cinco columnas en el nivel de Resumen de anuncio.

Para investigar recursos individuales, utilice una tabla independiente con Nombre del recurso (medios de pago) y las columnas Resumen del recurso coincidentes. No agregue los totales de las dos tablas.

### Ejemplo de anuncios de mejor rendimiento de red

¿Quiere saber dónde está el mejor rendimiento de sus anuncios de Meta?

Para investigar, utilice desgloses adicionales para la geografía y la demografía. Utilice el nombre de la campaña o el nombre del anuncio como dimensión y utilice las métricas como se describe en la siguiente tabla. Cada métrica tiene el mismo sufijo de componente.

| Métricas | Nivel de informes |
| --- | --- |
| Impresiones | Geo del anuncio |
| Clics | Geo del anuncio |
| Gastar | Resumen de publicidad |
| Tasa de clics | Geo del anuncio |
| Costo por clic | Resumen de publicidad |


