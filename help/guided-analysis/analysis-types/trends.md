---
title: Tendencias
description: Encuentre patrones y cambios en la participación del usuario a lo largo del tiempo.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 2%

---

# Tendencias

{{release-limited-testing}}

El **Tendencias** [Tipo de análisis](overview.md) proporciona una valiosa perspectiva sobre el rendimiento del producto o el comportamiento de los usuarios a lo largo del tiempo. El eje horizontal de este informe siempre es una granularidad de tiempo, mientras que el eje vertical mide los eventos deseados. Los casos de uso de este tipo de análisis incluyen:

* **Evaluar el rendimiento del producto**: las tendencias permiten evaluar el rendimiento general del producto durante un periodo determinado. Al analizar métricas como la participación del usuario, las tasas de conversión o los ingresos, puede identificar si el rendimiento del producto mejora, se estanca o disminuye.
* **Adopción de funciones**: las tendencias le permiten comprender cómo adoptan los usuarios las nuevas funciones o actualizaciones que usted publique. Puede determinar qué funciones son populares y qué funciones requieren mejora. Esta información le permite tomar decisiones basadas en datos sobre qué funciones priorizar los esfuerzos de desarrollo.
* **Comportamiento del usuario**: las tendencias pueden proporcionar una perspectiva del comportamiento del usuario a lo largo del tiempo. Al examinar las acciones específicas que realizan los usuarios, puede identificar patrones en los que estos pueden abandonarlos. Puede combinar las perspectivas de este tipo de análisis con una [Canal](funnel.md) para obtener aún más información sobre el comportamiento.
* **Pruebas y experimentación A/B**: si ejecuta pruebas A/B en su producto, puede utilizar Tendencias para medir qué pruebas son las más exitosas con el paso del tiempo.

[Captura de pantalla de tendencias]

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **Eventos**: los eventos que desea medir en el informe. Cada evento seleccionado aquí se representa como una línea de color o como un conjunto de barras, según el tipo de gráfico. Se agrega a la tabla una fila que representa el evento de tendencias. Se pueden incluir hasta cinco eventos.
* **People**: Los segmentos que desea medir en el informe. Cada segmento seleccionado aquí duplica el número de líneas del gráfico y las filas de la tabla. Cada conjunto de eventos se representa para cada segmento. Se pueden incluir hasta cinco segmentos.

## Tipos de vista

Las tendencias ofrecen los siguientes tipos de vista. Puede cambiar el tipo de vista mediante el menú desplegable situado en la parte superior izquierda del gráfico.

* **Uso:** Mida la participación del usuario con el tiempo.

## Ajustes del gráfico

Las tendencias ofrecen la siguiente configuración de gráfico. Puede ajustar la configuración del gráfico mediante el menú entre el tipo de vista y el selector de calendario.

* **Métrica**: La métrica que desea medir. Las opciones incluyen Eventos, Sesiones, Usuarios, Eventos por sesión y Eventos por usuario.
* **Tipo de gráfico**: el tipo de visualización que desea utilizar. Las opciones incluyen Línea, Barra, Barra apilada y Área apilada.

## Aplicar comparación de tiempo

Las tendencias ofrecen la capacidad de comparar el período de tiempo actual con un período de tiempo anterior. Si selecciona una opción en este menú, cada línea recibe una línea de puntos de color similar. Esta línea de puntos representa la misma métrica en el intervalo de fechas anterior seleccionado. Al establecer esta opción, se duplica el número de líneas del gráfico y de filas de la tabla.

Las opciones de comparación de tiempo disponibles incluyen el periodo anterior, 13 semanas antes, 52 semanas antes y un intervalo de fechas personalizado. Si selecciona Intervalo de fechas personalizado, aparecen opciones adicionales para permitirle seleccionar el número y la granularidad. Si selecciona Ninguno, se elimina la comparación de fechas.

## Intervalo de fechas

Establece el intervalo de fechas deseado. Hay dos componentes importantes en esta configuración:

* **Intervalo**: La granularidad de fecha en la que desea ver los datos. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **Fecha**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas están disponibles para su comodidad o puede utilizar el selector de calendario para establecer la fecha exacta deseada.
