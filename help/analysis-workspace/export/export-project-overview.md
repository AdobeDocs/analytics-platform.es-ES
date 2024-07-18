---
description: Conozca los métodos disponibles para la exportación desde Analysis Workspace.
keywords: Analysis Workspace
title: Cómo exportar los datos del proyecto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# Información general sobre la exportación

Puede exportar informes de Customer Journey Analytics desde Analysis Workspace. Es posible que desee exportar informes de Customer Journey Analytics por varios motivos, como para utilizarlos en herramientas de terceros o combinarlos con datos externos.

En las siguientes secciones se describen los tipos de archivo admitidos, los distintos métodos disponibles para la exportación y las ventajas de cada método.

## Tipos de archivo admitidos

Puede exportar informes de Customer Journey Analytics como un archivo de PDF, CSV o JSON.

* **PDF:** Proporciona una manera fácil de compartir datos visuales con las partes interesadas. Los archivos de PDF contienen todas las tablas y visualizaciones mostradas (visibles) en el proyecto.

* **CSV:** Permite ver datos sin procesar en una aplicación de hoja de cálculo, como Excel. Los archivos CSV contienen datos de texto sin formato.

* **JSON:** Proporciona un formato de archivo estándar abierto para compartir datos.

## Métodos de exportación

Hay varios métodos disponibles al exportar desde Analysis Workspace. Al elegir un método de exportación, tenga en cuenta qué desea exportar y quién debe acceder a él.

| Método de exportación | Ventajas |
|---------|----------|
| [Descargar en su estación de trabajo](/help/analysis-workspace/export/download-send.md) | Utilice este método si desea: <ul><li>Descargue proyectos en su estación de trabajo personal.</li><li>Las descargas son solo ad hoc (no se pueden programar).</li> <li>Descargue un total de 50 000 filas.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Enviar a otros usuarios](/help/analysis-workspace/export/t-schedule-report.md) | Utilice este método si desea: <ul><li>Enviar por correo electrónico los datos de los Customer Journey Analytics exportados a otros usuarios de la organización.</li><li>Puede ser ad hoc o según una programación.</li> <li>Incluya un total de 50 000 filas.</li> <!--true?--> |
| [Enviar a una aplicación en la nube](/help/analysis-workspace/export/export-cloud.md) | Utilice este método si desea: <ul><li>Exporte a una ubicación compartida, como Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 o Snowflake.</li><li>Puede ser ad hoc o según una programación.</li><li>Almacene mayores cantidades de datos de Customer Journey Analytics.</li><li>Exportar tablas completas que contengan miles o millones de filas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
