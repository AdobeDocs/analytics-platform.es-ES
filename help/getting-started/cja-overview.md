---
title: Información general sobre Customer Journey Analytics
description: Introducción a Análisis de Viaje del Cliente
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Información general sobre Customer Journey Analytics

El análisis de viaje del cliente es una función de Analytics que le permite utilizar la potencia del espacio de trabajo de Análisis con datos de la plataforma de Adobe Experience. Puede desglosar, filtrar, consulta y visualizar datos de años, y se combina con la capacidad de Platform de albergar todo tipo de esquemas y tipos de datos. Con el Modelo de datos de **experiencia (XDM)**, los datos se pueden representar y organizar de forma uniforme, listos para la combinación y exploración. **Los servicios** de Consulta de experiencias le permiten utilizar herramientas y marcos compatibles con SQL para realizar consultas y manipular todos los datos.

## Comparación de CJA con Adobe Analytics tradicional

El análisis de viajes del cliente amplía el ámbito de Analytics al ofrecer funciones fáciles de usar entre canales y eliminar las limitaciones de versiones anteriores de Adobe Analytics. Algunas mejoras notables son:

* **eventos** y variables ilimitadas: Los conceptos de eVars, props y eventos ya no existen. Los datos se centran principalmente en dimensiones y métricas. Los conjuntos de datos pueden tener una cantidad ilimitada de dimensiones y métricas únicas.
* **Valores**&#x200B;únicos ilimitados: Adobe Experience Platform no se limita a ninguna limitación única, como los valores únicos de 500.000 en los grupos de informes tradicionales.
* **Modificar datos** históricos: Con Adobe Experience Platform, los datos se pueden eliminar o corregir.
* **Datos** de grupos de informes múltiples: Las implementaciones existentes de varios conjuntos de datos se pueden combinar en la plataforma.

La versión inicial de Análisis del viaje del cliente incluye muchas de las funciones incluidas en Espacio de trabajo de Análisis. Para obtener una lista completa, consulte Compatibilidad con [las funciones de Análisis del viaje del](cja-aa.md)cliente.

## Comparación de CJA con análisis entre dispositivos

[Análisis](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) cruzado de dispositivos se integra con el servicio de identidad de la plataforma de experiencia de Adobe, utilizando Co-op Graph o Private Graph, para identificar cómo los dispositivos digitales se asignan a las personas. Está disponible para los clientes de Adobe Analytics Ultimate.

CJA se integra con los conjuntos de datos de la plataforma Adobe Experience y permite la análisis entre canales en el espacio de trabajo de Análisis. Aunque CJA todavía no se integra con los gráficos de identidad Co-op o Privada, puede &quot;unir su propia ID&quot; para unir conjuntos de datos, y esos conjuntos de datos pueden ir más allá de los datos digitales para incluir puntos de contacto en línea y sin conexión. Los requisitos previos de CJA se tratan más detalladamente a continuación.

## Casos de uso clave

El análisis de viajes del cliente le permite:

* **Ver al cliente en un contexto** de viaje: Puede realizar vistas y análisis de datos de forma secuencial, abarcando varios canales. Los datos del centro de llamadas, los sistemas POS y las propiedades en línea se pueden combinar en una única vista de sistema de informes.
* **Poner a disposición de todos** los usuarios perspectivas: Democratizar el acceso a los datos y permitir que más personas tomen decisiones comerciales con perspectivas derivadas de los datos. Cualquier miembro de la organización responsable de cualquier aspecto de la experiencia del cliente puede tomar decisiones reales con mayor rapidez, basándose en datos más completos.
* **Aproveche el poder de la ciencia de datos para sus analistas**: El análisis de viaje del cliente permite a los seres humanos utilizar la ciencia de datos para obtener una perspectiva y una análisis profundas.
* **Visualice e interactúe con sus conjuntos de datos mediante sistemas de informes** ad-hoc: Workspace puede utilizar cualquier conjunto de datos de la plataforma de Adobe Experience que se ajuste a algunas reglas básicas.
* **Vista de datos** no web: Workspace ya no se limita a una definición rígida de &quot;visita individual&quot; o &quot;evento&quot;. Los esquemas personalizados permiten un control completo de los datos y las definiciones.
* **Ejerza un bueno control sobre la manipulación** de datos: Cambie los datos que ha cargado, cree nuevos conjuntos de datos e impórtelos en Workspace. Adobe Experience Platform proporciona herramientas de consulta, extracción, transformación y carga a través del servicio de Consulta de Experience Cloud.

## Requisitos previos

Para poder realizar inicios mediante el análisis de viajes del cliente, se deben cumplir los siguientes requisitos previos:

* Su organización tiene un contrato activo con Adobe Analytics para Select, Prime o Ultimate con el complemento Customer Journey Analytics. Si no está seguro de qué tipo de contrato tiene o no está seguro de si tiene el complemento CJA, póngase en contacto con el administrador de cuentas de su organización.
* Su organización se ha aprovisionado para Adobe Experience Platform.

## Permisos de acceso de usuario

Para crear conexiones, agregar conjuntos de datos, etc., necesita los siguientes permisos en la Consola [de administración](https://adminconsole.adobe.com/enterprise/):

* Para administrar conjuntos de datos en la plataforma de experiencias, debe formar parte de un Perfil de productos de la plataforma que le conceda el permiso &quot;Administrar conjuntos de datos&quot;. Para obtener más información, consulte [Control de acceso en Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Para crear una conexión a un conjunto de datos de plataforma, debe formar parte de un Perfil de productos de plataforma que le proporcione los siguientes permisos:
   * Esquemas de Vista
   * Conjuntos de datos de Vista
   * Administrar Áreas de nombres de identidad
   * Entornos aislados de Vista
* Para acceder a Análisis de viajes del cliente o establecer una conexión, también deberá agregarlo a un Perfil de producto de Análisis de viajes del cliente en la Consola de [administración](https://adminconsole.adobe.com/enterprise/).

### Actualizaciones terminológicas

Se ha cambiado el nombre de varias funciones de CJA para que se ajusten a las normas del sector. Algunos nombres actualizados incluyen:

* Los segmentos ahora se conocen como &#39;Filtros&#39;.
* Los grupos de informes virtuales ahora se conocen como &quot;Vistas&quot;.
* Las clasificaciones ahora se conocen como &quot;conjuntos de datos de búsqueda&quot;.
* Los atributos del cliente ahora se conocen como &quot;conjuntos de datos de Perfil&quot;.
* Los contenedores de visita individual ahora se conocen como contenedores de &quot;Evento&quot;.
* Los contenedores de visitas ahora se conocen como contenedores de &#39;sesión&#39;.
* Los contenedores de Visitante ahora se conocen como contenedores &#39;personales&#39;.

## Otras funciones creadas en la plataforma Adobe Experience

Customer Journey Analytics es una de las funciones de muchos que dependen de Adobe Experience Platform. Varias otras capacidades, también integradas en Platform, le permiten aprovechar al máximo sus datos.

Adobe Experience Platform le permite centralizar y estandarizar los datos y el contenido de los clientes de cualquier sistema y aplicar la ciencia de datos y el aprendizaje automático para mejorar el diseño y el envío de las experiencias personalizadas. Los datos del cliente en la plataforma se almacenan como conjuntos de datos, que consisten en un esquema y lotes de datos. Para obtener más información sobre la plataforma, consulte [Adobe Experience Platform Architecture Overview](https://www.adobe.io/apis/experienceplatform/home/overview.html).

Desde la ingestión de datos hasta el acceso directo a SQL, varios componentes de la plataforma de experiencias son fundamentales para el análisis del viaje del cliente y actúan junto con él:

* [Servicio](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html)de Consulta: Utilice SQL estándar para recuperar datos de Adobe Experience Platform, como datos de soluciones de Adobe, datos de origen de clientes o cualquier otro dato de plataforma. Se trata de una herramienta sin servidor que le permite unirse a cualquier conjunto de datos y capturar los resultados de la consulta como un nuevo conjunto de datos para su uso en sistema de informes, Área de trabajo de ciencia de datos o para su inserción en el servicio de Perfil. Puede utilizar el servicio de Consulta para crear ecosistemas de análisis de datos, creando una imagen de los consumidores en sus diversos canales de interacción. Estos canales pueden incluir sistemas de puntos de venta, web, móviles, CRM, etc.
* [Perfil](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)del cliente en tiempo real:
* [Servicio de identidad](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Área de trabajo](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) de ciencias de datos en la opción &quot;desarrollador&quot;: puede utilizar inteligencia artificial (AI) prediseñada y modelos de aprendizaje automático en Adobe Experience Platform para influir en varios puntos del viaje del cliente. Al descubrir perspectivas ocultas, puede hacer mejores predicciones en todo el viaje del cliente, sugerir los mejores pasos siguientes recomendados o automatizar procesos engorrosos.
