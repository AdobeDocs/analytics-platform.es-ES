---
title: Crear una conexión
description: Describe cómo crear una conexión para un conjunto de datos de Platform en Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 2bbfe2296d658dd38464a4a9d7810ae6d6eda306
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 45%

---


# Crear una conexión

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

Haga clic [aquí](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para ver un vídeo de información general.

>[!IMPORTANT]
>
>Puede combinar varios conjuntos de datos de [!DNL Experience Platform] en una sola conexión.

1. Acceda a [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Haga clic en **[!UICONTROL Crear nueva conexión]** en la parte superior derecha.

   ![Crear conexión](assets/create-connection0.png)

1. Elija un simulador para pruebas en el Experience Platform que contenga los conjuntos de datos a los que desea crear una conexión.

   Adobe Experience Platform proporciona [entornos](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) limitados que dividen una sola instancia de Platform en entornos virtuales independientes para ayudar a desarrollar y desarrollar aplicaciones de experiencia digital. Puede considerar los entornos limitados como &quot;silos de datos&quot; que contienen conjuntos de datos. Los Simuladores para pruebas se utilizan para controlar el acceso a los conjuntos de datos. No se puede acceder a los datos de los entornos limitados. Una vez seleccionado el simulador para pruebas, el carril izquierdo muestra todos los conjuntos de datos de ese simulador para pruebas desde los que puede extraer.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (If you have a lot of datasets to choose from, you can search for the right one(s) using the **[!UICONTROL Search datasets]** search bar above the list of datasets.)

## Configurar el conjunto de datos

En el lado derecho, ahora puede configurar el conjunto de datos que ha agregado.

![Configurar el conjunto de datos](assets/create-connection.png)

1. **[!UICONTROL Tipo]** de conjunto de datos: Para cada conjunto de datos que agregó a esta conexión, el [!UICONTROL Customer Journey Analytics] establece automáticamente el tipo de conjunto de datos en función de los datos que ingresan.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | Tipo de conjunto de datos | Descripción | Marca de tiempo | Esquema | ID de la persona |
   |---|---|---|---|---|
   | [!UICONTROL Evento] | Datos que representan eventos en el tiempo (p. ej., visitas web, interacciones, transacciones, datos de TPV, datos de encuesta, datos de impresión de publicidad, etc.). Por ejemplo, estos datos podrían ser datos típicos del flujo de navegación, con un ID de cliente o un ID de cookie y una marca de tiempo. Con los datos de evento, tiene flexibilidad para saber qué ID se utiliza como ID de persona. | Se establece automáticamente en el campo de marca de tiempo predeterminado a partir de los esquemas basados en eventos en [UICONTROL Experience Platform]. | Cualquier esquema integrado o personalizado basado en una clase XDM con el comportamiento &quot;Serie temporal&quot;. Algunos ejemplos son &quot;Evento de experiencias XDM&quot; o &quot;Evento de decisiones XDM&quot;. | Puede elegir qué ID de persona desea incluir. Cada esquema del conjunto de datos definido en Experience Platform puede tener su propio conjunto de una o más identidades definidas y asociadas a un área de nombres de identidad. Cualquiera de ellos puede utilizarse como ID de persona. Algunos ejemplos son: ID de cookie, ID con título, ID de usuario, código de seguimiento, etc. |
   | [!UICONTROL Búsqueda] | Análogo a un archivo de clasificaciones. Estos datos se utilizan para buscar valores o claves encontrados en los datos de Evento o de Perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento para los nombres de producto. | N/A | Cualquier esquema integrado o personalizado basado en una clase XDM con el comportamiento &quot;Record&quot;, excepto la clase &quot;XDM Individual Profile&quot;. | N/A |
   | [!UICONTROL Perfil] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. Por ejemplo, le permite cargar datos de CRM sobre sus clientes. | N/A | Cualquier esquema integrado o personalizado basado en la clase &quot;XDM Individual Perfil&quot;. | Puede elegir qué ID de persona desea incluir. Cada conjunto de datos definido en [!DNL Experience Platform] tiene su propio conjunto de uno o más ID de persona definidos, como ID de cookie, ID de título, ID de usuario, código de seguimiento, etc.<br>![ID de persona](assets/person-id.png)**Nota:** Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar conjuntos de datos correctamente, necesita usar el mismo ID de persona. |

1. **[!UICONTROL ID]** de conjunto de datos: Este ID se genera automáticamente.

1. **[!UICONTROL Marca]** de hora: agregar contenido aquí

1. **[!UICONTROL Esquema]**: Este es el [esquema](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/schema/composition.html) en función del cual se creó el conjunto de datos en Adobe Experience Platform.

1. **[!UICONTROL ID]** de persona: Seleccione un ID de persona en la lista desplegable de identidades disponibles. Estas identidades se definieron en el esquema del conjunto de datos en el Experience Platform. Consulte a continuación para obtener información sobre cómo utilizar el mapa de identidad como ID de persona.

   >[!IMPORTANT]
   >
   >Si no hay ID de persona para elegir, significa que uno o más ID de persona no se han definido en el esquema. Vista [este vídeo](https://youtu.be/G_ttmGl_LRU) sobre cómo definir una identidad en Experience Platform.

1. Haga clic en **[!UICONTROL Siguiente]** para ir al cuadro de diálogo [!UICONTROL Activar conexión] .

### Usar el mapa de identidad como ID de persona

Customer Journey Analytics ahora admite la capacidad de usar el mapa de identidad para su ID de persona. Mapa de identidad es una estructura de datos de mapa que permite a alguien cargar pares de clave -> valor. Las claves son Áreas de nombres de identidad y el valor es una estructura que contiene el valor de identidad. El mapa de identidad existe en cada fila o evento cargado y se completa para cada fila en consecuencia.

El mapa de identidad está disponible para cualquier conjunto de datos que utilice un esquema basado en la clase XDM de ExperienceEvent. Al seleccionar un conjunto de datos para incluirlo en una conexión CJA, tiene la opción de seleccionar un campo como ID principal o el mapa de identidad:

![](assets/idmap1.png)

Si selecciona Mapa de identidad, obtendrá dos opciones de configuración adicionales:

| Opción | Descripción |
|---|---|
| [!UICONTROL Usar área de nombres de ID primario] | Esto indica a CJA, por fila, que busque la identidad en el mapa de identidad que está marcado con un atributo primario=true y que la utilice como ID de persona para esa fila. Esto significa que esta es la clave principal que se utilizará en el Experience Platform para la partición. También es el candidato principal para el uso como ID de visitante de CJA (según la configuración del conjunto de datos en una conexión CJA). |
| [!UICONTROL Área de nombres] | (Esta opción solo está disponible si no utiliza la Área de nombres de ID principal). Las Áreas de nombres de identidad son un componente del servicio [de identidad de](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) Adobe Experience Platform que sirve de indicadores del contexto al que se relaciona la identidad. Si especifica una Área de nombres, CJA buscará en el mapa de identidad de cada fila esta clave de Área de nombres y utilizará la identidad bajo esa Área de nombres como ID de persona para esa fila. Tenga en cuenta que, como CJA no puede realizar una exploración completa de todos los conjuntos de datos de todas las filas para determinar qué Áreas de nombres están realmente presentes, en la lista desplegable se enumeran todas las Áreas de nombres posibles. Debe saber qué Áreas de nombres se especifican en los datos; no se puede detectar automáticamente. |

## Habilitar conexión

![Habilitar conexión](assets/create-connection2.png)

1. Para habilitar una conexión, defina esta configuración:

   | Opción | Descripción |
   |---|---|
   | [!UICONTROL Asignar nombre a una conexión] | Asigne un nombre descriptivo a la conexión. La conexión no se puede guardar sin un nombre. |
   | [!UICONTROL Descripción] | Añada más detalles para distinguir esta conexión de otras. |
   | [!UICONTROL Conjuntos de datos] | Los conjuntos de datos que se incluyen en esta conexión. |
   | [!UICONTROL Importe automáticamente todos los conjuntos de datos nuevos en esta conexión, a partir de hoy.] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL Importar los datos existentes] | Al seleccionar esta opción y al guardar la conexión, se importarán todos los datos (históricos) existentes de [!DNL Experience Platform] de todos los conjuntos de datos de esta conexión. En el futuro, todos los datos históricos existentes para cualquier conjunto de datos nuevo agregado a esta conexión guardada también se importarán de manera automática. <br>**Tenga en cuenta que, una vez guardada esta conexión, la configuración no se puede modificar.** |

   **Tenga en cuenta que:**

   * Si el tamaño acumulado de los datos históricos para todos los conjuntos de datos de la conexión supera las 1500 millones de filas, un mensaje de error indicará que no puede importar esta cantidad de datos históricos. Sin embargo, si agregara un conjunto de datos con mil millones de filas de datos históricos, importara esos datos y, una semana después, agregara otro conjunto de datos del mismo tamaño y se importaran sus datos históricos, esto funcionaría.
   * Priorizamos los nuevos datos agregados a un conjunto de datos en la conexión, por lo que estos datos tienen la latencia más baja.
   * Cualquier dato de relleno (datos históricos) se importa a una velocidad más lenta.

1. Haga clic en **[!UICONTROL Guardar]**.

El paso siguiente en el flujo de trabajo es [crear una vista de datos](/help/data-views/create-dataview.md).
