---
title: Prácticas recomendadas de atribución
description: Comprenda las prácticas recomendadas para decidir qué modelo de atribución utilizar.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
TQID: https://experienceleague.adobe.com/noNo2rP-srAtUJbG-kYgipLHknMsWWZR4iJwDv-2ioc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 466
ht-degree: 63%

---

# Prácticas recomendadas de atribución

Elegir el modelo de atribución correcto para su organización depende de una serie de consideraciones. Este artículo explora una metodología y algunas prácticas recomendadas generales:

* [Análisis exploratorio](#exploratory-analysis)
* [Atribuciones basadas en reglas](#rule-base-attribution)
* [Uso de atribución algorítmica](#use-algorithmic-attribution)

## Análisis de exploración

>[!NOTE]
>Este análisis debe realizarse antes de elegir un modelo de atribución.

Esta fase consiste inicialmente en comprender el comportamiento del cliente y definir las métricas de conversión. En función de las métricas de conversión, herramientas como [Fuentes de datos](https://experienceleague.adobe.com/es/docs/analytics/export/analytics-data-feed/data-feed-overview) (para datos sin procesar) o Analysis Workspace le facilitan la comprensión de

* El número de clientes que están tocando diferentes canales de marketing antes de convertir
* La proporción/distribución de estos comportamientos

Por ejemplo, si el 50 % de los clientes tocan tres canales antes de la conversión, ¿existe interacción entre esos tres canales?
A continuación puede realizar análisis de canal superior e inferior para ampliar su comprensión.

### Análisis del canal superior

Los canales de análisis del canal superior se utilizan para concienciar sobre la marca o el producto. Por ejemplo, el objetivo de la mayoría de los anuncios de TV es la imagen de marca. Puede usar el [modelo de atribución Time Decay](/help/analysis-workspace/attribution/models.md), ya que las personas se olvidarán de su anuncio de TV con el tiempo.

### Análisis de canal inferior

En el análisis de canal inferior, la suposición es que las personas ya conocen su marca y usted quiere que se conviertan. Utilice correos electrónicos, notificaciones push o anuncios de Facebook.

## Atribución basada en reglas

El propósito de este paso es validar las hipótesis.

**Ejemplo 1**

Supongamos que su hipótesis es: &quot;*Mi canal de primer contacto tiene más impacto en la conversión que mi canal de último contacto.*&quot;

En este caso, debe usar el [modelo de atribución en forma de J invertida](/help/analysis-workspace/attribution/models.md) para probar esta hipótesis. Este modelo proporciona el 60 % del crédito al primer punto de contacto.

**Ejemplo 2**

Supongamos que su hipótesis es: *&quot;En un sector específico (como el de los viajes), la ventana de atribución es de 60 o 90 días, no de 30, porque los clientes investigan mucho antes de comprar un producto.*&quot;

En este caso, cambiaría su [ventana retrospectiva](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/models) a 90 días.

## Uso de atribución algorítmica

Si todavía no tiene un modelo de atribución que proporcione respuestas satisfactorias a todas las preguntas, puede emplear [atribución algorítmica](/help/analysis-workspace/attribution/algorithmic.md). Como es muy difícil validar un gran número de hipótesis y combinaciones posibles, la atribución algorítmica recurre a algoritmos integrados para asignar crédito entre elementos de dimensión.

## Otras consideraciones

* Es posible que necesite utilizar los servicios de un científico de datos en lugar de depender solo de Analysis Workspace.
* Puede confiar en los datos sin procesar, como en las fuentes de datos de Adobe.
* Considere utilizar [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), por ejemplo, si quiere tener en cuenta los datos de sus impresiones.

