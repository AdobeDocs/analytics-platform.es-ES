---
title: Dominios utilizados por Customer Journey Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Dominios utilizados por Customer Journey Analytics

Algunas configuraciones de cortafuegos bloquean los dominios en los que Customer Journey Analytics depende para su interfaz de producto. Puede utilizar esta lista de dominios para modificar la configuración de red de su organización y permitir el acceso a los productos desde su organización. Adobe recomienda permitir estos dominios a través del cortafuegos de su organización para una experiencia óptima.

| Tecnología | Dominio |
| --- | --- |
| dominios de Customer Journey Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Almacenamiento de Microsoft® Azure Blob | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Dominios de Adobe Experience Cloud

Además de los dominios anteriores, Adobe Experience Cloud se basa en varios dominios para recopilar datos y exportar informes. Consulte [Dominios utilizados por Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/domains) para obtener esta lista de dominios.

>[!MORELIKETHIS]
>
>[Direcciones IP utilizadas por Customer Journey Analytics](ip-addresses.md)
>
>[Dominios utilizados por Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/domains)
