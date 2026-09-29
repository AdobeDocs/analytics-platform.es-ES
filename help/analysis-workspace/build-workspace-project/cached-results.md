---
title: Usar resultados en caché para una carga más rápida en Analysis Workspace
description: Habilite una configuración de proyecto en Analysis Workspace que almacene en caché los resultados de las consultas durante 12 horas para que los proyectos se carguen al instante. Actualice en cualquier momento para ver los datos más recientes.
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
source-git-commit: 6bcbf10e6bff660f57f598f6cf75b43eb75c7db3
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%
---

# Usar resultados en caché en proyectos de Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Usar resultados en caché para una carga más rápida"
>abstract="Cuando se habilita, los resultados se cargan más rápido durante 12 horas después de que un usuario abra un proyecto por primera vez o se envíe mediante una programación. Cualquiera que abra el proyecto durante ese tiempo verá los mismos resultados, aunque los datos sigan fluyendo en segundo plano. Para cargar los resultados más recientes, actualice paneles individuales o todo el proyecto."

Puede configurar proyectos de Analysis Workspace para que muestren los resultados en caché durante un periodo de 12 horas, lo que permite que los resultados se carguen instantáneamente para cualquiera que abra el proyecto después de cargarlo inicialmente.

Los proyectos los puede cargar inicialmente un usuario que abra el proyecto o una entrega de proyecto programada.

>[!NOTE]
>
>Solo se almacenan en caché los resultados de la consulta. Los datos de evento subyacentes siguen fluyendo a Customer Journey Analytics de la forma habitual.
>
>Para ver los datos más recientes antes de que los resultados en caché caduquen, puedes [actualizar manualmente los resultados](#manually-refresh-results-on-cached-projects).

## Comprender los resultados en caché de un proyecto

### Cuando los resultados se almacenan en caché

La primera vez que se ejecuta el proyecto, Analysis Workspace ejecuta la consulta de la forma habitual y almacena en caché los resultados para un periodo de 12 horas. Esto sucede cuando alguien abre el proyecto o cuando el proyecto se ejecuta para una entrega programada. Por ejemplo, si un proyecto está programado para su entrega a las 6:00 a.m., los resultados se almacenan en caché hasta las 6:00 p.m. Todos los que abren el proyecto entre las 6:00 AM y las 6:00 PM ven los resultados cargarse instantáneamente, incluso la primera persona en abrirlo.

Después de 12 horas, los resultados en caché caducan. La siguiente consulta del proyecto, independientemente de si un usuario lo abre o se ejecuta una entrega programada, se carga a velocidad normal e inicia un nuevo periodo de 12 horas.

### Quién puede ver los resultados en caché

Los resultados almacenados en caché se comparten con todas las personas que tienen acceso al proyecto y a las vistas de datos utilizadas en el proyecto.

### Qué resultados se almacenan en caché

Analysis Workspace almacena en caché cada consulta que se ejecuta, no todas las versiones posibles de un proyecto. Cuando alguien cambia la consulta, como al seleccionar un elemento del menú desplegable de un panel o al aplicar un segmento, Analysis Workspace ejecuta una nueva consulta. La nueva consulta se carga a velocidad normal la primera vez. Después, sus resultados también se almacenan en caché.

El almacenamiento en caché de una nueva consulta no sobrescribe ni invalida los resultados que ya se han almacenado en caché. La vista del proyecto original se almacena en caché junto con otras variaciones que se han ejecutado.

>[!BEGINSHADEBOX]

**Ejemplo de escenario**

Supongamos que un proyecto de Rendimiento de campaña global incluye segmentos para diferentes regiones y está programado para su envío a las 6:00 a. m.:

| Fecha | Acción | Velocidad de carga |
| --- | --- | --- |
| 6:00 | Entrega programada del proyecto | Normal (los resultados se almacenan en caché para su uso futuro) |
| 07:06 | El usuario A abre el proyecto | Rápido |
| 07:06 | El usuario A aplica el segmento de América | Normal (los resultados se almacenan en caché para su uso futuro) |
| 08:01 | El usuario B abre el proyecto | Rápido |
| 08:01 | El usuario B aplica el segmento de América | Rápido |
| 08:01 | El usuario B aplica el segmento EMEA | Normal (los resultados se almacenan en caché para su uso futuro) |

>[!ENDSHADEBOX]

## Habilitar los resultados en caché de un proyecto

Cualquier persona que pueda actualizar la configuración del proyecto puede habilitar los resultados en caché. Esto incluye al propietario del proyecto y a todas las personas que tengan la función **[!UICONTROL Editar original]** para el proyecto. Para obtener más información acerca de las funciones de proyecto, vea [Compartir una función de proyecto específica](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

En el proyecto de Workspace en el que desea habilitar los resultados en caché para una carga más rápida:

1. Vaya a **[!UICONTROL Proyectos]** > **[!UICONTROL Información y configuración del proyecto]**.
1. Seleccione **[!UICONTROL Usar resultados en caché para una carga más rápida]**.
1. Seleccione **[!UICONTROL Guardar]**.

## Ver marcas de tiempo de datos en proyectos en caché

Cuando se configura un proyecto para que utilice resultados almacenados en caché, se muestra una marca de tiempo en la parte superior del proyecto que indica cuándo se almacenaron los resultados en caché:

* **[!UICONTROL Mostrando datos de] [_fecha y hora_]**: todos los paneles del proyecto muestran los resultados en la caché a partir de la fecha y la hora mostradas.
* **[!UICONTROL Mostrando algunos datos de] [_fecha y hora_]**: algunos paneles muestran resultados en caché de la fecha y la hora mostradas, mientras que otros se actualizaron más recientemente.

Los paneles también muestran una marca de hora, que indica cuándo se almacenaron los resultados en caché:

* **[!UICONTROL Mostrando datos de] [_fecha y hora_]**: el panel muestra los resultados en caché de la fecha y la hora mostradas.

## Actualizar manualmente los resultados de los proyectos en caché

Puede actualizar manualmente los resultados de un proyecto en cualquier momento durante la ventana de 12 horas para ver los datos más recientes. Cuando se actualiza todo el proyecto, comienza una nueva ventana de 12 horas y todos los que abran el proyecto durante esa ventana verán los resultados actualizados.

En el proyecto de Workspace en el que desee ver los datos más recientes, puede actualizar los resultados de todo el proyecto o de un solo panel.

### Actualizar los resultados de todo el proyecto

Para cargar los resultados más recientes de todos los paneles e iniciar una nueva ventana de 12 horas:

1. Seleccione **[!UICONTROL Actualizar]** en la parte superior del proyecto junto a la marca de tiempo del proyecto.

### Actualizar los resultados de un solo panel

>[!NOTE]
>
>Esta opción no está disponible durante la fase alfa de lanzamiento.

Para cargar los resultados más recientes para un solo panel:

1. Seleccione **[!UICONTROL Actualizar]** junto a la marca de tiempo de un panel.

