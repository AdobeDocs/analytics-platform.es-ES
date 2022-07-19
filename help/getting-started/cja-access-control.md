---
title: Control de acceso de CJA
description: Obtenga información sobre los requisitos de control de acceso para crear conexiones, agregar conjuntos de datos, crear vistas de datos, etc.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# Control de acceso de CJA

Para crear conexiones, agregar conjuntos de datos y demás, necesita los siguientes permisos en la [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Para acceder a Customer Journey Analytics o establecer una conexión, se le tendrá que añadir como Admin al **producto de Customer Journey Analytics** en [Admin Console](https://adminconsole.adobe.com/enterprise/). Los administradores de productos tienen los siguientes permisos:
   * Crear/actualizar/eliminar conexiones o Vistas de datos
   * Actualizar o eliminar proyectos, filtros, métricas calculadas o filtros creados por otros usuarios
   * Compartir un proyecto del Espacio de trabajo con todos los usuarios
* Convertirse en administrador de productos dentro de Customer Journey Analytics no es suficiente para crear, actualizar o eliminar una conexión. Para crear una conexión a un conjunto de datos de Experience Platform, también necesita permisos de Experience Platform. Específicamente, debe formar parte de un **perfil del producto Experience Platform** que le proporciona los siguientes permisos:
   * Esquemas de vistas
   * Administrar esquemas
   * Ver espacios de nombres de identidad
   * Conjuntos de datos de vistas

Para obtener más información sobre los permisos de Experience Platform, consulte [Control de acceso en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es).

>[!NOTE]
>
>No se puede otorgar ni rechazar permisos a métricas o dimensiones individuales en Customer Journey Analytics como se puede hacer en la versión tradicional de Adobe Analytics. Las métricas y dimensiones se pueden modificar en las [vistas de datos](/help/data-views/data-views.md) y, por lo tanto, están sujetas a cambios en CJA, que también modifica la creación de informes de forma retroactiva.

## Acceso de usuarios

Los usuarios que no son administradores (usuarios) en Customer Journey Analytics no pueden realizar vistas de las Vistas de datos o las Conexiones, pero sí crear filtros, proyectos y métricas calculadas.