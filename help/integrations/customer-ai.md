---
description: Descubra cómo AEP Customer AI se integra con Workspace en CJA.
title: Integración de Customer AI con CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---


# Integración de Customer AI con CJA

>[!NOTE]
>
>Esta página está en construcción.

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), como parte de Adobe Experience Platform Intelligent Services, proporciona a los especialistas en marketing la capacidad de generar predicciones de clientes a nivel individual.

Con la ayuda de factores influyentes, la Customer AI puede indicarle qué es lo más probable que haga un cliente y por qué. Además, los especialistas en marketing pueden beneficiarse de las predicciones y perspectivas de Customer AI para personalizar las experiencias de los clientes al ofrecer las ofertas y los mensajes más adecuados.

La AI del cliente funciona analizando uno de los siguientes conjuntos de datos para predecir puntuaciones de tendencia de pérdida o conversión:

* Datos de Adobe Analytics mediante el conector de origen de Analytics
* Datos de Adobe Audience Manager mediante el conector de origen del Audience Manager
* Conjunto de datos de Evento de experiencia (EE)
* Conjunto de datos de Evento de experiencia del consumidor (CEE)

Customer AI se integra con Customer Journey Analytics (CJA) en la medida en que los conjuntos de datos habilitados para Customer AI se pueden aprovechar en las vistas de datos y los informes en CJA.

## Flujo de trabajo

Algunos de los pasos se realizan en Adobe Experience Platform antes de trabajar con la salida en CJA.

### Paso 1: Descargar puntuaciones de Customer AI

La descarga de puntuaciones de Customer AI se realiza mediante una combinación de llamadas de API de Experience Platform, tal como se describe [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### Paso 2: Definición de entradas y salidas de Customer AI

Este proceso se describe en la sección [Entrada y salida en Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) documentación.

### Paso 3: Configuración de una instancia de Customer AI

Una vez que haya preparado los datos y haya establecido todas sus credenciales y esquemas, comience por seguir la [Configuración de una instancia de AI del cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guía.

### Paso 4: Configuración de una conexión CJA a conjuntos de datos de Customer AI

En CJA, ahora puede [crear una o más conexiones](/help/connections/create-connection.md) a conjuntos de datos de Experience Platform instrumentados para Customer AI. Estos conjuntos de datos aparecen con el prefijo &quot;Puntuaciones de AI del cliente&quot;, como se muestra a continuación:

![Puntuaciones de CAI](assets/cai-scores.png)

Cada predicción, como &quot;Probabilidad de actualizar cuenta&quot;, equivale a un conjunto de datos.

Este es un ejemplo de esquema XDM que CJA traería como parte de un conjunto de datos existente o nuevo:

![esquema CAI](assets/cai-schema.png)

(Tenga en cuenta que el ejemplo es un conjunto de datos de perfil; el mismo conjunto de objetos de esquema formaría parte de un conjunto de datos de Experience Event que CJA obtendría. El conjunto de datos de Evento de experiencia incluiría marcas de hora como fecha de puntuación). Todos los clientes puntuados en este modelo tendrían una puntuación, una scoreDate, etc. asociados a ellos.

### Paso 5: Crear vistas de datos en función de estas conexiones

En CJA, ahora puede continuar creando vistas de datos con las dimensiones que se incluyeron como parte de la conexión que ha establecido.