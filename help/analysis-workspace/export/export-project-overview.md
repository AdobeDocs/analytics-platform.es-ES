---
description: Conozca los métodos disponibles para la exportación desde Analysis Workspace.
keywords: Analysis Workspace
title: Cómo exportar datos del proyecto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: c91ee21a3d4e20e3bdaeb75f2011ede6eee6cba0
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 55%

---

# Información general sobre la exportación

Puede exportar proyectos de Customer Journey Analytics (parte de ellos) desde Analysis Workspace. Es posible que desee exportar informes de Customer Journey Analytics por varios motivos, como para usarlos en herramientas de terceros o para combinarlos con datos externos.

En las siguientes secciones se describen los tipos de archivo admitidos, los distintos métodos disponibles para la exportación y las ventajas de cada método.

## Tipos de archivos admitidos

Puede exportar informes de Customer Journey Analytics como un archivo PDF, CSV o JSON.

* **PDF:** proporciona una manera sencilla de compartir datos visuales con las partes interesadas. Los archivos PDF contienen todas las tablas y visualizaciones mostradas (visibles) en el proyecto. 

* **CSV:** le permite ver datos sin procesar en una aplicación de hoja de cálculo, como Excel. Los archivos CSV contienen datos de texto sin formato.

* **JSON:** proporciona un formato de archivo estándar abierto para compartir datos.

## Métodos de exportación

Hay varios métodos disponibles cuando desea exportar desde Analysis Workspace. Cuando elija un método de exportación, tenga en cuenta qué desea exportar y quién debe acceder a él.

| Método de exportación | Utilice este método si desea... |
|---------|----------|
| [Descargar en su estación de trabajo](/help/analysis-workspace/export/download-send.md) | <li>Descargar proyectos en su estación de trabajo personal.</li><li>Descargar solo datos específicos (no programados).</li> <li>Descargue un máximo de 50 000 filas.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Enviar a otros usuarios](/help/analysis-workspace/export/t-schedule-report.md) | <li>Enviar por correo electrónico datos de Customer Journey Analytics exportados a otros usuarios de la organización.</li><li>Envíe el correo electrónico ad hoc o según una programación.</li> <li>Incluya un máximo de 50 000 filas en el correo electrónico.</li> <!--true?--> |
| [Exportar a una aplicación en la nube](/help/analysis-workspace/export/export-cloud.md) | <li>Exportar a una ubicación de la nube, como <ul><li>Zona de aterrizaje de datos de Adobe Experience Platform</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Exportar datos ad hoc o según una programación.</li><li>Almacenar mayores cantidades de datos de Customer Journey Analytics.</li><li>Exportar tablas completas que contengan miles o millones de filas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
