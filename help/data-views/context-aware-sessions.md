---
title: Sesiones según el contexto
description: Configuración en una vista de datos que puede utilizar para definir sesiones contextuales.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: ht
source-wordcount: '236'
ht-degree: 100%

---


# Sesiones según el contexto

Las sesiones contextuales en Vistas de datos cambian el modo en que Customer Journey Analytics calcula las sesiones a partir de los datos de la conexión.

Dentro de la pestaña [!UICONTROL Configuración] de las vistas de datos, puede definir una sesión de cualquier manera para que coincida con la forma en que las personas interactúan con las experiencias digitales. Las definiciones de sesiones contextualizadas son inofensivas y no modifican los datos subyacentes. Puede configurar varias vistas de datos, cada una con su definición de sesión contextual específica, como base para sus proyectos de Workspace.

Para definir el contexto de una sesión para una vista de datos, haga lo siguiente:

1. Seleccione **[!UICONTROL Vistas de datos]** en la interfaz de usuario de Customer Journey Analytics.

1. Cree una nueva vista de datos o edite una existente. Consulte [Creación o edición de una vista de datos](create-dataview.md) para obtener más información.

1. Seleccione la pestaña **[!UICONTROL Configuración.]** Debajo de [!UICONTROL Configuración de sesión]:

   1. Escriba un valor para **[!UICONTROL tiempo de espera de sesión]** en [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL día(s)] o [!UICONTROL semana(s)]. El tiempo de espera de sesión determina cuánto tiempo puede estar inactiva una sesión (sin que se produzcan eventos) antes de iniciar una nueva.

   2. Seleccione una métrica de la lista **[!UICONTROL Suelte una métrica aquí]** debajo de [!UICONTROL Iniciar nueva sesión con una métrica]. También puede arrastrar y soltar una métrica desde el panel izquierdo en el campo **[!UICONTROL Suelte una métrica]**. La métrica seleccionada define el inicio de una nueva sesión. Puede definir más de una métrica.

1. Seleccione **[!UICONTROL Guardar]** o **[!UICONTROL Guardar y finalizar]** para guardar la definición de sesión contextual.

