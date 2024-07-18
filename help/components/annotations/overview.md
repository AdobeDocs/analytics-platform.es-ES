---
title: Descripción general de anotaciones
description: Cómo utilizar anotaciones en Espacio de trabajo.
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 100%

---

# Descripción general de anotaciones

Las anotaciones le permiten comunicar de forma eficaz los matices y perspectivas de datos contextuales a su organización. Permiten enlazar eventos de calendario con dimensiones/métricas específicas. Puede anotar una fecha o un intervalo de fechas con problemas de datos conocidos, días festivos, lanzamientos de campañas, etc. A continuación, puede mostrar gráficamente los eventos y ver si las campañas u otros eventos han afectado al tráfico del sitio, al uso de aplicaciones móviles, a los ingresos o a alguna otra métrica.

Por ejemplo, supongamos que comparte proyectos con su organización. Si tuvo un pico importante en el tráfico debido a una campaña de marketing, podría crear una anotación de “Fecha de inicio de la campaña” y ampliarla a toda la vista de datos. Cuando los usuarios ven cualquier conjunto de datos que incluya esa fecha, verán la anotación dentro de sus proyectos, junto a sus datos.

![Gráfico de líneas con anotación resaltada.](assets/multi-day.png)

Recuerde:

* Las anotaciones se pueden asociar a una sola fecha o a un intervalo de fechas.

* Pueden aplicarse a todo el conjunto de datos o a métricas, dimensiones o filtros especificados.

* Pueden aplicarse al proyecto en el que se crearon (predeterminado) o a todos los proyectos.

* Pueden aplicarse a la vista de datos en la que se crearon (predeterminada) o a todas las vistas de datos.

## Permisos

De forma predeterminada, solo los administradores pueden crear anotaciones. Los usuarios tienen derechos para ver las anotaciones como lo hacen con otros componentes de Analytics (como filtros, métricas calculadas, etc.).

Sin embargo, los administradores pueden dar el permiso de [!UICONTROL Creación de anotaciones] (herramientas de Analytics) a los usuarios a través de [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=es).

## Activación o desactivación de anotaciones {#annotations-on-off}

Las anotaciones se pueden activar o desactivar en varios niveles:

* En el nivel de visualización: configuración de [!UICONTROL Visualización] > [!UICONTROL Mostrar anotaciones]

* En el nivel de proyecto: [!UICONTROL Información y configuración del proyecto] > [!UICONTROL Mostrar anotaciones]

* En el nivel de usuario: [!UICONTROL Componentes] > [!UICONTROL Preferencias de usuario] > [!UICONTROL Datos] > [!UICONTROL Mostrar anotaciones]

![Cuadro de diálogo Configuración de visualización con Mostrar anotaciones resaltado](assets/show-ann.png)

![Preferencias del usuario que resaltan Mostrar anotaciones.](assets/show-ann2.png)
