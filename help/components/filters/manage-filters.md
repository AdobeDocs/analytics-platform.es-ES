---
title: Administrar filtros
description: descubra cómo administrar los filtros en Customer Journey Analytics
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Administrar filtros

El Administrador de filtros ofrece muchas formas de depurar segmentos, como compartir, etiquetar, aprobar, copiar, eliminar y marcar como favoritos.

El Administrador de filtros muestra todos los filtros que posee y que se han compartido con usted. Los usuarios con nivel de administrador pueden ver todos los filtros de la organización. Esta descripción general presenta la interfaz de usuario y las capacidades del Administrador de filtros.

Para acceder al Administrador de filtros, vaya a **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** en la navegación superior.

## Interfaz de usuario del Administrador de filtros

![](assets/filter-manager-ui.png)

| # | Función de la interfaz de usuario | Descripción |
|---|---|---|
| 1 | Barra de herramientas de administración de filtros | Una vez que haya marcado un filtro, aparecerá esta barra de herramientas. Puede realizar la mayoría de las tareas de gestión desde esta barra de herramientas. |
| 2 | Casillas de verificación | Marque un filtro para administrarlo. |
| 4 | Favoritos | Al hacer clic en la estrella que aparece junto a un filtro, ésta se vuelve amarilla y marca el filtro como favorito. |
| 5 | Título y descripción | Se proporciona en el Generador de filtros. Para editar el título y la descripción, haga clic en el vínculo del título; esto le lleva de nuevo al Generador de filtros. |
| 6 | Grupos de informes | Esta columna indica en qué grupo de informes se guardó por última vez el filtro. |
| 7 | Propietario | Indica quién es el propietario del filtro. Si no es administrador, solo podrá ver los filtros que le pertenecen o que se han compartido con usted. |
| 8 | Etiquetas (la columna no aparece porque no está marcada en el selector de columnas) | Etiquetas que usted o las personas que compartieron el filtro con usted aplicaron al filtro. |
| 9 | Compartido con | Enumera los individuos o grupos (solo administrador) o todos (solo administrador) con los que compartió el filtro. |
| 10 | Fecha de modificación | Muestra la fecha en que se modificó el filtro por última vez. |
| 11 | Selector de columnas | (Superior derecha) Permite seleccionar qué columnas mostrar en el Administrador de filtros. |
| 12 | Icono compartido | Indica que usted o usted comparten este filtro. |
| 13 | Icono de aprobado | Indica que un administrador ha aprobado este filtro. |
| 14 | Otros filtros | Permite ver los filtros por Etiquetas, Grupos de informes, Propietarios y Otros (Mostrar todo, Míos, Compartidos conmigo, Aprobados, Favoritos). |

## Filtros de plan

El hecho de dedicar un cierto tiempo a la planificación de los segmentos aumenta las probabilidades de que sean útiles para su organización y de que se mantenga bajo control el número de segmentos.

* Tome en consideración la audiencia: ¿quién lo consumirá? ¿Con quién lo compartirá? ¿Qué grupos de personas utilizarán este filtro y cómo debo etiquetarlo en consecuencia? Esto también significa proporcionar una buena descripción del filtro. Como mínimo, la descripción debe responder a las siguientes preguntas:

   * ¿Para qué sirve este filtro?

   * ¿Cuándo debo usar este filtro?

* Determine el ámbito del filtro. ¿Qué contenedor [de](/help/components/filters/filters-overview.md) filtro representa mejor el ámbito? Utilice el contenedor más pequeño posible.

* Decida qué elementos incluir en la definición del filtro y qué valores.

* Piense en cómo desea que se desarrolle su proceso de aprobación. ¿Una sola persona revisará y aprobará los filtros o será una decisión del comité?

* Defina los filtros con vistas a una biblioteca de filtros que ofrezca a los usuarios empresariales la capacidad de apilar y reutilizar fragmentos o componentes de filtros de forma modular. ¿Qué &quot;módulos&quot; necesita definir para que dicha biblioteca se haga realidad?

### Filtros de etiqueta

En el Administrador de filtros, los filtros de etiquetado permiten organizarlos. Todos los usuarios pueden crear etiquetas para filtros y aplicar una o más etiquetas a un segmento. Sin embargo, solo puede ver las etiquetas de los filtros que le pertenecen o que se han compartido con usted.

¿Qué tipo de etiquetas debería crear? A continuación encontrará una serie de sugerencias para crear etiquetas útiles:

* Etiquetas basadas en nombres de equipos, como “Marketing social” o “Marketing móvil”.

* Etiquetas de proyectos (etiquetas de análisis), como análisis de Páginas de entrada.

* Etiquetas de categorías: Para hombres, Área geográfica.

* Etiquetas de flujo de trabajo: pendiente de aprobación, conservado para (una unidad empresarial específica).

Para etiquetar un filtro:

1. En el Administrador de filtros, marque la casilla de verificación situada junto al filtro que desee etiquetar. Aparece la barra de herramientas de administración de filtros.

1. Haga clic **[!UICONTROL Tag]** y

   * Seleccione una de las etiquetas existentes, o bien

   * introduzca un nuevo nombre de etiqueta y pulse **[!UICONTROL Enter]**.

1. Click **[!UICONTROL Tag]** again to tag the segment.

La etiqueta debería aparecer en la columna de etiquetas. (Haga clic en el icono del engranaje en la esquina superior derecha para administrar las columnas.)
You can also filter on tags by going to **[!UICONTROL Filters > Tags]**.

### Aprobar filtros

Dentro del Administrador de filtros, puede configurar un flujo de trabajo que incluya la aprobación de filtros para varios niveles de aplicación, para departamentos o grupos específicos y que sea coherente con las políticas de informes.

A continuación se muestra cómo marcar un filtro como aprobado:

1. En el Administrador de filtros, marque la casilla a la izquierda del título Filtro.

1. Haga clic **[!UICONTROL Approve]** en la barra de tareas de administración de filtros.

1. Considere la posibilidad de compartir el segmento o segmentos aprobados con su organización.

1. Haga clic en **[!UICONTROL OK]**.

   Observe el icono de aprobación junto al filtro en la lista:

   ![](assets/seg_approved.png)

1. You can also unapprove an approved segment by clicking **[!UICONTROL Unapprove]**.

### Compartir filtros

En función de sus permisos, puede compartir filtros con toda la organización, grupos o usuarios individuales.

| Administrador | No administrador |
|---|---|
| Puede compartir filtros con Todos, con Grupos y con Usuarios. See the [Admin Console documentation](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) for more information. | Puede compartir filtros solo con usuarios individuales. |

¿Cuándo debe compartir filtros con toda la empresa en lugar de con un grupo de usuarios o personas? A continuación se indica una serie de prácticas recomendadas seguir:

* Como administrador, comparta un filtro con Todos si es útil para toda la empresa y todos se sienten cómodos al utilizarlo. En este caso, también debe considerar la posibilidad de convertirlo en un filtro aprobado.

* Como administrador, comparta un filtro con un perfil de producto específico si el filtro proporciona un buen valor comercial para ese equipo. No apruebe oficialmente este tipo de filtro.

* Como administrador o usuario individual, comparta un filtro con otras personas para examinarlo y validarlo. Si finalmente no resulta útil, descártela. No apruebe oficialmente este tipo de filtro.

Para compartir un filtro:

1. En el Administrador de filtros, marque la casilla de verificación situada junto al filtro que desee compartir.

1. En la barra de herramientas de administración de filtros, haga clic en **[!UICONTROL Share]**.

1. Si es administrador, puede seleccionar Todos o elegir entre Grupos y Usuarios de su organización. Si no es administrador, solo verá usuarios individuales. Utilice el campo Buscar para buscar grupos o usuarios. Haga clic en **[!UICONTROL Share]**. The Shared icon appears next to the filter: ![](assets/share_icon.png)

1. Puede filtrar los filtros compartidos con usted accediendo a Filtros > Otros filtros > Compartidos conmigo.

### Marcar filtros como favoritos

Marcar los segmentos como favoritos es otra manera de organizarlos para que su uso sea más sencillo.

1. En el Administrador de filtros, marque la estrella junto a cualquier filtro que desee marcar como favorito. La estrella se vuelve amarilla cuando la seleccionas.

1. También puede filtrar por favoritos con Filtros > Otros filtros > Favoritos.

