---
title: Creación de conjuntos de datos de consulta para clasificar datos en Customer Journey Analytics
description: Obtenga información sobre cómo crear conjuntos de datos de consulta para clasificar datos en Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
autotag-review: '2026-05-19T08:11:57.362Z'
TQID: 'https://experienceleague.adobe.com/mu-yJABb7bfRMW6Kn5DBUZuSxggVyIUeOeGQHMgxetM'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 818
ht-degree: 100%

---

# Creación de conjuntos de datos de consulta para clasificar datos en Customer Journey Analytics {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="Crear un conjunto de datos de consulta para cada dimensión que contenga datos de clasificación"
>abstract="De forma similar a los datos de clasificaciones en Adobe Analytics, los conjuntos de datos de consulta son el método para clasificar datos en Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

De forma similar a los datos de clasificaciones en Adobe Analytics, los conjuntos de datos de consulta son el método para clasificar datos en Customer Journey Analytics.

Cuando se utiliza el conector de origen de Analytics, algunos conjuntos de datos de consulta estándar se aplican automáticamente en el momento del informe. Para obtener más información, consulte [Adición de consultas estándar a sus conjuntos de datos](/help/connections/standard-lookups.md).

Para clasificar los datos en Customer Journey Analytics al utilizar el SDK web de Experience Platform, debe crear un esquema personalizado y un conjunto de datos de consulta para cada dimensión que contenga los datos que desea clasificar.

## Creación de un esquema personalizado para utilizarlo con el conjunto de datos de consulta

Cree un nuevo esquema personalizado para cada dimensión que contenga datos que desee clasificar en Customer Journey Analytics. Cuando cree el conjunto de datos de consulta en un paso posterior, hará referencia a este esquema.

Repita este proceso para cada dimensión que contenga datos que desee clasificar.

Para crear un esquema para utilizarlo con un conjunto de datos de consulta en Customer Journey Analytics:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Esquemas]** en la sección **[!UICONTROL Administración de datos]** del carril izquierdo.

1. Seleccione **[!UICONTROL Crear esquema]**.

   ![Botón Crear esquema](assets/schema-create.png)

1. Seleccione **[!UICONTROL Manual]**. Esto le permite añadir manualmente campos y grupos de campos al esquema. Elija **[!UICONTROL Seleccionar]** para continuar hasta la siguiente página del asistente de creación.

1. En la página **[!UICONTROL Detalles del esquema]**, seleccione **[!UICONTROL Otro]** y, a continuación, seleccione **[!UICONTROL Personalizado]**.

   ![Crear personalizado](assets/schema-custom.png)

1. Seleccione **[!UICONTROL Crear clase]**.

   <!-- add screenshot -->

1. En el cuadro de diálogo **[!UICONTROL Crear clase]**, especifique un nombre y una descripción para el esquema, seleccione **[!UICONTROL Registro]** y, a continuación, seleccione **[!UICONTROL Crear]**.

1. Continúe con [Crear un conjunto de datos de consulta](#create-a-lookup-dataset).

## Creación de un conjunto de datos de consulta

Después de [crear un esquema personalizado](#create-a-custom-schema-to-use-with-the-lookup-dataset) para utilizarlo en un conjunto de datos de consulta, debe crear el conjunto de datos de consulta y asignarlo a su esquema.

Repita este proceso para cada dimensión que contenga datos que desee clasificar.

Para crear un conjunto de datos de consulta para utilizarlo con un esquema en Customer Journey Analytics:

>[!NOTE]
>
>El siguiente proceso utiliza un archivo CSV para crear el conjunto de datos. También puede utilizar cualquier otro método disponible para importar datos a Experience Platform, como configurar una secuencia de datos.

1. En la interfaz de usuario de Adobe Experience Platform, seleccione **[!UICONTROL Flujos de trabajo]** en el carril izquierdo.

   ![Crear personalizado](assets/lookup-dataset-workflows.png)

1. Seleccione **[!UICONTROL Asignar CSV al esquema XDM]** y, a continuación, seleccione **[!UICONTROL Iniciar]**.

1. En la sección **[!UICONTROL Detalles del conjunto de datos]**, seleccione **[!UICONTROL Nuevo conjunto de datos]**.

1. Especifique un nombre y una descripción para la aplicación.

1. En el campo **[!UICONTROL Esquema]**, seleccione el esquema que creó para los conjuntos de datos de consulta, tal como se describe en [Crear un esquema para los conjuntos de datos de consulta](#create-a-schema-for-lookup-datasets).

1. Seleccione **[!UICONTROL Siguiente]**.

1. En la **[!UICONTROL página del esquema Asignar CSV a XDM]**, en la sección **[!UICONTROL Cargar archivos]**, seleccione **[!UICONTROL Elegir archivos]** y, a continuación, busque en el sistema de archivos el archivo que contiene la información de clasificación de la dimensión a la que desea aplicar los datos de clasificación. Por ejemplo, puede ser una hoja de cálculo que enumere los ID de campo y los nombres de campo correspondientes. <!-- correct? How can I better explain what this file is?-->

   ![Asignar archivo CSV](assets/lookup-map-csv.png)

1. Seleccione **[!UICONTROL Siguiente]**.

1. Una vez cargado el archivo, revise las asignaciones para asegurarse de que son precisas. Las columnas del archivo CSV se enumeran en **[!UICONTROL Datos de origen]** y sus campos de esquema XDM correspondientes se indican en **[!UICONTROL Campo de destino]**.

   Platform proporciona automáticamente recomendaciones inteligentes para los campos asignados automáticamente en función del esquema o el conjunto de datos de destino seleccionado. Puede ajustar manualmente las reglas de asignación para adaptarlas a sus casos de uso.

   Para obtener más información sobre el proceso de asignación, consulte [Asignación de un archivo CSV a un esquema XDM existente](https://experienceleague.adobe.com/es/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) en la documentación de Experience Platform.

1. Seleccione **[!UICONTROL Finalizar]**.

1. Continúe con [Añadir el conjunto de datos de consulta a su conexión en Customer Journey Analytics](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics).

## Añada el conjunto de datos de consulta a su conexión en Customer Journey Analytics

Después de [crear un esquema personalizado](#create-a-custom-schema-to-use-with-the-lookup-dataset) y [crear un conjunto de datos de consulta](#create-a-lookup-dataset), debe añadir el conjunto de datos de consulta a su conexión en Customer Journey Analytics.

Repita este proceso para cada dimensión que contenga datos que desee clasificar.

Para añadir el conjunto de datos de consulta a su conexión en Customer Journey Analytics:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Conexiones]**, opcionalmente desde **[!UICONTROL Administración de datos]**, en el menú superior.

1. Seleccione el ![icono Más](assets/More.svg) junto a la conexión donde desea añadir el conjunto de datos de consulta y, a continuación, seleccione **[!UICONTROL Editar]**.

   <!-- add screenshot -->

1. Seleccione **[!UICONTROL Agregar conjuntos de datos]**.

1. En el cuadro de diálogo **[!UICONTROL Añadir conjuntos de datos]**, seleccione el conjunto de datos de consulta que ha creado y, a continuación, seleccione **[!UICONTROL Siguiente]**.

1. En el campo **[!UICONTROL ID de persona]**, seleccione un ID de persona de las identidades disponibles definidas en el esquema de su conjunto de datos que configuró en Experience Platform. <!-- fill out other fields? -->

1. Seleccione **[!UICONTROL Agregar conjuntos de datos]** y luego seleccione **[!UICONTROL Guardar]**.

   <!-- is there a step right in between here where you select the dataset -->

1. Utilizando el campo **[!UICONTROL Clave]** y el campo **[!UICONTROL Clave de coincidencia]**, cree una correlación entre el campo del conjunto de datos de consulta y el del conjunto de datos de resumen o evento.

1. Repita este proceso hasta que todos los conjuntos de datos de búsqueda se añadan a la conexión en Customer Journey Analytics.

{{upgrade-final-step}}

