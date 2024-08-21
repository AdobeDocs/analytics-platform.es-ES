---
title: Información general de las vistas de datos
description: Una vista de datos especifica cómo desea interpretar los elementos de los datos de la conexión de Customer Journey Analytics, como, por ejemplo, métricas, dimensiones, sesiones, etc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0e4e4621abe02c022981e458282543908b2396c2
workflow-type: ht
source-wordcount: '1078'
ht-degree: 100%

---

# Información general de las vistas de datos

Una vista de datos es un contenedor específico del Customer Journey Analytics que le permite determinar cómo interpretar los datos de una [conexión](/help/connections/create-connection.md). Especifica todas las dimensiones y métricas disponibles en Analysis Workspace y de qué columnas obtienen esos datos las dimensiones y métricas. Las vistas de datos se definen a fin de prepararse para la creación de informes en Analysis Workspace.

>[!NOTE]
>
>Cualquier configuración que seleccione o cambie en una vista de datos es retroactiva y no destructiva. En otras palabras, no cambian permanentemente los datos subyacentes.

Puede crear distintas vistas de datos para la misma conexión, con conjuntos de componentes muy diferentes (dimensiones/métricas). O bien, puede crear vistas de datos con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Por ejemplo, puede tener una vista de datos en la que todas las dimensiones estén configuradas como [!UICONTROL Último contacto] y, simultáneamente, otra vista de datos (basada en el mismo conjunto de datos) con todas las dimensiones definidas como [!UICONTROL Primer contacto].

Los proyectos del Espacio de trabajo en Customer Journey Analytics se basan en vistas de datos.

>[!IMPORTANT]
>
>Se pueden añadir hasta 5000 métricas y 5000 dimensiones a una sola vista de datos.

## Funcionalidades de vistas de datos {#capabilities}

Las vistas de datos le permiten cambiar espontáneamente la configuración del elemento de esquema sin tener que variar el esquema en Adobe Experience Platform ni volver a implementar el entorno de Customer Journey Analytics.

* Puede cambiar un componente de una métrica a una dimensión y viceversa. Puede crear métricas a partir de campos de cadena o crear dimensiones a partir de campos numéricos. Esta funcionalidad facilita las cosas, ya que no tiene que crear un campo numérico en el esquema XDM para cada métrica que desee. En su lugar, puede crearlo de manera espontánea en el cuadro de diálogo de vistas de datos. Estos son algunos ejemplos:
   * **Cree una o varias dimensiones a partir de un único campo de esquema**. Se trata de una relación de uno a varios. Por ejemplo, puede crear una o más métricas de ingresos o una o más dimensiones de ingresos desde un único campo de esquema.
   * **Utilice un campo de cadena como métrica**: Al rellenar un esquema en Experience Platform con un conjunto de datos, es posible que no sepa por adelantado qué elementos de esquema necesita. Por ejemplo, es posible que no se haya dado cuenta de que necesitaba una métrica para *Errores de una página*. Como resultado, no se ha creado ningún elemento de esquema numérico a este efecto. Al utilizar un elemento de cadena como métrica, ahora puede utilizar la configuración de vistas de datos para especificar que cada vez que una cadena contenga la palabra `error`, se pueda utilizar como métrica.
   * **Utilizar un campo numérico como dimensión**: por ejemplo, si desea extraer la métrica Ingresos de la dimensión Ingresos, la dimensión Ingresos debería mostrar cada valor como un elemento de dimensión; y el número de instancias para cada elemento de dimensión como una métrica. 

* Puede crear varias métricas con diferentes modelos de atribución o con diferentes ventanas retrospectivas desde el mismo campo de esquema.

* Puede editar el ID de un componente para garantizar la compatibilidad con vistas de datos cruzados. El ID de componente es lo que utiliza la API de informes para identificar una métrica o dimensión específica. Dado que puede crear arbitrariamente muchas métricas o dimensiones a partir de un campo XDM, tiene la opción de definir su propio ID de componente. Como resultado, una métrica que utilice en un proyecto de Workspace puede utilizarse de forma compatible en todas las vistas de datos (y en la API). Incluso si las métricas se basan en campos totalmente diferentes de distintas conexiones, vistas de datos o de un esquema diferente en XDM.

* Puede especificar el nombre descriptivo del componente que aparecerá en Analysis Workspace. De forma predeterminada, este nombre se hereda del nombre para mostrar del esquema, pero ahora se puede sobrescribir para esta vista de datos específica.

* Puede ver más información relacionada con el esquema sobre los componentes. Por ejemplo:

   * de qué tipo de conjunto de datos (evento, perfil, consulta, resumen) se origina el componente,
   * de qué tipo de esquema (cadena, entero, etc.) se origina, y
   * la ruta del esquema (el campo XDM en el que se basa).

* Puede etiquetar un componente para que le resulte más fácil buscarlo en Workspace.

* Puede ocultar un componente en la creación de informes. Algunas métricas y dimensiones requieren una segunda métrica o dimensión para su configuración (como la anulación de duplicación de métricas o de compras, por ejemplo). Ocultar un componente le permite definir un componente que se puede utilizar en la configuración de otro componente sin que se vea expuesto en la creación de informes.

* Puede aplicar formato a una métrica, como por ejemplo, mostrar decimales, tiempo, porcentaje o moneda; especificar las posiciones decimales; mostrar tendencias ascendentes como verde o rojo; y especificar opciones de moneda.

* Puede crear una métrica o dimensión basada únicamente en algunos de los valores del campo de esquema. Por ejemplo, si desea una métrica de Errores, puede crear una métrica a partir del campo del nombre de página, pero solo incluir aquellas páginas que contengan la palabra `error`. La métrica Errores creada de esta manera admite filtros, se puede insertar en métricas calculadas y funciona con atribución, flujo, visitas en orden previsto, etc.

* Para las dimensiones, puede incluir o excluir automáticamente solo determinados valores dentro de un campo específico. Por ejemplo, si un desarrollador envía un valor incorrecto de `dev mistake` a un campo, puede excluirlo fácilmente de los informes mediante una regla de exclusión. La dimensión se comporta como si el valor incorrecto nunca existiera en los datos.

* Puede cambiar el nombre de los contenedores en una vista de datos y hacer que los contenedores aparezcan con su nombre nuevo en cualquier proyecto de Workspace basado en la vista de datos.

## Requisitos previos de vistas de datos {#prerequisites}

* Para poder crear vistas de datos, debe [configurar una o más conexiones a conjuntos de datos de Experience Platform](/help/connections/create-connection.md).
* Para crear o administrar una vista de datos, necesita un [conjunto de permisos en Adobe Admin Console](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-overview).
* Si utiliza el [conector de origen de Adobe Analytics](/help/data-ingestion/analytics.md) o tiene conocimientos previos de Adobe Analytics, es posible que desee comprender cómo se relacionan los campos de los esquemas y conjuntos de datos con sus homólogos de Adobe Analytics. Consulte [Asignaciones de datos de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) para obtener más información.

## Configuración de vista de datos que se puede anular el Espacio de trabajo {#settings-override}

Algunos ajustes de la vista de datos se pueden anular en Analysis Workspace en el ámbito del proyecto, mientras que otros no.

* [!UICONTROL Ventana retroactiva]
* Atribución de métricas
* Indica si los usuarios ven o no el elemento de línea [!UICONTROL Sin valor] en un informe

## Configuración de vista de datos que no se puede anular el Espacio de trabajo {#settings-no-override}

* [!UICONTROL Tipo de componente]
* Formato de métrica
* Nombre de la vista de datos
* Asignación de dimensiones

## Eliminación de vistas de datos {#delete}

Si elimina una vista de datos en [!UICONTROL Customer Journey Analytics], aparecerá un mensaje de error que indica que dejarán de funcionar todos los proyectos de [!UICONTROL Workspace] que dependan de esa vista de datos eliminada.

## Pasos siguientes

* [Creación de vistas de datos](/help/data-views/create-dataview.md)
* [Casos de uso de vistas de datos](/help/use-cases/data-views/data-views-usecases.md)
