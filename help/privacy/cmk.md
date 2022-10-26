---
title: Claves administradas por el cliente
description: Aprenda a configurar claves gestionadas por el cliente para CJA.
hide: true
hidefromtoc: true
source-git-commit: 3aa5d9e1b426e67f27ef1909a2640f335719502a
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Claves administradas por el cliente

>[!NOTE]
>
>Esta funcionalidad estará disponible en noviembre de 2022.

Customer Journey Analytics (CJA) proporciona la opción para [Escudo sanitario](https://www.adobe.com/trust/compliance/hipaa-ready.html) y los clientes de Privacy &amp; Security Shield para utilizar una clave administrada por el cliente de Azure (CMK) que se aplicará a sus datos de CJA.  Tenga en cuenta que este proceso es independiente de [Configuración de Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Actualmente, las claves gestionadas por el cliente solo están disponibles para las organizaciones que han adquirido la variable [Escudo de protección sanitaria o Escudo de privacidad y seguridad](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) oferta de complementos.

## Configuración de CMK para CJA

Siga estos pasos para configurar CMK para CJA:

1. Asegúrese de que tiene derecho a Adobe CJA CMK comprobando con su equipo de cuenta de Adobe.
1. Asegúrese de que, en Azure, es un administrador con una función privilegiada, como administrador de aplicaciones, administrador de aplicaciones de nube o administrador global. [Obtenga más información en Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Cree un nuevo Azure Key Vault para utilizarlo solo con CJA. [Obtenga más información en Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Conceda acceso a la aplicación de Adobe Azure a su clave en el almacén de claves. Este es el ID de aplicación de Adobe: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Obtenga más información en Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Cree un ticket del Servicio de atención al cliente de Adobe solicitando la configuración de CMK. Incluya el URI de Azure en su ticket.
1. El Servicio de atención al cliente de Adobe confirmará la finalización de la aplicación CMK en sus datos de CJA.
