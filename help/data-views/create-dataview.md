---
title: Creación de una vista de datos
description: Todos los ajustes que se pueden ajustar para crear o editar una vista de datos.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 49b4998194274eec2ab8eca231029ccb5ccf648d
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 77%

---

# Creación de una vista de datos

La creación de una vista de datos implica crear métricas y dimensiones a partir de elementos de esquema o utilizar componentes estándares. La mayoría de los elementos de esquema pueden ser una dimensión o una métrica según los requisitos de la empresa. Una vez arrastrado un elemento de esquema a una vista de datos, las opciones aparecen a la derecha, donde puede ajustar el funcionamiento de la dimensión o métrica en CJA.

## Configuración de los contenedores y los ajustes de las vistas de datos

1. En Customer Journey Analytics, vaya a la ficha **[!UICONTROL Vistas de datos]**.
2. Haga clic en **[!UICONTROL Agregar]** para crear una vista de datos y ajustar su configuración.

![Nueva vista de datos](assets/new-data-view.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Conexión] | Este campo vincula la vista de datos con la conexión establecida anteriormente, que tiene uno o varios conjuntos de datos de Adobe Experience Platform. |
| [!UICONTROL Nombre] | Es obligatorio asignar un nombre a la vista de datos. |
| [!UICONTROL Descripción] | No es obligatorio proporcionar descripción detallada, pero se recomienda. |
| [!UICONTROL Zona horaria] | Elija en qué zona horaria desea que se presenten los datos. |
| [!UICONTROL Etiquetas] | [!UICONTROL Las etiquetas permiten organizar las vistas de datos en categorías.] |
| [!UICONTROL Contenedores] | Puede cambiar el nombre de los contenedores aquí para determinar cómo aparecerán en cualquier proyecto de Workspace basado en esta vista de datos. Los [!UICONTROL contenedores] se utilizan en filtros y visitas en orden previsto/flujo, entre otros, para definir la amplitud o el alcance del contexto. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=es#filter-containers) |
| [!UICONTROL El nombre del contenedor de persona es...] | [!UICONTROL Persona] (valor predeterminado). El contenedor [!UICONTROL Persona] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico. Puede cambiar el nombre de este contenedor a Usuario o a cualquier otro término que prefiera. |
| [!UICONTROL El nombre del contenedor de sesión es...] | [!UICONTROL Sesión] (valor predeterminado). El contenedor [!UICONTROL Sesión] le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica. Puede cambiar el nombre de este contenedor a Visita o a cualquier otro término que prefiera. |
| [!UICONTROL El nombre del contenedor de eventos es...] | [!UICONTROL Evento] (valor predeterminado). El contenedor [!UICONTROL Evento] define qué eventos de página desea incluir o excluir de un filtro. |

A continuación, puede crear métricas y dimensiones a partir de elementos de esquema. También puede utilizar componentes estándares.

## Creación de métricas y dimensiones a partir de elementos de esquema

1. En [!UICONTROL Customer Journey Analytics] > [!UICONTROL Vistas de datos], haga clic en la pestaña [!UICONTROL Componentes].

![Ficha Componentes](assets/components-tab.png)

Puede ver la [!UICONTROL Conexión] en la parte superior izquierda, que contiene los conjuntos de datos, y sus [!UICONTROL Campos de esquema] a continuación. Tenga en cuenta que:

* Los componentes ya incluidos son los componentes estándar necesarios (generados por el sistema).
* Adobe aplica el filtro **[!UICONTROL Contiene datos]** de forma predeterminada, de modo que solo aparecen los campos de esquema que contienen datos. Si está buscando un campo que no contenga datos, quite el filtro.

1. A continuación, arrastre un campo de esquema, como [!UICONTROL pageTitle], desde el carril izquierdo a la sección Métricas o Dimensión.

   Puede arrastrar el mismo campo de esquema a las secciones de dimensiones o métricas varias veces y configurar la misma dimensión o métrica de diferentes maneras.
Por ejemplo, desde el campo **[!UICONTROL pageTitle]** puede crear una dimensión llamada “Páginas de producto” y otra “Páginas de error”, etc., cambiando el nombre del **[!UICONTROL Nombre del componente]** a la derecha. En el campo **[!UICONTROL pageTitle]**, también puede crear métricas a partir de un valor de cadena. Por ejemplo, puede crear una o más métricas **[!UICONTROL Pedidos]** con diferentes configuraciones de atribución y diferentes valores de inclusión/exclusión.

   ![Ficha 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Puede arrastrar carpetas de campo de esquema completas desde el carril izquierdo y se ordenan automáticamente en secciones tradicionales. Los campos de cadena terminan en la sección [!UICONTROL Dimension] y los números en la sección [!UICONTROL Métricas]. O bien, puede hacer clic en **[!UICONTROL Add all]** y añadir todos los campos de esquema.

1. Una vez que seleccione el componente, verá una serie de configuraciones a la derecha. Configure el componente mediante los ajustes descritos en

* [ Información general sobre la configuración de componentes](/help/data-views/component-settings/overview.md)
* [ Configuración de componentes de atribución](/help/data-views/component-settings/attribution.md)
* [ Configuración de los componentes de comportamiento](/help/data-views/component-settings/behavior.md)
* [ Configuración de componentes de formato](/help/data-views/component-settings/format.md)
* [[!UICONTROL Incluir|] excluir configuración de componentes](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL Configuración de componentes de ] deduplicación de métricas](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL Sin ] configuración de componentes de valor](/help/data-views/component-settings/no-value-options.md)
* [ Configuración de componentes de persistencia](/help/data-views/component-settings/persistence.md)
   [[!UICONTROL Configuración de componentes de ] bloque de valores](/help/data-views/component-settings/value-bucketing.md)

## Utilice la función [!UICONTROL Duplicar]

Duplicar métricas o dimensiones y luego modificar configuraciones específicas es una manera sencilla de crear varias métricas o dimensiones a partir de un único campo de esquema. Simplemente, seleccione la opción [!UICONTROL Duplicar] debajo del nombre de la métrica o dimensión en la parte superior derecha. A continuación, modifique la nueva métrica o dimensión y guárdela con un nombre más descriptivo.

![Duplicar](assets/duplicate.png)

## Filtrar campos y dimensiones/métricas de esquema

Puede filtrar los campos de esquema en el carril izquierdo según los siguientes tipos de datos:

![Filtrar campos](assets/filter-fields.png)

También puede filtrar por conjuntos de datos y por si un campo de esquema contiene datos o si es una identidad. De forma predeterminada, se aplica el filtro **[!UICONTROL Contiene datos]** a todas las vistas de datos.

![Filtrar otros](assets/filter-other.png)

## Añadir un filtro global a la vista de datos

Puede agregar filtros que se apliquen a toda una vista de datos. Este filtro se aplica a cualquier informe que ejecute en Workspace.

1. Haga clic en la pestaña [!UICONTROL Configuración] en [!UICONTROL Vistas de datos].
1. Arrastre un filtro desde la lista en el carril izquierdo al campo [!UICONTROL Añadir filtros].
