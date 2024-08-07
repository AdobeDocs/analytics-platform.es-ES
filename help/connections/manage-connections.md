---
title: Descubra cómo administrar conexiones en Customer Journey Analytics
description: Describe cómo administrar conexiones a conjuntos de datos de Experience Platform en Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: c0599526e6a6a9ac9788a4ce29bcf44256b6c4df
workflow-type: tm+mt
source-wordcount: '3277'
ht-degree: 14%

---

# Administrar conexiones

Una vez que haya [creado o editado una o más conexiones](/help/connections/create-connection.md), puede administrarlas en **[!UICONTROL Conexiones]**. Las conexiones le permiten:

* Vea todas las conexiones de un vistazo, incluido el propietario, el entorno de pruebas y cuándo se crearon y modificaron las conexiones.
* Editar una conexión.
* Eliminar una conexión.
* Crear una vista de datos a partir de una conexión.
* Ver todos los conjuntos de datos de una conexión.
* Compruebe el estado de los conjuntos de datos de la conexión y el estado del proceso de ingesta. Por ejemplo, ¿cuándo están disponibles los datos para que pueda empezar con los informes y análisis en Analysis Workspace?
* Identifique cualquier discrepancia en los datos debido a una configuración incorrecta. ¿Le faltan filas? En caso afirmativo, ¿qué filas faltan y por qué? ¿Configuró incorrectamente las conexiones y esto causó la falta de datos en el Customer Journey Analytics?
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
| [!UICONTROL Conjuntos de datos] | Muestra uno o más vínculos a los conjuntos de datos que forman parte de la conexión. Puede seleccionar el hipervínculo del conjunto de datos para ver el conjunto de datos en la conexión. Si más conjuntos de datos forman parte de la conexión seleccionada, seleccione **[!UICONTROL +*x* more]** para mostrar el panel **[!UICONTROL Conjuntos de datos incluidos]**. Este panel muestra vínculos a todos los conjuntos de datos y una opción para buscar un conjunto de datos específico que forme parte de la conexión.<p><img src="./assets/datasets-included.png" alt="Datassets incluidos" width="400"/><p>Al seleccionar un nombre de conjunto de datos, se abre el conjunto de datos en la IU del Experience Platform en una nueva pestaña. |
| [!UICONTROL Zona protegida] | Muestra la zona protegida de [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) desde la que esta conexión obtiene sus conjuntos de datos. Este entorno de pruebas se seleccionó cuando creó la conexión. No se puede modificar. |
| [!UICONTROL Propietario] | La persona que creó la conexión. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para conjuntos de datos: <p>![Estado verde](assets/status-green.svg))    **[!UICONTROL _x _en]**para conjuntos de datos configurados para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** para conjuntos de datos no configurados para importar datos nuevos. |
| [!UICONTROL Fecha de creación] | La marca de tiempo cuando se creó la conexión. |
| [!UICONTROL Última modificación] | La marca de tiempo de la última actualización de la conexión. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno entre conjuntos de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos entre conjuntos de datos,<p>![Estado naranja](assets/status-orange.svg)   **[!UICONTROL _x _rellenos en procesamiento]**para el número de rellenos en procesamiento entre conjuntos de datos,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados para los conjuntos de datos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se definan rellenos para los conjuntos de datos de la conexión. |

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

La interfaz de detalles Conexiones proporciona una vista detallada del estado de una conexión. Puede realizar lo siguiente:

* Compruebe el estado de los conjuntos de datos de la conexión y del proceso de ingesta.
* Identifique los problemas de configuración que pueden provocar registros omitidos o eliminados.
* Ver cuándo están disponibles los datos para los informes.

| Interfaz de usuario | Descripción |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Editar conexión] | Para editar los detalles de una conexión, seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexión]**. Consulte [Crear o editar una conexión](create-connection.md) para obtener más información. |
| Selector de conjunto de datos | Permite seleccionar uno o todos los conjuntos de datos de la conexión. No puede seleccionar conjuntos de datos múltiples. El valor predeterminado es [!UICONTROL Todos los conjuntos de datos]. |
| Selector de intervalo de fechas | Edite la fecha de inicio o de finalización, o bien seleccione ![Calendario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) para abrir el selector de intervalo de datos. En el selector de intervalo de fechas, seleccione un intervalo de fechas utilizando uno de los períodos predefinidos (por ejemplo **[!UICONTROL Últimos 6 meses]**) o utilice el calendario para seleccionar las fechas de inicio y finalización. Seleccione **[!UICONTROL Aplicar]** para aplicar el nuevo intervalo de datos. |
| [!UICONTROL Registros de datos de eventos disponibles] | Número total de filas del conjunto de datos de evento disponibles para el sistema de informes, **para toda la conexión**. Este recuento es independiente de cualquier configuración de calendario. El recuento cambia si selecciona un conjunto de datos del selector de conjuntos de datos o en la tabla. Una vez añadidos los datos, existe una latencia de una a dos horas para que los datos aparezcan en los informes. |
| [!UICONTROL Métricas] | Resume los registros de evento, búsqueda y conjunto de datos de perfil que se agregan, omiten y eliminan, y el número de lotes agregados, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**.<p>Seleccione **[!UICONTROL Comprobar detalles]** para mostrar la ventana emergente **[!UICONTROL Comprobar detalles omitidos]**. La ventana emergente enumera el número de registros omitidos y el motivo de todos los conjuntos de datos de evento o conjuntos de datos seleccionados.<p><img src="./assets/skipped-records.png" width="500"/><p>Seleccione la ventana emergente ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) con más información. Por algunas razones omitidas, como [!UICONTROL ID de visitante vacío], la ventana emergente muestra PSQL de muestra para EQS (Experience Platform para el servicio de consultas) que puede usar en [servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=es) para consultar los registros omitidos en el conjunto de datos. Seleccione ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copiar PSQL de muestra para EQS]** para copiar el SQL. |
| [!UICONTROL Registros añadidos] | Indica cuántas filas se añadieron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Se actualiza cada diez minutos. |
| [!UICONTROL Registros omitidos] | Indica cuántas filas se omitieron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Los motivos por los que se omiten registros son: faltan marcas de hora, falta ID de persona o no es válido, etc. Se actualiza cada diez minutos. <p>ID de persona no válidos (como `undefined` o `00000000`, o cualquier combinación de números y letras en un [!UICONTROL ID de persona] que aparece en un evento más de 1 millón de veces en un mes determinado) son ID que no se pueden atribuir a ningún usuario o persona en particular. Estas filas no se pueden ingerir en el sistema, y conlleva a la creación de informes e ingestas propensas a errores. Para corregir ID de persona no válidos, tiene tres opciones:<ul><li>Use [Configuración](/help/stitching/overview.md) para rellenar los identificadores de usuario sin definir o todos cero con identificadores de usuario válidos.</li><li>Vacíe el ID de usuario, que luego se omiten durante la ingesta (preferible a los ID de usuario no válidos o todos cero).</li><li>Corrija cualquier ID de usuario no válido en el sistema antes de ingerir los datos.</li></ul> |
| [!UICONTROL Registros] eliminados | Indica cuántas filas se eliminaron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Alguien podría haber eliminado un conjunto de datos en [!DNL Experience Platform], por ejemplo. Se actualiza cada diez minutos.<p>En algunos casos, este valor también puede incluir registros reemplazados, como con la vinculación o algunas actualizaciones del conjunto de datos de búsqueda. Consideremos este ejemplo:</p><ul><li>Puede cargar un registro a un conjunto de datos de perfil individual de XDM, que CJA está configurado para introducir como datos de búsqueda de perfil. En los detalles de la conexión, este conjunto de datos mostraría 1 registro añadido.</li><li>Puede cargar un duplicado del registro original en el mismo conjunto de datos de AEP, que ahora contiene dos registros. CJA ingiere el registro adicional del conjunto de datos de búsqueda de perfiles. Al ver que ya ha introducido un registro de perfil en la conexión para ese ID de persona, CJA elimina su versión anterior y agrega los nuevos datos de perfil. En los detalles de la conexión, esta acción representaría 1 registro añadido y 1 registro eliminado, ya que CJA solo conserva los datos de búsqueda de perfil más recientes para cualquier ID de persona introducido.</li><li>En total, el conjunto de datos de AEP contiene dos registros que son idénticos. Por separado, los detalles de conexión de CJA muestran el estado de sus datos ingeridos: 2 registros añadidos y 1 registro eliminado para este conjunto de datos de perfil. </li></ul> |
| ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Buscar nombre o ID del conjunto de datos_ | Campo de búsqueda de conjunto de datos. Puede buscar en la tabla de conjuntos de datos por nombre de conjunto de datos o [!UICONTROL ID de conjunto de datos]. |
| [!UICONTROL Tabla de conjuntos de datos] | Muestra los conjuntos de datos que forman parte de la conexión. |
| [!UICONTROL Conjuntos de datos] | Muestra el nombre del conjunto de datos que forma parte de la conexión. Puede seleccionar el hipervínculo para abrir el conjunto de datos en la interfaz de usuario de Experience Platform en una nueva pestaña. Puede seleccionar la fila o la casilla de verificación para mostrar solo los detalles del conjunto de datos seleccionado. |
| [!UICONTROL ID de conjunto de datos] | Generado automáticamente por el Experience Platform. |
| [!UICONTROL Registros añadidos] | El número de registros del conjunto de datos (filas) agregados a una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Registros omitidos] | El número de registros del conjunto de datos (filas) omitidos durante la transferencia de datos para una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Registros eliminados] | El número de registros del conjunto de datos (filas) quitados de una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Lotes añadidos] | El número de lotes de conjuntos de datos que se han agregado a una conexión. |
| [!UICONTROL Última incorporación] | La marca de tiempo del último lote del conjunto de datos que se ha agregado a una conexión. |
| [!UICONTROL Tipo de fuente de datos] | El tipo de origen del conjunto de datos. El tipo de origen se define al crear una conexión. |
| [!UICONTROL Tipo de conjunto de datos] | El tipo de conjunto de datos para este conjunto de datos. El tipo puede ser [!UICONTROL Evento], [!UICONTROL Búsqueda] o [!UICONTROL Perfil]. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#configure-dataset) |
| Esquema | El esquema del Experience Platform en el que se basa el conjunto de datos. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para el conjunto de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**si el conjunto de datos está configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** si el conjunto de datos está configurado para no importar datos nuevos. |
| [!UICONTROL Transformar datos] | Muestra el estado de transformación de los conjuntos de datos de búsqueda B2B aplicables. Consulte [Transformación de conjuntos de datos para búsquedas B2B](transform-datasets-b2b-lookups.md) para obtener más información.<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**para conjuntos de datos aplicables habilitados para transformación, <p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** para conjuntos de datos aplicables no habilitados para transformación, y<p>**[!UICONTROL N/A]** para todos los demás conjuntos de datos, no aplicable para la transformación. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno del conjunto de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos procesando]**para el número de rellenos procesando,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se hayan configurado rellenos. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para el conjunto de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**si el conjunto de datos está configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** si el conjunto de datos está configurado para no importar datos nuevos. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno del conjunto de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos procesando]**para el número de rellenos procesando,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se hayan configurado rellenos. |

>[!IMPORTANT]
>
>Los datos introducidos antes del 13 de agosto de 2021 no se reflejan en la interfaz [!UICONTROL Connections].

#### Panel de conexión

Cuando no se selecciona ningún conjunto de datos en la tabla de conjuntos de datos, un panel a la derecha de la interfaz Conexiones muestra las opciones y los detalles de la conexión.

| Opciones/detalles | Descripción |
| --- | --- |
| ![Actualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Actualizar] | Para actualizar la conexión y permitir que se reflejen los registros agregados recientemente, seleccione ![Actualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualizar]**. |
| ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]** | [Eliminar](#delete-a-connection) esta conexión. |
| ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear vista de datos]** | [Crear una vista de datos](#create-a-data-view) basada en esta conexión. Consulte [Vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es) para obtener más información. |
| [!UICONTROL Nombre de la conexión] | Muestra el nombre descriptivo de la conexión. |
| [!UICONTROL Descripción de la conexión] | Muestra una descripción más detallada que describe el propósito de esta conexión. |
| [!UICONTROL Zona protegida] | La zona protegida [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) desde la que esta conexión obtiene sus conjuntos de datos. Este entorno de pruebas se seleccionó la primera vez que creó la conexión. No se puede modificar. |
| [!UICONTROL ID de conexión] | Este ID se genera en el Experience Platform. Puede usar ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar el ID. |
| [!UICONTROL Vistas de datos mediante conexión] | Enumera todas las vistas de datos que utilizan esta conexión. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para conjuntos de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**para cuántos conjuntos de datos se han configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** para cuántos conjuntos de datos está desactivada la importación de datos nuevos. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno de los conjuntos de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos entre conjuntos de datos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos en procesamiento]**para el número de rellenos en procesamiento entre conjuntos de datos,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados para los conjuntos de datos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se definan rellenos para los conjuntos de datos de la conexión. |
| Transformar datos | Muestra el estado de transformación de los conjuntos de datos de búsqueda B2B aplicables. Consulte [Transformación de conjuntos de datos para búsquedas B2B](transform-datasets-b2b-lookups.md) para obtener más información.<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**para el número de conjuntos de datos habilitados para la transformación. |
| [!UICONTROL Creado por] | Muestra el nombre de la persona que creó la conexión. |
| [!UICONTROL Última modificación] | Muestra la marca de tiempo del último cambio realizado en la conexión. |
| [!UICONTROL Última modificación de:] | Muestra la persona que modificó la conexión por última vez. |

#### Panel Conjunto de datos

Cuando se selecciona un conjunto de datos en la tabla de conjuntos de datos, un panel a la derecha de la interfaz Conexiones muestra detalles del conjunto de datos seleccionado.

| Detalles | Descripción |
| --- | --- |
| [!UICONTROL ID de la persona] | Muestra una identidad que se definió en el esquema del conjunto de datos en Experience Platform. Esta identidad es el ID de persona que seleccionó durante la creación de la conexión. Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar conjuntos de datos, debe utilizar el mismo ID de persona en ellos. |
| [!UICONTROL Clave] | Muestra la clave que ha especificado para un conjunto de datos de búsqueda. |
| [!UICONTROL Clave de coincidencia] | Muestra la clave coincidente que ha especificado para un conjunto de datos de búsqueda. |
| [!UICONTROL Marca de tiempo] | Muestra la marca de tiempo definida para un conjunto de datos de evento. |
| [!UICONTROL Registros disponibles] | Muestra el número total de filas ingeridas para este conjunto de datos, para el período de tiempo particular seleccionado a través del calendario. Una vez añadidos, no hay latencia en cuanto a la aparición de datos en los informes. Sin embargo, cuando crea una conexión completamente nueva, hay [latencia](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Registros añadidos] | Muestra cuántas filas se añadieron en el período de tiempo seleccionado. |
| [!UICONTROL Registros eliminados] | Muestra cuántos registros se eliminaron durante el período de tiempo seleccionado. |
| [!UICONTROL Lotes añadidos] | Muestra cuántos lotes de datos se añadieron a este conjunto de datos. |
| [!UICONTROL Registros omitidos] | Muestra cuántas filas se omitieron durante la ingesta en el período de tiempo seleccionado.<p>Los motivos por los que se omiten registros son: faltan marcas de hora, falta ID de persona o no es válido, etc. Se actualiza cada diez minutos.<p>ID de persona no válidos (como `undefined` o `00000000`, o cualquier combinación de números y letras en un [!UICONTROL ID de persona] que aparece en un evento más de 1 millón de veces en un mes determinado) son ID que no se pueden atribuir a ningún usuario o persona en particular. Estas filas no se pueden ingerir en el sistema, y conlleva a la creación de informes e ingestas propensas a errores. Para corregir ID de persona no válidos, tiene tres opciones:<ul><li>Use [Configuración](/help/stitching/overview.md) para rellenar los identificadores de usuario sin definir o todos cero con identificadores de usuario válidos.</li><li>Vacíe el ID de usuario, que luego se omitirá durante la ingesta (preferible a los ID de usuario no válidos o todos cero).</li><li>Corrija cualquier ID de usuario no válido en el sistema antes de ingerir los datos.</li></ul> |
| [!UICONTROL Última incorporación] | Muestra cuándo se añadió el último lote. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para el conjunto de datos: <p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _en]**si el conjunto de datos está configurado para importar datos nuevos, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _x Desactivado_]** si el conjunto de datos está configurado para no importar datos nuevos. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno del conjunto de datos.<p>![Estado rojo](assets/status-red.svg)   **[!UICONTROL _x _rellenos fallidos]**para el número de rellenos fallidos,<p>![Estado rojo](assets/status-orange.svg)   **[!UICONTROL _x _rellenos procesando]**para el número de rellenos procesando,<p>![Estado verde](assets/status-green.svg)   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p>![Estado gris](assets/status-gray.svg)   **[!UICONTROL _Desactivado_]** en caso de que no se hayan configurado rellenos.<p>Para mostrar un cuadro de diálogo con una descripción general de los rellenos anteriores para el conjunto de datos, seleccione <img src="./assets/pastbackfill.svg" alt="Rellenos anteriores" width="15"/> **[!UICONTROL Rellenos anteriores]**. |
| [!UICONTROL Tipo de fuente de datos] | Tipo de origen de datos definido al agregar el conjunto de datos a la conexión. |
| [!UICONTROL Tipo de conjunto de datos] | [!UICONTROL Evento], [!UICONTROL Búsqueda] o [!UICONTROL Perfil]. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#configure-dataset) |
| [!UICONTROL Esquema] | Muestra el esquema del Experience Platform en el que se basa este conjunto de datos. |
| [!UICONTROL ID de conjunto de datos] | Esta ID del conjunto de datos se genera en el Experience Platform. |


## Uso

La interfaz [!UICONTROL Uso] muestra el uso de filas ingeridas y notificables en todas las conexiones. Esta interfaz le permite determinar si el uso del Customer Journey Analytics cumple con lo acordado contractualmente. Además de los fines de monitorización, puede utilizar la interfaz de usuario de para planificar mejor la renovación de la licencia de Customer Journey Analytics.

Puede seleccionar un intervalo de tiempo (entre los últimos 6 meses, el año hasta la fecha o los últimos 2 años) y un intervalo (entre mensual o trimestral) para monitorizar el uso del Customer Journey Analytics. La interfaz se divide en dos secciones:

* Filas ingeridas: filas totales ingeridas/enviadas desde conjuntos de datos de evento en todas las conexiones de CJA, incluidos los registros omitidos durante la ingesta
* Filas reportables: filas reportables totales que incluyen todos los datos de eventos en todas las conexiones de CJA

![vista de uso](assets/usage-view.png)

Seleccione la ficha **[!UICONTROL Uso]** para tener acceso a la interfaz.

### Informe de uso

1. Seleccione un **[!UICONTROL intervalo de tiempo]**. Puede seleccionar entre **[!UICONTROL últimos 6 meses]**, **[!UICONTROL año hasta la fecha]** o **[!UICONTROL últimos 2 años]**.
1. Seleccionar un **[!UICONTROL intervalo]**. Puede seleccionar entre **[!UICONTROL mensual]** o **[!UICONTROL trimestral]**.

Para [!UICONTROL filas ingeridas]:

* Un panel muestra el total de filas introducidas que incluyen todos los datos de eventos en todas las conexiones actualizadas el segundo día de un mes. En el panel:
   * un cuadro muestra el número de filas introducidas del último mes y el cambio en % (indicado por ▲ o ▼) con respecto al mes anterior.
   * un gráfico de líneas muestra las [!UICONTROL filas ingeridas mensualmente] ◼︎.<br/>Para ver una ventana emergente que muestra el número de filas introducidas mensualmente durante un mes, pase el ratón sobre cualquier punto de datos del gráfico de líneas.


Para [!UICONTROL filas reportables]:

* Un panel muestra el total de filas sobre las que se pueden realizar informes que incluyen todos los datos de eventos en todas las conexiones actualizadas el segundo día de un mes. En el panel:
   * un cuadro muestra el número total acumulado de filas sobre las que se puede realizar un informe.
   * un cuadro muestra el número total de filas sobre las que se puede realizar un informe del último mes y el cambio en % (indicado por ▲ o ▼) con respecto al mes anterior.
   * un gráfico de líneas muestra las ◼︎ [!UICONTROL filas mensuales de las que se debe informar].<br/>Para ver una ventana emergente que muestra el número de filas notificables acumulativas de un mes específico, pase el ratón sobre cualquier punto de datos del gráfico de líneas.
   * un gráfico de líneas muestra las [!UICONTROL filas acumulativas sobre las que se puede generar informe] ◼︎.<br/>Para ver una ventana emergente que muestra el número de filas mensuales sobre las que se puede realizar un informe durante un mes, pase el ratón sobre cualquier punto de datos del gráfico de líneas.


>[!MORELIKETHIS]
>
>[Ver, solucionar problemas y modificar la configuración de conexión](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html) tutorial.
