---
title: Control de acceso de CJA
description: Obtenga información sobre los requisitos de control de acceso para crear conexiones, agregar conjuntos de datos, crear vistas de datos, etc.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 53%

---

# Control de acceso de CJA

Para acceder y realizar tareas en Customer Journey Analytics, debe agregarlo como administrador al **Perfil de producto del Customer Journey Analytics** en el [Admin Console](https://adminconsole.adobe.com/enterprise/). Los administradores de productos tienen los siguientes permisos:

* Crear/actualizar/eliminar conexiones o vistas de datos
* Actualizar o eliminar proyectos, filtros, métricas calculadas o filtros creados por otros usuarios
* Compartir proyectos de Workspace con todos los usuarios

## Permisos necesarios de Adobe Experience Platform

Convertirse en administrador de productos solo en Customer Journey Analytics no es suficiente para crear, actualizar o eliminar una conexión. Para crear una conexión a un conjunto de datos de Experience Platform, también necesita permisos de Experience Platform. Específicamente, debe formar parte de un **perfil del producto Experience Platform** que le proporciona los siguientes permisos:

* Esquemas de vistas
* Administrar esquemas
* Ver espacios de nombres de identidad
* Conjuntos de datos de vistas

Para obtener más información sobre los permisos de Experience Platform, consulte [Control de acceso en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es).

## Conceder acceso a métricas o dimensiones individuales

No se puede otorgar ni rechazar permisos a métricas o dimensiones individuales en Customer Journey Analytics como se puede hacer en la versión tradicional de Adobe Analytics. Las métricas y dimensiones se pueden modificar en las [vistas de datos](/help/data-views/data-views.md) y, por lo tanto, están sujetas a cambios en CJA, que también modifica la creación de informes de forma retroactiva.

## Acceso de usuarios

Los usuarios que no son administradores (usuarios) de Customer Journey Analytics no pueden ver vistas de datos o conexiones, pero sí crear filtros, proyectos y métricas calculadas.

