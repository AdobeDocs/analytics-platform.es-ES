---
title: Vista de fricción
description: Compare las tasas de conversión entre pasos.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 63dd68d31a9f2b907419fa660904f1dfdacaa0b8
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# [!UICONTROL Fricción] vista

El **[!UICONTROL Fricción]** La vista de proporciona una representación visual de un recorrido de usuario crítico en el producto. El eje horizontal representa cada paso que debe pasar un usuario. El eje vertical representa el porcentaje de usuarios o sesiones en cada paso. Todos los pasos deben realizarse en el orden previsto, pero pueden producirse en cualquier momento dentro de la ventana de creación de informes.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Análisis de conversión**: Puede analizar las conversiones en cada fase del canal, por ejemplo, un cierre de compra minorista, el registro de una cuenta, el flujo de suscripción o cualquier otro recorrido crítico dentro de la experiencia del producto. Al rastrear el número de usuarios que progresan de un paso al siguiente, puede identificar cuellos de botella que tienen tasas de conversión inusuales o no deseadas. Esta información es valiosa para saber dónde puede mejorar el recorrido del producto para obtener resultados inmediatos.
* **Análisis de experimentación**: puede comparar las tasas de conversión en un canal que tenga pasos opcionales o pasos en los que se esté ejecutando un experimento A/B. Esta información puede ayudarle a determinar qué variación del canal conduce a la tasa de conversión más alta, de modo que pueda animar a más usuarios en ese camino.
* **Optimización de incorporación**: optimice el proceso de incorporación de su producto examinando el comportamiento del usuario en torno a los eventos clave. Puede identificar con qué pasos luchan los usuarios o no logran completarlos.
* **Adopción y participación de funciones**: comprenda cómo los usuarios interactúan con funciones específicas del producto. El análisis de la progresión de los usuarios a través de pasos relacionados con las funciones le permite ver las tasas de adopción e identificar áreas en las que los usuarios podrían infrautilizar determinadas funciones. A continuación, puede utilizar esta información para centrarse en las mejoras de funciones y aumentar las tasas de adopción.
* **Eficacia del canal de marketing**: mida la eficacia de los canales de marketing. Puede crear un segmento centrado en usuarios que interactuaron con diferentes canales de marketing (por ejemplo, búsqueda de pago, visualización, búsqueda natural o directa) y luego comparar sus recorridos para ver qué canal ofrece los mejores resultados de producto.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Ver]**: cambie entre este tipo de vista y [Tendencias de conversión](conversion-trends.md).
* **[!UICONTROL Pasos]**: los puntos de contacto del evento que desea rastrear. Cada barra del gráfico representa un paso. Se pueden incluir hasta diez pasos.
   * [!UICONTROL Comparar]: Cada paso proporciona una opción para comparar varios eventos en un solo paso de canal, lo que crea un &quot;embudo ramificado&quot;. Esta función le permite comparar la fricción de dos recorridos en paralelo sin crear dos análisis independientes. Resulta útil cuando hay opciones de paso o cuando se está ejecutando un experimento A/B dentro del canal.
* **[!UICONTROL Contabilizado como]**: el ámbito que desea aplicar al canal. Las opciones incluyen [!UICONTROL Sesiones] y [!UICONTROL Usuarios].
   * [!UICONTROL Sesiones]: todos los pasos deben realizarse dentro de la misma sesión para que se cuenten.
   * [!UICONTROL Usuarios]: todos los pasos deben realizarse dentro de la ventana de creación de informes seleccionada para que se puedan contar.
* **[!UICONTROL Segmentos]**: Los segmentos con los que desea comparar el canal. Cada segmento seleccionado divide cada paso en varias barras. Cada color representa un segmento diferente. Se pueden incluir hasta tres segmentos.

## Ajustes del gráfico

La vista de fricción ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Pasos].
* **[!UICONTROL Conversión de]**: Determina el cálculo de porcentaje de paso a paso. Las opciones incluyen calcular la conversión desde el [!UICONTROL Primer paso] o [!UICONTROL Paso anterior].

## Comparación del tiempo

{{apply-time-comparison}}

![Comparación del tiempo de fricción](../assets/friction-compare.png){style="border:1px solid gray"}

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Esta configuración no afecta a las vistas sin tendencias, como Fricción.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
