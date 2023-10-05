---
description: Administración de registros para exportaciones existentes
keywords: Analysis Workspace
title: Solución de problemas de exportaciones fallidas
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 2c9dfdf36e47b9467077310a31dc2c6258137d35
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Solución de problemas de exportaciones fallidas

{{release-limited-testing}}

Cuando usted [exportar tablas completas desde Analysis Workspace a destinos en la nube](/help/analysis-workspace/export/export-cloud.md), puede ver el estado de esas exportaciones desde el [Pestaña Exportaciones](/help/components/exports/manage-exports.md) y desde el [Pestaña Registros](/help/components/exports/manage-export-logs.md). Las exportaciones con errores muestran un estado de [!UICONTROL **Error**].

## Errores y acciones comunes

Las exportaciones pueden fallar por varios motivos. En la tabla siguiente se describen algunos de los motivos más comunes, con acciones que puede realizar para solucionar los errores:

| Causa del error | Acción sugerida | Más información |
|---------|----------|---------|
| Ubicación o información de cuenta no válida | Asegúrese de que sus credenciales y otra información sean correctas para la cuenta y la ubicación de en la nube a la que está exportando. | [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md). |
| Una dimensión o métrica del informe se ha eliminado de la vista de datos | Póngase en contacto con el administrador del sistema para ver qué componentes se eliminaron de la vista de datos. Es posible que tenga que utilizar una vista de datos diferente en la exportación o quitar componentes de la tabla que ya no estén disponibles. | [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md) |
| Límite de fila excedido | Según el tipo de licencia, puede exportar un máximo de 3 millones, 30 millones, 150 millones o 300 millones de filas. Actualice la tabla que está exportando para reducir el número total de filas. | [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md) |
| Caducidad de exportación programada | La exportación programada que configuró ha caducado. Actualice la caducidad de la exportación. | [Administración de exportaciones](/help/components/exports/manage-exports.md) |
| Dimension no admitido | <p>No se admite ninguna dimensión que cumpla los siguientes criterios en la exportación de tabla completa:</p> <ul><li>Utiliza una matriz de objetos</li><li>Tiene habilitada la persistencia<li>No utiliza una dimensión de enlace</li> | <ul><li>[Usar matrices de objetos](/help/use-cases/object-arrays.md)</li><li>Configuración de componentes de [persistencia](/help/data-views/component-settings/persistence.md)<li>[Uso de dimensiones y métricas de enlace en Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Una directiva de gobernanza de datos que aplica su organización restringe la exportación de los componentes de la tabla | Póngase en contacto con el administrador del sistema para ver qué componentes están restringidos para no exportarse. Elimine los componentes restringidos antes de la exportación. | *Filtro en políticas de gobernanza de datos en vistas de datos* sección en [Etiquetas y políticas](/help/data-views/data-governance.md) |

## Póngase en contacto con el servicio de atención al cliente de Adobe

Si sigue teniendo problemas, póngase en contacto con el Servicio de atención al cliente de Adobe. Cuando contacte con el Servicio de atención al cliente con respecto a una exportación fallida, asegúrese de tener disponible la siguiente información:

* Nombre de exportación

* ID de exportación

* ID de instancia

* Nombre de la vista de datos

* Ubicación

* Cuenta

* Conexión

* Nombre de empresa
