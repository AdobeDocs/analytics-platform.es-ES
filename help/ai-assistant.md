---
description: Cómo hacer preguntas sobre la documentación de Customer Journey Analytics
title: Asistente de IA para Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---


# Asistente de IA para Adobe Customer Journey Analytics

El asistente de IA es una experiencia conversacional que permite a los profesionales realizar tareas a un ritmo rápido. Si la tarea consiste en comprender los conceptos, solucionar problemas o buscar a través de la información. El asistente de IA también permite a los no expertos realizar tareas expertas y aumenta la calidad general del trabajo.

El asistente de IA en Customer Journey Analytics está formado en su documentación de Adobe Experience League. Cuando se le hace una pregunta, AI Assistant responde con una respuesta útil que permite un aprendizaje rápido.

Como usuario novato, puede utilizar el asistente de IA para aprender conceptos de Customer Journey Analytics e incorporarse a productos y funciones con los que no está familiarizado. Como usuario experimentado, puede utilizar el Asistente de IA para presentar casos de uso o sugerencias y trucos más avanzados.

Algunos ejemplos de preguntas conceptuales son:

* ¿Cuál es la diferencia entre la ingesta por lotes y la transmisión?
* ¿Para qué se utiliza Customer Journey Analytics?
* ¿Cómo configuro una vista de datos?

Las preguntas que no entran en el ámbito de Customer Journey Analytics, como las preguntas sobre otros productos de Adobe como Adobe Target y Adobe Creative Cloud Suite, no se pueden responder.

El asistente de IA para Customer Journey Analytics está disponible para todos los niveles de productos.

## Conocimiento del producto {#knowledge}

El modelo de recuperación del conocimiento del producto está formado en Customer Journey Analytics. Otras funciones, como el análisis de datos, se implementarán más adelante.

| Conocimiento del producto | Ejemplos |
| --- | --- |
| Aprendizaje puntual | <ul><li>¿Cuál es la diferencia entre Adobe Analytics y Customer Journey Analytics?</li><li>¿Cómo se crea una métrica calculada?</li></ul> |
| Abrir detección | <ul><li>¿Cómo puedo exportar un proyecto de Workspace?</li><li>¿Cómo puedo encontrar componentes duplicados de Workspace?</li></ul> |
| Resolución de problemas | <ul><li>¿Cuánto tiempo tardan los datos en entrar en CJA?</li><li>¿Cuántos campos derivados puedo tener en una conexión de Customer Journey Analytics?</li></ul> |

## Acceso a funciones

Los siguientes parámetros rigen el acceso a la función de asistente de IA:

* **Acceso a la solución**: el Asistente de IA está disponible en Customer Journey Analytics, pero no en Adobe Analytics. También está disponible en Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP y otras aplicaciones de Experience Platform.

* **Acceso contractual**: Si no puede usar el Asistente de IA, comuníquese con el administrador de su organización o con el representante de cuenta Adobe. Antes de que su organización pueda utilizar AI Assistant, su empresa debe aceptar ciertos términos legales relacionados con GenAI.

* **Permisos**: en [!UICONTROL Adobe Admin Console], el permiso de [!UICONTROL Herramientas de informes] **[!UICONTROL Asistente de IA: Conocimiento del producto]** determina el acceso a esta herramienta. Un [administrador de perfil de producto](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html) debe seguir estos pasos en el [!UICONTROL Admin Console]:
   1. Vaya a **[!UICONTROL Admin Console]** > **[!UICONTROL Productos y servicios]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfiles de productos]**
   1. Seleccione el título del perfil de producto para el que desea proporcionar acceso a [!UICONTROL AI Assistant: Product Knowledge].
   1. En el perfil de producto específico, seleccione **[!UICONTROL Permisos]**.
   1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para editar **[!UICONTROL Herramientas de informes]**.
   1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) para agregar **Asistente de IA: conocimiento del producto** a **[!UICONTROL Elementos de permiso incluidos]**.

      ![Agregar permiso](assets/ai-assistant-permissions.png).

   1. Seleccione **[!UICONTROL Guardar]** para guardar los permisos.

Consulte [Control de acceso](/help/technotes/access-control.md#access-control) para obtener más información.

## Acceso al Asistente de IA en la IU de Customer Journey Analytics

1. Para iniciar el asistente de IA, seleccione el icono Asistente de IA en el encabezado superior de cualquier página de la interfaz de usuario del Customer Journey Analytics.

   ![icono del Asistente de IA](assets/ai-asst1.png)

   Al utilizar el Asistente de inteligencia artificial por primera vez, aparece un aviso de exención de responsabilidad con algunos términos y condiciones de uso del Asistente.

1. En el cuadro que se proporciona, haga una pregunta específica en lenguaje natural al asistente de IA.

   ![Cuadro de preguntas](assets/ai-asst2.png)

1. (Opcional) Para mostrar las fuentes, haga clic en **[!UICONTROL Mostrar fuentes]**, y se mostrarán las fuentes de documentación que indicaron la respuesta.

1. (Opcional) También puede proporcionar una votación de pulgares hacia arriba o hacia abajo sobre la utilidad de cualquier respuesta dada.

1. (Opcional) Puede marcar la respuesta para contenido inapropiado o perjudicial.
