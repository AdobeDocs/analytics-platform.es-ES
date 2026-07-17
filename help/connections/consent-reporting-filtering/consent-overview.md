---
title: Información general sobre filtrado e informes de consentimiento
description: Obtenga información sobre cómo informar sobre la pertenencia a la política de consentimiento de visitantes y filtrar los visitantes sin consentimiento en el momento de la ingesta en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 1058
ht-degree: 2%

---

# Resumen de filtrado e informes de consentimiento

La creación de informes y el filtrado de consentimiento utilizan los datos de pertenencia a directivas de consentimiento almacenados en los conjuntos de datos de Perfil de Adobe Experience Platform para ayudarle a crear informes sobre el consentimiento del visitante y, opcionalmente, excluir a los visitantes que no dan su consentimiento antes de que sus datos se introduzcan en Customer Journey Analytics.

## Requisitos previos

Antes de configurar la creación de informes y el filtrado de consentimiento, asegúrese de lo siguiente:

* Su organización dispone de una licencia para Adobe Healthcare Shield o Privacy &amp; Security Shield.
* Tiene permisos de administrador del sistema en Customer Journey Analytics.
* La zona protegida que desea utilizar contiene un conjunto de datos de perfil con datos de pertenencia a directivas de consentimiento en el campo `consentPoliciesIDMap`.
* La conexión que desea configurar ya existe. Para obtener más información, consulte [Crear o editar una conexión](/help/connections/create-connection.md).

El diagrama siguiente y la tabla asociada muestran una representación de alto nivel de cómo el sistema de informes y el filtrado de consentimiento hace que los datos de directivas de consentimiento estén disponibles en Analysis Workspace y filtra los datos de visitantes en el momento de la ingesta:

![Información general sobre filtrado e informes de consentimiento](assets/consent-overview.png)

| Número | Función | Función |
|---------|----------|---------|
| 1 | Configuración de filtrado e informes de consentimiento | Interfaz de configuración en Customer Journey Analytics que se utiliza para habilitar los informes de consentimiento y, opcionalmente, el filtrado de consentimiento. |
| 2 | Zona protegida | Debe contener el conjunto de datos de perfil que incluye los datos de pertenencia a directivas de consentimiento sobre los que desea informar. |
| 3 | Conjunto de datos del perfil | Incluye los datos de pertenencia a la política de consentimiento de cada visitante. La pertenencia a la directiva de consentimiento se almacena en el campo `consentPoliciesIDMap` de un conjunto de datos de perfil. Este conjunto de datos de perfil se agrega a la conexión que seleccione. <p>El perfil de cada visitante enumera las directivas de consentimiento con las que coincide. Customer Journey Analytics lee este campo para poner a disposición de los informes las políticas de consentimiento y para evaluar qué visitantes incluir durante la ingesta.</p> |
| 4 | Conjunto de datos de búsqueda de política de consentimiento | Proporciona nombres descriptivos de directivas y descripciones para los informes. El conjunto de datos de búsqueda se crea automáticamente y se mantiene sincronizado con Experience Platform. Existe un máximo de un conjunto de datos de búsqueda de directivas de consentimiento por zona protegida. |
| 5 | Conexión | La conexión en la que se aplican los informes y el filtrado de consentimiento. Todas las vistas de datos de la conexión heredan la configuración. |
| 6 | Componentes de política de consentimiento | Nuevas dimensiones, métricas y un campo derivado que representan la pertenencia a la directiva de consentimiento. Estos componentes se crean automáticamente y están disponibles para la creación de informes en Analysis Workspace. |
| 7 | Filtrado del tiempo de ingesta | Cuando el filtrado está habilitado, los visitantes que no dan su consentimiento se excluyen durante la ingesta, según las acciones de marketing que configure. |

## Informes de consentimiento frente a filtrado

La creación de informes y el filtrado de consentimiento son dos funcionalidades independientes. Puede habilitar los informes de consentimiento por su cuenta o habilitar tanto los informes como el filtrado a la vez.

### Informes de consentimiento

Al habilitar los informes de consentimiento, Customer Journey Analytics agrega un conjunto de componentes de directiva de consentimiento a las vistas de datos de la conexión configurada. Estos componentes le permiten utilizar Analysis Workspace para informar sobre qué visitantes coinciden con las distintas directivas de consentimiento mediante los datos de pertenencia a directivas de consentimiento en los conjuntos de datos de perfil de Experience Platform.

Para que la creación de informes sea legible, Customer Journey Analytics sincroniza los nombres y las descripciones de las directivas de Experience Platform en un conjunto de datos de búsqueda de directivas de consentimiento. Cuando se crea, actualiza, cambia el nombre o elimina una directiva en Experience Platform, el conjunto de datos de búsqueda se actualiza automáticamente.

Para obtener información sobre los componentes que crea la creación de informes de consentimiento, consulte [Analizar datos de directivas de consentimiento](/help/connections/consent-reporting-filtering/consent-analyze.md).

### Filtrado de consentimiento

>[!IMPORTANT]
>
>Los datos de consentimiento que se filtran (excluyen) no se almacenan en Customer Journey Analytics y no se pueden recuperar para fechas pasadas al actualizar la configuración.

Al habilitar el filtrado de consentimiento, Customer Journey Analytics excluye a los visitantes que no dan su consentimiento en el momento de la ingesta. Como el filtrado se produce en el momento de la ingesta, los datos de los visitantes excluidos nunca entran en Customer Journey Analytics y no están disponibles para la creación de informes.

Tenga en cuenta lo siguiente al utilizar el filtrado de consentimiento:

* Customer Journey Analytics determina las directivas de consentimiento que se aplican a las acciones de marketing que ha configurado.

  Una acción de marketing representa una categoría de uso de datos. Customer Journey Analytics determina qué políticas de consentimiento se aplican a cada acción de marketing y usted habilita el filtrado para cada acción de marketing de forma independiente al [crear su configuración](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration).

  | Acción de marketing | Descripción |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Informes estándar de Customer Journey Analytics en Analysis Workspace. |
  | **[!UICONTROL Ciencia de datos]** | Casos de uso de análisis avanzados, aprendizaje automático y ciencia de datos. |

* Los datos de un visitante se incorporan solamente si el visitante coincide con **todas** las directivas de consentimiento aplicables. Si a un visitante le falta alguna política aplicable, se excluyen los datos de ese visitante.

## Configuración de informes y filtros de consentimiento

Al configurar los informes y el filtrado de consentimiento, se selecciona la zona protegida y el conjunto de datos de perfil que contienen los datos de pertenencia a la directiva de consentimiento, se elige la conexión o las conexiones que se van a configurar y se elige si se filtran los datos de cada acción de marketing. A continuación, Customer Journey Analytics crea automáticamente el conjunto de datos de búsqueda de la política de consentimiento y los componentes de la política de consentimiento.

Para obtener más información, consulte [Configurar la creación de informes y el filtrado de consentimiento](/help/connections/consent-reporting-filtering/consent-configure.md).

## Administrar las configuraciones de filtrado y creación de informes de consentimiento

Puede administrar las configuraciones de filtrado y creación de informes de consentimiento una vez creadas. Puede ver, editar y eliminar configuraciones.

Para obtener información sobre cómo administrar las configuraciones existentes, consulte [Administrar configuraciones de filtrado y generación de informes de consentimiento](/help/connections/consent-reporting-filtering/consent-manage.md).

## Analizar datos de directivas de consentimiento

Con los datos de directivas de consentimiento disponibles en Customer Journey Analytics, puede crear informes sobre los visitantes que coinciden con las directivas de consentimiento y utilizar insight para comprender las audiencias de consentimiento en los informes.

Para obtener más información, consulte [Analizar datos de directivas de consentimiento](/help/connections/consent-reporting-filtering/consent-analyze.md).

## Requisitos de permisos y función de filtrado y creación de informes de consentimiento

Se requieren las siguientes funciones de Customer Journey Analytics y permisos de Experience Platform para la creación de informes y el filtrado de consentimiento:

| Compatibilidad | Requisitos de rol o permiso de Customer Journey Analytics | Requisitos de permiso de Experience Platform |
|---------|----------|----------|
| [Crear configuraciones de filtrado e informes de consentimiento](/help/connections/consent-reporting-filtering/consent-configure.md) | Administrador del sistema | <ul><li>Conjuntos de datos: leer, escribir</li><li>Esquemas: leer, escribir</li></ul> <p>Se requiere acceso de lectura para el conjunto de datos de perfil que contiene los datos de pertenencia a directivas de consentimiento. Se requiere acceso de escritura porque se crea un conjunto de datos de búsqueda de directivas de consentimiento y se mantiene sincronizado.</p> |
| Ver componentes de política de consentimiento en la vista de datos | Administrador de perfil de producto para el perfil de producto al que está asignada la vista de datos <p>Para obtener más información, consulte [Control de acceso](/help/technotes/access-control.md).</p> | N/A |
| Uso de componentes de política de consentimiento en Analysis Workspace | Acceso a una vista de datos donde se agregaron los componentes de la directiva de consentimiento | n/a |

## Casos de uso de filtrado y creación de informes de consentimiento

Por ejemplo, en los casos de uso que resaltan el valor que proporcionan los informes y el filtrado de consentimiento, consulte [Casos de uso de filtrado y creación de informes de consentimiento](/help/connections/consent-reporting-filtering/consent-use-cases.md).

## Límites de filtrado e informes de consentimiento

Tenga en cuenta los límites siguientes al [configurar la creación de informes y el filtrado de consentimiento](/help/connections/consent-reporting-filtering/consent-configure.md):

* Una sola zona protegida solo puede tener un conjunto de datos de búsqueda de directivas de consentimiento. Varias configuraciones en la misma zona protegida comparten ese conjunto de datos de búsqueda.

* Una conexión solo se puede asociar con una configuración de filtrado y creación de informes de consentimiento.
