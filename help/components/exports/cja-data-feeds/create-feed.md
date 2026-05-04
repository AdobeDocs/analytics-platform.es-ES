---
title: Crear un feed de datos
description: Aprenda a crear una fuente de datos y conozca la información del archivo que debe proporcionar a Adobe.
hide: true
feature: Components
source-git-commit: a565bc01f47255b98436a52c00a933a6f845e9ec
workflow-type: tm+mt
source-wordcount: '2477'
ht-degree: 20%

---

# Creación de un feed de datos

Al crear un feed de datos, debe proporcionar a Adobe lo siguiente:

* La información sobre el destino al que desea enviar los archivos de datos sin procesar

* Los datos que desea incluir en cada archivo

* La frecuencia con la que se debe enviar la fuente de datos (incluida la ventana retrospectiva si elige incluir las visitas que llegan tarde)

Antes de crear un feed de datos, es importante tener una comprensión básica de las fuentes de datos y asegurarse de que cumple todos los requisitos previos. Para obtener más información, consulte [Información general sobre feeds de datos](data-feed-overview.md).

## Crear o configurar una fuente de datos {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_os_strings"
>title="Reemplazar cadenas del sistema operativo"
>abstract="Esta opción limpia la salida de datos detectando las siguientes secuencias de cadenas incrustadas en los datos del cliente y reemplazándolas por un espacio: <br/>Windows: CRLF, CR o TAB<br/>Mac y Linux: \n, \r o \t"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_export_file"
>title="Manifiesto"
>abstract="Elija si desea incluir un archivo de manifiesto con cada entrega de feed de datos. Los archivos de manifiesto contienen información para cada archivo incluido en el feed de datos. Al enviar datos del feed de datos en un solo paquete, también puede optar por incluir un archivo de finalización, pero se recomiendan los archivos de manifiesto. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_notify"
>title="Notificar cuando se complete"
>abstract="Especifique una o varias direcciones de correo electrónico a las que se debe enviar una notificación después de enviar el feed de datos. Las múltiples direcciones de correo electrónico deben separarse con una coma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_lookback_date_range"
>title="Intervalo de fecha de retroactividad"
>abstract="Controla la distancia a la que se muestra Customer Journey Analytics al procesar la entrega de fuentes de datos.<br/>Esta configuración no altera la ventana de frecuencia (hora o día). Sin embargo, el intervalo de fechas de retrospectiva puede influir en los datos que se envían. La calificación de segmentos, el cálculo de sesiones y la persistencia de dimensiones se ven afectados por el intervalo de fechas retrospectivo."

<!-- markdownlint-enable MD034 -->

<!-- added help for Dynamic lookups to this page: help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md -->

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.

1. Seleccione el icono de 9 cuadrados en la esquina superior derecha, luego seleccione [!UICONTROL **Customer Journey Analytics**].

1. En la barra de navegación superior, vaya a [!UICONTROL **Administrador**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione [!UICONTROL **Crear fuente de datos**].

   Aparece una página con las siguientes fichas: [!UICONTROL **Detalles**], [!UICONTROL **Estructura de datos**] y [!UICONTROL **Envío**].

   ![Nueva página de fuente de datos](assets/data-feed-new.png)

1. En la sección [!UICONTROL **Detalles**], complete los campos siguientes:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre**] | El nombre de la fuente de datos. Los nombres deben ser únicos dentro del grupo de informes seleccionado y pueden tener hasta 255 caracteres de longitud. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Etiquetas**] | Aplique cualquier etiqueta a la fuente de datos para facilitar la categorización. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Descripción**] | Especifique una descripción para la fuente de datos. La descripción que agregue será visible al editar la fuente de datos. |
   | [!UICONTROL **Vista de datos**] | Seleccione la vista de datos que contiene los datos que desea exportar. |

1. En la sección [!UICONTROL **Formato de datos**], especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Formato de compresión**] | Tipo de compresión utilizado. **Gzip** genera archivos en formato `.tar.gz`. **Zip** genera archivos en formato `.zip`. |
   | [!UICONTROL **Tipo de empaquetado**] | Seleccione [!UICONTROL **Varios archivos**] para la mayoría de las fuentes de datos. Esta opción pagina los datos en fragmentos de 2 GB sin comprimir. (Si se selecciona la opción [!UICONTROL **Varios archivos**] y los datos sin comprimir de la ventana de informes ocupan menos de 2 GB, se envía un solo archivo). Si se selecciona **Un solo archivo**, se genera el archivo `hit_data.tsv` en un único archivo potencialmente masivo. |
   | [!UICONTROL **Manifiesto**] | Elija si desea incluir un archivo de manifiesto con cada entrega de feed de datos. <p>Puede elegir entre las siguientes opciones:</p><ul><li>**[!UICONTROL Archivo de manifiesto]**: contiene información para cada archivo incluido en la fuente de datos.</li><li>**[!UICONTROL Finalizar archivo (heredado)]**: indica que la fuente de datos se completó correctamente. No se incluye otra información. Esta opción es adecuada para las fuentes existentes que originalmente utilizaron esta opción y que deben volver a procesarse. Solo está disponible cuando se envían datos de fuente de datos en un solo paquete. </li><li>**[!UICONTROL Ninguno]**: no se incluye ningún archivo</li></ul> |
   | [!UICONTROL **Enviar manifiesto aunque no haya datos**] | Determina si Adobe debe enviar un archivo de manifiesto <!--[manifest file](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md#feed-manifest)--> al destino cuando no se recopilan datos para un intervalo de fuente. Si selecciona **Archivo de manifiesto**, recibirá un archivo de manifiesto similar al siguiente cuando no se recopilen datos:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Reemplazar cadenas del sistema operativo**] | Al recopilar datos, algunos caracteres (como las líneas nuevas) pueden causar problemas. Seleccione esta opción para eliminar estos caracteres de los archivos de fuente.<p>Esta opción detecta las siguientes secuencias de cadenas incrustadas en los datos del cliente y las reemplaza por un espacio:</p> <ul><li>**Windows:** CRLF, CR o TAB</li><li>**Mac y Linux:** \n, \r o \t</li></ul> |
   | [!UICONTROL **Habilitar búsquedas dinámicas**] | Las búsquedas dinámicas permiten recibir archivos de búsqueda adicionales en la fuente de datos que, de lo contrario, no estarán disponibles. Esta configuración permite enviar las siguientes tablas de búsqueda con cada archivo de feed de datos:<ul><li> **Nombre de operador**</li><li>**Atributos móviles**</li><li>**Tipo de sistema operativo**</li></ul><!--<p>For more information, see [Dynamic lookups](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md).</p>--> |
   | **Permitir visitas que llegan tarde** | Los datos históricos pueden llegar después de que un trabajo de fuente de datos termine de procesarse durante una hora o un día determinados, por ejemplo, mediante visitas con marca de tiempo u origen de datos.<p>Seleccione esta opción para incluir datos que llegaron después de que el trabajo de feed de datos terminara de procesar los datos dentro de la frecuencia de creación de informes establecida (normal o diariamente o cada hora). Con esta opción habilitada, cada vez que un feed de datos procesa la información, examina las visitas que han llegado y las procesa por lotes con el siguiente archivo de feed de datos que se envía.</p><!--<p>For more information, see [Late-arriving hits](/help/export/analytics-data-feed/c-df-contents/late-arriving-hits.md).</p>--> |
   | **Ventana retrospectiva** (para visitas que llegan tarde) | Esta opción se muestra cuando la opción **[!UICONTROL Permitir visitas que llegan tarde]** está habilitada. Seleccione la ventana retrospectiva para limitar el lapso de tiempo de las visitas tardías que se incluyen. Seleccione **[!UICONTROL Ilimitado]** si desea permitir todas las visitas que llegan tarde, independientemente de la demora. Puede elegir un intervalo preestablecido, como **[!UICONTROL 1 hora]**, **[!UICONTROL 2 horas]**, **[!UICONTROL 1 semana]**, **[!UICONTROL 2 semanas]**, etc. O bien, seleccione **[!UICONTROL Ventana retrospectiva personalizada]** y, a continuación, en el campo **[!UICONTROL Retrospectiva personalizada]** especifique una ventana retrospectiva de hasta 26.280 horas. |

1. En la sección [!UICONTROL **Estructura de datos**], asegúrese de que la vista de datos correcta esté seleccionada en el campo **[!UICONTROL Vista de datos]**. <p>Tenga en cuenta lo siguiente al seleccionar una vista de datos:</p> <ul><li>Si se crean varias fuentes de datos para la misma vista de datos, cada fuente de datos debe tener definiciones de columnas diferentes.</li><li>La lista de columnas disponibles depende de la empresa de inicio de sesión a la que pertenezca la vista de datos seleccionada. Si cambia la vista de datos, puede cambiar la lista de columnas disponibles. </li></ul>

1. Utilice uno o ambos de los métodos siguientes para determinar qué columnas de datos incluir en la fuente:

   * **Agregar columnas individualmente:** En la sección **[!UICONTROL Disponible]** de la izquierda, seleccione las columnas que desee incluir y, a continuación, seleccione **[!UICONTROL Incluir]**. Todas las columnas de datos de Adobe Analytics están disponibles. Para seleccionar varias columnas, mantenga presionada la tecla **[!UICONTROL Mayús]**, o bien mantenga presionada la tecla **[!UICONTROL Comando]** (en macOS) o la tecla **[!UICONTROL Ctrl]** (en Windows). Haga clic en **[!UICONTROL Agregar todo]** para incluir todas las columnas en un feed de datos.

     Las columnas que agregue aparecerán en la sección **[!UICONTROL Included]** de la derecha.

   * **Agregar una plantilla de columna:** En el campo **[!UICONTROL Plantillas de columna]**, seleccione una plantilla de columna para agregar. Una plantilla de columna es un grupo predefinido de columnas y Adobe proporciona varias de forma predeterminada.

     Todas las columnas incluidas en la plantilla aparecen en la sección **[!UICONTROL Included]** de la derecha.

1. (Opcional) Para crear una plantilla de columna basada en la fuente de datos que está creando, seleccione **[!UICONTROL Guardar como plantilla]**, especifique un nombre para la plantilla y, a continuación, seleccione **[!UICONTROL Guardar]**. Esta opción es útil si planea crear fuentes de datos adicionales que incluyan las mismas columnas.

   ![Crear plantilla de columna al crear una fuente de datos](assets/data-feed-template-create2.png)

1. (Opcional) Para descargar una lista de columnas incluidas en formato .csv, seleccione **[!UICONTROL Descargar columnas]**. Esta opción puede resultar útil para las fuentes de datos que tienen un gran número de columnas.

1. En la sección [!UICONTROL **Delivery**], especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Tipo de fuente**] | Seleccione el tipo de fuente que desea crear:<ul><li>[!UICONTROL **Fuente activa**]: exporta datos actuales y futuros.</li><li>[!UICONTROL **Fuente de relleno**]: exporta datos históricos entre dos fechas pasadas.</li></ul> |
   | [!UICONTROL **Fecha de inicio**] | Especifique la fecha en la que desea que comience la fuente de datos. Para empezar a procesar fuentes de datos para datos históricos de inmediato, asegúrese de seleccionar [!UICONTROL **Fuente de relleno**] y luego establezca esta fecha en cualquier fecha del pasado en que se estén recopilando datos. La fecha de inicio se basa en la zona horaria de la vista de datos. |
   | [!UICONTROL **Fecha de finalización**] | Especifique la fecha en la que desea que finalice la fuente de datos. La fecha de finalización se basa en la zona horaria de la vista de datos. |
   | [!UICONTROL **Frecuencia**] | Seleccione la frecuencia con la que se debe enviar la fuente de datos. Los eventos con marcas de tiempo incluidas en la ventana de frecuencia se incluyen en la entrega de fuentes de datos. Los campos [!UICONTROL **Intervalo de fechas de retrospectiva**] y [!UICONTROL **Demora de procesamiento**] también pueden afectar qué eventos se incluyen en los datos para la frecuencia de envío que elija.<p>Seleccione esta opción para incluir datos de una hora o de un día:</p><ul><li>**Diario**: las fuentes contienen datos de un día completo, de medianoche a medianoche en el huso horario de la vista de datos. Utilice esta opción para fuentes de relleno o para fuentes activas.</li><li>**Por hora**: las fuentes contienen datos de una sola hora. Utilice esta opción para las fuentes activas.</li></ul> |
   | [!UICONTROL **Intervalo de fechas de retrospectiva**] | Controla la distancia a la que se muestra Customer Journey Analytics al procesar la entrega de fuentes de datos. <p>Esta configuración no altera la ventana de frecuencia (hora o día), que define el lapso de tiempo de los eventos que se incluirán en la salida de fuente de datos. Sin embargo, el intervalo de fechas de retrospectiva puede influir en los datos que se envían de las siguientes maneras: </p><ul><li>**Calificación de segmentos**: Cuando se aplica un segmento a su definición de fuente de datos, cualquier evento dentro del intervalo de fechas retrospectivas determina si una persona cumple los requisitos. La configuración del contenedor del segmento determina el ámbito. (Los contenedores posibles son: Persona, Sesión o Evento. B2B tiene los siguientes contenedores adicionales: Cuenta global, Cuenta, Oportunidad, Grupo de compra).  <p>Por ejemplo, si se utiliza un contenedor de persona y la persona se califica durante el intervalo de fechas retrospectivas, también se calificarán todos los eventos de esa persona durante la ventana de frecuencia.</p></li><li>**Cálculo de sesión**: los límites de sesión se calculan usando datos dentro del intervalo de fechas retrospectivo.</li><li>**Persistencia de Dimension**: Si elige establecer la persistencia en una dimensión individual, también elige una caducidad para determinar cuánto tiempo persiste un elemento de dimensión más allá del evento en el que está establecido. <p>El intervalo de fechas de retrospectiva afecta a la persistencia de la dimensión cuando la caducidad se establece en cualquiera de las siguientes opciones de la vista de datos:</p><ul><li>Para cada dimensión de la definición de fuente de datos que usa [!UICONTROL **Ventana de informes**] como caducidad, el intervalo de fecha retrospectiva se convierte en la nueva ventana de informes.</li><li>Para cada dimensión de la definición de fuente de datos que usa [!UICONTROL **Tiempo personalizado**] como caducidad, y si la hora personalizada que se selecciona se extiende más allá del intervalo de fechas de retrospectiva, se ignora la hora personalizada y se usa el intervalo de fechas de retrospectiva para la caducidad de la dimensión.<p>Para obtener más información acerca de cómo establecer la persistencia en dimensiones dentro de la vista de datos, vea [Configuración del componente de persistencia](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Retraso de procesamiento**] | Elija si desea esperar un tiempo determinado antes de procesar un archivo de fuente de datos. Un retraso puede resultar útil para ofrecer a las implementaciones móviles la oportunidad de que los dispositivos sin conexión se conecten y envíen datos. También se puede utilizar para dar cabida a los procesos del lado del servidor de su organización en la administración de archivos procesados anteriormente. En la mayoría de los casos, no es necesario un retraso. Puede retrasar una fuente hasta 8 horas (480 minutos) o incluso más si selecciona un período de tiempo personalizado (9999 minutos de retraso o aproximadamente 1 semana).<p>Si no se establece ningún retraso, solo se incluyen en la fuente los eventos que se encuentran dentro de la ventana de frecuencia (el último día o la última hora). |

1. En la sección [!UICONTROL **Destino**], configure el destino al que desea enviar los datos.

   >[!NOTE]
   >
   >Al configurar el destino de un informe, tenga en cuenta lo siguiente:
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Todas las cuentas de nube que haya configurado anteriormente están disponibles para su uso en fuentes de datos. Puede configurar cuentas en la nube desde el administrador Ubicaciones, en [Componentes > Exportaciones > Cuentas de ubicación](/help/components/exports/cloud-export-accounts.md).
   >
   >* Las cuentas de nube de están asociadas a su cuenta de usuario de Customer Journey Analytics. Otros usuarios no pueden usar ni ver las cuentas de nube que configure a menos que las ponga a disposición de todos los usuarios de su organización.
   >
   >* Puede editar cualquier ubicación que cree desde el administrador Ubicaciones en [Componentes > Exportaciones > Ubicaciones](/help/components/exports/cloud-export-locations.md).

   Complete los campos siguientes:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Cuenta**] | Realice cualquiera de los siguientes pasos:<ul><li>**Usar una cuenta existente:** Seleccione el menú desplegable situado junto al campo **[!UICONTROL Cuenta]**. O bien, empiece a escribir el nombre de la cuenta y, a continuación, selecciónela en el menú desplegable. <p>Las cuentas solo están disponibles si las ha configurado o si se comparten con una organización de la que forma parte.</p></li><li>**Crear una nueva cuenta:** Seleccione **[!UICONTROL Agregar nuevo]** debajo del campo **[!UICONTROL Cuenta]**. Para obtener información sobre cómo configurar la cuenta, consulte [Configurar cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Ubicación**] | Realice cualquiera de los siguientes pasos:<ul><li>**Usar una ubicación existente:** Seleccione el menú desplegable situado junto al campo **[!UICONTROL Ubicación]**. O bien, empiece a escribir el nombre de la ubicación y, a continuación, selecciónela en el menú desplegable.</li><li>**Crear una nueva ubicación:** Seleccione **[!UICONTROL Agregar nuevo]** debajo del campo **[!UICONTROL Ubicación]**. Para obtener información sobre cómo configurar la ubicación, consulte [Configurar ubicaciones de exportación de la nube](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Notificar cuando se complete**] | Especifique una o varias direcciones de correo electrónico a las que se debe enviar una notificación después de que la fuente de datos se haya enviado correctamente o no se haya enviado. Las múltiples direcciones de correo electrónico deben separarse con una coma. |
   | [!UICONTROL **Habilitar manifiesto**] | Elija si desea incluir un archivo de manifiesto con cada entrega de feed de datos. <p>Puede elegir entre las siguientes opciones:</p><ul><li>**[!UICONTROL Archivo de manifiesto]**: contiene información para cada archivo incluido en la fuente de datos.</li><li>**[!UICONTROL Finalizar archivo (heredado)]**: indica que la fuente de datos se completó correctamente. No se incluye otra información. Esta opción es adecuada para las fuentes existentes que originalmente utilizaron esta opción y que deben volver a procesarse. Solo está disponible cuando se envían datos de fuente de datos en un solo paquete. </li><li>**[!UICONTROL Ninguno]**: no se incluye ningún archivo</li></ul> |

1. Seleccione **[!UICONTROL Guardar]**.

## Administrar plantillas de columna

Las plantillas le permiten reutilizar las mismas columnas para futuras fuentes de datos que cree.

Al administrar plantillas, puede crear nuevas plantillas, utilizar plantillas que ya se han creado, copiar plantillas, editar plantillas y eliminar plantillas.

**[!UICONTROL Administrador]** > **[!UICONTROL Fuentes de datos]** > **[!UICONTROL Administrar plantillas]**

![Administrar plantillas de columna](assets/data-feed-template-manage.png)

### Creación de una plantilla de columna

Al crear varias fuentes de datos que utilicen las mismas columnas, Adobe recomienda crear plantillas de columna. Cualquier plantilla de columna que cree estará disponible para su uso por parte de cualquier persona de su organización.

Para crear una plantilla de columna:

1. En Adobe Analytics, vaya a [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**] > **[!UICONTROL Administrar plantillas]**.

1. Seleccione **[!UICONTROL Crear nueva plantilla]** para crear una nueva plantilla de columna.

   ![Crear plantilla de columna](assets/data-feed-template-create.png)

1. En el campo **[!UICONTROL Nombre de plantilla]**, especifique un nombre para la plantilla.

1. En la sección **[!UICONTROL Disponible]** de la izquierda, seleccione las columnas que desee incluir y después seleccione **[!UICONTROL Incluir]**. Todas las columnas de datos disponibles en Adobe Analytics están disponibles. Para seleccionar varias columnas, mantenga presionada la tecla **[!UICONTROL Mayús]**, o bien mantenga presionada la tecla **[!UICONTROL Comando]** (en macOS) o la tecla **[!UICONTROL Ctrl]** (en Windows). Haga clic en **[!UICONTROL Agregar todo]** para incluir todas las columnas en un feed de datos.

   Las columnas que agregue aparecerán en la sección **[!UICONTROL Included]** de la derecha.

1. Seleccione **[!UICONTROL Guardar]**.

### Edición de una plantilla de columna

1. En Adobe Analytics, vaya a [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**] > **[!UICONTROL Administrar plantillas]**.

1. Seleccione la plantilla que desee editar y, a continuación, seleccione **[!UICONTROL Editar]**.

1. Realice las modificaciones que desee y seleccione **[!UICONTROL Guardar]**.

### Copiar una plantilla de columna

1. En Adobe Analytics, vaya a [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**] > **[!UICONTROL Administrar plantillas]**.

1. Seleccione la plantilla que desee copiar y, a continuación, seleccione **[!UICONTROL Copiar]**.

1. En el campo **[!UICONTROL Nombre de plantilla]**, especifique un nombre para la plantilla.

1. Realice cambios adicionales y, a continuación, seleccione **[!UICONTROL Guardar]**.

### Eliminar plantillas de columna

1. En Adobe Analytics, vaya a [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**] > **[!UICONTROL Administrar plantillas]**.

1. Seleccione una o más plantillas que desee eliminar y, a continuación, seleccione **[!UICONTROL Eliminar]**.


<!-- why would you want to do this? -->


<!--
I don't think we need anything after this, but saving here just in case:

1. In the [!UICONTROL **Feed Information**] section, complete the following fields:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the data feed. Must be unique within the selected report suite, and can be up to 255 characters in length. [Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique) |
   | [!UICONTROL **Report suite**] | The report suite that the data feed is based on. If multiple data feeds are created for the same report suite, they must have different column definitions. Only source report suites support data feeds; virtual report suites are not supported. |
   | [!UICONTROL **Email when complete**] | The email address to be notified when a feed finishes processing. The email address must be properly formatted. |
   | [!UICONTROL **Feed interval**] | Select **Daily** for backfill or historical data. Daily feeds contain a full day's worth of data, from midnight to midnight in the report suite's time zone. Select **Hourly** for continuing data (Daily is also available for continuing feeds if you prefer). Hourly feeds contain a single hour's worth of data. |
   | [!UICONTROL **Delay processing**] | Wait a given amount of time before processing a data feed file. A delay can be useful to give mobile implementations an opportunity for offline devices to come online and send data. It can also be used to accommodate your organization's server-side processes in managing previously processed files. In most cases, no delay is needed. A feed can be delayed by up to 120 minutes. |
   | [!UICONTROL **Start & end dates**] | The start date indicates the date when you want the data feed to begin. To immediately begin processing data feeds for historical data, set this date to any date in the past when data is being collected. The start and end dates are based on the report suite's time zone. |
   | [!UICONTROL **Continuous feed**] | This checkbox removes the end date, allowing a feed to run indefinitely. When a feed finishes processing historical data, a feed waits for data to finish collecting for a given hour or day. Once the current hour or day concludes, processing begins after the specified delay. |
   
1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select the destination where you want the data to be sent. 

   >[!NOTE]
   >
   >Consider the following when configuring a report destination:
   >
   >* We recommend using a cloud account for your report destination. [Legacy FTP and SFTP accounts](#legacy-destinations) are available, but are not recommended.
   >* Any cloud accounts that you previously configured are available to use for Data Feeds. You can configure cloud accounts in any of the following ways:
   >
   >   * When configuring cloud accounts for [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) 
   >   
   >   * When [importing Adobe Analytics classification data](/help/components/locations/locations-manager.md) (Any locations that are configured for importing classification data cannot be used.)
   >   
   >   * From the Locations manager, in [Components > Locations](/help/components/locations/configure-import-accounts.md) 
   >
   >* Cloud accounts are associated with your Adobe Analytics user account. Other users cannot use or view cloud accounts that you configure.
   >
   >* You can edit any locations that you create from the Locations manager in [Components > Locations](/help/components/locations/configure-import-accounts.md)

   ![Data feed destination drop-down menu](assets/datafeed-destinations-dropdown.png)

   Use any of the following destination types when creating a data feed. For configuration instructions, expand the destination type. (Additional [legacy destinations](#legacy-destinations) are also available, but are not recommended.)

   +++Amazon S3

   You can send feeds directly to Amazon S3 buckets. This destination type requires only your Amazon S3 account and the location (bucket). 

   Adobe Analytics uses cross-account authentication to upload files from Adobe Analytics to the specified location in your Amazon S3 instance.

   When using Amazon S3 with Data Feeds, only SSE-S3 encryption is supported.

   To configure an Amazon S3 bucket as the destination for a data feed:

   1. Begin creating a data feed as described in [Create and configure a data feed](#create-and-configure-a-data-feed).
   
   1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select [!UICONTROL **Amazon S3**].

      ![Amazon S3 destination](assets/datafeed-destination-amazons3.png)

   1. Select [!UICONTROL **Select location**].

      The Amazon S3 Export Locations page is displayed.

   1. (Conditional) If an Amazon S3 account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that were configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).
   
      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

      The destination is now configured to send data to the Amazon S3 location that you specified.
   
   1. (Conditional) If you have not previously added an Amazon S3 account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the account. This can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the account. |
         | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **User ARN**] | The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created. |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the account.  |
         | [!UICONTROL **Description**] | A description for the account. |
         | [!UICONTROL **Bucket**] | The bucket within your Amazon S3 account where you want Adobe Analytics data to be sent. <p>Ensure that the User ARN that was provided by Adobe has the `S3:PutObject` permission in order to upload files to this bucket. This permission allows the User ARN to upload initial files and overwrite files for subsequent uploads.</p><p>Bucket names must meet specific naming rules. For example, they must be between 3 to 63 characters long, can consist only of lowercase letters, numbers, dots (.), and hyphens (-), and must begin and end with a letter or number. [A complete list of naming rules are available in the AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Amazon S3 location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Azure RBAC

   You can send feeds directly to an Azure container by using RBAC authentication. This destination type requires an Application ID, Tenant ID, and Secret. 

   To configure an Azure RBAC account as the destination for a data feed:

   1. If you haven't already, create an Azure application that Adobe Analytics can use for authentication, then grant access permissions in access control (IAM). 
   
      For information, refer to the [Microsoft Azure documentation about how to create an Azure Active Directory application](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal). 
   
   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select [!UICONTROL **Azure RBAC**].

      ![Azure RBAC destination](assets/datafeed-destination-azurerbac.png)

   1. Select [!UICONTROL **Select location**].

      The Azure RBAC Export Locations page is displayed.

   1. (Conditional) If an Azure RBAC account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

      Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure RBAC location that you specified.

   1. (Conditional) If you have not previously added an Azure RBAC account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the Azure RBAC account. This name displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the Azure RBAC account. This description displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose.  |
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information: 
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the location. This name displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Description**] | A description for the location. This description displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account**] | The Azure storage account. |
         | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. |
         | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure the Application ID that you specified when configuring the Azure RBAC account has been granted the `Storage Blob Data Contributor` role in order to access the container (folder).</p> <p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure RBAC location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Azure SAS

   You can send feeds directly to an Azure container by using SAS authentication. This destination type requires an Application ID, Tenant ID, Key vault URI, Key vault secret name, and secret. 

   To configure Azure SAS as the destination for a data feed:

   1. If you haven't already, create an Azure application that Adobe Analytics can use for authentication. 
   
      For information, refer to the [Microsoft Azure documentation about how to create an Azure Active Directory application](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal). 
   
   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, select [!UICONTROL **Azure SAS**].

      ![Azure SAS destination](assets/datafeed-destination-azuresas.png)

   1. Select [!UICONTROL **Select location**].

      The Azure SAS Export Locations page is displayed.

   1. (Conditional) If an Azure SAS account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure SAS location that you specified.
   
   1. (Conditional) If you have not previously added an Azure SAS account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the Azure SAS account. This name displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the Azure SAS account. This description displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Key vault URI**] | <p>The path to the SAS URI in Azure Key Vault. To configure Azure SAS, you need to store an SAS URI as a secret using Azure Key Vault. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>After the key vault URI is created:<ul><li>Add an access policy on the Key Vault in order to grant permission to the Azure application that you created.<p>For information, see the [Microsoft Azure documentation about how to assign a Key Vault access policy](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Or</p><p>If you want to grant an access role directly without creating an access policy, see the [Microsoft Azure documentation about how to assign Azure roles using Azure portal](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). This adds the role assignment for the application ID to access the key vault URI. </p></li><li>Make sure the Application ID has been granted the `Key Vault Certificate User` built-in role in order to access the key vault URI.</br><p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Key vault secret name**] | The secret name you created when adding the secret to Azure Key Vault. In Microsoft Azure, this information is located in the Key Vault you created, on the **Key Vault** settings pages. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information: 
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the location. This name displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Description**] | A description for the location. This description displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. |
         | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure that the SAS URI store that you specified in the Key Vault secret name field when configuring the Azure SAS account has the `Write` permission. This allows the SAS URI to create files in your Azure container. <p>If you want the SAS URI to also overwrite files, make sure that the SAS URI store has the `Delete` permission.</p><p>For more information, see [Blob storage resources](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) in the Azure Blob Storage documentation.</p> |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure SAS location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Google Cloud Platform

   You can send feeds directly to Google Cloud Platform (GCP) buckets. This destination type requires only your GCP account name and the location (bucket) name. 
   
   Adobe Analytics uses cross-account authentication to upload files from Adobe Analytics to the specified location in your GCP instance.

   To configure a GCP bucket as the destination for a data feed:

   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, select [!UICONTROL **Google Cloud Platform**].

      ![Google Cloud Platform destination](assets/datafeed-destination-gcp.png)

   1. Select [!UICONTROL **Select location**].

      The GCP Export Locations page is displayed.

   1. (Conditional) If a Google Cloud Platform account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Google Cloud Platform location that you specified.
   
   1. (Conditional) If you have not previously added a GCP account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the account. This can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the account. |
         | [!UICONTROL **Project ID**] | Your Google Cloud project ID. See the [Google Cloud documentation about getting a project ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Principal**] | The Principal is provided by Adobe. You must grant permission to receive feeds to this principal. |
         | [!UICONTROL **Name**] | A name for the account.  |
         | [!UICONTROL **Description**] | A description for the account. |
         | [!UICONTROL **Bucket**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. <p>Ensure that you have granted either of the following permissions to the Principal provided by Adobe: (For information about granting permissions, see [Add a principal to a bucket-level policy](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in the Google Cloud documentation.)<ul><li>`roles/storage.objectCreator`: Use this permission if you  want to limit the Principal to only create files in your GCP account. </br>**Important:** If you use this permission with scheduled reporting, you must use a unique file name for each new scheduled export. Otherwise, the report generation will fail because the Principal does not have access to overwrite existing files.</li><li>(Recommended) `roles/storage.objectUser`: Use this permission if you want the Principal to have access to view, list, update, and delete files in your GCP account.</br>This permission allows the Principal to overwrite existing files for subsequent uploads, without the need to auto-generate unique file names for each new scheduled export.</li></ul><p>If your organization is using [Organization policy constraints](https://cloud.google.com/storage/docs/org-policy-constraints) to allow only the Google Cloud Platform account in your allow list, you need the following Adobe-owned Google Cloud Platform organization ID: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the GCP location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

1. In the  [!UICONTROL **Data Column Definitions**] section, select the latest [!UICONTROL **All Adobe Columns**] template in the drop-down menu, then complete the following fields:
   
   |Field | Function |
   |---------|----------|
   | [!UICONTROL **Remove escaped characters**] | When collecting data, some characters (such as newlines) can cause issues. Check this box if you would like these characters removed from feed files. |
   | [!UICONTROL **Compression format**] | The type of compression used. **Gzip** outputs files in `.tar.gz` format. **Zip** outputs files in `.zip` format. |
   | [!UICONTROL **Packaging type**] | Select [!UICONTROL **Multiple files**] for most data feeds. This option paginates your data into uncompressed 2GB chunks. (If the [!UICONTROL **Multiple files**] option is selected and uncompressed data for the reporting window is less than 2GB, one file is sent.) Selecting **Single file** outputs the `hit_data.tsv` file in a single, potentially massive file. |
   | [!UICONTROL **Manifest**] | Determines whether Adobe should deliver a [manifest file](c-df-contents/datafeeds-contents.md#feed-manifest) to the destination when no data is collected for a feed interval. If you select **Manifest File**, you receive a manifest file similar to the following when no data is collected:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Column templates**] | When creating many data feeds, Adobe recommends creating a column template. Selecting a column template automatically includes the specified columns in the template. Adobe also provides several templates by default. |
   | [!UICONTROL **Available columns**] | All available data columns in Adobe Analytics. Click [!UICONTROL Add all] to include all columns in a data feed. |
   | [!UICONTROL **Included columns**] | The columns to include in a data feed. Click [!UICONTROL Remove all] to remove all columns from a data feed. |
   | [!UICONTROL **Download CSV**] | Downloads a CSV file containing all included columns. |

1. Select [!UICONTROL **Save**] in the top-right.

    Historical data processing begins immediately. When data finishes processing for a day, the file is sent to the destination that you configured.

    For information about how to access the data feed and to get a better understanding of its contents, see [Data feed contents - overview](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Legacy destinations

>[!IMPORTANT]
>
>The destinations described in this section are legacy, and are not recommended. Instead, use one of the following destinations when creating a data feed: Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS. See [Create and configure a data feed](#create-and-configure-a-data-feed) for detailed information about each of these recommended destinations. 


The following information provides configuration information for each of the legacy destinations:

### FTP

Data feed data can be delivered to an Adobe or customer-hosted FTP location. Requires an FTP host, username, and password. Use the path field to place feed files in a folder. Folders must already exist; feeds throw an error if the specified path does not exist.

Use the following information when completing the available fields:

* [!UICONTROL **Host**]: Enter the desired FTP destination URL. For example, `ftp://ftp.omniture.com`.
* [!UICONTROL **Path**]: Can be left blank
* [!UICONTROL **Username**]: Enter the username to log in to the FTP site.
* [!UICONTROL **Password and confirm password**]: Enter the password to log in to the FTP site.

### SFTP

SFTP support for data feeds is available. Requires an SFTP host, username, and the destination site to contain a valid RSA or DSA public key. You can download the appropriate public key when creating the feed.

### S3

You can send feeds directly to Amazon S3 buckets. This destination type requires a Bucket name, an Access Key ID, and a Secret Key. See [Amazon S3 bucket naming requirements](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) within the Amazon S3 docs for more information.

The user you provide for uploading data feeds must have the following [permissions](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >For each upload to an Amazon S3 bucket, [!DNL Analytics] adds the bucket owner to the BucketOwnerFullControl ACL, regardless of whether the bucket has a policy that requires it. For more information, see "[What is the BucketOwnerFullControl setting for Amazon S3 data feeds?](df-faq.md#BucketOwnerFullControl)"

The following 16 standard AWS regions are supported (using the appropriate signature algorithm where necessary):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>The cn-north-1 region is not supported.

### Azure Blob

Data feeds support Azure Blob destinations. Requires a container, account, and a key. Amazon automatically encrypts the data at rest. When you download the data, it gets decrypted automatically. See [Create a storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) within the Microsoft Azure docs for more information.

>[!NOTE]
>
>You must implement your own process to manage disk space on the feed destination. Adobe does not delete any data from the server.

-->
