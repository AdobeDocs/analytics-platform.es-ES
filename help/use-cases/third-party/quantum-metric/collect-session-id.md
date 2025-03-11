---
title: Recopilación de ID de sesión de métricas cuánticas en Customer Journey Analytics
description: Modifique la implementación para incluir los ID de sesión y poder analizarlos en Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: 2d6c5d5b546ef8ba952d4ba4397d897ed4566283
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Recopilación de ID de sesión de métricas cuánticas en Customer Journey Analytics

Algunos casos de uso, como [vinculación de repeticiones de sesión de métrica cuántica](tie-session-replays.md) o [uso de mapas de calor de métrica cuántica](heatmap.md) requieren que modifique la implementación para recopilar el ID de sesión de métrica cuántica. Esta página describe ese proceso para incorporar correctamente esos datos en la implementación existente.

En estos pasos se da por hecho que utiliza etiquetas en la recopilación de datos de Adobe Experience Platform. Puede adaptar estos métodos de recopilación de datos a una implementación manual de Web SDK si su organización no utiliza etiquetas.

## Paso 1: Recopilar el ID de sesión de métrica cuántica con la extensión de etiquetas de métrica cuántica

Siga estos pasos para anexar el ID de sesión de métrica cuántica a los datos que envía a Adobe Experience Platform.

1. Utilice la extensión de métrica cuántica en la interfaz de usuario de etiquetas para enviar datos a la métrica cuántica.
1. Cree cuatro elementos de datos:
   1. Uno que captura el identificador de sesión de la métrica cuántica de la cookie de métrica cuántica llamada `QuantumMetricSessionID`
   1. Una que extrae el identificador de sesión de métrica cuántica de `localStorage`. A veces, este elemento de datos se carga más rápido que la cookie establecida en el otro elemento de datos.
   1. Utilice el asistente de elementos de datos o JavaScript personalizado para extraer el nodo `s` del elemento de datos `localStorage`.
   1. Una que utilice la lógica para buscar primero el elemento de datos de cookie y devolverlo a una ruta de objeto XDM si se encuentra. Si no está definido, intente buscar en el elemento de datos de objeto `localStorage` extraído.
1. Envíe el elemento de datos final ID de sesión de métrica cuántica al objeto XDM enviado en cada evento.

>[!NOTE]
>A veces, Web SDK se ejecuta más rápido que el código de métrica cuántica. En estos casos, el ID de sesión se envía en la visita posterior. Si un visitante regresa, el ID de sesión no se recopila en estas instancias.

Consulte la documentación de la [extensión de etiqueta de métrica cuántica](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) para obtener más información.

## Paso 2: Confirmar los campos del conjunto de datos incluidos

Confirme que los conjuntos de datos de la conexión ahora tienen el ID de sesión de métrica cuántica en el conjunto de datos deseado.

## Paso 3: Añadir el ID de sesión de métrica cuántica como dimensión disponible

Edite la vista de datos existente para añadir el ID de sesión como una dimensión disponible en Customer Journey Analytics.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Vistas de datos]** en el menú superior.
1. Seleccione la vista de datos existente que desee.
1. Busque la lista ID de sesión de métrica cuántica a la izquierda y arrástrela al área de dimensiones en el centro.
1. En el panel derecho, establezca la configuración [persistencia](/help/data-views/component-settings/persistence.md) en &#39;Sesión&#39;.
1. Haga clic en **[!UICONTROL Guardar]**.


