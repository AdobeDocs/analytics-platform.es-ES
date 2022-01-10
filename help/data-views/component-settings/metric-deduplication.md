---
title: Configuración del componente de anulación de deduplicación de métricas
description: Cuenta solo la primera aparición de una métrica en los informes.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: ht
source-wordcount: '111'
ht-degree: 100%

---

# Configuración del componente de anulación de deduplicación de métricas

La anulación de deduplicación de métricas le permite configurar una métrica para que solo cuente los valores de forma no repetitiva.

| Configuración | Descripción |
| --- | --- |
| Anulación de duplicación métrica | Casilla de verificación que permite habilitar la anulación de deduplicación de métricas. Deshabilitado de forma predeterminada. |
| Ámbito de anulación de duplicación | Permite determinar hasta dónde llega la comprobación única.<br>**Sesión**: solo se cuenta la primera ocurrencia de métrica de la sesión.<br>**Persona**: solo se cuenta la primera ocurrencia de métrica en la ventana de creación de informes. |
| ID de anulación de duplicación | En lugar de aplicar la anulación de deduplicación en la propia métrica, le permite aplicar la anulación de duplicación de métricas en función de una dimensión. Útil para dimensiones como ID de compra para aplicar la anulación de deduplicación. |
