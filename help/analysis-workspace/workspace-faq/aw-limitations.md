---
description: Lista de limitaciones conocidas en Adobe Analysis Workspace y componentes relacionados
title: Limitaciones conocidas
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
TQID: https://experienceleague.adobe.com/rbguvYCSFfbmMVr5IBC1M9OD0wDIG0Z4p28Z2dOerBc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 100%

---

# Limitaciones conocidas

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
* Segmentos ad hoc creados en la [zona desplegable del panel](/help/analysis-workspace/c-panels/panels.md) son un tipo de segmento rápido. No aparecen en la barra izquierda de Workspace ni en el Administrador de componentes del segmento, a menos que se hagan públicos. Para obtener más información, consulte [Segmentos rápidos](/help/components/segments/seg-quick.md).

## Métricas calculadas

* Las métricas calculadas no se pueden usar en determinadas visualizaciones. Consulta [Visualizaciones](#visualizations).
* Las métricas calculadas no se pueden usar en el panel de [!UICONTROL Attribution], ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Determinados componentes y operadores no están disponibles si se crea una métrica calculada desde Workspace (en lugar de hacerlo desde [!UICONTROL Componentes > Segmentos]). Por ejemplo, [!UICONTROL Dirección IP].

## Intervalos de fechas

* Los intervalos de fechas personalizados no admiten [!UICONTROL Este día del año pasado], [!UICONTROL Este día del mes pasado], etc.


## Configuración de informes

* Algunas de las opciones de la página [!UICONTROL Configuración de informes] no se aplican. Analysis Workspace solo utiliza la configuración de [!UICONTROL Idioma, moneda y codificación] de la parte inferior: [!UICONTROL Separador de miles], [!UICONTROL Codificación de informes programados] y [!UICONTROL Carácter separador de CSV].

