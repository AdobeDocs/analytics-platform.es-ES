---
description: Descubra cómo AEP Attribution AI se integra con Workspace en CJA.
title: Integración de Attribution AI con CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: e75836841cdaf8acd2408723111f13048d31505d
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 5%

---

# Integración de Attribution AI con CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), como parte de Adobe Experience Platform Intelligent Services, es un servicio de atribución algorítmica de varios canales que calcula la influencia y el impacto incremental de las interacciones de los clientes con los resultados especificados. Con Attribution AI, los especialistas en marketing pueden medir y optimizar el gasto en marketing y publicidad al comprender el impacto de cada interacción individual con los clientes en cada fase de los recorridos de los clientes.

Attribution AI admite dos categorías de puntuaciones: algorítmica y basada en reglas. Las puntuaciones algorítmicas incluyen puntuaciones incrementales e influenciadas. Las puntuaciones basadas en reglas incluyen Primer toque, Último toque, Lineal, Forma de U y Deterioro de tiempo.

Attribution AI se integra con Customer Journey Analytics (CJA) en la medida en que Attribution AI ejecuta modelos con datos y luego CJA importa la salida de esos modelos como un conjunto de datos, que luego se puede integrar con el resto de sus conjuntos de datos CJA. Los conjuntos de datos habilitados para Attribution AI se pueden aprovechar en las vistas de datos y los informes en CJA.

Attribution AI admite 3 esquemas de Experience Platform: Evento de experiencia, Adobe Analytics y Evento de experiencia del consumidor.

## Flujo de trabajo

Algunos de los pasos se realizan en Adobe Experience Platform antes de trabajar con la salida en CJA.

### Descargar puntuaciones de Attribution AI

1. En el Experience Platform, descargue las puntuaciones de Attribution AI, tal como se describe [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).
1. En Experience Platform, cree una instancia de Attribution AI seleccionando y asignando datos, definiendo eventos y formando los datos, como se describe [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).
1. En CJA,

## Diferencias entre Attribution AI y Attribution IQ

Entonces, ¿cuándo se deben usar los datos de Attribution AI en lugar de [Attribution IQ](/help/analysis-workspace/attribution/overview.md), ¿una capacidad nativa de CJA? Esta tabla muestra algunas de las diferencias en la funcionalidad:

| Funcionalidad | Attribution AI | Attribution IQ |
| --- | --- | --- |
| ¿Atribución fraccionada? | Sí | No |
| Permite a los usuarios ajustar el modelo | No | Sí |
| Hace atribución entre canales (Nota: AAI no utiliza los mismos datos enlazados que CJA). | Sí | Sí |
| Incluye puntuaciones incrementales e influidas | Sí | No |
| ¿Modelado ML | Sí | Sí |
| ¿Modelado ML con predicciones? | Sí | No |

{style=&quot;table-layout:auto&quot;}
