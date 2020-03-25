---
title: Información general sobre Filtros
description: Comprenda para qué filtros se utilizan y cómo crear un filtro sencillo.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Información general sobre Filtros

El análisis de viaje del cliente le permite crear, administrar, compartir y aplicar filtros de audiencia potentes y centrados a sus informes. Los Filtros permiten identificar subconjuntos de visitantes en función de las características o las interacciones con el sitio web. Los Filtros están diseñados como perspectivas de audiencia codificadas que puede crear para sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo.

Los Filtros se pueden basar en atributos (tipo de explorador, dispositivo, número de visitas, país, sexo), interacciones (campañas, búsqueda de palabras clave, motor de búsqueda), salidas y entradas (visitantes de Facebook, una página de aterrizaje definida, dominio de referencia), variables personalizadas (campo de formulario, categorías definidas, ID del cliente) y otros criterios.

Puede crear y guardar filtros en el Generador de filtros o generar filtros a partir de una visualización de visitas en el orden previsto (en Workspace). Además, los filtros se pueden utilizar juntos como filtros apilados.

>[!IMPORTANT]
Los Filtros se conocen como &#39;segmentos&#39; en Adobe Analytics. Se ha cambiado el nombre de los segmentos a filtros porque Adobe Experience Platform tiene una definición diferente de &quot;segmento&quot;. Un segmento en AEP hace referencia a...

El filtrado incluye el Generador [de](/help/components/filters/create-filters.md) filtros para construir filtros y ejecutar una prueba previa, y el Administrador [de](/help/components/filters/manage-filters.md) filtros para recopilar, etiquetar, aprobar, establecer la seguridad y compartir filtros en toda la organización.

## filtros secuenciales

Los filtros secuenciales permiten identificar visitantes en función de la navegación y la vista de la página en el sitio, lo que proporciona un filtro de acciones e interacciones definidas. Los segmentos secuenciales ayudan a identificar qué le gusta a un visitante y qué evita un visitante. Al generar filtros secuenciales, el operador ENTONCES se utiliza para definir y ordenar la navegación por visitante.

Vea el siguiente ejemplo:

![](assets/sequential_fil.png)

| Visita uno | Visita dos | Visita tres |
|---|---|---|
| El visitante fue a la página de aterrizaje principal (A), excluyó la página de campaña (B) y, a continuación, vio la página Producto (C). | El visitante volvió a dirigirse a la página de aterrizaje principal (A), excluyó la página de campaña (B) y volvió a dirigirse a la página Producto (C) y, a continuación, a una nueva página (D). | El visitante ingresó y siguió la misma ruta que en la primera y la segunda visita, y luego excluyó la página F para ir directamente a una página de producto de destino (G). |

## contenedores de filtro

Los Filtros se basan en una jerarquía de nivel Persona, Sesión y Evento mediante un modelo de contenedor anidado. Los contenedores anidados permiten definir atributos de persona y acciones en función de reglas entre los contenedores y dentro de ellos.

>[!NOTE]
>El contenedor Persona era anteriormente conocido como el contenedor del Visitante. El contenedor Sesión se denominaba contenedor Visita y el contenedor Evento solía ser el contenedor Visita individual.

Un filtro establece condiciones para filtrar un visitante en función de sus atributos o interacciones con el sitio. Para definir condiciones en un filtro, debe definir reglas para filtrar visitantes en función de las características del visitante y/o las características de navegación. Si desea desglosar todavía más los datos de los visitantes, puede filtrar basándose en las visitas específicas y/o las visitas individuales de cada visitante para ver una página. El Generador de filtros proporciona una arquitectura sencilla para crear estos subconjuntos y aplicar reglas como contenedores de persona, sesión o Evento anidados y jerárquicos.

La arquitectura de contenedor empleada en el Generador de filtros define Persona como el contenedor más externo, que contiene datos globales específicos para el visitante en las visitas y vistas de páginas. Un contenedor de sesión anidado le permite establecer reglas para desglosar los datos del visitante en función de las sesiones, y un contenedor de Evento anidado le permite desglosar la información del visitante en función de vistas de página individuales. Cada contenedor permite realizar informes a través del historial de un visitante, las interacciones desglosadas por sesiones o desglosar eventos individuales.

### contenedor personal

El contenedor Persona incluye todas las visitas y vistas de página para visitantes dentro de un intervalo de tiempo específico. Un filtro en el nivel Persona devuelve la página que cumple la condición más todas las demás páginas vistas por el visitante (y solo restringidas por intervalos de fechas definidos). Como el contenedor más definido, los informes generados en el nivel de contenedor Persona devolverán vistas de página en todas las visitas y le permitirán generar una análisis de varias visitas. En consecuencia, el contenedor Persona es el más susceptible de cambiar según los intervalos de fechas definidos.
Los contenedores de persona pueden incluir valores basados en el historial general de un visitante:

* Días antes de la primera compra

* Página de entrada original

* Dominios de referencia originales

### contenedor de sesión

El contenedor Sesión permite identificar las interacciones de página, campañas o conversiones para una sesión específica. El contenedor de sesión es el contenedor más utilizado porque captura los comportamientos de toda la sesión de visita una vez cumplida la regla y le permite definir qué sesiones desea incluir o excluir al generar y aplicar un segmento. Puede ayudarle a responder a estas preguntas:

* ¿Cuántos visitantes vieron la sección Noticias y Deportes en la misma sesión?

* ¿Qué páginas contribuyeron a una conversión exitosa a una venta?

Los contenedores de sesión incluyen valores basados en la incidencia por sesión:

* Número de sesión

* Página de entrada

* Frecuencia de retorno

* Métricas de participación

* Métricas asignadas linealmente

### contenedor Evento

El contenedor Evento define qué eventos de página desea incluir o excluir de un filtro. Es el contenedor más limitado del que dispone para identificar clics específicos y vistas de página cuando una condición sea verdadera, lo que le permite ver un código de seguimiento único, o aislar un comportamiento en una sección en concreto de su sitio. También es posible que desee señalar un valor específico cuando se produzca una acción, como el canal de mercadotecnia cuando se realice un pedido.

Los contenedores de Evento incluyen valores basados en desgloses de una sola página:

* Productos

* props de lista

* Dimensiones de Lista

* Dimensiones de comercialización (en el contexto de los eventos)