---
title: Crear una conexión
description: Describe cómo crear una conexión a un conjunto de datos de la plataforma en Análisis del viaje del cliente.
translation-type: tm+mt
source-git-commit: 7fdda3a4171400ba018fe31b492737553c575998

---


# Crear una conexión

Una conexión permite integrar conjuntos de datos desde [!DNL Adobe Experience Platform] a [!UICONTROL Workspace]. Para informar sobre [!DNL Experience Platform] conjuntos de datos, primero debe establecer una conexión entre conjuntos de datos en [!DNL Experience Platform] y [!UICONTROL Workspace].

Haga clic [aquí](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para ver un vídeo de información general.

>[!IMPORTANT] Puede combinar varios [!DNL Experience Platform] conjuntos de datos en una sola conexión.

1. Vaya a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Haga clic en **[!UICONTROL Create new connection]** en la parte superior derecha.

![Crear conexión](assets/create-connection.png)

1. El carril izquierdo muestra todos los conjuntos de datos de los [!DNL Experience Platform] que puede extraer. Seleccione uno o varios conjuntos de datos en los que desee extraer [!UICONTROL Customer Journey Analytics] y haga clic en **[!UICONTROL Add]**. (Si tiene muchos conjuntos de datos para elegir, puede buscar los correctos mediante la barra de búsqueda que se encuentra encima de la lista de conjuntos de datos).

1. A continuación, para cada conjunto de datos que agregó a esta conexión, establece automáticamente el tipo de conjunto de datos en función de los datos que ingresan. [!UICONTROL Customer Journey Analytics] Existen tres tipos diferentes de conjuntos de datos: [!UICONTROL Event] datos, [!UICONTROL Profile] datos y [!UICONTROL Lookup] datos.

   | Tipo de conjunto de datos | Descripción | Marca de tiempo | Esquema | ID de la persona |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Datos que representan eventos en el tiempo (por ejemplo, visitas web, interacciones, transacciones, datos de PDV, datos de encuesta, datos de impresiones de publicidad, etc.). Estos son datos típicos del flujo de navegación, con un ID de cliente o una ID de cookie y una marca de tiempo. Con los datos de Evento, le permitimos utilizar cualquier ID que desee. | Se establecerá en Marca de hora. | El [!DNL Experience Platform] esquema en el que se basa este tipo de conjunto de datos. | N/A |
   | [!UICONTROL Lookup] | Análogo a un archivo de clasificaciones. Estos datos se utilizan para buscar valores o claves encontrados en los datos de Evento o Perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a nombres de producto. | N/A | El [!DNL Experience Platform] esquema en el que se basa este tipo de conjunto de datos. | N/A |
   | [!UICONTROL Profile] | Analógico [!UICONTROL Customer Attributes] : para atributos no cambiantes y no temporales. Datos que se aplican a sus visitantes, usuarios o clientes en los [!UICONTROL Event] datos. Por ejemplo, le permite cargar datos de CRM sobre sus clientes. | N/A | El [!DNL Experience Platform] esquema en el que se basa este tipo de conjunto de datos. | Puede elegir qué ID de persona desea incluir. Cada conjunto de datos definido en el [!DNL Experience Platform] tiene su propio conjunto de uno o más ID de persona definidos, como ID de cookie, ID de título, ID de usuario, código de seguimiento, etc.<br>![Persona](assets/person-id.png)**IDNote **: Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar realmente conjuntos de datos, debe utilizar el mismo ID de persona. |

1. Al hacer clic **[!UICONTROL Next]** se abre el cuadro de [!UICONTROL Create Connection] diálogo.

   ![Crear conexión](assets/create-connection2.png)

1. En el [!UICONTROL Create Connection] cuadro de diálogo, defina esta configuración:

   | Campo | Descripción |
   |---|---|
   | [!UICONTROL Name Connection] | Asigne un nombre descriptivo a la conexión. La conexión no se puede guardar sin un nombre. |
   | [!UICONTROL Description] | Añada más detalles para distinguir esta conexión de otras. |
   | [!UICONTROL Datasets] | Los conjuntos de datos que se incluyen en esta conexión. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Seleccione esta opción si desea establecer una conexión continua, de modo que los lotes de datos nuevos que se agreguen a los conjuntos de datos de esta conexión fluyan automáticamente a [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | Al seleccionar esta opción y guardar la conexión, se importarán todos los datos (históricos) existentes de [!DNL Experience Platform] todos los conjuntos de datos de esta conexión. En el futuro, todos los datos históricos existentes para cualquier conjunto de datos nuevo agregado a esta conexión guardada también se importarán automáticamente. <br>**Tenga en cuenta que, una vez guardada esta conexión, esta configuración no se puede cambiar.** |

   **Tenga en cuenta que:**

   * Si el tamaño acumulado de los datos históricos para todos los conjuntos de datos de la conexión supera las 1.500 millones de filas, un mensaje de error indicará que no puede importar esta cantidad de datos históricos. Sin embargo, si se agregara un conjunto de datos con mil millones de filas de datos históricos, se importaran esos datos y una semana después se agregara otro conjunto de datos del mismo tamaño e se importaran sus datos históricos, esto funcionaría.
   * Priorizamos los nuevos datos agregados a un conjunto de datos en la conexión, por lo que estos datos tienen la latencia más baja.
   * Cualquier dato de relleno (histórico) se importa a una velocidad más lenta.

1. Haga clic en **[!UICONTROL Save]**.

El siguiente paso en el flujo de trabajo es [crear una vista](/help/data-views/create-dataview.md)de datos.
