---
title: Información general sobre las conexiones de Customer Journey Analytics
description: Obtenga información sobre las conexiones en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 55%

---

# Información general sobre conexiones

Las conexiones permiten a los administradores de productos de Customer Journey Analytics establecer conexiones con diferentes [!DNL Adobe Experience Platform] fuentes de datos, como eventos, búsquedas y conjuntos de datos de perfil. Estas conexiones permiten la integración de datos de una Conexión a una Vista de datos derivada. Las conexiones son la base de CJA y se crean desde [!DNL Experience Platform] conjuntos de datos de origen. El acceso a Conexiones también le permite ver el administrador de Conexiones, donde puede ver los conjuntos de datos subyacentes que componen la conexión, así como realizar selecciones críticas de edición y configuración.

Se recomienda restringir el acceso a la administración de Conexiones a un grupo de administración principal. Las configuraciones a nivel de conexión tienen implicaciones contractuales con respecto a las asignaciones de volumen para los datos introducidos en Customer Journey Analytics.

A continuación, se muestra un vídeo introductorio:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Permisos necesarios

Para crear una conexión de Customer Journey Analytics, necesita los siguientes permisos en [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Modelado de datos: Esquemas de vista, Administrar esquemas
* Administración de datos: Ver conjuntos de datos, Administrar conjuntos de datos
* Ingesta de datos: Administrar fuentes
* Ver espacios de nombres de identidad

Customer Journey Analytics
* Acceso de administrador de productos

>[!IMPORTANT]
>
>Puede combinar varios conjuntos de datos de [!DNL Experience Platform] en una sola conexión.
