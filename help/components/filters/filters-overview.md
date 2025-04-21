---
title: Información general de segmentación
description: Comprenda para qué segmentos se utilizan y cómo crear un segmento simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 5%

---


# Información general de segmentación

Customer Journey Analytics le permite generar, administrar, compartir y aplicar a sus informes poderosos segmentos centrados en la audiencia. Los segmentos le permiten identificar subconjuntos de personas, sesiones o eventos según sus características o interacciones. Los segmentos están diseñados como análisis de audiencia codificados que puede crear para sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo.

Los segmentos se pueden basar en:

- atributos (tipo de explorador, dispositivo, número de visitas, país, sexo),
- interacciones (campañas, búsqueda de palabras clave, motor de búsqueda),
- salidas y entradas (personas de Facebook, una página de aterrizaje definida, dominio de referencia, evento de geovalla),
- variables personalizadas (campo de formulario, categorías definidas, ID de cliente),
- y otros criterios.

Consulte [Crear segmentos](/help/components/filters/create-filters.md) para ver las distintas opciones disponibles para crear segmentos. A continuación, genere, modifique y guarde la definición de un segmento en el [Generador de segmentos](filter-builder.md). También puede crear segmentos rápidos con el [Generador de segmentos rápidos](quick-filters.md). Y también puede generar segmentos a partir de visualizaciones en Workspace, por ejemplo, usando la visualización de [Visitas en el orden previsto](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utiliza [Administrador de segmentos](manage-filters.md) para administrar segmentos.

## Planificar segmentos

En especial, como administrador, la correcta planificación de los segmentos mejora las posibilidades de que se utilicen. Tenga en cuenta lo siguiente al planificar los segmentos:

- **Audiencia**: ¿Quién usará sus segmentos? Asegúrese de proporcionar una buena descripción del segmento para que la audiencia entienda lo siguiente:
   - ¿Para qué sirve este segmento?

   - ¿Cuándo debo utilizar este segmento?

- **Ámbito**: ¿Qué [contenedor de segmento](#filter-containers) representa mejor los datos que busca? Utilice el contenedor más pequeño posible.

- **Componentes**: decida qué componentes incluirá en la definición del segmento y con qué valores se validarán las condiciones.

- **Proceso**: considere un proceso de aprobación para sus segmentos. No hay ningún flujo de trabajo de aprobación en Customer Journey Analytics, pero aún puede organizar un proceso para determinar si aprueba o no un segmento.

- **Modularidad**: defina segmentos con la modularidad en mente. Los usuarios de tus segmentos deberían poder [apilar segmentos](filter-builder.md#stack-filters) fácilmente para crear nuevos segmentos poderosos.


## Tipos de segmentos

Puede crear tres tipos de segmentos:

### Segmentos rápidos

Los segmentos rápidos le permiten explorar datos fácilmente dentro de un proyecto de Workspace determinado, sin necesidad de crear un segmento en el [Generador de segmentos](/help/components/filters/create-filters.md). El segmento se define directamente en la interfaz de Workspace. Consulte [Segmentos rápidos](quick-filters.md) para obtener más información.

### Segmentos regulares

Los segmentos regulares permiten identificar datos (personas, sesiones y eventos) en función de una o más condiciones. Si tiene más de una condición, utilice operadores lógicos como Y y O para definir el segmento más adelante. Puede utilizar contenedores para agrupar condiciones y generar segmentos más complejos. Consulte [Generador de segmentos](filter-builder.md) para obtener más información.

### Segmentos secuenciales

>[!IMPORTANT]
>
>Debe tener el paquete **Select** para crear segmentos secuenciales entre canales. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

Los segmentos secuenciales le permiten identificar datos (personas, sesiones y eventos) en función de la navegación (vistas de página de su sitio, interacciones con escenas en su aplicación móvil o el uso de un menú en un cuadro de la parte superior). Los segmentos secuenciales le ayudan a identificar, por ejemplo, qué le gusta a una persona y qué evita. El operador lógico Then se utiliza para definir un segmento secuencial. Consulte [Segmentos secuenciales](seg-sequential-build.md) para obtener más información.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Contenedores de segmentos {#containers}

Los segmentos se basan en una jerarquía de nivel persona, sesión y evento mediante un modelo de contenedor anidado. Los contenedores anidados le permiten definir condiciones entre los contenedores y dentro de ellos.


<table style="table-layout: fixed; border: none;" width="100%">

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
>
>Para usuarios de Adobe Analytics:
> 
> - El contenedor **Person** se conoce en Adobe Analytics como el contenedor **Visitor**.
> - El contenedor **Session** se conoce en Adobe Analytics como el contenedor **Visit**.
> - El contenedor **Event** se conoce en Adobe Analytics como el contenedor **Hit**.
>

Un segmento establece las condiciones necesarias para segmentar a las personas, las sesiones o los eventos en función de las condiciones. Por ejemplo, las condiciones para segmentar a las personas se basan en las características de la persona y los rasgos de navegación. Para desglosar aún más los datos, puede segmentar sesiones específicas, eventos de vista de página, toques de pantalla, opciones de menú en un cuadro en la parte superior y más. También puede segmentar atributos que haya introducido desde un CRM o un sistema de fidelidad. El [Generador de segmentos](/help/components/filters/filter-builder.md) proporciona una interfaz sencilla para generar estos subconjuntos y aplicar condiciones en contenedores anidados, jerárquicos, de persona, de sesión y de eventos.

La arquitectura de contenedor empleada en el [Generador de segmentos](/help/components/filters/filter-builder.md) define la persona como el contenedor exterior. Este contenedor contiene datos globales específicos de la persona en sesiones y eventos como vistas de página, pantallas de aplicaciones móviles o pantallas de menú en un cuadro en la parte superior. Un contenedor de sesión anidado le permite establecer reglas para desglosar los datos de la persona en función de las sesiones. Un contenedor de eventos anidado le permite desglosar la información de la persona en función de las interacciones individuales. Cada contenedor le permite realizar informes basados en el historial de una persona, en las interacciones detalladas por sesión o en el desglose de eventos individuales.

### Contenedor de persona

El contenedor Persona incluye cada sesión y cada evento para las personas que cumplen los requisitos para la condición especificada en el contenedor. Cuando define un segmento con una condición simple como `Page Name equals Checkout`, el contenedor de persona responde a:

- Todas las personas que han visitado la página con el nombre `Checkout`.
- Todas las sesiones de estas personas.
- Todos los datos de evento de estas personas.

Al ser el contenedor definido con mayor amplitud, los informes generados en el nivel del contenedor de persona devuelven eventos y sesiones para todas las personas aptas para el segmento. El contenedor Persona es el más susceptible de cambiar en función de intervalos de fechas definidos.
Los contenedores de persona pueden incluir valores basados en el historial general de una persona:

- Días antes de la primera compra.
- Página de entrada original o pantalla de inicio de la aplicación móvil.
- Dominios de referencia originales

### Contenedor de sesión

El contenedor Sesión le permite identificar interacciones de páginas o interacciones de aplicaciones móviles, campañas o conversiones para una sesión específica. El contenedor de sesión es el contenedor más utilizado, ya que captura los comportamientos de la sesión al completo cuando se cumple la regla. El contenedor Sesión también le permite definir qué sesiones desea incluir o excluir al generar y aplicar un segmento.  Cuando define un segmento con una condición simple como `Page Name equals Checkout`, el contenedor de sesión responde como:

- Todas las sesiones en las que se visitó una página con el nombre `Checkout`.
- Todos los datos de evento de esas sesiones.

El contenedor de sesión puede ayudarle a responder a las siguientes preguntas:

- ¿Cuántas sesiones incluyeron fuentes de datos web y de centros de llamadas?
- ¿Qué páginas contribuyeron a una conversión exitosa para una venta?

Los contenedores de sesión incluyen valores basados en eventos por sesión:

- Tipo de sesión.
- Página de entrada.
- Frecuencia de retorno.
- Métricas de participación.
- Métricas asignadas linealmente.

Las vistas de datos de Customer Journey Analytics le permiten determinar la duración de una sesión, pero también cuándo se debe crear una nueva. Por ejemplo, puede definir una nueva sesión de aplicación móvil basada en cada vez que un usuario inicie la aplicación móvil. Consulte [Configuración de sesión](/help/data-views/session-settings.md) para obtener más información.

### Contenedor de evento

El contenedor Evento define qué página, aplicación móvil u otro tipo de eventos desea incluir o excluir de un segmento. Es el más estrecho de los contenedores disponibles. Permite identificar clics específicos, vistas de página y toques en un botón de una aplicación móvil donde una condición es verdadera. El contenedor Evento le permite ver un único código de seguimiento o aislar un comportamiento en un área concreta de la aplicación móvil. También es posible que desee localizar un valor específico cuando se produzca una acción, como el canal de marketing cuando se realice un pedido. Cuando define un segmento con una condición simple como `Page Name equals Checkout`, el contenedor de evento se resuelve en:

- Todos los eventos de vista de página donde el nombre de página es igual a `Checkout`.

Los contenedores de evento incluyen desgloses de una sola página basados en valores para:

- Productos
- props de lista
- Dimensiones de lista
- Dimensiones de comercialización (en el contexto de eventos)


### Contenedor de grupo lógico

Grupo lógico le permite agrupar condiciones en un único punto de comprobación secuencial de segmento. Como parte de la secuencia, la lógica definida en el contenedor identificado como [!UICONTROL grupo lógico] se evalúa después de cualquier punto de comprobación secuencial anterior y antes de cualquier punto de comprobación secuencial siguiente. Consulte [Grupo lógico](seg-sequential-build.md#logic-group) para obtener más información.

### Anidar contenedores

Al crear contenedores dentro de otros contenedores, en realidad está creando un segmento dentro de otro segmento. La siguiente lógica se aplica a los contenedores anidados:

1. Determinar qué datos se incluyen utilizando el contenedor exterior. Los datos que no coincidan con esta regla exterior se descartarán en el informe.
2. Aplicar la definición de segmento anidada a los datos restantes. La definición de segmento anidada NO se aplica a ningún dato que la primera definición haya descartado.
3. Repita el proceso hasta que se hayan calculado todas las definiciones de segmentos de contenedores anidados. Los datos restantes se incluyen en el resultado y se utilizan para la creación de informes.

>[!NOTE]
>
>Cuando anida un segmento dentro de otro (por ejemplo, arrastra un segmento desde el panel Componentes a la definición del segmento), se crea un contenedor con una copia (no una referencia) de la definición del segmento arrastrado.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Crear segmentos](create-filters.md)
>[Generador de segmentos ](filter-builder.md)
>[Segmentos rápidos](quick-filters.md)
>[Segmentos secuenciales](seg-sequential-build.md)
>[Administrar segmentos](manage-filters.md)
>
