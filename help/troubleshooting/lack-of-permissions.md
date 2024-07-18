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
ht-degree: 100%

---

# Falta de permisos

Customer Journey Analytics no funciona correctamente si no se han implementado determinados permisos de Adobe Experience Platform.

Por ejemplo, después de crear una [Conexión](../connections/overview.md) y [Vista de datos](../data-views/data-views.md), es posible que aparezca el siguiente mensaje de error en la sección [Componentes](/help/data-views/create-dataview.md#components):


>[!BEGINSHADEBOX]

*[!UICONTROL Algo ha ido mal al recuperar las políticas de DULE. Verifique los permisos de la cuenta, las políticas o las etiquetas. Mensaje: Prohibido.]*

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
