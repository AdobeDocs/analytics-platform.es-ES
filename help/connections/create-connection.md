---
title: Crear o editar una conexión
description: Describe cómo crear o editar una conexión para un conjunto de datos de Experience Platform en Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '3507'
ht-degree: 97%

---

# Crear o editar una conexión {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="Registros añadidos"
>abstract="El número de registros (filas) agregados a una Conexión durante el intervalo de tiempo seleccionado para los conjuntos de datos seleccionados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="Registros omitidos"
>abstract="El número de registros (filas) omitidos durante la transferencia de datos para una Conexión durante el intervalo de tiempo seleccionado para los conjuntos de datos seleccionados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="Registros eliminados"
>abstract="El número de registros (filas) eliminados de una conexión durante el intervalo de tiempo seleccionado para los conjuntos de datos seleccionados"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="Última incorporación"
>abstract="La marca de tiempo del último lote de cualquier conjunto de datos se ha transferido a una conexión."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="Habilitar la ventana de datos acumulados"
>abstract="Defina la retención de datos como una ventana móvil en meses con respecto a la conexión."

<!-- markdownlint-enable MD034 -->


La experiencia de flujo de trabajo de creación y edición de conexiones reúne todos los ajustes de configuración del conjunto de datos y la conexión al centro de la pantalla con un flujo de trabajo de asistencia. Proporciona una experiencia detallada de selección, configuración y revisión de conjuntos de datos. Y permite especificar información crítica como el tipo de conjunto de datos, el tamaño, el esquema, el identificador del conjunto de datos, el estado del lote, el estado de relleno, los ID de persona y mucho más para reducir el riesgo de configurar incorrectamente la conexión. A continuación se muestra una descripción general de las funciones:

* Puede habilitar un período de retención de datos móvil al crear la conexión.
* Puede agregar y eliminar conjuntos de datos de una conexión. (Al eliminar un conjunto de datos, éste se elimina de la conexión y afecta a las vistas de datos asociadas y a los proyectos de Analysis Workspace subyacentes).
* Puede habilitar y solicitar datos de relleno por conjunto de datos.
* Puede editar conjuntos de datos, por ejemplo, para solicitar otro relleno.
* Puede importar los datos existentes por conjunto de datos.

+++ Vídeo para ilustrar la creación y edición de una experiencia de conexión

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

+++

## Requisitos previos

El número máximo de conjuntos de datos que se pueden añadir a una conexión es de 100. La combinación depende del paquete de Customer Journey Analytics que haya adquirido su compañía.

Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

| Paquete **Seleccionar** | Paquete de **Foundation** |
| --- | --- |
| Cualquier combinación de conjuntos de datos de evento/perfil/consulta/resumen que sumen 100 | Un conjunto de datos de evento por conexión |
|  | Hasta 99 conjuntos de datos de perfil, consulta o resumen por conexión |

{style="table-layout:auto"}

## Creación y configuración de la conexión {#create-connection}

1. En Customer Journey Analytics, seleccione la pestaña **[!UICONTROL Conexiones]**.
1. Seleccione **[!UICONTROL Crear nueva conexión]**.

   ![Configuración de conexión sin título](assets/create-conn1.png)

1. Configure los ajustes de conexión.

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Nombre de la conexión]** | Introduzca un nombre único para la conexión. |
   | **[!UICONTROL Descripción de la conexión]** | Describa el propósito de esta conexión. |
   | **[!UICONTROL Zona protegida]** | Elija una zona protegida en Experience Platform que contenga los conjuntos de datos a los que desea conectarse.<p>Adobe Experience Platform proporciona [zonas protegidas](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/home) limitadas que dividen una sola instancia de Platform en entornos virtuales independientes para ayudar a desarrollar y desarrollar aplicaciones de experiencia digital. Puede considerar las zonas protegidas como “silos de datos” que contienen conjuntos de datos. Las zonas protegidas se utilizan para controlar el acceso a los conjuntos de datos.<p>Una vez seleccionada la zona protegida, el carril izquierdo muestra todos los conjuntos de datos de la zona protegida desde los que puede extraer datos. |
   | **[!UICONTROL Activar la ventana de datos móviles]** | Si está marcada, esta casilla le permite definir la retención de datos de Customer Journey Analytics como un período de tiempo variable en meses (1 mes, 3 meses, 6 meses, etc.), a nivel de conexión.<p>La retención de datos se basa en marcas de hora de conjuntos de datos de evento y se aplica solo a conjuntos de datos de evento. No existe ninguna configuración de ventana de datos móviles para conjuntos de datos de búsqueda o perfil, ya que no hay marcas de tiempo aplicables. Sin embargo, si la conexión incluye perfiles o conjuntos de datos de búsqueda (además de uno o más conjuntos de datos de evento), esos datos se conservarán durante el mismo período de tiempo.<p> La principal ventaja es que solo almacena o genera informes sobre datos que son aplicables y útiles, y elimina los datos más antiguos que ya no son útiles. Le ayuda a mantenerse por debajo de los límites del contrato y reduce el riesgo de costes adicionales.<p>Si deja el valor predeterminado (sin marcar), la configuración de retención de datos de Adobe Experience Platform reemplaza el período de retención. Si tiene datos de 25 meses en Experience Platform, Customer Journey Analytics recibirá 25 meses de datos mediante el relleno. Si eliminase 10 de esos meses en Platform, Customer Journey Analytics conservaría los 15 meses restantes. |
   | **[!UICONTROL Agregar conjuntos de datos]** (consulte más abajo) | Agregue conjuntos de datos si no aparecen conjuntos de datos en su lista de conjuntos de datos. |
   | **[!UICONTROL Nombre del conjunto de datos]** | Seleccione uno o varios conjuntos de datos que desee incluir en Customer Journey Analytics y seleccione **[!UICONTROL Añadir]**.<p>(Si tiene muchos conjuntos de datos para elegir, puede buscar los correctos mediante la barra de búsqueda Buscar conjuntos de datos que se encuentra arriba de la lista de conjuntos de datos). |
   | **[!UICONTROL Última actualización]** | Solo para conjuntos de datos de evento, esta configuración se establece automáticamente en el campo de marca de tiempo predeterminado de esquemas basados en eventos en Experience Platform. “N/A” significa que este conjunto de datos no contiene datos. |
   | **[!UICONTROL Número de registros]** | El total de registros del mes anterior para el conjunto de datos en Experience Platform. |
   | **[!UICONTROL Esquema]** | Este es el [esquema](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/composition) en función del cual se creó el conjunto de datos en Adobe Experience Platform. |
   | **[!UICONTROL Tipo de conjunto de datos]** | Para cada conjunto de datos que agregó a esta conexión, Customer Journey Analytics establece de manera automática el tipo de conjunto de datos en función de los datos que ingresan. Existen tres tipos diferentes de conjuntos de datos: datos: datos de evento, datos de perfil y datos de búsqueda. Consulte la siguiente tabla para obtener una explicación de los tipos de conjuntos de datos. |
   | **[!UICONTROL Granularidad]** | La granularidad de los datos del conjunto de datos; solo se aplica a los conjuntos de datos de resumen. |
   | **[!UICONTROL Tipo de fuente de datos]** | El tipo de fuente de datos del conjunto de datos. No es aplicable a los conjuntos de datos de resumen. |
   | **[!UICONTROL ID de la persona]** | Seleccione un ID de persona en la lista desplegable de identidades disponibles. Estas identidades se definieron en el esquema del conjunto de datos en Experience Platform. Consulte a continuación para obtener información sobre cómo usar el mapa de identidad como ID de persona.<p>IMPORTANTE: Si no hay ningún ID de persona para elegir, significa que uno o más ID de persona no se han definido en el esquema. Mire [este vídeo](https://www.youtube.com/watch?v=G_ttmGl_LRU) sobre cómo definir una identidad en Experience Platform. |
   | **[!UICONTROL Clave]** | Solo para conjuntos de datos de búsqueda (como _id). |
   | **[!UICONTROL Clave de coincidencia]** | Solo para conjuntos de datos de búsqueda (como _id). |
   | **[!UICONTROL Importar datos nuevos]** | Establézcalo en Activado o Desactivado. |
   | **[!UICONTROL Datos de relleno]** | Puede solicitar el relleno de los datos de un conjunto de datos. Por ejemplo, puede solicitar que se rellenen los datos de los últimos 7 días. Configure el conjunto de datos correctamente y pruebe la conexión. Si todo parece correcto, puede rellenar fácilmente todos los datos restantes.<p>Además, puede habilitar la importación de nuevos datos por el conjunto de datos.  |
   | **[!UICONTROL Estado de relleno]** | Este estado indica si se están procesando datos de relleno. |

   {style="table-layout:auto"}

## Agregar y configurar conjuntos de datos {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="Clave de correspondencia"
>abstract="Seleccione un campo para unirse a uno de los conjuntos de datos de eventos. Si esta lista está vacía, probablemente no haya agregado ni configurado ningún conjunto de datos de eventos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="Importar datos nuevos"
>abstract="Los lotes nuevos que se agreguen al conjunto de datos de Experience Platform se agregarán automáticamente a esta conexión y estarán disponibles para su análisis."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="Relleno del conjunto de datos"
>abstract="Esta opción rellenará los datos (históricos) existentes de Experience Platform para este conjunto de datos en la conexión."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="Transformar conjunto de datos"
>abstract="Esta opción transformará el conjunto de datos para que pueda utilizarse para búsquedas basadas en personas en escenarios B2B. Una vez activada, la transformación del conjunto de datos es irreversible."

<!-- markdownlint-enable MD034 -->

El nuevo flujo de trabajo permite agregar un conjunto de datos de Experience Platform al crear una conexión.

1. En el cuadro de diálogo Configuración de conexión, haga clic en **[!UICONTROL Añadir conjuntos de datos]**.

1. En el paso [!UICONTROL Seleccionar conjuntos de datos], verá una lista de los conjuntos de datos de Experience Platform.

   ![Seleccionar conjuntos de datos](assets/select-datasets.png)

   Para cada conjunto de datos, la lista muestra:

   | Columna | Descripción |
   |---|---|
   | Conjunto de datos | Nombre del conjunto de datos. Seleccione el nombre para dirigirle al conjunto de datos en Experience Platform. Seleccione ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) para mostrar una ventana emergente con más detalles para el conjunto de datos. Puede seleccionar **[!UICONTROL Editar en Platform]** para editar el conjunto de datos directamente en Experience Platform. |
   | Tipo de conjunto de datos | El tipo del conjunto de datos: evento, perfil, consulta o resumen. |
   | Número de registros | El total de registros del mes anterior para el conjunto de datos en Experience Platform. |
   | Esquema | El esquema del conjunto de datos. Seleccione el nombre para dirigirle al esquema en Experience Platform. |
   | Último lote | El estado del último lote ingerido en Experience Platform. Consulte [Estados de lotes](https://experienceleague.adobe.com/es/docs/experience-platform/ingestion/batch/troubleshooting#batch-states) para ver más información. |
   | ID de conjunto de datos | El ID del conjunto de datos. |
   | Última actualización | La última marca de tiempo actualizada del conjunto de datos. |


1. Seleccione uno o varios conjuntos de datos y seleccione **[!UICONTROL Siguiente]**. Al menos un conjunto de datos de evento debe formar parte de la conexión.
   * Para cambiar las columnas mostradas para la lista de conjuntos de datos, seleccione ![Configuración de columna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) y seleccione las columnas que desea mostrar en el cuadro de diálogo [!UICONTROL Personalizar tabla].
   * Para buscar un conjunto de datos específico, utilice el campo de búsqueda ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Para alternar entre mostrar u ocultar los conjuntos de datos seleccionados, seleccione ![Seleccionar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL Ocultar seleccionados]** o **[!UICONTROL Mostrar seleccionados]**.
   * Para quitar un conjunto de datos de la lista de conjuntos de datos seleccionados, utilice ![Cerrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Para quitar todos los conjuntos de datos seleccionados, seleccione **[!UICONTROL Borrar todo]**.




1. Ahora configure los conjuntos de datos uno a uno.

   ![Configurar conjuntos de datos](assets/add-dataset.png)

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL ID de la persona]** | Solo disponible para conjuntos de datos de evento y perfil. Seleccione un ID de persona en la lista desplegable de identidades disponibles. Estas identidades se definieron en el esquema del conjunto de datos en Experience Platform. Consulte a continuación para obtener información sobre cómo usar el mapa de identidad como ID de persona.<p>Si no hay ningún ID de persona para elegir, significa que uno o más ID de persona no se han definido en el esquema. Consulte [Definición de campos de identidad en la IU](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/fields/identity) para obtener más información. <p>El valor del ID de persona seleccionado se considera que distingue entre mayúsculas y minúsculas. Por ejemplo, `abc123` y `ABC123` son dos valores diferentes. |
   | **[!UICONTROL Marca de tiempo]** | Solo para conjuntos de datos de evento y resumen, esta configuración se establece automáticamente en el campo de marca de tiempo predeterminado de esquemas basados en eventos en Experience Platform. |
   | **[!UICONTROL Clave]** | Solo disponible para conjuntos de datos de búsqueda. Clave que se utiliza para un conjunto de datos de búsqueda. |
   | **[!UICONTROL Clave de coincidencia]** | Solo disponible para conjuntos de datos de búsqueda. La clave coincidente para unirse a uno de los conjuntos de datos de evento. Si esta lista está vacía, es probable que no haya añadido ni configurado ningún conjunto de datos de evento. |
   | **[!UICONTROL Zona horaria]** | Solo disponible para datos de resumen. Seleccione la zona horaria adecuada para los datos de resumen de las series temporales. |
   | **[!UICONTROL Tipo de fuente de datos]** | Seleccione un tipo de fuente de datos. <br/>Los tipos de fuentes de datos incluyen los siguientes: <ul><li>[!UICONTROL Datos web]</li><li>[!UICONTROL Datos de aplicación móvil]</li><li>[!UICONTROL Datos POS]</li><li>[!UICONTROL Datos CRM]</li><li>[!UICONTROL Datos de las encuestas]</li><li>[!UICONTROL Datos de centro de llamadas]</li><li>[!UICONTROL Datos del producto]</li><li> [!UICONTROL Datos de cuentas]</li><li> [!UICONTROL Datos de transacción]</li><li>[!UICONTROL Datos de valoraciones del cliente]</li><li> [!UICONTROL Otro]</li></ul>Este campo se utiliza para estudiar los tipos de fuentes de datos que se utilizan. |
   | **[!UICONTROL Importar datos nuevos]** | Habilite esta opción si desea establecer una conexión continua. Con una conexión continua, los nuevos lotes de datos que se añaden a los conjuntos de datos están disponibles automáticamente en Workspace. |
   | **[!UICONTROL Relleno del conjunto de datos]** | Habilite **[!UICONTROL Relleno de todos los datos existentes]** para asegurarse de que se rellenan todos los datos existentes.<br/><br/>Seleccione **[!UICONTROL Solicitar relleno]** para rellenar los datos históricos de un período específico. Puede definir hasta 10 períodos de relleno de conjuntos de datos.<ol><li>Defina el periodo introduciendo datos de inicio y finalización o seleccionando fechas utilizando ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Seleccione **[!UICONTROL Relleno de cola]** para añadir el relleno a la lista o **[!UICONTROL Cancelar]** para cancelar.</li></ol>Para cada entrada, seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) para editar el periodo o seleccione ![Eliminar](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) para eliminar la entrada.<br/><br/>En rellenos:<ul><li>Puede rellenar cada conjunto de datos individualmente.</li><li>Prioriza los nuevos datos agregados a un conjunto de datos en la conexión, por lo que estos datos tienen la latencia más baja.</li><li>Cualquier dato de relleno (datos históricos) se importa a una velocidad más lenta. La cantidad de datos históricos influye en la latencia.</li><li>El conector de origen de Analytics importa hasta 13 meses de datos, independientemente de su tamaño, para las zonas protegidas de producción. El relleno en zonas protegidas que no sean de producción está limitado a tres meses.</li></ul> |
   | **[!UICONTROL Transformación de un conjunto de datos]** | Para conjuntos de datos de consulta B2B específicos, puede habilitar la transformación de un conjunto de datos para escenarios adecuados de creación de informes basados en personas B2B. Consulte [Transformación de conjuntos de datos para búsquedas B2B](transform-datasets-b2b-lookups.md) para obtener más información. |
   | **[!UICONTROL Estado de relleno]** | Los posibles indicadores de estado son:<ul><li>Correcto</li><li>Procesamiento de X rellenos</li><li>Off</li></ul> |
   | **[!UICONTROL ID de conjunto de datos]** | Este ID se genera automáticamente. |
   | **[!UICONTROL Descripción]** | La descripción dada a este conjunto de datos cuando se creó. |
   | **[!UICONTROL Tamaño del conjunto de datos]** | El tamaño del conjunto de datos. |
   | **[!UICONTROL Esquema]** | Este es el esquema en función del cual se creó el conjunto de datos en Adobe Experience Platform. |
   | **[!UICONTROL Conjunto de datos]** | El nombre del conjunto de datos. |
   | **[!UICONTROL Vista previa: *nombre del conjunto de datos *]** | Previsualiza el conjunto de datos con columnas de fecha, mi ID e Identificador. |
   | **[!UICONTROL Eliminar]** | Puede eliminar o quitar el conjunto de datos y cambiar el ID de persona sin eliminar toda la conexión. Eliminar o quitar reduce los costes que implica la ingesta de datos y el engorroso proceso de volver a crear toda la conexión y las vistas de datos asociadas. |

   {style="table-layout:auto"}

## Previsualización de la conexión {#preview}

Para obtener una vista previa de la conexión que ha creado, seleccione **[!UICONTROL Vista previa de conexión]** en el cuadro de diálogo Configuración de conexión.

![Previsualización de la conexión](assets/create-conn4.png)

Esta vista previa contiene algunas columnas que indican la configuración de conexión. Los tipos de columnas que se muestran dependen de los conjuntos de datos individuales.

## Tipos de conjuntos de datos {#dataset-types}

Para cada conjunto de datos que agregó a esta conexión, [!UICONTROL Customer Journey Analytics] establece de manera automática el tipo de conjunto de datos en función de los datos que ingresan.

>[!IMPORTANT]
>
>Añada al menos un conjunto de datos de evento o resumen como parte de una conexión.

Existen diferentes tipos de conjuntos de datos: datos de [!UICONTROL Evento], datos de [!UICONTROL Perfil], datos de [!UICONTROL Consulta] y datos de [!UICONTROL Resumen].

| Tipo de conjunto de datos | Descripción | Marca de tiempo | Esquema | ID de la persona |
|---|---|---|---|---|
| **[!UICONTROL Evento]** | Datos que representan eventos en el tiempo. Por ejemplo, visitas web, interacciones, transacciones, datos de TPV, datos de encuesta, datos de impresión de publicidad, etc. Estos datos podrían ser datos del flujo de navegación típicos, con un ID de cliente o un ID de cookie y una marca de tiempo. Con los datos de evento, tiene flexibilidad para saber qué ID se utiliza como ID de persona. | Se establece automáticamente en el campo de marca de tiempo predeterminado a partir de los esquemas basados en eventos en [!UICONTROL Experience Platform]. | Cualquier esquema integrado o personalizado basado en una clase XDM con el comportamiento “Serie temporal”. Algunos ejemplos son “Evento de experiencias XDM” o “Evento de decisiones XDM”. | Puede elegir qué ID de persona desea incluir. Cada esquema del conjunto de datos definido en Experience Platform puede tener su propio conjunto de una o más identidades definidas y asociadas a un área de nombres de identidad. Cualquiera de ellos puede utilizarse como ID de persona. Algunos ejemplos son: ID de cookie, ID vinculado, ID de usuario, código de seguimiento, etc. |
| **[!UICONTROL Búsqueda]** | Ahora puede añadir conjuntos de datos como consultas de campos dentro de todos los tipos de conjuntos de datos: conjuntos de datos de perfil, consulta y evento (este último siempre ha sido compatible). Esta capacidad adicional amplía la capacidad de Customer Journey Analytics para admitir modelos de datos complejos, incluido B2B. Estos datos se utilizan para buscar valores o claves encontrados en los datos de Evento, Perfil o de Búsqueda. Puede agregar hasta dos niveles de búsquedas. (Tenga en cuenta que [Campos derivados](/help/data-views/derived-fields/derived-fields.md) no se puede usar como claves coincidentes para búsquedas dentro de Conexiones). Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a los nombres de producto. Vea el [ejemplo B2B](/help/use-cases/b2b/example.md) para ver un ejemplo. | N/A | Cualquier esquema integrado o personalizado basado en una clase XDM con el comportamiento “Record”, excepto la clase “XDM Individual Profile”. | N/A |
| **[!UICONTROL Perfil]** | Datos que se aplican a sus personas, usuarios o clientes en los datos de [!UICONTROL Evento]. Por ejemplo, le permite cargar datos de CRM sobre sus clientes. | N/A | Cualquier esquema integrado o personalizado basado en la clase “XDM Individual Perfil”. | Puede elegir qué ID de persona desea incluir. Cada conjunto de datos (excepto los de resumen) definido en [!DNL Experience Platform] tiene su propio conjunto de uno o más ID de persona definidos. Por ejemplo, ID de cookie, ID vinculado, ID de usuario, código de seguimiento, etc.<br>![ID de persona ](assets/person-id.png)**Nota**: Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes lo reflejará. Para combinar conjuntos de datos, es necesario usar el mismo ID de persona. |
| **Resumen** | Datos de series temporales que no están vinculadas a un ID de persona individual. Los datos de resumen representan datos agregados en un nivel diferente de agregación, por ejemplo campañas. Puede utilizar estos datos en Customer Journey Analytics para admitir varios casos de uso. Consulte [Datos de resumen](/help/data-views/summary-data.md) para obtener más información. | Se establece automáticamente en el campo de marca de tiempo predeterminado a partir de los esquemas de métricas de resumen basados en eventos en Experience Platform. Solo se admite la granularidad por hora o por día. | Cualquier esquema integrado o personalizado basado en la clase «Métricas de resumen de XDM». | N/A |

{style="table-layout:auto"}

## Usar campos numéricos como claves y valores de búsqueda {#numeric}

Esta funcionalidad de búsqueda es útil si desea agregar un campo numérico como un coste o margen a un campo de clave basado en cadenas. Permite que los valores numéricos formen parte de búsquedas, ya sea como claves o como valores. En el esquema de búsqueda, es posible que tenga valores numéricos vinculados, por ejemplo, a sus nombres de producto, COGS, costos de marketing de campaña o márgenes. Este es un ejemplo de esquema de búsqueda en Adobe Experience Platform:

![Esquema de búsqueda](assets/schema.png)

Ahora se admite la introducción de estos valores como métricas o dimensiones en la creación de informes de Customer Journey Analytics. Al configurar la conexión y extraer los conjuntos de datos de consulta, puede editar los conjuntos de datos para seleccionar la [!UICONTROL Clave] y [!UICONTROL Clave de coincidencia]:

![Editar conjunto de datos](assets/lookup-dataset.png)

Al configurar una vista de datos basada en esta conexión, se agregan los valores numéricos como componentes a la vista de datos. Cualquier proyecto basado en esta vista de datos puede generar informes sobre estos valores numéricos.

## Use el mapa de identidad como ID de persona {#id-map}

Customer Journey Analytics admite la capacidad de usar el mapa de identidad para su ID de persona. El mapa de identidad es una estructura de datos de mapa que le permite cargar pares de clave -> valor. Las claves son áreas de nombres de identidad y el valor es una estructura que contiene el valor de identidad. El mapa de identidad existe en cada fila o evento cargado y se completa para cada fila en consecuencia.

El mapa de identidad está disponible para cualquier conjunto de datos que utilice un esquema basado en la clase [ExperienceEvent XDM](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home). Al seleccionar un conjunto de datos para incluir en una conexión de Customer Journey Analytics, tiene la opción de seleccionar un campo como ID principal o el mapa de identidad:

![](assets/idmap1.png)

Si selecciona Mapa de identidad, obtendrá dos opciones de configuración adicionales:

| Opción | Descripción |
|---|---|
| **[!UICONTROL Usar área de nombres de ID primario]** | Esta opción indica a Customer Journey Analytics que busque la identidad en el Mapa de identidad que está marcado con un atributo `primary=true` y que la utilice como ID de persona para esa fila. Esta identidad es la clave principal que se utiliza en el Experience Platform para la partición. Y esta identidad también es la candidata principal para su uso como ID de persona de Customer Journey Analytics (según la configuración del conjunto de datos en una conexión de Customer Journey Analytics). |
| **[!UICONTROL Área de nombres]** | (Esta opción solo está disponible si no utiliza el área de nombres de ID principal). Las áreas de nombres de identidad son un componente del [servicio de identidad de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/identity/features/namespaces). Las áreas de nombres sirven como indicadores del contexto al que se relaciona una identidad. Si especifica un área de nombres, Customer Journey Analytics busca en el Mapa de identidad de cada fila esta clave de área de nombres y utilizará la identidad en el área de nombres como ID de persona para esa fila. Dado que Customer Journey Analytics no puede realizar una exploración completa de todos los conjuntos de datos de todas las filas para determinar qué áreas de nombres están presentes, en la lista desplegable se muestran todas las áreas de nombres posibles. Sepa qué áreas de nombres se especifican en los datos; estas áreas de nombres no se detectan automáticamente. |

{style="table-layout:auto"}

### Casos extremos del mapa de identidad {#id-map-edge}

En esta tabla se muestran las dos opciones de configuración cuando están presentes los casos extremos y cómo se gestionan:

| Opción | No hay ID presentes en el Mapa de identidad | ID múltiples, ninguno marcado como principales | Los ID múltiples se marcan como principales | ID único, marcado como principal o no | Área de nombres no válida con un ID marcado como principal |
|---|---|---|---|---|---|
| **[!UICONTROL Usar área de nombres de ID primario] verificado** | Customer Journey Analytics descarta la fila. | Customer Journey Analytics descarta la fila porque no hay ningún ID principal especificado. | Todos los ID marcados como principales, con todas las áreas de nombres, se extraen en una lista. A continuación, se ordenan alfabéticamente; con esta nueva clasificación, la primera área de nombres con su primer ID se utiliza como el ID de persona. | El ID único se utiliza como ID de persona. | Aunque el área de nombres puede no ser válida (no está presente en Adobe Experience Platform), Customer Journey Analytics utiliza el ID principal de dicha área de nombres como ID de persona. |
| **[!UICONTROL Área de nombres de un mapa de identidad específica] seleccionada** | Customer Journey Analytics descarta la fila. | Todos los ID del área de nombres seleccionada se extraen en una lista y el primero se utiliza como ID de persona. | Todos los ID del área de nombres seleccionada se extraen en una lista y el primero se utiliza como ID de persona. | Todos los ID del área de nombres seleccionada se extraen en una lista y el primero se utiliza como ID de persona. | Todos los ID del área de nombres seleccionada se extraen en una lista y el primero se utiliza como ID de persona. (Solo se puede seleccionar un área de nombres válida en el momento de la creación de la conexión, por lo que no es posible utilizar un área de nombres o ID no válida como ID de persona) |

{style="table-layout:auto"}

## Cálculo del número promedio de eventos diarios {#average-number}

Este cálculo debe realizarse para todos los conjuntos de datos de la conexión.

1. Vaya a [Servicios de consulta de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/query/home) y cree una consulta.

   La consulta tendría un aspecto similar al siguiente:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   En este ejemplo, “analytics_demo_data” es el nombre del conjunto de datos.

2. Para mostrar todos los conjuntos de datos que existen en Adobe Experience Platform, realice la consulta `Show Tables`.


## Eliminación algorítmica de conjuntos de datos de búsqueda grandes

Al crear una conexión, puede añadir grandes conjuntos de datos para fines de búsqueda. Por ejemplo, un conjunto de datos que representa un catálogo de productos de modo que se pueda buscar información descriptiva del producto al crear informes y visualizaciones. Un conjunto de datos de consulta de este tamaño puede superar el máximo de 10 millones de consultas únicas implementadas actualmente como mecanismo de protección, lo que provoca que se omitan datos adicionales.

Puede solicitar la eliminación algorítmica de un gran conjunto de datos de búsqueda. Esta limpieza algorítmica solo mantiene los datos en el conjunto de datos de búsqueda que coincide con las claves del conjunto de datos de evento. De este modo, no es necesario cargar todo el conjunto de datos de búsqueda sin eliminar. Se eliminan los artículos antiguos o utilizados con menos frecuencia, lo que podría afectar ligeramente a los informes, pero trae beneficios significativos. El algoritmo se remonta 90 días y se actualiza semanalmente.

Póngase en contacto con el equipo de soporte de Adobe para obtener más información y para habilitar esta capacidad.
