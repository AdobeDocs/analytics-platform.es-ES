---
description: Utilice subtítulos inteligentes para generar perspectivas en lenguaje natural y mostrar rápidamente las tendencias dentro de las visualizaciones.
title: Pies de ilustración inteligentes
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# Pies de ilustración inteligentes

Los subtítulos inteligentes utilizan aprendizaje automático avanzado e IA generativa para proporcionar información valiosa en lenguaje natural para las visualizaciones de Workspace. La versión inicial proporciona perspectivas generadas automáticamente para el [Línea](line.md) visualización. (A continuación se muestran otras visualizaciones).

Los subtítulos inteligentes están orientados a:

* Analistas que necesitan narrativas para compartir con otros usuarios. Los analistas necesitan estas perspectivas para poder proporcionar contexto a sus usuarios.
* Usuarios empresariales que deseen descubrir rápidamente ofertas para llevar de alto nivel.

Los subtítulos están disponibles para todos los usuarios de Customer Journey Analytics y no requieren permisos especiales.

## Iniciar subtítulos inteligentes {#launch}

Para iniciar subtítulos generados automáticamente para una visualización de líneas, haga clic en **[!UICONTROL Subtítulos inteligentes]** en la parte superior derecha de la visualización.

![Inicie la ventana de análisis que muestra los subtítulos inteligentes de la tendencia de vistas del producto. ](assets/intell-caps-1.png)

Ahora se están generando perspectivas en lenguaje natural.

Tenga en cuenta que

* Necesita un mínimo de 3 puntos de datos para que los subtítulos se generen correctamente. De lo contrario, podría recibir un error que dice &quot;No hay suficientes datos para analizar&quot;.

* Los subtítulos se generan cada vez que los datos seleccionados subyacentes cambian en la tabla que alimenta la visualización.

* Si hay varias métricas en la tabla, los subtítulos solo se generan para la primera métrica o la métrica seleccionada actualmente por el usuario.

* Si guarda el proyecto en este punto y lo vuelve a cargar más adelante, los subtítulos se actualizan automáticamente con nuevos datos. Lo mismo se aplica a los proyectos programados y a los archivos de PDF exportados desde este proyecto.

## Ver e interpretar subtítulos {#view}

A continuación se muestra un ejemplo del aspecto que podrían tener los subtítulos:

![Subtítulos inteligentes para la visualización de líneas, incluidos Estacionalidad, Mínimo, Máximo, Pico y Rechazar.](assets/captions.png)

## Copiar al portapapeles {#copy}

Puede copiar los subtítulos en un portapapeles y pegarlos en una herramienta Powerpoint u otra. Busque el **[!UICONTROL Copiar subtítulos en el portapapeles]** en la parte superior derecha del cuadro de diálogo subtítulos.

## Editar subtítulos {#edit}

Puede editar los subtítulos, como ocultar o mostrar una categoría particular de perspectivas. Por ejemplo, si no desea conocer el orden mínimo, puede ocultarlo y hacer clic en Aplicar para que no se vuelva a mostrar.

1. Clic **[!UICONTROL Editar visualización de subtítulos inteligentes]** junto al icono del portapapeles.

1. En el cuadro de diálogo de edición, haga clic en el icono del ojo junto a la perspectiva que desee ocultar.

1. Haga clic en **[!UICONTROL Aplicar]**.

Utilice el mismo proceso para mostrar los subtítulos.

## Exportar subtítulos {#export}

Puede **exportar subtítulos mediante PDF**, siempre que el proyecto se guarde con los subtítulos generados.

## Alternar subtítulos desactivada {#toggle}

Si no desea que se generen subtítulos inteligentes, puede desactivar esta función en Preferencias de visualización y desmarcar **[!UICONTROL Mostrar subtítulos inteligentes]**.

![Opciones de visualización de líneas que muestran la opción para desactivar Mostrar subtítulos inteligentes.](assets/toggle-captions.png)

## Subtítulos inteligentes en cuadros de resultados móviles

Los subtítulos inteligentes también están disponibles en Customer Journey Analytics [cuadros de resultados móviles](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).