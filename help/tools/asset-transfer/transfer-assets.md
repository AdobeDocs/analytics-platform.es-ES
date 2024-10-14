---
title: Transferir recursos
description: Obtenga información sobre cómo transferir componentes de un usuario a otro
role: Admin
solution: Customer Journey Analytics
source-git-commit: faa9545fa3928a19aeaaf7285a9643e7dc253cea
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---


# Transferir recursos

La herramienta de transferencia de recursos permite transferir la propiedad de los recursos a otros usuarios. Assets puede incluir componentes como proyectos, filtros, intervalos de fechas, métricas calculadas, anotaciones, alertas y proyectos programados.

Los Assets suelen estar vinculados a un propietario individual y, en algunos casos, como los filtros y las métricas calculadas, los administradores no pueden editarlos ni compartirlos. Cuando los usuarios abandonan la organización o se modifica su función, puede ser necesario transferir la propiedad de estos activos a otros usuarios para garantizar la continuidad y el acceso adecuado.

## Permisos

La transferencia de recursos requiere permisos de administrador de productos para Customer Journey Analytics.

## Transferir recursos

1. En CJA, vaya a **[!UICONTROL Herramientas]** > **[!UICONTROL Transferencia de recursos]**.

   ![Elemento de menú de transferencia de recursos](/help/tools/asset-transfer/assets/asset-transfer.png)

1. En el cuadro de diálogo **[!UICONTROL Usuarios]**, busque y seleccione el usuario desde el que desea transferir recursos.

   >[!IMPORTANT]
   >
   >Solo puede realizar una transferencia individual, de un usuario a otro. No se admiten transferencias &quot;uno a varios&quot; o &quot;varios a uno&quot;.


1. Después de seleccionar un usuario, la opción Transferir recursos aparece en la parte inferior de la pantalla.

   ![opción de menú](/help/tools/asset-transfer/assets/after-selection.png)

1. Haga clic en **[!UICONTROL Transferir recursos]**.

1. En la pantalla **[!UICONTROL Transferir recursos]**, seleccione primero el destinatario al que desea transferir los recursos.

1. Ahora, revise las carpetas de cada componente en la navegación izquierda para seleccionar componentes individuales o todos los recursos de una carpeta que desea transferir.

   Tenga en cuenta que la transferencia de recursos de un administrador a un no administrador no actualiza el destinatario a un administrador.

1. Para seleccionar _todos_ los recursos de una carpeta, marque la casilla junto a **[!UICONTROL Nombre]** en la parte superior de la tabla.

   ![seleccionar recursos para transferir](/help/tools/asset-transfer/assets/select-assets.png)

1. Haga clic en **[!UICONTROL Transferir]** en la parte superior derecha después de haber realizado todas las selecciones.

1. Haga clic en **[!UICONTROL Confirmar]** cuando aparezca el mensaje de confirmación.

   >[!IMPORTANT]
   >
   >No cierre la pantalla durante la transferencia para evitar el aborto del proceso. Esto garantiza una experiencia de transferencia sin problemas.

## Transferencia de recursos durante la actualización de Adobe Analytics a Customer Journey Analytics

Uno de los principales casos de uso de la transferencia de recursos es durante la actualización de Adobe Analytics a Customer Journey Analytics.

La característica [Migración de componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) de Adobe Analytics le permite migrar proyectos de propiedad del administrador a otros administradores. Todos los componentes que componen estos proyectos se vuelven a crear en Customer Journey Analytics y el administrador de destinatarios es propietario de todos esos componentes, independientemente de quién los haya creado.

Posteriormente, esta herramienta de transferencia de recursos permite a los administradores reasignar componentes a sus legítimos propietarios.

## Exportar a CSV

Puede exportar una lista de recursos transferidos de un usuario a otro a un archivo .csv.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->