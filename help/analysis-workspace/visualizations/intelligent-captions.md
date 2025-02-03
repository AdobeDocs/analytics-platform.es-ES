---
description: Utilice subtítulos inteligentes para generar perspectivas en lenguaje natural y mostrar tendencias dentro de las visualizaciones.
title: Pies de ilustración inteligentes
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 5d391a73fb30ebc8f443f5a88357c866df03ce96
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 16%

---

# Pies de ilustración inteligentes {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="Subtítulos inteligentes: Área"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="Subtítulos inteligentes: Barra"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="Subtítulos inteligentes: Anillo"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="Subtítulos inteligentes: Barra horizontal"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="Subtítulos inteligentes: Línea"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="Subtítulos inteligentes: Visitas en el orden previsto"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="Subtítulos inteligentes: Flujo"
>abstract="Genere información en forma de lenguaje natural para ayudarle a comprender e interpretar los datos más fácilmente para esta visualización."

<!-- markdownlint-enable MD034 -->

La funcionalidad Subtítulos inteligentes utiliza IA generativa avanzada para proporcionar perspectivas clave para las visualizaciones de Workspace utilizadas con más frecuencia en lenguaje natural.

Los subtítulos inteligentes están orientados a:

* Analistas, que necesitan narrativas para compartir con otros usuarios. Los analistas necesitan estas perspectivas para poder proporcionar contexto a sus usuarios.
* Usuarios empresariales que deseen descubrir rápidamente los principales conocimientos.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Subtítulos inteligentes](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

## Iniciar subtítulos inteligentes {#launch}

Para iniciar subtítulos inteligentes generados automáticamente para una visualización, seleccione ![Subtítulos inteligentes](/help/assets/icons/AI.svg) en la parte superior derecha de la visualización. Esta selección genera perspectivas en lenguaje natural.

![Iniciar análisis con los subtítulos inteligentes para la tendencia de vistas de productos. ](assets/intelligent-captions.gif)


Tenga en cuenta que:

* Necesita un mínimo de 3 puntos de datos para generar subtítulos correctamente. De lo contrario, podría recibir un error como **[!UICONTROL No hay suficientes datos para analizar]**.

* Los subtítulos se generan cada vez que los datos seleccionados subyacentes cambian en la tabla que alimenta la visualización.

* Si hay varias métricas en una tabla de forma libre asociada, los subtítulos solo se generan para la primera métrica o la métrica seleccionada actualmente por el usuario. Sin embargo, se pueden generar subtítulos para varias métricas en las visualizaciones de líneas y áreas.

* Si guarda el proyecto en un punto específico y lo vuelve a cargar más adelante, los subtítulos se actualizan automáticamente con nuevos datos. Lo mismo se aplica a los proyectos programados y a los archivos de PDF exportados desde un proyecto.


## Visualizaciones {#visualizations}

Los subtítulos inteligentes son compatibles con las siguientes visualizaciones:

* [Línea](line.md) (incluyendo multilínea)
* [Barra](bar.md)
* [Barra horizontal](horizontal-bar.md)
* [Área](area.md) (incluidas varias líneas de área)
* [Anillo](donut.md)
* [Visita en orden previsto](fallout/fallout-flow.md)
* [Flujo](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## Acciones

Puede realizar las siguientes acciones en los subtítulos inteligentes:

### Copiar en el portapapeles {#copy}

Puede copiar los subtítulos en un portapapeles y pegarlos en un PowerPoint u otras herramientas. Puede copiar títulos individuales en la vista uno por uno, o bien puede copiar todos los títulos a la vez en la vista de títulos expandidos.

* Para copiar los subtítulos, seleccione ![Copiar subtítulos al portapapeles](/help/assets/icons/Copy.svg) en la parte superior derecha del cuadro de diálogo de subtítulos.

### Mostrar todos los subtítulos inteligentes o cada uno  {#show-all-or-individual}

Puede mostrar todos los subtítulos inteligentes a la vez en una vista expandida, o bien puede mostrar subtítulos inteligentes individuales en una vista uno por uno.

* Para mostrar todos los subtítulos inteligentes, seleccione ![Mostrar todos los subtítulos inteligentes](/help/assets/icons/Maximize.svg).
* Para mostrar subtítulos inteligentes individuales, uno por uno, seleccione ![Mostrar subtítulos inteligentes individuales](/help/assets/icons/Minimize.svg).

### Editar pantalla {#edit}

Puede editar la visualización de subtítulos, como ocultar o mostrar una categoría particular de perspectivas.

1. Seleccione ![Editar visibilidad de subtítulos inteligentes](/help/assets/icons/EditInLight.svg) en el cuadro de diálogo Subtítulos inteligentes.

1. Alterne entre ![Alternar visibilidad](/help/assets/icons/Visibility.svg) para mostrar una perspectiva específica (como **[!UICONTROL Min]**) o ![Alternar visibilidad](/help/assets/icons/VisibilityOff.svg) para ocultar una perspectiva específica (como **[!UICONTROL Spike]**).

   ![Editar subtítulos inteligentes](assets/edit-intelligent-captions.png)

1. Seleccione **[!UICONTROL Aplicar]**.


### Proporcionar comentarios

Puede proporcionar comentarios sobre los subtítulos inteligentes generados (solo se pueden proporcionar comentarios en la vista de subtítulos expandidos).

1. Seleccione ![Más acciones](/help/assets/icons/More.svg) en el cuadro de diálogo Subtítulos inteligentes.

1. Seleccione ![Buena respuesta](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Buena respuesta]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Respuesta incorrecta]** o ![Indicador](/help/assets/icons/Flag.svg) **[!UICONTROL Informe]**.

1. En el cuadro de diálogo **[!UICONTROL Gracias por sus comentarios]**, proporcione sus comentarios y seleccione **[!UICONTROL Enviar]** para enviar los comentarios.

### Exportar {#export}

Puede exportar subtítulos inteligentes como parte de un PDF, siempre y cuando el proyecto se guarde con los subtítulos inteligentes generados.

### Alternar desactivado {#toggle}

Si prefiere no mostrar subtítulos inteligentes, puede desactivar la función.

1. Vaya a [Preferencias de visualizaciones](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Desmarque **[!UICONTROL Mostrar subtítulos inteligentes]**.

   ![Opciones de visualización de líneas que muestran la opción de desactivar Mostrar subtítulos inteligentes.](assets/toggle-captions.png)

1. Seleccione **[!UICONTROL Guardar]** para guardar la preferencia.


## Subtítulos inteligentes en cuadros de resultados móviles

Los subtítulos inteligentes también están disponibles en los [cuadros de resultados móviles](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) del Customer Journey Analytics.

## Acceso a funciones

Los siguientes parámetros rigen el acceso a los subtítulos inteligentes:

* **Acceso a la solución**: la característica Subtítulos inteligentes está disponible en Customer Journey Analytics, pero no en Adobe Analytics.

* **Acceso contractual**: Si no puede usar subtítulos inteligentes, póngase en contacto con el administrador de su organización o con el representante de cuentas de Adobe (administrador). Antes de poder utilizar subtítulos inteligentes en su organización, debe aceptar determinados términos legales relacionados con la inteligencia artificial aplicada a la generación.

* **Permisos**: en [!UICONTROL Adobe Admin Console], el permiso de [!UICONTROL Herramientas de informes] **[!UICONTROL Subtítulos inteligentes]** determina el acceso. Un [administrador de perfil de producto](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html) debe seguir estos pasos en el [!UICONTROL Admin Console]:
   1. Vaya a **[!UICONTROL Admin Console]** > **[!UICONTROL Productos y servicios]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfiles de productos]**.
   1. Seleccione el título del perfil de producto para el que desea proporcionar acceso a Subtítulos inteligentes.
   1. En el perfil de producto específico, seleccione **[!UICONTROL Permisos]**.
   1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para editar **[!UICONTROL Herramientas de informes]**.
   1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) para agregar **Subtítulos inteligentes** a **[!UICONTROL Elementos de permiso incluidos]**.

      ![Agregar permiso](./assets/intelligent-captions-permissions.png)

   1. Seleccione **[!UICONTROL Guardar]** para guardar los permisos.

Consulte [Control de acceso](/help/technotes/access-control.md#access-control) para obtener más información.
