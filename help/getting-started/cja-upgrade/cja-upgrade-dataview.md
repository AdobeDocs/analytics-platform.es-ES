---
title: Creación de una vista de datos en Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 95%

---

# Creación de una vista de datos en Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Creación de una vista de datos en Customer Journey Analytics"
>abstract="Una vista de datos es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión. <br><br>Aunque la creación inicial de la vista de datos tarda unos minutos, la configuración de cada dimensión y métrica con la configuración de componente deseada puede tardar varios días. Esta configuración se aplica de forma retroactiva, por lo que su organización puede perfeccionarla con el tiempo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

La creación de una vista de datos implica crear métricas y dimensiones a partir de elementos de esquema o utilizar componentes estándares. La mayoría de los elementos de esquema pueden ser una dimensión o una métrica según los requisitos de la empresa. Una vez arrastrado un elemento de esquema a una vista de datos, las opciones aparecen a la derecha, donde puede ajustar el funcionamiento de la dimensión o métrica en Customer Journey Analytics.

Para crear una vista de datos:

1. Inicie sesión en [Customer Journey Analytics](https://analytics.adobe.com) y seleccione **[!UICONTROL Vistas de datos]**, opcionalmente desde **[!UICONTROL Administración de datos]**, en el menú superior.

1. Seleccione **[!UICONTROL Crear nueva vista de datos]**. También puede seleccionar una vista de datos existente de la lista de vistas de datos para editarla.

1. En la pestaña [!UICONTROL **Configurar**], especifique un nombre para la vista de datos y lleve a cabo su configuración básica, componentes y opciones de calendario.

   Para obtener información detallada sobre cada campo, consulte [Configurar](/help/data-views/create-dataview.md#configure) en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md).

   ![Configuración de una vista de datos](assets/dataview-configure.png)

1. Seleccione la pestaña [!UICONTROL **Componentes**].

   La pestaña [!UICONTROL **Componentes**] es donde se establecen los componentes de una vista de datos, lo que significa que se pueden crear métricas y dimensiones a partir de elementos del esquema. También puede utilizar componentes estándares.

   ![Pestaña Componentes](assets/dataview-components.png)

1. En la pestaña [!UICONTROL **Componentes**], arrastre elementos del esquema desde el carril izquierdo hasta la sección [!UICONTROL **Métricas**] o hasta la sección [!UICONTROL **Dimensiones**]. Los elementos del esquema que añada se convertirán en métricas o dimensiones en la vista de datos.

   Para obtener información detallada sobre las opciones disponibles al añadir componentes a una vista de datos, consulte [Componentes](/help/data-views/create-dataview.md#components) en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md).

1. Seleccione la pestaña [!UICONTROL **Configuración.**] Desde aquí, puede configurar filtros para aplicarlos a toda la vista de datos y configurar el tiempo de espera de la sesión y las métricas.

   Para obtener información detallada sobre las opciones disponibles al configurar opciones para una vista de datos, consulte [Configuración](/help/data-views/create-dataview.md#settings) en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md).

1. Seleccionar **[!UICONTROL Guardar]** para almacenar la configuración de la vista de datos existente.

1. Una vez especificada toda la configuración deseada, seleccione **[!UICONTROL Guardar y finalizar]**.

{{upgrade-final-step}}
