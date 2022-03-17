---
title: Información general de filtros
description: Comprenda para qué filtros se utilizan y cómo crear un filtro simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 38c64f99b5e4a0061ccf9afb1d5ff219a78aec94
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 100%

---

# Información general de Filtros {#overview}

Customer Journey Analytics le permite crear, administrar, compartir y aplicar filtros de audiencia poderosos y centrados en sus informes. Los filtros le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los Filtros están diseñados como perspectivas de audiencia codificadas que puede crear para atender sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo.

Los Filtros se pueden basar en atributos (tipo de explorador, dispositivo, cantidad de visitas, país, sexo), interacciones (campañas, búsqueda de palabras clave, motor de búsqueda), salidas y entradas (visitantes de Facebook, una página de aterrizaje definida, dominio de referencia), variables personalizadas (campo de formulario, categorías definidas, ID del cliente) y otros criterios.

Puede crear y guardar filtros en el Generador de filtros o generar filtros a partir de una visualización de visitas en el orden previsto (en Workspace). Además, los filtros se pueden usar juntos como filtros apilados.

Los filtros del [Generador de filtros](/help/components/filters/create-filters.md) para construir filtros y ejecutar una prueba previa, y el [Administrador de filtros](/help/components/filters/manage-filters.md) para recopilar, etiquetar, aprobar, establecer la seguridad y compartir filtros en toda la organización.

## Tipos de filtro {#types}

Puede crear diferentes tipos de filtros en Workspace y el Generador de filtros, en función de lo complejo que deban ser, si solo deben aplicarse a este proyecto, etc. Este es un resumen de los tipos de filtros:

| Tipo de filtro | ¿Creado dónde? | ¿Dónde se aplica? | Uso |
| --- | --- | --- | --- |
| Filtro de lista de componentes | Haga clic en +, que le lleva al [Generador de filtros](/help/components/filters/create-filters.md) | Todos los proyectos del espacio de trabajo | Para filtros más complejos, filtros secuenciales |
| Filtro rápido | [Generador de filtros rápidos](/help/components/filters/quick-filters.md) | Solo proyecto, pero puede guardar y agregar a la lista de segmentos. | Flexibilidad para agregar o editar una o más reglas |
| Filtro de proyecto específico | [Arrastrar y soltar en la zona de colocación de segmentos de un proyecto](/help/components/filters/ad-hoc-filters.md) | Solo proyecto, pero puede guardar y agregar a la lista de filtros. | Para filtros de una sola regla |
| Filtros en un análisis de visitas en orden previsto | [Visualización de visitas en orden previsto](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) en Analysis Workspace | Para visualizaciones de visitas en el orden previsto individuales | Cree filtros a partir de un punto de contacto, añada filtros como punto de contacto y compare flujos de trabajo clave entre distintos filtros |
| Filtro basado en métricas calculadas | [Generador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=es) | Para métricas calculadas individuales | Aplicar filtros dentro de su definición de métrica |

## Filtros secuenciales {#sequential}

Los filtros secuenciales le permiten identificar a los visitantes en función de la navegación y las vistas de página en su sitio, lo que proporciona un filtro de acciones e interacciones definidas. Los filtros secuenciales le ayudan a identificar qué le gusta a un visitante, así como lo que evita. Cuando se generan filtros secuenciales, se utiliza el operador THEN para definir y ordenar la navegación del visitante.

Vea el siguiente ejemplo:

![](assets/sequential_fil.png)

| Visita uno | Visita dos | Visita tres |
| --- | --- | --- |
| El visitante accedió a la página de aterrizaje principal (A), excluyó la página de campaña (B) y después vio la página de producto (C). | El visitante volvió a acceder a la página de aterrizaje principal (A), excluyó la página de campaña (B) y vio de nuevo la página del producto (C), para acceder a continuación a una nueva página (D). | El visitante accedió y siguió la misma ruta que en la primera y la segunda visita, y después excluyó la página F para ir directamente a una página de producto dirigida (G). |

## Contenedores de filtro {#containers}

Los Filtros se basan en una jerarquía de nivel persona, sesión y evento mediante un modelo de contenedor anidado. Los contenedores anidados le permiten definir los atributos y las acciones de la persona en función de las reglas entre los contenedores y dentro de ellos.

>[!NOTE]
>El contenedor de persona era conocido como el contenedor del visitante. El contenedor de sesión se denominaba contenedor de visita, y el contenedor de evento era el contenedor de visita individual.

Un filtro establece las condiciones necesarias para filtrar a un visitante en función de sus atributos o de las interacciones con su sitio. Para establecer las condiciones en un filtro, debe fijar las reglas que filtran a los visitantes según sus características de visitante y/o rasgos de navegación. Si desea desglosar todavía más los datos de los visitantes, puede filtrar basándose en las visitas específicas y/o las visitas individuales de cada visitante para ver una página. El Generador de filtros proporciona una arquitectura simple para crear estos subconjuntos y aplicar reglas como contenedores anidados, jerárquicos, de persona, de sesión y de eventos.

La arquitectura de contenedor empleada en el Generador de filtros define la persona como el contenedor exterior, que incluye datos globales específicos del visitante en las visitas y vistas de páginas. Un contenedor de sesión anidado le permite establecer reglas para desglosar los datos del visitante en función de las sesiones, y un contenedor de eventos individual anidado le permite desglosar la información del visitante según las vistas de página individuales. Cada contenedor le permite realizar informes basados en el historial del visitante o en las interacciones detalladas por sesión, o bien desglosar los eventos individuales.

### Contenedor de persona {#person}

El contenedor de persona incluye todas las visitas y vistas de página de los visitantes en un período de tiempo específico. Un filtro en el nivel de persona devuelve la página que cumple la condición, además de todas las demás páginas visitadas por el visitante (restringidas únicamente por los intervalos de fechas definidos). Al ser el contenedor definido con mayor amplitud, los informes generados en el nivel del contenedor de persona muestran vistas de página de todas las visitas, lo que le permite generar análisis multivisitas. Por tanto, el contenedor de persona es el más propenso a cambiar en función de intervalos de fechas definidos. Los contenedores de persona pueden incluir valores basados en el historial general de un visitante:

* Días antes de la primera compra
* Página de entrada original
* Dominios de referencia originales

### Contenedor de sesión {#session}

El contenedor de sesión le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica. El contenedor de sesión es el contenedor más utilizado, ya que captura los comportamientos de la sesión de visita al completo cuando se cumple la regla y le permite definir qué sesiones desea incluir o excluir al generar y aplicar un filtro. Puede ayudarle a responder a estas preguntas:

* ¿Cuántos visitantes vieron la sección Noticias y Deportes en la misma sesión?
* ¿Qué páginas contribuyeron a una conversión exitosa para una venta?

Los contenedores de sesión incluyen valores basados en la incidencia por sesión:

* Número de sesión
* Página de entrada
* Frecuencia de retorno
* Métricas de participación
* Métricas asignadas linealmente

### Contenedor de evento {#event}

El contenedor de evento individual define qué eventos de página desea incluir o excluir de un filtro. Es el contenedor más limitado del que dispone para identificar clics específicos y vistas de página cuando una condición sea verdadera, lo que le permite ver un código de seguimiento único, o aislar un comportamiento en una sección en concreto de su sitio. También podría interesarle localizar un valor específico cuando se produzca una acción, como el canal de marketing cuando se realice un pedido.

Los contenedores de evento incluyen desgloses de una sola página basados en valores:

* Productos
* props de lista
* Dimensiones de lista
* Dimensiones de comercialización (en el contexto de eventos)

## Plantilla de filtro predefinida {#template}

La versión tradicional de Analytics incluye numerosos filtros de plantilla (filtros) y métricas calculadas predefinidos. Muchos de ellos no se aplican en CJA, o será necesario cambiarles el nombre o volver a crearlos. Otros dependerán de una solución para variables según el contexto en CJA.

| Nombre del filtro | Descripción |
| --- | --- |
| Todos los datos | Se trata de un filtro obligatorio que se añade dinámicamente a los informes cuando se agrega una métrica a la fila de una tabla improvisada. |
