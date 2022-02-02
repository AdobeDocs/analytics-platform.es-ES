---
title: Configuración de componentes de atribución
description: Permite establecer la atribución predeterminada para una métrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---

# Configuración de componentes de atribución

La atribución permite establecer un modelo de atribución predeterminado para una métrica. Puede anular el modelo de atribución de una métrica determinada mientras trabaja en Analysis Workspace.

![Atribución](../assets/attribution-settings.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Establecer atribución] | Habilita un modelo de atribución predeterminado cuando se utiliza esta métrica. Este valor predeterminado se puede sobrescribir en una [!UICONTROL tabla improvisada] o en una métrica calculada. |
| [!UICONTROL Modelo de atribución] | Permite especificar qué modelo de atribución [predeterminado](/help/analysis-workspace/attribution/models.md) utilizar. El valor predeterminado es [!UICONTROL Último toque]. Las opciones son: Último toque, Primer toque, Lineal, Participación, Mismo toque, Forma de U, Curva J, J Inversa, Deterioro de tiempo, Personalizado, Algorítmico. Algunas de estas opciones crean campos adicionales que es necesario rellenar, como Personalizado o Deterioro de tiempo. Puede crear varias métricas utilizando el mismo campo: esto significa que puede tener una métrica de ingresos [!UICONTROL Último toque] y una métrica de ingresos [!UICONTROL Primer toque], pero en función del mismo campo de ingresos del esquema. |
| [!UICONTROL Ventana retroactiva] | Permite especificar una ventana retrospectiva predeterminada para una métrica. Las opciones son: [!UICONTROL Persona] (ventana de informes), [!UICONTROL Sesión] y [!UICONTROL Personalizado]. Cuando se selecciona [!UICONTROL Personalizado], también se le da la opción de seleccionar cualquier número de días/semanas/meses/etc. (Hasta 90 días), igual que [!UICONTROL Attribution IQ]. Puede tener varias métricas utilizando el mismo campo de esquema, pero cada una con una ventana retrospectiva independiente. |
