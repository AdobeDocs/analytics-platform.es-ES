---
title: Información general sobre las métricas calculadas
description: 'Obtenga más información sobre '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Información general sobre las métricas calculadas

Las métricas calculadas y calculadas avanzadas (o derivadas) son métricas personalizadas que puede crear a partir de métricas existentes. Nuestras herramientas de métricas calculadas ofrecen una forma muy flexible de crear, administrar y ajustar métricas. Como expertos en marketing, gestores de productos y analistas, les permite plantear preguntas acerca de los datos sin tener que cambiar su implementación de [!DNL Analytics] 

Puede

* Create filtered metrics that are derived at report run time, [without having to change the implementation](https://youtu.be/CuQTm9RaUpY). Éstos se pueden ver históricamente porque se basan en filtros.
* Compartir métricas entre grupos de informes. Esto significa que todas las métricas de reciente creación se aplican a todos los grupos de informes en la misma empresa de inicio de sesión.
* (Solo métricas calculadas avanzadas) Filtre las métricas. Por ejemplo, puede crear una métrica para “Visitantes nuevos”, con un recuento de personas de las cuales sea la primera sesión.
* (Solo métricas calculadas avanzadas) Incorporar funciones estadísticas para ayudar a describir mejor los datos. Por ejemplo, puede contar el número de elementos de un informe o agregar el número de desviaciones estándar para cada elemento.

## Métricas calculadas en comparación con métricas calculadas avanzadas

A continuación se muestra una comparación de las competencias de las métricas calculadas y las métricas calculadas avanzadas:

| Opciones del creador | Métricas calculadas | Métricas calculadas avanzadas (derivadas) |
|---|---|---|
| Tipos de formato (decimal, tiempo, porcentaje, moneda | Sí | Sí |
| Cambios de atribución (predeterminado, lineal, de participación, etc. | Sí | Sí |
| Tipos de métrica (estándar, total | Sí | Sí |
| Operadores básicos (sumar, restar, multiplicar, dividir) | Sí | Sí |
| Aplicar filtros | No | Sí |
| [Funciones básicas (recuento, valor absoluto, media, etc.)](/help/components/calc-metrics/cm-functions.md) | No | Sí |
| [Funciones avanzadas (regresión, si/entonces, unidad tipificada, etc.)](/help/components/calc-metrics/cm-adv-functions.md) | No | Sí  |

## Herramientas

| Herramienta | Competencias |
|--- |--- |
| Creador de métricas calculadas | <ul><li>Cree métricas calculadas avanzadas con modelos de asignación avanzados.</li><li>Agregue filtros en línea a las fórmulas de métricas.</li><li>Compare filtros en el mismo informe. Por ejemplo, comparar los visitantes locales con los visitantes internacionales.</li><li>Utilizar funciones estadísticas.</li><li> Proporcionar descripciones de métricas detalladas (mostrar qué hace, dónde utilizarla y para qué NO utilizarla).</li><li>Copiar definiciones en métricas nuevas.</li><li>Proporcionar una vista previa de métricas en línea.</li><li>Establecer la polaridad de una métrica, lo cual indica si es bueno o malo que un evento personalizado predeterminado (métrica) vaya al alza.</li><li>Etiquetar métricas.</li></ul> |
| Administrador de métricas calculadas | <ul><li>Compartir métricas con otros.</li><li>Aprobar y ajustar métricas.</li><li>Organizar (etiquetar) sus métricas para que los demás puedan encontrarlas.</li><li>Eliminar métricas.</li><li>Cambiar el nombre de métricas.</li></ul> |
| API para métricas calculadas | Parte del conjunto de API de Adobe Analytics 2.0. |

