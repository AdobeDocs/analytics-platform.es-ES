---
description: Aprenda a utilizar la visualización de flujo en un proyecto de Workspace.
title: Configuración de una visualización de flujo
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: a7350b6fc8fa75de07238543ed0db48af42b7577
workflow-type: tm+mt
source-wordcount: '1735'
ht-degree: 83%

---

# Configuración de una visualización de flujo {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_startswith"
>title="Comienza con"
>abstract="Este campo solo puede establecer en la versión inicial. Para actualizar este campo, seleccione **[!UICONTROL Restablecer]** para generar una nueva visualización de flujo."

>[!CONTEXTUALHELP]
>id="workspace_flow_contains"
>title="Contiene"
>abstract="Este campo solo puede establecer en la versión inicial. Para actualizar este campo, seleccione **[!UICONTROL Restablecer]** para generar una nueva visualización de flujo."

>[!CONTEXTUALHELP]
>id="workspace_flow_endswith"
>title="Finaliza con"
>abstract="Este campo solo puede establecer en la versión inicial. Para actualizar este campo, seleccione **[!UICONTROL Restablecer]** para generar una nueva visualización de flujo."

>[!CONTEXTUALHELP]
>id="workspace_flow_pathingdimension"
>title="Dimensión de las rutas"
>abstract="Seleccione una dimensión para usarla como ruta de acceso al componente seleccionado o desde este."

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="Contenedor de flujo"
>abstract="Seleccione el contenedor que desea utilizar para mostrar (números para) las rutas."

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_disabled"
>title="Incluir repeticiones (deshabilitado)"
>abstract="Las repeticiones no se pueden eliminar de las visualizaciones de flujo que incluyen dimensiones de varios valores."

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_default"
>title="Incluir repeticiones"
>abstract="Las visualizaciones de flujo se basan en instancias de una dimensión. Esta configuración le da la opción de incluir o excluir instancias repetidas, por ejemplo, recargas de página. "

>[!CONTEXTUALHELP]
>id="workspace_flow_limit_occurrence"
>title="Limitar a la primera/última ocurrencia"
>abstract="Los resultados se limitan a las rutas en las que el primer/último punto de contacto es una entrada/salida."

>[!CONTEXTUALHELP]
>id="workspace_flow_numberofcolumns"
>title="Número de columnas"
>abstract="Este campo solo puede establecer en la versión inicial. Para actualizar este campo, seleccione **[!UICONTROL Restablecer]** para generar una nueva visualización de flujo."

>[!CONTEXTUALHELP]
>id="workspace_flow_itemsexpandedpercolumn"
>title="Elementos expandidos por columna"
>abstract="Este campo solo puede establecer en la versión inicial. Para actualizar este campo, seleccione **[!UICONTROL Restablecer]** para generar una nueva visualización de flujo."

>[!CONTEXTUALHELP]
>id="workspace_flow_resettoupdate"
>title="Restablecer para actualizar"
>abstract="Este campo solo puede establecer en la versión inicial. Para actualizar este campo, seleccione **[!UICONTROL Restablecer]** para generar una nueva visualización de flujo."


Las visualizaciones de flujo le ayudan a comprender los recorridos que se originan a partir de un evento de conversión específico en el sitio web o la aplicación. O que conducen a un evento de conversión específico. La visualización traza una ruta a través de las dimensiones (y elementos de dimensión) o métricas.

Puede configurar el inicio o el final de la ruta que le interese. O bien, analice todas las rutas que fluyen a través de una dimensión o elemento de dimensión.

![Pantalla de configuración de flujo que muestra los campos Comienza con, Contiene y Finaliza con.](assets/new-flow.png)

## Usar

1. Añada una visualización ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flujo]**. Consulte [Añadir una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Ancle la visualización de flujo mediante una de las opciones siguientes:

   * [!UICONTROL **Comienza con**] (métricas, dimensiones o elementos), o
   * [!UICONTROL **Contiene**] (dimensiones o elementos), o
   * [!UICONTROL **Finaliza con**] (métricas, dimensiones o elementos)

   Cada una de estas categorías se muestra como *zona de colocación*. Puede rellenar la zona de colocación de tres formas:

   * Utilice el menú desplegable para seleccionar métricas o dimensiones.
   * Arrastre las dimensiones o métricas del panel izquierdo.
   * Empiece a escribir el nombre de una dimensión o métrica y, a continuación, selecciónela cuando aparezca en el menú desplegable.

   >[!IMPORTANT]
   >
   >Las métricas calculadas no se pueden usar con los campos **[!UICONTROL Comienza con]** o **[!UICONTROL Termina con]**.

1. Si elige una métrica, también debe proporcionar una [!UICONTROL **Dimensión de rutas**] para usar como ruta de acceso o de salida del componente seleccionado, como se muestra aquí. El valor predeterminado es [!UICONTROL **Página**].

   ![Configuración de flujo](assets/flow-configure.png)

1. (Opcional) Seleccione **[!UICONTROL Mostrar ajustes avanzados]** para configurar cualquiera de las siguientes opciones:


   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Etiquetas de ajustes]** | Normalmente, las etiquetas de los elementos de flujo se truncan para ahorrar espacio en la pantalla, pero puede hacer la etiqueta entera visible al marcar esta casilla.  Valor predeterminado = sin marcar. |
   | **[!UICONTROL Incluir instancias de repetición]** | Las visualizaciones de flujo se basan en instancias de una dimensión. Esta configuración le da la opción de incluir o excluir instancias repetidas, por ejemplo, recargas de página. Sin embargo, las repeticiones no se pueden eliminar de las visualizaciones de flujo que incluyen dimensiones multivalor, como listVars, listProps, s.product, eVars de comercialización, etc. <p>Esta opción está desactivada de forma predeterminada.</p> |
   | **[!UICONTROL Limitar a la primera/última ocurrencia]** | Limite las rutas a aquellas que comienzan/terminan con la primera/última ocurrencia de una dimensión, un elemento o una métrica. Consulte [Limitar a la primera/última ocurrencia](#example-scenario-for-limit-to-firstlast-occurrence) para obtener una explicación más detallada. |
   | **[!UICONTROL Número de columnas]** | El número de columnas que quiere incluir en el diagrama de flujo. Puede especificar hasta un máximo de 5 columnas. |
   | **[!UICONTROL Elementos expandidos por columna]** | Cuántos elementos desea incluir en cada columna. Puede especificar un máximo de 10 elementos expandidos por columna. |
   | **[!UICONTROL Contenedor de flujo]** | Puede alternar entre **[!UICONTROL Cuenta global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Cuenta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Oportunidad]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Grupo de compra]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Sesiones]** y **[!UICONTROL Persona]** para analizar las rutas. Esta configuración le ayuda a comprender la participación a nivel de contenedor específico (entre sesiones) o a restringir el análisis a una sola sesión. |

   >[!IMPORTANT]
   >
   >La combinación de **[!UICONTROL Número de columnas]** y **[!UICONTROL Elementos expandidos por columna]** determina el número de solicitudes subyacentes necesarias para crear la visualización del flujo. Cuanto más altos sean esos números, más tiempo se tarda en procesar una visualización.


1. Seleccione **[!UICONTROL Generar]**.


### Ejemplo

Suponga que desea rastrear la ruta que siguieron los usuarios tanto hacia como desde las páginas más populares de su sitio.

1. Cree una visualización de flujo tal como se ha descrito anteriormente.
1. Arrastre la dimensión [!UICONTROL **Página**] al campo **[!UICONTROL Contiene]** y, a continuación, seleccione [!UICONTROL **Generar**].
1. La visualización de flujo se genera con la página más vista visible en el nodo de enfoque en el centro de la visualización. También verá las páginas principales que llevan a esa página (a la izquierda del nodo de enfoque), así como las páginas principales que salen de esa página (a la derecha del nodo de enfoque).
1. Analice los datos en el flujo, tal como se describe en [Configurar](#configure).


## Configuración

En la parte superior de las visualizaciones aparece un resumen de la configuración de flujo. Las rutas del diagrama son proporcionales. Las rutas con más actividad se muestran más gruesas.

![Ejemplo de salida de flujo que muestra Termina con Visitas, dimensión de rutas: Página y contenedor de Flujo: Visitantes.](assets/flow-output.png)

Para explorar en profundidad los datos, tiene varias opciones:

* El diagrama de flujo es interactivo. Pase el ratón por encima del diagrama para cambiar los detalles que se muestran.

* Al seleccionar en un nodo del diagrama, aparecen los detalles de dicho nodo. Seleccione de nuevo el nodo para contraerlo.

  ![Ejemplo de diagrama de flujo interactivo que muestra detalles de nodo.](assets/node-details.png)

* Puede filtrar una columna para mostrar solo ciertos resultados, como incluir y excluir, especificar criterios, etc.

* Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) en el lado izquierdo o derecho para expandir una columna.

* Para personalizar la salida, use las opciones del [menú contextual](#context-menu).

* Para editar el flujo o reconstruirlo con diferentes opciones, seleccione ![Editar](/help/assets/icons/Edit.svg) junto al resumen de la configuración.

## Filtro

Por encima de cada columna aparece un ![Filtro](/help/assets/icons/Filter.svg) cuando pasa el puntero por encima. Al hacer clic en el filtro, obtiene el mismo cuadro de diálogo de filtro que existe en la tabla de forma libre. Consulte [Filtrar y ordenar](freeform-table/../../freeform-table/filter-and-sort.md).

* Utilice **[!UICONTROL Mostrar configuración avanzada]** para configurar los ajustes avanzados para incluir o excluir determinados criterios con una lista de operadores. Consulte [Filtros y ordenación](../freeform-table/filter-and-sort.md) para obtener más información.
* Una vez filtrada una columna, esa columna específica refleja el filtrado. Un ![filtro](/help/assets/icons/FilterColored.svg) azul indica que la columna está filtrada.  El filtro reduce la columna para mostrar solo el elemento permitido en el filtro. También elimina todos los elementos, excepto el elemento que desee en el filtro.
* Todas las columnas descendentes y ascendentes deben persistir, siempre y cuando haya datos que fluyen a los nodos que quedan.
* Para quitar un filtro, seleccione ![Filtro](/help/assets/icons/Filter.svg) para abrir el menú de filtros. Quite los filtros aplicados y, a continuación, seleccione **[!UICONTROL Guardar]**. El flujo volverá a su estado anterior sin filtrar.

## Menú contextual

Utilice un menú contextual en cualquier nodo de la visualización de flujo con las siguientes opciones:

| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Centrarse en este nodo]** | Cambia el interés al nodo seleccionado. El nodo de interés aparece en el centro del diagrama de flujo. |
| **[!UICONTROL Volver a empezar]** | Le hace regresar al generador de diagramas de forma libre, donde puede crear un nuevo diagrama de flujo. |
| **[!UICONTROL Crear un segmento para esta ruta]** | Creación de segmentos. Esta selección le lleva al Generador de segmentos, donde puede configurar el nuevo segmento. |
| **[!UICONTROL Desglose]** | Desglosa el nodo mediante las dimensiones, métricas o tiempo disponibles. |
| **[!UICONTROL Filtrar columna]** | Aparecerán las mismas opciones de filtro que están disponibles en la tabla de forma libre. Para obtener más información acerca de las opciones disponibles, consulte la sección &quot;Aplicar un filtro simple o avanzado a una tabla&quot; en [Filtrar y ordenar tablas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| **[!UICONTROL Excluir elemento]** o **[!UICONTROL Restaurar elementos excluidos]** | Quita un nodo específico de la columna y lo crea automáticamente como filtro en la parte superior de la columna. Para restaurar el elemento excluido, seleccione en el menú contextual **[!UICONTROL Restaurar elemento excluido]**. también puede abrir el segmento en la parte superior de la columna y quitar el recuadro con el elemento que acaba de excluir. |
| **[!UICONTROL Tendencia]** | Crea un diagrama de tendencia para el nodo. |
| **[!UICONTROL Mostrar columna siguiente]** / **[!UICONTROL Mostrar columna anterior]** | Muestra la columna siguiente (derecha) o anterior (izquierda) de la visualización. |
| **[!UICONTROL Ocultar columna]**&#x200B;n | Oculta la columna seleccionada de la visualización. |
| **[!UICONTROL Expandir toda la columna]** | Expande una columna para mostrar todos los nodos. De forma predeterminada, únicamente se muestran los cinco nodos principales. |
| **[!UICONTROL Crear audiencia a partir de la selección]** | Crea una audiencia basada en la columna seleccionada. |
| **[!UICONTROL Contraer toda la columna]** | Oculta todos los nodos de una columna. |

## Limitar a la primera/última ocurrencia

Al utilizar esta opción, tenga en cuenta que:

* **[!UICONTROL Limitar a primera/última incidencia]** solo cuenta la primera/última incidencia de la serie. Todas las demás ocurrencias de los criterios **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]** se descartan.
* Si se usa con un flujo de **[!UICONTROL Comienza con]**, solo se incluye la primera incidencia que coincida con los criterios de inicio.
En el ejemplo siguiente, se incluyen **todas** las ocurrencias de *Añadir al carro de compras* y *Categoría principal del producto* en cada paso del flujo.
  ![Sin límite, primero](assets/limitofffirst.png)

  En el ejemplo siguiente, solo se incluyen las **primeras** ocurrencias de *Añadir al carro de compras* y *Categoría principal del producto* en cada paso del flujo.
  ![Lint, inicio](assets/limitonfirst.png)
* Si se usa con un flujo **[!UICONTROL Finaliza con]**, solo se incluye la última ocurrencia que coincida con los criterios de finalización.
En el ejemplo siguiente, se incluyen **todas** las ocurrencias de *Categoría principal del producto* y *Añadir al carro de compras* en cada paso del flujo.
  ![Sin límite, primero](assets/limitofflast.png)

  En el ejemplo siguiente, solo se incluyen las **últimas** ocurrencias de *Categoría principal del producto* y *Añadir al carro de compras* en cada paso del flujo.
  ![Lint, inicio](assets/limitonlast.png)
* La serie utilizada difiere según el contenedor. Si usa el contenedor **[!UICONTROL Session]**, la serie de eventos estará limitada a una sesión.  Si usa cualquiera de los otros contenedores (por ejemplo, **[!UICONTROL Persona]**, o **[!UICONTROL Cuenta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, o **[!UICONTROL Oportunidad]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}), la serie de eventos se basa en el contenedor especificado y puede abarcar varias sesiones.
* La opción **[!UICONTROL Limitar a la primera/última ocurrencia]** puede configurarse en los ajustes avanzados cuando se utiliza un elemento de métrica o dimensión en los campos **[!UICONTROL Comienza con]** o **[!UICONTROL Termina con]**.


>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

