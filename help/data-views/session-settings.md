---
title: Configuración de sesión
description: Configuración en una vista de datos que puede utilizar para definir la duración de una sesión y el déclencheur para iniciar una nueva
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: bb2061f9119b8391bf3cedce4029685537d1e239
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 38%

---


# Configuración de sesión

La configuración de sesión en Vistas de datos cambia la forma en que Customer Journey Analytics calcula las sesiones a partir de los datos de la conexión.

Dentro de la pestaña **[!UICONTROL Configuración]** de las vistas de datos, puede definir una sesión de cualquier manera para que coincida con la forma en que las personas interactúan con las experiencias digitales. Las definiciones de configuración de sesión no son destructivas y no modifican los datos subyacentes. Puede configurar varias vistas de datos (cada una con su propia definición de configuración de sesión específica) como base para sus proyectos de Workspace.

Para definir el contexto de una sesión para una vista de datos, haga lo siguiente:

1. Seleccione **[!UICONTROL Vistas de datos]** en la interfaz de usuario de Customer Journey Analytics.

2. Cree una nueva vista de datos o edite una existente. Consulte [Creación o edición de una vista de datos](create-dataview.md) para obtener más información.

3. Seleccione la pestaña **[!UICONTROL Configuración.]** Debajo de [!UICONTROL Configuración de sesión]:

   1. Escriba un valor para **[!UICONTROL tiempo de espera de sesión]** en [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL día(s)] o [!UICONTROL semana(s)]. El tiempo de espera de sesión determina cuánto tiempo puede estar inactiva una sesión (sin que se produzcan eventos) antes de iniciar una nueva.

      Utilice un breve tiempo de espera de sesión (por ejemplo, 30 minutos) si está interesado en analizar principalmente interacciones en línea. Por ejemplo, analizar si los perfiles que visitan las páginas de productos de su tienda en línea agregaron productos al carro de compras o incluso los compraron en línea.

      Utilice un tiempo de espera de sesión largo (por ejemplo, 3 meses) si combina datos en línea y sin conexión y desea analizar si los clientes que han adquirido uno o más de sus productos han llamado a su centro de contacto en los tres primeros meses después de su compra.


   2. Seleccione una métrica de la lista **[!UICONTROL Suelte una métrica aquí]** debajo de **[!UICONTROL Iniciar nueva sesión con una métrica]**. También puede arrastrar y soltar una métrica desde el panel izquierdo en el campo **[!UICONTROL Suelte una métrica]**. La métrica seleccionada define el inicio de una nueva sesión. Puede definir más de una métrica.

      Puede utilizar cualquier tipo de métrica para definir una nueva sesión. Por ejemplo, imagine que desea definir una nueva sesión cada vez que un perfil inicia la aplicación móvil. Entrada **[!UICONTROL Vista de datos]** > **[!UICONTROL Componentes]**, define un componente de tipo métrica, denominado **[!UICONTROL Lanzamientos]**, basado en un **[!UICONTROL appInteraction]** **[!UICONTROL Nombre]** campo de esquema. Especifique también la variable **[!UICONTROL Lanzamientos]** componente de métrica para contar solo el valor cuando el valor coincida `launch`.

      ![Lanzamientos del componente de métrica de interacción de aplicación](assets/component-launches.png)

      A continuación, arrastre y suelte o seleccione la opción **[!UICONTROL Lanzamientos]** métrica como métrica para definir una nueva sesión.

      ![Inicios de configuración de sesión](assets/session-settings-launches-metric.png)



4. Seleccionar **[!UICONTROL Guardar]** o **[!UICONTROL Guardar y finalizar]** para guardar la definición de la configuración de sesión.

