---
title: Información general de filtros
description: Comprenda para qué filtros se utilizan y cómo crear un filtro simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 58%

---


# Información general de Filtros {#overview}

Customer Journey Analytics le permite generar, administrar, compartir y aplicar filtros de audiencia poderosos y centrados en sus informes. Los filtros le permiten identificar subconjuntos de personas en función de sus características o de las interacciones con el sitio web. Los Filtros están diseñados como perspectivas de audiencia codificadas que puede crear para atender sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo.

Los filtros se pueden basar en atributos (tipo de explorador, dispositivo, número de visitas, país, sexo), interacciones (campañas, búsqueda de palabras clave, motor de búsqueda), salidas y entradas (personas de Facebook, una página de aterrizaje definida, dominio de referencia), variables personalizadas (campo de formulario, categorías definidas, ID del cliente) y otros criterios.

Puede crear y guardar filtros en el Generador de filtros o generar filtros a partir de una visualización de visitas en el orden previsto (en Workspace). Además, los filtros se pueden usar juntos como filtros apilados.

Los filtros del [Generador de filtros](/help/components/filters/filter-builder.md) para construir filtros y ejecutar una prueba previa, y el [Administrador de filtros](/help/components/filters/manage-filters.md) para recopilar, etiquetar, aprobar, establecer la seguridad y compartir filtros en toda la organización.

El número máximo de filtros que puede crear por cada organización de IMS es 50 000.

## Tipos de filtro {#types}

Para obtener información sobre los tipos de filtros disponibles y cómo crearlos, consulte [Creación de filtros](/help/components/filters/create-filters.md).

## Filtros secuenciales {#sequential}

Los filtros secuenciales le permiten identificar a las personas en función de la navegación y las vistas de página en su sitio, lo que proporciona un filtro de acciones e interacciones definidas. Los filtros secuenciales le ayudan a identificar qué le gusta a una persona y qué evita. Cuando se generan filtros secuenciales, se utiliza el operador THEN para definir y ordenar la navegación de la persona.

Vea el siguiente ejemplo:

![](assets/sequential_fil.png)

| Visita uno | Visita dos | Visita tres |
| --- | --- | --- |
| La persona accedió a la página de aterrizaje principal (A), excluyó la página de campaña (B) y después vio la página del producto (C). | La persona volvió a acceder a la página de aterrizaje principal (A), excluyó la página de campaña (B) y vio de nuevo la página del producto (C), para acceder a continuación a una nueva página (D). | La persona accedió y siguió la misma ruta que en la primera y la segunda visita, y después excluyó la página F para ir directamente a una página de producto dirigida (G). |

## Contenedores de filtro {#containers}

Los Filtros se basan en una jerarquía de nivel persona, sesión y evento mediante un modelo de contenedor anidado. Los contenedores anidados le permiten definir los atributos y las acciones de la persona en función de las reglas entre los contenedores y dentro de ellos.

>[!NOTE]
>El contenedor de persona era conocido como el contenedor del visitante. El contenedor de sesión se denominaba contenedor de visita, y el contenedor de evento era el contenedor de visita individual.

Un filtro establece las condiciones necesarias para filtrar a una persona en función de sus atributos o de las interacciones con su sitio. Para establecer las condiciones en un filtro, debe fijar las reglas que filtran a las personas según sus características personales y/o rasgos de navegación. Para desglosar aún más los datos de las personas, puede filtrar según las visitas específicas o las visitas individuales de cada persona para ver una página. El Generador de filtros proporciona una arquitectura simple para crear estos subconjuntos y aplicar reglas como contenedores anidados, jerárquicos, de persona, de sesión y de eventos.

La arquitectura de contenedor empleada en el Generador de filtros define la persona como el contenedor exterior, que incluye datos globales específicos de la persona en las visitas y vistas de páginas. Un contenedor de sesión anidado le permite establecer reglas para desglosar los datos de la persona en función de las sesiones, y un contenedor de evento anidado le permite desglosar la información de la persona según las vistas de página individuales. Cada contenedor le permite realizar informes basados en el historial de una persona, en las interacciones detalladas por sesión o en el desglose de eventos individuales.

### Contenedor de persona {#person}

El contenedor Persona incluye todas las visitas y vistas de página de las personas en un lapso de tiempo específico. Un filtro en el nivel de persona devuelve la página que cumple la condición, además de todas las demás páginas visitadas por la persona (restringidas únicamente por los intervalos de fechas definidos). Al ser el contenedor definido con mayor amplitud, los informes generados en el nivel del contenedor de persona muestran vistas de página de todas las visitas, lo que le permite generar análisis multivisitas. Por tanto, el contenedor de persona es el más propenso a cambiar en función de intervalos de fechas definidos. Los contenedores de persona pueden incluir valores basados en el historial general de una persona:

* Días antes de la primera compra
* Página de entrada original
* Dominios de referencia originales

### Contenedor de sesión {#session}

El contenedor de sesión le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica. El contenedor de sesión es el contenedor más utilizado, ya que captura los comportamientos de la sesión de visita al completo cuando se cumple la regla y le permite definir qué sesiones desea incluir o excluir al generar y aplicar un filtro. Puede ayudarle a responder a estas preguntas:

* ¿Cuántas sesiones se realizaron con fuentes de datos web y de centro de llamadas?
* ¿Qué páginas contribuyeron a una conversión exitosa para una venta?

Los contenedores de sesión incluyen valores basados en la incidencia por sesión:

* Tipo de sesión
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
| Todos los datos | Se trata de un filtro obligatorio que se añade dinámicamente a los informes cuando se agrega una métrica a la fila de una tabla de forma libre. |
