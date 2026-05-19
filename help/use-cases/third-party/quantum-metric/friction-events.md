---
title: Añadir eventos de fricción de métricas cuánticas a Customer Journey Analytics
description: Agregue eventos de fricción recopilados de métricas cuánticas a los datos de comportamiento de Customer Journey Analytics para profundizar en las perspectivas en CJA.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
autotag-review: '2026-05-19T09:50:19.249Z'
TQID: 'https://experienceleague.adobe.com/ez4GO2CJ0g-nOGI4GlYrZQhuGKxQRvWoXPe4vcHGznU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c4147b6e-073b-4d3c-9ab1-d60f2f4434efid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 685
ht-degree: 1%

---

# Añadir eventos de fricción de métricas cuánticas a Customer Journey Analytics

La métrica cuántica recopila eventos de fricción como la lentitud de carga de la página, los errores de carga de página, los clics de ira, etc. Estos eventos se pueden pasar a Customer Journey Analytics como eventos complementarios en el recorrido del usuario. Con esta combinación de datos, puede comprender mejor el impacto de la fricción en las métricas descendentes.

## Requisitos previos:

Este caso de uso tiene dos requisitos:

* Debe tener derecho al paquete **operaciones de desarrollo** de la métrica cuántica.
* Debe utilizar etiquetas en la recopilación de datos de Adobe Experience Platform.

## Paso 1: Crear un campo de esquema para dar cabida a los eventos de fricción de métricas cuánticas

Este caso de uso requiere un campo de esquema dedicado al que enviar datos. Puede crear este campo en cualquier ubicación deseada del esquema y ponerle el nombre que desee. Se proporcionan valores de ejemplo si su organización no tiene preferencias en cuanto a nombre o ubicación.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Esquemas]**.
1. Seleccione el esquema que desee en la lista.
1. Seleccione el icono ![Agregar campo](/help/assets/icons/AddCircle.svg) junto al objeto deseado. Por ejemplo, junto a `Implementation Details`.
1. A la derecha, ingrese el [!UICONTROL Nombre] deseado. Por ejemplo, `qmErrorName`.
1. Escriba el [!UICONTROL nombre para mostrar] deseado. Por ejemplo, `Quantum Metric error name`.
1. Seleccione [!UICONTROL Type] como **[!UICONTROL String]**.
1. Seleccione **[!UICONTROL Guardar]**.

## Paso 2: Capturar eventos de fricción utilizando la extensión de etiqueta de métrica cuántica

Consulte [Extensión de métrica cuántica](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) en la guía Destinos de Adobe Experience Platform para obtener instrucciones sobre cómo configurar las etiquetas para incluir datos de métrica cuántica. El uso de esta extensión pasa más filas a un conjunto de datos existente.

Utilice etiquetas en la recopilación de datos de Adobe Experience Platform para definir manualmente el nombre del evento de fricción de modo que se pueda incluir en el objeto XDM y analizarse. Una forma de hacerlo es mediante el código personalizado de la regla:

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

A continuación, añada el elemento de datos definido dinámicamente al objeto XDM:

![Captura de pantalla del nombre de error de métrica cuántica](assets/error-name.png)

## Paso 3: Añadir una o más dimensiones y métricas a la vista de datos en Customer Journey Analytics

Edite la vista de datos existente para añadir el ID de sesión como una dimensión disponible en Customer Journey Analytics.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Vistas de datos]**, opcionalmente desde **[!UICONTROL Administración de datos]**, en el menú superior.
1. Seleccione la vista de datos existente que desee.
1. Busque la lista del campo de evento de fricción de métrica cuántica a la izquierda y arrástrela al área de métricas en el centro.
1. En el panel derecho, establezca la configuración [Incluir/Excluir valores](/help/data-views/component-settings/include-exclude-values.md) en los eventos de fricción que desee rastrear. Se pueden añadir varios eventos de fricción a la misma métrica para combinarlos. También puede arrastrar otra copia del campo de eventos de fricción al área de métricas para rastrear otros eventos de fricción como una métrica independiente.
1. Cuando haya creado todas las dimensiones y métricas deseadas, haga clic en **[!UICONTROL Guardar]**.
1. Para obtener una lista completa de los eventos de error, consulte la documentación de la métrica cuántica. Si tiene más preguntas, comuníquese con el representante de atención al cliente de la métrica cuántica o envíe una solicitud a través del [Portal de solicitudes de clientes de métricas cuánticas](https://community.quantummetric.com/s/public-support-page).

## Paso 4: Uso de la dimensión y las métricas con el resto de los datos en Analysis Workspace

Con los datos de eventos de fricción de métricas cuánticas recopilados junto con el resto de los datos de visitantes, puede utilizarlos exactamente como lo haría con cualquier otra dimensión o métrica en Customer Journey Analytics.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Workspace]** en el menú superior.
1. Seleccione un proyecto existente o cree un proyecto.
1. Crear [tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Arrastre las dimensiones y métricas deseadas al lienzo de Workspace para su análisis.

![Gráfico de fricción](assets/friction-graph.png)

Las posibles ideas de análisis incluyen:

* Tendencia de datos de eventos de fricción a lo largo del tiempo
* En una visualización de visitas en el orden previsto o funnel, añada eventos de Customer Journey Analytics como algunos pasos y eventos de fricción de métricas cuánticas como otros. Este informe permite ver dónde se producen los problemas más comunes de los visitantes.
* Cree y aplique un segmento para los visitantes que experimenten eventos de fricción para un análisis más profundo
