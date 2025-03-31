---
title: Descubra cómo administrar conexiones en Customer Journey Analytics
description: Describe cómo administrar conexiones a conjuntos de datos de Experience Platform en Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 7f2f2fc92c188c4cdfba7d87b7b64458daf2f0a6
workflow-type: tm+mt
source-wordcount: '4143'
ht-degree: 25%

---

# Administrar conexiones

Una vez que haya [creado o editado una o más conexiones](/help/connections/create-connection.md), puede administrarlas en **[!UICONTROL Conexiones]**. Las conexiones le permiten:

* Vea todas las conexiones de un vistazo, incluido el propietario, el entorno de pruebas y cuándo se crearon y modificaron las conexiones.
* Editar una conexión.
* Eliminar una conexión.
* Crear una vista de datos a partir de una conexión.
* Ver todos los conjuntos de datos de una conexión.
* Compruebe el estado de los conjuntos de datos de la conexión y el estado del proceso de ingesta. Por ejemplo, ¿cuándo están disponibles los datos para que pueda empezar con los informes y análisis en Analysis Workspace?
* Identifique cualquier discrepancia en los datos debido a una configuración incorrecta. ¿Le faltan filas? En caso afirmativo, ¿qué filas faltan y por qué? ¿Configuró incorrectamente las conexiones y esto causó la falta de datos en Customer Journey Analytics?
* Obtenga información sobre el uso de filas ingeridas y notificables en todas las conexiones.

[!UICONTROL Conexiones] tiene dos interfaces: [[!UICONTROL Lista]](#list) y [[!UICONTROL Uso]](#usage).


## Lista

La interfaz [!UICONTROL List] es la interfaz predeterminada para Conexiones. Si no está seleccionada, seleccione la ficha **[!UICONTROL Lista]** para tener acceso a la interfaz.

![vista de lista](assets/list-view.png)

La interfaz [!UICONTROL List] muestra una tabla de todas las conexiones disponibles. Puede buscar rápidamente una conexión usando el cuadro Buscar ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

En la tabla están disponibles las siguientes columnas o iconos.

| Columna o icono | Descripción |
| --- | --- |
| [!UICONTROL Nombre] | Nombre descriptivo de la conexión. Para ver los detalles de la conexión, seleccione el nombre del hipervínculo. Ver [detalles de conexión](#connection-details). |
| ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para ver información sobre [!UICONTROL Conjuntos de datos incluidos], [!UICONTROL espacio aislado], [!UICONTROL Propietario] y más, seleccione ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) junto al nombre de la conexión.<p>Una ventana emergente muestra detalles. <p><img src="./assets/conn-info.png" alt="Ver información de conexión" width="400"/> |
| ![Vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Para [crear una vista de datos](#create-a-data-view) para la conexión, seleccione ![Vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Este icono solo se muestra cuando no hay ninguna vista de datos asociada a la conexión. |
| ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleccione ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) para: <p>![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Editar](#edit-a-connection) una conexión.<p>![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Eliminar](#delete-a-connection) una conexión.<p>![Vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Crear nueva vista de datos](#create-a-data-view). Para crear vistas de datos adicionales para la conexión. |
| [!UICONTROL Conjuntos de datos] | Uno o más vínculos a los conjuntos de datos que forman parte de la conexión. Puede seleccionar el hipervínculo del conjunto de datos para ver el conjunto de datos en la conexión. Si más conjuntos de datos forman parte de la conexión seleccionada, seleccione **[!UICONTROL +*x* more]** para mostrar el panel **[!UICONTROL Conjuntos de datos incluidos]**. Este panel muestra vínculos a todos los conjuntos de datos y una opción para buscar un conjunto de datos específico que forme parte de la conexión.<p><img src="./assets/datasets-included.png" alt="Datassets incluidos" width="400"/><p>Al seleccionar un nombre de conjunto de datos, se abre el conjunto de datos en la IU de Experience Platform en una nueva pestaña. |
| [!UICONTROL Zona protegida] | La [zona protegida de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/home) desde la que esta conexión obtiene sus conjuntos de datos. Este entorno de pruebas se seleccionó cuando creó la conexión. No se puede modificar. |
| [!UICONTROL Propietario] | La persona que creó la conexión. |
| [!UICONTROL Importar datos nuevos] | Estado de la importación de nuevos datos para conjuntos de datos: <p>![Estado verde](assets/status-green.svg))    **[!UICONTROL _x _en]**para conjuntos de datos configurados para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** para conjuntos de datos no configurados para importar datos nuevos. |
| [!UICONTROL Fecha de creación] | La marca de tiempo cuando se creó la conexión. |
| [!UICONTROL Última modificación] | La marca de tiempo de la última actualización de la conexión. |
| [!UICONTROL Datos de relleno] | El estado para los datos de relleno entre conjuntos de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos entre conjuntos de datos,<p>![Estado naranja](assets/status-orange.svg)   **[!UICONTROL _x _rellenos en procesamiento]**para el número de rellenos en procesamiento entre conjuntos de datos,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados para los conjuntos de datos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se definan rellenos para los conjuntos de datos de la conexión. |

Para configurar qué columnas mostrar, seleccione ![Configuración de columna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), que muestra el cuadro de diálogo **Personalizar tabla** que le permite activar o desactivar columnas en la tabla.

### Edición de una conexión

1. Seleccione ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) junto al nombre de la conexión
1. Seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** en el menú contextual.

Como alternativa, puede:

1. Seleccione la fila de conexión.

1. Seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** de la barra azul.

Al editar una conexión, puede:

* Iniciar y detener la importación de nuevos datos.
* Cambiar el nombre de una conexión.
* Actualice los conjuntos de datos.
* Elimine los conjuntos de datos de las conexiones.

Consulte [Crear o editar una conexión](create-connection.md) para obtener más información.


### Eliminar una conexión {#connections-delete}

1. Seleccione ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) junto al nombre de la conexión.
1. Seleccione ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]**.

Como alternativa, puede:

1. Seleccione la fila de conexión.

1. Seleccione ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]** de la barra azul.

Al eliminar una conexión, un panel **[!UICONTROL Eliminar conexión]** indica qué vistas de datos se eliminan y qué proyectos de Workspace se ven afectados.

![Eliminar conexión](assets/delete-connection.png)

Seleccione **[!UICONTROL Continuar]** para eliminar la conexión.

Consulte [Implicaciones de eliminación](/help/technotes/deletion.md) para obtener más información sobre cómo eliminar una conexión.


### Creación de una vista de datos para una conexión

* Si no hay ninguna vista de datos asociada a la conexión:

   1. Seleccione ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) junto al nombre de la conexión.

* Si ya se han creado una o más vistas de datos para la conexión:

   1. Seleccione ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) junto al nombre de la conexión.
   1. Seleccione ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear nueva vista de datos]**.

Como alternativa, puede:

1. Seleccione la fila de conexión.

1. Seleccione ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear vista de datos]** desde la barra de botones azul.

Consulte [Creación o edición de una vista de datos](/help/data-views/create-dataview.md) para obtener más información.

### Detalles de conexión {#connection-detail}

Para ir a los detalles de una conexión, seleccione un nombre de conexión en la tabla de conexiones.

![Ventana de todos los conjuntos de datos que muestra los widgets y la configuración](assets/conn-details.png)

La interfaz de detalles Conexiones proporciona una vista detallada del estado de una conexión. Puedes realizar lo siguiente:

* Compruebe el estado de los conjuntos de datos de la conexión y del proceso de ingesta.
* Identifique los problemas de configuración que pueden provocar registros omitidos o eliminados.
* Ver cuándo están disponibles los datos para los informes.

| Interfaz de usuario | Descripción |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Editar conexión] | Para editar los detalles de una conexión, seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexión]**. Consulte [Crear o editar una conexión](create-connection.md) para obtener más información. |
| Selector de conjunto de datos | Permite seleccionar uno o todos los conjuntos de datos de la conexión. No puede seleccionar conjuntos de datos múltiples. El valor predeterminado es [!UICONTROL Todos los conjuntos de datos]. |
| Selector de intervalo de fechas | Edite la fecha de inicio, la fecha de finalización o seleccione ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) para abrir el selector de intervalo de fechas. En el selector de intervalo de fechas, seleccione un intervalo de fechas utilizando uno de los períodos predefinidos (por ejemplo **[!UICONTROL Últimos 6 meses]**) o utilice el calendario para seleccionar las fechas de inicio y finalización. Seleccione **[!UICONTROL Aplicar]** para aplicar el nuevo intervalo de fechas. |
| [!UICONTROL Registros de datos de eventos disponibles] | Número total de filas del conjunto de datos de evento disponibles para el sistema de informes, **para toda la conexión**. Este recuento es independiente de cualquier configuración de calendario. El recuento cambia si selecciona un conjunto de datos del selector de conjuntos de datos o en la tabla. Una vez añadidos los datos, existe una latencia de una a dos horas para que los datos aparezcan en los informes. |
| [!UICONTROL Métricas] | Resuma los registros de evento, búsqueda, perfil y conjunto de datos de resumen que se agregan, omiten y eliminan, y el número de lotes agregados. Estas métricas se basan en **el conjunto de datos y el intervalo de fechas que ha seleccionado**.<p>Seleccione **[!UICONTROL Comprobar detalles]** para mostrar la ventana emergente **[!UICONTROL Comprobar detalles omitidos]**. La ventana emergente enumera el número de registros omitidos y el motivo de todos los conjuntos de datos de evento o conjuntos de datos seleccionados.<p><img src="./assets/skipped-records.png" width="500"/><p>Seleccione la ventana emergente ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) con más información. Por algunas razones omitidas, como [!UICONTROL ID de visitante vacío], la ventana emergente muestra PSQL de muestra para EQS (Experience Platform para Query Service) que puede usar en [Query Service](https://experienceleague.adobe.com/es/docs/experience-platform/query/home) para consultar los registros omitidos en el conjunto de datos. Seleccione ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copiar PSQL de muestra para EQS]** para copiar el SQL. |
| [!UICONTROL Registros añadidos] | Indica cuántas filas se añadieron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Se actualiza cada diez minutos. |
| [!UICONTROL Registros omitidos] | Indica cuántas filas se omitieron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Los motivos por los que se omiten registros son: faltan marcas de hora, falta ID de persona o no es válido, etc. Se actualiza cada diez minutos. <p>ID de persona no válidos (como `undefined` o `00000000`, o cualquier combinación de números y letras en un [!UICONTROL ID de persona] que aparecen en un evento más de 1 millón de veces en un mes determinado) son ID que no se pueden atribuir a ningún usuario o persona en particular. Estas filas no se pueden ingerir en el sistema, y conlleva a la creación de informes e ingestas propensas a errores. Para corregir ID de persona no válidos, tiene tres opciones:<ul><li>Use [Configuración](/help/stitching/overview.md) para rellenar los identificadores de usuario sin definir o todos cero con identificadores de usuario válidos.</li><li>Vacíe el ID de usuario, que luego se omiten durante la ingesta (preferible a los ID de usuario no válidos o todos cero).</li><li>Corrija cualquier ID de usuario no válido en el sistema antes de ingerir los datos.</li></ul> |
| [!UICONTROL Registros] eliminados | Indica cuántas filas se eliminaron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Alguien podría haber eliminado un conjunto de datos en [!DNL Experience Platform], por ejemplo. Se actualiza cada diez minutos.<p>En algunos casos, este valor también puede incluir registros reemplazados, como con la vinculación o algunas actualizaciones del conjunto de datos de búsqueda. Consideremos este ejemplo:</p><ul><li>Se carga un registro en un conjunto de datos de perfil individual de XDM, que Customer Journey Analytics está configurado para introducir como datos de búsqueda de perfil. En los detalles de la conexión, este conjunto de datos mostraría 1 registro añadido.</li><li>Puede cargar un duplicado del registro original en el mismo conjunto de datos de AEP, que ahora contiene dos registros. Customer Journey Analytics ingiere el registro adicional del conjunto de datos de búsqueda de perfiles. Al ver que ya ha introducido un registro de perfil en la conexión para ese ID de persona, Customer Journey Analytics elimina su versión anterior y agrega los nuevos datos de perfil. En los detalles de la conexión, esta acción representaría 1 registro añadido y 1 registro eliminado, ya que Customer Journey Analytics solo conserva los datos de búsqueda de perfil más recientes para cualquier ID de persona introducido.</li><li>En total, el conjunto de datos de AEP contiene dos registros que son idénticos. Por otro lado, los detalles de conexión de Customer Journey Analytics muestran el estado de sus datos ingeridos: 2 registros añadidos y 1 registro eliminado para este conjunto de datos de perfil. </li></ul> |
| ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Buscar nombre o ID del conjunto de datos_ | Campo de búsqueda de conjunto de datos. Puede buscar en la tabla de conjuntos de datos por nombre de conjunto de datos o [!UICONTROL ID de conjunto de datos]. |
| [!UICONTROL Tabla de conjuntos de datos] | Los conjuntos de datos que forman parte de la conexión. |
| [!UICONTROL Conjuntos de datos] | Nombre del conjunto de datos que forma parte de la conexión. Puede seleccionar el hipervínculo para abrir el conjunto de datos en la interfaz de usuario de Experience Platform en una nueva pestaña. Puede seleccionar la fila o la casilla de verificación para mostrar solo los detalles del conjunto de datos seleccionado. |
| [!UICONTROL ID de conjunto de datos] | Generado automáticamente por Experience Platform. |
| [!UICONTROL Registros añadidos] | El número de registros del conjunto de datos (filas) agregados a una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Registros omitidos] | El número de registros del conjunto de datos (filas) omitidos durante la transferencia de datos para una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Registros eliminados] | El número de registros del conjunto de datos (filas) quitados de una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Lotes añadidos] | El número de lotes de conjuntos de datos que se han agregado a una conexión. |
| [!UICONTROL Última incorporación] | La marca de tiempo del último lote del conjunto de datos que se ha agregado a una conexión. |
| [!UICONTROL Tipo de fuente de datos] | El tipo de origen del conjunto de datos. El tipo de origen se define al crear una conexión. |
| [!UICONTROL Tipo de conjunto de datos] | El tipo de conjunto de datos para este conjunto de datos. El tipo puede ser [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup] o [!UICONTROL Summary]. [Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| Esquema | El esquema de Experience Platform en el que se basa el conjunto de datos. |
| [!UICONTROL Importar datos nuevos] | Estado de importación de nuevos datos para el conjunto de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**si el conjunto de datos está configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** si el conjunto de datos está configurado para no importar nueva importación de datos. |
| [!UICONTROL Transformar datos] | El estado de transformación de los conjuntos de datos de consulta B2B aplicables. Consulte [Transformación de conjuntos de datos para búsquedas B2B](transform-datasets-b2b-lookups.md) para obtener más información.<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**para conjuntos de datos aplicables habilitados para transformación, <p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** para conjuntos de datos aplicables no habilitados para transformación, y<p>**[!UICONTROL N/A]** para todos los demás conjuntos de datos, no aplicable para la transformación. |
| [!UICONTROL Datos de relleno] | El estado de los datos de relleno del conjunto de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos procesando]**para el número de rellenos procesados,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se hayan configurado los rellenos. |
| [!UICONTROL Importar datos nuevos] | Estado de importación de nuevos datos para el conjunto de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**si el conjunto de datos está configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** si el conjunto de datos está configurado para no importar datos nuevos. |
| [!UICONTROL Datos de relleno] | El estado de los datos de relleno del conjunto de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos procesando]**para el número de rellenos procesados,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se hayan configurado rellenos. |

>[!IMPORTANT]
>
>Los datos introducidos antes del 13 de agosto de 2021 no se reflejan en la interfaz [!UICONTROL Connections].

#### Panel de conexión

Cuando no se selecciona ningún conjunto de datos en la tabla de conjuntos de datos, un panel a la derecha de la interfaz Conexiones muestra las opciones y los detalles de la conexión.

| Opciones | Descripción |
| --- | --- |
| ![Actualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Actualizar] | Para actualizar la conexión y permitir que se reflejen los registros agregados recientemente, seleccione ![Actualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualizar]**. |
| ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]** | [Eliminar](#delete-a-connection) esta conexión. |
| ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear vista de datos]** | [Crear una vista de datos](#create-a-data-view) basada en esta conexión. Consulte [Vistas de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) para obtener más información. |
| [!UICONTROL Nombre de la conexión] | Nombre descriptivo de la conexión. |
| [!UICONTROL Descripción de la conexión] | Una descripción más detallada que describe el propósito de esta conexión. |
| [!UICONTROL Zona protegida] | La [zona protegida de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/home) desde la que esta conexión obtiene sus conjuntos de datos. Este entorno de pruebas se seleccionó la primera vez que creó la conexión. No se puede modificar. |
| [!UICONTROL ID de conexión] | Este ID se genera en Experience Platform. Puede usar ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar el ID. |
| [!UICONTROL Vistas de datos mediante conexión] | Enumera todas las vistas de datos que utilizan esta conexión. |
| [!UICONTROL Importar datos nuevos] | Estado de la importación de nuevos datos para conjuntos de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**para cuántos conjuntos de datos se han configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** para cuántos conjuntos de datos está desactivada la importación de datos nuevos. |
| [!UICONTROL Datos de relleno] | El estado de los datos de relleno para los conjuntos de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos entre conjuntos de datos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos en procesamiento]**para el número de rellenos en procesamiento entre conjuntos de datos,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados para los conjuntos de datos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se definan rellenos para los conjuntos de datos de la conexión. |
| Transformar datos | El estado de transformación de los conjuntos de datos de consulta B2B aplicables. Consulte [Transformación de conjuntos de datos para búsquedas B2B](transform-datasets-b2b-lookups.md) para obtener más información.<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**para el número de conjuntos de datos habilitados para la transformación. |
| [!UICONTROL Creado por] | Nombre de la persona que creó la conexión. |
| [!UICONTROL Última modificación] | La marca de tiempo del último cambio en la conexión. |
| [!UICONTROL Última modificación de:] | La persona que modificó la conexión por última vez. |

#### Panel Conjunto de datos

Cuando se selecciona un conjunto de datos en la tabla de conjuntos de datos, un panel a la derecha de la interfaz Conexiones muestra detalles del conjunto de datos seleccionado.

| Detalles | Descripción |
| --- | --- |
| [!UICONTROL ID de la persona] | Identidad definida en el esquema del conjunto de datos en Experience Platform. Esta identidad es el ID de persona que seleccionó durante la creación de la conexión. Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar conjuntos de datos, debe utilizar el mismo ID de persona en ellos. |
| [!UICONTROL Clave] | La clave que ha especificado para un conjunto de datos de búsqueda. |
| [!UICONTROL Clave de coincidencia] | La clave coincidente que ha especificado para un conjunto de datos de búsqueda. |
| [!UICONTROL Marca de tiempo] | La marca de tiempo definida para un conjunto de datos de evento. |
| [!UICONTROL Registros disponibles] | El número total de filas ingeridas para este conjunto de datos, para el período de tiempo particular seleccionado a través del calendario. Una vez añadidos, no hay latencia en cuanto a la aparición de datos en los informes. Sin embargo, cuando crea una conexión completamente nueva, hay [latencia](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| [!UICONTROL Registros añadidos] | Cantidad de filas añadidas en el período de tiempo seleccionado. |
| [!UICONTROL Registros eliminados] | Cuántos registros se eliminaron durante el período de tiempo seleccionado. |
| [!UICONTROL Lotes añadidos] | Cuántos lotes de datos se añadieron a este conjunto de datos. |
| [!UICONTROL Registros omitidos] | Cuántas filas se omitieron durante la ingesta en el período de tiempo seleccionado.<p>Los motivos por los que se omiten registros son: faltan marcas de hora, falta ID de persona o no es válido, etc. Se actualiza cada diez minutos.<p>ID de persona no válidos (como `undefined` o `00000000`, o cualquier combinación de números y letras en un [!UICONTROL ID de persona] que aparece en un evento más de 1 millón de veces en un mes determinado) son ID que no se pueden atribuir a ningún usuario o persona en particular. Estas filas no se pueden ingerir en el sistema, y conlleva a la creación de informes e ingestas propensas a errores. Para corregir ID de persona no válidos, tiene tres opciones:<ul><li>Use [Configuración](/help/stitching/overview.md) para rellenar los identificadores de usuario sin definir o todos cero con identificadores de usuario válidos.</li><li>Vacíe el ID de usuario, que luego se omitirá durante la ingesta (preferible a los ID de usuario no válidos o todos cero).</li><li>Corrija cualquier ID de usuario no válido en el sistema antes de ingerir los datos.</li></ul> |
| [!UICONTROL Última incorporación] | La marca de tiempo del último lote añadido. |
| [!UICONTROL Importar datos nuevos] | Estado de importación de nuevos datos para el conjunto de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**si el conjunto de datos está configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** si el conjunto de datos está configurado para no importar datos nuevos. |
| [!UICONTROL Datos de relleno] | El estado de los datos de relleno del conjunto de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos procesando]**para el número de rellenos procesados,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se hayan configurado rellenos.<p>Para mostrar un cuadro de diálogo con una descripción general de los rellenos anteriores para el conjunto de datos, seleccione <img src="./assets/pastbackfill.svg" alt="Rellenos anteriores" width="15"/> **[!UICONTROL Rellenos anteriores]**. |
| [!UICONTROL Tipo de fuente de datos] | Tipo de origen de datos definido al agregar el conjunto de datos a la conexión. |
| [!UICONTROL Tipo de conjunto de datos] | [!UICONTROL Evento], [!UICONTROL Perfil], [!UICONTROL Búsqueda] o [!UICONTROL Resumen]. [Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL Esquema] | El esquema de Experience Platform en el que se basa este conjunto de datos. |
| [!UICONTROL ID de conjunto de datos] | Este ID de conjunto de datos se genera en Experience Platform. |


## Uso {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Métricas de uso clave"
>abstract="Proporcione datos mensuales y totales para las filas principales e históricas notificables."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Filas introducidas mensualmente"
>abstract="Mide el número total de registros añadidos al sistema cada mes para proporcionar información sobre el crecimiento de los datos y las tasas de ingesta."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Filas mensuales notificables"
>abstract="Realiza el seguimiento del número de filas disponibles para la creación de informes. Las filas notificables son las filas introducidas menos las filas que se omiten y eliminan durante la ingesta. Las filas notificables sirven como métrica clave para la facturación y el uso de datos."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Desglose detallado."
>abstract="Puede ver métricas detalladas por conexión, conjunto de datos, zona protegida y etiquetas, con la opción de descargar un archivo CSV de los datos."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Otros conjuntos de datos"
>abstract="Para los meses anteriores a septiembre de 2024, los datos se recopilaron en el nivel de conjunto de datos y se muestran como *Otros conjuntos de datos* para una mayor claridad. A partir de septiembre de 2024, los datos se recopilan en un nivel de conjunto de datos granular y *Otros conjuntos de datos* dejan de aparecer."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Conjuntos de datos o conexiones desconocidos"
>abstract="Los conjuntos de datos o conexiones desconocidos se muestran con sus ID."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Datos no disponibles"
>abstract="Los datos históricos anteriores a septiembre de 2024 no están disponibles debido a limitaciones del sistema. Las métricas se recopilan y muestran a partir de septiembre de 2024. El gráfico muestra los últimos 18 meses en la cronología y los datos futuros aparecerán a medida que los datos estén disponibles."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Filas principales notificables"
>abstract="Muestra el número total de filas disponibles durante los últimos 13 meses. Por ejemplo, el 1 de febrero de 2024, el número muestra el total de filas disponibles con una marca de tiempo de evento de enero de 2023 a enero de 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Filas históricas notificables"
>abstract="Muestra el número total de filas disponibles para el período anterior a 13 meses. Por ejemplo, el 1 de febrero de 2024, el número muestra el total de filas disponibles con una marca de tiempo de evento anterior a enero de 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Métricas de uso clave"
>abstract="Proporcione datos mensuales y totales para las filas principales e históricas notificables."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Filas introducidas mensualmente"
>abstract="Mide el número total de registros añadidos al sistema cada mes para proporcionar información sobre el crecimiento de los datos y las tasas de ingesta."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Filas mensuales notificables"
>abstract="Realiza el seguimiento del número de filas disponibles para la creación de informes. Las filas notificables son las filas introducidas menos las filas que se omiten y eliminan durante la ingesta. Las filas notificables sirven como métrica clave para la facturación y el uso de datos."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Desglose detallado."
>abstract="Puede ver métricas detalladas por conexión, conjunto de datos, zona protegida y etiquetas, con la opción de descargar un archivo CSV de los datos."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Otros conjuntos de datos"
>abstract="Para los meses anteriores a septiembre de 2024, los datos se recopilaron en el nivel de conjunto de datos y se muestran como *Otros conjuntos de datos* para una mayor claridad. A partir de septiembre de 2024, los datos se recopilan en un nivel de conjunto de datos granular y *Otros conjuntos de datos* dejan de aparecer."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Conjuntos de datos o conexiones desconocidos"
>abstract="Los conjuntos de datos o conexiones desconocidos se muestran con sus ID."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Datos no disponibles"
>abstract="Los datos históricos anteriores a septiembre de 2024 no están disponibles debido a limitaciones del sistema. Las métricas se recopilan y muestran a partir de septiembre de 2024. El gráfico muestra los últimos 18 meses en la cronología y los datos futuros aparecerán a medida que los datos estén disponibles."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Filas principales notificables"
>abstract="Muestra el número total de filas disponibles durante los últimos 13 meses. Por ejemplo, el 1 de febrero de 2024, el número muestra el total de filas disponibles con una marca de tiempo de evento de enero de 2023 a enero de 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Filas históricas notificables"
>abstract="Muestra el número total de filas disponibles para el período anterior a 13 meses. Por ejemplo, el 1 de febrero de 2024, el número muestra el total de filas disponibles con una marca de tiempo de evento anterior a enero de 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Filas principales notificables"
>abstract="Las filas principales sobre las que se puede informar son valores de instantánea, no totales agregados. Estos valores se actualizan dinámicamente en función del último mes del intervalo de fechas seleccionado. Si un cliente selecciona de enero a marzo, los valores reflejarán la instantánea de marzo."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Filas históricas notificables"
>abstract="Las filas históricas de las que se puede realizar un informe son valores instantáneos, no totales agregados. Estos valores se actualizan dinámicamente en función del último mes del intervalo de fechas seleccionado. Si un cliente selecciona de enero a marzo, los valores reflejarán la instantánea de marzo."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Filas acumulativas disponibles para creación de informes"
>abstract="Las filas acumulativas sobre las que se puede generar informes son valores de instantánea, no totales agregados. Estos valores se actualizan dinámicamente en función del último mes del intervalo de fechas seleccionado. Si un cliente selecciona de enero a marzo, los valores reflejarán la instantánea de marzo."

<!-- markdownlint-enable MD034 -->



La interfaz [!UICONTROL Uso] muestra el uso de filas ingeridas y notificables en todas las conexiones. Si no está seleccionado, seleccione la ficha **[!UICONTROL Uso]** para tener acceso a la interfaz.

Esta interfaz le permite determinar si el uso de Customer Journey Analytics cumple con lo acordado contractualmente. Además de supervisar, puede utilizar la interfaz de uso para planificar la renovación de su licencia de Customer Journey Analytics.

La interfaz de uso utiliza las siguientes métricas

| Nombre de la métrica | Descripción |
|---|---|
| Filas históricas notificables | Recuento de filas para el periodo superior a 13 meses. |
| Filas principales notificables | Recuento de filas en los últimos 13 meses. |
| Filas ingeridas | Cantidad de filas introducidas para el periodo específico. |
| Filas notificables | ¿Cuántas filas de datos tiene como parte de la conexión durante el período específico? |
| Filas acumuladas | Cuántas filas se incorporan hasta el mes específico. |

>[!NOTE]
>
>A partir de julio de 2024, se recopilan los datos de los registros principal, histórico y total. Póngase en contacto con el administrador de su cuenta para obtener datos históricos anteriores.
>



La interfaz de uso consta de dos paneles:

* Panel **[!UICONTROL Métricas de uso de claves]**: proporciona filas de informes de datos principales e históricos. El panel también realiza un seguimiento de los cambios porcentuales en comparación con el mes anterior, tanto para las filas de datos principales como para las históricas.

  El panel se muestra en una visualización:

   * **[!UICONTROL Filas de datos principales de las que se puede informar]**.

     ¿Cuántas filas notificables ha tenido en los últimos 13 meses? El número de resumen es el número de filas principales sobre las que se puede realizar informes (por ejemplo, 741M) en el último mes (por ejemplo, diciembre de 2024).

   * **[!UICONTROL Filas de datos históricos para notificar]**.

     ¿Cuántas filas notificables tiene para el período anterior a 13 meses? El número de resumen es el número de filas históricas de las que se puede realizar un informe (por ejemplo, 127 millones) en el último mes (por ejemplo, diciembre de 2024).

  Cuando pasa el ratón sobre cualquier barra apilada de la visualización, una ventana emergente muestra el número de filas de esa parte específica de la barra (por ejemplo).


  ![Métricas de uso de claves](assets/usage-key-usage-metrics.png)

* Un panel combinado que muestra tres subpaneles para:

+++ Filas ingeridas

  El subpanel **[!UICONTROL Filas ingeridas]** mide el número total de registros agregados al sistema cada mes, lo que proporciona una perspectiva del crecimiento de los datos y las tasas de ingesta. El subpanel proporciona un resumen del total de filas introducidas de este mes y el cambio con respecto al mes anterior.

  ![Filas ingeridas](assets/usage-ingested-rows.png)

  Puede situarse sobre los puntos de datos en la visualización para mostrar una ventana emergente con más detalles.

+++

+++ Filas notificables

  La visualización de **[!UICONTROL filas reportables]** realiza un seguimiento del número de filas disponibles para el sistema de informes al restar las filas omitidas y eliminadas de las filas ingeridas, lo que sirve como métrica clave para la facturación y el uso de datos. El subpanel proporciona dos resúmenes:

   * **[!UICONTROL Total del último mes]**: Un resumen del total de filas sobre las que se debe informar hasta este mes.
   * **[!UICONTROL Este mes]**: Un resumen del total de filas de este mes sobre las que se puede realizar un informe y el cambio con respecto al mes anterior.

  ![Filas transportables](assets/usage-reportable-rows.png)

  Puede situarse sobre los puntos de datos en las visualizaciones para mostrar una ventana emergente con más detalles.

+++

+++ Desglose de detalles

  Puede usar la tabla **[!UICONTROL Detalle del desglose]** para ver las métricas detalladas por conexión, conjunto de datos, zona protegida y etiquetas. Los conjuntos de datos se comunican utilizando ID en lugar de nombres, ya que los nombres de los conjuntos de datos se pueden modificar durante un período de informe. Se informa de conjuntos de datos o conexiones desconocidos mediante identificadores.

  Para los meses anteriores a septiembre de 2024, los datos se recopilaron en el nivel de conjunto de datos y se muestran como [!UICONTROL Otros conjuntos de datos] para una mayor claridad. A partir de septiembre de 2024, los datos se recopilarán en un nivel de conjunto de datos granular y [!UICONTROL Otros conjuntos de datos] ya no aparecerá.

   * Para cambiar el desglose, selecciona una combinación para **[!UICONTROL Ver por]** y **[!UICONTROL Desglosar por]**.

     | **[!UICONTROL Ver por]** opciones | **[!UICONTROL Desglose por]** opciones |
     |---|---|
     | **[!UICONTROL Conexión]** | **[!UICONTROL -]** y **[!UICONTROL Conjunto de datos]** |
     | **[!UICONTROL Conjunto de datos]** | **[!UICONTROL -]** |
     | **[!UICONTROL Zona protegida]** | **[!UICONTROL Conexión]** |
     | **[!UICONTROL Etiqueta]** | **[!UICONTROL Conexión]** |

  ![Desglose por detalle](assets/usage-detail-breakdown.png)

+++

  Puede definir un **[!UICONTROL intervalo de tiempo]** en meses para generar el informe. Use ![Calendario](/help/assets/icons/Calendar.svg) para seleccionar el intervalo de tiempo.

>[!MORELIKETHIS]
>
>[Ver, solucionar problemas y modificar la configuración de conexión](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) tutorial.
