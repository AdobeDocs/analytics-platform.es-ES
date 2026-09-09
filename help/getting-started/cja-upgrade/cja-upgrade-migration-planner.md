---
title: Migración de AppMeasurement o etiquetas a XDM
description: Obtenga información acerca de la migración de AppMeasurement o etiquetas a XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: db34e721f156b3eb0aab20b2dca57e194c83d6fb
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 5%

---

# Migración de etiquetas a XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="Resumen de migraciones"
>abstract="Migre una implementación de etiquetas a Adobe Experience Platform Web SDK al actualizar a Customer Journey Analytics.<br/>Continúe con una migración existente o inicie una nueva."

<!-- markdownlint-enable MD034 -->

El planificador de migración proporciona un asistente de migración que automatiza la migración de etiquetas a XDM, incluida la creación de esquemas. Estas son algunas de las tareas más complejas y laboriosas asociadas con una actualización de Adobe Analytics a Customer Journey Analytics.

## Implementaciones de Adobe Analytics compatibles

El planificador de migración es compatible con las implementaciones de Adobe Analytics que utilizan la extensión de Analytics (etiquetas).

El Planificador de migración no está disponible para implementaciones de Adobe Analytics que utilicen AppMeasurement o Experience Platform Web SDK.

## Actualizar tareas incluidas en el planificador de migración

El planificador de migración proporciona un asistente de migración que automatiza las siguientes tareas de actualización complejas y laboriosas:

* **Creación de esquema XDM**: Crea automáticamente un nuevo esquema XDM basado en las variables del grupo de informes de Adobe Analytics. El planificador de migración analiza de forma inteligente las variables del grupo de informes de Adobe Analytics y, a continuación, utiliza esa información para crear los campos necesarios en XDM. El esquema XDM resultante incluye solo los campos necesarios en el esquema de Customer Journey Analytics.

  También puede apuntar a un esquema XDM existente o puede crear un esquema XDM desde cero.

  +++ Si decide crear un esquema XDM desde cero, puede ampliar esta sección para obtener información sobre recursos útiles.

  * [Planifique la arquitectura de su esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

  * [Cree su esquema personalizado deseado en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

    Tenga en cuenta las siguientes opciones al crear el esquema:

    * Si desea integrar Customer Journey Analytics con RTCDP, debe habilitar la opción **[!UICONTROL Perfil]** en su esquema, tal como se describe en [Creación de un esquema XDM para utilizarlo con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}. Con esta opción habilitada, cuando los datos se introducen en conjuntos de datos basados en este esquema, los datos se combinan con el perfil del cliente en tiempo real.

    * Si desea incluir datos de medios de streaming, debe [configurar su esquema para ingerir y utilizar datos de streaming](/help/data-ingestion/streaming.md){target="_blank"}.

    +++

  * **Migración de su implementación de Adobe Analytics a Web SDK**: Ya sea que su implementación de Adobe Analytics utilice etiquetas o JavaScript, el planificador de migración le guiará a través de la migración a Experience Platform Web SDK.

    * **Migrar propiedades de etiquetas de AppMeasurement a Web SDK**:

    * **Migrar una implementación de JavaScript de AppMeasurement a la biblioteca de JavaScript de Web SDK**

  * **Creación de vistas de datos en Customer Journey Analytics**: crea automáticamente vistas de datos y las rellena con componentes, según los campos de esquema XDM que se creen.


## Antes de empezar

Antes de crear una migración, asegúrese de que dispone de lo siguiente:

* Una implementación de Adobe Analytics compatible (la extensión de Analytics para etiquetas). Consulte [Implementaciones de Adobe Analytics compatibles](#supported-adobe-analytics-implementations).

* Acceda a la propiedad de etiquetas de Adobe que desee migrar, en la organización de Experience Cloud en la que ha iniciado sesión.

* Acceso al grupo de informes de Adobe Analytics cuyas variables desea asignar a XDM.

* Permiso para crear esquemas en Adobe Experience Platform.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Migración de una implementación de Analytics a Web SDK

Una migración avanza por tres etapas: [!UICONTROL **Auditoría**], [!UICONTROL **Asignación**] y [!UICONTROL **Implementación**]. Siga los siguientes pasos para crear una migración y, a continuación, continúe con [Validar e implementar una migración](#validate-and-deploy-a-migration) para completar cada etapa.

1. En Customer Journey Analytics, abra el [!UICONTROL **Planificador de migración**].

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. En el Planificador de migración, en la ficha [!UICONTROL **Migraciones**], seleccione [!UICONTROL **Nuevo**].

   ![Cuadro de diálogo Nueva migración, donde elige un tipo de migración e introduce un nombre de migración.](assets/migration-planner-new-migration.png)

1. Especifique la siguiente información:

   | Nombre de campo | Función |
   | --------- | ---------- |
   | [!UICONTROL **Nombre**] | Especifique un nombre para esta migración. |
   | [!UICONTROL **Descripción**] | Especifique una descripción opcional para esta migración. |
   | [!UICONTROL **Propiedad de etiquetas**] | Seleccione la propiedad Etiquetas de Adobe que desee migrar. Para obtener más información, consulte [Propiedades](https://experienceleague.adobe.com/es/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"} en la documentación de Experience Platform. |
   | [!UICONTROL **Biblioteca de etiquetas**] | Seleccione la instantánea de la biblioteca de etiquetas en la que se basa la migración. La instantánea determina qué versión de la biblioteca de etiquetas se utiliza. Para obtener más información, consulte [Información general de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview){target="_blank"} en la documentación de Experience Platform. |

1. En el campo [!UICONTROL **Nombre de la migración**], especifique un nombre para esta migración y luego seleccione [!UICONTROL **Siguiente**].

1. Seleccione la propiedad de etiquetas que desee migrar y, a continuación, seleccione [!UICONTROL **Siguiente**].

   Solo aparecen las propiedades de etiquetas disponibles para la organización de Experience Cloud que ha iniciado sesión.

1. Seleccione la instantánea de la biblioteca de etiquetas que desee migrar y, a continuación, seleccione [!UICONTROL **Siguiente**].

   La instantánea determina en qué versión de la biblioteca de etiquetas se basa la migración. Cada instantánea muestra su entorno (como [!UICONTROL **Development**], [!UICONTROL **Staging**] o [!UICONTROL **Production**]).

1. Seleccione el conjunto de asignaciones para determinar cómo se asignarán las variables de Analytics a los campos de esquema XDM.

   Realice cualquiera de los siguientes pasos:

   * Seleccione [!UICONTROL **Crear un nuevo conjunto de asignaciones**].

   * Seleccione un conjunto de asignaciones existente.

     Los conjuntos de asignaciones que se crearon durante una migración anterior o como un conjunto de asignaciones independiente están disponibles para su selección.

     La reutilización de un conjunto de asignaciones en varias migraciones aplica las mismas asignaciones a cada migración.

1. Seleccione [!UICONTROL **Crear migración**].

1. Continúe con la siguiente sección: [Validar e implementar una migración](#validate-and-deploy-a-migration).

## Validación e implementación de una migración

Después de crear una migración, ábrala para completar sus tres fases: [!UICONTROL **Auditoría**], [!UICONTROL **Asignación**] y [!UICONTROL **Implementación**].

1. En el Planificador de migración, seleccione la ficha [!UICONTROL **Migraciones**].

1. Junto a la migración que desea validar, seleccione [!UICONTROL **Abrir**].

   La página de información general de migración muestra las tres etapas que se deben completar, junto con un resumen de la migración y sus artefactos.

   ![La página de información general de migración con las tarjetas de fase de auditoría, asignación e implementación.](assets/migration-planner-overview.png)

1. Complete la fase [!UICONTROL **Auditoría**]:

   1. En la tarjeta de auditoría ([!UICONTROL **Auditoría de extensiones de etiquetas**] o [!UICONTROL **Auditoría de JavaScript**], según el tipo de migración), seleccione [!UICONTROL **Iniciar auditoría**] para revisar las reglas y los elementos de datos incluidos en la migración.

      ![La página de auditoría, donde se seleccionan reglas y elementos de datos y se resuelven los resultados.](assets/migration-planner-audit.png)

   1. En las pestañas [!UICONTROL **Reglas**] y [!UICONTROL **Elementos de datos**], seleccione los elementos que desea incluir en la migración.

      Las reglas marcadas [!UICONTROL **en la biblioteca**] se han publicado. Las reglas marcadas como [!UICONTROL **Propiedad solamente**] existen en la propiedad pero no forman parte de la biblioteca seleccionada.

   1. Revise los resultados de las reglas seleccionadas. Para cada hallazgo, seleccione [!UICONTROL **Revisar**] para resolverlo o [!UICONTROL **Ignorar**] para dejarlo sin dirección.

      Por ejemplo, cuando dos reglas tienen eventos y condiciones idénticos, la búsqueda de [!UICONTROL **Duplicar eventos de regla**] le permite mantener una regla y eliminar la otra, o seleccionar [!UICONTROL **No hacer nada**] para confirmar la búsqueda sin realizar ningún cambio.

      La resolución de los hallazgos es opcional antes de continuar. Para obtener la lista completa de tipos de resultados y cómo resolverlos, vea [Revisar y resolver resultados de auditoría](#review-and-resolve-audit-findings).

   1. Seleccione [!UICONTROL **Guardar y continuar**].

1. Complete la fase [!UICONTROL **Asignación**]:

   1. En la tarjeta [!UICONTROL **Asignación XDM de Analytics →**], seleccione [!UICONTROL **Crear nueva asignación**].

   1. Elija si desea crear un nuevo esquema basado en las variables de Analytics o asignarlo a un esquema de Experience Platform existente. A continuación, siga las indicaciones para seleccionar el grupo de informes, asignar campos y revisar el esquema.

      Para ver los pasos detallados, consulte [Asignar variables de Analytics a campos XDM](#map-analytics-variables-to-xdm-fields). Para reutilizar un conjunto de asignaciones entre migraciones, consulte [Crear y administrar conjuntos de asignaciones](#create-and-manage-mapping-sets).

1. Complete la fase [!UICONTROL **Implementación**]:

   1. En la tarjeta [!UICONTROL **Generar implementación de Web SDK**], utilice los resultados de auditoría y asignación para generar el paquete de implementación de Web SDK y, a continuación, impleméntelo en su sitio.

      Para ver los pasos detallados, consulte [Generar e implementar la implementación de Web SDK](#generate-and-deploy-the-web-sdk-implementation).


## Revisar y resolver conclusiones de auditoría

Durante la fase [!UICONTROL **Auditoría**], el Planificador de migración indica los resultados de las reglas seleccionadas. La resolución de los hallazgos es opcional antes de continuar, pero la resolución de los mismos ayuda a garantizar una migración limpia.

Para cada hallazgo, seleccione [!UICONTROL **Revisar**] para abrir el hallazgo y elegir cómo resolverlo, o seleccione [!UICONTROL **Ignorar**] para dejarlo sin dirección.

El planificador de migración puede marcar los siguientes tipos de conclusiones:

* [!UICONTROL **Eventos de regla duplicados**]: dos o más reglas tienen eventos y condiciones idénticos. Cuando revise la búsqueda, compare las reglas principales y duplicadas, mantenga una regla y elimine la otra o seleccione [!UICONTROL **No hacer nada**] para confirmar la búsqueda sin realizar ningún cambio.

* [!UICONTROL **Lógica de regla duplicada**]: Las reglas comparten la misma lógica. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **Acciones de regla mal ordenadas**]: Las acciones de una regla se ejecutan en un orden que podría causar problemas durante la migración. <!-- Confirm the exact remediation options for this finding type. -->

Si un hallazgo no tiene corrección guiada, el Planificador de migración muestra [!UICONTROL **No hay detalles de corrección disponibles**]. Revise la búsqueda manualmente y descártela cuando se resuelva.

El panel [!UICONTROL **Conclusiones**] muestra cuántas conclusiones ha abordado y cuántas aún están abiertas. Cuando hayas terminado, selecciona [!UICONTROL **Guardar y continuar**].

## Asignación de variables de Analytics a campos XDM

Durante la fase [!UICONTROL **Mapping**], se asignan las variables de Analytics a campos XDM y se genera o selecciona el esquema de destino. En la tarjeta [!UICONTROL **Asignación de Analytics → XDM**], seleccione [!UICONTROL **Crear nueva asignación**] y, a continuación, complete los siguientes pasos:

1. **Opción de esquema**: elija si desea crear un nuevo esquema basado en las variables de Analytics o asignarlo a un esquema de Experience Platform existente.

1. **Grupo de informes**: seleccione el grupo de informes de Analytics cuyas variables desee asignar.

1. **esquema de Experience Platform**: cree el esquema XDM de destino o seleccione el esquema existente para asignar.

1. **Asignación manual**: revise las asignaciones automáticas y ajuste cómo se asignan las variables individuales de Analytics a los campos XDM.

1. **Revisar esquema**: revise las asignaciones y el esquema resultantes y confirme.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

Para reutilizar un conjunto de asignaciones entre migraciones, consulte [Crear y administrar conjuntos de asignaciones](#create-and-manage-mapping-sets).

## Comparación de resultados de migración

Use [!UICONTROL **Comparar resultados**] en la página de información general de migración para validar la migración antes de implementarla.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Generación e implementación de la implementación de Web SDK

Durante la fase de [!UICONTROL **Implementación**], el planificador de migración utiliza los resultados de auditoría y asignación para crear el paquete de implementación de Web SDK.

1. En la página de información general sobre la migración, en la tarjeta [!UICONTROL **Generar implementación de Web SDK**], genere el paquete de implementación.

1. Genere la biblioteca de etiquetas para la migración seleccionando [!UICONTROL **Generar biblioteca de etiquetas**].

1. Configure la implementación dual y, a continuación, implemente la implementación de Web SDK en su sitio.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

Para ver los artefactos producidos por esta fase, consulte [Exportar artefactos de migración](#export-migration-artifacts).

## Exportar artefactos de migración

La página de información general de migración proporciona los artefactos que genera el planificador de migración. Puede descargar artefactos individuales del panel [!UICONTROL **Artefactos del proyecto**] o seleccionar [!UICONTROL **Exportar todo**] para exportar todo a la vez.

Los siguientes artefactos están disponibles:

* [!UICONTROL **Asignación de JSON**]: la asignación entre sus variables de Analytics y los campos XDM.

* [!UICONTROL **Esquema XDM (JSON)**]: El esquema XDM de destino creado para la migración.

* [!UICONTROL **Biblioteca de desarrollo de etiquetas**]: La biblioteca de etiquetas creada para la implementación de Web SDK.

Cada artefacto muestra su estado, como [!UICONTROL **Listo**] o [!UICONTROL **No compilado**]. Un artefacto está disponible para descargar después de que se genere en el escenario correspondiente.

## Creación y administración de conjuntos de asignaciones {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="Conjuntos de asignaciones"
>abstract="Los conjuntos de asignaciones determinan cómo se asignan las variables de Analytics a los campos XDM.<br/>Cree un nuevo conjunto de asignaciones o elija uno existente para aplicar las mismas asignaciones en varias migraciones. También puede hacer referencia a conjuntos de asignaciones en otras tareas de migración."

<!-- markdownlint-enable MD034 -->

Los conjuntos de asignaciones determinan cómo se asignan las variables de Analytics a los campos de esquema XDM.

Puede crear un nuevo conjunto de asignaciones [&#x200B; durante el proceso de migración](#migrate-an-analytics-implementation-to-the-web-sdk). O bien, puede crear un conjunto de asignaciones independiente para utilizarlo con una migración futura o con otras tareas de migración.

### Creación de un conjunto de asignaciones independiente {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="Elija un esquema."
>abstract="Los conjuntos de asignaciones determinan cómo se asignan las variables de Analytics a los campos XDM.<br/>Cree un nuevo conjunto de asignaciones o elija uno existente para aplicar las mismas asignaciones en varias migraciones. También puede hacer referencia a conjuntos de asignaciones en otras tareas de migración."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="Preferencia de grupo de campos"
>abstract="Elija grupos de campos estándar para utilizar grupos de campos de Adobe publicados cuando sea posible. Esto promueve la máxima coherencia y vuelve a los campos de inquilino personalizados cuando no hay campos estándar disponibles.<br/>Elija grupos de campos personalizados para usar campos personalizados de espacio de nombres de inquilino cuando sea posible. Esto promueve la máxima flexibilidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="Período retroactivo"
>abstract="Controla hasta dónde se retrocede al determinar qué variables reciben datos de forma activa. Las variables que incluyen datos dentro del período retroactivo se incluyen en el esquema."

<!-- markdownlint-enable MD034 -->

1. En el Planificador de migración, seleccione la ficha [!UICONTROL **Conjuntos de asignaciones**].

1. Seleccione [!UICONTROL **Nuevo conjunto de asignaciones**].

1. En el campo [!UICONTROL **Nombre**], escriba un nombre descriptivo para que pueda identificar este conjunto de asignaciones más adelante y, a continuación, seleccione [!UICONTROL **Siguiente**].

1. En el menú [!UICONTROL **Grupo de informes**], seleccione el grupo de informes cuyas variables desee asignar a campos XDM y, a continuación, seleccione [!UICONTROL **Siguiente**].

1. En la sección [!UICONTROL **Elija un esquema para la asignación XDM**], elija si desea crear un nuevo esquema basado en las variables de Analytics o asignarlo a un esquema de Experience Platform existente.

   La opción de crear un nuevo esquema le guiará a través del proceso de asignación de las variables de Analytics a campos XDM. La elección de utilizar un esquema existente permite asignar manualmente las variables a un esquema preregistrado en el registro de esquemas de Experience Platform.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **Crear un nuevo esquema**]: ejecute los análisis Básico y Avanzado para sugerir automáticamente asignaciones de campo XDM para las variables de Analytics y, a continuación, revise el esquema resultante.

   * [!UICONTROL **Usar un esquema existente**]: busque y seleccione un esquema que ya esté registrado en el registro de esquemas de Experience Platform y, a continuación, arrastre manualmente variables de Analytics a campos XDM.

1. En el menú desplegable [!UICONTROL **Preferencia de grupo de campos**], elija cómo desea organizar las variables personalizadas en grupos de campos:

   * [!UICONTROL **Estándar primero**]: utilice grupos de campos de Adobe publicados cuando sea posible. Esto promueve la máxima coherencia y vuelve a los campos de inquilino personalizados cuando no hay campos estándar disponibles.

   * [!UICONTROL **Personalizado primero**]: utilice los campos personalizados del espacio de nombres de inquilino siempre que sea posible. Esto promueve la máxima flexibilidad.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. En el campo [!UICONTROL **Periodo de retroactividad**], seleccione cuánto debe retroceder para determinar qué variables están recibiendo datos de forma activa. Las variables que incluyen datos dentro del período retroactivo se incluyen en el esquema.

1. Seleccione [!UICONTROL **Crear conjunto de asignaciones**].

El nuevo conjunto de asignaciones aparece en la ficha [!UICONTROL **Conjuntos de asignaciones**], donde puede abrirlo para revisar los detalles.

### Exportación de un conjunto de asignaciones

Puede exportar un conjunto de asignaciones para utilizarlo con otras tareas de migración o en otras herramientas.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### Conjuntos de asignación de publicación y versión

Cada conjunto de asignaciones tiene un estado y una versión. En la ficha [!UICONTROL **Conjuntos de asignaciones**], un conjunto de asignaciones puede aparecer como:

* [!UICONTROL **borrador**]: el conjunto de asignaciones aún se está editando.

* [!UICONTROL **publicado**]: el conjunto de asignaciones ha finalizado.

* [!UICONTROL **en migración**]: el conjunto de asignaciones está enlazado a una o más migraciones.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### Editar un conjunto de asignaciones <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### Eliminar un conjunto de asignaciones <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## Administración de migraciones existentes

### Búsqueda y seguimiento de migraciones

La ficha [!UICONTROL **Migraciones**] enumera sus migraciones y su progreso. Utilícelo para buscar una migración para continuar o para comprobar el estado de las migraciones que están en curso.

* **Buscar**: Utilice el campo de búsqueda para encontrar una migración por nombre o propiedad.

* **Filtro**: filtre la lista por tipo de migración o por estado.

* **Seguimiento del progreso**: cada migración muestra su progreso en las tres etapas (por ejemplo, 1/3) y un estado general:

  * [!UICONTROL **No iniciada**]: la migración se ha creado, pero no se ha completado ninguna etapa.

  * [!UICONTROL **En curso**]: Al menos una etapa está completa.

  * [!UICONTROL **Completado**]: las tres etapas han finalizado.

Para continuar una migración, selecciona [!UICONTROL **Abrir**] junto a ella.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

