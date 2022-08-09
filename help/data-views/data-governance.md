---
title: Compatibilidad con CJA para la administración de datos de Adobe Experience Platform
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# Compatibilidad con CJA para la administración de datos de Adobe Experience Platform

La integración entre CJA y [Administración de datos de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) permite el etiquetado de datos de CJA confidenciales y la aplicación de políticas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por el Experience Platform se pueden ver en el flujo de trabajo de vistas de datos de CJA. Estas etiquetas detienen o advierten a los usuarios que crean métricas y/o dimensiones a partir de campos confidenciales.

Además, cuando se exportan datos desde CJA (mediante informes, exportación, API, etc.), se añaden advertencias o etiquetas para notificar a los usuarios que un informe contiene información confidencial que debe tratarse de una manera específica.

Esta integración le permite administrar el cumplimiento de normas más fácilmente. Los administradores de datos de su organización pueden establecer políticas para restringir el uso. Como resultado, los usuarios de CJA pueden usar los datos con mayor seguridad, sabiendo que cumplen con las políticas definidas por los administradores de datos.

## Etiquetado y políticas en Adobe Experience Platform

Al crear un conjunto de datos en Experience Platform, puede crear [etiquetas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) para algunos o todos los elementos del conjunto de datos. Hasta ahora, estas etiquetas no estaban expuestas en CJA. Con esta versión, puede ver estas etiquetas en CJA. De especial interés para CJA es la etiqueta C8, que dice &quot;Los datos no se pueden usar para medir los sitios web o las aplicaciones de su organización&quot;.

El etiquetado en sí mismo no significa que se apliquen estas etiquetas de uso de datos. Para eso se utilizan las políticas. Las políticas se crean mediante la variable [API del servicio de directivas](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) en Experience Platform.

Las políticas tienen dos componentes: la etiqueta de datos y una acción de marketing que los consumidores de datos pueden realizar en el contexto de las políticas de uso restringido de datos. En el contexto de CJA, dos Adobes definidos [acciones de marketing](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) son importantes:

* Analytics: uso de datos con fines analíticos, como medición, análisis e informes sobre el uso que hacen los consumidores de las aplicaciones o los sitios de su organización.

* Exportar estos datos fuera del entorno de Adobe, como exportar datos a un tercero.

Asocia etiquetas y acciones de marketing con una directiva y, a continuación, activa la directiva. La política toma la etiqueta y la acción de marketing y dice: aplique esta restricción. En CJA aparecen dos políticas definidas por Adobe:

* Política de Analytics
* Descargar directiva

## Ver etiquetas de datos en vistas de datos de CJA

Las etiquetas de datos creadas en el Experience Platform se muestran en tres ubicaciones de la interfaz de usuario de vistas de datos:

| Ubicación | Descripción |
| --- | --- |
| Botón Información de un campo de esquema | Al hacer clic en este botón, se indica qué etiquetas de uso de datos se aplican actualmente a un campo:<p>![](assets/data-label-left.png) |
| Carril derecho debajo [Configuración de componentes](/help/data-views/component-settings/overview.md) | Todas las etiquetas de uso de datos se enumeran aquí:<p>![](assets/data-label-right.png) |
| Agregar etiquetas de datos como una columna | Puede agregar Etiquetas de datos como una columna a las columnas Componentes incluidos en las vistas de datos. Haga clic en el icono del selector de columnas y seleccione Etiquetas de uso de datos:<p>![](assets/data-label-column.png) |

### Filtro en las etiquetas de Control de datos en CJA

En el editor de vistas de datos, haga clic en el icono Filtro de la pista izquierda y filtre los componentes de vistas de datos por etiquetas de control de datos:

![](assets/filter-labels.png)

### Filtrar por políticas de control de datos en CJA

Puede comprobar si hay una directiva activada que bloquee el uso de ciertos elementos de vista de datos de CJA para análisis o exportación con fines específicos.

De nuevo, haga clic en el icono Filtro en el carril izquierdo y, en Administración de datos, haga clic en Directivas:

![](assets/filter-policies.png)

Si la directiva está activada, los campos de esquema que tienen ciertas etiquetas de datos (como C8) asociadas a ellas no se pueden usar para fines de análisis ni descarga (como enviar por correo electrónico o compartir archivos pdf) en CJA Workspace.

Tenga en cuenta lo siguiente

* No se le permite agregarlas a vistas de datos. Estos campos aparecerán atenuados en la lista de campos Esquema del carril izquierdo.
* No se puede guardar una vista de datos que tenga campos bloqueados.


