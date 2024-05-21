---
title: Vista de frecuencia
description: Mida la participación en función de la frecuencia de uso.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: 481e52bbfe06268642522b908f9b7ac66c882433
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 6%

---

# [!UICONTROL Frecuencia] vista

El **[!UICONTROL Frecuencia]** ver datos de eventos de grupos según la frecuencia con la que se producen eventos en el producto. El eje vertical de esta vista contiene bloques que representan la frecuencia del evento. El eje horizontal mide el número de usuarios o sesiones para cada bloque.

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?learn=on)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Participación**: efectúe el seguimiento de la participación de los usuarios en cualquier evento del producto. Puede hacer clic en cualquier parte del gráfico de barras para guardarla como un segmento. Los segmentos para bloques de participación bajos pueden ayudarle a determinar por qué los usuarios no interactúan con el evento con la frecuencia deseada. Los segmentos para bloques de participación altos pueden ayudarle a comprender por qué los usuarios interactúan con el evento a menudo. A partir de ahí, puede animar a otros usuarios a adoptar un comportamiento similar.
* **Lealtad del cliente**: configure el evento en Pedidos y la métrica en Usuarios. Esta vista le permite agrupar usuarios según la cantidad de veces que han realizado una compra en el sitio dentro del intervalo de fechas especificado.
* **Optimización de soporte**: vea el número de llamadas de asistencia o casos abiertos por usuario para obtener información sobre los usuarios que encuentran la mayor cantidad de problemas. A continuación, puede crear un segmento para centrarse en su experiencia y ayudar a identificar y resolver sus problemas.
* **Servicios de suscripción**: Es más probable que los usuarios con baja participación se pierdan. Comprender el comportamiento de los usuarios con un alto nivel de participación puede ayudar a fomentar un comportamiento similar para los usuarios con un bajo nivel de participación, lo que les hace menos propensos a cancelar su suscripción.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Ver]**: cambie entre este tipo de vista y [Uso](usage.md).
* **[!UICONTROL Eventos]**: los eventos que desea medir. Cada evento seleccionado se representa como un gráfico independiente. Se agrega a la tabla una fila que representa el evento de tendencias. Se pueden incluir hasta cinco eventos.
* **[!UICONTROL Contabilizado como]**: método de contabilización que desea aplicar a los eventos seleccionados. Las opciones incluyen [!UICONTROL Usuarios], [!UICONTROL Sesiones], [!UICONTROL Porcentaje de usuarios] y [!UICONTROL Porcentaje de sesiones]. El denominador de las métricas basadas en porcentajes en esta vista son los usuarios o las sesiones que realizaron los eventos seleccionados, no todos los usuarios activos del producto.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado duplica el número de barras del gráfico y las filas de la tabla. Se pueden incluir hasta cinco segmentos.

## Ajustes del gráfico

El [!UICONTROL Frecuencia] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra horizontal] y [!UICONTROL Barra apilada].

## Configuración del depósito

Determina cómo se clasifica el evento en grupos.

* **[!UICONTROL Bloques automáticos]**: Identifique automáticamente el tamaño de bloque óptimo en función de la distribución de datos.
* **[!UICONTROL Bloques personalizados]**: Personalice la forma en que los datos se agrupan en bloques.
   * [!UICONTROL Desde]: el primer bloque. La frecuencia menor que este valor se excluye de los informes.
   * [!UICONTROL Hasta]: La frecuencia mayor que este valor se agrupa en el último bloque.
   * [!UICONTROL Tamaño]: El intervalo del contenedor.

## Comparación del tiempo

{{apply-time-comparison}}

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencia. Esta configuración no afecta a las vistas sin tendencias como Frecuencia.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.
