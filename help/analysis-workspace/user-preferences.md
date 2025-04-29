---
title: Establecimiento de las preferencias de usuario en Analysis Workspace
description: Puede establecer preferencias generales y de proyecto para los usuarios.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: e4ddb98b800457e407bb414ed4929c5d5018cf30
workflow-type: tm+mt
source-wordcount: '3947'
ht-degree: 74%

---

# Preferencias de usuario

Puede administrar la configuración de Analysis Workspace y sus componentes relacionados para todos los proyectos o paneles nuevos que cree. Los proyectos y paneles existentes no se ven afectados.

## Actualizar preferencias

Puede actualizar sus preferencias de las siguientes maneras:

- Seleccione ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Editar preferencias]** de la interfaz principal de Workspace.
- Seleccione **[!UICONTROL Proyecto]** > **[!UICONTROL Preferencias de usuario]** en el menú cuando trabaje en un proyecto de Workspace.
- Seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Preferencias]** en la barra de menús superior de Customer Journey Analytics (solo disponible para administradores de productos).

## Configurar preferencias

Puede configurar las siguientes preferencias:

### Preferencias generales

Las preferencias generales se aplican a su experiencia de Customer Journey Analytics en el explorador. Para obtener información sobre cómo acceder a estas preferencias, consulte [Actualizar preferencias](#update-preferences).

| Preferencia | Opciones |
| --- | --- |
| **[!UICONTROL Página de aterrizaje]** | Elija la página que se muestra como predeterminada al acceder a Customer Journey Analytics: <ul><li>Lista de proyectos (predeterminado)</li><li>Proyecto en blanco</li><li>Análisis guiado de Tendencias en blanco</li><li>Proyecto específico seleccionado de una lista</li></ul> |
| **[!UICONTROL Sugerencias]** | Muestra sugerencias en un cuadro azul en el área inferior derecha de Analysis Workspace. <p>Esta opción está habilitada de manera predeterminada.</p> |
| **[!UICONTROL Componentes mostrados en los grupos del panel izquierdo]** | Elige cuántos componentes de cada grupo se van a mostrar en el menú Componentes del panel izquierdo. <p>Si elige 0 para un grupo de componentes, ya no se puede acceder al grupo de componentes desde el panel izquierdo.</p><p>De forma predeterminada, se muestran cinco componentes para cada uno de los siguientes grupos:</p> <ul><li>Dimensiones</li><li>Métricas</li><li>Segmentos</li><li>Intervalos de fechas</li></ul> <p>Para obtener más información sobre los componentes en Analysis Workspace, consulte la [Información general sobre componentes](/help/components/overview.md).</p> |

### Preferencias de organización de IMS {#ims-organization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Permitir compartir solo con usuarios de Workspace"
>abstract="Cuando está habilitada, la opción **[!UICONTROL Compartir con cualquiera]** ya no está disponible para los usuarios cuando comparten un proyecto de Analysis Workspace. Las personas que anteriormente recibieron acceso a un proyecto mediante esta opción de uso compartido ya no pueden acceder al proyecto."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Requiere autenticación de Experience Cloud"
>abstract="Cuando está habilitada, las personas que tienen acceso a un proyecto desde la opción Compartir con cualquiera de Analysis Workspace deben autenticarse mediante sus credenciales de Experience Cloud."

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Permitir comentarios sobre proyectos"
>abstract="Cuando se habilita, hay un área de comentarios disponible en el carril derecho de cada proyecto en Analysis Workspace."

<!-- markdownlint-enable MD034 -->

Puede actualizar las preferencias de la compañía que se aplican a todas las personas y proyectos de su organización. Para obtener información sobre cómo acceder a estas preferencias, consulte [Actualizar preferencias](#update-preferences).

| Sección | Preferencia | Opciones |
| --- | --- | --- |
| **Uso compartido de proyectos** | | |
| | Permitir compartir solo con usuarios de Workspace | Cuando esta opción está habilitada, las personas de su organización no pueden ver la opción **[!UICONTROL Compartir con cualquiera]** en el menú **[!UICONTROL Compartir]**. Esto significa que no se pueden compartir proyectos con personas que no tengan una cuenta de Analysis Workspace en su organización, tal como se describe en [Compartir un proyecto con cualquiera (no se requiere inicio de sesión)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) en [Compartir proyectos](/help/analysis-workspace/curate-share/share-projects.md).<br/>Esta opción está deshabilitada de forma predeterminada para todas las organizaciones (lo que significa que los usuarios pueden compartir proyectos con personas externas a la organización) excepto para los clientes que tengan licencia de Healthcare Shield. <p>Tenga en cuenta lo siguiente al activar o desactivar esta opción:<ul><li>Cuando se activa esta opción, las personas que anteriormente recibieron acceso a un proyecto mediante la opción de uso compartido [!UICONTROL Compartir con cualquiera] ya no pueden acceder al proyecto.</li><li>Si esta opción está habilitada (para permitir el uso compartido solo con usuarios de Workspace) y luego deshabilitada (para permitir el uso compartido con cualquier persona), las personas que anteriormente recibieron acceso a un proyecto mediante la opción de uso compartido [!UICONTROL Compartir con cualquiera] no recuperan automáticamente su acceso al proyecto. En este caso, el usuario que ha compartido el proyecto debe habilitar la opción [!UICONTROL **El vínculo está activo**] que está disponible al compartir un proyecto con cualquier persona **([!UICONTROL Compartir]** > **[!UICONTROL Compartir con cualquiera]**), tal como se describe en [Compartir un proyecto con cualquiera (no se requiere inicio de sesión)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) en [Compartir proyectos](/help/analysis-workspace/curate-share/share-projects.md).</li><li>**Para los clientes que tengan licencia de Healthcare Shield:** esta opción está habilitada de forma predeterminada y no se puede deshabilitar. Antes de deshabilitar esta opción para que los usuarios puedan usar la opción de uso compartido [!UICONTROL Compartir con cualquiera], debe añadir primero el permiso [!UICONTROL Compartir vínculos de proyectos con cualquiera] (que se encuentra en [!UICONTROL Herramientas de creación de informes]) en Adobe Admin Console. Una vez añadido el permiso, puede deshabilitar esta opción y aceptar el aviso legal resultante. Para obtener información sobre cómo añadir un permiso en Admin Console, consulte [Administración de permisos de productos en Admin Console](https://helpx.adobe.com/es/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Requiere autenticación de Experience Cloud | Cuando esta opción está habilitada, las personas a las que se les da acceso a un proyecto desde la opción Compartir con cualquiera de Analysis Workspace deben autenticarse con sus credenciales de Experience Cloud.<p>Después de habilitar esta opción, cada vez que se comparta un proyecto con la opción de uso compartido [!UICONTROL Compartir con alguien], se habilitará la opción [!UICONTROL Requiere autenticación de Experience Cloud] en el cuadro de diálogo de uso compartido y la persona que comparte el proyecto no podrá deshabilitarla. Para obtener información sobre cómo se pueden compartir proyectos con cualquier persona, consulte [Compartir un proyecto con cualquiera (no se requiere inicio de sesión)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) en[Compartir proyectos](/help/analysis-workspace/curate-share/share-projects.md). <p> <p>Ten en cuenta lo siguiente al habilitar esta opción: <ul><li>Al habilitar esta opción, se desactivan todos los proyectos que se compartieron anteriormente con la opción de uso compartido [!UICONTROL Compartir con cualquiera] y que no tienen activada la opción [!UICONTROL Se requiere autenticación de Experience Cloud].<p>Si esta opción está habilitada (se requiere autenticación de Experience Cloud) y luego se deshabilita (para permitir que cualquier persona con el vínculo acceda al proyecto), las personas que anteriormente recibieron acceso a un proyecto mediante la opción de uso compartido [!UICONTROL Compartir con alguien] no recuperan automáticamente su acceso al proyecto. En este caso, el usuario o la usuaria que compartió el proyecto debe habilitar la opción [!UICONTROL El vínculo está activo] que está disponible al compartir un proyecto con cualquier persona **([!UICONTROL Compartir]** > **[!UICONTROL Compartir con cualquiera]** > **[!UICONTROL El vínculo está activo]**), tal como se describe en [Compartir un proyecto con cualquiera (no se requiere inicio de sesión)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) en [Compartir proyectos](/help/analysis-workspace/curate-share/share-projects.md).</li><li>Esta opción solo está disponible si el SSO está implementado en su organización. Para obtener información sobre cómo los administradores del sistema pueden habilitar el SSO para su organización, consulta [Configurar la identidad y el inicio de sesión único](https://helpx.adobe.com/es/enterprise/using/set-up-identity.html).</p><p>Si SSO está configurado para su organización, compruebe si se ha implementado algún tipo de creación de cuenta automática en la consola. Normalmente, un administrador del sistema lo configuraría, tal como se describe en [Habilitar la creación automática de cuentas](https://helpx.adobe.com/es/enterprise/using/automatic-account-creation.html).</li><li>Si su organización dispone de licencias para Healthcare Shield, esta opción está habilitada de forma predeterminada y no se puede deshabilitar.</li></ul> |

{style="table-layout:auto"}

<!-- 

Add this to the table above - exchange - for pipe: (End of April, 2025 when project commenting is GA)

**Project commenting** 
- - Allow commenting on projects - When this option is enabled, a comments area is available in the right rail of each project in Analysis Workspace. <p>Project owners can disable the comments area for a given project, as described in [Create projects](/help/analysis-workspace/build-workspace-project/create-projects.md).</p> <p>For more information about commenting in Analysis Workspace projects, see [Add and manage comments in projects](/help/analysis-workspace/build-workspace-project/comment-projects.md).</p> 

-->

### Preferencias de proyectos y análisis {#project-and-analysis-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Paleta categórica"
>abstract="Se aplica a numerosas visualizaciones de Analysis Workspace y análisis guiado. Cada color representa un valor categórico distinto."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Paleta divergente"
>abstract="Se aplica a la tabla Cohorte de Analysis Workspace y análisis guiado por el crecimiento del usuario. Esta paleta tiene un significado numérico con dos extremos y una línea de base en el medio."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Paleta secuencial"
>abstract="Se aplica al análisis guiado por Tendencias de frecuencia (barra apilada). Esta paleta tiene un significado numérico de claro a oscuro."

Puede personalizar estas preferencias para todos los nuevos proyectos de Analysis Workspace, nuevos paneles de Analysis Workspace y nuevos análisis guiados. Para obtener información sobre cómo acceder a estas preferencias, consulte [Actualizar preferencias](#update-preferences).

Algunas de estas mismas preferencias también se pueden personalizar para proyectos individuales, tal como se describe en la [Información general sobre proyectos](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

| Sección | Preferencia | Opciones |
| --- | --- | --- |
| **Mostrar** | | |
|  | [Ver densidad](/help/analysis-workspace/build-workspace-project/view-density.md) | Elige cuánto contenido se mostrará en la pantalla al reducir el margen vertical del carril izquierdo, las tablas de forma libre y las tablas de cohorte. <ul><li>Compacto</li><li>Cómodo</li><li>Expandido (predeterminado)</li></ul> |
| | [Paleta de color](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Elija las paletas de colores de visualización que se utilizan en Analysis Workspace y en análisis guiado. <ul><li> Paleta categórica: se aplica a muchas visualizaciones de Analysis Workspace y al análisis guiado. Cada color representa un valor categórico distinto. Elija entre las opciones que proporciona Adobe o introduzca una paleta personalizada definida por valores hexadecimales delimitados por comas.</li><li> Paleta divergente: se aplica a la tabla de cohortes en Analysis Workspace y al análisis guiado de crecimiento de usuarios. Esta paleta contiene un significado numérico con dos extremos y una línea de base en el medio.<li> Paleta secuencial: se aplica al análisis guiado de tendencias de frecuencia (barra apilada). Esta paleta contiene un significado numérico, de claro a oscuro.</li></ul> |
| **Datos** | | |
|  | [Vista de datos](/help/analysis-workspace/c-panels/panels.md#data-view) | Elige desde dónde las tablas y las visualizaciones obtienen sus datos. <ul><li>Más reciente (predeterminado)</li><li>Vista de datos específicos seleccionados de una lista</li></ul> |
|  | [Calendario](/help/analysis-workspace/c-panels/panels.md#calendar) | Seleccione de una lista de: <ul><li>Intervalos proporcionados por Adobe (el valor predeterminado es Este mes)</li><li>Hacer que, por defecto, [!UICONTROL los componentes del intervalo de fecha sean relativos al calendario del panel].</li></ul> |
|  | [Tipo de panel](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>Improvisado (predeterminado)</li><li>En blanco</li><li>Acceso rápido a información</li></ul> |
|  | Recuento de instancias | Habilitar [!UICONTROL Contar instancias repetidas] para especificar si se cuentan las instancias en los informes. Por ejemplo, cuando se habilita, varias vistas de página consecutivas a la misma página se tratan como varias vistas de página. Cuando está desactivado, varias vistas de página consecutivas a la misma página cuentan como una sola vista de página. <p>**Nota:** Esta configuración solo afecta a determinadas métricas (como Sesiones) y no se aplica a Flujo o Visualizaciones de flujo.</p> |
|  | Formato de número | <ul><li>1000,00 (predeterminado)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Carácter separador de CSV | <ul><li>Coma (predeterminado)</li><li>Punto y coma</li><li>Dos puntos</li><li>Barra vertical</li><li>Periodo</li><li>Espacio</li><li>Tabulación</li></ul> |
|  | Mostrar anotaciones | Elija si las anotaciones estarán visibles en los proyectos. Para obtener más información sobre las anotaciones, consulte la [Información general sobre anotaciones](/help/components/annotations/overview.md). |


### Preferencias de tabla de forma libre {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Mostrar anomalías"
>abstract="Al seleccionar **[!UICONTROL Mostras anomalías]** se ejecutará automáticamente la Detección de anomalías en la primera columna de métrica añadida a una tabla de forma libre de series temporales."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Mostrar previsión"
>abstract="Al seleccionar **[!UICONTROL Mostrar previsión]**, se ejecutará automáticamente la previsión en la primera columna de métrica añadida a una tabla de forma libre de series temporales."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Métrica predeterminada de la tabla"
>abstract="Seleccione la métrica predeterminada que se utilizará para las tablas de forma libre. Si la vista de datos seleccionada no contiene la métrica predeterminada seleccionada, la tabla cambia automáticamente a otra métrica principal."


Puede personalizar las preferencias de tabla de forma libre para todos los proyectos nuevos que cree en Analysis Workspace. Para obtener información sobre cómo acceder a estas preferencias, consulte [Actualizar preferencias](#update-preferences).

Algunas de estas mismas preferencias también se pueden personalizar para proyectos individuales.

Haga clic en los títulos de las secciones vinculadas para obtener más información y contexto sobre las preferencias disponibles.

| Sección | Preferencia | Opciones |
| --- | --- | --- |
| **Tabla** | | |
| | Tipo de tabla | <ul><li>De forma libre</li><li>Generador de tablas</li></ul> |
| | Métrica predeterminada de la tabla | <ul><li>Ocurrencias</li><li>Visitantes únicos</li><li>Visitas</li></ul> |
| | Dimensión predeterminada de tabla | Elija entre Minuto, Hora, Día, Semana, Mes, Trimestre o Año. |
| | Alinear fechas | Seleccione esta opción para alinear fechas de cada columna con todas a partir de la misma fila. |
| **[Columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Justificar el texto del encabezado | Permite justificar el texto del encabezado en las tablas de forma libre para que los encabezados sean más legibles y las tablas se puedan compartir con mayor facilidad. Esto resulta útil en el procesamiento de archivos .pdf y en las métricas con nombres largos. Está activada de forma predeterminada. |
| | Mostrar totales | Este número de totales suele ser igual o un subconjunto de [!UICONTROL Total general]. Refleja cualquier segmento de tabla aplicado en la tabla de forma libre, incluida la opción [!UICONTROL Incluir ninguno]. |
| | Mostrar totales generales | Este número total representa todos los eventos que se han recopilado, a veces denominados *total de vista de datos*. Cuando se aplica un segmento en el nivel de panel o en la tabla de forma libre, este total se ajusta para reflejar todos los eventos que coinciden con los criterios del segmento. El total general no es compatible con tablas o desgloses con [filas estáticas](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostrar minigráfico | Muestre u oculte gráficos de líneas en la parte inferior del gráfico. Cuando esté oculta, la leyenda cambiará para no hacer referencia visual a las líneas. |
| | Número | Determina si una celda muestra u oculta el valor numérico de la métrica. Por ejemplo, si la métrica es Visualizaciones de la página, el valor numérico es el número de visualizaciones de la página para el elemento de fila. |
| | Porcentaje | Determina si una celda muestra u oculta el valor porcentual de la métrica. Por ejemplo, si la métrica es vistas de página, el valor porcentual es el número de vistas de página para el elemento de fila dividido por el total de vistas de página para la columna.  Nota: Puede mostrar porcentajes superiores al 100% para mejorar la precisión. También puede mover el límite superior al 1000% para asegurarse de que las columnas pueden aumentar demasiado de anchura. |
| | Mostrar anomalías <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Determina si se ha ejecutado una detección de anomalías en los valores de esta columna. |
| | Mostrar previsión | Determina si los valores de previsión se muestran automáticamente para la primera columna de métrica en cualquier tabla de forma libre de series temporales que cree. |
| | La interpretación de cero no tiene valor | Para las celdas con un valor de 0, determina si se va a mostrar un 0 o una celda en blanco. Esto es útil si desea analizar los datos de todos los días de un mes y todavía faltan algunos días.  En vez de mostrar 0 para las fechas futuras, se pueden mostrar celdas en blanco. Los gráficos también respetan esta configuración (por ejemplo, los carros de compras no muestran una línea o barra con 0 valores cuando se activa esta configuración). |
| | Contexto | Determina si una celda muestra u oculta todo el formato de la celda, que incluye la gráfico de barras y el formato condicional <ul><li>Gráfico de barras</li> Muestra un gráfico de barras horizontal que representa el valor de la celda con relación al total de la columna. <li>Formato condicional</li>Para obtener más información sobre el formato condicional, consulte “Formato condicional” en [Configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Vista previa de celda | Muestra una vista previa del aspecto de cada una de las celdas con las opciones de formato seleccionadas actualmente aplicadas. |
| **[Fila](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Desglose por posición | Seleccione esta opción si desea que el desglose permanezca con la posición del elemento en lugar de con el propio elemento. Para obtener más información sobre los desgloses, consulte [Desglose de dimensiones](/help/components/dimensions/t-breakdown-fa.md). |
| | Cálculo de porcentajes | <ul><li>Columna</li><li>Fila</li></ul> |
| | Totales de columnas (solo filas estáticas) | <ul><li>Mostrar suma de filas: muestra la suma de los elementos de línea individuales </li><li>Mostrar el total general: muestra la suma de filas sin duplicar.</li></ul> |

### Preferencias de visualizaciones {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="Contenedor predeterminado"
>abstract="Seleccione el contenedor predeterminado que se utilizará para las visualizaciones del [!UICONTROL flujo]. Si la vista de datos seleccionada no contiene el contenedor predeterminado seleccionado, la visualización [!UICONTROL Flujo] cambiará automáticamente a otro contenedor principal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="Contenedor predeterminado"
>abstract="Seleccione el contenedor predeterminado que se utilizará para las visualizaciones de [!UICONTROL visitas en orden previsto]. Si la vista de datos seleccionada no contiene el contenedor predeterminado seleccionado, la visualización [!UICONTROL Visitas en el orden previsto] cambiará automáticamente a otro contenedor principal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="Método de recuento predeterminado"
>abstract="Seleccione el método de recuento predeterminado que se utilizará para las visualizaciones del [!UICONTROL Histograma]. Si la vista de datos seleccionada no contiene el método de contabilización predeterminado seleccionado, la visualización [!UICONTROL Histograma] cambiará automáticamente a otro método de contabilización principal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="Contenedor predeterminado"
>abstract="Seleccione el contenedor predeterminado que se utilizará para las visualizaciones del [!UICONTROL Lienzo del recorrido]. Si la vista de datos seleccionada no contiene el contenedor predeterminado seleccionado, la visualización [!UICONTROL lienzo de Recorrido] cambiará automáticamente a otro contenedor principal."


Puede actualizar las preferencias de visualización para todos los proyectos nuevos que cree en Analysis Workspace. Para obtener información sobre cómo acceder a estas preferencias, consulte [Actualizar preferencias](#update-preferences).

Algunas de estas mismas preferencias también se pueden personalizar para visualizaciones individuales.

Haga clic en los títulos de las secciones vinculadas para obtener más información y contexto sobre las preferencias disponibles.

| Sección | Preferencia | Opciones |
| --- | --- | --- |
| **Valores generales predeterminados** | | |
| | Porcentajes | Muestra valores en porcentajes para todas las visualizaciones. |
| | Leyenda visible | Permite ocultar el texto de leyenda detallado para todas las visualizaciones. |
| | Límite máximo de elementos | Reduce el número de elementos en el eje X para todas las visualizaciones. Esta preferencia puede resultar útil si tiene un conjunto de datos grande. |
| | Mostrar doble eje (cuando corresponda) | Solo es aplicable si cuenta con dos métricas: puede tener un eje Y a la izquierda (para una métrica) y a la derecha (para otra métrica). Esta preferencia es útil cuando las métricas trazadas son de magnitudes muy diferentes. |
| | Normalización (cuando corresponda) | Fuerza métricas para igualar proporciones. Esta preferencia es útil cuando las métricas trazadas son de magnitudes muy diferentes. |
| | Anclar el eje Y en cero | Si todos los valores marcados en el gráfico están considerablemente por encima de cero, el gráfico actualiza de forma predeterminada la parte inferior del eje Y a NO CERO. Si marca esta casilla, el eje Y se fuerza en cero (y vuelve a dibujar el gráfico). |
| | Anclar las anomalías a que escalen el eje Y | El eje Y se escala con valores de anomalía. |
| **[Líneas](/help/analysis-workspace/visualizations/line.md)** | | |
| | Porcentajes | Muestra valores en porcentajes para las visualizaciones de Línea. |
| | Leyenda visible | Permite ocultar el texto de leyenda detallado para la visualización de línea. |
| | Límite máximo de elementos | Reduce el número de elementos en el eje X de la visualización de línea. Esta preferencia puede resultar útil si tiene un conjunto de datos grande. |
| | Mostrar doble eje (cuando corresponda) | Solo es aplicable si cuenta con dos métricas: puede tener un eje Y a la izquierda (para una métrica) y a la derecha (para otra métrica). Esta preferencia es útil cuando las métricas trazadas son de magnitudes muy diferentes. |
| | Normalización (cuando corresponda) | Fuerza métricas para igualar proporciones. Esta preferencia es útil cuando las métricas trazadas son de magnitudes muy diferentes. |
| | Mostrar el eje X | Muestra el eje X en el gráfico de líneas. |
| | Mostrar el eje Y | Muestra el eje Y en el gráfico de líneas. |
| | Anclar eje Y | Si todos los valores marcados en el gráfico están considerablemente por encima de cero, el gráfico muestra de forma predeterminada la parte inferior del eje Y distinta a cero. Si marca esta casilla, el eje Y se forzará a ser cero (y se redibujará el gráfico). |
| | Permitir que las anomalías escalen el eje Y | Si tiene varias métricas en un gráfico, debe pasar el ratón sobre cada anomalía para ver la banda de confianza de la métrica. Para que la visualización sea más legible, el intervalo de confianza de Detección de anomalías no escala automáticamente el eje Y. Esta configuración permite que el intervalo de confianza escale la visualización. <p>Para obtener más información, consulte [Visualización de anomalías en Analysis Workspace](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| | Deje que la previsión se ajuste al eje Y | Si tiene valores de previsión que están fuera de los límites superior e inferior de los valores históricos, el eje Y no escala automáticamente estos valores previstos. Cuando se activa, esta opción no escala correctamente el eje Y para los valores pronosticados. |
| | Mostrar mínimo | Superponga una etiqueta de valor mínimo para resaltar rápidamente los valores de una métrica. Nota: Los valores mínimos se derivan de los puntos de datos visibles en la visualización, no del conjunto completo de valores dentro de una dimensión. |
| | Mostrar máximo | superponga una etiqueta de valor máximo para resaltar rápidamente los picos de una métrica. Nota: Los valores máximos se derivan de los puntos de datos visibles en la visualización, no del conjunto completo de valores dentro de una dimensión. |
| | Mostrar línea de tendencia | Se muestra una línea de tendencia promedio móvil o una regresión en la serie de líneas. Las líneas de tendencia ayudan a mostrar un patrón más claro en los datos. |
| **[Cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | [!BADGE Contenedor de B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/> | Seleccione el contenedor preferido para el análisis de cohorte en el caso de una conexión [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} basada en la cuenta. <p>Las opciones disponibles son las siguientes:</p> <ul><li>Cuentas globales [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Cuentas [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Comprando grupos [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Oportunidades [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Persona</li></ul> |
| | Granularidad | En las visualizaciones de tendencias, puede cambiar la granularidad de tiempo (Día, Semana, Mes, Trimestre o Año). Este cambio también se aplica a la tabla de fuente de datos. |
| | Mostrar sólo porcentaje | Elimina el valor numérico y solo muestra el porcentaje. |
| | Redondear el porcentaje al entero más cercano | Redondea el valor porcentual al total más cercano en lugar de mostrar el valor decimal. |
| | Mostrar una fila porcentual promedio | Inserta una nueva fila en la parte superior de la tabla y, a continuación, agrega el promedio de los valores dentro de cada columna. |
| **[Gráficos combinados](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Mostrar el eje X | Muestra el eje X en el gráfico combinado. |
| | Mostrar el eje Y | Muestra el eje Y en el gráfico combinado. |
| | Mostrar puntos en las líneas | Muestra puntos en las líneas en los gráficos combinados. |
| **[Resumen de métricas clave](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | Tipo de visualización de resumen | <ul><li>Enfatizar el cambio porcentual</li><li>Enfatización del valor numérico</li></ul> |
| | Mostrar minigráficos | Se muestran u ocultan gráficos de líneas en la parte inferior del gráfico. Cuando esté oculta, la leyenda cambiará para no hacer referencia visual a las líneas. |
| | Mostrar máx. y mín. en los reflectores | Se muestran valores mínimos y máximos en gráficos de líneas principales y de comparación. |
| | Mostrar comparación | Se muestran datos de comparación. Cuando están ocultos, el gráfico de líneas de comparación y los objetos de cambio de resumen no se ven. |
| | Opciones de valor numérico | En la sección [!UICONTROL **Resumen de métricas clave**] <ul><li>Mostrar cambio de porcentaje</li><li>Mostrar diferencia en bruto</li>Diferencia en bruto entre el valor total de la métrica en el intervalo de fechas principal y el secundario</ul> |
| **[Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Contenedor | Seleccione el contenedor preferido para analizar las rutas. El contenedor preferido le ayuda a comprender la participación de la cuenta en varios niveles de contenedor B2B [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, la participación de la persona en el nivel de persona (entre sesiones) o a restringir el análisis a una sola sesión. <p>Las opciones disponibles son las siguientes:</p> <ul><li>Cuentas globales [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Cuentas [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Comprando grupos [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Oportunidades [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Sesión</li><li>Persona</li></ul> |
| **[Flujo](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contenedor | Seleccione el contenedor preferido para analizar. El contenedor preferido le ayuda a comprender la participación de la cuenta en varios niveles de contenedor B2B [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, la participación de la persona en el nivel de persona (entre sesiones) o a restringir el análisis a una sola sesión. <p>Las opciones disponibles son las siguientes:</p> <ul><li>Cuentas globales [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Cuentas [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Comprando grupos [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Oportunidades [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Sesión</li><li>Persona</li></ul> |
| | Etiquetas de ajustes | Normalmente, las etiquetas de los elementos de flujo se truncan para ahorrar espacio en la pantalla, pero puede hacer la etiqueta entera visible al marcar esta casilla. Valor predeterminado = sin marcar. |
| | Incluir instancias de repetición | Las visualizaciones de flujo se basan en instancias de una dimensión. Esta configuración le da la opción de incluir o excluir instancias repetidas, por ejemplo, recargas de página. Sin embargo, las repeticiones no se pueden eliminar de las visualizaciones de flujo que incluyen dimensiones multivalor, como listVars, listProps, s.product, eVars de comercialización, etc. Valor predeterminado = sin marcar. |
| | Mostrar información sobre herramientas | Determina si se muestra la información de objeto, que contiene datos de nodo, al pasar el ratón por encima de nodos individuales dentro de una visualización de flujo. |
| | Número de columnas | Determina cuántas columnas desea incluir en el diagrama de flujo. |
| | Elementos expandidos por columna | Cuántos elementos desea incluir en cada columna. |
| **[Lienzo de recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)** | | |
| | Contenedor | Seleccione el contenedor preferido para analizar las rutas. El contenedor preferido le ayuda a comprender la participación de la cuenta en varios niveles de contenedor B2B [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, la participación de la persona en el nivel de persona (entre sesiones) o a restringir el análisis a una sola sesión. <p>Las opciones disponibles son las siguientes:</p> <ul><li>Cuentas globales [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Cuentas [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Comprando grupos [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Oportunidades [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>Sesión</li><li>Persona</li></ul> |
| **Gráficos apilados** | | |
| | Apilada al 100 % | Esta configuración en las visualizaciones de áreas apiladas, barras apiladas o barras horizontales apiladas convierte el gráfico en una visualización “apilada al 100 %”. <p>Para obtener más información, consulte [Barra y barra apilada](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Histograma](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Número de contenedores | Elija el número de intervalos de fechas (contenedores) en la visualización. El número máximo de contenedores es 50. <p>Para obtener más información, consulte [Histograma](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Método de recuento | Elija entre las siguientes opciones: <ul><li>Visita individual</li><li>Sesión</li><li>Persona</li></ul> <p>Por ejemplo, cuando se utiliza con vistas de página, puede elegir vistas de página por persona, vistas de página por visita o vistas de página por evento. Para visitas, se utiliza “Ocurrencias” como métrica del eje y en una tabla de forma libre.</p> |
| **[Cambio de resumen](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valor | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Cambio porcentual</li><li>Diferencia en bruto</li></ul> |
| | Porcentajes | Muestra valores en porcentajes para las visualizaciones de Cambio de resumen. |
| | Leyenda visible | Permite ocultar el texto de leyenda detallado para la visualización de Cambio de resumen. |
| **[Número de resumen](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Porcentajes | Muestra valores en porcentajes para las visualizaciones de Número de resumen. |
| | Leyenda visible | Permite ocultar el texto de leyenda detallado para la visualización de Número de resumen. |
| | Valor de resumen por | Elija entre Máx., Mín., Promedio, Mediana y Suma. |
| | Valor abreviado | En la sección **[!UICONTROL Número de resumen]** |
| **[Gráfico de rectángulos](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | Porcentajes | Muestra valores en porcentajes para las visualizaciones de Gráfico de rectángulos. |
| | Límite máximo de elementos | Reduce el número de elementos en el eje X de la visualización del Gráfico de rectángulos. Esta preferencia puede resultar útil si tiene un conjunto de datos grande. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Leyenda visible | Permite ocultar el texto de leyenda detallado para la visualización de Venn. |
| **[Dispersión](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Porcentajes | Muestra valores en porcentajes para las visualizaciones de Dispersión. |
| | Leyenda visible | Permite ocultar el texto de leyenda detallado para la visualización de Dispersión. |
| | Límite máximo de elementos | Reduce el número de elementos en el eje X en la visualización de Dispersión.  Esta preferencia puede resultar útil si tiene un conjunto de datos grande. |
| | Anclar el eje Y en cero | Si todos los valores marcados en el gráfico están considerablemente por encima de cero, el gráfico muestra de forma predeterminada la parte inferior del eje Y distinta a cero. Si marca esta casilla, el eje Y se fuerza en cero (y vuelve a dibujar el gráfico). |

## Restaurar preferencias predeterminadas

Puede restaurar todas sus preferencias de usuario a los valores predeterminados del sistema. Esta preferencia no afecta a las preferencias del administrador en la ficha Compañía.

No se puede deshacer esta acción.

1. En Customer Journey Analytics, selecciona [!UICONTROL **Componentes**] **>** [!UICONTROL **Preferencias**] del menú superior. O bien, seleccione **[!UICONTROL Proyecto]** > **[!UICONTROL Configuración de usuario]** en el menú Workspace.

1. En la esquina superior derecha, seleccione **[!UICONTROL Restaurar valores predeterminados]**.

1. Seleccione **[!UICONTROL Restaurar valores predeterminados]** en **[!UICONTROL Restaurar la configuración predeterminada del sistema]**.

## [!UICONTROL Tema oscuro]

Si prefiere tener un fondo oscuro para la interfaz de usuario de Customer Journey Analytics, puede alternarla al [!UICONTROL Tema oscuro].

1. Haga clic en el icono de usuario de Experience Cloud en la parte superior derecha.

   ![dark-theme](assets/dark-theme.png)

1. Habilitar **[!UICONTROL tema oscuro]**.

