---
title: Administrar filtros
description: descubra cómo administrar filtros en Customer Journey Analytics
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Administrar filtros

El Administrador de filtros oferta muchas formas de depurar segmentos, como compartir, etiquetar, aprobar, copiar, eliminar y marcar como favoritos.

El Administrador de filtros muestra todos los filtros que posee y que se han compartido con usted. Los usuarios con nivel de administrador pueden ver todos los filtros de la organización. Esta descripción general presenta la interfaz de usuario y las capacidades del Administrador de filtros.

Para acceder al Administrador de filtros, vaya a **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** en la navegación superior.

## Interfaz de usuario del Administrador de filtros

![](assets/filter-manager-ui.png)

| # | Función de interfaz de usuario | Descripción |
|---|---|---|
| 1 | Barra de herramientas de administración de filtros | Una vez que haya marcado un filtro, aparecerá esta barra de herramientas. Puede realizar la mayoría de las tareas de gestión desde esta barra de herramientas. |
| 2 | Casillas de verificación | Marque un filtro para administrarlo. |
| 4 | Favoritos | Al hacer clic en la estrella que aparece junto a un filtro, ésta se vuelve amarilla y marca el filtro como favorito. |
| 5 | Título y descripción | Se proporciona en el Generador de filtros. Para editar el título y la descripción, haga clic en el vínculo del título; esto le lleva de nuevo al Generador de filtros. |
| 6 | Grupos de informes | Esta columna indica en qué grupo de informes se guardó por última vez el filtro. |
| 7 | Propietario | Indica quién es el propietario del filtro. Si no es administrador, solo podrá ver los filtros que le pertenecen o los que se han compartido con usted. |
| 8 | Etiquetas (no marcadas en el selector de columnas, por lo que no aparece la columna) | Etiquetas que usted o las personas que compartieron el filtro con usted aplicaron al filtro. |
| 9 | Compartido con | Lista los individuos o grupos (solo administrador) o todos (solo administrador) con los que compartió el filtro. |
| 10 | Fecha de modificación | Muestra la fecha en que se modificó el filtro por última vez. |
| 11 | Selector de columnas | (Superior derecha) Permite seleccionar qué columnas mostrar en el Administrador de filtros. |
| 12 | Icono compartido | Indica que usted o usted comparten este filtro. |
| 13 | Icono Aprobado | Indica que un administrador ha aprobado este filtro. |
| 14 | Otros Filtros | Permite ver filtros por etiquetas, grupos de informes, propietarios y otros (Mostrar todo, Mío, Compartido conmigo, Aprobado, Favoritos). |

## filtros del plan

Dedicar algún tiempo a planificar segmentos mejora las posibilidades de que sean útiles para su organización y de que sus números se mantengan bajo control.

* Consideremos la audiencia: ¿Quién lo consumirá? ¿Con quién lo compartirás? ¿Qué grupos de personas utilizarán este filtro y cómo debo etiquetarlo en consecuencia? Esto también significa proporcionar una buena descripción del filtro. Como mínimo, la descripción debe responder a estas preguntas:

   * ¿Para qué sirve este filtro?

   * ¿Cuándo debo usar este filtro?

* Determine el ámbito del filtro. ¿Qué contenedor [de](/help/components/filters/filters-overview.md) filtro representa mejor el ámbito? Utilice el contenedor más pequeño posible.

* Decida qué elementos incluir en la definición del filtro y qué valores.

* Considere cómo desea que se desarrolle el proceso de aprobación. ¿Una sola persona revisará y aprobará los filtros o será una decisión del comité?

* Defina sus filtros con vista a una biblioteca de filtros que ofrezca a los usuarios empresariales la capacidad de apilar y reutilizar piezas o componentes de filtro de forma modular. ¿Qué &quot;módulos&quot; necesita definir para que dicha biblioteca se haga realidad?

### filtros de etiquetas

En el Administrador de filtros, el etiquetado de filtros permite organizarlos. Todos los usuarios pueden crear etiquetas para filtros y aplicar una o varias a un segmento. Sin embargo, solo puede ver las etiquetas de los filtros que le pertenecen o que se han compartido con usted.

¿Qué tipo de etiquetas debe crear? Estas son algunas sugerencias para etiquetas útiles:

* Etiquetas basadas en nombres de equipo, como Marketing social o Marketing móvil.

* Etiquetas de proyecto (etiquetas de análisis), como análisis de página de entrada.

* Etiquetas de Categoría: de los hombres; geografía.

* Etiquetas de flujo de trabajo: Que se apruebe; Depurado para (una unidad de negocio específica)

Para etiquetar un filtro:

1. En el Administrador de filtros, marque la casilla de verificación situada junto al filtro que desee etiquetar. Aparece la barra de herramientas de administración de filtros.

1. Haga clic **[!UICONTROL Tag]** y

   * Seleccione una de las etiquetas existentes, o bien

   * introduzca un nuevo nombre de etiqueta y pulse **[!UICONTROL Enter]**.

1. Click **[!UICONTROL Tag]** again to tag the segment.

La etiqueta debe aparecer ahora en la columna Etiquetas. (Haga clic en el icono de engranaje en la parte superior derecha para administrar las columnas).
You can also filter on tags by going to **[!UICONTROL Filters > Tags]**.

### Aprobar filtros

Dentro del Administrador de filtros, puede configurar un flujo de trabajo que incluya la aprobación de filtros para varios niveles de aplicación, para departamentos o grupos específicos y que sea coherente con las políticas de sistema de informes.

A continuación se muestra cómo marcar un filtro como aprobado:

1. En el Administrador de filtros, marque la casilla a la izquierda del título Filtro.

1. Haga clic **[!UICONTROL Approve]** en la barra de tarea de administración de filtros.

1. Considere la posibilidad de compartir el segmento o segmentos aprobados con su organización.

1. Haga clic en **[!UICONTROL OK]**.

   Observe el icono de aprobación junto al filtro en la lista:

   ![](assets/seg_approved.png)

1. You can also unapprove an approved segment by clicking **[!UICONTROL Unapprove]**.

### Compartir filtros

En función de sus permisos, puede compartir filtros con toda la organización, grupos o usuarios individuales.

| Administrador | No administrador |
|---|---|
| Puede compartir filtros con Todos, con Grupos y con Usuarios. Consulte la documentación [de la Consola de](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) administración para obtener más información. | Puede compartir filtros solo con usuarios individuales. |

¿Cuándo debe compartir filtros con toda la compañía en lugar de con un grupo de usuarios o personas? Estas son algunas de las prácticas recomendadas que puede seguir:

* Como administrador, comparta un filtro con Todos si resulta útil para toda la compañía y todos se sienten cómodos al utilizarlo. En este caso, también debe considerar la posibilidad de convertirlo en un filtro aprobado.

* Como administrador, comparta un filtro con un Perfil de producto específico si el filtro proporciona un buen valor comercial para ese equipo. No apruebe oficialmente este tipo de filtro.

* Como administrador o usuario individual, comparta un filtro con otras personas para examinarlo y validarlo. Si no resulta útil, puede descartarse. No apruebe oficialmente este tipo de filtro.

Para compartir un filtro:

1. En el Administrador de filtros, marque la casilla de verificación situada junto al filtro que desee compartir.

1. En la barra de herramientas de administración de filtros, haga clic en **[!UICONTROL Share]**.

1. Si es administrador, puede seleccionar Todos o elegir entre Grupos y Usuarios de su organización. Si no es administrador, solo verá usuarios individuales. Utilice el campo Buscar para buscar grupos o usuarios. Haga clic en **[!UICONTROL Share]**. The Shared icon appears next to the filter: ![](assets/share_icon.png)

1. Puede filtrar los filtros compartidos con usted accediendo a Filtros > Otros Filtros > Compartidos conmigo.

### Marcar filtros como favoritos

Marcar los segmentos como favoritos es otra manera de organizarlos para que su uso sea más sencillo.

1. En el Administrador de filtros, marque la estrella junto a cualquier filtro que desee marcar como favorito. La estrella se vuelve amarilla cuando la seleccionas.

1. También puede filtrar por favoritos con Filtros > Otros filtros > Favoritos.

