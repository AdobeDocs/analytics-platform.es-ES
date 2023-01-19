---
title: Ingesta de datos de Marketo Engage en AEP e informes en CJA
description: Aprenda a incorporar datos de Marketo Engage a CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# Ingesta de datos de Marketo Engage en AEP e informes en CJA

Puede aprovechar los conjuntos de datos de Marketo Engage disponibles en Adobe Experience Platform (AEP) para ofrecer valiosas soluciones de análisis e informes a los especialistas en marketing B2B. A continuación, informe sobre estos conjuntos de datos en Customer Journey Analytics (CJA)

## Paso 1: Asignación de campos de datos de origen de Marketo a sus destinos XDM

Asigne los objetos [Personas](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=es#persons) y [Actividades](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=es#activities) a sus respectivos campos de destino de esquema XDM.

## Paso 2: Ingesta de datos de Marketo en AEP

Utilice el [conector de Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=es) para llevar los datos de Marketo a Experience Platform y mantenerlos actualizados mediante aplicaciones conectadas a la plataforma.

## Paso 3: Configurar una conexión a este conjunto de datos en CJA

Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y CJA. Puede encontrar más información en [Crear una conexión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es).

## Paso 4: Crear una o más vistas de datos

Una [vista de datos ](/help/data-views/data-views.md)es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión. Especifica todas las dimensiones y métricas disponibles en Analysis Workspace; en este caso, métricas y dimensiones específicas de Marketo. También especifica de qué columnas obtienen los datos esas dimensiones y métricas. Las vistas de datos se definen a fin de prepararse para la creación de informes en Analysis Workspace.

## Paso 5: Informes en Analysis Workspace

Un caso de uso que puede explorar es: ¿Cuántas visitas de páginas web de posibles clientes tuvimos entre abril y junio de 2020?

1. Abra [Analysis Workspace](/help/analysis-workspace/home.md) y cree un nuevo proyecto.
Los clientes con B2B/B2P CDP pueden realizar análisis de tipo B2C en CJA. Los objetos B2B aún no están disponibles.

1. Cree un [filtro](/help/components/filters/create-filters.md) para vistas de páginas web como se indica a continuación: Tipo de evento = web.webpagedetails.pageViews :

   ![](../assets/marketo-filter.png)

1. En la tabla de forma libre, arrastre el filtro que ha creado: Vistas de página web y, a continuación, arrastre el intervalo de fechas Mes. Esto le proporciona visitas a la página web por posibles clientes cada mes:

   ![](../assets/marketo-freeform.png)

1. O tire de las siguientes dimensiones: Clave de persona o Dirección de correo electrónico de trabajo. Esto le proporciona las visitas a la página web de cada posible cliente:

   ![](../assets/marketo-freeform2.png)
