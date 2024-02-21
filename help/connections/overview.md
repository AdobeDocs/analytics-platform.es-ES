---
title: Información general sobre las conexiones de Customer Journey Analytics
description: Obtenga información sobre las conexiones en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 14cdc7bd8817dbf1d7a9950fa6ff62aedff82640
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 39%

---

# Información general sobre conexiones

Las conexiones permiten a los administradores de productos de Customer Journey Analytics establecer conexiones con diferentes fuentes de datos de AEP, como conjuntos de datos de evento, búsqueda y perfil. Estas conexiones permiten la integración de datos de una Conexión a una Vista de datos derivada. Se recomienda restringir el acceso a la administración de Conexiones a un grupo de administración principal. Las configuraciones a nivel de conexión tienen implicaciones contractuales con respecto a las asignaciones de volumen para los datos introducidos en Customer Journey Analytics.
Las conexiones son la base de CJA y se crean a partir de conjuntos de datos de origen de AEP. El acceso a Conexiones también permite ver el administrador de Conexiones, que le permite ver los conjuntos de datos subyacentes que componen la conexión, así como realizar selecciones críticas de edición y configuración.

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
