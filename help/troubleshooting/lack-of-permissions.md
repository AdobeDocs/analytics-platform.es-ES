---
title: Falta de permisos
description: Obtenga información sobre cómo solucionar problemas derivados de la falta de permisos
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 84a1cd485110be23b1977d916fc39e058b370066
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# Falta de permisos

El Customer Journey Analytics no funciona correctamente cuando no se han implementado ciertos permisos de Adobe Experience Platform.

Por ejemplo, después de crear un [Conexión](../connections/overview.md) y [Vista de datos](../data-views/data-views.md), es posible que aparezca el siguiente mensaje de error en la [Componentes](/help/data-views/create-dataview.md#components) sección:


>[!BEGINSHADEBOX]

*[!UICONTROL Se ha producido un error y no se han podido cargar los campos de esquema. Inténtelo de nuevo.]*

>[!ENDSHADEBOX]


Para corregir este error, debe tener privilegios de administrador de sistemas o productos para una organización que tenga un producto de Experience Platform. Consulte [Información general de control de acceso](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) para obtener más información.

1. Vaya a la IU de Adobe Experience Platform.

1. Seleccionar **[!UICONTROL Permisos]** desde el carril izquierdo.

1. Seleccionar **[!UICONTROL Funciones]**.

1. Desplácese hasta la función correspondiente.

1. Seleccionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para editar la función.

1. Asegurar **[!UICONTROL Administrar políticas de uso de datos]** y **[!UICONTROL Ver directivas de uso de datos]** se añaden a **[!UICONTROL Gobernanza de datos]** contenedor.

1. Seleccionar **[!UICONTROL Guardar]** para guardar los cambios.


