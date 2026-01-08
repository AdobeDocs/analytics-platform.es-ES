---
title: Asignación de datos de Analytics de varias organizaciones de IMS
description: Descubra cómo puede solicitar asignar datos de grupos de informes de varias organizaciones de IMS de origen a una organización de IMS de destino.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Asignación de datos de Analytics de varias organizaciones de IMS

El conector de origen de Analytics solo puede introducir datos de grupos de informes de Adobe Analytics que pertenezcan a la misma organización para la que está autorizado a utilizar Customer Journey Analytics. La función para asignar datos de Analytics de varias organizaciones IMS proporciona una solución para esta limitación. El proceso para habilitar esta función se describe en este artículo.


## Escenario

Dispone de varias organizaciones IMS y tiene datos de Analytics en varios grupos de informes en estas organizaciones IMS. Esta configuración podría ser el resultado de lo siguiente:

* adquisiciones o fusiones
* requisitos de estructura organizativa
* restricciones de implementación regional

De forma predeterminada, no puede crear informes sobre la combinación de datos de varios grupos de informes en varias organizaciones de IMS en Customer Journey Analytics. El motivo de esta limitación es que la ingesta de datos de Adobe Analytics en Experience Platform a través del conector de origen de Analytics solo admite la ingesta de datos propiedad de una única organización IMS. La organización IMS para la que está aprovisionado y que utiliza para iniciar sesión en Adobe Analytics, Experience Platform y Customer Journey Analytics.

Con la función *asignar datos de Analytics de varias organizaciones de IMS*, puede solicitar a Adobe que asigne datos. La función usa el conector de origen de Analytics para asignar datos de grupos de informes que residen en varias organizaciones IMS de *origen* a conjuntos de datos que forman parte de una organización IMS de *destino*. Por ejemplo:

| Ilustración | Explicación |
|---|---|
| ![Asignar datos en varias organizaciones de IMS](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Esta asignación le permite informar sobre grupos de informes que existen en la organización IMS 1, la organización IMS 2 y la organización IMS 3 desde una conexión en Customer Journey Analytics aprovisionada dentro de la organización IMS 3. |

{style="table-layout:fixed"}

## Cómo usar

Para configurar y habilitar la característica *asignar datos de Analytics de varias organizaciones de IMS*, debe solicitar la asignación a través del administrador de cuentas de Adobe. Para ello, haga lo siguiente:

1. Como administrador de la organización IMS de destino, solicite correos electrónicos de aprobación a todos los administradores de la organización IMS de origen para los que desee asignar grupos de informes. Puede utilizar el siguiente texto como plantilla para que el correo electrónico solicite la aprobación a los administradores de la organización IMS de origen.

   | Plantilla de correo electrónico de muestra |
   | --- |
   | *Representante de nombres de compañías*, para otorgar a la organización de destino seleccionada acceso a las siguientes organizaciones de IMS (lista de organizaciones de IMS de origen), necesitamos asegurarnos de que un administrador para cada organización de IMS envíe su aprobación para permitir acceso a sus datos. Esto ayuda a garantizar que se han respetado los permisos de acceso a datos de cualquier organización de IMS afectada. Para garantizar que contamos con la aprobación adecuada, pida a un administrador registrado de Adobe para cada organización de administración que responda a este correo electrónico con su nombre y la organización de IMS que representan y que diga &quot;Yo apruebo&quot; para indicar que aprueban que los datos de esta organización de IMS aparezcan en la organización de destino [enumerar la organización de IMS de destino]. Tenga en cuenta que este administrador debe ser un administrador registrado en el sistema de Adobe como administrador para esa organización de IMS. |

1. Envíe un correo electrónico como administrador de la organización IMS de destino al administrador de cuentas de Adobe que solicite la asignación de grupos de informes dentro de varias organizaciones IMS de origen a la organización IMS de destino. Adjunte los correos electrónicos de aprobación recibidos de los administradores de la organización IMS de origen.

Una vez que el administrador de cuentas recibe el correo electrónico con la solicitud para asignar datos de Analytics de varias organizaciones, la solicitud se revisa dentro de Adobe. El administrador de cuentas se pone en contacto con usted para cualquier pregunta adicional, formación opcional y otra información.

Una vez aprobada, se crea la asignación solicitada y se le notifica. El nombre de la organización de IMS de origen se anexa al nombre del grupo de informes en la [lista de grupos de informes de Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) en Experience Platform.

## Limitaciones y riesgos

Las siguientes limitaciones se aplican a los datos de *map Analytics de varias organizaciones de IMS*:

* Puede conectar un grupo de informes solo una vez entre organizaciones.
* Debe eliminar todas las conexiones para una organización de IMS definida como la organización de IMS de destino en una asignación antes de poder solicitar la eliminación de la asignación.
* Los ECID no son compatibles entre las organizaciones IMS de origen asignadas y no son compatibles con la organización IMS de destino.
* Un usuario con permisos suficientes para configurar el conector de origen de Analytics en la organización IMS de destino tiene la capacidad de introducir datos de Analytics de cualquier organización IMS de origen asignada. No se comprueba la existencia de permisos para ese usuario en ninguna de las organizaciones IMS de origen.
