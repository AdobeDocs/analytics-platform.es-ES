---
title: Guía del usuario de CJA para usuarios de Adobe Analytics
description: Qué considerar desde la perspectiva de un usuario cuando su empresa mueve datos de Adobe Analytics a Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 30e02f8865daea5d0f6a669f84714abec25ecd76
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 8%

---

# Guía del usuario de CJA para usuarios de Adobe Analytics

Si su organización está empezando a emplear un Customer Journey Analytics, es posible que observe algunas similitudes y diferencias entre la versión tradicional de Analytics y la de CJA. Esta página pretende explicar estas diferencias para ayudar a su organización a familiarizarse con el nuevo flujo de trabajo de implementación y creación de informes. Esta página también proporciona recursos adicionales sobre nuevos conceptos y pasos adicionales para que su recorrido como analista sea más fácil y exitoso.

Se ha cambiado el nombre de varias funciones de CJA y se han rediseñado para que se ajusten a los estándares del sector. Algunos términos actualizados incluyen segmentos, grupos de informes virtuales, clasificaciones, atributos del cliente y nombres de contenedor. Ya no existen las limitaciones de eVars y props, lo que favorece dimensiones y métricas personalizadas y flexibles.

## Qué no ha cambiado

Gran parte de lo que está familiarizado con los informes no ha cambiado.

* Puede seguir utilizando la potencia de [Analysis Workspace](/help/analysis-workspace/home.md) para analizar los datos. Workspace funciona igual que en la versión tradicional de Adobe Analytics.
* La misma versión de [Tableros de Adobe Analytics](/help/mobile-app/home.md) está disponible y funciona de forma similar entre CJA y la versión tradicional de Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) tiene una nueva interfaz y se ejecuta en PC, Mac y la versión web de Excel.

## Cambios en los informes

Tiene acceso a muchos más datos de canales cruzados para analizar. Por ejemplo, puede crear un proyecto de espacio de trabajo que analice el rendimiento de varios canales

![visualizaciones multicanal](assets/cross-channel.png)

## Cambios en la arquitectura de datos {#architecture}

Customer Journey Analytics obtiene sus datos de Adobe Experience Platform. Experience Platform le permite centralizar y estandarizar los datos y el contenido de los clientes de cualquier sistema o canal y aplica la ciencia de datos y el aprendizaje automático para mejorar el diseño y el envío de las experiencias personalizadas.

Los datos del cliente en la plataforma se almacenan como conjuntos de datos que consisten en un esquema y lotes de datos. Para obtener más información sobre la plataforma, consulte la [Descripción general de arquitectura de Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Su administrador de CJA establece [conexiones](/help/connections/create-connection.md) a conjuntos de datos en Platform. Luego construyen [vistas de datos](/help/data-views/data-views.md) usando esas conexiones. Conceptualmente, las vistas de datos son similares a los grupos de informes virtuales y constituyen la base de los informes en Customer Journey Analytics. Dado que la plataforma obtiene todos los datos para los informes, los grupos de informes ya no existen como contenedores para los datos.

Una conexión permite que el administrador de Analytics integre conjuntos de datos desde [!DNL Adobe Experience Platform] into [!UICONTROL Customer Journey Analytics], incluido en el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe ofrece varias formas de introducir datos en Adobe Experience Platform, incluidos los datos de grupos de informes a través del conector de origen de Adobe Analytics o del SDK web. Las implementaciones existentes de varios grupos de informes se pueden combinar en Platform. Las conexiones y vistas de datos basadas en estos conjuntos de datos pueden combinar datos que existían anteriormente en grupos de informes separados.

## Cambios en el concepto de grupos de informes virtuales {#data-views}

[!UICONTROL Vistas de datos] tome el concepto de grupos de informes virtuales tal como existen hoy en día y expórtelo a [habilitar controles adicionales en los datos](/help/data-views/create-dataview.md) disponible mediante conexiones. Estos cambios hacen que la configuración general, como los intervalos de huso horario y de tiempo de espera de sesión, sea configurable y retroactiva. La configuración de variables individuales, como la atribución y la caducidad, también se puede personalizar en un informe o en un nivel de vista de datos. Estos ajustes también son no destructivos y retroactivos.

Tenga en cuenta que el selector de grupos de informes en la esquina superior derecha ahora le permite elegir entre las vistas de datos disponibles:

![data-view-selector](assets/data-views.png)

Consulte [Ejemplos de uso en vistas de datos](/help/data-views/data-views-usecases.md) para obtener más información sobre este concepto.

## Cambios en el concepto de eVars y props

[!UICONTROL eVars], [!UICONTROL props]y [!UICONTROL events] en la versión tradicional de Adobe Analytics ya no existe en [!UICONTROL Customer Journey Analytics]. Hay disponibles un número ilimitado de elementos de esquema, incluidas dimensiones, métricas y campos de lista. Todos los ajustes de atribución aplicados anteriormente durante el proceso de recopilación de datos se aplican ahora en el momento de la consulta.

## Cambios en el concepto de segmentos

Adobe ha cambiado el nombre del componente &quot;segmentos&quot; a &quot;filtros&quot; para que se ajuste mejor a los estándares del sector y proporcione una mejor distinción con los segmentos de Adobe Experience Platform.\

[!UICONTROL Customer Journey Analytics] ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier elemento de esquema de Platform. Este cambio significa que ninguno de los segmentos existentes es compatible con [!UICONTROL Customer Journey Analytics]. Si desea mover segmentos de Adobe Analytics existentes a Customer Journey Analytics, consulte el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Aunque todavía no puede compartir ni publicar [!UICONTROL filtros] ([!UICONTROL segmentos]) desde [!DNL Customer Journey Analytics] para Experience Platform Unified Profile, esta funcionalidad está en desarrollo.

Además del concepto de cambiar segmentos, también se actualizan los contenedores de segmentos.

* **Los contenedores de visita individual ahora son contenedores de &quot;Evento&quot;**. El contenedor [!UICONTROL Persona] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico.
* **Los contenedores de visita ahora son contenedores de &quot;sesión&quot;**. El contenedor [!UICONTROL Sesión] le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica.
* **Los contenedores de visitante ya están [!UICONTROL Persona] contenedores**. El contenedor [!UICONTROL Persona] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico.

## Cambios en el concepto de métricas calculadas

Las métricas calculadas tienen un nombre similar entre la versión tradicional de Analytics y CJA. Sin embargo, [!UICONTROL Customer Journey Analytics] ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier elemento de esquema de Platform. Este cambio fundamental significa que ninguna de las métricas calculadas existentes es compatible con [!UICONTROL Customer Journey Analytics]. Si desea mover las métricas calculadas de Adobe Analytics al Customer Journey Analytics, consulte el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Cambios en la atribución de variables y la configuración de caducidad

[!UICONTROL Customer Journey Analytics] aplica todas las configuraciones de variables, incluidas la atribución y la caducidad, en el momento del informe. Esta configuración ahora reside en [vistas de datos](/help/data-views/component-settings/persistence.md), y algunos ajustes de variables (como la atribución) se pueden cambiar en proyectos de Workspace.

Puede tener varias versiones de la misma variable en la misma vista de datos. Por ejemplo, puede tener una dimensión Código de seguimiento que caduque pasados 30 días y otra que caduque al final de una sesión. Ambas dimensiones de código de seguimiento utilizan los mismos datos de origen, pero usan diferentes configuraciones de atribución.

También puede tener varias vistas de datos basadas en la misma conexión. Por ejemplo, puede tener una vista de datos con un tiempo de espera de sesión de 30 minutos y otra con un tiempo de espera de sesión de 15 minutos. Ambas vistas de datos aparecen en el selector superior derecho para que pueda realizar una transición sin problemas entre ellas.

## Cambios en el concepto de clasificaciones

Las &quot;clasificaciones&quot; ahora se conocen como &quot;Conjuntos de datos de búsqueda&quot;. Los conjuntos de datos de búsqueda se utilizan para buscar valores o claves encontrados en los datos de evento o perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a los nombres de producto. Consulte [Agregar datos de nivel de cuenta como un conjunto de datos de consulta](/help/use-cases/b2b.md) para un ejemplo de uso.

## Cambios en el concepto de atributos del cliente

Los &quot;atributos del cliente&quot; ahora se conocen como &quot;conjuntos de datos de perfil&quot;. Los conjuntos de datos de perfil contienen datos que se aplican a sus visitantes, usuarios o clientes en la variable [!UICONTROL Evento] datos. Por ejemplo, le permite cargar datos CRM sobre sus clientes. Puede elegir qué ID de persona desea incluir. Cada conjunto de datos definido en [!DNL Experience Platform] tiene su propio conjunto de uno o más ID de persona definidos.

## Cambios en la forma en que el Adobe identifica a los visitantes

CJA amplía los conceptos de identidades más allá de los ECID para incluir cualquier ID que desee utilizar, incluidos el ID de cliente, el ID de cookie, el ID de título, el ID de usuario, el código de seguimiento, etc. Usar un ID de área de nombres común en conjuntos de datos o usar [Análisis en canales múltiples](/help/connections/cca/overview.md) ayuda a vincular a las personas en diferentes conjuntos de datos. Cualquier usuario que configure un proyecto de Workspace en CJA debe comprender los ID utilizados en los conjuntos de datos. Consulte el siguiente vídeo que resalta el uso de identidades en el Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Cambios en el concepto del elemento de dimensión Tráfico bajo

En la versión tradicional de Analytics, una variable que recibe demasiados valores únicos comienza a agrupar los elementos de dimensión en `Low-Traffic`. El Customer Journey Analytics tiene muchas limitaciones a los campos de alta cardinalidad. Los cambios en la arquitectura de informes permiten a Analysis Workspace crear informes sobre muchos elementos de dimensión únicos más. Consulte [Larga cola](../analysis-workspace/workspace-faq/long-tail.md) para obtener más información sobre cómo CJA optimiza el sistema de informes para dimensiones con muchos valores únicos.
