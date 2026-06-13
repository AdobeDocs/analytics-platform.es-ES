---
title: Asignación del modelo de datos de GA4 a Customer Journey Analytics
description: Comprenda cómo el modelo de datos basado en eventos de GA4 se traduce a esquemas XDM y conjuntos de datos en Customer Journey Analytics.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# Asignación del modelo de datos de GA4 a Customer Journey Analytics

GA4 y Customer Journey Analytics son plataformas basadas en eventos, lo que hace que la traducción del modelo de datos entre ellas sea más directa de lo que era desde Universal Analytics. Entender cómo los eventos y parámetros de GA4 se corresponden con los campos XDM y los conjuntos de datos de Customer Journey Analytics facilita la interpretación de los informes y la colaboración con el equipo de implementación.

## Modelo de datos basado en eventos de GA4

Cada interacción en GA4 es un **evento**: una acción con nombre con un conjunto opcional de **parámetros** que proporciona contexto. No hay tipos de objetos independientes para vistas de página, sesiones u objetivos; todos son eventos.

| Tipo de evento de GA4 | Ejemplos |
|---|---|
| Recopilado automáticamente | `page_view`, `session_start`, `first_visit`, `scroll` |
| Medición mejorada | `file_download`, `video_start`, `form_submit` |
| Recomendado | `purchase`, `add_to_cart`, `sign_up` |
| Personalizado | Cualquier nombre de evento que defina |

Cada evento puede llevar hasta 25 parámetros. Por ejemplo, un evento `purchase` suele incluir `transaction_id`, `value`, `currency` y `items` como parámetros.

## Almacenamiento de datos en Customer Journey Analytics

Customer Journey Analytics obtiene sus datos de **Adobe Experience Platform**. Los datos de Platform se almacenan en **conjuntos de datos**, cada uno de los cuales se ajusta a un **esquema** creado con el **Modelo de datos de experiencia (XDM)**. XDM es el estándar abierto de Adobe para representar los datos de experiencia del cliente.

Hay tres tipos de conjuntos de datos utilizados en Customer Journey Analytics:

| tipo de conjunto de datos CJA | equivalente de GA4 | Lo que contiene |
|---|---|---|
| [!UICONTROL Conjunto de datos de evento] | Flujo de evento de GA4 | Interacciones de series de tiempo (vistas de página, clics, compras) |
| [!UICONTROL Conjunto de datos de perfil] | Propiedades de usuario de GA4 | Atributos de nivel de persona (campos CRM, estado de lealtad, demografía) |
| [!UICONTROL Conjunto de datos de consulta] | Dimensiones personalizadas de GA4 utilizadas como tablas de referencia | Datos de referencia de clave-valor (catálogo de productos, nombres de campañas) |

Customer Journey Analytics no tiene eVars, props ni eventos de éxito. Todas las dimensiones y métricas proceden directamente de campos de esquema XDM. No hay límites en la cantidad de valores de dimensión únicos.

## Eventos recopilados automáticamente

GA4 registra automáticamente un conjunto de eventos a través de su SDK. La siguiente tabla asigna esos eventos a sus equivalentes XDM o Customer Journey Analytics.

| Evento recopilado automáticamente de GA4 | Equivalente de XDM/Customer Journey Analytics |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` (campo XDM estándar) |
| `session_start` | Inicio de sesión (automático, por definición de sesión de vista de datos) |
| `first_visit` | Segmento de [!UICONTROL primera sesión] |
| `scroll` | Evento personalizado (requiere una asignación de implementación explícita) |
| `click` | `xdm.web.webInteraction` campos (requiere implementación) |
| `video_start` / `video_complete` | Campos de esquema de recopilación de medios (con servicios de medios de streaming de Adobe) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order` (esquema comercial XDM estándar) |
| `add_to_cart` | `xdm.commerce.productListAdds` (esquema de comercio XDM estándar) |

>[!NOTE]
>
>Varios de los eventos de medición mejorados de GA4 (como desplazamiento, descarga de archivos o vídeo) requieren una asignación explícita a campos XDM al implementar mediante Web SDK. No se recopilan automáticamente del mismo modo que los gestiona SDK de GA4.

## Eventos y parámetros personalizados

En GA4, los eventos personalizados tienen un nombre y hasta 25 parámetros. En Customer Journey Analytics, los eventos personalizados se asignan a campos de esquema XDM personalizados definidos durante la implementación:

* El **nombre de evento** se convierte en un valor de campo en un campo XDM (normalmente [`xdm.eventType`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)).
* Cada **parámetro** se convierte en un campo de esquema XDM independiente. Cualquier campo XDM puede exponerse como dimensión o como métrica al [configurar una vista de datos](/help/data-views/component-settings/overview.md).

>[!NOTE]
>
>Las rutas de campo XDM específicas para los eventos personalizados de su organización se determinan durante la implementación de Web SDK. Trabaje con su equipo de implementación para comprender la asignación de campos específica antes de crear informes. Consulte [Arquitectar su esquema](../cja-upgrade/cja-upgrade-schema-architect.md) para obtener más información.

## Propiedades del usuario

Las propiedades de usuario de GA4 son atributos persistentes establecidos en un usuario (por ejemplo, `membership_tier` o `account_type`). En Customer Journey Analytics, se asignan a **conjuntos de datos de perfil** en Platform.

Un conjunto de datos de perfil se ingiere por separado de los datos de evento y se une a él en Customer Journey Analytics mediante un ID de persona compartido. Los ID de persona comunes utilizados en este contexto incluyen un ID de cliente o un hash de correo electrónico. Una vez unidos, esos atributos de perfil están disponibles como dimensiones en Analysis Workspace junto con los datos de nivel de evento.

Este enfoque le da a Customer Journey Analytics más flexibilidad que el modelo de propiedades de usuario de GA4: GA4 le limita a las propiedades de usuario definidas en su SDK, mientras que los conjuntos de datos de perfil de Customer Journey Analytics pueden incluir cualquier atributo de cualquier sistema (CRM, plataforma de lealtad, registros de soporte) siempre y cuando comparta un identificador unido.

Si su organización aún necesita introducir datos de GA en Adobe Experience Platform, consulte [Ingesta de datos históricos de Google Analytics](/help/use-cases/third-party/ga/backfill.md) y [Configuración de la transmisión de datos de Google Analytics](/help/use-cases/third-party/ga/streaming.md) para ver las guías de configuración de administración.
