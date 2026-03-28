---
title: Casos de uso de Audience Analysis
description: Conozca los casos de uso de Análisis de audiencia.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
exl-id: 4f465e71-f1b5-4f38-a1db-645550856849
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Casos de uso de Audience Analysis {#analyze-audiences-use-cases}

Audience Analysis permite crear informes con los datos de pertenencia a audiencias de Experience Platform en Customer Journey Analytics. Esto se logra mediante configuraciones administradas mediante el asistente de configuraciones de Análisis de audiencia, que le ayuda a determinar qué conjunto de datos de perfil está ingiriendo, además de otros parámetros y detalles de configuración. (Para obtener información general más detallada, consulte [Resumen de análisis de audiencia](/help/connections/audience-analysis/audience-analysis-overview.md).)

Este documento incluye casos de uso de ejemplo que resaltan el valor que proporciona Análisis de audiencia. Antes de revisar los casos de uso, familiarícese primero con las consideraciones de creación de informes que se indican a continuación. Es importante tener en cuenta estas consideraciones al revisar los casos de uso, ya que pueden afectar al resultado final de los informes.

## Consideraciones del informe

La versión inicial de Audience Analysis establece las bases esenciales necesarias para procesar e ingerir audiencias de Experience Platform en Customer Journey Analytics. Al realizar el análisis, es importante tener en cuenta varios factores que pueden influir en los resultados de los proyectos de Workspace:

* **Los datos de pertenencia a audiencias son precisos solamente el día anterior (&quot;ayer&quot;)**: Los datos de pertenencia a audiencias siempre contendrán el último conjunto de datos de instantánea de perfil generado por el servicio de perfil unificado. Este conjunto de datos de perfil es una instantánea diaria y es precisa solo para el día anterior (&quot;ayer&quot;), y se regenera y vuelve a procesar automáticamente cada noche. Las dimensiones de audiencia están disponibles para la creación de informes y desgloses, no para la reconstrucción de estados de audiencia históricos.

   * Ejemplo: independientemente del intervalo temporal para la creación de informes que se haya elegido, la audiencia de la que se puede realizar el informe de CJA siempre respetará el estado de pertenencia a audiencia presente en la última instantánea de perfil ingerida (&quot;ayer&quot;).

      * Por ejemplo, si se amplía la ventana de tiempo de la creación de informes a &quot;últimos 30 días&quot;, se incluirán más eventos y se dará la impresión de que el tamaño de la audiencia está cambiando. Sin embargo, la composición del perfil de la audiencia siempre coincidirá con la instantánea de &quot;ayer&quot;, independientemente de la ventana de tiempo elegida.

* **Las dimensiones deben tener un evento correspondiente para ser incluidas**: las dimensiones de Análisis de audiencia solo pueden analizarse donde existan eventos correspondientes en CJA. Si un momento de comportamiento, canal o ciclo vital no se representa como un evento en la conexión de CJA, no se puede analizar.

   * Ejemplo: Una audiencia que se utiliza para dirigirse a personas con un anuncio incluiría significativamente más personas en la audiencia de RTCDP que en la de CJA. Esto se debe a que la audiencia de CJA está limitada a las personas que tuvieron un evento en CJA durante la ventana de creación de informes.

* **La resolución de identidad se basa únicamente en un área de nombres única**: la resolución de identidad depende totalmente del área de nombres de identidad seleccionada como parte de la configuración de Análisis de audiencia. El análisis se limitará a dicho área de nombres de identidad, y los eventos que no entren en ella no estarán disponibles para los informes de análisis de audiencia.

   * Ejemplo: Para un conjunto de datos de evento vinculado que combina CRM y ECID, y la configuración de Análisis de audiencia utiliza el ID de CRM, solo las filas que contengan un ID de CRM se reconocerán como parte de la audiencia de la que se puede realizar un informe en CJA. Por lo tanto, el tamaño de audiencia resultante puede ser menor de lo previsto.

## Casos de uso de ejemplo

### Caso de uso 1

Comprenda cómo se comporta una audiencia específica en un canal determinado (por ejemplo, web o aplicación) para responder preguntas como las siguientes:

* _&quot;¿Qué están haciendo los miembros de clientes potenciales de alto valor en el sitio en este momento (páginas, características, canales)?&quot;_

* _&quot;¿Qué campañas y contenido sobreindexan esta audiencia en comparación con todas las demás?&quot;_

#### Flujo de configuración

1. Configure el análisis de audiencia en CJA para un solo área de nombres de identidad (por ejemplo, ECID o CRM_ID) y una vista de datos centrada en la web.

   * Esto introducirá automáticamente los datos de pertenencia a audiencias en la conexión elegida mediante la exportación diaria de instantáneas de perfil

   * Se recomienda seleccionar el área de nombres de identidad que crea que tiene la mayor cobertura en el conjunto de datos de evento

1. Cree sus proyectos de Workspace para lo siguiente:

   * Desglose Nombre de audiencia por página, producto, campaña, dispositivo, etc.

   * Compare audiencias y no audiencias (o con otra audiencia) en métricas como sesiones, tasa de conversión e ingresos por persona.

1. Utilice las perspectivas generadas para ajustar las estrategias de optimización de canal (por ejemplo, reglas de segmentación, ajuste de contenido u oferta).

#### Consideraciones de resolución de identidad

| Caso de uso | Pregunta empresarial principal | Consideración de resolución de identidad | Organizaciones de alta autenticación/área de nombres única (eventos que ya tienen un ID de persona, como inicio de sesión /CRM) | Organizaciones fragmentadas o con varios espacios de nombres (eventos en ECID + CRM + otros) |
|---------|----------|---------|---------|---------|
| Análisis profundo del comportamiento de la audiencia en estado actual | _&quot;¿Qué está haciendo la audiencia X en el canal Y en este momento?&quot; (páginas, canales, contenido, ofertas)_ | Los eventos y perfiles deben compartir un área de nombres de identidad coherente en la conexión de CJA y en la configuración de Análisis de audiencia para obtener una cobertura óptima. | La mayoría de la actividad ya está vinculada a un ID de inicio de sesión/CRM, por lo que las audiencias de AEP se unen sin problemas a los datos de comportamiento en CJA. <p>Se obtiene una visión clara de lo que hace cada audiencia en un canal determinado con brechas de creación de informes mínimas esperadas.</p> | Incluso cuando se una con un conjunto de datos vinculado, el sistema de informes se restringirá al área de nombres de identidad única elegida en la configuración. <p>Si algunos clientes existen con otros ID, su comportamiento no se incluirá, lo que puede generar una vista parcial durante la creación de informes.</p> |

### Caso de uso 2

Ayude a los especialistas en marketing o a los diseñadores de recorridos a comprender qué audiencias se superponen para que puedan anular la duplicación de experiencias y evitar conflictos de ofertas entre campañas:

* _&quot;¿Cuánta superposición hay hoy entre los miembros de fidelidad, los abandonos del carro de compras y la alta tendencia a la pérdida?&quot;_

* _&quot;¿Qué audiencias tienen más probabilidades de entrar en conflicto con ofertas promocionales de alto valor esta semana?&quot;_

#### Flujo de configuración

1. Configure el Análisis de audiencias en CJA para un área de nombres de identidad única alineada con la activación de RTCDP/AJO (por ejemplo, CRM_ID si los recorridos están basados en personas).

   * Esto introducirá automáticamente los datos de pertenencia a audiencias en la conexión elegida mediante la exportación diaria de instantáneas de perfil.

   * Esto se puede utilizar para enriquecer una vista de datos existente que ya alimente la participación clave y los informes de conversión.

1. Utilice la plantilla predeterminada Información general de Análisis de audiencia y visualizaciones de superposición:

   * Ejecute intersecciones de audiencia y vistas de sobreindexación/subindexación (por ejemplo, % de abandonadores del carro de compras que también están en Oro de fidelización).

   * Los segmentos se superponen por dimensiones principales (por ejemplo, tipo de dispositivo, interés del producto) para comprender dónde importan más los conflictos.

1. Utilice las perspectivas para ajustar aspectos críticos, como:

   * Reglas de conflicto de ofertas o reglas de acción de marketing en RTCDP y AJO.

   * Mejoras en la audiencia (por ejemplo, ajustar las definiciones de destinatario donde la superposición es demasiado alta).

#### Consideraciones de resolución de identidad

| Caso de uso | Pregunta empresarial principal | Consideración de resolución de identidad | Organizaciones de alta autenticación/área de nombres única (eventos que ya tienen un ID de persona, como inicio de sesión /CRM) | Organizaciones fragmentadas o con varios espacios de nombres (eventos en ECID + CRM + otros) |
|---------|----------|---------|---------|---------|
| Superposición de audiencias y detección de colisiones | _&quot;¿Qué audiencias se superponen hoy para que podamos evitar conflictos de ofertas?&quot;_ | La superposición solo se calcula para audiencias que utilizan el mismo ID de persona y con actividad en la conexión de CJA. | Debido a que la mayoría de la actividad ya está vinculada a un único ID de inicio de sesión/CRM, se espera que esto proporcione un mapa de superposición fiable entre las audiencias. <p>Los gráficos de superposición proporcionan una imagen fiable de las audiencias que entran en conflicto y de dónde aplicar las supresiones o las reglas de prioridad.</p> | Si partes de la recorrido de viven con otros ID (por ejemplo, navegación anónima solo ECID, ID del centro de llamadas), esos eventos no se mostrarán en el análisis de superposición. <p>Las personas pueden seguir existiendo en varias áreas de nombres.</p><p>La superposición se basará en el área de nombres de identidad incluido en la configuración. Si algunos perfiles siguen divididos entre ID, la superposición puede provocar que no se comuniquen todos los conflictos reales.</p> |

### Caso de uso 3

Comprenda el comportamiento de los clientes que recientemente abandonaron una audiencia clave y lo que hicieron al salir para responder preguntas como las siguientes:

* _&quot;¿Quién acaba de dejar una audiencia clave y qué hizo al salir?&quot;_

* _&quot;¿Qué ocurrió justo antes de salir? (errores, participación baja, cambios de precio).&quot;_

#### Flujo de configuración

1. Configure el Análisis de audiencias en CJA para un solo área de nombres de identidad (por ejemplo, CRM_ID o ID de inicio de sesión) y las vistas de datos relevantes (web, aplicación, CRM, etc.).

   * Esto ingiere automáticamente los datos de pertenencia a audiencias en la conexión elegida mediante la exportación diaria de instantáneas de perfil.

   * Se recomienda seleccionar el área de nombres de identidad que crea que tiene la mayor cobertura en el conjunto de datos de evento.

1. En la plantilla Análisis de audiencia/Resumen de audiencia (fija a _ayer_), use:

   * Miembros actuales: que sigue en la audiencia

   * Audiencia saliente: quién se fue ayer

1. Cree sus proyectos de Workspace para lo siguiente:

   * Filtre por perfiles que salieron de Audience X ayer y después observe lo siguiente:

      * Su comportamiento antes de la salida (últimas sesiones, errores, exposición de precio/oferta, mezcla de canales).

      * Su comportamiento después de la salida (si cambiaron de producto, bajaron de categoría, quedaron inactivos).

   * Desglose esa cohorte de salida por región, dispositivo, tenencia y nivel de valor para encontrar bolsillos de alto impacto.

1. Utilice las perspectivas para actualizaciones de recorrido y configuraciones de audiencias de recuperación en RTCDP o AJO.

#### Consideraciones de resolución de identidad

| Caso de uso | Pregunta empresarial principal | Consideración de resolución de identidad | Organizaciones de alta autenticación/área de nombres única (eventos que ya tienen un ID de persona, como inicio de sesión /CRM) | Organizaciones fragmentadas o con varios espacios de nombres (eventos en ECID + CRM + otros) |
|---------|----------|---------|---------|---------|
| Audiencias abandonadas: análisis de pérdida | _&quot;¿Quién acaba de dejar una audiencia clave?&quot;_ <p>_&quot;¿Qué hicieron al salir?&quot;_</p> | La salida de audiencia se rastrea en el mismo ID de persona utilizado para la conexión y la configuración de audiencia. | Las salidas medidas con un ID de inicio de sesión/CRM estable tienden a reflejar un verdadero cambio de comportamiento. <p>Cuando alguien deja una audiencia con este ID, suele significar un cambio real (pérdida, reducción de categoría, inactividad).</p><p>Puede analizar su comportamiento reciente para ajustar los recorridos y las ofertas de recuperación con confianza.</p> | Las salidas solo son visibles cuando los perfiles y eventos comparten el ID configurado y, por lo tanto, requieren una interpretación cuidadosa.<p>Utilice cohortes de salida como una pista o señal sólida, pero se recomienda que se compruebe con otros puntos de datos antes de tomar decisiones críticas.</p> |
