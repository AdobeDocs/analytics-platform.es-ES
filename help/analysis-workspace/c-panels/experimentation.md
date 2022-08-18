---
description: Obtenga información sobre cómo analizar los resultados de las pruebas A/B en el panel Experimentación con CJA.
title: Panel de experimentación
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# Panel de experimentación

>[!NOTE]
>
>Actualmente, esta funcionalidad está en [prueba limitada](/help/release-notes/releases.md).

La variable **[!UICONTROL Experimento]** permite comparar diferentes variaciones de experiencia del usuario, marketing o mensajería para determinar cuál es la mejor opción para obtener un resultado específico. Puede evaluar el alza y la confianza de cualquier experimento A/B desde cualquier plataforma de experimentación: en línea, sin conexión, desde soluciones de Adobe, Adobe Journey Optimizer e incluso datos de BYO (que le aporten sus propios).

>[!IMPORTANT]
>
>En este punto, [Adobe Analytics para Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=es) Los datos (A4T) no se pueden evaluar en la variable [!UICONTROL Experimento] panel.

## Control de acceso

El panel Experimento está disponible para todos los usuarios de Customer Journey Analytics (CJA). No se requieren derechos de administrador ni otros permisos. Sin embargo, la configuración requiere etiquetas en vistas de datos que solo los administradores pueden asignar.

## Terminología

* **Experimento**: Un experimento es un conjunto de variaciones de una experiencia que se expusieron a los usuarios finales para determinar cuál es mejor mantener a perpetuidad. Un experimento consta de dos o más variaciones, una de las cuales se considera la variación de control.

* **Variación**: Una de las dos o más alteraciones en la experiencia de un usuario final que se están comparando con el fin de identificar la mejor alternativa. Se debe seleccionar una variación como control y solo se puede considerar que una variación es la variación de control.

* **Control**: Variación específica que representa el estado actual o el estado predeterminado de la experiencia de un usuario. A qué se comparan todas las demás variaciones.

* **Métrica de normalización**: Base (sesiones o personas) en la que se ejecutará una prueba. Por ejemplo, una prueba puede comparar las tasas de conversión de varias variaciones en las que la tasa de conversión se calcula como conversiones por sesión o conversiones por persona.

* **Métrica de conversión**: La métrica con la que un usuario compara variaciones. La variación con el resultado más deseable para la métrica de conversión (ya sea la más alta o la más baja) se declara como &quot;ganadora&quot; de un experimento.

## Paso 1: Crear conexión para experimentar conjuntos de datos

Una vez que se hayan añadido los datos del experimento [ingested](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) en Adobe Experience Platform, [crear una conexión en CJA](/help/connections/create-connection.md) a uno o más conjuntos de datos de experimento.

## Paso 2: Adición de etiquetas de contexto en vistas de datos

En la configuración de vistas de datos de CJA, los administradores pueden agregar [etiquetas de contexto](/help/data-views/component-settings/overview.md) a una dimensión o métrica y servicios de CJA como [!UICONTROL Experimento] puede utilizar estas etiquetas para sus fines. Para el panel Experimento se utilizan dos etiquetas predefinidas:

* [!UICONTROL Experimento]
* [!UICONTROL Variant]

En la vista de datos que contiene datos de experimentación, elija dos dimensiones, una con los datos de experimentación y otra con los datos de variante. A continuación, etiquete esas dimensiones con la etiqueta **[!UICONTROL Experimento]** y **[!UICONTROL Variant]** etiquetas.

![etiqueta de contexto](assets/context-label.png)

Sin estas etiquetas presentes, el panel Experimento no funciona.

## Paso 3: Configuración del panel Experimento

1. En CJA Workspace, arrastre el panel Experimentación a un proyecto.

![panel de experimento](assets/experiment.png)




