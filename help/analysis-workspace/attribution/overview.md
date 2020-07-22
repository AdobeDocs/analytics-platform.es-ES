---
title: Información general de Attribution
description: El concepto de atribuir crédito de un evento de éxito a varios elementos de dimensión.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 56%

---


# Información general de Attribution

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

La atribución permite a los analistas personalizar la forma en que los elementos de dimensión obtienen crédito por los eventos de éxito. Por ejemplo:

1. Un visitante a su sitio hace clic en un vínculo de búsqueda paga a una de las páginas de productos. Agregue el producto al carro de compras, pero no lo compre.
2. Al día siguiente, verá una publicación en los medios sociales de uno de sus amigos, haga clic en el vínculo y, a continuación, complete la compra.

En algunos informes, es posible que desee atribuir el orden a la búsqueda paga. En otros informes, es posible que desee atribuir el orden a Social. La atribución permite controlar este aspecto del sistema de informes. Está disponible para todas las organizaciones en Adobe Analytics Ultimate, Prime, Select y Foundation. Si no está seguro de qué tipo de contrato tiene con Adobe, póngase en contacto con el administrador de cuentas de su organización.

## Valor de IQ de atribución

El recorrido del cliente no es lineal y a menudo es bastante impredecible. Cada cliente actúa sigue su propio recorrido; a menudo se duplican, se paralizan, se reinician o se involucran en otro comportamiento no lineal. Esto hace que sea difícil saber el impacto de los esfuerzos de marketing a lo largo del recorrido del cliente. También obstaculiza los esfuerzos por unir múltiples canales de datos.

![Problema de Attribution IQ](assets/attribution_iq_problem.png)

Adobe Analytics mejora la atribución al permitir lo siguiente:

* Definir la atribución más allá del contenido multimedia de pago: cualquier dimensión, métrica, canal o evento puede aplicarse a modelos (por ejemplo, búsqueda interna), no solo a campañas de marketing.
* Utilizar la comparación de modelos de atribución sin límites: compare dinámicamente todos los modelos que desee.
* Evitar cambios de implementación: con el procesamiento de tiempo de informes y las sesiones con reconocimiento de contexto, el contexto del recorrido del cliente puede generarse y aplicarse en el tiempo de ejecución.
* Construir la sesión más adecuada para su situación de atribución.
* Desglosar la atribución por segmentos: compare fácilmente el rendimiento de sus canales de marketing en cualquier segmento importante (por ejemplo, clientes nuevos frente a repetidos, producto X frente a producto Y, nivel de fidelidad o CLV).
* Inspeccionar análisis de canales cruzados y de múltiples contactos mediante Diagramas de Venn e Histogramas, y resultados de atribución de tendencias.
* Analizar visualmente secuencias de marketing clave: explore las rutas que generaron una conversión visualmente con las visualizaciones de visitas en el orden previsto y flujo de varios nodos.
* Generar métricas calculadas: Utilice todos los métodos de asignación de atribuciones que desee.

## Funciones

Attribution IQ incluye las siguientes funciones:

* [Panel](../c-panels/attribution.md)de atribución: Tome cualquier dimensión y métrica y compárela rápidamente con diferentes modelos de atribución.
* [Aplicar atribución a una métrica](../build-workspace-project/column-row-settings/column-settings.md): Utilice una atribución no predeterminada en cualquier métrica de un proyecto.
* [Aplicar atribución a un desglose](/help/components/dimensions/t-breakdown-fa.md): Utilice una atribución no predeterminada en un desglose.
* [Comparar modelos](/help/components/apply-create-metrics.md)de atribución: Ver rápidamente cómo se comparan los distintos modelos de atribución para cualquier métrica.
