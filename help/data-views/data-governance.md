---
title: Etiquetas y políticas
description: Descubra cómo las etiquetas y políticas de datos definidas en AEP afectan a las vistas de datos y a los informes en CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: a28247e861e2f8853a6e2d2b81e7f6ed221caec0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Etiquetas y políticas

>[!NOTE]
>
>Actualmente, esta funcionalidad está en [prueba limitada](/help/release-notes/releases.md).

Al crear un conjunto de datos en Experience Platform, puede crear [etiquetas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) para algunos o todos los elementos del conjunto de datos. Hasta ahora, estas etiquetas no estaban expuestas en CJA. Con esta versión, puede ver estas etiquetas en CJA. De especial interés para CJA son estas etiquetas:

* La variable `C8` label - **[!UICONTROL Sin medición]**. Esta etiqueta significa que los datos no se pueden usar para análisis en los sitios web o las aplicaciones de su organización.

* La variable `C12` label - **[!UICONTROL Sin exportación de datos general]**. Los campos de esquema etiquetados de esta manera no se pueden exportar ni descargar desde CJA (a través de informes, exportación, API, etc.)

El etiquetado en sí mismo no significa que se apliquen estas etiquetas de uso de datos. Para eso se utilizan las políticas. Las políticas se crean mediante la variable [API del servicio de directivas](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) en Experience Platform.

En CJA aparecen dos políticas definidas por Adobe que afectan a los informes y a la descarga/uso compartido:

* **[!UICONTROL Aplicar Analytics]** directiva
* **[!UICONTROL Aplicar descarga]** directiva

## Ver etiquetas de datos en vistas de datos de CJA

Las etiquetas de datos que se crearon en el Experience Platform se muestran en tres ubicaciones de la interfaz de usuario de vistas de datos:

| Ubicación | Descripción |
| --- | --- |
| Botón Información de un campo de esquema | Al hacer clic en este botón, se indica cuál [!UICONTROL Etiquetas de uso de datos] actualmente se aplica a un campo:<p>![](assets/data-label-left.png) |
| Carril derecho debajo [Configuración de componentes](/help/data-views/component-settings/overview.md) | Cualquiera [!UICONTROL Etiquetas de uso de datos] se enumeran aquí:<p>![](assets/data-label-right.png) |
| Agregar etiquetas de datos como una columna | Puede añadir [!UICONTROL Etiquetas de datos] como columna para [!UICONTROL Componentes incluidos] en vistas de datos. Haga clic en el icono del selector de columnas y seleccione **[!UICONTROL Etiquetas de uso de datos]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtro en las etiquetas de Control de datos en las vistas de datos

En el editor de vistas de datos, haga clic en el icono Filtro en la pista izquierda y filtre los componentes de vistas de datos por etiquetas de control de datos:

![](assets/filter-labels.png)

Haga clic en **[!UICONTROL Aplicar]** para ver qué componentes tienen etiquetas adjuntas.

## Filtrar por políticas de control de datos en vistas de datos

Puede comprobar si hay una directiva activada que bloquee el uso de ciertos elementos de vista de datos de CJA para análisis o exportación con fines específicos.

De nuevo, haga clic en el icono Filtro en el carril izquierdo y, en Administración de datos, haga clic en Directivas:

![](assets/filter-policies.png)

Haga clic en **[!UICONTROL Aplicar]** para ver qué directivas están habilitadas.

## Cómo [!UICONTROL Aplicar Analytics] la directiva afecta a los proyectos de Workspace

Si esta directiva está activada, los campos de esquema que tienen determinadas etiquetas de datos (como C8) asociadas a ellas no se pueden usar con fines de análisis dentro de CJA Workspace.

Para los informes, esto significa que

* No puede agregar estos campos a las vistas de datos y aparecen atenuados en el carril izquierdo [!UICONTROL Campos de esquema] lista.
* No se puede guardar una vista de datos que tenga campos bloqueados.

Si intenta realizar análisis de Workspace en vistas de datos que contienen elementos prohibidos para análisis, obtendrá un aviso similar al siguiente:

![](assets/policy-enforce.png)

En componentes individuales, el mensaje sería similar a este:

![](assets/policy-enforce2.png)

## Cómo [!UICONTROL Aplicar descarga] la directiva afecta a los proyectos de Workspace

Si esta directiva está activada, cualquier exportación o descarga (como correos electrónicos o archivos pdfs compartidos) de proyectos de Workspace hash de los campos confidenciales. Puede seguir realizando análisis de estos campos en Workspace, pero si intenta enviar un correo electrónico o compartir un proyecto de otro modo, los campos bloqueados aparecerán como elementos con hash en el archivo .pdf.

Añada una captura de pantalla aquí.

## Ver etiquetas en el Report Builder

Consulte _esta sección_ para obtener más información. (enlace al documento de Christine)
