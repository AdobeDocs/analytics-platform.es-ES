---
description: Descubra cómo AEP Attribution AI se integra con Workspace en CJA.
title: Integración de Attribution AI con CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: acfa4086c525ed78b52e430c110ec1daca9d20a5
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 2%

---

# Integración de Attribution AI con CJA

>[!NOTE]
>
>Esta funcionalidad se lanzará el 25 de mayo de 2022.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), como parte de Adobe Experience Platform Intelligent Services, es un servicio de atribución algorítmica de varios canales que calcula la influencia y el impacto incremental de las interacciones de los clientes con los resultados especificados. Con Attribution AI, los especialistas en marketing pueden medir y optimizar el gasto en marketing y publicidad al comprender el impacto de cada interacción individual con los clientes en cada fase de los recorridos de los clientes.

Attribution AI admite dos categorías de puntuaciones: algorítmica y basada en reglas. Las puntuaciones algorítmicas incluyen puntuaciones incrementales e influenciadas.

* **Puntuaciones influidas** divide el 100% del crédito de conversión entre los canales de marketing.
* **Puntuaciones incrementales** primero, tenga en cuenta una línea de base de conversión que habría alcanzado incluso sin marketing. Esta línea de base depende de las observaciones de IA sobre patrones, temporadas, etc., debido al reconocimiento de marca, lealtad y boca a boca existente. El crédito restante se divide entre canales de marketing.

Las puntuaciones basadas en reglas incluyen [!UICONTROL Primer contacto], [!UICONTROL Último contacto], [!UICONTROL Lineal], [!UICONTROL Forma de U]y [!UICONTROL Declive temporal]. Attribution AI admite 3 esquemas de Experience Platform: Evento de experiencia, Adobe Analytics y Evento de experiencia del consumidor.

Attribution AI se integra con Customer Journey Analytics (CJA) en la medida en que Attribution AI ejecuta modelos con datos y luego CJA importa la salida de esos modelos como un conjunto de datos, que luego se puede integrar con el resto de sus conjuntos de datos CJA. Los conjuntos de datos habilitados para Attribution AI se pueden aprovechar en las vistas de datos y los informes en CJA.

## Flujo de trabajo

Algunos de los pasos se realizan en Adobe Experience Platform antes de trabajar con la salida en CJA. El resultado consiste en un conjunto de datos con un modelo de Attribution AI aplicado.

### Paso 1: Crear una instancia de Attribution AI

En Experience Platform, cree una instancia de Attribution AI seleccionando y asignando datos, definiendo eventos y formando los datos, como se describe [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Paso 2: Configuración de una conexión CJA en conjuntos de datos de Attribution AI

En CJA, ahora puede [crear una o más conexiones](/help/connections/create-connection.md) a conjuntos de datos de Experience Platform instrumentados para la Attribution AI. Estos conjuntos de datos aparecen con el prefijo &quot;Puntuaciones de Attribution AI&quot;, como se muestra a continuación:

![Puntuaciones AAI](assets/aai-scores.png)

### Paso 3: Crear vistas de datos en función de estas conexiones

En CJA, [crear una o más vistas de datos](/help/data-views/create-dataview.md) que contienen los campos XDM de Attribution AI. (Sería bueno tener una captura de pantalla aquí.)

### Paso 4: Informar sobre datos AAI en CJA Workspace

En un proyecto de CJA Workspace, puede extraer métricas como &quot;Pedidos AAI&quot; y dimensiones como &quot;Nombre de campaña AAI&quot; o &quot;Canal de marketing AAI&quot;, por ejemplo.

![Dimensiones AAI](assets/aai-dims.png)

Aquí vemos un proyecto de Workspace con datos de AAI que muestra pedidos con puntuaciones influenciadas e incrementales. Desglose hasta cualquier dimensión para comprender la atribución mediante: campaña, grupo de productos, segmento de usuario, ubicación geográfica, etc.

![Proyecto AAI](assets/aai-project.png)

![Proyecto AAI](assets/aai-project2.png)

Comprenda la interacción del canal para ver qué canal se puede utilizar de forma más eficaz con otros canales:

![Superposición de canal de marketing](assets/mc-overlap.png)

Esta tabla muestra las rutas principales a la conversión (desduplicadas) para ayudarle a diseñar y optimizar los puntos de contacto:

![Canales principales](assets/top-channels.png)

Aquí, vemos el tiempo de espera para la conversión cuando un punto de contacto está en la mezcla. Ayuda a optimizar el tiempo de espera:

![Tiempo de espera](assets/lead-time.png)

## Nuevas métricas de CJA

| Métrica | Descripción |
| --- | --- |
| [!UICONTROL Tasa de adquisición] | Para cada canal, entre las rutas de conversión que tocó, el porcentaje del canal es el Inicio. |
| [!UICONTROL Tasa de reproductor] | Para cada canal, entre las rutas de conversión que tocó, el porcentaje del canal es un reproductor. |
| [!UICONTROL Tasa de cierre] | Para cada canal, entre las rutas de conversión que tocó, el porcentaje del canal es el más cercano. |
| [!UICONTROL AAI AVG Days Away from Order] | Para cada canal, el número promedio de días desde el pedido. |
| [!UICONTROL AAI AVG Total Days in Sales Process] | Para cada canal, el promedio de días totales de las rutas de conversión que tocó. |
| [!UICONTROL AVG se aleja del orden] | Para cada canal, el promedio se aleja del orden. |

## Diferencias entre Attribution AI y Attribution IQ

Entonces, ¿cuándo se deben usar los datos de Attribution AI en lugar de [Attribution IQ](/help/analysis-workspace/attribution/overview.md), ¿una capacidad nativa de CJA? Esta tabla muestra algunas de las diferencias en la funcionalidad:

| Funcionalidad | Attribution AI | Attribution IQ |
| --- | --- | --- |
| ¿Atribución fraccionada? | Sí | No |
| Permite a los usuarios ajustar el modelo | Sí | Sí |
| Hace atribución entre canales (Nota: AAI no utiliza los mismos datos enlazados que CJA). | Sí | Sí |
| Incluye puntuaciones incrementales e influidas | Sí | No |
| ¿Modelado ML | Sí | Sí |
| ¿Modelado ML con predicciones? | Sí | No |

{style=&quot;table-layout:auto&quot;}
