---
title: Vista de frecuencia
description: Medir la participación en función de la frecuencia de uso.
feature: Guided Analysis
keywords: análisis de productos
source-git-commit: 1e095720301f3e59e88674d086f5e0de9df88872
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 3%

---

# [!UICONTROL Frecuencia] vista

El **[!UICONTROL Frecuencia]** ver datos de eventos de grupos según la frecuencia con la que se ve un evento. El eje vertical de este informe contiene bloques que representan la frecuencia de los eventos vistos. El eje horizontal mide el número de usuarios o sesiones para cada bloque.

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Participación**: efectúe el seguimiento de la participación de los usuarios en cualquier evento. Puede hacer clic en una barra horizontal para guardarla como un segmento. Los segmentos para bloques de participación bajos pueden ayudarle a determinar por qué los usuarios no interactúan con el evento con la frecuencia deseada. Los segmentos para bloques de participación altos pueden ayudarle a comprender por qué los usuarios interactúan con el evento a menudo. A partir de ahí, puede animar a otros usuarios a adoptar un comportamiento similar.
* **Lealtad del cliente**: configure el evento en Pedidos y la métrica en Usuarios. Este informe permite agrupar a los usuarios según la cantidad de veces que han realizado una compra en el sitio dentro del intervalo de fechas especificado.
* **Optimización de soporte**: Ver este informe por número de llamadas de asistencia o casos abiertos puede proporcionarle una perspectiva sobre los usuarios que encuentran la mayor cantidad de problemas. A continuación, puede crear un segmento para centrarse en su experiencia y ayudar a identificar y resolver sus problemas.
* **Servicios de suscripción**: Este informe es útil para las organizaciones que tienen servicios de suscripción. Es más probable que se pierdan usuarios con poca participación, por lo que puede ver este informe para analizar el comportamiento de los usuarios con un alto nivel de participación. Comprender el comportamiento de los usuarios con un alto nivel de participación puede ayudar a fomentar un comportamiento similar para los usuarios con un bajo nivel de participación, lo que les hace menos propensos a cancelar su suscripción.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Eventos]**: los eventos que desea medir. Cada evento seleccionado se representa como un gráfico independiente. Se agrega a la tabla una fila que representa el evento de tendencias. Se pueden incluir hasta cinco eventos.
* **[!UICONTROL People]**: Los segmentos que desea medir. Cada segmento seleccionado duplica el número de líneas del gráfico y las filas de la tabla. Se pueden incluir hasta cinco segmentos.

## Ajustes del gráfico

El [!UICONTROL Frecuencia] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Métrica]**: La métrica que desea medir. Las opciones incluyen [!UICONTROL Usuarios] y [!UICONTROL Sesiones].
* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra horizontal] y [!UICONTROL Barra apilada].

## Configuración del depósito

Determina cómo se clasifica el evento en grupos.

* **[!UICONTROL Bloques automáticos]**: Identifique automáticamente el tamaño de bloque óptimo en función de la distribución de datos.
* **[!UICONTROL Bloques personalizados]**: Controle la forma en que el informe agrupa los datos en bloques.
   * [!UICONTROL Desde]: el primer bloque. La frecuencia menor que este valor se excluye de los informes.
   * [!UICONTROL Hasta]: La frecuencia mayor que este valor se agrupa en el último bloque.
   * [!UICONTROL Tamaño]: El intervalo del contenedor.

## Aplicar comparación de tiempo

{{apply-time-comparison}}

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Esta configuración no afecta a las vistas sin tendencias como Frecuencia.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
