---
title: Información general de filtros
description: Comprenda para qué filtros se utilizan y cómo crear un filtro sencillo.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Descripción general de los filtros

El análisis de trayectoria del cliente le permite crear, administrar, compartir y aplicar a sus informes filtros de audiencia potentes y centrados. Los filtros permiten identificar subconjuntos de visitantes en función de las características o las interacciones con el sitio web. Los filtros están diseñados como perspectivas de audiencia codificadas que se pueden crear para sus necesidades específicas y, a continuación, verificar, editar y compartir con otros integrantes del equipo.

Los filtros se pueden basar en atributos (tipo de explorador, dispositivo, número de visitas, país, sexo), interacciones (campañas, búsqueda de palabras clave, motor de búsqueda), salidas y entradas (visitantes de Facebook, página de aterrizaje definida, dominio de referencia), variables personalizadas (campo de formulario, categorías definidas, ID del cliente) y otros criterios.

Puede crear y guardar filtros en el Generador de filtros, o bien generar filtros a partir de una visualización de visitas en el orden previsto (en Workspace). Además, los filtros se pueden utilizar juntos como filtros apilados.

>[!IMPORTANT]
Los filtros se conocen como &#39;segmentos&#39; en Adobe Analytics. Hemos cambiado el nombre de los segmentos a filtros porque Adobe Experience Platform tiene una definición diferente de &quot;segmento&quot;. Un segmento en AEP hace referencia a...

Filtering includes the [Filter Builder](/help/components/filters/create-filters.md) to construct filters and run a pre-test, and the [Filter Manager](/help/components/filters/manage-filters.md) to collect, tag, approve, set security, and share filters across your organization.

## Filtros secuenciales

Los filtros secuenciales permiten identificar a los visitantes en función de la navegación y la vista de página en todo el sitio, lo que proporciona un filtro de acciones e interacciones definidas. Los segmentos secuenciales le ayudan a identificar qué le gusta a un visitante, así como lo que evita. Al generar filtros secuenciales, el operador ENTONCES se utiliza para definir y ordenar la navegación de los visitantes.

Vea el siguiente ejemplo:

![](assets/sequential_fil.png)

| Visita uno | Visita dos | Visita tres |
|---|---|---|
| El visitante fue a la página de aterrizaje principal (A), excluyó la página de campaña (B) y luego vio la página de producto (C). | El visitante volvió a dirigirse a la página de aterrizaje principal (A), excluyó la página de campaña (B) y volvió a visitar la página de productos (C) y, a continuación, a una nueva página (D). | El visitante ingresó y siguió la misma ruta que en la primera y la segunda visita, y luego excluyó la página F para ir directamente a una página de producto de destino (G). |

## Contenedores de filtro

Los filtros se basan en una jerarquía de nivel Persona, Sesión y Evento utilizando un modelo de contenedor anidado. Los contenedores anidados permiten definir atributos de persona y acciones en función de reglas entre y dentro de los contenedores.

>[!NOTE]
>El contenedor Persona se conocía anteriormente como contenedor de visitante. El contenedor de sesión se denominaba contenedor de visita y el contenedor de evento solía ser el contenedor de visita individual.

Un filtro establece condiciones para filtrar a un visitante en función de sus atributos o interacciones con el sitio. Para establecer las condiciones en un filtro, debe establecer reglas para filtrar a los visitantes en función de sus características y/o características de navegación. Si desea desglosar todavía más los datos de los visitantes, puede filtrar basándose en las visitas específicas y/o las visitas individuales de cada visitante para ver una página. El Generador de filtros proporciona una arquitectura sencilla para crear estos subconjuntos y aplicar reglas como contenedores anidados, jerárquicos de Persona, Sesión o Evento.

La arquitectura de contenedor empleada en el Generador de filtros define Persona como el contenedor exterior, que contiene datos globales específicos del visitante en visitas y vistas de página. Un contenedor de sesión anidado le permite establecer reglas para desglosar los datos del visitante en función de las sesiones, y un contenedor de eventos anidado le permite desglosar la información del visitante en función de las vistas de página individuales. Cada contenedor permite realizar informes a través del historial de un visitante, las interacciones desglosadas por sesiones o desglosar eventos individuales.

### Contenedor de persona

El contenedor Persona incluye todas las visitas y vistas de página de los visitantes dentro de un intervalo de tiempo específico. Un filtro en el nivel Persona devuelve la página que cumple la condición más todas las demás páginas vistas por el visitante (y solo restringidas por intervalos de fechas definidos). Como contenedor definido con mayor amplitud, los informes generados en el nivel de contenedor Persona devolverán vistas de página en todas las visitas y le permitirán generar un análisis de varias visitas. En consecuencia, el contenedor Persona es el más susceptible de cambiar según los intervalos de fechas definidos.
Los contenedores de personas pueden incluir valores basados en el historial general de un visitante:

* Días antes de la primera compra

* Página de entrada original

* Dominios de referencia originales

### Contenedor de sesión

El contenedor Sesión permite identificar las interacciones de página, las campañas o las conversiones para una sesión específica. El contenedor Sesión es el contenedor más utilizado porque captura los comportamientos de toda la sesión de visita una vez cumplida la regla y le permite definir qué sesiones desea incluir o excluir al generar y aplicar un segmento. Puede ayudarle a responder a estas preguntas:

* ¿Cuántos visitantes vieron la sección Noticias y deportes en la misma sesión?

* ¿Qué páginas contribuyeron a una conversión exitosa a una venta?

Los contenedores de sesión incluyen valores basados en la incidencia por sesión:

* Número de sesión

* Página de entrada

* Frecuencia de retorno

* Métricas de participación

* Métricas asignadas linealmente

### Contenedor de eventos

El contenedor de eventos define qué eventos de página desea incluir o excluir de un filtro. Es el contenedor más limitado del que dispone para identificar clics específicos y vistas de página cuando una condición sea verdadera, lo que le permite ver un código de seguimiento único, o aislar un comportamiento en una sección en concreto de su sitio. También podría interesarle localizar un valor específico cuando se produzca una acción, como el canal de marketing cuando se realice un pedido.

Los contenedores de eventos incluyen valores basados en desgloses de una sola página:

* Productos

* props de lista

* Dimensiones de lista

* Dimensiones de comercialización (en contexto de eventos)