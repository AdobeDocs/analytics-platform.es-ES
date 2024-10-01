---
description: Aprenda a utilizar la visualización de flujo en un proyecto de Workspace.
title: Configuración de una visualización de flujo
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 37%

---

# Configuración de una visualización de flujo

Las visualizaciones de flujo le ayudan a comprender los recorridos que se originan a partir de un evento de conversión específico en el sitio web o la aplicación. O que conducen a un evento de conversión específico. La visualización traza una ruta a través de las dimensiones (y elementos de dimensión) o métricas.

Puede configurar el inicio o el final de la ruta que le interese. O bien, analice todas las rutas que fluyen a través de una dimensión o elemento de dimensión.

![Pantalla de configuración de flujo que muestra los campos Comienza con, Contiene y Finaliza con.](assets/new-flow.png)

## En su lugar, utilice 

1. Agregue una visualización ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]**. Consulte [Agregar una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Ancle la visualización de flujo mediante una de las opciones siguientes:

   * [!UICONTROL **Comienza con**] (métricas, dimensiones o elementos), o
   * [!UICONTROL **Contiene**] (dimensiones o elementos), o
   * [!UICONTROL **Finaliza con**] (métricas, dimensiones o elementos)

   Cada una de estas categorías se muestra en pantalla como una *zona de colocación*. Puede rellenar la zona de colocación de tres formas:

   * Utilice el menú desplegable para seleccionar métricas o dimensiones.
   * Arrastre dimensiones o métricas desde el panel izquierdo.
   * Empiece a escribir el nombre de una dimensión o métrica y, a continuación, selecciónela cuando aparezca en la lista desplegable.

   >[!IMPORTANT]
   >
   >No se pueden usar las métricas calculadas en los campos **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]**.

1. Si elige una métrica, también debe proporcionar un [!UICONTROL **Dimension de rutas**] que utilizará como ruta de acceso o de origen del componente seleccionado, como se muestra a continuación. El valor predeterminado es [!UICONTROL **Página**].

   ![Configuración de flujo](assets/flow-configure.png)

1. (Opcional) Seleccione **[!UICONTROL Mostrar configuración avanzada]** para configurar cualquiera de las siguientes opciones:


   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Etiquetas de ajustes]** | Normalmente, las etiquetas de los elementos de flujo se truncan para ahorrar espacio en la pantalla, pero puede hacer la etiqueta entera visible al marcar esta casilla.  Valor predeterminado = sin marcar. |
   | **[!UICONTROL Incluir instancias de repetición]** | Las visualizaciones de flujo se basan en instancias de una dimensión. Esta configuración le da la opción de incluir o excluir instancias repetidas, por ejemplo, recargas de página. Sin embargo, las repeticiones no se pueden eliminar de las visualizaciones de flujo que incluyen dimensiones multivalor, como listVars, listProps, s.product, eVars de comercialización, etc. <p>Esta opción está desactivada de forma predeterminada.</p> |
   | **[!UICONTROL Limitar a la primera/última ocurrencia]** | Limite las rutas a las rutas que comienzan o finalizan con la primera o la última aparición de una dimensión, un elemento o una métrica. Consulte [Limitar a la primera/última ocurrencia](#example-scenario-for-limit-to-firstlast-occurrence) para obtener una explicación más detallada. |
   | **[!UICONTROL Número de columnas]** | El número de columnas que quiere incluir en el diagrama de flujo. Puede especificar hasta un máximo de 5 columnas. |
   | **[!UICONTROL Elementos expandidos por columna]** | Cuántos elementos desea incluir en cada columna. Puede especificar un máximo de 10 elementos expandidos por columna. |
   | **[!UICONTROL Contenedor de flujo]** | Puede cambiar entre **[!UICONTROL Sesiones]** y **[!UICONTROL Persona]** para analizar las rutas. Esta configuración le ayuda a comprender la participación de una persona en el nivel de persona (entre sesiones) o a restringir el análisis a una sola sesión. |

   >[!IMPORTANT]
   >
   >La combinación de **[!UICONTROL Número de columnas]** y **[!UICONTROL Elementos expandidos por columna]** determina el número de solicitudes subyacentes necesarias para crear la visualización del flujo. Cuanto más altos sean esos números, más tiempo se tarda en procesar una visualización.


1. Seleccione **[!UICONTROL Generar]**.


### Ejemplo

Supongamos que desea rastrear la ruta que tomaron los usuarios tanto hacia como desde las páginas más populares del sitio.

1. Cree una visualización de flujo como se ha descrito anteriormente.
1. Arrastre la dimensión [!UICONTROL **Página**] al campo **[!UICONTROL Contiene]** y, a continuación, seleccione [!UICONTROL **Generar**].
1. Se genera la visualización de flujo, con la página más vista visible en el nodo de enfoque, en el centro de la visualización. También verá las páginas principales que dirigen a esa página (a la izquierda del nodo de enfoque), así como las páginas principales que dirigen fuera de esa página (a la derecha del nodo de enfoque).
1. Analice los datos en el flujo, tal como se describe en [Configurar](#configure).


## Configuración

En la parte superior de las visualizaciones aparece un resumen de la configuración de flujo. Las rutas del diagrama son proporcionales. Las rutas con más actividad se muestran más gruesas.

![Ejemplo de salida de flujo que muestra Ends with Visits, dimensión Pathing: Page y contenedor de flujo: Visitors.](assets/flow-output.png)

Para explorar en profundidad los datos, tiene varias opciones:

* El diagrama de flujo es interactivo. Pase el ratón por encima del diagrama para cambiar los detalles que se muestran.

* Al seleccionar en un nodo del diagrama, aparecen los detalles de dicho nodo. Vuelva a seleccionar el nodo para contraerlo.

  ![Ejemplo de diagrama de flujo interactivo que muestra detalles de nodo.](assets/node-details.png)

* Puede filtrar una columna para mostrar solo ciertos resultados, como incluir y excluir, especificar criterios, etc.

* Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) en el lado izquierdo o derecho para expandir una columna.

* Para personalizar la salida, use las opciones del [menú contextual](#context-menu).

* Para editar el flujo o reconstruirlo con diferentes opciones, seleccione ![Editar](/help/assets/icons/Edit.svg) junto al resumen de la configuración.

## Filtro

Encima de cada columna aparece un filtro ![Filter](/help/assets/icons/Filter.svg) al pasar el ratón por encima. Al seleccionar el filtro, obtiene el mismo cuadro de diálogo de filtro que existe en la tabla de forma libre. Ver [Filtrar y ordenar](freeform-table/../../freeform-table/filter-and-sort.md).

* Use **[!UICONTROL Mostrar avanzado]** para configurar las opciones avanzadas con el fin de incluir o excluir ciertos criterios con una lista de operadores. Consulte [Filtros y ordenación](../freeform-table/filter-and-sort.md) para obtener más información.
* Una vez filtrada una columna, esa columna específica refleja el filtrado. Un ![filtro](/help/assets/icons/FilterColored.svg) azul indica que la columna está filtrada.  El filtro reduce la columna para mostrar solo el elemento permitido en el filtro. También elimina todos los elementos, excepto el elemento que desee en el filtro.
* Todas las columnas descendentes y ascendentes persisten, siempre y cuando haya datos que fluyen a los nodos restantes.
* Para quitar un filtro, selecciona ![Filtro](/help/assets/icons/Filter.svg) para abrir el menú de filtros. Quite los filtros aplicados y, a continuación, seleccione **[!UICONTROL Guardar]**. El flujo volverá a su estado anterior sin filtrar.

## Menú contextual

Utilice un menú contextual en cualquier nodo de la visualización de flujo con las siguientes opciones:

| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Centrarse en este nodo]** | Cambia el interés al nodo seleccionado. El nodo de interés aparece en el centro del diagrama de flujo. |
| **[!UICONTROL Volver a empezar]** | Vuelva al generador de diagramas improvisados, donde puede crear un nuevo diagrama de flujo. |
| **[!UICONTROL Crear un filtro para esta ruta]** | Crear un filtro. Esta selección le lleva al Generador de filtros, donde puede configurar el nuevo filtro. |
| **[!UICONTROL Desglose]** | Desglosa el nodo mediante las dimensiones, métricas o tiempo disponibles. |
| **[!UICONTROL Columna de filtro]** | Aparecerán las mismas opciones de filtro que están disponibles en la tabla de forma libre. Para obtener más información acerca de las opciones disponibles, vea la sección &quot;Aplicar un filtro simple o avanzado a una tabla&quot; en [Filtrar y ordenar tablas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| **[!UICONTROL Excluir elemento]** o **[!UICONTROL Restaurar elementos excluidos]** | Quita un nodo específico de la columna y lo crea automáticamente como filtro en la parte superior de la columna. Para restaurar el elemento excluido, en el menú contextual, seleccione **[!UICONTROL Restaurar elemento excluido]**. También puede abrir el filtro en la parte superior de la columna y quitar el recuadro con el elemento que acaba de excluir. |
| **[!UICONTROL Tendencia]** | Crea un diagrama de tendencia para el nodo. |
| **[!UICONTROL Mostrar columna siguiente]** / **[!UICONTROL Mostrar columna anterior]** | Muestra la columna siguiente (derecha) o anterior (izquierda) de la visualización. |
| **[!UICONTROL Ocultar columna]**n | Oculta la columna seleccionada de la visualización. |
| **[!UICONTROL Expandir toda la columna]** | Expande una columna para mostrar todos los nodos. De forma predeterminada, únicamente se muestran los cinco nodos principales. |
| **[!UICONTROL Crear audiencia a partir de la selección]** | Crea una audiencia basada en la columna seleccionada. |
| **[!UICONTROL Contraer toda la columna]** | Oculta todos los nodos de una columna. |

## Limitar a la primera/última ocurrencia

Al utilizar esta opción, tenga en cuenta que:

* **[!UICONTROL Limitar a primera/última incidencia]** solo cuenta la primera/última incidencia de la serie. Todas las demás ocurrencias de los criterios **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]** se descartan.
* Si se usa con un flujo de **[!UICONTROL Comienza con]**, solo se incluirá la primera incidencia que coincida con los criterios de inicio.
En el ejemplo siguiente, se incluyen **todas** las ocurrencias de *Agregar al carro de compras* y *Categoría principal del producto* en cada paso del flujo.
  ![Sin límite, primero](assets/limitofffirst.png)

  En el ejemplo siguiente, solo se incluyen las **primeras** ocurrencias de *Agregar al carro de compras* y *Categoría principal del producto* en cada paso del flujo.
  ![Lint, inicio](assets/limitonfirst.png)
* Si se usa con un flujo **[!UICONTROL Finaliza con]**, solo se incluirá la última incidencia que coincida con los criterios finales.
En el ejemplo siguiente, se incluyen **todas** las ocurrencias de *categoría principal del producto* y *Agregar al carro de compras* en cada paso del flujo.
  ![Sin límite, primero](assets/limitofflast.png)

  En el ejemplo siguiente, solo se incluyen las **últimas** ocurrencias de *categoría principal del producto* y *Agregar al carro de compras* en cada paso del flujo.
  ![Lint, inicio](assets/limitonlast.png)
* La serie utilizada difiere según el contenedor. Si se usa el contenedor **[!UICONTROL Persona]**, la serie de eventos es la sesión. Si se usa el contenedor **[!UICONTROL Session]**, la serie de eventos son todos los eventos de un usuario determinado en el intervalo de fechas proporcionado.
* La opción **[!UICONTROL Limitar a primera/última incidencia]** se puede configurar en la configuración avanzada cuando se usa un elemento de métrica o Dimension en los campos **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]**.


>[!MORELIKETHIS]
>
>[Agregar una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

