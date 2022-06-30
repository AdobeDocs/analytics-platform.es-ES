---
title: Información general sobre las métricas calculadas
description: Obtenga información sobre las métricas filtradas que se derivan del tiempo de ejecución del informe.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
source-git-commit: e98b21824789600c7729cce99d7592011ad18577
workflow-type: ht
source-wordcount: '457'
ht-degree: 100%

---

# Información general sobre las métricas calculadas

Las métricas calculadas y calculadas avanzadas (o derivadas) son métricas personalizadas que puede crear a partir de métricas existentes. Nuestras herramientas de métricas calculadas ofrecen una forma muy flexible de crear, administrar y ajustar métricas. Como expertos en marketing, gestores de productos y analistas, les permite plantear preguntas acerca de los datos sin tener que cambiar su implementación.  

Puede

* Crear métricas filtradas que se derivan del tiempo de ejecución de un informe, sin tener que cambiar la implementación. Estas pueden verse en el historial, ya que se basan en filtros.
* (Solo métricas calculadas avanzadas) Filtrar métricas. Por ejemplo, puede crear una métrica para “Visitantes nuevos”, con un recuento de personas de las cuales sea la primera sesión.
* (Solo métricas calculadas avanzadas) Incorporar funciones estadísticas para ayudar a describir mejor los datos. Por ejemplo, puede contar el número de elementos de un informe o agregar el número de desviaciones estándar para cada elemento.

## Métricas calculadas en comparación con métricas calculadas avanzadas

A continuación se muestra una comparación de las competencias de las métricas calculadas y las métricas calculadas avanzadas:

| Opciones del creador | Métricas calculadas | Métricas calculadas avanzadas (derivadas) |
|---|---|---|
| Tipos de formato (decimal, tiempo, porcentaje, moneda) | Sí | Sí |
| Cambios de atribución (predeterminado, lineal, de participación, etc.) | Sí | Sí |
| Tipos de métrica (estándar, total) | Sí | Sí |
| Operadores básicos (sumar, restar, multiplicar, dividir) | Sí | Sí |
| Aplicar filtros | No | Sí |
| [Funciones básicas (recuento, valor absoluto, media, etc.)](/help/components/calc-metrics/cm-functions.md) | No | Sí |
| [Funciones avanzadas (regresión, si/entonces, unidad tipificada, etc.)](/help/components/calc-metrics/cm-adv-functions.md) | No | Sí |

## Herramientas

| Herramienta | Competencias |
|--- |--- |
| Creador de métricas calculadas | <ul><li>Cree métricas calculadas avanzadas con modelos de asignación avanzados.</li><li>Añadir filtros en línea a fórmulas métricas.</li><li>Comparar filtros en el mismo informe. Por ejemplo, comparar los visitantes locales con los visitantes internacionales.</li><li>Utilizar funciones estadísticas.</li><li> Proporcionar descripciones de métricas detalladas (mostrar qué hace, dónde utilizarla y para qué NO utilizarla).</li><li>Copiar definiciones en métricas nuevas.</li><li>Proporcionar una vista previa de métricas en línea.</li><li>Establecer la polaridad de una métrica, lo cual indica si es bueno o malo que un evento personalizado predeterminado (métrica) vaya al alza.</li><li>Etiquetar métricas.</li></ul> |
| Administrador de métricas calculadas | <ul><li>Compartir métricas con otros.</li><li>Aprobar y ajustar métricas.</li><li>Organizar (etiquetar) sus métricas para que los demás puedan encontrarlas.</li><li>Eliminar métricas.</li><li>Cambiar el nombre de métricas.</li></ul> |
| API para métricas calculadas | Parte del conjunto API de CJA. |

## Plantillas de métricas calculadas en CJA

| Nombre de métrica calculada | Descripción de métrica calculada |
| --- | --- |
| Sesiones por persona | Número promedio de sesiones por persona |
| Tasa de inicio de sesión | Porcentaje de tiempo que un elemento de dimensión tuvo lugar en el primer evento de una sesión. |
| Tasa de finalización de sesión | Porcentaje de tiempo que cualquier elemento de dimensión se produjo en el último evento de una sesión. |
| Tiempo empleado por persona | Promedio de tiempo que una persona ha invertido en un elemento de dimensión determinado. |
| Tiempo empleado por sesión | Promedio de tiempo que una persona ha invertido por sesión en un elemento de dimensión determinado. |
