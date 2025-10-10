---
title: Información general sobre la segmentación
description: Conozca para qué sirven los segmentos y cómo crear un segmento simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 100%

---


# Información general sobre la segmentación

Customer Journey Analytics le permite crear, administrar, compartir y aplicar segmentos del público potentes y centrados en sus informes. Los segmentos le permiten identificar subconjuntos de personas, sesiones o eventos basándose en las características o en las interacciones. Los segmentos están diseñados como información del público codificada que puede crear de acuerdo con sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo.

Los segmentos se pueden basar en lo siguiente:

- atributos (tipo de explorador, dispositivo, número de visitas, país, género),
- interacciones (campañas, búsqueda de palabras clave, motor de búsqueda),
- salidas y entradas (personas de Facebook, una página de aterrizaje definida, un dominio de referencia, evento de perímetro),
- variables personalizadas (campo de formulario, categorías definidas, ID de cliente),
- y otros criterios.

Consulte [Crear segmentos](/help/components/segments/seg-create.md) para ver las distintas opciones disponibles para crear segmentos. A continuación, genere, modifique y guarde la definición de un segmento en el [Generador de segmentos](seg-builder.md). También puede crear segmentos rápidos con el [Generador de segmentos rápidos](seg-quick.md). Y también puede generar segmentos a partir de visualizaciones en Workspace, por ejemplo, usando la visualización de [Visitas en el orden previsto](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utilice el [Administrador de segmentos](seg-manage.md) para administrar segmentos.

## Planificación de los segmentos

En especial, como administrador, la correcta planificación de los segmentos mejora las posibilidades de que se utilicen. Tenga en cuenta lo siguiente a la hora de planificar segmentos:

- **Público**: ¿Quién utilizará sus segmentos? Asegúrese de suministrar una buena descripción del segmento para que el público comprenda lo siguiente:
   - ¿Para qué sirve este segmento?

   - ¿Cuándo debo utilizar este segmento?

- **Ámbito**: ¿qué [contenedor de segmento](#segment-containers) representa mejor los datos que busca? Utilice el contenedor más pequeño posible.

- **Componentes**: decida qué componentes incluirá en la definición del segmento y con qué valores deben validarse las condiciones.

- **Proceso**: tenga en cuenta un proceso de aprobación para sus segmentos. No hay ningún flujo de trabajo de aprobación en Customer Journey Analytics, pero aún puede organizar un proceso para determinar si aprueba o no un segmento.

- **Modularidad**: defina segmentos teniendo presente la modularidad. Los usuarios de sus segmentos deberían poder [apilar segmentos](seg-builder.md#stack-filters) fácilmente para crear nuevos segmentos potentes.


## Tipos de segmentos

Puede crear tres tipos de segmentos:

### Segmentos rápidos

Los segmentos rápidos permiten explorar fácilmente los datos de un proyecto de Workspace determinado, sin necesidad de crear un segmento en el [Generador de segmentos](/help/components/segments/seg-create.md). El segmento se define directamente en la interfaz de Workspace. Consulte [Segmentos rápidos](seg-quick.md) para obtener más información.

### Segmentos regulares

Los segmentos regulares permiten identificar datos (personas, sesiones, eventos) en función de una o varias condiciones. Si tiene más de una condición, utilice los operadores lógicos como And y Or para definir mejor el segmento. Puede utilizar contenedores para agrupar condiciones y generar segmentos más complejos. Consulte [Generador de segmentos](seg-builder.md) para obtener más información.

### Segmentos secuenciales

>[!IMPORTANT]
>
>Debe tener el paquete **Seleccionar** para crear segmentos secuenciales en canales múltiples. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

Los segmentos secuenciales le permiten identificar datos (personas, sesiones, eventos) en función de la navegación (vistas de página en su sitio, interacciones con escenas en su aplicación móvil o el uso de un menú en un cuadro de la parte superior). Los segmentos secuenciales le ayudan a identificar qué le gusta a una persona, así como lo que evita. El operador lógico Then se utiliza para definir un segmento secuencial. Consulte [Segmentos secuenciales](seg-sequential-build.md) para obtener más información.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Contenedores de segmentos {#containers}

Los segmentos se basan en una jerarquía a nivel de persona, sesión y evento usando un modelo de contenedor anidado. Los contenedores anidados le permiten definir condiciones entre los contenedores y dentro de ellos.


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
>Para los usuarios de Adobe Analytics:
> 
> - El contenedor **Persona** se conoce en Adobe Analytics como el contenedor **Visitante**.
> - El contenedor **Sesión** se conoce en Adobe Analytics como el contenedor **Visita**.
> - El contenedor **Evento** se conoce en Adobe Analytics como el contenedor **Acción**.
>

Un segmento establece las condiciones para segmentar las personas, las sesiones o los eventos en función de condiciones. Por ejemplo, las condiciones para segmentar las personas se basan en las características de la persona y los rasgos de navegación. Para desglosar aún más los datos, puede segmentar sesiones específicas, eventos de vista de página, pulsaciones en la pantalla, opciones de menú en un cuadro en la parte superior y mucho más. También puede segmentar atributos que haya introducido desde una CRM o un sistema de lealtad. El [Generador de segmentos](/help/components/segments/seg-builder.md) proporciona una interfaz simple para crear estos subconjuntos y aplicar condiciones en contenedores anidados, jerárquicos de Persona, de Sesión o Evento.

La arquitectura de contenedor empleada en el [Generador de segmentos](/help/components/segments/seg-builder.md) define Persona como el contenedor más externo. Este contenedor contiene datos generales específicos de la persona en sesiones y eventos como vistas de página, pantallas de aplicaciones móviles o pantallas de menú en un cuadro en la parte superior. Un contenedor Sesión anidado le permite establecer reglas para desglosar los datos de la persona en función de las sesiones. Un contenedor Evento anidado le permite desglosar la información de la persona en función de interacciones individuales. Cada contenedor le permite generar informes basados en el historial de una persona, las interacciones detalladas por sesiones o bien desglosar eventos individuales.

### Contenedor de persona

El contenedor Persona incluye cada sesión y cada evento para las personas que cumplen los requisitos para la condición especificada en el contenedor. Cuando define un segmento con una condición simple como `Page Name equals Checkout`, el contenedor Persona se resuelve como lo siguiente:

- Todas las personas que han visitado la página con el nombre `Checkout`.
- Todas las sesiones de estas personas.
- Todos los datos de evento de estas personas.

Al ser el contenedor con la definición más amplia, los informes generados en el nivel de contenedor Persona devuelven eventos y sesiones para todas las personas que cumplen los requisitos del segmento. Por tanto, el contenedor Persona es el más propenso a cambiar en función de intervalos de fechas definidos. 
Los contenedores de persona pueden incluir valores basados en el historial general de una persona:

- Días antes de la primera compra.
- Página de entrada original o pantalla de inicio de la aplicación móvil.
- Dominios de referencia originales.

### Contenedor de sesión

El contenedor Sesión le permite identificar interacciones con páginas o con aplicaciones móviles, campañas o conversiones para una sesión específica. El contenedor Sesión es el contenedor más utilizado, ya que captura los comportamientos de toda la sesión una vez cumplida la regla. El contenedor Sesión también le permite definir qué sesiones desea incluir o excluir al generar y aplicar un segmento.  Cuando define un segmento con una condición simple como `Page Name equals Checkout`, el contenedor Sesión responde se resuelve como:

- Todas las sesiones en las que se visitó una página con el nombre `Checkout`.
- Todos los datos de evento de esas sesiones.

El contenedor de sesión puede ayudarle a responder a las siguientes preguntas:

- ¿Cuántas sesiones incluyeron fuentes de datos tanto de la web como del centro de llamadas?
- ¿Qué páginas contribuyeron a una conversión exitosa para una venta?

Los contenedores de sesión incluyen valores basados en los eventos por sesión:

- Tipo de sesión.
- Página de entrada.
- Frecuencia de retorno.
- Métricas de participación.
- Métricas asignadas linealmente.

Las vistas de datos de Customer Journey Analytics le permiten determinar la duración de una sesión, pero también cuándo se debe crear una nueva. Por ejemplo, puede definir una nueva sesión de aplicación móvil basada en cada vez que un usuario inicia su aplicación móvil. Consulte [Configuración de sesiones](/help/data-views/session-settings.md) para obtener más información.

### Contenedor de evento

El contenedor Evento define qué página, aplicación móvil u otros tipos de eventos desea incluir o excluir de un segmento. Es el más estrecho de los contenedores disponibles. Permite identificar clics específicos, vistas de página y pulsaciones en botones en una aplicación móvil cuando se cumple una condición. El contenedor Evento le permite ver un único código de seguimiento o aislar un comportamiento en un área concreta de la aplicación móvil. También podría interesarle localizar un valor específico cuando se produzca una acción, como el canal de marketing cuando se formalice un pedido. Cuando define un segmento con una condición simple como `Page Name equals Checkout`, el contenedor Evento se resuelve como lo siguiente:

- Todos los eventos de vista de página donde el nombre de página es igual a `Checkout`.

Los contenedores de evento incluyen desgloses de una sola página basados en valores para lo siguiente:

- Productos
- props de lista
- Dimensiones de lista
- Dimensiones de comercialización (en el contexto de eventos)



### Contenedores B2B

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Si tiene acceso a [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md), encontrará contenedores adicionales disponibles para usarlos en segmentos. Puede encontrar más información sobre el uso de estos contenedores adicionales en [Conceptos y funciones de B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Contenedor de grupo lógico

El grupo lógico permite agrupar condiciones en un único punto de comprobación de segmento secuencial. Como parte de la secuencia, la lógica definida en el contenedor identificado como [!UICONTROL Grupo lógico] se evalúa después de cualquier punto de comprobación secuencial anterior y antes de cualquier punto de comprobación secuencial posterior. Consulte [Grupo lógico](seg-sequential-build.md#logic-group) para obtener más información.

### Anidar contenedores

Al crear contenedores de segmentos dentro de otros contenedores, básicamente está creando un segmento dentro de otro. La siguiente lógica se aplica a los contenedores anidados:

1. Determinar qué datos se incluyen utilizando el contenedor exterior. Los datos que no coincidan con esta regla exterior se descartarán en el informe.
2. Aplicar la definición de segmento anidado a los demás datos. La definición de segmento anidado no se aplica a ningún dato que la primera definición haya descartado.
3. Repetir hasta que se hayan calculado todas las definiciones de segmento de los contenedores anidados. Los datos restantes se incluirán en el resultado y se utilizarán para la creación de informes.

>[!NOTE]
>
>Cuando anida un segmento dentro de otro (por ejemplo, arrastra un segmento desde el panel Componentes hasta la definición del segmento), se crea un contenedor con una copia (no una referencia) de la definición del segmento arrastrado.

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
>[Creación de segmentos](seg-create.md)
>>[Generador de segmentos](seg-builder.md)
>>[Segmentos rápidos](seg-quick.md)
>>[Segmentos secuenciales](seg-sequential-build.md)
>>[Administración de segmentos](seg-manage.md)
