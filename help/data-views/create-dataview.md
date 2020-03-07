---
title: Creación de una vista de datos
description: Describe cómo crear una vista de datos en un conjunto de datos de plataforma en el análisis de viajes del cliente (CJA).
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# Creación de una vista de datos

Una vista de datos es similar a un grupo de informes virtuales en Analytics, en el sentido de que es una vista &quot;filtrada&quot; de los datos. Puede crear diferentes vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos. Por ejemplo, puede tener una vista de datos en la que todas las dimensiones estén configuradas como &quot;Último toque&quot; y, simultáneamente, otra vista de datos (basada en el mismo conjunto de datos) con todas las dimensiones definidas como &quot;Primer toque&quot;.

Los proyectos de espacio de trabajo en Análisis de viajes del cliente se basan en vistas de datos.

Haga clic [aquí](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) para ver un vídeo de información general.

## Requisitos previos

Para poder crear vistas de datos, debe [configurar una o varias conexiones a conjuntos de datos](/help/connections/create-connection.md)de la plataforma Adobe Experience.

## Ajustar configuración

1. En Análisis del viaje del cliente, vaya a la **[!UICONTROL Data Views]** ficha.

1. Haga clic en **[!UICONTROL Add]** para agregar una vista de datos y configurar su configuración.

   | Configuración de sesión | Definición |
   |---|---|
   | Conexión | Este campo vincula la vista de datos con la conexión que estableció anteriormente, que contiene los conjuntos de datos de la plataforma. |
   | Nombre | Es obligatorio asignar un nombre a la vista de datos. |
   | Descripción | Una descripción detallada no es obligatoria, pero se recomienda. |
   | Agregar etiquetas | Las etiquetas permiten organizar las vistas de datos en categorías. |
   | Zona horaria | Elija el huso horario de la vista de datos. |
   | Tiempo de espera de la sesión | Seleccione la definición de una &quot;sesión&quot;. La configuración de tiempo de espera de sesión define la cantidad de inactividad que debe tener un visitante único antes de que se inicie automáticamente una nueva sesión. El valor predeterminado es de 30 minutos. For example, if you set the session timeout to 45 minutes, a new session grouping is created for each sequence of hits collected, separated by 45 minutes of inactivity. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Iniciar nueva sesión con evento | Una nueva sesión se inicia cuando se activa un evento, independientemente de si se ha superado o no el tiempo de espera de la sesión. La sesión recién creada incluye el evento que la ha iniciado. Además, es posible utilizar varios eventos para iniciar una sesión, y se activa una nueva si se observa en los datos cualquiera de esos eventos. Esta configuración afectará al recuento de visitas, al contenedor de segmentos Sesión (antes Visita) y a la lógica de caducidad de visitas en las dimensiones. |
   | Añadir filtros | &quot;Filtros&quot; es el término para &quot;segmentos&quot; en el análisis de viajes del cliente. Si desea filtrar los datos, arrastre el filtro adecuado aquí desde el carril izquierdo. Si no selecciona ningún filtro, la vista de datos contendrá todos los datos. |

1. Haga clic en **[!UICONTROL Continue]**.

## Añadir componentes

1. Ahora es el momento de agregar componentes (dimensiones, métricas) a la vista de datos (similar a la experiencia de depuración en los grupos de informes virtuales). Observe que cada uno de los campos de los conjuntos de datos ahora se traducen en dimensiones o métricas. Arrastre dimensiones y métricas al panel o **[!UICONTROL Seleccionar todo** para agregar todos los componentes.

   ![](assets/add-all-components.png)

1. Haga clic en la **[!UICONTROL Add Components]** ficha para agregar dimensiones y métricas a la vista de datos.

   ![](assets/add-all-components2.png)

1. (Opcional) Puede cambiar el nombre de un componente por un nombre descriptivo o cambiar su configuración de atribución seleccionándolo y editando su configuración. Tenga en cuenta que se conserva el nombre subyacente. Para obtener más información, consulte [Configurar vistas de datos y atribución](/help/data-views/configure-dataviews.md).

1. Los siguientes pasos son para [especificar la configuración](/help/data-views/configure-dataviews.md)de componente y atribución.