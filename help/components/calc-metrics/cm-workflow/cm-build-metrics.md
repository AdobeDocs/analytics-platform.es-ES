---
description: El Creador de métricas calculadas proporciona un lienzo en el que arrastrar y soltar Dimension, métricas, filtros y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedor, reglas y operadores. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o métricas calculadas avanzadas complejas.
title: Crear métricas
source-git-commit: e50636784e406da84c986645ac380d68d9622bc6
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 86%

---

# Crear métricas

El Creador de métricas calculadas proporciona un lienzo en el que arrastrar y soltar Dimension, métricas, filtros y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedor, reglas y operadores. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o métricas calculadas avanzadas complejas.

Existen varias formas de acceder al Creador de métricas calculadas:

* En Analysis Workspace, abra un proyecto y haga clic en **[!UICONTROL + Nuevo]** > **[!UICONTROL Crear métrica]** .
* En [!DNL Analytics], vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]**.

* Haga clic en **[!UICONTROL + Agregar]**, en la parte superior del [Administrador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md), o bien

* Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Informes]**, abra cualquier informe, haga clic en el icono Métricas ![](assets/metrics_icon.png) para subir el riel de Métricas y, por último, haga clic en **[!UICONTROL Agregar]**.

![](assets/cm_builder_ui.png)

## Componentes de la interfaz de usuario {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Título </span> </td> 
   <td colname="col3"> <p>Es obligatorio nombrar la métrica. No puede guardar la métrica a menos que tenga un nombre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Descripción </span> </td> 
   <td colname="col3"> <p>Proporciónele una descripción descriptiva que indique para qué se utiliza y para distinguirla de métricas similares. </p> <p>La descripción también aparece en el informe. Se recomienda NO añadir la fórmula en la descripción; en su lugar, describa para qué se debe o no utilizar la métrica. (La fórmula se genera a medida que crea la métrica, debajo del encabezado del Resumen. Como resultado, no hay necesidad de agregar la fórmula a la descripción). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Formato </span> </td> 
   <td colname="col3"> <p>Las opciones incluyen Decimal, Hora, Porcentaje y Moneda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Lugares decimales </span> </td> 
   <td colname="col3"> <p>Muestra cuántos lugares decimales se mostrarán en el informe. El número máximo de lugares decimales que puede especificar es 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Mostrar tendencia ascendente como... </span> </td> 
   <td colname="col3"> <p>Esta configuración de polaridad de métrica muestra si Analytics debe considerar una tendencia ascendente en la métrica como buena (verde) o mala (rojo). Como resultado, el gráfico del informe se mostrará en rojo o en verde cuando vaya hacia arriba. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Etiquetas </span> </td> 
   <td colname="col3"> <p>Etiquetar es una buena forma de organizar las métricas. Todos los usuarios pueden crear etiquetas y aplicar una o más a una métrica. Sin embargo, solo verá las etiquetas de los segmentos que sean suyos o que se hayan compartido con usted. ¿Qué tipo de etiquetas debería crear? A continuación encontrará una serie de sugerencias para crear etiquetas útiles: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Etiquetas basadas en <b>nombres de equipos</b>, como Marketing social o Marketing móvil. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F">Etiquetas de <b>proyectos</b> (etiquetas de análisis), como análisis de páginas de entrada. </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3">Etiquetas de <b>categorías</b>: para hombres, geografía. </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B">Etiquetas de <b>flujo de trabajo</b>: pendiente de aprobación, conservado para (una unidad empresarial específica). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Resumen </span> </td> 
   <td colname="col3"> <p>La fórmula de <span class="uicontrol">Resumen</span> se actualiza cada vez que realice cambios en la definición de la métrica. Esta fórmula también se muestra en el carril de métrica a la izquierda, al pasar el ratón por encima de una métrica y hacer clic en el icono <img placement="inline"  src="assets/i_icon.png" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definición </span> </td> 
   <td colname="col3"> <p>Aquí es donde arrastra las métricas/métricas calculadas, segmentos o funciones para crear la métrica calculada. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">Si arrastra una métrica calculada, ampliará su definición de métrica automáticamente. </li> 
      <li id="li_A483D352522E4572AB43042473053359">Puede anidar definiciones en contenedores. Sin embargo, a diferencia de los contenedores de segmento, estos contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operador </span> </td> 
   <td colname="col3"> <p>Dividido entre ( <img placement="inline"  src="assets/divided_icon.png" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) es el operador predeterminado, además de los operadores +, - y x. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Vista previa </span> </td> 
   <td colname="col3"> <p>Proporciona una lectura rápida de cualquier posible error. La vista previa abarca los últimos 90 días. Esta es una forma de calibrar inicialmente si ha seleccionado los componentes adecuados para su métrica. Un resultado inesperado significaría que debe volver a revisar la definición de la métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Agregue </span> </td> 
   <td colname="col3"> <p>Puede añadir contenedores y números estáticos a la definición de todos los tipos de métricas calculadas. Para obtener métricas calculadas avanzadas, también puede añadir segmentos y funciones. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">Los contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. Así, cualquier cosa que se encuentre en un contenedor se procesará antes de la operación siguiente. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">Al arrastrar un segmento a un contenedor, se segmenta todo lo que se encuentra en dicho contenedor (solo métricas calculadas avanzadas). </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">Puede apilar múltiples segmentos en un contenedor. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Icono de engranaje (<span class="uicontrol">Tipo de métrica</span>, <span class="uicontrol">Atribución </span>) </td> 
   <td colname="col3"> <p>Si selecciona el icono de engranaje junto a una métrica, puede especificar el <a href="/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md"  >tipo de métrica y los modelos de atribución</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + Nuevo </span> </td> 
   <td colname="col3"> <p>Le permite crear un componente nuevo, como un filtro nuevo (que le lleva al <a href="/help/components/filters/create-filters.md"  > Generador de filtros </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Buscar componentes </p> </td> 
   <td colname="col3"> <p>En esta barra de búsqueda puede buscar dimensiones, métricas, segmentos (solo métricas calculadas avanzadas) y funciones (solo métricas calculadas avanzadas). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de dimensiones </p> </td> 
   <td colname="col3"> <p>En lugar de salir del Creador de métricas calculadas para generar un segmento simple (en el Generador de segmentos), como “Página = Página principal”, puede arrastrar Página y seleccionar Página principal directamente en el Creador de métricas calculadas. </p> <p>Esto conlleva un flujo de trabajo mucho más simplificado en lo relativo a la creación de métricas calculadas segmentadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de métricas </p> </td> 
   <td colname="col3"> <p>Las métricas se dividen en 3 categorías: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Métricas estándar ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Métricas calculadas ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Plantillas de métricas (<img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />), al final de la lista. </li> 
    </ul> <p>Cuando pasa el ratón por encima de una métrica, puede ver el icono de información a su derecha: <img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Si hace clic en este icono, le proporcionará la siguiente información: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">La fórmula de cómo se calcula. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">Una vista previa de la tendencia de la métrica. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">Un icono de edición (lápiz) en la parte superior derecha que le conducirá al Generador de métricas calculadas donde puede editar esta métrica calculada. </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de filtros </p> </td> 
   <td colname="col3"> <p>(Solo métricas calculadas avanzadas) Como administrador, esta lista muestra todos los filtros creados en su empresa de inicio de sesión. Si es un usuario no administrador, en esta lista se muestran los filtros que le pertenecen y los que compartieron con usted. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de funciones </p> </td> 
   <td colname="col3"> <p>(Solo métricas calculadas avanzadas) Las funciones se dividen en dos listas: <a href="/help/components/calc-metrics/cm-functions.md"  >Básicas</a> (utilizadas con más frecuencia) y <a href="/help/components/calc-metrics/cm-adv-functions.md"  >Avanzadas</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Selector de la vista de datos </p> </td> 
   <td colname="col3"> <p>Permite cambiar a una vista de datos diferente. </p> </td> 
  </tr> 
 </tbody> 
</table>
