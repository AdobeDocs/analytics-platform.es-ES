---
title: Creación de un esquema para Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 60%

---

# Creación de un conjunto de datos para utilizarlo con Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Creación de un conjunto de datos en Adobe Experience Platform"
>abstract="Un conjunto de datos es una ubicación en la que residen los datos recopilados. Cree esta ubicación en Adobe Experience Platform.<br><br>Crear un conjunto de datos con un esquema en mente solo lleva unos minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Un conjunto de datos es la construcción que almacena y administra los datos que recopila en Adobe Experience Platform.

Para crear un conjunto de datos:

1. En Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Conjuntos de datos]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

1. Seleccione **[!UICONTROL Crear conjunto de datos]**.

   ![Crear conjunto de datos](assets/create-dataset.png)

1. Seleccione **[!UICONTROL Crear conjunto de datos a partir de esquema]**.

   ![Crear conjunto de datos a partir de esquema](assets/create-dataset-from-schema.png)

1. Seleccione el esquema creado anteriormente y, después, **[!UICONTROL Siguiente]**.

1. Asigne un nombre al conjunto de datos y (opcionalmente) proporcione una descripción.

   ![Nombre del conjunto de datos](assets/name-your-datatest.png)

1. Seleccione **[!UICONTROL Finalizar]**.

1. Seleccione el conmutador **[!UICONTROL Perfil]**.

   Se le pedirá que habilite el conjunto de datos para el perfil. Una vez habilitado, el conjunto de datos enriquece los perfiles de clientes en tiempo real con sus datos ingeridos.

   >[!IMPORTANT]
   >
   >    Solo puede habilitar un conjunto de datos para un perfil cuando el esquema, al que se adhiere el conjunto de datos, también esté habilitado para el perfil.

   ![Habilitar esquema para perfil](assets/aepwebsdk-dataset-profile.png)

   Consulte [Guía de la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) para obtener mucha más información sobre cómo ver, previsualizar, crear y eliminar un conjunto de datos. También puede aprender a habilitar un conjunto de datos para el perfil del cliente en tiempo real.

{{upgrade-final-step}}
