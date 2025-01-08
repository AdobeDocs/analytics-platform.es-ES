---
title: Claves administradas por el cliente
description: Obtenga información sobre cómo configurar claves administradas por el cliente para Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 14%

---

# Claves administradas por el cliente

Adobe Customer Journey Analytics proporciona la opción para que los clientes de [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) y Privacy &amp; Security Shield utilicen claves gestionadas por el cliente (CMK) para los datos del Customer Journey Analytics. Tenga en cuenta que este proceso es independiente de [Adobe Experience Platform CMK setup](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Las claves administradas por el cliente solo están disponibles para las organizaciones que hayan adquirido el complemento [Healthcare Shield o Privacy &amp; Security Shield](https://experienceleague.adobe.com/es/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield).

## Configurar claves administradas por el cliente para Customer Journey Analytics en Azure

Siga estos pasos para configurar CMK para el Customer Journey Analytics que se ejecuta en Azure:

1. Asegúrese de que tiene derecho a Adobe Customer Journey Analytics CMK y de que su organización utiliza Adobe Experience Platform, que se ejecuta en Azure. Puede comprobar estos derechos poniéndose en contacto con el equipo de la cuenta de Adobe.
1. Asegúrese de que, en Azure, es un administrador con una función de privilegio, como administrador de aplicaciones, administrador de aplicaciones de nube o administrador global. Consulte [Funciones integradas de Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference) para obtener más información.
1. Cree un nuevo Azure Key Vault para utilizarlo solo con Customer Journey Analytics. Consulte [Documentación de Microsoft Azure Key Vault](https://learn.microsoft.com/es-es/azure/key-vault/general/) para obtener más información.
1. Conceda acceso a la aplicación de Adobe Azure a su clave en el almacén de claves. Consulte [Configurar claves administradas por el cliente para una cuenta existente](https://learn.microsoft.com/es-es/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault) para obtener más información. El ID de aplicación de Adobe es:

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Cree un ticket del Servicio de atención al cliente de Adobe solicitando la configuración de CMK. Incluya el URI de Azure en su ticket. El URI se encuentra en el campo **Identificador de clave** de la clave de Azure:

   ![Campos de identificador de clave que muestran el URI de https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. El Servicio de atención al cliente de Adobe confirma la finalización de la aplicación CMK en los datos del Customer Journey Analytics.

Todos los datos que utiliza Platform se cifran en tránsito y en reposo para mantener los datos seguros, con o sin claves administradas por el cliente. Para obtener información sobre el cifrado de Adobe Experience Platform, consulte [Cifrado de datos en Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption).

## Configurar claves administradas por el cliente para Customer Journey Analytics en Amazon Web Service

>[!AVAILABILITY]
>
>Esta sección se aplica a las implementaciones de Experience Platform que se ejecutan en Amazon Web Service (AWS). Un Experience Platform que se ejecuta en AWS está disponible actualmente para un número limitado de clientes. Para obtener más información acerca de la infraestructura de Experience Platform compatible, consulte la [descripción general de la nube múltiple de Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud).

Si su organización utiliza Adobe Experience Platform con Amazon Web Service, CMK ya estará configurado para usted. No se necesita ninguna configuración adicional.
