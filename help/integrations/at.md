---
title: Informes de Target
description: Integración de Adobe Target con Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# Informes de Target

La creación de informes de Target en Customer Journey Analytics le permite medir e informar sobre las actividades de Adobe Target directamente en Customer Journey Analytics. Esta funcionalidad es comparable a la que se realiza en Adobe Analytics (AA) mediante Analytics for Target (A4T), pero con la conectividad con Adobe Experience Platform (AEP).

Al agregar el conjunto de datos de búsqueda de clasificación de Target (que está disponible de forma predeterminada en Experience Platform) a una conexión de Customer Journey Analytics, los usuarios ahora están debidamente expuestos a las herramientas de creación de informes de Target, la atribución de pedidos de Target y otras funciones. Con solo una pequeña preparación y ajustes realizados dentro de la vista de datos de Customer Journey Analytics, estas actividades pueden estar disponibles inmediatamente para cualquier usuario que desee enviar datos de Target directamente a CJA.

## Ventajas principales

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de Customer Journey Analytics a los informes de actividad de Target en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Los especialistas en marketing pueden aprovechar las funciones de Customer Journey Analytics, como el Panel de experimentación, para analizar más a fondo la personalización de su sitio web.
* Los especialistas en marketing pueden tener una única fuente de creación de informes para Adobe Journey Optimizer y Target. Ambos productos de personalización se pueden conectar a Customer Journey Analytics para obtener una vista más integral de la personalización web.

## Notas y consideraciones

Su actividad de Target debe [usar Customer Journey Analytics como fuente de informes](https://experienceleague.adobe.com/es/docs/target/using/integrate/cja/target-reporting-in-cja).

Una vez que el conjunto de datos de evento de clasificación de Target se ha agregado a una conexión, se deben realizar algunos ajustes menores en la vista de datos una vez que estos componentes se han agregado como dimensiones, lo que incluye:

* Configurar la persistencia para que sea similar a cómo se rastrea en Target (póngase en contacto con un consultor de Target o con el cliente para asegurarse de que la configuración sea correcta).

* Estableciendo persistencia en TODO, lo que permite rastrear simultáneamente varias actividades de Target y no sobrescribirlas con actividades futuras o anteriores.

## Información más detallada

Consulte [Creación de informes de Target en Adobe Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/target/using/integrate/cja/target-reporting-in-cja) en la documentación de Target para obtener más información.

Consulte el panel [Experimentación](../analysis-workspace/c-panels/experimentation.md) para obtener más información sobre cómo los analistas pueden comparar distintas variaciones de experiencia del usuario, marketing o mensajería para determinar cuál es la mejor opción a fin de obtener un resultado específico. Puede evaluar el alza y la confianza de cualquier experimento A/B desde cualquier plataforma de experimentación: en línea, sin conexión, desde soluciones de Adobe como Target o Journey Optimizer e incluso datos propios.
