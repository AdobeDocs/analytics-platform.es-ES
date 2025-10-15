---
description: Aprenda a generar presentaciones en formato pptx a partir de informes de Workspace.
keywords: Analysis Workspace
title: Generar presentaciones desde informes de Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Narración de datos: Generar presentaciones de diapositivas a partir de informes de Workspace {#generate-powerpoint}

Puede generar automáticamente presentaciones .pptx desde proyectos de Analysis Workspace. Al generar presentaciones, Customer Journey Analytics identifica automáticamente las perspectivas clave y las convierte en diapositivas preparadas para las partes interesadas.

Esta funcionalidad reduce el tiempo y el esfuerzo necesarios para sacar a la luz los resultados de los proyectos de Workspace y le permite crear narrativas ejecutivas y comunicar el impacto comercial rápidamente.

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

1. Vaya al proyecto de Workspace que contiene los datos que desea utilizar como base para la presentación.

1. Seleccione **[!UICONTROL Generar diapositivas]** en la esquina superior derecha de la página.

1. Especifique la siguiente información:

   | Opción | Descripción |
   |---------|----------|
   | **[!UICONTROL Título de portada]** | Especifique un título para la presentación. Este título aparece en la diapositiva de título de la presentación. |
   | **[!UICONTROL Incluir nombre del moderador]** | Especifique el nombre del moderador. Este nombre aparece en la diapositiva de título de la presentación, debajo del título de la portada. |
   | **[!UICONTROL Paneles y visualizaciones que incluir]** | Elija los paneles y la visualización que desee incluir en la presentación. Puede incluir hasta 50 visualizaciones.<p>Se admiten la mayoría de los paneles y las visualizaciones. Para obtener información acerca de paneles y visualizaciones no compatibles, vea [Elementos y características de proyecto no compatibles](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Descripciones de paneles y visualizaciones]** | |
   | **[!UICONTROL Anotaciones]** | |
   | **[!UICONTROL Enfatizar componentes]** | Elija entre las visualizaciones hasta 5 métricas y 5 dimensiones que desee resaltar en la presentación.<p>Cuando no se aplica ningún énfasis, los componentes se muestran en las presentaciones de la siguiente manera:<ul><li>**Métricas y dimensiones:** Cursiva</li><li>**Elementos de Dimension:** Comillas</li></ul></p><p>Cuando se aplica énfasis, los componentes se muestran en las presentaciones de la siguiente manera:</p><ul><li>**Métricas y dimensiones:** Cursiva y negrita</li><li>**Elementos de Dimension:** Negrita cuando se enfatiza la dimensión correspondiente<p>También se aplica un color al elemento de dimensión cuando este se resalta en el gráfico.</p></li></ul> |

(Condicional) Seleccione **[!UICONTROL Tema predeterminado]** si desea que las diapositivas se generen con el tema predeterminado.

1. Seleccione si desea utilizar una temática predeterminada o cargar una plantilla personalizada:

   * **[!UICONTROL Tema predeterminado]**:

   * **[!UICONTROL Cargar plantilla]**:





## Editar diapositivas de una presentación generada anteriormente


## Descargar una presentación .pptx generada

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


