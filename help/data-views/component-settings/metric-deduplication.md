---
title: Configuración del componente de deduplicación de métricas
description: Contar solo la primera aparición de una métrica en los informes.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 9%

---


# Configuración del componente de deduplicación de métricas

La deduplicación de métricas le permite configurar una métrica para que solo cuente los valores de forma no repetitiva.

| Configuración | Descripción |
| --- | --- |
| Anulación de duplicación métrica | Casilla de verificación que permite habilitar la deduplicación de métricas. Deshabilitado de forma predeterminada. |
| Ámbito de anulación de duplicación | Permite determinar hasta dónde llega la comprobación única.<br>**Sesión**: Solo se cuenta la primera incidencia de métrica de la sesión.<br>**Persona**: Solo se cuenta la primera aparición de métrica en la ventana de informes. |
| ID de anulación de duplicación | En lugar de aplicar la deduplicación en la propia métrica, le permite aplicar la deduplicación de métricas en función de una dimensión. Valioso para dimensiones como ID de compra para aplicar la deduplicación. |
