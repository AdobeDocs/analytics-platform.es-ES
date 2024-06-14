---
title: Información general sobre las conexiones de Customer Journey Analytics
description: Obtenga información sobre las conexiones en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 7a5fa07e3bafa3da5b044ce37299196a006f1d64
workflow-type: ht
source-wordcount: '184'
ht-degree: 100%

---

# Información general sobre conexiones

Las conexiones permiten a los administradores de productos de Customer Journey Analytics establecer conexiones con diferentes fuentes de datos de [!DNL Adobe Experience Platform], como conjuntos de datos de evento, búsqueda y perfil. Estas conexiones permiten la integración de datos de una Conexión a una Vista de datos derivada. Las conexiones son la base de CJA y se crean a partir de conjuntos de datos de origen de [!DNL Experience Platform]. El acceso a Conexiones también permite ver el administrador de Conexiones, que le permite ver los conjuntos de datos subyacentes que componen la conexión, así como realizar selecciones críticas de edición y configuración.

Se recomienda restringir el acceso a la administración de Conexiones a un grupo de administración principal. Las configuraciones a nivel de Conexión tienen implicaciones contractuales con respecto a las asignaciones de volumen para los datos introducidos en Customer Journey Analytics.

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
