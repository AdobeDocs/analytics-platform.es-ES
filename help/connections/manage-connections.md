---
title: Descubra cómo administrar conexiones en Customer Journey Analytics
description: Describe cómo administrar conexiones a conjuntos de datos de Experience Platform en Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0b41cc80310c49bd1b0c73f1323f86c8b280e15f
workflow-type: tm+mt
source-wordcount: '2487'
ht-degree: 27%

---

# Administrar conexiones

Una vez que haya [ha creado o editado una o más conexiones](/help/connections/create-connection.md), puede administrarlos en **[!UICONTROL Conexiones]**. Las conexiones le permiten:

* Vea todas las conexiones de un vistazo, incluido el propietario, el entorno de pruebas y cuándo se crearon y modificaron las conexiones.
* Editar una conexión.
* Eliminar una conexión.
* Crear una vista de datos a partir de una conexión.
* Ver todos los conjuntos de datos de una conexión.
* Compruebe el estado de los conjuntos de datos de la conexión y el estado del proceso de ingesta. Por ejemplo, ¿cuándo están disponibles los datos para que pueda empezar con los informes y análisis en Analysis Workspace?
* Identifique cualquier discrepancia en los datos debido a una configuración incorrecta. ¿Le faltan filas? En caso afirmativo, ¿qué filas faltan y por qué? ¿Configuró incorrectamente las conexiones y esto causó la falta de datos en el Customer Journey Analytics?


En la tabla se muestran todas las conexiones disponibles. Puede buscar rápidamente una conexión utilizando la opción Buscar ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) cuadro.

En la tabla están disponibles las siguientes columnas/iconos.

| Columna/icono | Descripción |
| --- | --- |
| [!UICONTROL Nombre] | Nombre descriptivo de la conexión. Para ver los detalles de la conexión, seleccione el nombre del hipervínculo. Consulte [Detalles de conexión](#connection-details). |
| ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para ver información acerca de [!UICONTROL Conjuntos de datos incluidos], [!UICONTROL Sandbox], [!UICONTROL Propietario], etc., seleccione ![Información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) junto al nombre de la conexión.<p>Una ventana emergente muestra detalles. <p><img src="./assets/conn-info.png" alt="Ver información de conexión" width="50%" /> |
| ![Vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Hasta [creación de una vista de datos](#create-a-data-view) para la conexión, seleccione ![Vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . Este icono solo se muestra cuando no hay ninguna vista de datos asociada a la conexión. |
| ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Seleccionar ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) hasta: <p>![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Editar](#edit-a-connection) una conexión.<p>![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Eliminar](#delete-a-connection) una conexión.<p>![Vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Crear nueva vista de datos](#create-a-data-view). Utilice esto para crear vistas de datos adicionales para la conexión. |
| [!UICONTROL Conjuntos de datos] | Muestra uno o más vínculos a los conjuntos de datos que forman parte de la conexión. Puede seleccionar el hipervínculo del conjunto de datos para ver el conjunto de datos en la conexión. Si forman parte de la conexión seleccionada más conjuntos de datos, seleccione **[!UICONTROL +*x* más]** para mostrar un **[!UICONTROL Conjuntos de datos incluidos]** panel. Este panel muestra vínculos a todos los conjuntos de datos y una opción para buscar un conjunto de datos específico que forme parte de la conexión.<p><img src="./assets/datasets-included.png" alt="Datassets incluidos" width="50%" /><p>Al seleccionar un nombre de conjunto de datos, se abre el conjunto de datos en la IU del Experience Platform en una nueva pestaña. |
| [!UICONTROL Zona protegida] | Muestra el [zona protegida de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) de la que esta conexión obtiene sus conjuntos de datos. Este entorno de pruebas se seleccionó cuando creó la conexión. No se puede modificar. |
| [!UICONTROL Propietario] | La persona que creó la conexión. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para conjuntos de datos: <p><span style="color:green">●</span>   **[!UICONTROL _x _Activado]**para cuántos conjuntos de datos se han configurado para importar datos nuevos y&lt;/b<p><span style="color:gray">●</span>   **[!UICONTROL _x desactivada_]** para cuántos conjuntos de datos está desactivada la importación de datos nuevos. |
| [!UICONTROL Fecha de creación] | La marca de tiempo cuando se creó la conexión. |
| [!UICONTROL Última modificación] | La marca de tiempo de la última actualización de la conexión. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno entre conjuntos de datos.<p><span style="color:red">●</span>   **[!UICONTROL _x _relleno fallido]**para el número de rellenos fallidos entre conjuntos de datos,<p><span style="color:orange">●</span>   **[!UICONTROL _x _procesamiento de rellenos]**para el número de rellenos de procesamiento entre conjuntos de datos,<p><span style="color:green">●</span>   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados para conjuntos de datos, y<p><span style="color:grey">●</span>   **[!UICONTROL _Desactivado_]** en caso de que no se definan rellenos para los conjuntos de datos de la conexión. |

Puede configurar qué columnas mostrar mediante ![Configuración de columna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Esto muestra el **Personalizar tabla** que permite activar o desactivar columnas en la tabla.

## Edición de una conexión

Permite a los administradores editar la conexión.

1. Seleccionar ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) junto al nombre de la conexión
1. Seleccionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** en el menú contextual.

Como alternativa, puede:

1. Seleccione la fila de conexión.

1. Seleccionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** de la barra azul.

Al editar una conexión, puede:

* Iniciar y detener la importación de nuevos datos.
* Cambiar el nombre de una conexión.
* Actualice los conjuntos de datos.
* Elimine los conjuntos de datos de las conexiones.

Consulte [Crear o editar una conexión](create-connection.md) para obtener más información.


## Eliminar una conexión {#connections-delete}

Permite a los administradores eliminar la conexión.

1. Seleccionar ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) junto al nombre de la conexión.
1. Seleccionar ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]**.

Como alternativa, puede:

1. Seleccione la fila de conexión.

1. Seleccionar ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]** de la barra azul.

Al eliminar una conexión, una **[!UICONTROL Eliminar conexión]** el panel indica qué vistas de datos se eliminan y qué proyectos de workspace se ven afectados.

<img src="./assets/delete-connection.png" alt="Eliminar conexión" width="50%" />

Seleccionar **[!UICONTROL Continuar]** para eliminar la conexión.

Consulte [Eliminar implicaciones](/help/admin/cja-deletion.md) para obtener más información sobre las implicaciones de eliminar una conexión.


## Creación de una vista de datos

Permite a los administradores crear una vista de datos para la conexión.

* Si no hay ninguna vista de datos asociada a la conexión:

   1. Seleccionar ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) junto al nombre de la conexión.

* Si ya se han creado una o más vistas de datos para la conexión:

   1. Seleccionar ![Más](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) junto al nombre de la conexión.
   1. Seleccionar ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear nueva vista de datos]**.

Como alternativa, puede:

1. Seleccione la fila de conexión.

1. Seleccionar ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear vista de datos]** de la barra de botones azul.

Consulte [Creación o edición de una vista de datos](/help/data-views/create-dataview.md) para obtener más información.

## Detalles de conexión {#connection-detail}

Para ir a los detalles de una conexión, seleccione un nombre de conexión en la tabla de conexiones.

![Ventana Todos los conjuntos de datos que muestra los widgets y la configuración](assets/conn-details.png)

La pantalla de detalles de Conexiones proporciona una vista detallada del estado de una conexión. Puede realizar lo siguiente:

* Compruebe el estado de los conjuntos de datos de la conexión y del proceso de ingesta.
* Identifique los problemas de configuración que pueden provocar registros omitidos o eliminados.
* Ver cuándo están disponibles los datos para los informes.

>[!IMPORTANT]
>
>Los datos introducidos antes del 13 de agosto de 2021 no se reflejan en este [!UICONTROL Conexiones] diálogo.

### Detalles de conexión

| Interfaz de usuario | Descripción |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Editar conexión] | Para editar los detalles de una conexión, seleccione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexión]** . Consulte [Crear o editar una conexión](create-connection.md) para obtener más información. |
| Selector de conjunto de datos | Permite seleccionar uno o todos los conjuntos de datos de la conexión. No puede seleccionar conjuntos de datos múltiples. El valor predeterminado es [!UICONTROL Todos los conjuntos de datos]. |
| Calendario/Selector de intervalo de fechas | El intervalo de fechas indica cuándo se añadieron datos a la conexión. Se incluyen todos los ajustes preestablecidos de calendario estándar. Puede personalizar el intervalo de fechas, pero en la lista desplegable no aparecerá ningún intervalo de fechas personalizado. |
| [!UICONTROL Registros de datos de evento disponibles] | Representa el número total de filas del conjunto de datos de evento disponibles para la creación de informes, **para toda la conexión**. Este recuento es independiente de cualquier configuración de calendario. El recuento cambia si selecciona un conjunto de datos del selector de conjuntos de datos o en la tabla. Una vez añadidos los datos, existe una latencia de una a dos horas para que los datos aparezcan en los informes. |
| [!UICONTROL Métricas] | Resume los registros añadidos, omitidos o eliminados del evento, y el número de lotes agregados, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. |
| [!UICONTROL Registros añadidos] | Indica cuántas filas se añadieron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Se actualiza cada diez minutos. <p>**Nota**: datos para **[!UICONTROL Registros añadidos]** solo incluye datos de evento en este momento, no datos de perfil o búsqueda. |
| [!UICONTROL Registros omitidos] | Indica cuántas filas se omitieron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Los motivos por los que se omiten registros son: faltan marcas de hora, falta ID de persona o no es válido, etc. Se actualiza cada diez minutos.<p>ID de persona no válido (como “sin definir”, “00000000” o cualquier combinación de números y letras en un [!UICONTROL ID de persona] que aparece en un evento más de 1 millón de veces en un mes determinado) no se puede atribuir a ningún usuario o persona en particular. No se pueden ingerir en el sistema, y conlleva la generación de informes e ingestas propensas a errores. Para corregir ID de persona no válidos, tiene tres opciones:<ul><li>Uso [Vinculación](/help/stitching/overview.md) para rellenar los ID de usuario sin definir o todos cero con ID de usuario válidos.</li><li>Vacíe el ID de usuario, que luego se omitirá durante la ingesta (preferible a los ID de usuario no válidos o todos cero).</li><li>Corrija cualquier ID de usuario no válido en el sistema antes de ingerir los datos.</li></ul><p>**Nota**: datos para **[!UICONTROL Registros omitidos]** solo incluye datos de evento en este momento, no datos de perfil o búsqueda. |
| [!UICONTROL Registros] eliminado | Indica cuántas filas se eliminaron en el período de tiempo seleccionado, **para el conjunto de datos y el intervalo de fechas que ha seleccionado**. Alguien podría haber eliminado un conjunto de datos en Experience Platform, por ejemplo. Se actualiza cada diez minutos. <p>**Nota**: datos para **[!UICONTROL Registros eliminados]** solo incluye datos de evento en este momento, no datos de perfil o búsqueda. |
| ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Buscar nombre o ID del conjunto de datos_ | Campo de búsqueda de conjunto de datos. Puede buscar la tabla de conjuntos de datos por nombre de conjunto de datos o [!UICONTROL ID de conjunto de datos]. |
| [!UICONTROL Tabla Conjuntos de datos] | Muestra los conjuntos de datos que forman parte de la conexión. |
| [!UICONTROL Conjuntos de datos] | Muestra el nombre del conjunto de datos que forma parte de la conexión. Puede seleccionar el hipervínculo para abrir el conjunto de datos en la interfaz de usuario de Experience Platform en una nueva pestaña. Puede seleccionar la fila o la casilla de verificación para mostrar solo los detalles del conjunto de datos seleccionado. |
| [!UICONTROL ID de conjunto de datos] | Generado automáticamente por el Experience Platform. |
| [!UICONTROL Registros añadidos] | El número de registros/filas del conjunto de datos agregados a una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Registros omitidos] | El número de registros/filas del conjunto de datos omitidos durante la transferencia de datos para una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Registros eliminados] | El número de registros/filas del conjunto de datos quitados de una conexión durante el intervalo de tiempo seleccionado. |
| [!UICONTROL Lotes añadidos] | Se ha agregado el número de lotes del conjunto de datos a una conexión. |
| [!UICONTROL Última incorporación] | La marca de tiempo del último lote del conjunto de datos agregado a una conexión. |
| [!UICONTROL Tipo de fuente de datos] | El tipo de origen del conjunto de datos. El tipo de origen se define al crear una conexión. |
| [!UICONTROL Tipo de conjunto de datos] | El tipo de conjunto de datos para este conjunto de datos. El tipo puede ser [!UICONTROL Evento], [!UICONTROL Búsqueda], o [!UICONTROL Perfil]. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#configure-dataset) |
| Esquema | El esquema del Experience Platform en el que se basa el conjunto de datos. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para el conjunto de datos: <p><span style="color:green">●</span>   **[!UICONTROL _x _Activado]**si el conjunto de datos está configurado para importar nuevos datos, y<p><span style="color:gray">●</span>   **[!UICONTROL _x desactivada_]** si el conjunto de datos está configurado para no importar nuevos datos importar. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno del conjunto de datos.<p><span style="color:red">●</span>   **[!UICONTROL _x _relleno fallido]**para el número de rellenos fallidos,<p><span style="color:orange">●</span>   **[!UICONTROL _x _procesamiento de rellenos]**para el número de rellenos procesados,<p><span style="color:green">●</span>   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p><span style="color:grey">●</span>   **[!UICONTROL _Desactivado_]** en caso de que no se configuren rellenos. |

### Panel de conexión

Cuando no se selecciona ningún conjunto de datos en la tabla de conjuntos de datos, un panel a la derecha de la interfaz Conexiones muestra las opciones y los detalles de la conexión.

| Opciones/detalles | Descripción |
| --- | --- |
| ![Actualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Actualizar] | Para actualizar la conexión y permitir que se reflejen los registros añadidos recientemente, seleccione ![Actualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Actualizar]**. |
| ![Eliminar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar]** | [Eliminar](#delete-a-connection) esta conexión. |
| ![Agregar vista de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Crear vista de datos]** | [Creación de una vista de datos](#create-a-data-view) en función de esta conexión. Consulte [Vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es) para obtener más información. |
| [!UICONTROL Nombre de la conexión] | Muestra el nombre descriptivo de la conexión. |
| [!UICONTROL Descripción de la conexión] | Muestra una descripción más detallada que describe el propósito de esta conexión. |
| [!UICONTROL Zona protegida] | El [zona protegida de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) de la cual esta conexión obtiene sus conjuntos de datos. Este entorno de pruebas se seleccionó la primera vez que creó la conexión. No se puede modificar. |
| [!UICONTROL ID de conexión] | Este ID se genera en el Experience Platform. Puede utilizar ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar el ID. |
| [!UICONTROL Vistas de datos mediante conexión] | Enumera todas las vistas de datos que utilizan esta conexión. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para conjuntos de datos: <p><span style="color:green">●</span>   **[!UICONTROL _x _Activado]**para cuántos conjuntos de datos están configurados para importar nuevos datos, y<p><span style="color:gray">●</span>   **[!UICONTROL _x desactivada_]** para cuántos conjuntos de datos está desactivada la importación de datos nuevos. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno de los conjuntos de datos.<p><span style="color:red">●</span>   **[!UICONTROL _x _relleno fallido]**para el número de rellenos fallidos entre conjuntos de datos,<p><span style="color:orange">●</span>   **[!UICONTROL _x _procesamiento de rellenos]**para el número de rellenos de procesamiento entre conjuntos de datos,<p><span style="color:green">●</span>   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados para conjuntos de datos, y<p><span style="color:grey">●</span>   **[!UICONTROL _Desactivado_]** en caso de que no se definan rellenos para los conjuntos de datos de la conexión. |
| [!UICONTROL Creado por] | Muestra el nombre de la persona que creó la conexión. |
| [!UICONTROL Última modificación] | Muestra la marca de tiempo del último cambio realizado en la conexión. |
| [!UICONTROL Última modificación de:] | Muestra la persona que modificó la conexión por última vez. |

### Panel Conjunto de datos

Cuando se selecciona un conjunto de datos en la tabla de conjuntos de datos, un panel a la derecha de la interfaz Conexiones muestra detalles del conjunto de datos seleccionado.

| Detalles | Descripción |
| --- | --- |
| [!UICONTROL ID de la persona] | Muestra una identidad que se definió en el esquema del conjunto de datos en Experience Platform. Este es el ID de persona que seleccionó durante la creación de la conexión. Si crea una conexión que incluye conjuntos de datos con distintos ID, el sistema de informes reflejará eso. Para combinar conjuntos de datos, debe utilizar el mismo ID de persona en ellos. |
| [!UICONTROL Clave] | Muestra la clave que ha especificado para un conjunto de datos de búsqueda. |
| [!UICONTROL Clave de coincidencia] | Muestra la clave coincidente que ha especificado para un conjunto de datos de búsqueda. |
| [!UICONTROL Marca de tiempo] | Mostrar la marca de tiempo definida para un conjunto de datos de evento. |
| [!UICONTROL Registros disponibles] | Representa el número total de filas ingeridas para este conjunto de datos, para el período de tiempo particular seleccionado a través del calendario. Una vez añadidos, no hay latencia en cuanto a la aparición de datos en los informes. Sin embargo, cuando cree una conexión completamente nueva, no habrá [latencia](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Registros añadidos] | Indica cuántas filas se añadieron en el período de tiempo seleccionado. <p>**Nota**: datos para **[!UICONTROL Registros añadidos]** solo incluye datos de evento en este momento, no datos de perfil o búsqueda. |
| [!UICONTROL Registros eliminados] | Indica cuántos registros se eliminaron durante el período de tiempo seleccionado. <p>**Nota**: datos para **[!UICONTROL Registros eliminados]** solo incluye datos de evento en este momento, no datos de perfil o búsqueda. |
| [!UICONTROL Lotes añadidos] | Indica cuántos lotes de datos se añadieron a este conjunto de datos. |
| [!UICONTROL Registros omitidos] | Indica cuántas filas se omitieron durante la ingesta en el período de tiempo seleccionado.<p>Los motivos por los que se omiten registros son: faltan marcas de hora, falta ID de persona o no es válido, etc. Se actualiza cada diez minutos.<p>ID de persona no válido (como “sin definir”, “00000000” o cualquier combinación de números y letras en un [!UICONTROL ID de persona] que aparece en un evento más de 1 millón de veces en un mes determinado) no se puede atribuir a ningún usuario o persona en particular. No se pueden ingerir en el sistema, y conlleva la generación de informes e ingestas propensas a errores. Para corregir ID de persona no válidos, tiene tres opciones:<ul><li>Uso [Vinculación](/help/stitching/overview.md) para rellenar los ID de usuario sin definir o todos cero con ID de usuario válidos.</li><li>Vacíe el ID de usuario, que luego se omitirá durante la ingesta (preferible a los ID de usuario no válidos o todos cero).</li><li>Corrija cualquier ID de usuario no válido en el sistema antes de ingerir los datos.</li></ul><p>**Nota**: datos para **[!UICONTROL Registros omitidos]** solo incluye datos de evento en este momento, no datos de perfil o búsqueda. |
| [!UICONTROL Última incorporación] | Indica cuándo se añadió el último lote. |
| [!UICONTROL Importar datos nuevos] | Muestra el estado de la importación de nuevos datos para el conjunto de datos: <p><span style="color:green">●</span>   **[!UICONTROL _x _Activado]**si el conjunto de datos está configurado para importar nuevos datos, y<p><span style="color:gray">●</span>   **[!UICONTROL _x desactivada_]** si el conjunto de datos está configurado para no importar nuevos datos importar. |
| [!UICONTROL Datos de relleno] | Muestra el estado de los datos de relleno del conjunto de datos.<p><span style="color:red">●</span>   **[!UICONTROL _x _relleno fallido]**para el número de rellenos fallidos,<p><span style="color:orange">●</span>   **[!UICONTROL _x _procesamiento de rellenos]**para el número de rellenos procesados,<p><span style="color:green">●</span>   **[!UICONTROL _x _rellenos completados]**para el número de rellenos completados, y<p><span style="color:grey">●</span>   **[!UICONTROL _Desactivado_]** en caso de que no se configuren rellenos.<p>Para mostrar un cuadro de diálogo con una descripción general de los rellenos anteriores para el conjunto de datos, seleccione <img src="./assets/pastbackfill.svg" alt="Rellenos anteriores" width="2%" /> **[!UICONTROL Rellenos anteriores]**. |
| [!UICONTROL Tipo de fuente de datos] | Tipo de origen de datos definido al agregar un conjunto de datos a la conexión. |
| [!UICONTROL Tipo de conjunto de datos] | [!UICONTROL Evento], [!UICONTROL Búsqueda] o [!UICONTROL Perfil]. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#configure-dataset) |
| [!UICONTROL Esquema] | Muestra el esquema del Experience Platform en el que se basa este conjunto de datos. |
| [!UICONTROL ID de conjunto de datos] | Esta ID del conjunto de datos se genera en el Experience Platform. |


>[!MORELIKETHIS]
>
>[Ver, solucionar problemas y modificar la configuración de conexión](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) tutorial.
