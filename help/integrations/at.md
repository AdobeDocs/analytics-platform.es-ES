---
title: Informes de Target en Adobe Customer Journey Analytics
description: Integración de Adobe Target con Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 40%

---

# Informes de Target en Adobe Customer Journey Analytics

La creación de informes de Target en Customer Journey Analytics le permite medir e informar sobre las actividades de Adobe Target directamente en Customer Journey Analytics. Esta funcionalidad es comparable a la que se realiza en Adobe Analytics (AA) mediante Analytics for Target (A4T), pero con la conectividad con Adobe Experience Platform (AEP).

Al agregar el conjunto de datos de búsqueda de clasificación de Target (que está disponible de forma predeterminada en Experience Platform) a una conexión de Customer Journey Analytics, los usuarios ahora están expuestos de forma adecuada a las herramientas de creación de informes de Target, la atribución de pedidos de Target y otras funciones. Con solo algunas preparaciones y ajustes menores realizados dentro de la vista de datos del Customer Journey Analytics, estas actividades pueden estar disponibles inmediatamente para cualquier usuario que desee enviar datos de Target directamente a CJA.

## Ventajas principales

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de Customer Journey Analytics a los informes de actividad de Target en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Los especialistas en marketing pueden aprovechar las funciones de Customer Journey Analytics, como el Panel de experimentación, para analizar más a fondo la personalización de su sitio web.
* Los especialistas en marketing pueden tener una única fuente de creación de informes para Adobe Journey Optimizer y Target. Ambos productos de personalización se pueden conectar a Customer Journey Analytics para obtener una vista más integral de la personalización web.

## Notas y consideraciones

Una vez que el conjunto de datos de evento de clasificación de Target se ha agregado a una conexión de CJA, hay que realizar algunos ajustes menores dentro de la vista de datos de CJA una vez que estos componentes se han agregado como dimensiones, lo que incluye:

* Configurar la persistencia para que sea similar a cómo se rastrea en Target (póngase en contacto con un consultor de Target o con el cliente para asegurarse de que la configuración sea correcta).

* Estableciendo persistencia en TODO, lo que permite rastrear simultáneamente varias actividades de Target y no sobrescribirlas con actividades futuras o anteriores.

## Información más detallada

Consulte [Creación de informes de Target en Adobe Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/target/using/integrate/cja/target-reporting-in-cja) en la documentación de Target para obtener más información.

Consulte el panel [Experimentación](../analysis-workspace/c-panels/experimentation.md) para obtener más información sobre cómo los analistas pueden comparar distintas variaciones de experiencia del usuario, marketing o mensajería para determinar cuál es la mejor opción a fin de obtener un resultado específico. Puede evaluar el alza y la confianza de cualquier experimento A/B desde cualquier plataforma de experimentación: en línea, sin conexión, desde soluciones de Adobe como Target o Journey Optimizer e incluso datos propios.
