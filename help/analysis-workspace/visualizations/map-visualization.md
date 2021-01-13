---
description: 'null'
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 100%

---


# Mapa

## Información general {#section_19F740FAF08D47B1AF1EF239A74FC75C}

La visualización de mapas en Analysis Workspace

* Permite crear un mapa visual de cualquier métrica (incluidas las métricas calculadas).
* Resulta útil para identificar y comparar datos de métricas entre distintas regiones geográficas.
* Admite dos fuentes de datos: latitud/longitud para el uso desde dispositivos móviles o dimensión geográfica para el uso en web.
* Admite exportación de PDF.
* Aprovecha WebGL para la visualización de gráficos. Si sus controladores gráficos no admiten la representación WebGL, es posible que deba actualizarlos.

## Creación de una visualización de mapas {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. En la lista de visualizaciones, arrastre **[!UICONTROL Mapa]** a un panel de forma libre:

   ![](assets/map-viz1.png)

1. Arrastre una métrica desde la lista de métricas (incluidas métricas calculadas).
1. Especifique la fuente de datos que desea utilizar. (Este cuadro de diálogo aparece únicamente si tiene habilitado el seguimiento de la ubicación para datos de aplicaciones móviles).

<table id="table_CD54B433464B4282A7524FB187016C47"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Latitud/Longitud móvil</b> </p> </td> 
   <td colname="col2"> <p>Esta opción representa los datos de aplicaciones móviles. </p> <p>Solo verá esta opción si la ha habilitado para su conjunto de informes en <span class="ignoretag"> <span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Administración </span> &gt; <span class="uicontrol"> Grupos de informes </span> &gt; <span class="uicontrol"> &lt;seleccionar grupo de informes&gt; </span> &gt; <span class="uicontrol"> Editar configuración </span> &gt; <span class="uicontrol"> Administración móvil </span> &gt; <span class="uicontrol"> Activar el seguimiento de ubicación</span></span>. </p> <p>Esta es la configuración predeterminada (si el seguimiento de la ubicación está habilitado). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Dimensión geográfica</b> </p> </td> 
   <td colname="col2"> <p>Esta opción representa los datos de segmentación geográfica según la ubicación de los visitantes, en función de su dirección IP. Estos datos se transforman en País, Región y Ciudad. Tenga en cuenta que no se desciende al nivel del código postal. </p> <p>Casi todos los grupos de informes tienen habilitada esta dimensión. Si no es así en su caso, póngase en contacto con el Servicio de atención al cliente de Adobe para habilitar los informes geográficos. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Haga clic en **[!UICONTROL Generar]**.

   Lo recibirá la vista Mundo, con un mapa de burbujas similar a este.

   ![](assets/bubble-world-view.png)

1. Ahora puede

   * **Hacer zoom** en este mapa para ampliar determinadas áreas haciendo doble clic en el mapa o utilizando la rueda de desplazamiento. El mapa se amplía o se reduce según dónde haya colocado el cursor. La dimensión requerida (país > estado > ciudad) se actualiza automáticamente según la interacción con el nivel de zoom.
   * **Comparar** dos o más visualizaciones de mapas en el mismo proyecto colocándolas una al lado de la otra.
   * **Mostrar comparaciones entre períodos (por ejemplo, año tras año)**:

      * Mostrar números negativos: por ejemplo, si planea crear una métrica año tras año, el mapa puede mostrar -33 % en Nueva York.
      * En las métricas de tipo porcentual, la agrupación reúne los porcentajes según la media.
      * Esquema de colores verde/rojo: positivo/negativo
   * **Girar** el mapa en 2D o 3D manteniendo presionada la tecla [!UICONTROL Ctrl] y desplazando el mapa.

   * **Alternar** entre las distintas vistas, como el mapa de calor, empleando las [configuraciones](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritas más adelante. La visualización de burbujas es la configuración predeterminada.


1. **Guardar** el proyecto para guardar la configuración completa del mapa (coordenadas, zoom, rotación).
1. La tabla improvisada, bajo la visualización, puede rellenarse arrastrando a ella dimensiones de localización y métricas desde el carril izquierdo:

   ![](assets/location-dimensions.png)

## Configuración de visualización de mapas {#section_5F89C620A6AA42BC8E0955478B3A427E}

Hay 2 conjuntos de configuraciones para el mapa:

El **icono de llave inglesa** en la parte superior recupera el cuadro de diálogo inicial, donde puede cambiar la métrica y la fuente de datos:

![](assets/map-wrench.png)

Al hacer clic en el **icono de engranaje**, se muestra esta configuración de visualización:

| Configuración | Descripción |
|--- |--- |
| Burbujas | Representa los eventos mediante burbujas. Un gráfico de burbujas es un gráfico multivariable a medio camino entre un diagrama de dispersión y un gráfico de superficie proporcional. Esta es la vista predeterminada. |
| Mapa de calor | Representa los eventos mediante un mapa de calor. Se trata de una representación gráfica de datos que muestra como colores los valores individuales contenidos en una matriz. |
| Estilos: tema de color | Muestra el esquema de colores para el mapa de calor y las burbujas. Puede elegir entre Coral, Rojos, Verdes o Azules. El valor predeterminado es Coral. |
| Estilos: estilo de mapa | Puede elegir entre Básico, Calles, Brillante, Claro, Oscuro y Satélite. |
| Radio de clúster | Agrupa los puntos de datos que se hallan dentro de un radio de píxeles definido. El valor predeterminado es 50. |
| Valor máximo personalizado | Le permite alterar el umbral para el valor máximo del mapa. Al ajustar este valor, se ajusta la escala de los valores (color y tamaño) de las burbujas/mapa de calor en relación con el valor máximo personalizado establecido. |
