---
title: Falta de permisos
description: Obtenga información sobre cómo solucionar problemas derivados de la falta de permisos
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Falta de permisos

El Customer Journey Analytics no funciona correctamente cuando no se han implementado ciertos permisos de Adobe Experience Platform.

Por ejemplo, después de crear un [Conexión](../connections/overview.md) y [Vista de datos](../data-views/data-views.md), es posible que aparezca el siguiente mensaje de error en la [Componentes](/help/data-views/create-dataview.md#components) sección:


>[!BEGINSHADEBOX]

*[!UICONTROL Error al recuperar las directivas DULE. Compruebe los permisos, directivas o etiquetas de la cuenta. Mensaje: Prohibido.]*

>[!ENDSHADEBOX]


1. Asegúrese de que tiene el control de acceso correcto:

   * Debe tener privilegios de administrador de sistemas o productos para una organización que tenga un producto de Experience Platform. Consulte [Información general de control de acceso](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) para obtener más información.

   * Debe ser un usuario en el perfil de producto AEP-Default-All-Users. Pregunte al administrador si no tiene los permisos para agregarse a este perfil. Consulte [Flujo de trabajo y jerarquía de control de acceso](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) para obtener más información.


1. Vaya a la interfaz de usuario de Adobe Experience Platform.

1. Seleccionar **[!UICONTROL Permisos]** desde el carril izquierdo.

1. Seleccionar **[!UICONTROL Funciones]**.

1. Desplácese hasta la función correspondiente.

1. Seleccionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para editar la función.

1. Asegurar **[!UICONTROL Administrar políticas de uso de datos]** y **[!UICONTROL Ver directivas de uso de datos]** se añaden a **[!UICONTROL Gobernanza de datos]** contenedor.

1. Seleccionar **[!UICONTROL Guardar]** para guardar los cambios.
