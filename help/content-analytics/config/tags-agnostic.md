---
title: Biblioteca JavaScript de Content Analytics
description: Obtenga información sobre cómo configurar Content Analytics sin utilizar etiquetas de recopilación de datos de Experience Platform y utilizar la biblioteca JavaScript de Content Analytics en su lugar.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
autotag-review: '2026-05-19T06:56:34.440Z'
TQID: 'https://experienceleague.adobe.com/GUYf0ZoTlAkoIIPWzfZTm0-eMvBjN8ieYSu6goHu3GA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 484
ht-degree: 4%

---


# Biblioteca JavaScript de Content Analytics

La biblioteca JavaScript de Adobe Content Analytics permite el seguimiento de eventos relacionados con el contenido en sitios web mediante el envío de datos de contenido a Adobe Experience Platform a través de Experience Platform Edge Network. Utilice esta biblioteca cuando desee implementar Content Analytics sin etiquetas de Adobe Experience Platform.

>[!NOTE]
>
>Este artículo se aplica a Content Analytics para el canal Web.


>[!PREREQUISITES]
>
>* Adobe Experience Platform Web SDK (Alloy) debe inicializarse en la página antes de llamar a `initializeContentLibrary`.
>* Complete el asistente de configuración guiada de Content Analytics para guiarle por todos los pasos necesarios para configurar los requisitos previos de una configuración de Content Analytics.
>* Una vez finalizada la configuración guiada, los ajustes de JavaScript están disponibles para su uso.


## Instalación

Puede instalar la biblioteca de dos formas:

### npm package

Use `npm` para instalar la biblioteca.

1. En la línea de comandos, utilice:

   ```bash
   npm install @adobe/content-analytics
   ```

1. Importe la biblioteca:

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### Etiqueta de script (CDN)

Cargue la biblioteca directamente desde la CDN.

1. Inicialice la [biblioteca JavaScript de Web SDK](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/install/library) y cargue el paquete de Content Analytics:

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   dónde
   * `alloy/2.x.x` hace referencia a la versión que desea usar de la [biblioteca de Web SDK JavaScript](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/install/library).
   * `content-analytics/1.x.x` hace referencia a la versión que desea utilizar de la biblioteca SDK de Content Analytics.

2. La compilación independiente expone `window.contentAnalytics` como función de inicialización.


## Configuración de flujo de datos

La opción `datastreamId` es obligatoria y debe hacer referencia a un conjunto de datos que tenga el servicio de Experience Platform configurado con un conjunto de datos de evento de experiencia de Content Analytics habilitado. Asegúrese de que la zona protegida asociada con el conjunto de datos no esté ya asociada a otra configuración de Content Analytics.

Puede proporcionar ID de flujo de datos independientes por entorno:

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Captura y definición de experiencias

Habilite el seguimiento de experiencias y controle cómo se identifican las experiencias en su sitio web. Las experiencias se definen combinando una **expresión regular de dominio** con **parámetros de consulta** opcionales que distinguen una experiencia de otra en páginas coincidentes.

| Opción | Tipo | Predeterminado | Descripción |
|--------|------|---------|-------------|
| `includeExperiences` | booleano | `false` | Habilitar seguimiento de vista de página/experiencia |
| `experienceConfigurations` | matriz | - | Definir experiencias por regex de dominio y parámetros de consulta |

Cada entrada de `experienceConfigurations` acepta:

| Propiedad | Tipo | Descripción |
|----------|------|-------------|
| `regEx` | string | Expresión regular de dominio coincidente con la dirección URL de la página (p. ej. `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | matriz | Nombres de parámetros de consulta cuyos valores distinguen experiencias en páginas coincidentes (p. ej. `["outdoors", "patio", "kitchen"]`) |

### Ejemplo

Consulte a continuación un ejemplo de cómo habilitar el seguimiento de experiencias con regex de dominio y parámetros de consulta.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## Filtrado de eventos

Controle qué direcciones URL de página y direcciones URL de recursos se incluyen en la recopilación de datos mediante expresiones regulares. Utilice los ejemplos de patrones siguientes como punto de partida y valide los patrones con un comprobador regex antes de la implementación.

| Opción | Tipo | Predeterminado | Descripción |
|--------|------|---------|-------------|
| `pageUrlQualifier` | cadena (regex) | - | Rastrear solo páginas cuya dirección URL coincida con este patrón |
| `assetUrlQualifier` | cadena (regex) | - | Rastrear solo recursos cuya dirección URL coincida con este patrón |
| `excludeURLsFromTracking` | matriz | `[]` | Lista de cadenas de URL que se excluirán del seguimiento |

### Ejemplo

Consulte a continuación un ejemplo de cómo excluir páginas de documentación de Content Analytics y tener en cuenta solo imágenes de producto para Content Analytics.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
