---
title: Informar sobre datos de Marketo Engage
description: Obtenga información sobre cómo informar sobre los datos de Marketo Engage en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: fedb1337b32e44fc00989bace6a4d1788043f55f
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 13%

---

# Informar sobre datos de Marketo Engage

Puede aprovechar los conjuntos de datos de Marketo Engage disponibles en Experience Platform para proporcionar valiosas soluciones de análisis e informes a los especialistas en marketing B2B. A continuación, informe sobre estos conjuntos de datos en Customer Journey Analytics.

Tenga en cuenta que:

* La creación de informes de Marketo Engage es la mejor manera de medir y optimizar los programas de marketing directamente en Marketo, y es rápida, prescriptiva y compatible con los expertos en marketing.
* Customer Recorrido Analytics proporciona una solución de análisis mucho más amplia y personalizable para los recorridos de clientes que abarcan varios canales, productos y unidades de negocio, incluidos, entre otros, los datos de Marketo.

Consulte [comparación de informes](#reporting-comparison) para obtener más información.

>[!NOTE]
>
>Puede considerar [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) para obtener mucho más valor de los datos de Marketo Engage. Puede combinar conjuntos de datos de Marketo Engage con conjuntos de datos de cuenta y búsqueda. E informe sobre la cuenta y el nivel de oportunidad en Customer Journey Analytics B2B edition.
>


Para informar sobre los datos de Marketo Engage en Customer Journey Analytics:

+++ &#x200B;1. Asigne campos de datos de origen de Marketo a sus destinos XDM

Asigne los objetos [Personas](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) y [Actividades](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) a sus respectivos campos de destino de esquema XDM.

+++

+++ &#x200B;2. Ingresar datos de Marketo en Adobe Experience Platform

Utilice el [conector de Marketo Engage](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo) para llevar los datos de Marketo a Experience Platform y mantenerlos actualizados mediante aplicaciones conectadas a la plataforma.

+++

+++ &#x200B;3. Configure una conexión con este conjunto de datos en Customer Journey Analytics

Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y Customer Journey Analytics. Consulte [Crear o editar una conexión](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-connections/create-connection).

+++


+++ &#x200B;4. Cree una o varias vistas de datos

Una [vista de datos ](/help/data-views/data-views.md)es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión. Especifica todas las dimensiones y métricas disponibles en Analysis Workspace; en este caso, métricas y dimensiones específicas de Marketo. También especifica de qué columnas obtienen los datos esas dimensiones y métricas. Las vistas de datos se definen a fin de prepararse para la creación de informes en Analysis Workspace.

+++ 

+++ &#x200B;5. Crear informes en Analysis Workspace

Un caso de uso que puede explorar es: ¿Cuántas visitas de páginas web de posibles clientes tuvo entre abril y junio de 2020?

1. Abra [Analysis Workspace](/help/analysis-workspace/home.md) y cree un nuevo proyecto.
Los clientes con B2B/B2P CDP pueden realizar análisis de tipo B2C en Customer Journey Analytics. Los objetos B2B aún no están disponibles.

1. Cree un [segmento](/help/components/segments/seg-create.md) para vistas de páginas web como se indica a continuación: Tipo de evento = web.webpagedetails.pageViews :

   ![Ventana de definición que muestra el evento y el tipo de evento](../assets/marketo-filter.png)

1. Extraiga el segmento que ha creado en la tabla de forma libre: Vistas de página web y, a continuación, extraiga el intervalo de fechas Mes. Esta acción le proporciona visitas a la página web por posibles clientes cada mes:

   ![Tabla de forma libre que muestra los eventos por mes.](../assets/marketo-freeform.png)

1. O tire de las siguientes dimensiones: Clave de persona o Dirección de correo electrónico de trabajo. Esta acción le proporciona las visitas a la página web de cada posible cliente:

   ![Tabla de forma libre que muestra eventos y workEmail.Address y vistas de páginas web.](../assets/marketo-freeform2.png)

Los datos de Marketo Engage en Customer Journey Analytics pueden diferir de lo que se ve en los informes que se encuentran en Marketo Engage.

+++


## Comparación de informes

La siguiente comparación entre los informes de Customer Journey Analytics y Marketo Engage detalla algunas diferencias importantes en las capacidades, flexibilidad, fuentes de verdad y casos de uso de los análisis.

### Customer Journey Analytics

Customer Journey Analytics es una herramienta de análisis avanzada en canales múltiples creada en Adobe Experience Platform. Customer Journey Analytics está diseñado para equipos empresariales que necesitan sistemas de informes potentes, flexibles y personalizables en fuentes de datos digitales y sin conexión.

#### Funcionalidades clave

* **Fuentes de datos**: Pueden combinar varios conjuntos de datos (web, CRM, correo electrónico, centro de llamadas, sin conexión, Marketo, etc.) para generar informes de recorrido del cliente a 360°.
* **Análisis de autoservicio**: arrastre y suelte el espacio de trabajo con paneles y visualizaciones altamente interactivos y personalizables.
* **Atribución avanzada**: admite modelos de atribución complejos, multitáctiles y personalizados en todos los datos conectados, no solo en los programas de marketing.
* **Análisis de audiencias y rutas**: segmentación profunda, cohorte y análisis de rutas entre recorridos de compradores.
* **Perspectivas procesables**: Habilita la orquestación basada en datos (por ejemplo, enviar perspectivas de vuelta a motores de marketing o personalización).
* **Escala empresarial**: Adecuado para organizaciones que necesitan administración empresarial, varias marcas y un gran volumen de datos.

#### Casos de uso habituales de Customer Journey Analytics

* Asignación avanzada del recorrido del cliente en varios canales y puntos de contacto.
* Segmentación y combinación complejas de datos en línea y sin conexión.
* Paneles de KPI personalizados para informes operativos y de nivel ejecutivo.
* Modelado de atribución holístico (más allá de solo digital o correo electrónico).


### Marketo Engage

Marketo Engage ofrece informes en la aplicación centrados en los KPI de automatización de marketing, la medición de programas y campañas y los análisis de impacto de marketing. Todos estos informes están directamente vinculados a la actividad dentro de Marketo.

#### Funcionalidades clave

* **Análisis de marketing nativo**: Informes estándar para correo electrónico, páginas de aterrizaje, campañas, posibles clientes, oportunidades, canalización y atribución de ingresos (primer, último, multitoque).
* **Análisis avanzados de BI (complemento)**: arrastre y suelte el Report Builder personalizado, señale y haga clic para analizar los datos de programas, cuentas o posibles clientes (consulte la Información general reciente de análisis avanzados de BI Analytics).
* **Paneles creados previamente**: Para el rendimiento de la campaña, la eficacia del canal y la contribución de canalización/ingresos.
* **Análisis de programas y canales**: Atribución y ROI específicos de los recorridos administrados por Marketo.
* **Centrado en el marketing**: Se centra en los usuarios que necesitan transparencia en el funnel de marketing: estadísticas de correo electrónico, formularios, campañas inteligentes e impacto en los ingresos.


#### Casos de uso habituales de Marketo Engage

* Rastree y optimice el rendimiento del correo electrónico, el programa y la campaña.
* Atribuir posibles clientes y canalización a tácticas de marketing.
* Monitorice las tendencias de participación y puntúe los posibles clientes.
* Comparta perspectivas con equipos de ventas/marketing sin recursos de ingeniería de datos.
* Acceda a informes listos para usar y fáciles de usar para expertos en marketing.


Consulte a continuación una tabla comparativa rápida sobre las funciones de creación de informes entre Marketo Engage y Customer Journey Analytics:

| Función | Marketo Engage | Customer Journey Analytics |
|---|---|---|
| **Enfoque principal** | Informes de programas de marketing y centrados en campañas. | Informes y análisis de recorrido y comportamiento holísticos y omnicanal. |
| **Fuentes de datos** | Datos generados en y a través de Marketo Engage. | Combina datos de cualquier dato habilitado para Experience Platform, incluidos Marketo, sitio web, aplicación móvil, canales sin conexión y mucho más. |
| **Atribución** | Atribución de un solo toque y de varios toques en datos de Marketo. | Atribución personalizada en canales múltiples en cualquier dato disponible en la solución. |
| **Flexibilidad y creación de informes personalizados** | BI avanzado (complemento) para análisis profundos de programas y cuentas. | Es muy flexible en la forma de crear espacios de trabajo, tableros o informes personalizados con todos los datos disponibles. |
| **Análisis de audiencia** | Filtre y segmente listas de programas, participación y listas inteligentes. | Visualizaciones de persona y recorrido enriquecidas, rutas de audiencia y análisis de superposición de segmentos. |
| **Usuarios previstos** | Especialistas en marketing, operadores de marketing, trabajadores de generación de demanda, funcionarios de ingresos. | Analistas, científicos de datos, estrategas de marketing, profesionales de la experiencia del cliente. |
| **Anulación de duplicación métrica** | Para los informes de rendimiento de correo electrónico, las métricas se deduplican automáticamente por ID de posible cliente, ID de campaña e ID de recurso de correo electrónico. Si se crean varios correos electrónicos a partir del mismo recurso de correo electrónico y se envían al mismo posible cliente desde el mismo programa, estos correos electrónicos solo se contarán como uno. | Sin aplicar filtros y métricas adicionales, los datos de los informes de correo electrónico se presentan como un recuento total del rendimiento del correo electrónico sin [anulación de duplicación de métricas](/help/data-views/component-settings/metric-deduplication.md). |

{style="table-layout:fixed"}
