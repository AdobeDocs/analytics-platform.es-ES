---
description: Lista de limitaciones conocidas en Adobe Analysis Workspace y componentes relacionados
title: Limitaciones conocidas en Analysis Workspace
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 69%

---

# Limitaciones conocidas en Analysis Workspace

Esta es una lista de limitaciones conocidas en Analysis Workspace y sus componentes relacionados:

## Tablas

* No se pueden agregar columnas de comparación de fechas cuando se utilizan intervalos de fechas o métricas como filas de una tabla.
* La creación de métricas a partir de la selección se desactiva cuando los filtros se utilizan como filas de una tabla. Además, la creación de una métrica a partir de una selección no debe aplicarse a columnas alineadas con la fecha.
* El formato condicional de las filas de desglose no puede utilizar intervalos personalizados.
* Las filas totales de la tabla no pueden incluir tendencias cuando se calculan los totales sumando la configuración de valores de fila (generalmente se utiliza con elementos de fila estáticos).
* [!UICONTROL El análisis de contribución] se puede ejecutar _solo_ con la granularidad [!UICONTROL diaria]. No se puede ejecutar con datos [!UICONTROL por hora], [!UICONTROL semanales], etc.

## Visualizaciones

* Las visualizaciones que aprovechan filtros como [!UICONTROL Visitas en el orden previsto], [!UICONTROL Flujo], [!UICONTROL Cohorte] e [!UICONTROL Histograma] no pueden aceptar las métricas calculadas como entradas.
* [!UICONTROL Flujo]: Las dimensiones de entrada y salida, por ejemplo: [!UICONTROL página de entrada], no se pueden usar en Flujos.
* [!UICONTROL Cohorte]: Los números no enteros no se pueden usar como criterios de cohorte.

## Componentes > Filtros

* Ciertas métricas y dimensiones no se pueden filtrar, como [!UICONTROL Ocurrencias], [!UICONTROL Visitantes únicos], etc.
* Los filtros específicos creados en la [zona desplegable del panel](/help/analysis-workspace/c-panels/panels.md) no aparecerán en el carril izquierdo de Workspace ni en el administrador de componentes de filtro, a menos que se hagan públicos. Esto se puede hacer editando el filtro y seleccionando **[!UICONTROL Convertir este filtro en público]**.

## Componentes > Métricas calculadas

* Las métricas calculadas no se pueden usar en determinadas visualizaciones. Consulte “Visualizaciones”.
* Las métricas calculadas no se pueden usar en el panel de [!UICONTROL Attribution], ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Ciertos componentes y operadores no están disponibles si se crea una métrica calculada desde Workspace (en lugar de hacerlo desde [!UICONTROL Components > filters]). Por ejemplo, [!UICONTROL Dirección IP].

## Componentes > Intervalos de fechas

* Los intervalos de fechas personalizados no admiten [!UICONTROL Este día del año pasado], [!UICONTROL Este día del mes pasado], etc.


## Componentes > Configuración de informes

* Algunas de las opciones de la página [!UICONTROL Configuración de informes] no se aplican. Analysis Workspace solo utiliza la configuración de [!UICONTROL Idioma, moneda y codificación] de la parte inferior: [!UICONTROL Separador de miles], [!UICONTROL Codificación de informes programados] y [!UICONTROL Carácter separador de CSV].

## Attribution IQ

* Un subconjunto de métricas no se admite en [!UICONTROL Attribution IQ]. Para obtener una lista completa, consulte las [preguntas más frecuentes sobre Attribution IQ](../attribution/faq.md).
