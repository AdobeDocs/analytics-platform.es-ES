---
title: Control de acceso de CJA
description: Obtenga información sobre los requisitos de control de acceso para los tres niveles de acceso en CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# Control de acceso de CJA

El Customer Journey Analytics (CJA) se rige por tres niveles de acceso o por tres funciones: Función de administrador de productos, función de administrador de perfil de producto y acceso de usuario. En este tema se explican estas funciones con más detalle.

## Función de administrador de productos

Los administradores de productos tienen permisos para completar cualquier tarea necesaria dentro de CJA. Debe agregarse como administrador de productos al **Perfil de producto del Customer Journey Analytics** en el [Admin Console](https://adminconsole.adobe.com/enterprise/) en Customer Journey Analytics > ficha Administradores > Agregar administrador. Los administradores de productos tienen los siguientes permisos:

* Crear/actualizar/eliminar conexiones o Vistas de datos
* Actualizar o eliminar proyectos, filtros, métricas calculadas o filtros creados por otros usuarios
* Compartir proyectos de Workspace con todos los usuarios

Convertirse en administrador de productos dentro de Customer Journey Analytics no es suficiente para crear, actualizar o eliminar una conexión. Para crear una conexión a un conjunto de datos de Experience Platform, también necesita permisos de Experience Platform. Específicamente, debe formar parte de un **perfil del producto Experience Platform** que le proporciona los siguientes permisos:

* Modelado de datos: Esquemas de vista, Administrar esquemas
* Administración de datos: Ver conjuntos de datos, Administrar conjuntos de datos
* Ingesta de datos: Administrar fuentes
* Ver espacios de nombres de identidad

Para obtener más información sobre los permisos de Experience Platform, consulte [Control de acceso en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es).

## Función de administrador del perfil de producto

Esta función es similar al administrador de productos, pero tiene un alcance más limitado. Un perfil de producto es un conjunto de permisos. Por ejemplo, un administrador de perfil de producto puede proporcionar acceso a todas las vistas de datos o a determinadas vistas de datos a los miembros de un perfil de producto. Para las herramientas de creación de informes, estos administradores pueden añadir estos permisos:

![permisos de admin console](assets/permissions.png)

## Acceso de nivel de usuario

Los usuarios que no son administradores (usuarios) de Customer Journey Analytics no pueden crear, editar ni ver conexiones o vistas de datos. Los usuarios pueden crear filtros, proyectos, audiencias y métricas calculadas con permisos especiales en el Admin Console.

## Revisión de proyecto de Workspace

Para obtener más información sobre cómo limitar componentes (dimensiones, métricas, segmentos e intervalos de fechas) en el nivel de proyecto de Workspace y cómo se vincula la depuración a las vistas de datos, consulte [Depurar proyectos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acceso a métricas o dimensiones individuales

No se puede otorgar ni rechazar permisos a métricas o dimensiones individuales en Customer Journey Analytics como se puede hacer en la versión tradicional de Adobe Analytics. Las métricas y dimensiones se pueden modificar en las [vistas de datos](/help/data-views/data-views.md) y, por lo tanto, están sujetas a cambios en CJA, que también modifica la creación de informes de forma retroactiva.

