---
title: Creación de un campo derivado del canal de marketing para Customer Journey Analytics
description: Obtenga información sobre cómo crear un campo derivado de canal de marketing para Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 25%

---

# Creación de un campo derivado del canal de marketing para Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Creación de un campo derivado del canal de marketing"
>abstract="Los campos derivados se crean dentro de una vista de datos.<br><br>Utilizar una configuración de canal de marketing predeterminada solo lleva unos minutos; crear una configuración de canal de marketing muy personalizada puede llevar varias horas."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Al utilizar el conector de origen de Analytics, los datos de los canales de marketing fluyen a Customer Journey Analytics a través de ese conector. Las reglas del canal de marketing deben seguir configurándose en la versión tradicional de Adobe Analytics y algunas no son compatibles. Para obtener más información, consulte [Usar dimensiones del canal de marketing](/help/use-cases/aa-data/marketing-channels.md).

Para utilizar canales de marketing en Customer Journey Analytics al utilizar Experience Platform Web SDK, puede utilizar campos derivados en una vista de datos para volver a crear los mismos canales de marketing y reglas de procesamiento para Customer Journey Analytics.

1. En Customer Journey Analytics, seleccione la vista de datos donde desee agregar canales de marketing.

1. En la vista de datos, seleccione la ficha **[!UICONTROL Componentes]**.

1. Seleccione **[!UICONTROL Crear campo derivado]** en el carril izquierdo.

1. En el cuadro de diálogo **[!UICONTROL Crear campo derivado]**, seleccione **[!UICONTROL Plantillas de función]** del menú desplegable.

   ![Crear plantillas de función de campo derivado](assets/derived-field-create.png)

1. Arrastre la plantilla **[!UICONTROL Canales de mercadotecnia]** al lienzo vacío.

1. Personalice la lógica de cada canal de marketing para asegurarse de que coincida con la lógica que utiliza para identificar cada canal en su entorno de Adobe Analytics.

   Puede modificar los nombres de los canales de salida o agregar lógica para identificar canales adicionales específicos de su organización.

1. En la columna derecha, especifique un nombre y una descripción para el canal de marketing.

1. Seleccione **[!UICONTROL Guardar]**.

   El nuevo campo derivado se agrega al contenedor Campos derivados > como parte de los Campos de esquema en el carril izquierdo de la vista Datos.

{{upgrade-final-step}}
