---
description: Conozca los distintos métodos disponibles para la exportación desde Analysis Workspace.
keywords: Analysis Workspace
title: Información general sobre exportar datos de proyecto
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Información general de exportación

Puede exportar datos de Customer Journey Analytics desde Analysis Workspace. Es posible que desee exportar los datos del Customer Journey Analytics por varios motivos, como almacenar grandes cantidades de datos históricos o analizar datos sin procesar en herramientas de terceros.

En las siguientes secciones se describen los tipos de archivo admitidos, los distintos métodos disponibles para la exportación y las ventajas de cada método.

## Tipos de archivo admitidos

Puede exportar datos de Customer Journey Analytics como un PDF o archivo CSV.

* **PDF:** Proporciona una forma sencilla de compartir datos visuales con las partes interesadas. Los archivos de PDF contienen todas las tablas y visualizaciones mostradas (visibles) en el proyecto.

* **CSV:** Permite ver datos sin procesar en una aplicación de hoja de cálculo como, por ejemplo, Excel. Los archivos CSV contienen datos de texto sin formato.

## Métodos de exportación

Hay varios métodos disponibles al exportar desde Analysis Workspace. Al elegir un método de exportación, tenga en cuenta qué desea exportar y quién debe acceder a él.

| Método de exportación | Ventajas |
|---------|----------|
| [Descargar en su estación de trabajo](/help/analysis-workspace/export/download-send.md) | Utilice este método si desea: <ul><li>Descargue proyectos en su estación de trabajo personal.</li><li>Las descargas son solo ad hoc (no se pueden programar).</li> <li>Descargue un total de 50 000 filas.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Enviar a otros usuarios](/help/analysis-workspace/export/t-schedule-report.md) | Utilice este método si desea: <ul><li>Enviar por correo electrónico los datos de los Customer Journey Analytics exportados a otros usuarios de la organización.</li><li>Puede ser ad hoc o según una programación.</li> <li>Incluya un total de 50 000 filas.</li> <!--true?--> |
| [Enviar a una aplicación de nube](/help/analysis-workspace/export/export-cloud.md) | Utilice este método si desea: <ul><li>Exporte a una ubicación compartida, como Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake o Adobe Experience Platform.</li><li>Puede ser ad hoc o según una programación.</li><li>Almacene grandes cantidades de datos históricos del Customer Journey Analytics.</br>Este tipo de datos se puede utilizar para detectar tendencias a largo plazo con el fin de obtener inteligencia empresarial y, en última instancia, conducir a una mejor toma de decisiones empresariales.</li><li>Exportar tablas completas que contengan miles o millones de filas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}

