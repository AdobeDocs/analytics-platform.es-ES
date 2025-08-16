---
description: Obtenga información sobre cómo utilizar los informes en tiempo real en Analysis Workspace.
title: Usar informes en tiempo real
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 14%

---

# Uso de creación de informes en tiempo real {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Actualización en tiempo real"
>abstract="Habilite la opción para actualizar los datos y las visualizaciones en este panel en tiempo real."

{{release-limited-testing}}

Para usar los informes en tiempo real, habilita la opción **[!UICONTROL Actualización en tiempo real]** en cualquiera de los siguientes paneles de su proyecto de Workspace:

* [Panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md)
* [De forma libre](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Atribución](/help/analysis-workspace/c-panels/attribution.md)
* [Elemento siguiente o anterior](/help/analysis-workspace/c-panels/next-previous.md)

Verá un mensaje con la marca de tiempo de la actualización más reciente de los datos. Por ejemplo: [!UICONTROL &#x200B; *Última actualización a las 07:55 pm*].

Seleccione el periodo en tiempo real sobre el que desea crear el informe desde el menú desplegable. Entre las opciones disponibles se encuentran:

* [!UICONTROL Últimos 15 minutos]
* [!UICONTROL Últimos 30 minutos]
* [!UICONTROL Última hora]
* [!UICONTROL Últimas 8 horas]
* [!UICONTROL Últimas 24 horas]

Ahora, todas las visualizaciones del panel se actualizan cada minuto durante un máximo de 30 minutos, mientras que la pestaña del explorador con el panel habilitado para la actualización en tiempo real está activa.

Por ejemplo, vea a continuación una instantánea de **[!UICONTROL Panel de informes en tiempo real]** que actualiza la visualización de barra de **[!UICONTROL Ingresos totales por hora]** y la tabla de forma libre de **[!UICONTROL Ingresos totales por hora]** a medida que el tiempo pasa de **[!UICONTROL *06:26pm*]** a **[!UICONTROL *06:27 pm *]**.

![Actualización en tiempo real](assets/real-time-refresh.gif)

Transcurridos 30 minutos, o en cuanto la ficha del explorador se vuelve inactiva, el conmutador **[!UICONTROL Actualización en tiempo real]** se desactiva automáticamente y se detienen las actualizaciones en tiempo real.
