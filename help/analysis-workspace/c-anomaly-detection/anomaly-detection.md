---
description: Obtenga información acerca de la detección de anomalías de datos en Analysis Workspace.
title: Funcionamiento de la detección de anomalías
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
source-git-commit: 689235eb0b982f4e572282f1c73e4606f9d82b12
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 93%

---

# Resumen de la Detección de anomalías

Puede ver y analizar las anomalías de datos en contexto, dentro de Analysis Workspace.

[Tutorial en vídeo de Detección de anomalías](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=es) (4:53)

La Detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores.

La detección de anomalías permite separar las “señales verdaderas” del “ruido” y así identificar los posibles factores que contribuyeron a hacer saltar estas señales o anomalías. En otras palabras, le permite identificar las fluctuaciones estadísticas que son importantes y las que no lo son. A continuación, podrá identificar la causa raíz de una anomalía real. Además, se pueden consultar predicciones de métricas (KPI) fiables.

Algunos ejemplos de anomalías que puede investigar son:

* Caídas drásticas en un valor de pedido promedio
* Picos en pedidos con ingresos bajos
* Picos o caídas en registros de prueba
* Caídas en vistas de páginas de aterrizaje
* Picos en eventos de almacenamiento de vídeo
* Picos en tasas de bits de vídeo bajas

El algoritmo de Detección de anomalías de Analysis Workspace incluye:

* Compatibilidad con las granularidades horaria, semanal y mensual, además de con la granularidad diaria.
* Diferenciación por temporadas (como el “Black Friday”) y períodos vacacionales.