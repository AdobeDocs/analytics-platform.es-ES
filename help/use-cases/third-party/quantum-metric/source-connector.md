---
title: Añadir datos de métricas cuánticas a Customer Journey Analytics
description: Utilice la métrica cuántica para la recopilación de datos de recorridos y conductas de usuarios y, a continuación, saque el CJA de esos datos recopilados para obtener perspectivas más ricas.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Añadir datos de métricas cuánticas a Customer Journey Analytics

>[!IMPORTANT]
>
>El conector de origen de la métrica cuántica aún no está disponible en este momento.

CJA desbloquea el control de tiempo del informe de los datos de QM, el análisis secuencial de datos, la atribución enriquecida y otros informes avanzados.  QM se puede enviar a AEP mediante el conector de origen de QM o la extensión de etiquetas de métricas cuánticas.

## Paso 1: Crear un conector de origen de métrica cuántica

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a [!UICONTROL Experience Platform] > [!UICONTROL Conexiones] > [!UICONTROL Fuentes].
1. Agregue el conector de origen de la métrica cuántica y siga las indicaciones hasta la finalización.

Consulte [Conectores de origen de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) para obtener más información.

## Paso 2: Crear una conexión en Customer Journey Analytics

Al crear un conector de origen para datos de métricas cuánticas se crea automáticamente un conjunto de datos en Adobe Experience Platform. Agregue este conjunto de datos a una [conexión](/help/connections/overview.md) nueva o existente en Customer Journey Analytics.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Conexiones]** en el menú superior.
1. Asigne un nombre a la conexión y agregue el conjunto de datos de métrica cuántica a la conexión.
1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>Aunque puede agregar datos de métricas cuánticas a la misma conexión que el resto de los datos de Customer Journey Analytics, esos datos no se pueden vincular sin un ID de persona común entre los dos conjuntos de datos. Si se desea este comportamiento, Adobe recomienda usar la [extensión Tag](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) en lugar del conector de origen.

## Paso 3: Crear una vista de datos en Customer Journey Analytics

Cree una [vista de datos](/help/data-views/data-views.md) para establecer la configuración de dimensiones y métricas.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Vistas de datos]** en el menú superior.
1. Seleccione la vista de datos que desee o cree una vista de datos.
1. Busque las dimensiones y métricas deseadas de la Métrica cuántica en la lista de campos de esquema de la derecha y arrástrelas al área de dimensiones y métricas en el centro.
1. Utilice el panel derecho para configurar cada dimensión y métrica deseadas.

## Paso 4: Inicio de los informes y análisis en Customer Journey Analytics

Ahora que los datos están disponibles en Customer Journey Analytics, puede empezar a crear informes con los datos.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Workspace]** en el menú superior.
1. Seleccione un proyecto existente o cree un proyecto.
1. Arrastre cualquier dimensión o métrica de métrica cuántica deseada al lienzo de Workspace para analizar los datos.
