---
title: Información general de filtros
description: Comprenda para qué filtros se utilizan y cómo crear un filtro simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 23%

---


# Información general de Filtros {#overview}

Customer Journey Analytics le permite generar, administrar, compartir y aplicar filtros de audiencia poderosos y centrados en sus informes. Los filtros le permiten identificar subconjuntos de personas en función de sus características o interacciones. Los Filtros están diseñados como perspectivas de audiencia codificadas que puede crear para atender sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo.

Los filtros se pueden basar en

- atributos (tipo de explorador, dispositivo, número de visitas, país, sexo),
- interacciones (campañas, búsqueda de palabras clave, motor de búsqueda),
- salidas y entradas (personas de Facebook, una página de aterrizaje definida, dominio de referencia, evento de geovalla),
- variables personalizadas (campo de formulario, categorías definidas, ID de cliente),
- y otros criterios.

Puede crear y guardar filtros en el Generador de filtros o generar filtros a partir de una visualización de visitas en el orden previsto (en Workspace). Además, los filtros se pueden usar juntos como filtros apilados.

El filtrado incluye [Generador de filtros](/help/components/filters/filter-builder.md) para construir filtros y ejecutar una prueba previa, y la variable [Administrador de filtros](/help/components/filters/manage-filters.md) para recopilar, etiquetar, aprobar, establecer la seguridad y compartir filtros en toda la organización.

El número máximo de filtros que puede crear por cada organización de IMS es 50 000.

## Tipos de filtro {#types}

Para obtener información sobre los tipos de filtros disponibles y cómo crearlos, consulte [Creación de filtros](/help/components/filters/create-filters.md).

## Filtros secuenciales {#sequential}

Los filtros secuenciales le permiten identificar a las personas en función de la navegación (vistas de página en su sitio, interacciones con escenas en su aplicación móvil o uso de un menú en un cuadro de la parte superior). Los filtros secuenciales proporcionan un filtro de acciones e interacciones definidas y le ayudan a identificar qué le gusta a una persona y qué evita. Cuando se generan filtros secuenciales, se utiliza el operador THEN para definir y ordenar la navegación de la persona.

>[!IMPORTANT]
>
>Debe tener el **Seleccionar** para crear filtros secuenciales de canales cruzados. Póngase en contacto con el administrador si no está seguro del paquete de Customer Journey Analytics que tiene.

Vea el siguiente ejemplo:

| Sesión uno | Sesión dos | Sesión tres |
| --- | --- | --- |
| La persona fue a la página de aterrizaje principal A, excluyó la página de campaña B y luego vio la página de producto C. | La persona volvió a acceder a la página de aterrizaje principal A, excluyó la página de campaña B y vio de nuevo la página del producto C, para acceder a continuación a una nueva página D. | La persona accedió y siguió la misma ruta que en la primera y la segunda visita, y después excluyó la página F para ir directamente a una página de producto dirigida G. |

## Contenedores de filtro {#containers}

Los filtros se basan en una jerarquía de nivel persona, sesión y evento mediante un modelo de contenedor anidado. Los contenedores anidados le permiten definir los atributos y las acciones de la persona en función de las reglas entre los contenedores y dentro de ellos.


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Persona</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sesión</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Evento</td>
</tr>
</table>

>[!NOTE]
>El contenedor de persona era conocido como el contenedor del visitante. El contenedor de sesión se denominaba contenedor de visita, y el contenedor de evento era el contenedor de visita individual.

Un filtro establece las condiciones necesarias para filtrar a una persona en función de sus atributos o de las interacciones con su sitio, aplicación móvil u otro tipo de dispositivo del que haya recopilado datos. Para establecer las condiciones en un filtro, debe fijar las reglas que filtran a las personas según sus características personales y/o rasgos de navegación. Para desglosar aún más los datos de las personas, puede filtrar según las visitas específicas o las visitas individuales de vista de página, los toques de pantalla o las opciones de menú de cada persona en un cuadro en la parte superior. Pero también filtre por atributos que haya ingerido desde un CRM o sistema de fidelidad. El Generador de filtros proporciona una arquitectura simple para crear estos subconjuntos y aplicar reglas como contenedores anidados, jerárquicos, de persona, de sesión y de eventos.

La arquitectura de contenedor empleada en el Generador de filtros define la persona como el contenedor exterior. El contenedor contiene datos globales específicos de la persona en las visitas y vistas de página, pantallas de aplicaciones móviles o pantallas de menú en un cuadro en la parte superior. Un contenedor de sesión anidado le permite establecer reglas para desglosar los datos de la persona en función de las sesiones, y un contenedor de evento anidado le permite desglosar la información de la persona según las interacciones individuales. Cada contenedor le permite realizar informes basados en el historial de una persona, en las interacciones detalladas por sesión o en el desglose de eventos de experiencia individuales.

### Contenedor de persona {#person}

El contenedor Persona incluye todas las visitas y vistas de página, la pantalla de la aplicación móvil, el cuadro en la parte superior o la interacción entre la consola y el juego para personas en un lapso de tiempo específico. Básicamente, todos los eventos de experiencia que forman parte de los conjuntos de datos definidos dentro de la conexión de Customer Journey Analytics. Un filtro en el nivel de persona devuelve las vistas de página, la aplicación móvil o las pantallas del cuadro superior que cumplen la condición. Además de todas las demás interacciones de esa misma persona en canales en línea y sin conexión (y solo restringidas por intervalos de fechas definidos). Al ser el contenedor definido con mayor amplitud, los informes generados en el nivel del contenedor de persona devuelven vistas de página, pantallas de aplicaciones móviles y mucho más en todas las visitas, lo que le permite generar análisis multicanal de varias visitas. Por lo tanto, el contenedor de persona es el más susceptible de cambiar en función de intervalos de fechas definidos.
Los contenedores de persona pueden incluir valores basados en el historial general de una persona:

- Días antes de la primera compra
- Página de entrada original o pantalla de inicio de la aplicación móvil
- Dominios de referencia originales

### Contenedor de sesión {#session}

El contenedor Sesión le permite identificar interacciones de páginas o interacciones de aplicaciones móviles, campañas o conversiones para una sesión específica. El contenedor de sesión es el contenedor más utilizado, ya que captura los comportamientos de la sesión de visita al completo cuando se cumple la regla. El contenedor Sesión también le permite definir qué sesiones desea incluir o excluir al generar y aplicar un filtro. Puede ayudarle a responder a las siguientes preguntas:

- ¿Cuántas sesiones se realizaron con fuentes de datos web y de centro de llamadas?
- ¿Qué páginas contribuyeron a una conversión exitosa para una venta?

Los contenedores de sesión incluyen valores basados en la incidencia por sesión:

- Tipo de sesión
- Página de entrada
- Frecuencia de retorno
- Métricas de participación
- Métricas asignadas linealmente

Las vistas de datos de Customer Journey Analytics le permiten determinar la duración de una sesión, pero también cuándo se debe crear una nueva. Por ejemplo, puede definir una nueva sesión de aplicación móvil basada en cada vez que un usuario inicie la aplicación móvil. Consulte [Configuración de sesión](/help/data-views/session-settings.md) para obtener más información.

### Contenedor de evento {#event}

El contenedor Evento define qué página, aplicación móvil u otro tipo de eventos desea incluir o excluir de un filtro. Es el contenedor más estrecho del que dispone para identificar clics, vistas de página y toques específicos en un botón de una aplicación móvil en el que una condición es verdadera. El contenedor Evento le permite ver un único código de seguimiento o aislar un comportamiento en un área concreta de la aplicación móvil. También podría interesarle localizar un valor específico cuando se produzca una acción, como el canal de marketing cuando se realice un pedido.

Los contenedores de evento incluyen desgloses de una sola página basados en valores para:

- Productos
- props de lista
- Dimensiones de lista
- Dimensiones de comercialización (en el contexto de eventos)

## Plantilla de filtro predefinida {#template}

La versión tradicional de Analytics incluye numerosas plantillas y métricas calculadas listas para usar. Muchos de ellos no se aplican en el Customer Journey Analytics, o hay que cambiarles el nombre o volver a crearlos. Otros dependen de una solución para variables según el contexto en Customer Journey Analytics.

| Nombre del filtro | Descripción |
| --- | --- |
| Todos los datos | Todos los datos es un filtro obligatorio que se añade dinámicamente a los informes cuando se agrega una métrica a la fila de una tabla de forma libre. |
