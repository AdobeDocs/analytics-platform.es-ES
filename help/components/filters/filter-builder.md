---
description: El Generador de filtros proporciona un lienzo al que arrastrar y en el que soltar los Dimension de métricas, los filtros y los eventos para filtrar a las personas en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar filtros simples o complejos que identifican atributos y acciones de personas en visitas y eventos.
title: Generar filtros
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: e97f206e2c2f00d32e7e06d56fcc84819fe329c6
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 23%

---

# Generador de filtros

El [!UICONTROL Generador de filtros] permite generar filtros simples o complejos que identifican atributos y acciones de personas en visitas y eventos. Proporciona un lienzo al que arrastrar y en el que soltar las dimensiones de métricas, los eventos u otros filtros para filtrar a las personas en función de la lógica, las reglas y los operadores de la jerarquía.

Para obtener información sobre cómo crear filtros rápidos que se apliquen únicamente al proyecto en el que se han creado, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

## Acceso al Generador de filtros

Puede acceder al Generador de filtros de cualquiera de las siguientes maneras:

* **Navegación superior**: haga clic en **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Filtros]**.
* **[!UICONTROL Analysis Workspace]**: Con un proyecto abierto en Analysis Workspace, seleccione **[!UICONTROL + Componentes]** > **[!UICONTROL Crear filtro]**.
* **[!UICONTROL Report Builder]**: [Trabajo con filtros en el Report Builder](/help/report-builder/work-with-filters.md).

## Resumen de criterios del generador {#section_F61C4268A5974C788629399ADE1E6E7C}

Puede agregar definiciones de reglas y contenedores para definir los filtros. (Para obtener información sobre el acceso al Generador de filtros, consulte [Acceso al Generador de filtros](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

| Elemento de la IU | Descripción |
| --- | --- |
| **[!UICONTROL Título]** | Asigne un nombre al filtro |
| **[!UICONTROL Descripción]** | Proporcione una descripción detallada para el filtro. |
| **[!UICONTROL Etiquetas]** | [Etiquetado del filtro](/help/components/filters/manage-filters.md) para crear, seleccione una lista de etiquetas existentes o cree una etiqueta nueva. |
| **[!UICONTROL Definiciones]** | Aquí es donde usted [generación y configuración de filtros](/help/components/filters/filters-overview.md), agregue reglas y anide y secuencie contenedores. |
| **[!UICONTROL Inclusión]** | (Selector de contenedor superior.) Permite seleccionar el nivel superior [contenedor](/help/components/filters/filters-overview.md) ( [!UICONTROL Persona], [!UICONTROL Session], [!UICONTROL Evento]). El contenedor de nivel superior predeterminado es el contenedor Evento. |
| **[!UICONTROL Opciones]** | Icono (engranaje) | <ul><li>**[!UICONTROL + Agregar contenedor]**: le permite agregar un nuevo contenedor (debajo del contenedor de nivel superior) a la definición del filtro.</li><li>**[!UICONTROL Excluir]**: permite definir el filtro excluyendo una o más dimensiones, filtros o métricas.</li></ul> |
| **[!UICONTROL Dimensiones]** | Los componentes se arrastran y sueltan desde la lista Dimension (barra lateral naranja). |
| **[!UICONTROL Operador]** | Puede comparar y restringir valores utilizando una selección de operadores. (es igual a, no es igual a, contiene, contiene todo, etc.) |
| **[!UICONTROL Valor]** | El valor introducido o seleccionado para la dimensión, el filtro o la métrica. |
| **[!UICONTROL Modelos de atribución]** | Disponible solo para dimensiones, estos modelos determinan qué valores de una dimensión se filtran. Los modelos de Dimension son especialmente útiles en filtros secuenciales.<ul><li>**[!UICONTROL Repetido]** (por defecto): Incluye instancias y valores persistentes para la dimensión.</li><li>**[!UICONTROL Instancia]**: Incluye instancias para la dimensión.</li><li>**[!UICONTROL Instancia no repetida]**: Incluye instancias únicas (no repetitivas) para la dimensión. Este es el modelo aplicado en Flujo cuando se excluyen instancias repetidas.</li></ul>Para ver un ejemplo, consulte la sección &quot;Modelos de atribución&quot; a continuación. |
| **[!UICONTROL Y/O/Entonces]** | Asigna los operadores [!UICONTROL Y/O/ENTONCES] entre contenedores o reglas. El operador ENTONCES le permite [definir filtros secuenciales](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Métrica]** | (Barra lateral verde) Métrica que se arrastró y soltó desde la lista Métricas. |
| **[!UICONTROL X]** | (Eliminar) Permite eliminar esta parte de la definición del filtro. |
| **[!UICONTROL Crear audiencia a partir del filtro]** | La creación de una audiencia a partir de un filtro le permite compartir el filtro con Adobe Experience Platform para su activación. [Más información...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Componente de búsqueda]** | Busca en la lista de dimensiones, filtros o métricas. |
| **[!UICONTROL Dimensiones]** | (Lista) La lista de dimensiones que se pueden incluir en el filtro. Haga clic en el encabezado para ampliarlo. |
| **[!UICONTROL Métricas]** | La lista de métricas que puede incluir en el filtro. Haga clic en el encabezado para ampliarlo. |
| **[!UICONTROL Filtros]** | La lista de filtros existentes que puede incluir en el filtro. Haga clic en el encabezado para ampliarlo. |
| **[!UICONTROL Selector de vista de datos]** | Permite seleccionar el grupo de informes en el que se guardará este filtro. Puede seguir utilizando el filtro en todas las vistas de datos. |
| **[!UICONTROL Previsualización de filtro]** | Permite obtener una vista previa de las métricas clave para ver si tiene un filtro válido y su amplitud. Representa el desglose del conjunto de datos que verá si aplica este filtro. Muestra tres círculos concéntricos y una lista para indicar el número y el porcentaje de coincidencias [!UICONTROL People], [!UICONTROL Sesiones], y [!UICONTROL Ejecución de informes] para un filtro ejecutado con un conjunto de datos.<p>Este gráfico se actualiza inmediatamente después de crear o realizar cambios en la definición del filtro. |
| **[!UICONTROL Guardar]** o **[!UICONTROL Cancelar]** | Guarda o cancela el filtro. Después de hacer clic **[!UICONTROL Guardar]**, se le redirigirá al Administrador de filtros, donde podrá administrar el filtro. |

## Generar un filtro {#build-filters}

1. Basta con arrastrar un Dimension, un filtro o un evento de métrica del panel izquierdo al [!UICONTROL Definiciones] field.

   ![](assets/drag_n_drop_dimension.png)

1. Establezca el [operador](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=es) en el menú desplegable.
1. Introduzca o seleccione un valor para el elemento seleccionado.
1. Agregue contenedores adicionales si es necesario, utilizando las reglas **[!UICONTROL AND]**, **[!UICONTROL OR]** o **[!UICONTROL THEN]**.
1. Después de colocar los contenedores y configurar las reglas, consulte los resultados del filtro en la tabla de validación, en la parte superior derecha. El validador indica el porcentaje y el número absoluto de vistas de página, visitas y personas únicas que coinciden con el filtro que ha creado.
1. En **[!UICONTROL Etiquetas]**, [etiqueta](/help/components/filters/manage-filters.md) Seleccione el contenedor seleccionando una etiqueta existente o creando una nueva.
1. Clic **[!UICONTROL Guardar]** para guardar el filtro.

   Se le redirige a la [Administrador de filtros](/help/components/filters/manage-filters.md), donde puede etiquetar, compartir y administrar el filtro de varias formas.

## Añadir contenedores {#containers}

Puede [generar un marco de contenedores](/help/components/filters/filters-overview.md) y luego colocar reglas lógicas y operadores entre medias.

1. Clic **[!UICONTROL Opciones > Agregar contenedor]**.

   Un nuevo [!UICONTROL **Evento**] el contenedor se abre sin un [!UICONTROL **Evento**] (Vista de página) identificados.

   ![](assets/new_container.png)

1. Cambie el tipo de contenedor según sea necesario.
1. Arrastre un Dimension, un filtro o un evento desde el panel izquierdo al contenedor.
1. Siga agregando nuevos contenedores desde el botón **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor]** del nivel superior situado en la parte superior de la definición, o agregue contenedores desde dentro de un contenedor para anidar la lógica.

   **OR**

   Seleccione una o más reglas y luego haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor de selección]**. Esto convierte su selección en un contenedor separado.

## Usar intervalos de fechas {#date-ranges}

Puede generar filtros que contengan intervalos de fechas móviles para responder a preguntas sobre campañas o eventos en curso.

Por ejemplo, puede crear fácilmente un filtro que incluya a &quot;todas las personas que hayan realizado una compra en los últimos 60 días&quot;.

Cree un contenedor de sesión y, dentro de él, agregue [!UICONTROL Últimos 60 días] intervalo de tiempo y métrica [!UICONTROL Pedidos superiores o iguales a 1], con un operador AND.

Aquí tiene un vídeo sobre el uso de intervalos de fechas móviles en los filtros:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Apilado de filtros {#stack}

El apilamiento de filtros funciona mediante la combinación de criterios en cada filtro utilizando un operador &quot;and&quot;, y luego aplicando los criterios combinados. Esto se puede hacer directamente en un proyecto de Workspace o en el Generador de filtros.

Por ejemplo, apilar un filtro &quot;usuarios de teléfonos móviles&quot; y un filtro &quot;geografía de Estados Unidos&quot; devolvería datos solo para usuarios de teléfonos móviles en Estados Unidos.

Piense en estos filtros como bloques de creación o módulos que puede incluir en una biblioteca de filtros para que los usuarios los utilicen como les parezca adecuado. De este modo, puede reducir drásticamente el número de filtros necesarios. Por ejemplo, supongamos que tiene 40 filtros:

* 20 para usuarios de teléfonos móviles en diferentes países (EEUU_móvil, Alemania_móvil, Francia_móvil, Brasil_móvil, etc.).
* 20 para usuarios de tabletas en diferentes países (EEUU_tableta, Alemania_tableta, Francia_tableta, Brasil_tableta, etc.).

Al utilizar el apilamiento de filtros, puede reducir el recuento de filtros a 22 y apilarlos según sea necesario. Debe crear estos filtros:

* un filtro para usuarios móviles
* un filtro para usuarios de tablet
* 20 filtros para las diferentes regiones geográficas

>[!NOTE]
>
>Al apilar dos filtros, se unen de forma predeterminada con una instrucción AND. No es posible cambiarlo a una instrucción OR.

1. Vaya al Generador de filtros.

1. Proporcione un título y una descripción para el filtro.

1. Clic **[!UICONTROL Mostrar filtros]** para que aparezca la lista de filtros en el panel de navegación izquierdo.

1. Arrastre los filtros que desee apilar al lienzo de definición del filtro.

1. Seleccione [!UICONTROL **Guardar**].

## Modelos de atribución {#attribution}

![](assets/attribution-models.jpg)

**Ejemplo: Filtro de eventos donde eVar 1 = A**

| Ejemplo | A | A | A (persistió) | B | A | C |
|---|---|---|---|---|---|---|
| Repetido | X | X | X | - | X | - |
| Instancia | X | X | - | - | X | - |
| Instancia no repetida | X | - | - | - | X | - |