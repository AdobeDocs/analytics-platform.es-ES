---
title: Casos de uso de exportación de datos
description: Comprender varios casos de uso de exportación de datos para Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 8118435a3982c405f76de9070afa05b8fd71ebf3
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Casos de uso de exportación de datos

Esta sección proporciona casos de uso de exportación de datos. Cada caso de uso se describe en su propio artículo. En algunos casos de uso, se proporciona más de una solución.

## Primeros pasos

Una de las diferencias únicas entre Adobe Analytics y Customer Journey Analytics está relacionada con el procesamiento de datos para la atribución y la sesionización. Consulte [Comparar el procesamiento de datos entre Adobe Analytics y Customer Journey Analytics.](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) para obtener más información.

### Adobe Analytics: atribución de tiempo de recopilación y sesionización.

En Adobe Analytics, todos los eventos se procesan en directo y en orden por ID de dispositivo, lo que permite al Adobe generar, almacenar y exportar datos del flujo de navegación con valores persistentes o atribuidos en el momento de la recopilación, lo que incluye:

* Persistencia del Dimension (por ejemplo, códigos de seguimiento de campaña que caducan después de 90 días).
* Número de visita y definición de sesión.
* Valores de Dimension, calculados mediante reglas de procesamiento y VISTA.

Esto afecta a la exportación de datos desde Adobe Analytics:

* El procesamiento de datos es estático después de la recopilación inicial.
* Las fuentes de datos incluyen columnas &quot;post&quot;, que reflejan el procesamiento del tiempo de recopilación.


### Customer Journey Analytics: atribución de tiempo de consulta y sesionización

En Customer Journey Analytics, los eventos no se recopilan en orden y se utiliza un ID de persona en lugar de un ID de dispositivo, lo que permite al Customer Journey Analytics actualizar la atribución y la definición de sesiones en el momento del informe. Este tipo de recopilación de datos presenta flexibilidad, como:

* La vinculación puede _repetición_ datos diariamente o semanalmente, asociando eventos anónimos con eventos conocidos. Consulte [Vinculación](../../stitching/overview.md) para obtener más información.
* La creación de sesiones y los valores persistentes cambian cada vez
   * se recopilen nuevos datos o
   * la vinculación agrega eventos al historial de una persona.

El procesamiento de tiempo del informe afecta a la exportación de datos desde Customer Journey Analytics. Las exportaciones que incluyen valores persistentes no coincidirán con los informes de los Customer Journey Analytics y los valores se alejarán con el tiempo.

Para mantener la coherencia de las métricas, se prefiere el uso de las nuevas funciones en Customer Journey Analytics. En general, la funcionalidad de exportación de datos de Experience Platform y Customer Journey Analytics supera la funcionalidad de fuente de datos de Adobe Analytics. El Experience Platform y el Customer Journey Analytics proporcionan:

* nuevas fuentes de datos y procesamiento sujetos a exportación de datos

   * incluir fuentes de datos no digitales,
   * aplicar atribución y sesionización personalizadas basadas en reglas empresariales, y
   * mantenga los recorridos del cliente actualizados con la vinculación.

* realización de casos prácticos de exportación de datos personalizados

   * exportar datos a donde los necesite, incluidas las herramientas de Business Intelligence (BI) y los destinos de nube,
   * mantener los datos sincronizados con Analysis Workspace mediante la integración de herramientas de BI,
   * no es necesario replicar la lógica de procesamiento en sus propios sistemas,
   * nueva compatibilidad con métricas calculadas, campos derivados y segmentación, y

* consideración de la seguridad y la gobernanza de datos por diseño

   * supervisar todas las exportaciones de datos por usuario y destino,
   * establecer límites sobre qué datos están disponibles para la exportación, y
   * establezca alertas para los problemas de envío y límites en las ventanas de envío programadas.


## Casos de uso y soluciones

En general, la exportación de datos admite varios casos de uso. Cada caso de uso es diferente en términos de los datos necesarios y de cómo acceder a ellos y exportarlos. El Experience Platform y el Customer Journey Analytics proporcionan una serie de funcionalidades que, independientemente o combinadas, pueden solucionar los distintos casos de uso. La siguiente tabla proporciona una descripción general de los casos de uso de exportación de datos identificados y las funcionalidades de Experience Platform y Customer Journey Analytics para implementar estos casos de uso.

| Casos de uso de exportación de datos | Funciones de Experience Platform y Customer Journey Analytics |
|---|---|
| **Data Backup**<br/> Conserve una copia completa de sus datos digitales para fines de cumplimiento normativo o normativos. | **Experience Platform**: [**Exportar conjuntos de datos**](export-datasets.md)<br/> Exporte los datos recopilados en Experience Platform directamente a destinos de nube según una programación o según sea necesario.<br/>*Actualmente de versión limitada, se espera una versión completa para los clientes de Customer Journey Analytics en junio de 2024.* |
| **Validación de datos**<br/> Evaluar la precisión de la recopilación de datos en los datos del flujo de navegación. | **Experience Platform**: [**Servicio de consultas (Data Distiller) y exportación de conjuntos de datos**](queryservice-export-datasets.md)<br/> Interfaz interactiva de PostgreSQL para ejecutar consultas SQL ad-hoc utilizando su herramienta SQL favorita para validar los datos en sus conjuntos de datos.<br/><br/>**Customer Journey Analytics**: [**Exportar tabla completa**](export-full-table.md)<br/> Valide los datos procesados de CJA con atribución y sesionización aplicadas. |
| **Herramientas de lago de datos, Data Warehouse o BI**<br/> Incluya datos digitales en sus propias herramientas de BI o lago de datos para usarlos con conjuntos de datos adicionales. | **Customer Journey Analytics**: [**Extensión de BI**](bi-extension.md)<br/> Agregue métricas procesadas de Customer Journey Analytics a las herramientas de visualización de datos, como Power BI y combinar con datos adicionales para informes personalizados <br/><br/>**Experience Platform**: [**Servicio de consultas (Data Distiller) y exportación de conjuntos de datos**](queryservice-export-datasets.md)<br> Genere datos personalizados del flujo de navegación utilizando SQL para enviarlos a destinos en la nube. |
| **Preparación para AI/ML**<br/> Mejore los modelos y tareas de inteligencia artificial/aprendizaje automático con datos de Customer Journey Analytics. | **Customer Journey Analytics**: [**Exportar tabla completa**](export-full-table.md)<br/> Exporte dimensiones y métricas procesadas de Customer Journey Analytics a destinos de nube una vez o recurrentes, incluidas las métricas calculadas y la segmentación.<br/><br/>**Experience Platform**: [**Servicio de consultas (Data Distiller) y exportación de conjuntos de datos**](queryservice-export-datasets.md)<br/> Generar datos de flujo de navegación personalizados con SQL para enriquecer los modelos AI/ML. |
