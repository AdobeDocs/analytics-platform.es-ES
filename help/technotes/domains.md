---
title: Dominios utilizados por Customer Journey Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

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
| MICROSOFT® AZURE CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Dominios empresariales de CX

Además de los dominios anteriores, CX Enterprise se basa en varios dominios para recopilar datos y exportar informes. Consulte [Dominios utilizados por CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) para obtener esta lista de dominios.

>[!MORELIKETHIS]
>
>[Direcciones IP utilizadas por Customer Journey Analytics](ip-addresses.md)
>
>[Dominios utilizados por CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
