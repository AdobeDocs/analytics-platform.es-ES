---
title: Configuración del componente de anulación de deduplicación de métricas
description: Cuenta solo la primera aparición de una métrica en los informes.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9a31b1dcba4015f00dd7ae8c43b317e1c5679a2c
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# Configuración del componente de anulación de deduplicación de métricas

La anulación de deduplicación de métricas le permite configurar una métrica para que solo cuente los valores de forma no repetitiva.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Anulación de duplicación métrica] | Casilla de verificación que permite habilitar la anulación de deduplicación de métricas. Deshabilitado de forma predeterminada. |
| [!UICONTROL Ámbito de anulación de duplicación] | Permite determinar hasta dónde llega la comprobación única.<br>**Sesión**: solo se cuenta la primera ocurrencia de métrica de la sesión.<br>**Persona**: solo se cuenta la primera ocurrencia de métrica en la ventana de creación de informes. |
| [!UICONTROL ID de anulación de duplicación] | En lugar de aplicar la anulación de deduplicación en la propia métrica, le permite aplicar la anulación de duplicación de métricas en función de una dimensión. Útil para dimensiones como ID de compra para aplicar la anulación de deduplicación. |
| [!UICONTROL Valor que mantener] | <ul><li>**Mantener primera instancia**: utilícelo en situaciones en las que la instancia inicial de la métrica sea válida. Lo más común probablemente sería una confirmación de compra. Incluso si alguien vuelve a cargar la página sin querer y obtiene otra instancia de confirmación de compra, el evento inicial es el válido.</li><li>**Mantener última instancia**: utilícelo en situaciones en las que recopilar la última instancia tenga más sentido. Ejemplo: Alguien actualiza su perfil en línea. Solo queremos contar una de estas actualizaciones por sesión. Sin embargo, pueden actualizar su perfil varias veces durante la sesión. Si conservamos la primera instancia, podría haber actividades que no se vincularan al evento. En este caso, tiene más sentido mantener la última instancia.</li></ul> |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>La anulación de duplicación en el ámbito de una _persona_ se evalúa mediante meses completos en tiempo UTC. Es posible que una ventana de creación de informes mensual parcial no muestre todas las instancias primera o última, si algunas ocurrieron dentro del mes completo, pero fuera de las fechas de creación de informes.
