---
title: Creación de un campo derivado de canal de marketing para Customer Journey Analytics
description: Obtenga información sobre cómo crear un campo derivado de canal de marketing para Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
TQID: https://experienceleague.adobe.com/nwxJ3KEss3SlZxpGB-CW4qDW9QpQqXL1kN-VslhuAVE
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 291
ht-degree: 100%

---

# Creación de un campo derivado de canal de marketing para Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Creación de un campo derivado de canal de marketing"
>abstract="Los campos derivados se crean dentro de una vista de datos.<br><br>Utilizar una configuración de canal de marketing predeterminada solo lleva unos minutos; crear una configuración de canal de marketing muy personalizada puede llevar varias horas."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Cuando se utiliza el conector de origen de Analytics, los datos de los canales de marketing fluyen hacia Customer Journey Analytics a través de ese conector. Las reglas del canal de marketing deben seguir configurándose en la versión tradicional de Adobe Analytics y algunas no son compatibles. Para obtener más información, consulte [Uso de dimensiones de canal de marketing](/help/use-cases/aa-data/marketing-channels.md).

Para poder utilizar canales de marketing en Customer Journey Analytics cuando se utiliza el SDK web de Experience Platform, puede utilizar campos derivados en una vista de datos para volver a crear los mismos canales de marketing y reglas de procesamiento para Customer Journey Analytics.

1. En Customer Journey Analytics, seleccione la vista de datos en la que desea añadir canales de marketing.

1. En la vista de datos, seleccione la pestaña **[!UICONTROL Componentes]**.

1. Seleccione **[!UICONTROL Crear campo derivado]** en el carril izquierdo.

1. En el cuadro de diálogo **[!UICONTROL Crear campo derivado]**, seleccione **[!UICONTROL Plantillas de funciones]** en el menú desplegable.

   ![Creación de plantillas de funciones de campo derivado](assets/derived-field-create.png)

1. Arrastre la plantilla **[!UICONTROL Canales de marketing]** al lienzo vacío.

1. Personalice la lógica de cada canal de marketing para asegurarse de que coincida con la lógica que utiliza para identificar cada canal en su entorno de Adobe Analytics.

   Puede modificar los nombres de los canales de salida o añadir lógica para identificar canales adicionales específicos de su organización.

1. En la columna de la derecha, especifique un nombre y una descripción para el canal de marketing.

1. Seleccione **[!UICONTROL Guardar]**.

   El nuevo campo derivado se añade al contenedor Campos derivados > como parte de los Campos de esquema en el carril izquierdo de la vista Datos.

{{upgrade-final-step}}
