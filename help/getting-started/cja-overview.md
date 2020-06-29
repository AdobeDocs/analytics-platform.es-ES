---
title: Información general sobre Customer Journey Analytics
description: Introducción a Customer Journey Analytics
translation-type: ht
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: ht
source-wordcount: '1137'
ht-degree: 100%

---


# Información general sobre Customer Journey Analytics

Customer Journey Analytics es una función de Analytics que le permite utilizar la potencia de Analysis Workspace con datos de Adobe Experience Platform. Puede desglosar, filtrar, consultar y visualizar datos de años, y se combina con la capacidad de Platform de albergar todo tipo de esquemas y tipos de datos. Con el **Experience Data Model (XDM)**, los datos se pueden representar y organizar de forma uniforme, listos para la combinación y exploración. **Los servicios de consulta de Experience** le permiten usar herramientas y marcos compatibles con SQL para hacer consultas y manipular todos los datos.

## Comparación de CJA con la versión tradicional de Adobe Analytics

Customer Journey Analytics amplía el ámbito de Analytics al ofrecer funciones fáciles de usar entre canales y al eliminar las limitaciones de versiones anteriores de Adobe Analytics. Algunas mejoras importantes:

* **Eventos y variables ilimitadas**: los conceptos de eVars, props y eventos ya no existen. Los datos se centran principalmente en dimensiones y métricas. Los conjuntos de datos pueden tener una cantidad ilimitada de dimensiones y métricas únicas.
* **Valores únicos ilimitados**: Adobe Experience Platform no se limita a ninguna limitación única, como los valores únicos de 500.000 en los grupos de informes tradicionales.
* **Modificar datos históricos**: con Adobe Experience Platform, los datos se pueden eliminar o corregir.
* **Datos de grupos de informes múltiples**: las implementaciones existentes de varios conjuntos de datos se pueden combinar en Platform.

La versión inicial de Customer Journey Analytics incluye muchas de las funciones incluidas en Analysis Workspace. Para obtener una lista completa, consulte [Compatibilidad con las funciones de Customer Journey Analytics](cja-aa.md).

## Comparación de CJA con análisis entre dispositivos

[El análisis](https://docs.adobe.com/content/help/es-ES/analytics/components/cda/cda-home.html) cruzado de dispositivos se integra con el servicio de identidad de Adobe Experience Platform, utilizando Co-op Graph o Private Graph, para identificar cómo los dispositivos digitales se asignan a las personas. Está disponible para los clientes de Adobe Analytics Ultimate.

CJA se integra con los conjuntos de datos de Adobe Experience Platform y permite el análisis entre canales en Analysis Workspace. Aunque CJA todavía no se integra con los gráficos de identidad Co-op o Privada, puede &quot;unir su propia ID&quot; para unir conjuntos de datos, y esos conjuntos de datos pueden ir más allá de los datos digitales para incluir puntos de contacto en línea y sin conexión. Los requisitos previos de CJA se tratan en más detalle a continuación.

## Casos de uso clave

Customer Journey Analytics le permite:

* **Ver al cliente en un contexto de recorrido**: puede obtener vistas y análisis de datos de forma secuencial abarcando varios canales. Los datos del centro de llamadas, los sistemas de POS y las propiedades en línea se pueden combinar en una única vista del sistema de informes.
* **Poner perspectivas a disposición de todos**: democratizar el acceso a los datos y permitir que más personas tomen decisiones comerciales con perspectivas derivadas de los datos. Cualquier miembro de la organización responsable de cualquier aspecto de la experiencia del cliente puede tomar decisiones reales con mayor rapidez según datos más completos.
* **Aproveche el poder de la ciencia de datos para sus analistas**: Customer Journey Analytics nos permite utilizar la ciencia de datos para obtener una perspectiva y un análisis profundos.
* **Visualice e interactúe con sus conjuntos de datos mediante sistemas de informes ad-hoc**: Workspace puede utilizar cualquier conjunto de datos de Adobe Experience Platform que se ajuste a algunas reglas básicas.
* **Vista de datos no web**: Workspace ya no se limita a una definición rígida de &#39;visita&#39; o &#39;evento&#39;. Los esquemas personalizados permiten un control completo de los datos y las definiciones.
* **Ejerza un buen control sobre la manipulación de datos**: cambie los datos que ha cargado, cree nuevos conjuntos de datos e impórtelos a Workspace. Adobe Experience Platform proporciona herramientas de consulta, extracción, transformación y carga a través del servicio de consulta de Experience Cloud.

## Requisitos previos

Para poder iniciar desde Customer Journey Analytics, se deben cumplir los siguientes requisitos previos:

* Su organización tiene un contrato activo con Adobe Analytics para Select, Prime o Ultimate con el complemento de Customer Journey Analytics. Si no está seguro de qué tipo de contrato tiene o no está seguro de si tiene el complemento de CJA, póngase en contacto con el Administrador de cuentas de su organización.
* Su organización se ha aprovisionado para Adobe Experience Platform.

## Permisos de acceso de usuario

Para crear conexiones, agregar conjuntos de datos, etc., necesita los siguientes permisos en la [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Para administrar conjuntos de datos en Experience Platform, debe formar parte de un perfil de productos de Platform que le conceda el permiso de &quot;Administrar conjuntos de datos&quot;. Para obtener más información, consulte [Control de acceso en Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Para crear una conexión para un conjunto de datos de Platform, debe formar parte de un perfil de productos de Platform que le proporcione los siguientes permisos:
   * Esquemas de vistas
   * Conjuntos de datos de vistas
   * Administrar áreas de nombres de identidad
   * Entornos aislados de vistas
* Para acceder a Customer Journey Analytics o establecer una conexión, también deberá agregarlo a un perfil de producto de Customer Journey Analytics en [Admin Console](https://adminconsole.adobe.com/enterprise/).

### Actualizaciones terminológicas

Se ha cambiado el nombre de varias funciones de CJA para que se ajusten a las normas del sector. Algunos nombres actualizados incluyen:

* Los segmentos ahora se conocen como &#39;Filtros&#39;.
* Los grupos de informes virtuales ahora se conocen como &#39;Vistas&#39;.
* Las clasificaciones ahora se conocen como &#39;Conjuntos de datos de búsqueda&#39;.
* Los atributos del cliente ahora se conocen como &#39;Conjuntos de datos de perfil&#39;.
* Los contenedores de visita individual ahora se conocen como contenedores de &#39;Evento&#39;.
* Los contenedores de visitas ahora se conocen como contenedores de &#39;Sesión&#39;.
* Los contenedores de Visitante ahora se conocen como contenedores de &#39;Persona&#39;.

## Otras funciones creadas en Adobe Experience Platform

Customer Journey Analytics es una de las funciones de muchos que dependen de Adobe Experience Platform. Muchas otras capacidades, también integradas en Platform, le permiten aprovechar al máximo sus datos.

Adobe Experience Platform le permite centralizar y estandarizar los datos y el contenido de los clientes de cualquier sistema y aplicar la ciencia de datos y el aprendizaje automático para mejorar el diseño y el envío de las experiencias personalizadas. Los datos del cliente en la plataforma se almacenan como conjuntos de datos que consisten en un esquema y lotes de datos. Para obtener más información sobre la plataforma, consulte la [Descripción general de arquitectura de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/experience-platform/landing/home.translate.html).

Desde la ingestión de datos hasta el acceso directo a SQL, varios componentes de Experience Platform son fundamentales para Customer Journey Analytics y actúan con él:

* [Servicio de consulta](https://docs.adobe.com/content/help/es-ES/experience-platform/query/home.translate.html): utilice SQL estándar para recuperar datos de Adobe Experience Platform, como datos de soluciones de Adobe, datos de origen de clientes o cualquier otro dato de Platform. Se trata de una herramienta sin servidor que le permite unirse a cualquier conjunto de datos y capturar los resultados de la consulta como un nuevo conjunto de datos para usar en el sistema de informes, en Data Science Workspace o para su inserción en el servicio de perfil. Puede utilizar el servicio de consulta para crear ecosistemas de análisis de datos creando una imagen de los consumidores en sus diversos canales de interacción. Estos canales pueden incluir sistemas de puntos de venta, web, móviles, CRM, etc.
* [Perfil del cliente en tiempo real](https://docs.adobe.com/content/help/es-ES/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Servicio de identidad](https://docs.adobe.com/content/help/es-ES/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://docs.adobe.com/content/help/es-ES/experience-platform/data-science-workspace/home.translate.html) la opción &quot;desarrollador&quot;: puede utilizar inteligencia artificial (IA) prediseñada y modelos de aprendizaje automático en Adobe Experience Platform para influir en varios puntos del recorrido del cliente. Al descubrir perspectivas ocultas, puede hacer mejores predicciones en todo el viaje del cliente, sugerir los mejores pasos siguientes recomendados o automatizar procesos engorrosos.
