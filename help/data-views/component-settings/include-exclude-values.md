---
title: Incluir valores de exclusión configuración de componentes
description: Incluya o excluya condicionalmente un elemento de dimensión según su valor.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---

# Incluir valores de exclusión configuración de componentes

Incluir valores de exclusión permite crear reglas que dependen del valor de un elemento de dimensión. Los valores que no cumplen los criterios establecidos se tratan en Analysis Workspace como si nunca hubieran existido, aunque los datos aún existan en el conjunto de datos subyacente.

![Incluir exclusión](../assets/include-exclude.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Establecer valores de inclusión y exclusión] | Casilla de verificación que permite habilitar condiciones en las que los datos se incluyen en una vista de datos. |
| [!UICONTROL Con distinción de mayúsculas y minúsculas] | Visible en tipos de datos de esquema de cadena. El valor predeterminado es Activado. Esta configuración solo se aplica a la lógica [!UICONTROL Incluir/excluir valores], no al valor resultante. Permite especificar si la regla distingue entre mayúsculas y minúsculas. |
| [!UICONTROL Coincidencias] | Le permite especificar qué valores desea tener en cuenta para la creación de informes antes de la atribución y filtros (por ejemplo, usar solo valores que contengan la frase “error”). Puede especificar: **[!UICONTROL Si se cumplen todos los criterios]** o **[!UICONTROL Si se cumple algún criterio]**. |
| [!UICONTROL Criterios] | Permite especificar la lógica de coincidencia que debe aplicarse a una regla de filtro específica.<ul><li>**Cadena**: Contiene la frase, Contiene cualquier término, Contiene todos los términos, No contiene ningún término, No contiene la frase, Es igual a, No es igual a, Comienza con, Finaliza con</li><li>**Doble/entero**: igual, no igual, es mayor que, es menor que, es mayor o igual que, es menor o igual que</li><li>**Fecha**: igual, no igual, es posterior a, es anterior, ocurre en</li></ul> |
| [!UICONTROL Operando de coincidencia] | Permite especificar el operando de coincidencia al que se debe aplicar el operador de coincidencia.<ul><li>**Cadena**: Campo de texto</li><li>**Doble/entero**: Campo de texto con flechas arriba/abajo para valores numéricos</li><li>**Fecha**: Selector de granularidad de día (calendario)</li><li>**Fecha y hora**: Selector de granularidad de fecha y hora</li></ul> |
| [!UICONTROL Añadir regla] | Permite especificar un operador de coincidencia y un operador adicionales. |
