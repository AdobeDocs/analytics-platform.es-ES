---
source-git-commit: a6f543d3b6aab06593d9fa40a5d3d6bbf4aa7c32
workflow-type: tm+mt
source-wordcount: '3977'
ht-degree: 32%

---
# Fragmentos

## Prueba limitada de fase de lanzamiento {#release-limited-testing}

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información acerca del proceso de lanzamiento de Customer Journey Analytics, consulte [lanzamientos de características de Customer Journey Analytics](/help/release-notes/releases.md).

## Sección de prueba limitada de fase de lanzamiento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información acerca del proceso de lanzamiento de Customer Journey Analytics, consulte [lanzamientos de características de Customer Journey Analytics](/help/release-notes/releases.md).

## Seleccionar paquete {#select-package}

>[!NOTE]
>
>Debe tener el paquete **Select** o superior para poder usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

## Paquete Prime {#prime-package}

>[!NOTE]
>
>Debe tener el paquete **Prime** o superior para poder usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

## Paquete Ultimate {#ultimate-package}

>[!NOTE]
>
>Debe tener el paquete **Ultimate** para poder usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.


## Criterios de filtro del diccionario de datos {#dd-filter-criteria}

1. (Opcional) Seleccione el icono **Filtrar** ![del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) y, a continuación, cualquiera de las siguientes opciones para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Filtros**] | Mostrar solo los componentes que son filtros. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Falta la descripción**] | Mostrar solo los componentes que aún no tienen descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Mostrar duplicados**] | Mostrar solo los componentes que tienen el mismo nombre o la misma descripción que otro componente en la vista de datos seleccionada. Esto incluye tanto los componentes que crea como los que proporciona Adobe. Los nombres o las descripciones deben coincidir de forma exacta para mostrarlos como duplicados. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No hay datos recientes**] | Mostrar solo los componentes que no han recopilado ningún dato en los últimos 90 días. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Creado por el Adobe**] <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

   {style="table-layout:auto"}

## Información del componente del diccionario de datos {#dd-component-information}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Aprobado**] | <p>Indica que el administrador revisó y aprobó el componente.</p><p>Los administradores ven una opción para [!UICONTROL **Desaprobar**]. Al seleccionar esta opción, se marca el componente como &quot;No aprobado&quot; para los usuarios.</p> |
| [!UICONTROL **No aprobado**] | <p>Indica que el administrador aún no ha revisado y aprobado el componente.</p><p>Los administradores ven la opción para [!UICONTROL **Aprobar**]. Al seleccionar esta opción, el componente se marca como “Aprobado” para los usuarios.</p> |
| [!UICONTROL **Descripción**] | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/components/add-component-descriptions.md)). |
| [!UICONTROL **Usado frecuentemente con**] | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección al seleccionar los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique el filtro **Mostrar todo** para asegurarse de que ve los componentes que no se han compartido con usted y que otro administrador podría haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similar a**] | <p>Muestra componentes con nombres similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí se mostrará cualquier componente duplicado de la vista de datos. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique el filtro **Mostrar todo** para asegurarse de que ve los componentes que no se han compartido con usted y que otro administrador podría haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Nota:** Actualmente, la sección **Similar a** incluye solo los componentes que crea y no los proporcionados por Adobe. En una versión futura se agregarán componentes proporcionados por Adobe.</p> |
| [!UICONTROL **Compatibilidad del producto**] | Indica en qué Customer Journey Analytics se puede utilizar esta métrica calculada. <p>Los valores posibles son:</p><ul><li>[!UICONTROL **En cualquier lugar del Customer Journey Analytics**]: la métrica calculada se puede usar en todos los Customer Journey Analytics, incluso en Analysis Workspace, Report Builder, etc.</li><li>[!UICONTROL **En cualquier lugar del Customer Journey Analytics (excluida la experimentación)**]: la métrica calculada se puede usar en todo el Customer Journey Analytics, excepto en el panel Experimentación.</li> <p>Para obtener información acerca de los criterios que determinan si se puede usar una métrica calculada con experimentación, consulte [Usar métricas calculadas en el panel Experimentación](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) en [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Etiquetas**] | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
| [!UICONTROL **Tipo de componente**] | Muestra el tipo de componente que es, ya sea un Dimension, una métrica, un filtro o un intervalo de fechas. |
| [!UICONTROL **Creado por**] | Muestra el nombre del usuario que ha creado el componente. |
| [!UICONTROL **Vista previa**] | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
| [!UICONTROL **Fecha de la última modificación**] | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver filtros, métricas, métricas calculadas e intervalos de fechas. |

{style="table-layout:auto"}

## Opciones de ordenación de componentes {#components-sort-options}

| Opción | Función |
|---------|----------|
| **[!UICONTROL Recomendado]** | Ordene los componentes de cada tipo (dimensión, métrica, filtro e intervalo de fechas) en función de su recomendación. Los componentes que utiliza con mayor frecuencia y más recientemente usted o otras personas de su organización aparecen en una posición superior en cada lista. |
| **[!UICONTROL Última modificación]** | Ordene los componentes de cada tipo (dimensión, métrica, filtro e intervalo de fechas) en función de la última fecha de modificación. Los componentes modificados más recientemente se muestran más arriba en cada lista. |
| **[!UICONTROL Alfabético]** | Ordene los componentes de cada tipo (dimensión, métrica, filtro e intervalo de fechas) en orden alfabético ascendente. |
| **[!UICONTROL Categórica]** | Ordene los componentes de cada tipo (dimensión, métrica, filtro e intervalo de fechas) según su categoría. Por ejemplo, componentes de vista de datos depurados frente a no depurados. |

{style="table-layout:auto"}

## Comparación del tiempo {#apply-time-comparison}

Puede comparar el período de tiempo actual con un período de tiempo anterior. Si selecciona una opción en este menú, cada punto de datos recibe un homólogo con líneas punteadas de color similar. Este homólogo representa la misma métrica en el intervalo de fechas anterior seleccionado. Al establecer esta opción, se duplica el número de elementos del gráfico y de las filas de la tabla.

Las opciones de comparación de tiempo disponibles incluyen el periodo anterior, 13 semanas antes, 52 semanas antes y un intervalo de fechas personalizado. Si selecciona Intervalo de fechas personalizado, aparecen opciones adicionales para permitirle seleccionar el número y la granularidad. Si selecciona Ninguno, se elimina la comparación de fechas.


## Vídeo de demostración de Adobe Analytics {#videoaa}

Este vídeo muestra la funcionalidad mediante Adobe Analytics. Sin embargo, la funcionalidad también está disponible en Customer Journey Analytics. Tenga en cuenta las siguientes diferencias terminológicas.

| Adobe Analytics | Customer Journey Analytics |
|:---:|:---:|
| Segmentos  | Filtros |
| Visitante | Persona |
| Visita | Sesión |
| Visita individual | Evento |


## Panel Filtros {#filterspanel}

1. Seleccione ![Filtro](/help/assets/icons/Filter.svg) para abrir el panel Filtros. Si necesita más espacio para la lista Filtros, puede seleccionar ![Filtro](/help/assets/icons/Filter.svg) una vez más para cerrar el panel.
1. Seleccione filtros de cualquiera de las secciones de filtros disponibles.


## Sección de filtro de etiquetas {#tagfiltersection}

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/assets/filter-tag.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Puede ![Buscar](/help/assets/icons/Search.svg) *Buscar etiquetas* para buscar etiquetas que pueda usar para filtrar.</li><li>Puede seleccionar más de una etiqueta. Las etiquetas disponibles dependen de las selecciones realizadas en otras secciones del panel de filtro.</li><li>Los números indican:<ul><li>**(1)**: El número de etiquetas seleccionadas (si se seleccionan una o más).</li><li>**2︎⃣**: número de etiquetas disponibles para los elementos resultantes del filtro actual.</li><li>7︎⃣: el número de elementos asociados con la etiqueta específica.</li></ul></li></ul> |


## Sección Filtro de vista de datos {#dataviewfiltersection}

| Vista de datos | Descripción |
|---|---|
| ![Vistas de datos](/help/assets/filter-dataview.png){width="300"} | La sección **[!UICONTROL Vista de datos]** le permite filtrar las vistas de datos. <ul><li>Puede ![Buscar](/help/assets/icons/Search.svg) *Buscar vistas de datos* para buscar vistas de datos que pueda usar para filtrar.</li><li>Puede seleccionar varias vistas de datos. Las vistas de datos disponibles dependen de las selecciones realizadas en otras secciones del panel de filtro.</li><li>Los números indican:<ul><li>**(2)**: El número de vistas de datos seleccionadas (si se seleccionan una o más vistas de datos).</li><li>**3︎⃣**: El número de vistas de datos disponibles para los elementos resultantes del filtro actual.</li><li>4︎⃣: el número de elementos asociados con la vista de datos específica.</li></ul></li></ul> |

## Sección de filtro de estado habilitado {#enabledstatusfiltersection}

| Estado habilitado | Descripción |
|---|---|
| ![Estado habilitado](/help/assets/filter-enabledstatus.png){width="300"} | La sección **[!UICONTROL Estado habilitado]** le permite filtrar por estado habilitado. <ul><li>Puede seleccionar más de un estado.</li><li>Los números indican:<ul><li>**(2)**: El número de estados seleccionados (si se seleccionan uno o más estados).</li><li>**2︎⃣**: El número de estados disponibles para los elementos resultantes del filtro actual.</li><li>1︎⃣: el número de elementos asociados con el estado específico.</li></ul></li></ul> |

## Escriba la sección de filtro {#typefiltersection}

| Tipo | Descripción |
|---|---|
| ![Tipo](/help/assets/filter-type.png){width="300"} | La sección **[!UICONTROL Type]** le permite filtrar por tipo. <ul><li>Puede seleccionar más de un tipo.</li><li>Los números indican:<ul><li>**(2)**: El número de tipos seleccionados (si se seleccionan uno o más tipos).</li><li>**1︎⃣**: número de tipos disponibles para los elementos resultantes del filtro actual.</li><li>3︎⃣: el número de elementos asociados con el tipo específico.</li></ul></li></ul> |

## Sección de filtro de propietario {#ownerfiltersection}

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/assets/filter-owners.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por propietarios. <ul><li>Puede ![Buscar](/help/assets/icons/Search.svg) *Buscar propietarios* para buscar los propietarios que pueda usar para filtrar.</li><li>Puede seleccionar más de un propietario. Los propietarios disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican:<ul><li>**(2)**: El número de propietarios seleccionados (si se seleccionan uno o más propietarios).</li><li>**3︎⃣**: El número de propietarios disponibles para los elementos resultantes del filtro actual.</li><li>4︎⃣: número de elementos asociados con el propietario específico.</li></ul></li></ul> |

## Otros filtros, sección de filtro {#otherfiltersfiltersection}

| Otros filtros | Descripción |
|---|---|
| ![Otros filtros](/help/assets/filter-other.png){width="300"} | La sección **[!UICONTROL Otros filtros]** le permite filtrar otros filtros predefinidos.<ul><li>Puede seleccionar una o varias de las siguientes opciones:<ul><li> **[!UICONTROL Mostrar todo]**</li><li>**[!UICONTROL Compartido conmigo]**</li><li>**[!UICONTROL Mío]**</li><li>**[!UICONTROL Aprobado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> Lo que puede seleccionar depende de la función y los permisos.</li><li>Puede seleccionar más de un filtro. Los demás filtros disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican:<ul><li>**(1)**: El número de otros filtros seleccionados (si se seleccionan uno o más filtros).</li><li>**5︎⃣**: El número de otros filtros disponibles para los elementos resultantes del filtro actual.</li><li>4︎⃣: el número de elementos asociados con el otro filtro específico.</li></ul></li></ul> |

## Sección de filtro de intervalo de fechas  {#daterangefiltersection}

| Intervalo de fecha aplicado | Descripción |
|---|---|
| ![Intervalo de fecha](/help/assets/filter-daterange.png){width="300"} | La sección Intervalo de fechas aplicado permite filtrar un intervalo de fechas aplicable a los elementos.<ol><li>Seleccione un intervalo de fecha.</li><li>En la ventana emergente del calendario, defina un intervalo de fechas o seleccione uno de los ajustes preestablecidos disponibles.<br>Como alternativa, también puede especificar un intervalo de fechas directamente en la sección Intervalo de fechas del panel Filtro.</li></ol><ul><li>Los números indican:<ul><li>**(1)**: El número de intervalos de fechas modificados a partir de los ajustes preestablecidos predeterminados.</li><li>**5︎⃣**: El número de intervalos de fechas disponibles para los elementos resultantes del filtro actual.</li></ul> |


## Modelos de atribución {#attribution-models-details}

Un modelo de atribución determina qué elementos de dimensión obtienen crédito por una métrica cuando se ven varios valores dentro de la ventana retrospectiva de una métrica. Los modelos de atribución solo se aplican cuando hay varios elementos de dimensión establecidos dentro de la ventana retrospectiva. Si solo se establece un elemento de dimensión, ese elemento de dimensión obtiene un 100% de crédito, independientemente del modelo de atribución utilizado.

| Icono | Modelo de atribución | Definición |
| :---: | :--- | --- |
| ![Último contacto](/help/assets/icons/AttributeLastTouch.svg) | Último contacto | Otorga un 100% de crédito al punto de contacto que se produce más recientemente antes de la conversión. Este modelo de atribución suele ser el valor predeterminado para cualquier métrica en la que no se especifique lo contrario en un modelo de atribución. Las organizaciones suelen utilizar este modelo en el que el tiempo de conversión es relativamente corto, como con el análisis de palabras clave de búsqueda interna. |
| ![Primer contacto](/help/assets/icons/AttributeFirstTouch.svg) | Primer contacto | Otorga un 100% de crédito al punto de contacto que se ve por primera vez dentro de la ventana retrospectiva de atribución. Las organizaciones suelen utilizar este modelo para comprender la imagen de marca o la adquisición de clientes. |
| ![Lineal](/help/assets/icons/AttributeLinear.svg) | Lineal | Otorga el mismo crédito a cada punto de contacto que se visualice y que conduzca a una conversión. Resulta útil cuando los ciclos de conversión son más largos o requieren una participación del cliente más frecuente. Las organizaciones suelen utilizar este modelo de atribución para medir la efectividad de las notificaciones de aplicaciones móviles o con productos por suscripción. |
| ![Participación](/help/assets/icons/AttributeParticipation.svg) | Participación | Otorga un 100% de crédito a todos los puntos de contacto únicos. Dado que cada punto de contacto recibe un 100 % de crédito, los datos de métricas suelen sumar más del 100 %. Si un elemento de dimensión aparece varias veces separadas y conduce a una conversión, los valores se deduplican al 100%. Este modelo de atribución es ideal en situaciones en las que desea comprender a qué puntos de contacto se exponen más los clientes. Los medios suelen utilizar este modelo para calcular la velocidad de contenido. Las organizaciones comerciales suelen utilizar este modelo para comprender qué partes de su sitio son esenciales para la conversión. |
| ![Mismo contacto](/help/assets/icons/AttributeSameTouch.svg) | Mismo contacto | Otorga un 100% de crédito al mismo evento en el que se produjo la conversión. Si un punto de contacto no se produce en el mismo evento que una conversión, se agrupa en &quot;Ninguno&quot;. Este modelo de atribución a veces se equipara a no tener ningún modelo de atribución. Resulta útil en escenarios en los que no desea valores de otros eventos que afecten a cómo una métrica da crédito a los elementos de dimensión. Los equipos de producto o diseño pueden utilizar este modelo para evaluar la eficacia de una página en la que se produce la conversión. |
| ![Forma de U](/help/assets/icons/AttributeUShaped.svg) | En forma de U | Otorga un 40% de crédito a la primera interacción, un 40% de crédito a la última interacción y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 50% de crédito a ambos. Este modelo de atribución se utiliza mejor en escenarios donde se valora más la primera y la última interacción, pero no se desea descartar por completo las interacciones adicionales intermedias. |
| ![Curva J](/help/assets/icons/AttributeJCurve.svg) | Curva J | Otorga un 60% de crédito a la última interacción, un 20% de crédito a la primera interacción y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 75% de crédito a la última interacción y un 25% de crédito a la primera. Similar a la Forma de U, este modelo de atribución favorece la primera y la última interacción, pero favorece más intensamente la última interacción. |
| ![J inversa](/help/assets/icons/AttributeInverseJ.svg) | J inversa | Otorga un 60% de crédito al primer contacto, un 20% al último contacto y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 75% de crédito a la primera interacción y un 25% de crédito a la última. Similar a la Forma de J, este modelo de atribución favorece la primera y la última interacción, pero favorece más intensamente la primera interacción. |
| ![Deterioro de tiempo](/help/assets/icons/AttributeTimeDecay.svg) | Deterioro de tiempo | Sigue un declive exponencial con un parámetro de semivida personalizado, con un valor predeterminado de 7 días. El valor de cada canal depende de la cantidad de tiempo que transcurra entre el inicio del punto de contacto y la conversión final. La fórmula utilizada para determinar el crédito es `2^(-t/halflife)`, donde `t` es la cantidad de tiempo entre un punto de contacto y una conversión. A continuación, todos los puntos de contacto se normalizan al 100%. Ideal para escenarios en los que desea medir la atribución con un evento específico e importante. Cuanto más tardía sea la conversión después de este evento, menor será el crédito. |
| ![Personalizado](/help/assets/icons/AttributeCustom.svg) | Personalizado | Permite especificar los pesos que desea dar al primer punto de contacto, al último punto de contacto y a cualquier punto de contacto intermedio. Los valores especificados se normalizan al 100% incluso si los números introducidos no suman 100. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. En el caso de interacciones con dos puntos de contacto, se omite el parámetro central. Los puntos de primer y último contacto se normalizan al 100% y el crédito se asigna en consecuencia. Este modelo es ideal para los analistas que desean un control total sobre su modelo de atribución y tienen necesidades específicas que otros modelos de atribución no satisfacen. |
| ![Algorítmico](/help/assets/icons/AttributeAlgorithmic.svg) | Algorítmico | Utiliza técnicas estadísticas para determinar dinámicamente la asignación óptima de crédito para la métrica seleccionada. El algoritmo utilizado para la atribución se basa en el dividendo de Harsanyi de la teoría de juegos cooperativa. El dividendo de Harsanyi es una generalización de la solución del valor de Shapley (llamada así por Lloyd Shapley, economista ganador del Premio Nobel) para distribuir crédito entre los jugadores en un juego con contribuciones desiguales al resultado.<br>En un nivel superior, la atribución se calcula como una coalición de actores a los que debe distribuirse equitativamente un excedente. La distribución del superávit de cada coalición se determina de acuerdo con el superávit creado previamente por cada subcoalición (o los elementos de dimensión que participaban antes) de manera recursiva. Para obtener más información, vea los artículos originales de John Harsanyi y Lloyd Shapley: <br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). Un modelo de negociación simplificado para un juego cooperativo de n personas. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Ventana retrospectiva de atribución {#attribution-lookback-window}

Una ventana retrospectiva es la cantidad de tiempo que una conversión debe devolverse en el tiempo para incluir los puntos de contacto. Si se establece un elemento de dimensión fuera de la ventana retrospectiva, el valor no se incluye en ningún cálculo de atribución.

* **14 días**: Busca hasta 14 días después de que se produjo la conversión.
* **30 días**: Busca hasta 30 días después de que se produjo la conversión.
* **60 días**: Busca hasta 60 días después de que se produjo la conversión.
* **90 días**: Busca hasta 90 días después de que se produjo la conversión.
* **Sesión**: Busca hasta el principio de la sesión en la que se produjo una conversión. Las ventanas retrospectivas de sesión respetan el [tiempo de espera de sesión](/help/data-views/create-dataview.md#session-settings) modificado en una vista de datos.
* **Persona (ventana de informes)**: Busca todas las visitas hasta el primer día del mes del intervalo de fechas actual. Por ejemplo, si el intervalo de fechas del informe es del 15 de septiembre al 30 de septiembre, el intervalo de fechas de retrospectiva de personas sería del 1 de septiembre al 30 de septiembre. Si utiliza esta ventana retrospectiva, puede ver ocasionalmente que los elementos de dimensión se atribuyen a fechas fuera de la ventana de creación de informes.
* **Tiempo personalizado:** le permite establecer una ventana retrospectiva personalizada desde el momento en que se produjo una conversión. Puede especificar el número de minutos, horas, días, semanas, meses o trimestres. Por ejemplo, si se produce una conversión el 20 de febrero, una ventana retrospectiva de cinco días evaluaría todos los puntos de contacto de la dimensión del 15 de febrero al 20 de febrero en el modelo de atribución.

## Ejemplo de atribución {#attribution-example}

Consideremos el siguiente ejemplo:

1. El 15 de septiembre, una persona llega a su sitio a través de un anuncio de búsqueda de pago y luego lo abandona.
1. El 18 de septiembre, la persona regresa a su sitio a través de un vínculo de medios sociales que obtuvo de un amigo. Agregan varios artículos al carro, pero no compran nada.
1. El 24 de septiembre, su equipo de marketing les enviará un correo electrónico con un cupón para algunos de los artículos del carrito. Aplican el cupón, pero visitan otros sitios para ver si hay otros cupones disponibles. Encontraron otro a través de un anuncio y finalmente hicieron una compra por valor de 50 dólares.

Según la ventana retrospectiva y el modelo de atribución, los canales reciben crédito diferente. A continuación se muestran algunos ejemplos:

* Con **primer contacto** y una **ventana retrospectiva de sesión**, la atribución solo se fijará en la tercera visita. Entre el correo electrónico y la visualización, el correo electrónico fue el primero, por lo que el correo electrónico recibe un 100% de crédito por la compra de 50 dólares.

* Con **primer contacto** y una **ventana retrospectiva de persona**, la atribución se fijará en las tres visitas. La búsqueda de pago fue la primera, así que recibe un 100% de crédito por la compra de 50 dólares.

* Con **linear** y una ventana retrospectiva de **sesión**, el crédito se divide entre el correo electrónico y la visualización. Cada uno de estos canales recibe un crédito de 25 dólares.
Con **linear** y una **ventana retrospectiva de persona**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Cada canal recibe un crédito de 12,50 dólares por esta compra.

* Con **J-shape** y una **ventana retrospectiva de persona**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización.

   * Se otorga un crédito del 60 % a la visualización, es decir, 30 dólares.
   * El 20 % de crédito se asigna a la búsqueda de pago, 10 dólares en este caso.
   * El 20% restante se divide entre el medio social y el correo electrónico, lo que otorga 5 dólares a cada uno.

* Con **Deterioro de tiempo** y una **ventana retrospectiva de persona**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Con la semivida de 7 días predeterminada:

   * Diferencia de cero días entre el punto de contacto de visualización y la conversión. `2^(-0/7) = 1`
   * Diferencia de cero días entre el punto de contacto del correo electrónico y la conversión. `2^(-0/7) = 1`
   * Diferencia de seis días entre el punto de contacto social y la conversión. `2^(-6/7) = 0.552`
   * Diferencia de nueve días entre el punto de contacto de búsqueda de pago y la conversión. `2^(-9/7) = 0.41`
   * La normalización de estos valores resulta en lo siguiente:

      * Visualización: 33,8 %, 16,88 dólares
      * Correo electrónico: 33,8 % 16,88 dólares
      * Medio social: 18,6 %, 9,32 dólares
      * Búsqueda de pago: 13,8 %, 6,92 dólares

Los eventos de conversión que generalmente tienen números enteros se dividen si el crédito pertenece a más de un canal. Por ejemplo, si dos canales contribuyen a un pedido mediante un modelo de atribución lineal, ambos canales obtienen 0,5 de ese pedido. Estas métricas parciales se suman en todas las personas y luego se redondean al entero más cercano para los informes.

## Comparaciones de visualización de recorrido {#journey-visualization-comparisons}

Varias visualizaciones en Customer Recorrido Analytics están diseñadas para analizar los recorridos que proporciona a sus clientes.

Utilice la siguiente información para elegir la visualización que mejor se adapte a sus necesidades.

| Función | Lienzo de recorrido | Visita en orden previsto | Flujo |
|---------|----------|---------|---------|
| **Secuencia predefinida de páginas** | Sí</br>Combina análisis exploratorios y predefinidos. La ruta final se utiliza cuando se utilizan nodos predefinidos en la ruta (los visitantes se cuentan siempre y cuando pasen de un nodo predefinido al otro). También se pueden mostrar los siguientes nodos inmediatos (no posibles). | Sí</br>La ruta puede ser una ruta final o puede restringirse al siguiente punto de contacto | No |
| **Secuencia exploratoria de páginas (Ad Hoc Analysis)** | Sí</br>Combina análisis exploratorios y predefinidos. La ruta final se utiliza cuando se utilizan nodos predefinidos en la ruta (los visitantes se cuentan siempre y cuando pasen de un nodo predefinido al otro). También se pueden mostrar los siguientes nodos inmediatos (no posibles). | Limitado</br>Permite hacer clic con el botón secundario y ver los abandonos inmediatos en una tabla de forma libre. | Sí</br>Sólo análisis exploratorio. Siempre dentro de una instancia de dimensión entre nodos. Esto significa que cada nodo muestra el siguiente punto de contacto inmediato (no eventual) a lo largo de la ruta. |
| **Muestra dónde abandonaron las personas (abandonaron) y continuaron (abandonaron)** | Sí</br>Muestra recorridos predefinidos y exploratorios | Sí</br>Muestra recorridos predefinidos | Sí</br>Muestra recorridos exploratorios |
| **recorridos lineales** | Sí | Sí | No |
| **recorridos no lineales con múltiples puntos de entrada y rutas** | Sí | No | Sí |
| **Métrica principal** | Cualquier métrica, incluidas las métricas calculadas | Solo sesión o persona | Solo ocurrencias (vistas de ruta) |
| **Métrica secundaria** | Sí<p>Cualquier métrica, incluidas las métricas calculadas</p> | No | No |
| **Compatibilidad con componentes en nodos o puntos de contacto** | Métricas, elementos de dimensión, filtros e intervalos de fechas. | Métricas, elementos de dimensión, filtros e intervalos de fechas. | Solo elementos de dimensión (excepto el punto de contacto inicial y final) |
| **Comparar filtros** | No | Sí<p>Realice comparaciones paralelas de dos filtros distintos en el mismo informe</p> | No |
| **Interacción de arrastrar y soltar** | Sí | Sí | No |
| **recorridos Adobe Journey Optimizer** | Sí</br>Abrir recorridos de Journey Optimizer para un análisis y una personalización más profundos | No | No |

{style="table-layout:auto"}
