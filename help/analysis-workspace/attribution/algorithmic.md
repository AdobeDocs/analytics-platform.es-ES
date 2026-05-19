---
title: Atribución algorítmica
description: Comprenda los detalles del modelo de atribución algorítmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 42%

---

# Atribución algorítmica

El [modelo de atribución](models.md) algorítmica en Analysis Workspace difiere de otros modelos en que utiliza técnicas estadísticas para asignar crédito entre los elementos de dimensión del informe o la tabla de forma libre. Al igual que todos los demás modelos de atribución en Analysis Workspace, la atribución algorítmica se puede utilizar en cualquier dimensión o métrica. La atribución algorítmica admite segmentación y desgloses ilimitados y distribuye el 100 % de las conversiones a una o más dimensiones de la tabla (también conocida como atribución &quot;fraccional&quot;).

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

El algoritmo utilizado para la atribución se basa en el dividendo de Harsanyi de la teoría de juegos cooperativa. El dividendo de Harsanyi es una generalización de la solución del valor de Shapley (llamada así por Lloyd Shapley, economista ganador del Premio Nobel) para distribuir crédito entre los jugadores en un juego con contribuciones desiguales al resultado.

En un nivel superior, el cálculo de atribución del crédito de conversión para cada punto de contacto considera cada uno de los puntos de contacto de marketing dentro de una ventana retrospectiva como una coalición de actores. Para esa coalición de actores, se debe distribuir equitativamente un superávit. La distribución del superávit de cada coalición se determina desde hasta el superávit que cada subcoalición creó recursivamente anteriormente.

Para más detalles, vea los artículos originales de John Harsanyi y Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Un modelo de negociación simplificado para un juego cooperativo de n personas. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>El resultado de la atribución algorítmica solo difiere de otros modelos cuando existen varios puntos de contacto dentro de la ventana retrospectiva establecida. Las conversiones con un solo punto de contacto reciben un 100% de crédito, independientemente del modelo de atribución.
