---
description: Lista de limitaciones conocidas en Adobe Analysis Workspace y componentes relacionados
title: Limitaciones conocidas en Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 93%

---

# Limitaciones conocidas en Analysis Workspace

Esta es una lista de limitaciones conocidas en Analysis Workspace y sus componentes relacionados:

## Tablas

* No se pueden agregar columnas de comparación de fechas cuando se utilizan intervalos de fechas o métricas como filas de una tabla.
* La creación de métricas a partir de una selección se desactiva cuando los segmentos se utilizan como filas de una tabla. Además, la creación de una métrica a partir de una selección no debe aplicarse a columnas alineadas con la fecha.
* El formato condicional de las filas de desglose no puede utilizar intervalos personalizados.
* Las filas totales de la tabla no pueden incluir tendencias cuando se calculan los totales sumando la configuración de valores de fila (generalmente se utiliza con elementos de fila estáticos).

## Visualizaciones

* Las visualizaciones que aprovechan segmentos, como [!UICONTROL Visita en orden previsto], [!UICONTROL Flujo], [!UICONTROL Cohorte] y [!UICONTROL Histograma], no pueden aceptar métricas calculadas como entradas.
* [!UICONTROL Flujo]: Las dimensiones de entrada y salida, por ejemplo: [!UICONTROL página de entrada], no se pueden usar en Flujos.
* [!UICONTROL Cohorte]: Los números no enteros no se pueden usar como criterios de cohorte.

## Segmentos 

* Ciertas métricas y dimensiones no se pueden segmentar, como [!UICONTROL Eventos], [!UICONTROL Personas], etc.
* Segmentos ad hoc creados en la [zona desplegable del panel](/help/analysis-workspace/c-panels/panels.md) son un tipo de segmento rápido. No aparecen en el panel izquierdo de Workspace ni en el Administrador de segmentos a menos que se hagan públicos. Para obtener más información, consulte [Segmentos rápidos](/help/components/filters/quick-filters.md).

## Métricas calculadas 

* Las métricas calculadas no se pueden usar en determinadas visualizaciones. Consulta [Visualizaciones](#visualizations).
* Las métricas calculadas no se pueden usar en el panel de [!UICONTROL Attribution], ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Determinados componentes y operadores no están disponibles si se crea una métrica calculada desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes > Segmentos]). Por ejemplo, [!UICONTROL Dirección IP].

## Intervalos de fechas

* Los intervalos de fechas personalizados no admiten [!UICONTROL Este día del año pasado], [!UICONTROL Este día del mes pasado], etc.


## Configuración de informes

* Algunas de las opciones de la página [!UICONTROL Configuración de informes] no se aplican. Analysis Workspace solo utiliza la configuración de [!UICONTROL Idioma, moneda y codificación] de la parte inferior: [!UICONTROL Separador de miles], [!UICONTROL Codificación de informes programados] y [!UICONTROL Carácter separador de CSV].

