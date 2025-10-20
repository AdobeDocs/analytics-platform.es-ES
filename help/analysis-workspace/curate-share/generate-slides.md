---
description: Aprenda a generar presentaciones en formato pptx a partir de informes de Workspace.
keywords: Analysis Workspace
title: Generar presentaciones desde informes de Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# Narración de datos: Generar presentaciones de diapositivas a partir de informes de Workspace {#generate-powerpoint}

Los usuarios con [los permisos necesarios](#permission-requirements-to-generate-slides) pueden generar automáticamente presentaciones .pptx a partir de proyectos de Analysis Workspace. Al generar estas presentaciones de diapositivas, Customer Journey Analytics crea automáticamente una historia a partir de sus datos identificando perspectivas clave y convirtiéndolas en diapositivas listas para las partes interesadas.

Esta funcionalidad reduce el tiempo y el esfuerzo necesarios para sacar a la luz los resultados de sus proyectos de Workspace y le permite crear rápidamente narrativas ejecutivas y comunicar el impacto comercial a las partes interesadas.

Esta historia de datos generada automáticamente permite a los analistas centrarse en la exploración de datos, mientras que Customer Journey Analytics depura y da formato a las conclusiones del analista para que las utilicen las partes interesadas.

## Comprender las historias de datos en las presentaciones de diapositivas

Analysis Workspace utiliza IA generativa para crear historias de datos en las presentaciones de diapositivas. Estas historias de datos complementan un análisis para un proyecto de Workspace determinado al proporcionar contexto adicional, destacar elementos importantes e ideas para los pasos siguientes. llamar las tendencias ocultas, las anomalías, los factores que contribuyen, los impulsores clave

### Valor adicional proporcionado por las historias de datos

Las historias de datos complementan un análisis para un proyecto de Workspace determinado al:

* Proporcionar contexto adicional

* Resaltar perspectivas importantes

* Llamar la atención sobre tendencias ocultas, anomalías y otros factores que contribuyen

* Identificación de controladores clave

* Dar ideas para los pasos siguientes

### Elementos de proyecto que dan forma a historias de datos

Analysis Workspace crea historias de datos teniendo en cuenta los siguientes elementos de proyecto:

* Relaciones entre dimensiones e intermétricas

* Los elementos individuales que forman la base del análisis: dimensiones, métricas, filtros, estructura de tabla de forma libre, visualizaciones y paneles

* Nombres asignados a los paneles, tablas y visualizaciones

* El orden de las métricas en una tabla de forma libre (para determinar la prioridad)

* Números y textos de resumen (para determinar las métricas que deben resaltarse en la historia de datos)

### Elementos de presentación de una historia de datos

Los artículos de datos constan de una diapositiva de resumen ejecutivo, diapositivas de detalle y divisores de sección.

**Resumen ejecutivo:** da prioridad a las perspectivas de mayor valor y crea una historia global de entre 1 y 5 frases de longitud.

**Diapositivas de detalle:** genera información relacionada con tablas, paneles o visualizaciones de un proyecto de Workspace. Las perspectivas constan de tendencias, estacionalidades, anomalías y correlaciones.

**Divisores de sección:** divide la información con divisores de sección con nombre y colocados correctamente.

## Generar una presentación .pptx basada en un proyecto de Workspace

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Paneles y visualizaciones incluidos"
>abstract="Elija los paneles y las visualizaciones que desee incluir en la presentación. Puede incluir hasta 50 visualizaciones."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Componentes enfatizados"
>abstract="Elija entre las visualizaciones hasta 5 métricas y 5 dimensiones que desee resaltar en la presentación. Las métricas que elija se muestran en cursiva, las dimensiones en negrita y los elementos de dimensión en color distinto."

<!-- markdownlint-enable MD034 -->

1. Vaya al proyecto de Workspace que contiene los datos que desea utilizar como base para la presentación de diapositivas.

1. Seleccione **[!UICONTROL Generar diapositivas]** en la esquina superior derecha de la página.

   Aparece el cuadro de diálogo Generar diapositivas.

   ![Cuadro de diálogo Generar diapositivas](assets/generate-slides.png)

1. Especifique la siguiente información:

   | Opción | Descripción |
   |---------|----------|
   | **[!UICONTROL Título de portada]** | Especifique un título para la presentación. Este título aparece en la diapositiva de título de la presentación. |
   | **[!UICONTROL Incluir nombre del moderador]** | Especifique el nombre del moderador. Este nombre aparece en la diapositiva de título de la presentación, debajo del título de la portada. |
   | **[!UICONTROL Paneles y visualizaciones que incluir]** | Elija los paneles y la visualización que desee incluir en la presentación. Puede incluir hasta 50 visualizaciones.<p>Se admiten la mayoría de los paneles y las visualizaciones. Para obtener información acerca de paneles y visualizaciones no compatibles, vea [Elementos y características de proyecto no compatibles](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Descripciones de paneles y visualizaciones]** | |
   | **[!UICONTROL Anotaciones]** | |
   | **[!UICONTROL Enfatizar componentes]** | Elija entre las visualizaciones hasta 5 métricas y 5 dimensiones que desee resaltar en la presentación.<p>Cuando no se aplica ningún énfasis, los componentes se muestran en las presentaciones de la siguiente manera:<ul><li>**Métricas y dimensiones:** Cursiva</li><li>**Elementos de Dimension:** Comillas</li></ul></p><p>Cuando se aplica énfasis, los componentes se muestran en las presentaciones de la siguiente manera:</p><ul><li>**Métricas y dimensiones:** Cursiva y negrita</li><li>**Elementos de Dimension:** Negrita cuando se enfatiza la dimensión correspondiente<p>También se aplica un color al elemento de dimensión cuando este se resalta en el gráfico.</p></li></ul> |

1. (Condicional) Seleccione **[!UICONTROL Tema predeterminado]** si desea generar diapositivas rápidamente en menos pasos y si no se requiere un tema corporativo para la presentación de diapositivas.

   Simplemente elija el tema de color de la presentación seleccionando el color deseado.

   ![Generar diapositivas con el tema predeterminado](assets/generate-slides-default-theme.png)

1. (Condicional) Seleccione **[!UICONTROL Cargar plantilla]** si la presentación de diapositivas debe coincidir con un tema corporativo. Esta opción requiere que cargue una plantilla personalizada y aplique los estilos personalizados.

   ![Generar diapositivas con una plantilla personalizada](assets/generate-slides-upload-template.png)

   Para cargar una plantilla personalizada, realice una de las acciones siguientes:

   * (Recomendado) Descargar una plantilla en blanco y modificarla.

      1. Descargue esta plantilla en blanco. <!--add link-->

      1. Aplique los estilos personalizados a la plantilla en blanco.

      1. Vuelva a cargar la plantilla sin cambiar los nombres de los diseños maestros.

   * Cargue una plantilla personalizada directamente.

      1. Desde el sistema de archivos, arrastre la plantilla personalizada al área de colocación.

         O bien

         Seleccione **[!UICONTROL Examinar]**, luego busque y seleccione su plantilla personalizada del sistema de archivos.

         Asegúrese de que el archivo cargado tenga diseños de patrón con los siguientes nombres: &quot;Title_Slide&quot;, &quot;Section_Divider&quot;, &quot;Title_Text&quot;, &quot;Title_Chart&quot;, &quot;Title_Two_Content_Mixed&quot;, &quot;Title_Three_Content_Mixed&quot;

         Se admiten archivos .pptx y .potx de hasta 25 MB de tamaño.

1. Seleccione **[!UICONTROL Exportar PPT]**.

1. (Recomendado) Revise y edite la presentación .ppt y realice los cambios que sean necesarios, tal como se describe en la sección siguiente, [Editar diapositivas de una presentación generada anteriormente](#edit-slides-from-a-previously-generated-presentation).

## Editar diapositivas de una presentación generada anteriormente


## Descargar una presentación .pptx generada



## Requisitos de permisos para generar diapositivas

>[!AVAILABILITY]
>
>Si su organización no tiene acceso para generar presentaciones de diapositivas desde un proyecto de Workspace, póngase en contacto con el representante de su cuenta de Adobe para obtener más información sobre las licencias.
>
>Esta capacidad está habilitada de forma predeterminada para todos los usuarios de organizaciones que tienen las licencias requeridas.

Los administradores de perfil de productos cuyas organizaciones tengan licencia para generar diapositivas pueden deshabilitar el acceso si es necesario.

En [!UICONTROL Adobe Admin Console], el permiso de [!UICONTROL herramientas de informes] y **[!UICONTROL narración de datos]** determina el acceso a esta capacidad. Un [administrador de perfil de producto](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html?lang=es) debe seguir estos pasos en [!UICONTROL Admin Console] si desea deshabilitar el acceso:
1. Vaya a **[!UICONTROL Admin Console]** > **[!UICONTROL Productos y servicios]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfiles de productos]**.
1. Seleccione el título del perfil de producto para el que desea proporcionar acceso a [!UICONTROL narración de datos].
1. En el perfil de producto específico, seleccione **[!UICONTROL Permisos]**.
1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para editar **[!UICONTROL Herramientas de creación de informes]**.
1. Seleccione ![AddCircle](/help/assets/icons/RemoveCircle.svg) para quitar **Data storytold** de **[!UICONTROL los elementos de permiso incluidos]**.

   <!--add screenshot of permission in the admin console-->

1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

Para obtener más información, consulte [Acceso de nivel de usuario](/help/technotes/access-control.md#user-level-access) en [Control de acceso](/help/technotes/access-control.md#access-control).

## Elementos y características de proyecto no compatibles {#unsupported}

Los siguientes elementos y características de Analysis Workspace utilizados en un proyecto no son compatibles con la generación de diapositivas:

* Panel de atribución

  Este panel se muestra atenuado cuando se muestran las opciones de configuración.

  El resto de paneles se pueden incluir en las diapositivas que se generan a partir de un proyecto de Workspace.

* Algunas visualizaciones

  La mayoría de las visualizaciones se pueden incluir en las diapositivas que se generan a partir de un proyecto de Workspace. Sin embargo, las siguientes visualizaciones no se pueden incluir y se muestran atenuadas cuando se muestran las opciones de configuración:

   * Tabla de cohortes

   * Lienzo de recorrido

   * Viñeta

   * Combo

   * Disperso

   * Mapa de árbol

* Desgloses

* Análisis guiados


