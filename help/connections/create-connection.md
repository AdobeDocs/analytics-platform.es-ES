---
title: Crear una conexión
description: Describe cómo crear una conexión a un conjunto de datos de la plataforma en Análisis del viaje del cliente.
translation-type: tm+mt
source-git-commit: 41029fb428308a247df65072af4e419a90098a15

---


# Crear una conexión

Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform en Workspace. Para informar sobre los conjuntos de datos de la plataforma, primero debe establecer una conexión entre los conjuntos de datos de la plataforma y del espacio de trabajo.

Haga clic [aquí](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para ver un vídeo de información general.

>[!IMPORTANT] Puede combinar varios conjuntos de datos de plataforma en una sola conexión.

1. Vaya a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Haga clic en **[!UICONTROL Create new connection]** en la parte superior derecha.

![Crear conexión](assets/create-connection.png)

1. El carril izquierdo muestra todos los conjuntos de datos de la plataforma desde los que puede extraer. Seleccione uno o varios conjuntos de datos que desee extraer de Análisis del viaje del cliente y haga clic en **[!UICONTROL Add]**. (Si tiene muchos conjuntos de datos para elegir, puede buscar los correctos mediante la barra de búsqueda que se encuentra encima de la lista de conjuntos de datos).

1. A continuación, por cada conjunto de datos que haya agregado a esta conexión, el análisis de viaje del cliente establece automáticamente el tipo de conjunto de datos en función de los datos que se vayan a introducir. Existen tres tipos diferentes de conjuntos de datos: Datos de Evento, datos de Perfil y datos de búsqueda.

   | Tipo de conjunto de datos | Descripción | Marca de tiempo | Esquema | ID de la persona |
   |---|---|---|---|---|
   | Evento | Datos que representan eventos en el tiempo (por ejemplo, visitas web, interacciones, transacciones, datos de PDV, datos de encuesta, datos de impresiones de publicidad, etc.). Estos son datos típicos del flujo de navegación, con un ID de cliente o una ID de cookie y una marca de tiempo. Con los datos de Evento, le permitimos utilizar cualquier ID que desee. | Se establecerá en Marca de hora. | esquema de plataforma en el que se basa este tipo de conjunto de datos. | N/A |
   | Búsqueda | Análogo a un archivo de clasificaciones. Estos datos se utilizan para buscar valores o claves encontrados en los datos de Evento o Perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a nombres de producto. | N/A | esquema de plataforma en el que se basa este tipo de conjunto de datos. | N/A |
   | Perfil | Analógico para Atributos del cliente: para atributos no temporales y no cambiantes. Datos que se aplican a sus visitantes, usuarios o clientes en los datos de Evento. Por ejemplo, le permite cargar datos de CRM sobre sus clientes. | N/A | esquema de plataforma en el que se basa este tipo de conjunto de datos. | Puede elegir qué ID de persona desea incluir. Cada conjunto de datos definido en la plataforma de Adobe Experience tiene su propio conjunto de uno o varios ID de persona definidos, como ID de cookie, ID de título, ID de usuario, código de seguimiento, etc.<br>![Persona](assets/person-id.png)**IDNote **: Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar realmente conjuntos de datos, debe utilizar el mismo ID de persona. |

1. Haga clic en **[!UICONTROL Next]**.

1. En el cuadro de diálogo Crear conexión, defina esta configuración:

   | Campo | Descripción |
   |---|---|
   | Nombre | Asigne un nombre descriptivo a la conexión. La conexión no se puede guardar sin un nombre. |
   | Descripción | Añada más detalles para distinguir esta conexión de otras. |
   | Tamaño | El tamaño colectivo de los conjuntos de datos en la conexión de datos. |
   | Conjuntos de datos | Los conjuntos de datos que se incluyen en esta conexión. |
   | Transmisión de datos | Para iniciar la transmisión de datos de esta conexión, habilite la transmisión de datos. Cuando se habilita el flujo de datos para esta conexión, se factura a la cuenta la cantidad de datos que esta conexión está transmitiendo. (Tenga en cuenta que también puede activar la transmisión de datos en el Administrador de conexiones). |

1. Haga clic en **[!UICONTROL Save]**. Al guardar esta conexión, suceden dos cosas:

   * Puede extraer todos los datos históricos de Platform para todos los conjuntos de datos que se encuentran en esta conexión.
   * Si ha habilitado el flujo continuo, establece una conexión en curso para que cualquier nuevo dato que se añada a los conjuntos de datos de esta conexión fluya automáticamente a Workspace.

El siguiente paso en el flujo de trabajo es [crear una vista](/help/data-views/create-dataview.md)de datos.
