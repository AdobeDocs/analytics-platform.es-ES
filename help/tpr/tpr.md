---
title: Total de informes de población
description: Utilice los informes de población total en Customer Journey Analytics para analizar perfiles y cuentas en sus conjuntos de datos, independientemente de la actividad de evento o los intervalos de fechas del panel.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: f7bbbaf0b737ab33088c7c585d6415f93deff4c8
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---

# Total de informes de población

La creación de informes de población total introduce la capacidad de analizar entidades definidas en conjuntos de datos de perfil y búsqueda, y crear informes sobre ellas, además de series de eventos basadas en el tiempo procedentes de conjuntos de datos de evento. Esta capacidad habilita nuevas clases de consultas, métricas y definiciones de audiencia que reflejan el ámbito completo de la base de clientes de una empresa.

Customer Journey Analytics se basa en eventos. Cada métrica, cada visualización, cada panel y cada informe se anclan a un intervalo de fecha y hora y a los eventos que se producen durante ese intervalo de fecha y hora. Hace preguntas a las soluciones como:

| Pregunta | Evento | Intervalo de fecha y hora |
|---|---|---|
| ¿Cuántas personas realizaron una compra la semana pasada? | compra | semana pasada |
| ¿Cuántas cuentas visitaron la página de precios en el primer trimestre? | visita | T1 |

El intervalo de fecha y hora del panel del espacio de trabajo filtra los datos, y las dimensiones y métricas describen lo que ha sucedido durante ese intervalo de fecha y hora.

Pero no todas las preguntas que su empresa necesita responder son sobre algo que sucedió. A veces necesitas saber sobre tu propia población.

| Pregunta | Evento | Intervalo de fecha y hora |
|---|---|---|
| ¿Cuántos clientes activos tenemos en este momento? | N/D | N/D |
| ¿Cuántas cuentas hay en nuestra base de datos? | N/D | N/D |
| ¿Cuántos de nuestros miembros no han hecho una compra en los últimos 30 días? | n/a | últimos 30 días |

Estas preguntas no son sobre eventos, sino sobre personas y cuentas que existen, hayan hecho o no algo recientemente.

Los informes de población total presentan una nueva clase de métricas que informan sobre los datos de perfil. Estos datos de perfil, que pueden contener personas y cuentas, en los conjuntos de datos de perfil son independientes del intervalo de fechas de un panel. Con los informes de población total, puede combinar métricas basadas en población y métricas basadas en eventos en el mismo análisis, lo que proporciona una imagen más completa de quiénes son sus clientes y qué han hecho.

La creación de informes de población total permite a Customer Journey Analytics crear informes sobre todas las entidades definidas en los conjuntos de datos de perfil y búsqueda, independientemente de la actividad de evento. Este informe incluye:

* **Consultas basadas en perfiles**: Analice atributos (independientemente de los eventos) de perfiles (todas las personas, cuentas, oportunidades y grupos de compra).
* **Perfil menos consultas de eventos**: identifique perfiles (todas las personas, cuentas, oportunidades y grupos de compras) que no realizaron una acción o experiencia específica durante la ventana de informes.
* **Búsquedas compartidas**: Admite la reutilización de conjuntos de datos de búsqueda en varias entidades para reducir los costos de ingesta y mejorar el rendimiento.

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## Total de métricas de informes de población

Las métricas de informes de población total se comportan de forma diferente a las métricas que se usan normalmente en Customer Journey Analytics:

* Las métricas de informes de población totales no están enlazadas al intervalo de fechas del panel. Una métrica de informes de población total como **[!UICONTROL Personas totales (Perfil)]** devuelve la población actual de su conjunto de datos de perfil, independientemente del intervalo de fechas aplicado al panel. Los filtros de fecha y las comparaciones de intervalos de fechas no afectan a las métricas de los informes de población total de la misma manera que estos filtros y comparaciones afectan a las métricas de evento.
* Los informes de población total requieren un conjunto de datos de perfil en la conexión. Las métricas de informes de población total solo aparecen cuando la conexión incluye al menos un conjunto de datos de perfil junto con al menos un conjunto de datos de evento. Las conexiones con solo conjuntos de datos de evento siguen funcionando exactamente como antes y no muestran las métricas de informes de población total.

En Workspace, las métricas de población total se marcan con un icono distinto (TBD) para que pueda identificar rápidamente qué métricas respetan el intervalo de fechas del panel y qué métricas no. Las métricas de población total se pueden usar junto con las métricas de evento en la mayoría de los lugares, pero no se admiten los tipos de visualización que dependen de secuencias de evento (como Visitas en el orden previsto y Flujo).

### Métricas estándar de informes de población total

De forma predeterminada, el sistema incluye tres métricas de informes de población total estándar, disponibles en cualquier vista de datos cuya conexión incluya un conjunto de datos de perfil:

* **Total de personas (perfil)**: el recuento total de personas en el conjunto de datos de perfil.
* **Cuentas totales (perfil)**: el recuento total de cuentas en el conjunto de datos de perfil. [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **Total de personas (perfil + evento)**: un recuento de uniones que combina personas con ámbito de perfil con personas con ámbito de evento.

También puede crear métricas personalizadas con cualquiera de los tres ámbitos, utilizando campos de los conjuntos de datos de perfil.

## Requisitos, requisitos previos y consideraciones

Para que los informes de población total funcionen correctamente, se deben tener en cuenta los requisitos previos, los requisitos y las consideraciones.

### Requisitos de conexión

Para que una conexión admita la creación de informes de población total:

* Se requiere al menos un conjunto de datos de evento para la conexión. No se admiten conexiones solo de perfil.
* Se debe agregar al menos un conjunto de datos de perfil a la conexión. Las métricas de informes de población total no aparecen en las vistas de datos creadas en conexiones que solo contienen datos de evento.
* Las búsquedas compartidas deben configurarse para cada conjunto de datos de perfil. Las búsquedas compartidas definen cómo se une cada conjunto de datos de perfil a los eventos de la conexión especificando la clave coincidente, el área de nombres (para campos de mapa de identidad) y la ruta de unión.

#### Configuración del conjunto de datos del perfil

Cuando se agrega un conjunto de datos de perfil a una conexión, Customer Journey Analytics rellena una configuración de búsqueda compartida predeterminada basada en el tipo de conjunto de datos:

* Para conjuntos de datos de perfil de persona: el valor predeterminado es coincidencia por contenedor establecido en [!UICONTROL Persona], con el mapa de identidad como campo de clave. Puede editar este valor predeterminado. Por ejemplo, para elegir un área de nombres específica del mapa de identidad en lugar de la clave principal. O para especificar un área de nombres secundaria en los casos en los que no se rellena el primer área de nombres (lo que es común en los conjuntos de datos enlazados).
* Para los conjuntos de datos de perfil de cuenta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: el valor predeterminado es coincidencia por contenedor establecido en [!UICONTROL Cuenta] (o [!UICONTROL Cuenta global], si las cuentas globales están habilitadas en la conexión). El campo de cuenta puede ser un identificador único o un mapa de identidad. Cuando el campo de cuenta es un mapa de identidad, se selecciona el área de nombres que se utilizará.

Puede configurar varias búsquedas compartidas en un único conjunto de datos de perfil para admitir varias rutas de unión a los eventos. Cuando se utiliza el mismo mapa de identidad como campo clave en varias búsquedas compartidas, las selecciones del área de nombres deben ser coherentes.

### Requisitos de vista de datos

Para que las métricas de informes de población totales funcionen correctamente en una vista de datos:

* La conexión debe incluir un conjunto de datos de perfil (consulte [Requisitos de conexión](#connection-requirements)). Si elimina el último conjunto de datos de perfil restante de una conexión, las métricas de creación de informes de población total no estarán disponibles en las vistas de datos creadas a partir de él.
* [Los segmentos del nivel de vista de datos](/help/data-views/create-dataview.md#settings-segments) no deben ser explícitos en cuanto a eventos. Si un segmento aplicado directamente a la vista de datos se define completamente en términos de condiciones con alcance de evento (por ejemplo, `hit where page = X`), no es posible realizar informes de población total en esa vista de datos. Antes de depender de las métricas de creación de informes de población total, compruebe que cualquier segmento del nivel de vista de datos sea compatible con la creación de informes con alcance de perfil.
* El ámbito de la métrica debe configurarse correctamente. Al crear un componente de métrica personalizado en el generador de vista de datos, seleccione el ámbito adecuado (evento, perfil o perfil + evento) en función del conjunto de datos del campo y de cómo desea que se comporte la métrica. El ámbito no se puede cambiar una vez que la métrica se ha utilizado en audiencias o informes recurrentes sin romper esas dependencias.

### Compatibilidad con Workspace

Las métricas de informes de población total se pueden usar junto con las métricas basadas en eventos en la mayoría de los contextos de Workspace: [tablas de forma libre](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), [visualizaciones de líneas](/help/analysis-workspace/visualizations/line.md), [barras](/help/analysis-workspace/visualizations/bar.md) y [barras horizontales](/help/analysis-workspace/visualizations/horizontal-bar.md), [tablas de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) cuando están configuradas correctamente, etc. Algunos tipos de visualización no son compatibles porque dependen inherentemente de secuencias de eventos:

* [Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md)
* tipos de visualización adicionales no compatibles que se confirmarán antes de la publicación.

Cuando se agrega una métrica de informes de población total a una visualización no admitida, Workspace indica que la métrica no se puede usar en ese contexto.

### Consideraciones de audiencia

Las audiencias creadas en las métricas de informes de población total dependen de las métricas que permanecen presentes en la vista de datos:

* Una audiencia recurrente que utiliza una métrica de informes de población total falla y pasa a un estado ERROR si la métrica de informes de población total se elimina de la vista de datos.
* La interfaz de Customer Journey Analytics evita la eliminación de una métrica, mientras que cualquier audiencia recurrente activa depende de la métrica y muestra instrucciones sobre la dependencia antes de confirmar la eliminación.

### Permisos

Por confirmar: cualquier requisito de acceso a funciones o roles en la organización IMS o el perfil de producto del cliente antes de que las métricas de informes de población totales sean visibles. Vale la pena marcar PM antes de la publicación.
