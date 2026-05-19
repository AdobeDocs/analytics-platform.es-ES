---
title: Falta de permisos
description: Obtenga información sobre cómo solucionar problemas derivados de la falta de permisos
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 94%

---

# Falta de permisos

Customer Journey Analytics no funciona correctamente si no se han implementado determinados permisos de Adobe Experience Platform.

Por ejemplo, después de crear una [Conexión](../connections/overview.md) y [Vista de datos](../data-views/data-views.md), es posible que aparezca el siguiente mensaje de error en la sección [Componentes](/help/data-views/create-dataview.md#components):


>[!BEGINSHADEBOX]

*[!UICONTROL Se produjo un error al recuperar las directivas DULE. Compruebe los permisos, directivas o etiquetas de la cuenta. Mensaje: Prohibido.]*

>[!ENDSHADEBOX]


1. Asegúrese de que tiene el control de acceso correcto:

   * Debe tener privilegios de administrador de sistemas o productos para una organización que tenga un producto de Experience Platform. Consulte [Información general sobre el control de acceso](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es#platform-permissions) para obtener más información.

   * Debe ser un usuario en el perfil de producto AEP-Default-All-Users. Hable con el administrador si no tiene los permisos para añadirse usted mismo a este perfil. Consulte [Jerarquía y flujo de trabajo de control de acceso](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es#access-control-hierarchy-and-workflow) para obtener más información.


1. Vaya a la IU de Adobe Experience Platform.

1. Seleccione **[!UICONTROL Permisos]** en el carril izquierdo.

1. Seleccione **[!UICONTROL Funciones]**.

1. Desplácese hasta la función correspondiente.

1. Seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para editar la función.

1. Asegúrese de que **[!UICONTROL Administrar políticas de uso de datos]** y **[!UICONTROL Ver directivas de uso de datos]** se han añadido al contenedor **[!UICONTROL Gobernanza de datos]**.

1. Seleccione **[!UICONTROL Guardar]** para guardar los cambios.
