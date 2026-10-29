---
description: Descubra cómo los administradores pueden agregar descripciones a los componentes mediante una vista de datos o el diccionario de datos.
title: Adición de descripciones de componentes
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# Adición de descripciones de componentes

Las descripciones ayudan a los usuarios a saber cómo utilizar los distintos componentes al crear proyectos en Analysis Workspace o al ver informes.

Los administradores de Customer Journey Analytics pueden agregar descripciones para los componentes (dimensiones, métricas, segmentos e intervalos de fechas) dentro de una vista de datos o mediante el diccionario de datos.

## Vista de datos

Puede agregar una descripción a un componente que haya agregado a la vista de datos. Consulte [Configuración de componentes](/help/data-views/component-settings/overview.md).

## Diccionario de datos

El diccionario de datos de Analysis Workspace ayuda a los usuarios y administradores a realizar un seguimiento y comprender mejor los componentes de su entorno de Customer Journey Analytics. El diccionario de datos permite a los administradores añadir descripciones de componentes directamente en Analysis Workspace.

Para obtener información sobre cómo editar una descripción de componente en el diccionario de datos, consulte [Editar entradas de componente en el diccionario de datos](/help/components/data-dictionary/edit-entries-data-dictionary.md).

Para obtener información general acerca del diccionario de datos, consulte la [descripción general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Configuración del componente de vista de datos](/help/data-views/component-settings/overview.md)
>[Entradas del componente del diccionario de datos](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Generar descripciones automáticamente

{{release-limited-testing-section}}

En lugar de escribir cada descripción manualmente, Customer Journey Analytics puede utilizar IA generativa para escribir descripciones. Puede generar una descripción para un solo componente o generar descripciones para muchos componentes al mismo tiempo.

Descripciones generadas:

* No tienen más de 3 frases.
* Finalice con el texto **[!UICONTROL Generado por Adobe mediante IA]**, de modo que los usuarios sepan que se generó la descripción.
* Se pueden editar una vez generados.

### Requisitos previos

Antes de poder generar descripciones, su organización debe aceptar determinados términos legales de IA generativa. Si su organización no ha aceptado estos términos, la opción para generar descripciones aparece atenuada. Seleccione el icono de información ![Información](/help/assets/icons/InfoOutline.svg) junto a la opción para obtener información sobre cómo habilitar la función o póngase en contacto con el administrador de su organización o con el equipo de cuenta de Adobe.

### Cómo se generan las descripciones

Las descripciones generadas se basan en la definición del componente y en un contexto adicional sobre cómo se utiliza el componente en la vista de datos, como:

* Los elementos principales de una dimensión
* Componentes que se utilizan con frecuencia con el componente

Cuando una métrica calculada o un segmento hace referencia a otro segmento, la descripción generada explica la definición del segmento al que se hace referencia.

### Generar descripciones desde varias ubicaciones

Puede generar descripciones en las siguientes áreas de Customer Journey Analytics. Algunas ubicaciones permiten generar descripciones para varios componentes, mientras que otras no.

Seleccione una ubicación para aprender a generar descripciones allí.

| Ubicación | Componentes compatibles | Componente único | Múltiples componentes |
| --- | --- | --- | --- |
| [Diccionario de datos](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensiones</li><li>Métricas</li><li>Métricas calculadas</li><li>Segmentos</li><li>Intervalos de fechas</li></ul> | Sí | Sí |
| [Vista de datos](/help/data-views/component-settings/overview.md) | <ul><li>Dimensiones</li><li>Métricas</li><li>Campos derivados</li><li>Métricas y dimensiones compartidas (para obtener más información, consulte [Métricas y dimensiones compartidas](#generate-descriptions-for-shared-metrics-and-dimensions)).</li></ul> | Sí | Sí |
| [Generador de segmentos](/help/components/segments/seg-builder.md) | Segmentos | Sí | No |
| [Administrador de segmentos](/help/components/segments/seg-manage.md#action-bar) | Segmentos | No | Sí |
| [Generador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | Métricas calculadas | Sí | No |
| [Administrador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | Métricas calculadas | No | Sí |
| [Generador de intervalos de fechas](/help/components/date-ranges/create.md#date-range-builder) | Intervalos de fechas | Sí | No |
| [Administrador de intervalos de fechas](/help/components/date-ranges/manage.md#action-bar) | Intervalos de fechas | No | Sí |

{style="table-layout:auto"}

### Generación de descripciones para métricas y dimensiones compartidas

Solo puede generar descripciones para métricas y dimensiones compartidas desde una vista de datos, como se muestra en la tabla de [Generar descripciones desde varias ubicaciones](#generate-descriptions-from-various-locations). No puede generar descripciones desde el [Administrador de dimensiones y métricas compartidas](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager).

Tenga en cuenta lo siguiente cuando genere una descripción para una métrica o dimensión compartida dentro de una vista de datos:

* La descripción se aplica a todas las vistas de datos en las que se comparte el componente y reemplaza cualquier descripción existente de ese componente en todas las demás vistas de datos y en el administrador de métricas y dimensiones compartidas.

* La descripción se basa en el contexto de la vista de datos en la que se genera (por ejemplo, los elementos de dimensión principales de la vista de datos).


