---
title: Creación de una vista de datos en Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 22%

---

# Creación de una vista de datos en Customer Journey Analytics

>[!NOTE]
>
>Esta documentación se debe usar después de completar el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Siga los pasos de esta página solo después de completar todos los pasos anteriores generados dinámicamente para su organización.
>
>Después de completar los pasos de esta página, continúe siguiendo los pasos de actualización que se generaron dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

La creación de una vista de datos implica crear métricas y dimensiones a partir de elementos de esquema o utilizar componentes estándares. La mayoría de los elementos de esquema pueden ser una dimensión o una métrica, según los requisitos de la empresa. Una vez arrastrado un elemento de esquema a una vista de datos, las opciones aparecen a la derecha, donde puede ajustar el funcionamiento de la dimensión o métrica en Customer Journey Analytics.

Para crear una vista de datos:

1. Inicie sesión en [Customer Journey Analytics](https://analytics.adobe.com) y vaya a la pestaña **[!UICONTROL Vistas de datos]**.

1. Seleccione **[!UICONTROL Crear nueva vista de datos]**. También puede seleccionar una vista de datos existente de la lista de vistas de datos para editarla.

1. En la ficha [!UICONTROL **Configurar**], especifique un nombre para la vista de datos y configure su configuración básica, componentes y opciones de calendario.

   Para obtener información detallada sobre cada campo, consulte [Configurar](/help/data-views/create-dataview.md#configure) en [Crear o editar una vista de datos](/help/data-views/create-dataview.md).

   ![Configuración de una vista de datos](assets/dataview-configure.png)

1. Seleccione la pestaña [!UICONTROL **Componentes**].

   En la pestaña [!UICONTROL **Componentes**] se establecen los componentes de una vista de datos, lo que significa que puede crear métricas y dimensiones a partir de elementos de esquema. También puede utilizar componentes estándares.

   ![Pestaña Componentes](assets/dataview-components.png)

1. En la pestaña [!UICONTROL **Componentes**], arrastre elementos de esquema desde el carril izquierdo a la sección [!UICONTROL **Métricas**] o a la sección [!UICONTROL **Dimension**]. Los elementos de esquema que agregue se convertirán en métricas o dimensiones en la vista de datos.

   Para obtener información detallada sobre las opciones disponibles al agregar componentes a una vista de datos, consulte [Componentes](/help/data-views/create-dataview.md#components) en [Crear o editar una vista de datos](/help/data-views/create-dataview.md).

1. Seleccione la pestaña [!UICONTROL **Configuración.**] Desde aquí, puede configurar filtros para aplicarlos a toda la vista de datos y configurar el tiempo de espera de la sesión y las métricas.

   Para obtener información detallada sobre las opciones disponibles al configurar opciones para una vista de datos, consulte [Configuración](/help/data-views/create-dataview.md#settings) en [Crear o editar una vista de datos](/help/data-views/create-dataview.md).

1. Seleccione **[!UICONTROL Guardar]** para guardar la configuración de la vista de datos.

1. Una vez especificada toda la configuración deseada, seleccione **[!UICONTROL Guardar y finalizar]**.

1. Continúe siguiendo los pasos de actualización generados dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

