---
title: Crear una conexión
description: Describe cómo crear una conexión a un conjunto de datos de la plataforma en Análisis del viaje del cliente.
translation-type: tm+mt
source-git-commit: 674835d9c8b79850051729c875bc67f0e4052a66
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Crear una conexión

Una conexión le permite integrar conjuntos de datos desde [!DNL Adobe Experience Platform] en [!UICONTROL Workspace]. Para informar sobre [!DNL Experience Platform] conjuntos de datos, primero debe establecer una conexión entre los conjuntos de datos en [!DNL Experience Platform] y [!UICONTROL Workspace].

Haga clic [aquí](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para ver un vídeo de información general.

>[!IMPORTANT] Puede combinar varios [!DNL Experience Platform] conjuntos de datos en una sola conexión.

1. Go to [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Haga clic en **[!UICONTROL Crear nueva conexión]** en la parte superior derecha.

   ![Crear conexión](assets/create-connection.png)

1. En primer lugar, elija un simulador para pruebas en la plataforma de experiencias que contenga los conjuntos de datos con los que desee crear una conexión. Adobe Experience Platform proporciona [entornos limitados](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) que dividen una instancia de plataforma única en entornos virtuales independientes para ayudar a desarrollar y desarrollar aplicaciones de experiencia digital. Puede considerar los entornos limitados como &quot;silos de datos&quot; que contienen conjuntos de datos. Los Simuladores para pruebas se utilizan para controlar el acceso a los conjuntos de datos. No se puede acceder a los datos de los entornos limitados.

1. Una vez seleccionado el simulador para pruebas, el carril izquierdo muestra todos los conjuntos de datos de ese simulador para pruebas desde los que puede extraer. Seleccione uno o varios conjuntos de datos que desee extraer de [!UICONTROL Customer Journey Analytics] y haga clic en **[!UICONTROL Añadir]**. (Si tiene muchos conjuntos de datos para elegir, puede buscar los correctos mediante la barra de búsqueda que se encuentra encima de la lista de conjuntos de datos).

1. A continuación, por cada conjunto de datos que haya agregado a esta conexión, [!UICONTROL Customer Journey Analytics] establece automáticamente el tipo de conjunto de datos en función de los datos que se vayan a introducir. Existen tres tipos diferentes de conjuntos de datos: [!UICONTROL Datos de Evento] , datos de [!UICONTROL Perfil] y datos de [!UICONTROL búsqueda] .

   | Tipo de conjunto de datos | Descripción | Marca de tiempo | Esquema | ID de la persona |
   |---|---|---|---|---|
   | [!UICONTROL Evento] | Datos que representan eventos en el tiempo (por ejemplo, visitas web, interacciones, transacciones, datos de PDV, datos de encuesta, datos de impresiones de publicidad, etc.). Por ejemplo, estos datos podrían ser datos típicos del flujo de navegación, con un ID de cliente o una ID de cookie y una marca de tiempo. Con los datos de Evento, tiene flexibilidad para saber qué ID se utiliza como ID de persona. | Se establece automáticamente en el campo de marca de hora predeterminado de esquemas basados en evento en la plataforma [de experiencias]UICONTROL. | Cualquier esquema integrado o personalizado basado en una clase XDM con el comportamiento &quot;Serie temporal&quot;. Algunos ejemplos son &quot;Evento de experiencias XDM&quot; o &quot;Evento de decisiones XDM&quot;. | Puede elegir qué ID de persona desea incluir. Cada esquema de conjunto de datos definido en la plataforma de experiencias puede tener su propio conjunto de una o más identidades definidas y asociadas con una Área de nombres de identidad. Cualquiera de ellos puede utilizarse como ID de persona. Algunos ejemplos son: ID de cookie, ID con título, ID de usuario, código de seguimiento, etc. |
   | [!UICONTROL Búsqueda] | Análogo a un archivo de clasificaciones. Estos datos se utilizan para buscar valores o claves encontrados en los datos de Evento o Perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a nombres de producto. | N/A | Cualquier esquema integrado o personalizado basado en una clase XDM con el comportamiento &quot;Record&quot;, excepto la clase &quot;XDM Individual Perfil&quot;. | N/A |
   | [!UICONTROL Perfil] | Analógico para Atributos  del cliente: para atributos no temporales y no cambiantes. Datos que se aplican a sus visitantes, usuarios o clientes en los datos de [!UICONTROL Evento] . Por ejemplo, le permite cargar datos de CRM sobre sus clientes. | N/A | Cualquier esquema integrado o personalizado basado en la clase &quot;XDM Individual Perfil&quot;. | Puede elegir qué ID de persona desea incluir. Cada conjunto de datos definido en el [!DNL Experience Platform] tiene su propio conjunto de uno o más ID de persona definidos, como ID de cookie, ID de título, ID de usuario, código de seguimiento, etc.<br>![Persona](assets/person-id.png)**IDNote **: Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar realmente conjuntos de datos, necesita usar el mismo ID de persona. |

1. Al hacer clic en **[!UICONTROL Siguiente]** , se abre el cuadro de diálogo [!UICONTROL Crear conexión] .

   ![Crear conexión](assets/create-connection2.png)

1. En el cuadro de diálogo [!UICONTROL Crear conexión] , defina esta configuración:

   | Campo | Descripción |
   |---|---|
   | [!UICONTROL Nombre de la conexión] | Asigne un nombre descriptivo a la conexión. La conexión no se puede guardar sin un nombre. |
   | [!UICONTROL Descripción] | Añada más detalles para distinguir esta conexión de otras. |
   | [!UICONTROL Conjuntos de datos] | Los conjuntos de datos que se incluyen en esta conexión. |
   | [!UICONTROL Importe automáticamente todos los conjuntos de datos nuevos en esta conexión, a partir de hoy.] | Seleccione esta opción si desea establecer una conexión continua, de modo que los lotes de datos nuevos que se agreguen a los conjuntos de datos de esta conexión fluyan automáticamente a [!UICONTROL Workspace]. |
   | [!UICONTROL Importar todos los datos existentes] | Al seleccionar esta opción y guardar la conexión, se importarán todos los datos (históricos) existentes de [!DNL Experience Platform] todos los conjuntos de datos de esta conexión. En el futuro, todos los datos históricos existentes para cualquier conjunto de datos nuevo agregado a esta conexión guardada también se importarán automáticamente. <br>**Tenga en cuenta que, una vez guardada esta conexión, esta configuración no se puede cambiar.** |

   **Tenga en cuenta que:**

   * Si el tamaño acumulado de los datos históricos para todos los conjuntos de datos de la conexión supera las 1.500 millones de filas, un mensaje de error indicará que no puede importar esta cantidad de datos históricos. Sin embargo, si se agregara un conjunto de datos con mil millones de filas de datos históricos, se importaran esos datos y una semana después se agregara otro conjunto de datos del mismo tamaño e se importaran sus datos históricos, esto funcionaría.
   * Priorizamos los nuevos datos agregados a un conjunto de datos en la conexión, por lo que estos datos tienen la latencia más baja.
   * Cualquier dato de relleno (histórico) se importa a una velocidad más lenta.

1. Haga clic en **[!UICONTROL Guardar]**.

El siguiente paso en el flujo de trabajo es [crear una vista](/help/data-views/create-dataview.md)de datos.
