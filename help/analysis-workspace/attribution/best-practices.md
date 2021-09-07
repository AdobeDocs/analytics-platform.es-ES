---
title: Prácticas recomendadas de atribución
description: ¿Cuáles son las prácticas recomendadas para decidirse por un modelo de atribución?
source-git-commit: 0e0d77425edeceb3ede6d2d7ca81846b30179607
workflow-type: ht
source-wordcount: '393'
ht-degree: 100%

---


# Prácticas recomendadas de atribución

Elegir el modelo de atribución correcto para su organización depende de una serie de consideraciones. Este artículo explora una metodología y algunas prácticas recomendadas generales.

## Paso 1: Análisis exploratorio

>[!NOTE]
>Este análisis debe realizarse antes de elegir un modelo de atribución.

Esta fase consiste inicialmente en comprender el comportamiento del cliente y definir las métricas de conversión. En función de las métricas de conversión, las herramientas como Analysis Workspace y la extracción de fuentes de datos de varios canales (como los datos de impresiones) pueden facilitar la comprensión de

* ¿Cuántos clientes tocan diferentes canales de marketing antes de la conversión?
* La proporción/distribución de estos comportamientos.

Por ejemplo, si el 50 % de los clientes tocan 3 canales antes de la conversión, ¿existe interacción entre esos 3 canales?
Luego puede realizar análisis de canal superior e inferior para ampliar su comprensión.

### Análisis de canal superior

El análisis de canal superior analiza los canales utilizados para crear imagen de marca o producto. Por ejemplo, el objetivo de la mayoría de los anuncios de TV es la imagen de marca. Puede utilizar el [modelo de atribución “Deterioro del tiempo”](/help/analysis-workspace/attribution/models.md), ya que las personas se olvidarán de su anuncio de TV con el tiempo.

### Análisis de canal inferior

En este análisis, la suposición es que las personas ya conocen su marca y usted quiere que se conviertan. Utilice notificaciones push o por correo electrónico o anuncios de Facebook.

## Paso 2: Atribución basada en reglas

El propósito de este paso es validar las hipótesis.

**Ejemplo 1**

Digamos que su hipótesis es “Mi canal de primer contacto tiene más impacto en la conversión que mi canal de último contacto. A continuación, utilice el [modelo de atribución “Forma de J invertida”](/help/analysis-workspace/attribution/models.md) para probar esta hipótesis. Este modelo da el 60 % del crédito al primer punto de contacto.

**Ejemplo 2**

Su hipótesis puede ser: “En nuestra industria (como en la de los viajes), la ventana de atribución es de 60 o 90 días, no de 30, porque los clientes investigan mucho antes de comprar un producto. Entonces, cambiaría su [ventana retrospectiva](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=es#lookback-windows) a 90 días.

## Paso 3: Utilizar atribución algorítmica

Como es muy difícil validar un gran número de hipótesis y combinaciones posibles, puede utilizar [atribución algorítmica](/help/analysis-workspace/attribution/algorithmic.md) para dejar este trabajo a los algoritmos integrados. Si ya ha encontrado el modelo de atribución que responde a todas sus preguntas y encaja perfectamente con lo que busca, entonces obviamente no necesita dar este paso.

## Otras consideraciones

* Es posible que necesite utilizar los servicios de un científico de datos en lugar de depender solo de Analysis Workspace.
