---
title: Crear un esquema para el Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 30%

---

# Crear un conjunto de datos para utilizarlo con un Customer Journey Analytics

>[!NOTE]
>
>Esta documentación se debe usar después de completar el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Siga los pasos de esta página solo después de completar todos los pasos anteriores generados dinámicamente para su organización.
>
>Después de completar los pasos de esta página, continúe siguiendo los pasos de actualización que se generaron dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Después de crear un esquema XDM, ahora debe definir la construcción para almacenar y administrar esos datos, lo que se hace en Adobe Experience Platform a través de un conjunto de datos.

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

1. Continúe siguiendo los pasos de actualización generados dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

