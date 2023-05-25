---
title: Embudo
description: Identificar áreas de fricción en una secuencia de pasos.
source-git-commit: 9c4ee66d35182cb89678ae868ff35e364df361a9
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# Embudo

{{release-limited-testing}}

El **Canal** [Tipo de análisis](overview.md) proporciona una representación visual de un recorrido de usuario crítico en el producto. El eje horizontal representa cada evento que un usuario debe tocar en orden. El eje vertical representa el porcentaje de usuarios o sesiones que tocaron cada evento. Todos los puntos de contacto deben realizarse en el orden previsto, pero pueden producirse en cualquier momento dentro de la ventana de creación de informes. Los casos de uso de este tipo de análisis incluyen:

* **Análisis de conversión**: El canal permite analizar las conversiones en cada fase del canal. Al rastrear el número de usuarios que progresan de un paso al siguiente, puede identificar cuellos de botella que tienen tasas de conversión inusuales o no deseadas. Esta información es valiosa para saber dónde puede mejorar el producto para obtener resultados inmediatos.
* **Optimización de incorporación**: el canal es útil para optimizar el proceso de incorporación del producto. Al examinar el comportamiento del usuario en torno a los eventos clave, puede identificar con qué pasos luchan los usuarios o no logran completarlos.
* **Adopción y participación de funciones**: el canal le ayuda a comprender cómo interactúan los usuarios con funciones específicas del producto. Al analizar la progresión de los usuarios a través de los pasos relacionados con las funciones, puede evaluar las tasas de adopción de las funciones e identificar las áreas en las que los usuarios pueden abandonar o infrautilizar determinadas funciones. A continuación, puede utilizar esta información para centrarse en las mejoras de las funcionalidades o la interfaz de usuario y aumentar las tasas de adopción.
* **Evaluación de campaña**: El canal puede ayudar a medir la eficacia de las campañas de marketing. Puede crear un segmento que se centre en los usuarios que han participado en una campaña determinada y comparar su proceso de conversión con otras campañas o con el producto en general.

[Captura de pantalla del embudo]

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **Pasos**: puntos de contacto del evento que desea rastrear. Cada barra del gráfico representa un paso. Se pueden incluir hasta diez pasos.
* **People**: Los segmentos con los que desea comparar el canal. Cada segmento seleccionado divide cada paso en varias barras. Cada color representa un segmento diferente. Se pueden incluir hasta tres segmentos.

## Tipos de vista

El canal ofrece los siguientes tipos de vista. Puede cambiar el tipo de vista mediante el menú desplegable situado en la parte superior izquierda del gráfico.

* **Fricción**: compare las tasas de conversión entre pasos.

## Ajustes del gráfico

El canal ofrece la siguiente configuración de gráfico. Puede ajustar la configuración del gráfico mediante el menú entre el tipo de vista y el selector de calendario.

* **Métrica**: La métrica que desea medir. Las opciones incluyen Sesiones y Usuarios.
* **Tipo de gráfico**: el tipo de visualización que desea utilizar. La única opción es Pasos.
* **Conversión de**: Determina el cálculo de porcentaje de paso a paso. Las opciones incluyen el cálculo de la conversión desde el primer paso o el paso anterior.

## Intervalo de fechas

La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas están disponibles para su comodidad o puede utilizar el selector de calendario para establecer la fecha exacta deseada.
