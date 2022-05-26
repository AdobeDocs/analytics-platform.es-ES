---
description: Descubra cómo AEP Attribution AI se integra con Workspace en CJA.
title: Integración de Attribution AI con CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: 320b34ca171bb835aa3b4a9a981cc19b14060ad9
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 10%

---

# Integración de Attribution AI con CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), como parte de Adobe Experience Platform Intelligent Services, es un servicio de atribución algorítmica de varios canales que calcula la influencia y el impacto incremental de las interacciones de los clientes con los resultados especificados. Con Attribution AI, los especialistas en marketing pueden medir y optimizar el gasto en marketing y publicidad al comprender el impacto de cada interacción individual con los clientes en cada fase de los recorridos de los clientes.

Attribution AI se integra con Customer Journey Analytics (CJA) en la medida en que Attribution AI ejecuta modelos con puntos de contacto de marketing de los clientes y fuentes de datos de conversión. A continuación, CJA importa la salida de esos modelos como un conjunto de datos o se puede integrar con el resto de los conjuntos de datos de CJA. Los conjuntos de datos habilitados para Attribution AI se pueden aprovechar en las vistas de datos y los informes en CJA.

Attribution AI admite 3 esquemas de Experience Platform: Evento de experiencia, Adobe Analytics y Evento de experiencia del consumidor.

Attribution AI admite dos categorías de puntuaciones: algorítmica y basada en reglas.

## Puntuaciones algorítmicas

Las puntuaciones algorítmicas incluyen puntuaciones incrementales e influenciadas.

* **[!UICONTROL Influenciado] score** divide el 100% del crédito de conversión entre los canales de marketing.
* **[!UICONTROL Incremental] score** primero, tenga en cuenta una línea de base de conversión que habría alcanzado incluso sin marketing. Esta línea de base depende de las observaciones de IA sobre patrones, temporadas, etc., debido al reconocimiento de marca, lealtad y boca a boca existente. El crédito restante se divide entre canales de marketing.

## Puntuaciones basadas en reglas

Las puntuaciones basadas en reglas incluyen

* **[!UICONTROL Primer contacto]** da un 100 % de crédito al punto de contacto que se ve por primera vez en la ventana retrospectiva de atribución.
* **[!UICONTROL Último contacto]** otorga un 100% de crédito al punto de contacto que se produce más recientemente antes de la conversión.
* **[!UICONTROL Lineal]** da el mismo crédito a cada punto de contacto que se visualice y que conduzca a una conversión.
* **[!UICONTROL Forma de U]** da un 40 % de crédito a la primera interacción, un 40 % de crédito a la última interacción y divide el 20 % restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 50% de crédito a ambos.
* **[!UICONTROL Declive temporal]** sigue un declive exponencial con un parámetro de semivida personalizado, donde el valor predeterminado es de 7 días. El valor de cada canal depende de la cantidad de tiempo que transcurra entre el inicio del punto de contacto y la conversión final. La fórmula utilizada para determinar el crédito es `2^(-t/halflife)`, donde `t` es la cantidad de tiempo entre un punto de contacto y una conversión. A continuación, todos los puntos de contacto se normalizan al 100%.

## Flujo de trabajo

Algunos de los pasos se realizan en Adobe Experience Platform antes de trabajar con la salida en CJA. El resultado consiste en un conjunto de datos con un modelo de Attribution AI aplicado.

### Paso 1: Crear una instancia de Attribution AI

En Experience Platform, cree una instancia de Attribution AI seleccionando y asignando datos, definiendo eventos y formando los datos, como se describe [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Paso 2: Configuración de una conexión CJA en conjuntos de datos de Attribution AI

En CJA, ahora puede [crear una o más conexiones](/help/connections/create-connection.md) a conjuntos de datos de Experience Platform instrumentados para la Attribution AI. Estos conjuntos de datos aparecen con el prefijo &quot;Puntuaciones de Attribution AI&quot;, como se muestra a continuación:

![Puntuaciones AAI](assets/aai-scores.png)

### Paso 3: Crear vistas de datos en función de estas conexiones

En CJA, [crear una o más vistas de datos](/help/data-views/create-dataview.md) que contienen los campos XDM de Attribution AI.

### Paso 4: Informar sobre datos AAI en CJA Workspace

En un proyecto de CJA Workspace, puede extraer métricas como &quot;Pedidos AAI&quot; y dimensiones como &quot;Nombre de campaña AAI&quot; o &quot;Canal de marketing AAI&quot;, por ejemplo.

![Dimensiones AAI](assets/aai-dims.png)

>[!IMPORTANT]
>
>Estas dimensiones y métricas no reciben un nombre nativo de esta manera. Son &quot;nombres descriptivos&quot;. La variable [convención de nomenclatura en Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/input-output.html?lang=en#attribution-ai-output-data) sigue la ruta de esquema. Se recomienda cambiar el nombre de las rutas de esquema AAI largas por nombres cortos y más descriptivos (dimensiones/métricas) en CJA. Puede hacerlo en **[!UICONTROL Vistas de datos]** > **[!UICONTROL Editar vista de datos]** > **[!UICONTROL Componentes]** pestaña > **[!UICONTROL Campos de esquema]** -> Haga clic en un campo de esquema -> **[!UICONTROL Nombre del componente]**.


**Pedidos con puntuaciones influidas e incrementales**

Aquí vemos un proyecto de Workspace con datos de AAI que muestra pedidos con puntuaciones influenciadas e incrementales. Desglose hasta cualquier dimensión para comprender la atribución mediante: campaña, grupo de productos, segmento de usuario, ubicación geográfica, etc.

![Proyecto AAI](assets/aai-project.png)

![Proyecto AAI](assets/aai-project2.png)

**Rendimiento de marketing**

Compare y contraste la atribución de puntos de contacto entre diferentes modelos de atribución:

![Comparar](assets/compare.png)

**Interacción con el canal**

Comprenda la interacción del canal para ver qué canal se puede utilizar de manera más eficaz con otros canales, utilizando un diagrama de Venn:

![Superposición de canal de marketing](assets/mc-overlap.png)

**Rutas principales de conversión**

Esta tabla muestra las rutas principales a la conversión (desduplicadas) para ayudarle a diseñar y optimizar los puntos de contacto:

![Canales principales](assets/top-channels.png)

**Tiempo de espera para la conversión**

Aquí, vemos el tiempo de espera para la conversión cuando un punto de contacto está en la mezcla. Ayuda a optimizar el tiempo de espera:

![Tiempo de espera](assets/lead-time.png)

## Diferencias entre Attribution AI y Attribution IQ

Entonces, ¿cuándo se deben usar los datos de Attribution AI en lugar de [Attribution IQ](/help/analysis-workspace/attribution/overview.md), ¿una capacidad nativa de CJA? Esta tabla muestra algunas de las diferencias en la funcionalidad:

| Funcionalidad | Attribution AI | Attribution IQ |
| --- | --- | --- |
| ¿La atribución incremental? | Sí | No |
| Permite a los usuarios ajustar el modelo | Sí | Sí |
| Hace atribución entre canales (Nota: AAI no utiliza los mismos datos enlazados que CJA). | Sí | Sí |
| Incluye puntuaciones influidas | Sí | Sí |
| ¿Modelado ML | Sí | Sí |
| Modelos de atribución basados en regiones | Sí | Sí |
| Puede configurar puntos de contacto de marketing en el modelo | Sí | No |

{style=&quot;table-layout:auto&quot;}
