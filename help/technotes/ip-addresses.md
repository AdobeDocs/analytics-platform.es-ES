---
title: Direcciones IP utilizadas por Customer Journey Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
solution: Customer Journey Analytics
feature: Basics
exl-id: 5c52986c-7ff3-45b5-9039-2bfb6529238c
role: Admin
source-git-commit: 0e4ea634a604a65484a57f5af8021badb86a865a
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 34%

---

# Direcciones IP utilizadas por Customer Journey Analytics

La configuración de algunos cortafuegos bloquea las direcciones IP que se originan de los servidores de recopilación de datos de Adobe o de los servidores responsables de acceder a datos. Puede utilizar esta lista de intervalos para modificar la configuración del cortafuegos de su organización y permitir el acceso y enviar datos desde su organización.

Esta página incluye las direcciones IP que debe agregar a la lista de permitidos para que funcionen los sistemas salientes, como [exportar datos a un proveedor de la nube](/help/analysis-workspace/export/export-cloud.md).

>[!IMPORTANT]
>
>Aunque Adobe hace todo lo posible para mantener este documento actualizado, no puede garantizar que la lista de intervalos de IP sea la misma. Los posibles cambios incluyen el crecimiento y la expansión del negocio, un registro de Internet requiere cambios en el espacio de direcciones IP de Adobe o un proveedor de servicio de Internet deja de funcionar.

## Clientes de EE. UU. y América

| Bloque IP (notación CIDR) |
| --- |
| `52.254.106.192/28` |
| `52.254.107.80/28` |
| `52.254.106.240/28` |
| `52.254.107.32/28` |
| `52.254.106.176/28` |
| `52.254.106.144/28` |
| `52.254.107.64/28` |
| `20.186.185.181` |
| `20.186.185.239` |
| `52.254.106.160/28` |
| `40.70.154.136/29` |
| `20.22.83.112` |
| `52.254.107.16/28` |
| `52.254.105.192/28` |
| `52.254.107.144/28` |
| `52.254.106.0/28` |
| `52.254.106.224/28` |
| `52.254.107.128/28` |
| `52.254.106.208/28` |
| `20.186.185.227` |
| `52.254.107.0/28` |
| `66.117.18.0/24` |

## Europa

| Bloque IP (notación CIDR) |
| --- |
| `40.74.6.128/28` |
| `51.144.184.248/29` |
| `40.74.7.192/28` |
| `40.74.7.128/28` |
| `40.74.7.176/28` |
| `20.50.23.153` |
| `40.74.6.80/28` |
| `40.74.6.144/28` |
| `40.74.5.128/28` |
| `51.105.144.1` |
| `51.105.144.81` |
| `40.74.4.176/28` |
| `52.142.236.87` |
| `40.74.4.144/28` |
| `20.101.246.9` |
| `40.74.4.160/28` |
| `40.74.7.160/28` |
| `40.74.7.144/28` |
| `40.74.3.176/28` |
| `51.124.70.4` |
| `40.74.6.96/28` |
| `40.74.7.208/28` |
| `40.74.6.112/28` |

## Australia

| Bloque IP (notación CIDR) |
| --- |
| `20.43.110.192/28` |
| `20.40.185.111` |
| `20.43.97.95` |
| `20.43.111.16/28` |
| `20.193.38.208/28` |
| `20.43.110.64/28` |
| `20.40.185.225` |
| `20.43.110.112/28` |
| `20.43.110.224/28` |
| `20.193.36.37` |
| `20.43.110.240/28` |
| `20.43.111.32/28` |
| `20.40.185.185` |
| `20.43.111.0/28` |
| `20.43.110.208/28` |
| `20.43.110.96/28` |
| `20.43.110.48/28` |
| `20.43.110.128/28` |
| `20.43.110.160/28` |
| `20.43.110.80/28` |
| `20.193.56.144/28` |
| `20.193.56.160/28` |
| `20.43.110.176/28` |
| `20.43.110.144/28` |
| `20.53.111.113` |
| `20.193.56.128/28` |
| `20.227.32.175` |

## Canadá

| Bloque IP (notación CIDR) |
| --- |
| `20.116.159.80/28` |
| `20.116.159.224/28` |
| `20.116.159.192/28` |
| `20.116.159.64/28` |
| `20.151.241.173` |
| `20.116.159.128/28` |
| `20.116.159.208/28` |
| `20.116.159.48/28` |
| `20.151.240.247` |
| `20.116.159.0/28` |
| `20.220.243.238` |
| `20.116.175.240/28` |
| `20.116.155.128/28` |
| `20.116.248.0/28` |
| `20.151.241.138` |
| `20.116.159.144/28` |
| `20.116.175.224/28` |
| `20.116.248.16/28` |
| `20.151.241.124` |
| `20.116.159.160/28` |
| `20.116.159.96/28` |
| `20.104.5.248` |
| `20.116.159.112/28` |
| `20.116.159.176/28` |
| `20.116.159.32/28` |
| `20.116.158.240/28` |

>[!MORELIKETHIS]
>
>[Dominios utilizados por Customer Journey Analytics](domains.md)
>
>[Direcciones IP utilizadas por Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)