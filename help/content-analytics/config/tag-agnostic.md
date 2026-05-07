---
title: Configuración independiente de etiquetas de Content Analytics
description: Obtenga información sobre cómo configurar Content Analytics sin utilizar etiquetas de recopilación de datos de Experience Platform
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
source-git-commit: d324e2b03d47ba1cf8e5abbadc817b98b27ea68e
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 5%

---

# Configuración agnóstica de etiquetas de Content Analytics

La biblioteca JavaScript de Adobe Content Analytics permite el seguimiento de eventos relacionados con el contenido en sitios web mediante el envío de datos de contenido a Adobe Experience Platform a través de Experience Platform Edge Network. Utilice esta biblioteca cuando desee implementar Content Analytics sin etiquetas Adobe Experience Platform (Launch).

>[!PREREQUISITES]
>
>Adobe Experience Platform Web SDK (Alloy) debe inicializarse en la página antes de llamar a `initializeContentLibrary`.

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

## Filtro de evento

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

>[!NOTE]
>
>Después de establecer una configuración de Content Analytics en la interfaz de [configuración guiada](/help/content-analytics/config/guided.md), las opciones de JavaScript específicas de su configuración están disponibles en esa vista de configuración.

