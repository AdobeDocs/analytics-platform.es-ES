---
description: Obtenga información sobre cómo utilizar los informes en tiempo real en Analysis Workspace.
title: Usar informes en tiempo real
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 5%

---


# Uso de informes en tiempo real

{{release-limited-testing}}

Para usar los informes en tiempo real, habilita la opción **[!UICONTROL Actualización en tiempo real]** en cualquiera de los siguientes paneles de su proyecto de Workspace:



* [Panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md)
* [Panel de forma libre](/help/analysis-workspace/c-panels/freeform-panel.md)
* ...

Verá un mensaje con la marca de tiempo de la actualización más reciente de los datos. Por ejemplo: [!UICONTROL  *Última actualización a las 07:55 pm*].

Seleccione el período en tiempo real sobre el que desea crear el informe en el menú desplegable. Entre las opciones disponibles se encuentran:

* [!UICONTROL Últimos 15 minutos]
* [!UICONTROL Últimos 30 minutos]
* [!UICONTROL Última hora]
* [!UICONTROL Últimas 8 horas]
* [!UICONTROL Últimas 24 horas]

Ahora todas las visualizaciones se actualizan cada minuto durante un máximo de 30 minutos, mientras que la pestaña del explorador con el panel habilitado para la actualización en tiempo real está activa.

![Actualización en tiempo real](assets/real-time-refresh.gif)

Transcurridos 30 minutos, o en cuanto la ficha del explorador se vuelve inactiva, el conmutador **[!UICONTROL Actualización en tiempo real]** se deshabilita automáticamente y se detienen las actualizaciones en tiempo real.
