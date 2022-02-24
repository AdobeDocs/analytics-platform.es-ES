---
description: Aprenda a especificar los puntos de contacto para crear una secuencia de visitas en el orden previsto multidimensional.
title: Configurar una visualización de abandonos
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '688'
ht-degree: 100%

---

# Configurar una visualización de abandonos

Puede especificar los puntos de contacto para crear una secuencia de visitas en el orden previsto multidimensional. Normalmente, un punto de contacto es una página de su sitio web. Sin embargo, los puntos de contacto no están limitados a páginas. Por ejemplo, puede añadir eventos, como unidades, así como visitantes únicos y visitas de retorno. También puede añadir dimensiones, como categoría, tipo de navegador o término de búsqueda interno.

Incluso puede añadir filtros dentro de un punto de contacto. Por ejemplo, es posible que desee comparar filtros como los usuarios de iOS y Android. Arrastre los filtros deseados sobre las visitas en el orden previsto y la información acerca de esos filtros se añadirá al informe de visitas en el orden previsto. Si desea mostrar únicamente esos filtros, puede eliminar la línea de base de Todas las visitas.

No existe limitación en el número de pasos que puede añadir o el número de dimensiones utilizadas.

Puede crear rutas para los eVars, incluidos los eVars de comercialización y [listVars](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=es) (variables que pueden tener múltiples valores por acción, como productos, listVars, eVars de comercialización y propiedades de lista). Por ejemplo, supongamos que alguien está mirando zapatos y camisetas en una página y en la siguiente mira camisetas y calcetines. El siguiente informe de flujo de productos desde zapatos será camiseta y calcetines, NO camiseta.

1. Arrastre una visualización de [!UICONTROL visitas en el orden previsto] de la lista desplegable Visualizaciones a una [!UICONTROL tabla improvisada].

1. Arrastre la dimensión Página en la tabla improvisada y, desde allí, arrastre una página (en este caso, Home - JJEsquire) al campo **[!UICONTROL Agregar punto de contacto]** como el primer punto de contacto.

   ![](assets/fallout1.png)

   Pase el ratón sobre un punto de contacto para ver si las visitas en el orden previsto y otra información sobre ese nivel, como el nombre del punto de contacto o el recuento de visitantes en ese punto y consulte el índice de éxito para ese punto de contacto (además de comparar el índice de éxito con otros puntos de contacto).

   Los números dentro de un círculo en la parte gris de la barra muestran la visita en el orden previsto entre puntos de contacto (no la visita en el orden previsto total hasta ese punto). El porcentaje de puntos de contacto muestra la visita en orden imprevisto desde el paso anterior al actual en el informe de visita en el orden previsto.

   También puede agregar una única página al informe de visitas en el orden previsto, en vez de toda la dimensión. Haga clic en la flecha derecha “>” en la dimensión de página para elegir la página específica que desea agregar al informe de visitas en el orden previsto.

1. Siga añadiendo puntos de contacto hasta que la secuencia se haya completado.

   Puede **combinar varios puntos de contacto** arrastrando uno o varios más a un punto de contacto.

   >[!NOTE]
   >
   >Los filtros se unen con AND, mientras que los elementos (como elementos de dimensión y métricas) se unen con OR.

   ![](assets/multiple_obj_touchpoint.png)

1. También puede **limitar puntos de contacto individuales a la siguiente visita** (en vez de hacerlo de forma eventual) dentro de la ruta. Debajo de cada punto de contacto, hay un selector con las opciones “Ruta eventual” y “Elemento siguiente”, como se muestra a continuación:

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ruta eventual </p> <p>(Predeterminado) </p> </td> 
   <td colname="col2"> <p>Se cuentan los visitantes que “eventualmente” se dirijan a la siguiente página de la ruta, pero no necesariamente al siguiente elemento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visita siguiente </p> </td> 
   <td colname="col2"> <p>Se cuentan los visitantes que se dirijan a la siguiente página de la ruta del elemento que aparece inmediatamente después. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ajustes de abandonos {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Configuración | Descripción |
|--- |--- |
| Contenedor de visitas en el orden previsto <ul><li>Visita</li><li>Visitante.</li></ul> | Permite alternar entre visitas y visitantes para analizar las rutas seguidas por los visitantes. La opción predeterminada es Visitante.  Estos ajustes le permiten comprender el compromiso del visitante a nivel de visitante (a lo largo de visitas) o restringir el análisis a una única visita. |

Al hacer **clic con el botón derecho en un punto de contacto**, se muestran las siguientes opciones:

| Opción | Descripción |
|--- |--- |
| Tendencia del punto de contacto | Consulte los datos de tendencia para un punto de contacto en un gráfico de líneas en el cual se hayan incorporado previamente algunos datos de detección de anomalías. |
| Tendencia del punto de contacto (%) | Realiza la tendencia del porcentaje total de visitas en el orden previsto. |
| Tendencia de todos los puntos de contacto (%) | Realiza la tendencia de todos los porcentajes de puntos de contacto en las visitas en el orden previsto (excepto “Todas las visitas”, si se incluye) en el mismo gráfico. |
| Desglosar visitas en el orden previsto en este punto de contacto | Vea qué hicieron los visitantes entre dos puntos de contacto (este punto de contacto y el siguiente) si continuaron hasta el siguiente punto de contacto. Así se crea una tabla improvisada que muestra sus dimensiones. Puede sustituir las dimensiones y otros elementos de la tabla. |
| Desglosar visitas en orden previsto en este punto de contacto | Vea qué han hecho las personas que no han seguido el embudo inmediatamente tras el paso seleccionado. |
| Crear filtro desde punto de contacto | Cree un nuevo filtro a partir de un punto de contacto seleccionado. |
