---
title: Vista Cronología
description: Explore los patrones de actividad de la sesión.
feature: Guided Analysis
keywords: análisis de productos
role: User
source-git-commit: 5cd54973b08285badbedce273ac28371158f194c
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 2%

---

# [!UICONTROL Cronología] vista

El **[!UICONTROL Cronología]** Esta vista permite analizar sesiones individuales para determinar patrones de comportamiento. El carril derecho permite seleccionar un ID de persona para su análisis. El área central muestra la hora, el valor de la propiedad y la duración de esa persona.

Este análisis requiere que agregue la variable **[!UICONTROL ID de persona]** componente estándar a la [vista de datos](/help/data-views/component-reference.md#optional). Si no tiene el [!UICONTROL ID de persona] componente añadido a la vista de datos, se muestra el siguiente mensaje:

> La propiedad PersonID es necesaria para este análisis. Agregue PersonID a la vista de datos.

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Exploración por fricción**: Si encuentra una caída pronunciada en el [Fricción](friction.md) , puede investigar las posibles causas de esa colocación mediante esta vista.
* **Comportamiento del error**: Si los usuarios encuentran un error en el producto, puede explorar qué hacen antes o después de ver ese error.
* **Validación de recopilación de datos**: los administradores de datos pueden filtrar esta vista para aislarse. Esta vista proporciona una forma sólida de asegurarse de que la implementación de su organización funciona según lo esperado.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Propiedad]**: propiedad para la que desea ver los valores. El análisis de sesión en el centro muestra los valores de la propiedad seleccionada aquí. También puede filtrar los datos por la propiedad seleccionada. Los operadores válidos para el filtro incluyen [!UICONTROL Igual a], [!UICONTROL No es igual a], [!UICONTROL Comienza por], [!UICONTROL Finaliza con], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Existe], y [!UICONTROL No existe].
* **[!UICONTROL Segmentos]**: El segmento que desea medir. El segmento seleccionado filtra los datos para centrarse únicamente en las personas que coinciden con los criterios del segmento. Se admite un segmento para esta vista.

## Ajustes del gráfico

El [!UICONTROL Cronología] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Mostrar como]**: Muestra los valores de propiedad deseados.
   * [!UICONTROL Mostrar todo]
   * [!UICONTROL Resaltar]
   * [!UICONTROL Solo vista]

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencia. Esta configuración no afecta a las vistas sin tendencias como Frecuencia.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
