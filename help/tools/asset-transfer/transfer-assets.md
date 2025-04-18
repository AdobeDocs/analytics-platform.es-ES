---
title: Transferir recursos
description: Obtenga información sobre cómo transferir componentes de un usuario a otro
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Transferir recursos

La herramienta de transferencia de recursos permite transferir la propiedad de los recursos a otros usuarios. Assets puede incluir componentes como proyectos, segmentos, intervalos de fechas, métricas calculadas, anotaciones, alertas y proyectos programados.

Assets suelen estar vinculados a un propietario individual y, en algunos casos, como los segmentos y las métricas calculadas, los administradores no pueden editarlos ni compartirlos. Cuando los usuarios abandonan la organización o se modifica su función, puede ser necesario transferir la propiedad de estos activos a otros usuarios para garantizar la continuidad y el acceso adecuado.

## Permisos

La transferencia de recursos requiere el permiso de administrador de productos para Customer Journey Analytics.

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

   >[!NOTE]
   >
   >La transferencia de recursos de un administrador a un no administrador no actualiza el destinatario a un administrador.


   >[!NOTE]
   >
   >    Al transferir recursos que hacen referencia a otros componentes (por ejemplo, proyectos que hacen referencia a otros segmentos y métricas calculadas), los componentes que no sean propiedad del propietario actual del proyecto solo se compartirán con el destinatario. La propiedad de todos los demás componentes se transferirá al destinatario.

1. Para seleccionar _todos_ los recursos de una carpeta, marque la casilla junto a **[!UICONTROL Nombre]** en la parte superior de la tabla.

   ![seleccionar recursos para transferir](/help/tools/asset-transfer/assets/select-assets.png)

1. Haga clic en **[!UICONTROL Transferir]** en la parte superior derecha después de haber realizado todas las selecciones.

1. Haga clic en **[!UICONTROL Confirmar]** cuando aparezca el mensaje de confirmación.

   >[!IMPORTANT]
   >
   >No cierre la pantalla durante la transferencia para evitar el aborto del proceso. Esto garantiza una experiencia de transferencia sin problemas.

## Transferir resultados

Hay tres posibles resultados para una transferencia:

- **Éxito de transferencia**: &quot;Assets se transfirió correctamente&quot;.

- **Éxito parcial**: &quot;Algunos recursos se transfirieron correctamente&quot;.

- **Error de transferencia**: &quot;No se pudieron transferir los recursos. Inténtelo de nuevo&quot;.

## Transferencia de recursos durante la actualización de Adobe Analytics a Customer Journey Analytics

Uno de los principales casos de uso de la transferencia de recursos es durante la actualización de Adobe Analytics a Customer Journey Analytics.

La característica [Migración de componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) de Adobe Analytics le permite migrar proyectos de propiedad del administrador a otros administradores. Todos los componentes que componen estos proyectos se vuelven a crear en Customer Journey Analytics y el administrador de destinatarios es propietario de todos esos componentes, independientemente de quién los haya creado.

Posteriormente, esta herramienta de transferencia de recursos permite a los administradores reasignar componentes a sus propietarios legítimos, tanto si son administradores como si no.

>[!IMPORTANT]
>
>Aunque puede transferir componentes con esta herramienta, usted como administrador debe asegurarse de que el destinatario tenga acceso a las vistas de datos necesarias para ver o utilizar estos componentes. Puede ver y asignar permisos en [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html).

## Exportar a CSV

La opción **[!UICONTROL Exportar a CSV]** solo permite a los administradores descargar una lista de usuarios mostrados en un archivo .csv. No les permite exportar una lista de recursos transferidos a un archivo .csv.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->
