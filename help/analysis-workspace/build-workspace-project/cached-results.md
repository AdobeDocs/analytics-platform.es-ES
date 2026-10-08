---
title: Usar resultados en caché para una carga más rápida en Analysis Workspace
description: Habilite una configuración de proyecto en Analysis Workspace que almacene en caché los resultados durante 12 horas para que los proyectos se carguen al instante. Actualice en cualquier momento para ver los datos más recientes.
feature: Workspace Basics
hide: true
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 32dfb7790f57293ea297bdcb8319c3d3b187a2ae
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 5%
---

# Utilizar los resultados almacenados en caché en los proyectos de Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Utilizar los resultados almacenados en caché para una carga más rápida"
>abstract="Cuando se activa esta opción, los resultados se cargan instantáneamente durante doce horas después de que un usuario abra un proyecto por primera vez o se envíe mediante una programación. Cualquiera que abra el proyecto durante ese tiempo obtendrá los mismos resultados, aunque los datos sigan fluyendo en el fondo. Para cargar los resultados más recientes, actualice los paneles individuales o todo el proyecto."

{{release-limited-testing}}

Puede configurar proyectos de Analysis Workspace para que muestren los resultados en caché durante un periodo de 12 horas, lo que permite que los resultados se carguen instantáneamente para cualquiera que abra el proyecto después de cargarlo inicialmente.

Los proyectos los puede cargar inicialmente un usuario que abra el proyecto o una entrega de proyecto programada.

## Comprender los resultados en caché de un proyecto

### Cuando los resultados se almacenan en caché

La primera vez que se carga el proyecto, los resultados se cargan a velocidad normal y Analysis Workspace los almacena en caché durante un período de 12 horas. Esto sucede cuando:

* Alguien abre el proyecto

* El proyecto se ejecuta para un envío programado

Por ejemplo, si un proyecto está programado para su entrega a las 6:00 a.m., los resultados se almacenan en caché hasta las 6:00 p.m. Todos los que abren el proyecto entre las 6:00 AM y las 6:00 PM ven los resultados cargarse instantáneamente, incluso la primera persona en abrirlo.

Después de 12 horas, los resultados en caché caducan. La próxima vez que se cargue el proyecto, tanto si un usuario lo abre como si se ejecuta una entrega programada, los resultados se cargarán a la velocidad normal y se iniciará un nuevo período de 12 horas.

### Qué resultados se almacenan en caché

#### El proyecto se almacena inicialmente en caché con su configuración original

Analysis Workspace almacena en caché los resultados del proyecto tal como estaban configurados originalmente, con sus vistas de datos seleccionadas, segmentos aplicados, intervalos de fechas, selecciones desplegables de panel, etc. Todos los que abren el proyecto ven estos resultados en la caché.

Si alguien cambia la configuración del proyecto mientras ve el proyecto en caché, los resultados se cargarán normalmente (no de forma instantánea) y [se almacenará en caché una nueva variación del proyecto](#project-variations-are-cached-as-the-project-is-modified).

#### Las variaciones de proyecto se almacenan en caché a medida que se modifica el proyecto

Se crea una nueva variación del proyecto cuando alguien cambia su configuración original, como seleccionando un elemento del menú desplegable de un panel, aplicando un segmento, cambiando un intervalo de fechas o cambiando la vista de datos seleccionada.

Una nueva variación carga a velocidad normal la primera vez. Después, sus resultados también se almacenan en caché, por lo que cualquier persona que cargue la misma variación verá los resultados instantáneamente.

Tenga en cuenta lo siguiente:

* Analysis Workspace almacena en caché cada variación de un proyecto que alguien carga. No almacena en caché todas las variaciones posibles de un proyecto.

* El almacenamiento en caché de una nueva variación no sobrescribe ni invalida los resultados que ya se han almacenado en caché. El proyecto original se almacena en caché junto con otras variaciones que las personas han cargado.

>[!BEGINSHADEBOX]

**Ejemplo de escenario**

Supongamos que un proyecto de Rendimiento de campaña global incluye segmentos para diferentes regiones y está programado para su envío a las 6:00 a. m.:

| Fecha | Acción | Velocidad de carga |
| --- | --- | --- |
| 6:00 | Entrega programada del proyecto | Normal (los resultados se almacenan en caché para su uso futuro) |
| 07:06 | El usuario A abre el proyecto | Instantáneo |
| 07:07 | El usuario A aplica el segmento de América | Normal (los resultados se almacenan en caché para su uso futuro) |
| 08:01 | El usuario B abre el proyecto | Instantáneo |
| 08:05 | El usuario B aplica el segmento de América | Instantáneo |
| 08:12 | El usuario B aplica el segmento EMEA | Normal (los resultados se almacenan en caché para su uso futuro) |

>[!ENDSHADEBOX]

### Cambios que hacen que los resultados en caché se actualicen con la siguiente carga de proyecto

Los siguientes cambios en la configuración subyacente de un proyecto hacen que Analysis Workspace actualice los resultados la próxima vez que alguien abra el proyecto, incluso si la ventana de 12 horas no ha caducado:

* Cambios en un componente de la vista de datos, como editar la configuración de [componentes](/help/data-views/component-settings/overview.md) de una dimensión o métrica

* Cambios en un [campo derivado](/help/data-views/derived-fields/derived-fields.md)

* Cambios en la definición de un segmento utilizada en el proyecto

Los resultados se cargan a velocidad normal y se almacenan en caché, lo que inicia un nuevo período de 12 horas.

### Quién ve los resultados en caché

Los resultados en caché se muestran de forma predeterminada para todas las personas que:

* Tiene acceso al proyecto

* Tiene acceso a las vistas de datos utilizadas en el proyecto

* Está cargando una variación del proyecto que ya se ha almacenado en caché, como una que tiene los mismos segmentos o selecciones desplegables de panel (para obtener más información, consulte [Qué resultados se almacenan en caché](#what-results-are-cached))

Al ver los resultados en caché, puede ver los datos más recientes [actualizando manualmente los resultados](#manually-refresh-results-on-cached-projects).

### Cuándo dejar los resultados en caché deshabilitados en un proyecto

Algunos proyectos dependen de los resultados para reflejar los datos más recientes cada vez que alguien los abra. Esto es común en proyectos que dependen en gran medida de datos del mismo día, datos que llegan tarde o [conjuntos de datos de búsqueda](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) que se actualizan con frecuencia.

Deje los resultados en caché deshabilitados en el proyecto si la mayoría de las personas que acceden a él necesitan ver:

* **Datos del día actual**

  Si un proyecto se almacena en caché a las 7:00 a. m., los resultados no incluyen los datos que llegan después de las 7:00 a. m. hasta que los resultados en caché caducan a las 7:00 p. m.

* **Datos que llegan tarde**

  Los datos que llegan tarde tienen marcas de tiempo de un período de tiempo anterior, pero llegan después de que haya pasado ese período. Por ejemplo, [los datos por lotes](/help/data-ingestion/batch.md) de un centro de llamadas podrían cargarse al día siguiente, o una aplicación móvil podría enviar eventos que haya almacenado sin conexión. Los resultados en caché no incluyen estos datos hasta que caducan.

* **Valores de búsqueda actualizados**

  Los resultados en caché siguen mostrando los valores de búsqueda anteriores, como los nombres de productos antiguos, hasta que caducan.

>[!NOTE]
>
>Si estas necesidades aparecen solo ocasionalmente, habilite los resultados en caché y [actualice el proyecto manualmente](#manually-refresh-results-on-cached-projects) cuando necesite los datos más recientes.

## Habilitar los resultados en caché de un proyecto

Cualquier persona que pueda actualizar la configuración del proyecto puede habilitar los resultados en caché. Esto incluye al propietario del proyecto y a todas las personas que tengan la función **[!UICONTROL Editar original]** para el proyecto. Para obtener más información acerca de las funciones de proyecto, vea [Compartir una función de proyecto específica](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>Es posible que los resultados en caché no sean adecuados si necesita ver los datos del día actual, los datos que llegan tarde o los valores de búsqueda actualizados de inmediato. Antes de habilitar esta configuración, revise [Cuándo dejar deshabilitados los resultados en caché en un proyecto](#when-to-leave-cached-results-disabled-on-a-project).

En el proyecto de Workspace en el que desea habilitar los resultados en caché para una carga más rápida:

1. Vaya a **[!UICONTROL Proyectos]** > **[!UICONTROL Información y configuración del proyecto]**.

1. Seleccione **[!UICONTROL Usar resultados en caché para una carga más rápida]**.

1. Seleccione **[!UICONTROL Guardar]**.

## Ver cuándo se muestran los resultados en caché en un proyecto

Se muestra una marca de tiempo en la parte superior del proyecto cuando se muestran los resultados en caché. La marca de tiempo especifica si todos los resultados se almacenan en caché o solo algunos resultados:

* **[!UICONTROL Mostrando resultados de] [_fecha y hora_]**: todos los paneles del proyecto muestran los resultados en la caché a partir de la fecha y la hora mostradas.

* **[!UICONTROL Mostrando algunos resultados de] [_fecha y hora_]**: algunos paneles muestran resultados en caché de la fecha y la hora mostradas, mientras que otros se actualizaron más recientemente.

![Marca de tiempo en el proyecto almacenado en caché](assets/project-cache-timestamp.png)

Los paneles también muestran una marca de hora, que indica cuándo se almacenaron los resultados en caché:

* **[!UICONTROL Mostrando resultados de] [_fecha y hora_]**: el panel muestra los resultados en caché de la fecha y la hora mostradas.

  >[!NOTE]
  >
  >Esta opción no está disponible durante la fase alfa de lanzamiento.

## Actualizar manualmente los resultados de los proyectos en caché

Solo se almacenan en caché los resultados que se muestran en el proyecto. Los datos de evento subyacentes siguen fluyendo a Customer Journey Analytics de la forma habitual.

Para ver los datos más recientes antes de que los resultados en caché caduquen, puede actualizar manualmente los resultados de un proyecto en cualquier momento durante el período de 12 horas. Cuando se actualiza todo el proyecto, comienza una nueva ventana de 12 horas y todos los que abran el proyecto durante esa ventana verán los resultados actualizados.

En el proyecto de Workspace en el que desee ver los datos más recientes, puede actualizar los resultados de todo el proyecto o de un solo panel.

### Actualizar los resultados de todo el proyecto

Para cargar los resultados más recientes de todos los paneles e iniciar una nueva ventana de 12 horas:

1. Seleccione el icono **[!UICONTROL Actualizar]** ![Actualizar](/help/assets/icons/Refresh.svg) en la parte superior del proyecto junto a la marca de tiempo del proyecto.

### Actualizar los resultados de un solo panel

>[!NOTE]
>
>Esta opción no está disponible durante la fase alfa de lanzamiento.

Para cargar los resultados más recientes para un solo panel:

1. Seleccione el icono **[!UICONTROL Actualizar]** ![Actualizar](/help/assets/icons/Refresh.svg) junto a la marca de tiempo de un panel.

