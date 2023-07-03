---
title: Claves gestionadas por el cliente
description: Obtenga información sobre cómo configurar claves gestionadas por el cliente para Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 66%

---

# Claves gestionadas por el cliente

Adobe Customer Journey Analytics proporciona la opción para [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) y a los clientes de Privacy &amp; Security Shield para utilizar una clave gestionada por el cliente de Azure (CMK) que se aplicará a los datos del Customer Journey Analytics.  Tenga en cuenta que este proceso es independiente de la [configuración de Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=es).

>[!NOTE]
>
>Actualmente, las claves gestionadas por el cliente solo están disponibles para las organizaciones que han adquirido el complemento [Healthcare Shield or Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html?lang=es).

## Configurar CMK para el Customer Journey Analytics

Siga estos pasos para configurar CMK para Customer Journey Analytics:

1. Asegúrese de que tiene derecho a Adobe Customer Journey Analytics CMK comprobando con su equipo de cuenta de Adobe.
1. Asegúrese de que, en Azure, es un administrador con una función de privilegio, como administrador de aplicaciones, administrador de aplicaciones de nube o administrador global. [Obtenga más información en Microsoft](https://learn.microsoft.com/es-es/azure/active-directory/roles/permissions-reference)
1. Cree un nuevo Azure Key Vault para utilizarlo solo con Customer Journey Analytics. [Obtenga más información en Microsoft](https://learn.microsoft.com/es-es/azure/key-vault/general/)
1. Conceda acceso a la aplicación de Adobe Azure a su clave en el almacén de claves. Este es el ID de aplicación de Adobe: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Obtenga más información en Microsoft](https://learn.microsoft.com/es-es/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Cree un ticket del Servicio de atención al cliente de Adobe solicitando la configuración de CMK. Incluya el URI de Azure en su ticket. El URI se puede encontrar en el campo **Identificador de clave** de la clave de Azure.

   ![](assets/key-identifier.png)

1. El Servicio de atención al cliente de Adobe confirmará la finalización de la aplicación CMK en los datos de su Customer Journey Analytics.

Todos los datos que utiliza Platform se cifran en tránsito y en reposo para mantener sus datos seguros, con o sin CMK. Para saber más sobre el cifrado de Adobe Experience Platform, haga clic en [más información](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=es).
