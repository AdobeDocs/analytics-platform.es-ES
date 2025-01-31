---
title: Información general sobre las conexiones de Customer Journey Analytics
description: Obtenga información sobre las conexiones en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# Información general sobre conexiones

Las conexiones permiten a los administradores de productos de Customer Journey Analytics establecer conexiones con diferentes fuentes de datos de [!DNL Adobe Experience Platform], como conjuntos de datos de evento, búsqueda y perfil. Estas conexiones permiten la integración de datos de una Conexión a una Vista de datos derivada. Las conexiones son la base de CJA y se crean a partir de conjuntos de datos de origen de [!DNL Experience Platform]. El acceso a Conexiones también permite ver el administrador de Conexiones, que le permite ver los conjuntos de datos subyacentes que componen la conexión, así como realizar selecciones críticas de edición y configuración.

Se recomienda restringir el acceso a la administración de Conexiones a un grupo de administración principal. Las configuraciones a nivel de Conexión tienen implicaciones contractuales con respecto a las asignaciones de volumen para los datos introducidos en Customer Journey Analytics.

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

## Permisos necesarios

Para crear una conexión de Customer Journey Analytics, necesita los siguientes permisos: Para obtener más información sobre los permisos, consulte la documentación de [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) y los [permisos de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/access-control/home).

### En Adobe Admin Console:

* Customer Journey Analytics: Administrador de productos
* Adobe Experience Platform: se ha añadido al perfil de producto denominado *AEP-Default-All-Users*

### En los permisos de Adobe Experience Platform:

* Modelado de datos: Esquemas de vista, Administrar esquemas
* Administración de datos: Ver conjuntos de datos, Administrar conjuntos de datos
* Ingesta de datos: Administrar fuentes
* Identity Management: ver áreas de nombres de identidad
* Zonas protegidas: zonas protegidas utilizadas en conexiones de Customer Journey Analytics relacionadas

>[!IMPORTANT]
>
>Puede combinar varios conjuntos de datos de [!DNL Experience Platform] en una sola conexión.
