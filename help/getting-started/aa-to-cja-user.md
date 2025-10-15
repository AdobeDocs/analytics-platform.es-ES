---
title: Guía para usuarios de Adobe Analytics
description: Qué considerar desde la perspectiva de un usuario cuando su empresa mueve datos de Adobe Analytics a Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 720751130d0f66bddffd13c6f160a85fcc7a7206
workflow-type: tm+mt
source-wordcount: '1454'
ht-degree: 98%

---

# Guía para usuarios de Adobe Analytics

Si su organización está empezando a emplear Adobe Customer Journey Analytics, es posible que observe algunas similitudes y diferencias entre Adobe Analytics y Customer Journey Analytics. Esta página pretende explicar estas diferencias para ayudar a su organización a familiarizarse con el nuevo flujo de trabajo de implementación y creación de informes. Esta página también proporciona recursos adicionales sobre nuevos conceptos y pasos adicionales para que su recorrido como analista sea más fácil y exitoso.

Se ha cambiado el nombre de varias funciones de Customer Journey Analytics y se han rediseñado para que se ajusten a los estándares del sector. Algunos términos actualizados incluyen segmentos, grupos de informes virtuales, clasificaciones, atributos del cliente y nombres de contenedor. Ya no existen las limitaciones de eVars y props, lo que favorece dimensiones y métricas personalizadas y flexibles.

## Qué no ha cambiado

Gran parte de lo que está familiarizado con los informes no ha cambiado.

* Puede seguir utilizando la potencia de [Analysis Workspace](/help/analysis-workspace/home.md) para analizar los datos. Workspace funciona igual que en la versión tradicional de Adobe Analytics.
* La misma versión de [paneles de Adobe Analytics](/help/mobile-app/home.md) está disponible y funciona de forma similar entre Customer Journey Analytics y Adobe Analytics.
* [Report Builder](/help/report-builder/rb-overview.md) tiene una nueva interfaz y se ejecuta en MS Windows, MacOS y la versión web de Excel. (Antes de esta versión de Report Builder, no se podía usar en Mac a menos que se ejecutara en VMware). Esta versión aún no admite solicitudes de datos AA tradicionales.

## Cambios en los informes

Tiene acceso a muchos más datos de canales cruzados para analizar. Por ejemplo, puede crear un proyecto en un espacio de trabajo que analice el rendimiento de varios canales, siempre que su organización incorpore estos conjuntos de datos y los incluya en las vistas de datos utilizadas por Customer Journey Analytics (consulte “Cambios en la arquitectura de datos” a continuación).

![Vista de fuentes de datos que muestra visualizaciones multicanal](assets/cross-channel.png)

## Cambios en la arquitectura de datos {#architecture}

Customer Journey Analytics obtiene sus datos de Adobe Experience Platform. Experience Platform le permite centralizar y estandarizar los datos y el contenido de los clientes de cualquier sistema o canal y aplica la ciencia de datos y el aprendizaje automático para mejorar el diseño y el envío de las experiencias personalizadas.

Los datos del cliente en Experience Platform se almacenan como conjuntos de datos, que consisten en un [esquema](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=es) y lotes de datos. Para obtener más información sobre la plataforma, consulte la [Descripción general de arquitectura de Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=es).

El administrador de Customer Journey Analytics establece [conexiones](/help/connections/create-connection.md) con los conjuntos de datos en Experience Platform. Luego construye las [vistas de datos](/help/data-views/data-views.md) usando esas conexiones. Conceptualmente, las vistas de datos son similares a los grupos de informes virtuales y son la base de la creación de informes en Customer Journey Analytics. Dado que Experience Platform obtiene todos los datos para la creación de informes, los grupos de informes ya no existen como contenedores de datos.

Una conexión le permite a su administrador de Analytics integrar conjuntos de datos de Adobe Experience Platform en Customer Journey Analytics:


<!-- Outdated UI

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->


Adobe ofrece varias formas de introducir datos en Adobe Experience Platform, incluidos los datos de grupos de informes a través del conector de origen de Adobe Analytics o del SDK web. Las implementaciones existentes de varios grupos de informes se pueden combinar en Experience Platform. Las conexiones y vistas de datos basadas en estos conjuntos de datos pueden combinar datos que existían anteriormente en grupos de informes separados.

## Cambios en el concepto de grupos de informes virtuales {#data-views}

Las [!UICONTROL Vistas de datos] toman el concepto de grupos de informes virtuales tal como existen hoy en día y lo amplían para [habilitar controles adicionales en los datos](/help/data-views/create-dataview.md) disponibles mediante conexiones. Estos cambios hacen que la configuración general, como los intervalos de huso horario y de tiempo de espera de sesión, sea configurable y retroactiva. La configuración de variables individuales, como la atribución y la caducidad, también se puede personalizar en un informe o en un nivel de vista de datos. Estos ajustes son no destructivos y retroactivos.

Tenga en cuenta que el selector de grupos de informes en la esquina superior derecha ahora le permite elegir entre las vistas de datos disponibles:

![selector-vista-de-datos](assets/data-views.png)

Consulte [Ejemplos de uso de vistas de datos](/help/use-cases/data-views/data-views-usecases.md) para obtener más información sobre este concepto.

## Cambios en el concepto de eVars y props

Los conceptos de [!UICONTROL eVars], las [!UICONTROL props] y los [!UICONTROL eventos] en Adobe Analytics tradicional ya no existen en [!UICONTROL Customer Journey Analytics]. En Adobe Analytics, las eVars y las props almacenan descripciones de contenido, clientes, campañas, etc. y los eventos cuentan cosas como ingresos, suscripciones o posibles clientes generados. Customer Journey Analytics conserva ambos tipos de datos y puede acceder a ellos del mismo modo, desde el carril izquierdo de Analysis Workspace, en Dimensiones o Métricas, respectivamente.

En Customer Journey Analytics, hay disponibles ilimitados elementos de esquema, incluidas dimensiones, métricas y campos de lista. Se asignan a elementos de esquema ilimitados, incluidas dimensiones, métricas y campos de lista en el Experience Platform. Todos los ajustes de visita y atribución aplicados después de las reglas de procesamiento en Adobe Analytics ahora se aplican en el momento de la consulta en el Customer Journey Analytics.

Con esta flexibilidad, puede encontrarse con situaciones en las que un solo campo de esquema puede utilizarse como dimensiones y como métrica para satisfacer diferentes necesidades de seguimiento.

## Cambios en el concepto de segmentos

Aunque técnicamente los segmentos no se migran de Adobe Analytics a Customer Journey Analytics, puede utilizar la herramienta de migración de componentes para volver a crear los segmentos de Adobe Analytics en Customer Journey Analytics. Los segmentos se vuelven a crear en Customer Journey Analytics en función de las dimensiones y métricas asignadas. Para obtener más información, consulte [prepárese para migrar los componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=es).

Aunque todavía no puede compartir ni publicar [!UICONTROL segmentos] ([!UICONTROL segmentos]) de [!DNL Customer Journey Analytics] en el perfil unificado de Experience Platform, esta funcionalidad está en desarrollo.

Además del concepto de cambiar segmentos, también se actualizan los contenedores de segmentos.

* **Los contenedores de visita individual ahora son [!UICONTROL contenedores] de evento**. El contenedor [!UICONTROL Evento] le permite desglosar la información de la persona en función de eventos individuales.
* **Los contenedores de visita ahora son [!UICONTROL contenedores] de sesión**. El contenedor [!UICONTROL Sesión] le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica.
* **Los contenedores de visitante hora son contenedores de [!UICONTROL Persona]**. El contenedor [!UICONTROL Persona] incluye todas las sesiones y eventos de una persona en un lapso de tiempo específico.

## Cambios en el concepto de métricas calculadas

Las métricas calculadas tienen un nombre similar entre Adobe Analytics y Customer Journey Analytics. Sin embargo, [!UICONTROL Customer Journey Analytics] ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier elemento de esquema de Experience Platform. Este cambio fundamental significa que ninguna de las métricas calculadas existentes es compatible con [!UICONTROL Customer Journey Analytics].


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mover métricas calculadas de Adobe Analytics a Customer Journey Analytics](https://video.tv.adobe.com/v/33880?captions=spa&quality=12&learn=on){target="_blank"} para ver un vídeo de demostración sobre cómo mover métricas calculadas.

>[!ENDSHADEBOX]

## Cambios en la atribución de variables y la configuración de caducidad

[!UICONTROL Customer Journey Analytics] aplica todas las configuraciones de variables, incluidas la atribución y la caducidad, en el momento del informe. Esta configuración ahora reside en [vistas de datos](/help/data-views/component-settings/persistence.md), y algunos ajustes de variables (como la atribución) se pueden cambiar en proyectos de Workspace.

Puede tener varias versiones de la misma variable en la misma vista de datos. Por ejemplo, puede tener una dimensión Código de seguimiento que caduque pasados 30 días y otra que caduque al final de una sesión. Ambas dimensiones de código de seguimiento utilizan los mismos datos de origen, pero usan diferentes configuraciones de atribución.

También puede tener varias vistas de datos basadas en la misma conexión. Por ejemplo, puede tener una vista de datos con un tiempo de espera de sesión de 30 minutos y otra con un tiempo de espera de sesión de 15 minutos. Ambas vistas de datos aparecen en el selector superior derecho para que pueda realizar una transición sin problemas entre ellas.

## Cambios en el concepto de clasificaciones

Las “clasificaciones” ahora se conocen como *Conjuntos de datos de búsqueda*. Los conjuntos de datos de búsqueda se utilizan para buscar valores o claves encontrados en los datos de Evento o de Perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a los nombres de producto.

## Cambios en el concepto de atributos del cliente

Los “atributos del cliente” ahora se conocen como “Conjuntos de datos de perfil”. Los conjuntos de datos de perfil contienen datos que se aplican a sus personas, usuarios o clientes en los datos de [!UICONTROL Evento]. Por ejemplo, le permite cargar datos de CRM sobre sus clientes. Puede elegir qué ID de persona desea incluir. Cada conjunto de datos definido en [!DNL Experience Platform] tiene su propio conjunto de uno o más ID de persona definidos.

## Cambios en la forma en que el Adobe identifica a los visitantes

Customer Journey Analytics amplía los conceptos de identidades más allá de los ECID para incluir cualquier ID que desee utilizar, incluidos el ID de cliente, el ID de cookie, el ID de título, el ID de usuario, el código de seguimiento, etc. Usar un ID de área de nombres común en conjuntos de datos o usar la [Vinculación](../stitching/overview.md) ayuda a vincular a las personas en diferentes conjuntos de datos. Cualquier usuario que configure un proyecto de Workspace en Customer Journey Analytics debe comprender los ID utilizados en los conjuntos de datos. Consulte el siguiente vídeo que resalta el uso de identidades en Customer Journey Analytics:


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Uso de la identidad en Customer Journey Analytics](https://video.tv.adobe.com/v/36395/?captions=spa&quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

## Cambios en el concepto de elemento de dimensión de poco tráfico

En Adobe Analytics tradicional, una variable que recibe demasiados valores únicos comienza a agrupar los elementos de dimensión en [!UICONTROL Poco tráfico]. Customer Journey Analytics tiene menos limitaciones en los campos de alta cardinalidad. Los cambios en la arquitectura de informes permiten a Analysis Workspace crear informes sobre muchos elementos de dimensión únicos más. Consulte [Dimensiones de cardinalidad alta](../components/dimensions/high-cardinality.md) para obtener más información sobre cómo Customer Journey Analytics optimiza los informes para dimensiones con muchos valores únicos.
