---
title: Configuración del componente de anulación de deduplicación de métricas
description: Cuenta solo la primera aparición de una métrica en los informes.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e2ebda486eae7740351370f48bdf104c90494ae3
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 75%

---

# Configuración del componente de anulación de deduplicación de métricas

La anulación de deduplicación de métricas le permite configurar una métrica para que solo cuente los valores de forma no repetitiva.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Anulación de duplicación métrica] | Casilla de verificación que permite habilitar la anulación de deduplicación de métricas. Deshabilitado de forma predeterminada. |
| [!UICONTROL Ámbito de anulación de duplicación] | Permite determinar hasta dónde llega la comprobación única.<br>**Sesión**: solo se cuenta la primera ocurrencia de métrica de la sesión.<br>**Persona**: solo se cuenta la primera ocurrencia de métrica en la ventana de creación de informes. |
| [!UICONTROL ID de anulación de duplicación] | En lugar de aplicar la anulación de deduplicación en la propia métrica, le permite aplicar la anulación de duplicación de métricas en función de una dimensión. Útil para dimensiones como ID de compra para aplicar la anulación de deduplicación. |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>   Deduplicación en un _person_ el ámbito se evalúa mediante meses completos en tiempo UTC. Es posible que una ventana de informes de mes parcial no muestre todas las instancias primera o última, si algunas ocurrieron dentro del mes completo pero fuera de las fechas de informes.
