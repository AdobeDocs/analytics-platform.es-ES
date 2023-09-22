---
description: Administración de registros para exportaciones existentes
keywords: Analysis Workspace
title: Solución de problemas de exportaciones fallidas
feature: Components
hide: true
hidefromtoc: true
source-git-commit: eb7ba8dd7809164bdcddb0d484754376d5b7ca9e
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---

# Solución de problemas de exportaciones fallidas

Cuando usted [exportar tablas completas desde Analysis Workspace a destinos en la nube](/help/analysis-workspace/export/export-cloud.md), puede ver el estado de esas exportaciones desde el [Pestaña Exportaciones](/help/components/exports/manage-exports.md) y desde el [Pestaña Registros](/help/components/exports/manage-export-logs.md). Las exportaciones con errores muestran un estado de [!UICONTROL **Error**].

## Errores y acciones comunes

Las exportaciones pueden fallar por varios motivos. En la tabla siguiente se describen algunos de los motivos más comunes, con acciones que puede realizar para solucionar los errores:

| Causa del error | Acción sugerida | Más información |
|---------|----------|---------|
| Ubicación o información de cuenta no válida | Asegúrese de que sus credenciales y otra información sean correctas para la cuenta y la ubicación de en la nube a la que está exportando. | [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md). |
| Una dimensión o métrica del informe se ha eliminado de la vista de datos | Póngase en contacto con el administrador del sistema para ver qué componentes se eliminaron de la vista de datos. Es posible que tenga que utilizar una vista de datos diferente en la exportación o quitar componentes de la tabla que ya no estén disponibles. | [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md) |
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