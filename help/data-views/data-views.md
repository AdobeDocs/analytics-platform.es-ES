---
title: ¿Qué es una vista de datos en Customer Journey Analytics?
description: Una vista de datos especifica cómo desea interpretar los elementos de los datos de la conexión CJA, como métricas, dimensiones, sesiones, etc.
translation-type: tm+mt
source-git-commit: c1f5048e33d52a71db9811c22f49c237ac583817
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 4%

---


# ¿Qué es una vista de datos?

Una vista de datos se encuentra sobre un Customer Journey Analytics (CJA) [connection](/help/connections/create-connection.md). Una conexión combina uno o más conjuntos de datos de Adobe Experience Platform y los conecta a CJA. La vista de datos especifica cómo desea interpretar los elementos de los datos de la conexión, como métricas, dimensiones, sesiones, etc. Las vistas de datos se definen a fin de prepararse para la creación de informes de los datos en Workspace.

Si ya ha utilizado la versión tradicional de Adobe Analytics, una vista de datos es similar a un grupo de informes virtuales, ya que es una vista &quot;filtrada&quot; de los datos.

Puede crear distintas vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. También puede crear varias vistas de datos para un único conjunto de datos. Por ejemplo, podría tener una vista de datos en la que todas las dimensiones estén configuradas como [!UICONTROL Último toque] y, simultáneamente, otra vista de datos (basada en el mismo conjunto de datos) con todas las dimensiones definidas como [!UICONTROL Primer toque].

Los proyectos de Workspace en Customer Journey Analytics se basan en vistas de datos.

## ¿Qué novedades hay en las vistas de datos?

La última actualización de las vistas de datos le ofrece una mayor flexibilidad en lo que puede hacer con las vistas de datos. Estas mejoras le permiten **cambiar espontáneamente la configuración del elemento de esquema en las vistas de datos, sin tener que cambiar el esquema en Adobe Experience Platform ni volver a implementar el entorno de CJA**.

* **Puede cambiar un componente de una métrica a un Dimension y viceversa**. Puede crear métricas a partir de campos de cadena o dimensiones a partir de campos numéricos. Esto facilita las cosas, ya que no tiene que crear un campo numérico en el esquema XDM para cada métrica que desee. En su lugar, puede crearlo espontáneamente en el cuadro de diálogo de vistas de datos. Estos son algunos ejemplos:
   * **Cree una o varias dimensiones a partir de un único campo** de esquema. Es una relación uno a varios. Por ejemplo, puede crear una o más métricas de ingresos o una o más dimensiones de ingresos desde un único campo de esquema.
   * **Utilice un campo de cadena como métrica**: Al rellenar un esquema en Experience Platform con un conjunto de datos, es posible que no sepa por adelantado qué elementos de esquema necesita. Por ejemplo, es posible que no se haya dado cuenta de que necesitaba una métrica para &quot;Errores en una página&quot;. Como resultado, no se ha creado ningún elemento de esquema numérico a este efecto. Al utilizar un elemento de cadena como métrica, ahora puede utilizar la configuración de vistas de datos para especificar que, cada vez que una cadena contenga la palabra &quot;error&quot;, se pueda utilizar como métrica.
   * **Utilice un campo numérico como dimensión**: Por ejemplo, si desea extraer la métrica Ingresos de la dimensión Ingresos , la dimensión Ingresos mostraría cada valor como un elemento de dimensión ($100, $175, $1000, etc.) y el número de instancias para cada elemento de dimensión. Los ingresos como métrica se comportarían como siempre.

* **Puede crear varias métricas con diferentes modelos de atribución o con diferentes** ventanas retroactivas desde el mismo campo de esquema.

* **Puede editar el ID de un componente** ; se utiliza para la compatibilidad con vistas de datos cruzados. El ID de componente es lo que utiliza la API de informes para identificar una métrica o dimensión específica. Dado que puede crear arbitrariamente muchas métricas o dimensiones a partir de un campo XDM, le daremos la opción de definir su propio ID de componente. Como resultado, una métrica que utilice en un proyecto de Workspace puede ser compatible con todas las vistas de datos (y la API), incluso si se basan en campos totalmente diferentes de diferentes conexiones o vistas de datos o de un esquema diferente en XDM.

* **Puede especificar el nombre descriptivo del componente que aparecerá en Analysis Workspace**. De forma predeterminada, este nombre se hereda del nombre para mostrar del esquema, pero ahora puede sobrescribirlo para esta vista de datos específica. (Así también funciona la depuración de componentes en los grupos de informes virtuales en la versión tradicional de Adobe Analytics).

* **Puede ver más información relacionada con el esquema sobre los componentes** , como: de qué tipo de conjunto de datos (evento, perfil, búsqueda) procede; qué tipo de esquema (cadena, entero, etc.) procedía de; y su ruta de esquema (el campo XDM en el que se basa).

* **Puede etiquetar un** componente para que sea más fácil buscarlo en Workspace.

* **Puede ocultar un componente en los informes**. Algunas métricas y dimensiones de la configuración de DV2 requerían una segunda métrica o dimensión para su configuración (como la deduplicación de métricas o la deduplicación de compras, por ejemplo). Esto le permite definir una métrica o dimensión que se puede usar en la configuración de otra métrica o dimensión sin estar expuesta directamente en los informes (como el ID de compra).

* **Puede aplicar formato a una métrica** , como mostrar decimal, tiempo, porcentaje o moneda; especificación de lugares decimales; mostrar tendencia ascendente como verde o rojo; y especificar opciones de moneda.

* Puede **crear una métrica o dimensión basada únicamente en algunos de los valores del campo de esquema**. Por ejemplo, si desea una métrica de &quot;errores&quot;, puede crear una métrica a partir del campo del nombre de página, pero solo incluir páginas que contengan la palabra &quot;error&quot;. La métrica de errores creada a partir de esta acción es compatible con filtros, se puede insertar en métricas calculadas y funciona con atribución, flujo, visitas en el orden previsto, etc.

* Para las dimensiones, puede **incluir o excluir automáticamente solo determinados valores dentro de un campo específico**. Por ejemplo, si un desarrollador envía un valor incorrecto de `dev mistake` a un campo, puede excluirlo fácilmente de los informes mediante una regla de exclusión y se comportará como si nunca existiera en los datos.

* Puede **cambiar el nombre de los contenedores** en una vista de datos y hacer que esos contenedores renombrados aparezcan en cualquier proyecto de Workspace basado en esa vista de datos.

## Requisitos previos

* Para poder crear vistas de datos, debe [configurar una o más conexiones a conjuntos de datos de Experience Platform](/help/connections/create-connection.md).
* Para crear o administrar una vista de datos, necesita un [conjunto de permisos en Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es-ES#admin-access-permissions).

## Ver información sobre un componente

Haga clic en el icono de información (i) de Workspace para ver en qué campo de esquema se basa un componente y su configuración, como una descripción.

## Configuración de vista de datos que puede anular en Workspace

Algunos ajustes de la vista de datos se pueden sobrescribir en Analysis Workspace a nivel de proyecto, mientras que otros no.

* Ventana retroactiva
* Atribución de métricas
* Indica si los usuarios ven o no el elemento de línea &quot;Sin valor&quot; en un informe

## Configuración de vista de datos que no se puede anular en Workspace

* Tipo de componente
* Formato de métrica
* Nombre de la vista de datos
* asignación de Dimension

## Eliminación de vistas de datos

Si elimina una vista de datos en el [!UICONTROL Customer Journey Analytics], un mensaje de error indicará que cualquier proyecto de Workspace que dependa de esta vista de datos eliminada ya no funcionará.
