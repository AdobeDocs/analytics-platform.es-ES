---
title: Control de acceso de CJA
description: Obtenga información sobre los requisitos de control de acceso para crear conexiones, agregar conjuntos de datos, crear vistas de datos, etc.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: e5ae592c6765638e26ee5252f458e82af9d24e44
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Control de acceso de CJA

Para acceder y realizar tareas en Customer Journey Analytics, se le debe agregar a usted como administrador al **Perfil de producto de Customer Journey Analytics** en [Admin Console](https://adminconsole.adobe.com/enterprise/). Los administradores de productos tienen los siguientes permisos:

* Crear/actualizar/eliminar conexiones o Vistas de datos
* Actualizar o eliminar proyectos, filtros, métricas calculadas o filtros creados por otros usuarios
* Compartir proyectos de Workspace con todos los usuarios

## Permisos necesarios de Adobe Experience Platform

Convertirse en administrador de productos dentro de Customer Journey Analytics no es suficiente para crear, actualizar o eliminar una conexión. Para crear una conexión a un conjunto de datos de Experience Platform, también necesita permisos de Experience Platform. Específicamente, debe formar parte de un **perfil del producto Experience Platform** que le proporciona los siguientes permisos:

* Esquemas de vistas
* Administrar esquemas
* Ver espacios de nombres de identidad
* Conjuntos de datos de vistas

Para obtener más información sobre los permisos de Experience Platform, consulte [Control de acceso en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es).

## Conceder acceso a métricas o dimensiones individuales

No se puede otorgar ni rechazar permisos a métricas o dimensiones individuales en Customer Journey Analytics como se puede hacer en la versión tradicional de Adobe Analytics. Las métricas y dimensiones se pueden modificar en las [vistas de datos](/help/data-views/data-views.md) y, por lo tanto, están sujetas a cambios en CJA, que también modifica la creación de informes de forma retroactiva.

## Acceso de usuarios

Los usuarios que no son administradores de productos (usuarios) en Customer Journey Analytics no pueden realizar vistas de las vistas de datos o las conexiones, pero sí crear filtros, proyectos y métricas calculadas.

## Revisión de proyecto de Workspace

Para obtener más información sobre cómo limitar componentes (dimensiones, métricas, segmentos e intervalos de fechas) en el nivel de proyecto, consulte [Depurar proyectos](/help/analysis-workspace/curate-share/curate.md).



