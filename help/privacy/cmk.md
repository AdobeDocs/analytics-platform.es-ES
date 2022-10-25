---
title: Claves administradas por el cliente
description: Aprenda a configurar claves gestionadas por el cliente para CJA.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
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

Siga estos pasos para configurar CMK para CJA:

1. Asegúrese de tener derecho a CMK comprobando con su equipo de cuenta de Adobe.
1. Cree un nuevo Azure Key Vault para utilizarlo solo con CJA.
1. Asocie su valor de clave de Azure a la aplicación CMK de Azure CJA (vínculo a continuación).
1. Cree un ticket del Servicio de atención al cliente de Adobe solicitando la configuración de CMK. Incluya el URI de Azure en su ticket.
1. El Servicio de atención al cliente de Adobe confirmará la finalización de la aplicación CMK en sus datos de CJA.
