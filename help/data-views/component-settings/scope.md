---
title: Configuración de componentes del ámbito
description: Configure el ámbito de un componente para la creación de informes de población total.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
source-git-commit: a4f7eef26a019f4f8a716f44d49985290b135112
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 4%

---


# Configuración de componentes del ámbito {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="Ámbito"
>abstract="Determinar el ámbito de un componente cuando se utiliza en informes. Puede seleccionar entre basado en eventos, en perfiles o en totales."

El ámbito de un componente de métrica determina cómo se utiliza el componente en los informes.

| Ámbito | Descripción |
|---|---|
| Basado en eventos | El ámbito del componente de métrica se basa en eventos. |
| Basado en perfiles | El ámbito del componente de métrica se basa en el perfil. Cuando se utiliza el componente en informes e intervalos de fechas, la métrica devuelve la población de los datos de perfil, independientemente del intervalo de fechas aplicado al panel. Los filtros de fecha y las comparaciones de intervalos de fechas no afectan a la creación de informes de esta métrica. |
| Basado en el total | El ámbito del componente de métrica se basa en perfiles y eventos. Cuando se utiliza el componente en los informes, la métrica devuelve la población de los datos de perfil y evento, independientemente del intervalo de fechas aplicado al panel. Los filtros de fecha y las comparaciones de intervalos de fechas no afectan a la creación de informes de esta métrica. |

