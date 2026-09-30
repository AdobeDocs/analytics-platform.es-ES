---
title: Configuración de componentes del ámbito
description: Configure el ámbito de un componente para la creación de informes de población total.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 18%
---

# Configuración de componentes del ámbito {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="Ámbito"
>abstract="Determine cómo se define el ámbito de un componente cuando se utiliza en los informes. Puede seleccionar entre basado en eventos, en perfiles o en totales."

El ámbito de un componente de métrica determina cómo se utiliza el componente en los informes.

| Ámbito | Descripción |
|---|---|
| Basado en eventos | El ámbito del componente de métrica se basa en eventos. |
| Basado en perfiles | El ámbito del componente de métrica se basa en el perfil. Cuando se utiliza el componente en los informes, la métrica devuelve la población de los datos de perfil, independientemente del intervalo de fechas aplicado al panel. Los filtros de fecha y las comparaciones de intervalos de fechas no afectan a la creación de informes de esta métrica. |
| Basado en el total | El ámbito del componente de métrica se basa en perfiles y eventos. Cuando se utiliza el componente en los informes, la métrica devuelve la población de los datos de perfil y evento, independientemente del intervalo de fechas aplicado al panel. Los filtros de fecha y las comparaciones de intervalos de fechas no afectan a la creación de informes de esta métrica. |

