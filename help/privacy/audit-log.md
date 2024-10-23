---
title: Registros de auditoría
description: Obtenga información sobre cómo ver y administrar registros de auditoría de Customer Journey Analytics.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 66%

---

# Registros de auditoría {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_userid"
>title="ID de usuario"
>abstract="El ID de usuario se puede encontrar pulsando el botón de información en una entrada de registro que contenga el usuario en cuestión."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_componentid"
>title="ID de componente"
>abstract="El ID de componente se puede encontrar pulsando el botón de información en una entrada de registro que contenga el componente en cuestión."

<!-- markdownlint-enable MD034 -->


Para aumentar la transparencia y la visibilidad de las actividades realizadas en el sistema, Adobe Customer Journey Analytics le permite auditar la actividad del usuario para varios servicios y funcionalidades en forma de &quot;registros de auditoría&quot;. Estos registros forman una pista de auditoría que puede ser útil en la resolución de problemas y ayudar a su empresa a cumplir de manera eficaz con las políticas de administración de datos corporativos y los requisitos regulatorios, como la Ley de Portabilidad y Responsabilidad del Seguro de Salud (HIPAA, Health Insurance Portability and Accountability Act).

En un sentido estricto, un registro de auditoría informa de **quién** realizó **qué** acción y **cuándo** lo hizo. Cada acción registrada contiene metadatos que indican el tipo de acción, la fecha y la hora, el ID de correo electrónico del usuario que realizó la acción y los atributos adicionales relevantes de ese tipo de acción.

Este tema cubre los registros de auditoría en Customer Journey Analytics, incluido cómo verlos y administrarlos en la interfaz de usuario.

## Acceso a los registros de auditoría

Cuando la función está habilitada para su organización, los registros de auditoría se recopilan automáticamente a medida que se produce la actividad. No es necesario habilitar manualmente la recopilación de registros.

Para ver y exportar los registros de auditoría, se debe contar con el permiso de control **[!UICONTROL Acceso a registros de auditoría]** en la consola de Adobe. Para obtener información sobre cómo administrar permisos individuales para funciones de Customer Journey Analytics, consulte la [documentación de control de acceso](../technotes/access-control.md).

## Vista del registro de auditoría en la IU

En el Customer Journey Analytics, vaya a **[!UICONTROL Herramientas]** > **[!UICONTROL Registros de auditoría]**.

El registro de auditoría correspondiente al día de hoy y al día de ayer se muestra de forma predeterminada.

![Resaltar registros de auditoría hoy y ayer. ](assets/audit_ui.png)

Para seleccionar qué columnas están visibles, vaya al selector de columnas ubicado en la parte superior derecha.

## Visualización de información sobre entradas de registro individuales

Haga doble clic en el botón de información (i) junto a una descripción.

![Registro de auditoría que resalta el botón de información. ](assets/info-button-audit.png)

Se muestran los siguientes elementos:

* **[!UICONTROL Nombre de la acción]**: Acción realizada. Entre los posibles valores están:
   * API_REQUEST
   * APROBAR
   * CREAR
   * DELETE
   * EDITAR
   * EMBARGO
   * EXPORTAR
   * ORG_CHANGE
   * ACTUALIZAR
   * SHARE
   * TRANSFERIR
   * DESAPROBAR
   * DEJAR DE COMPARTIR
* **[!UICONTROL Fecha de creación]**: La fecha y la hora en que se realizó la acción.
* **[!UICONTROL Descripción]**: Un resumen de la acción.
* **[!UICONTROL Nombre de usuario]**: El usuario que realizó la acción.
* **[!UICONTROL Correo electrónico]**: La dirección de correo electrónico del usuario que realizó la acción.
* **[!UICONTROL Nombre de componente]**: Componente sobre el que el usuario realizó una acción.
* **[!UICONTROL Tipo de componente]**: El tipo de componente. Entre los posibles valores están:
   * ANOTACIÓN
   * AUDIENCIA
   * CALCULATED_METRIC
   * CONEXIÓN
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTRO
   * IMS_ORG
   * MÓVIL
   * PROYECTO
   * INFORME
   * PROYECTO_PROGRAMADO
   * USUARIO
   * USER_GROUP
* **[!UICONTROL ID de componente]**: ID del componente sobre el que el usuario realizó una acción.
* **[!UICONTROL ID de organización de IMS]**: ID de IMS de la organización, con el formato `ABC123@AdobeOrg`.
* **[!UICONTROL Id. de registro]**: ID único que identifica esta entrada de registro.
* **[!UICONTROL ID de usuario]**: ID único que identifica al usuario que realizó la acción.
* **[!UICONTROL Tipo de usuario]**: El tipo de autenticación usado. Los valores válidos son los siguientes:
   * IMS
   * OKTA

### Filtrar registros de auditoría

Seleccione el icono de canal (![filtro](assets/filter-icon.png)) para mostrar una lista de controles de filtro y ayudar a reducir los resultados. Solo se muestran los últimos 1000 registros, independientemente de los distintos filtros seleccionados.

![Registro de auditoría que muestra los filtros mostrados para el intervalo de fechas.](assets/filters.png)

Los siguientes filtros están disponibles para eventos de auditoría en la interfaz de usuario:

| Filtro | Descripción |
| --- | --- |
| [!UICONTROL Intervalo de fecha] | Filtre en un intervalo distinto seleccionando una fecha diferente o un intervalo de fechas arrastrando el cursor sobre varias fechas. De forma predeterminada, se seleccionan las fechas de hoy y de ayer. |
| [!UICONTROL Acción] | Filtre por cualquier nombre de acción enumerado anteriormente. |
| [!UICONTROL ID de usuario] | Filtrar por un usuario específico con el ID. El ID de usuario se puede encontrar seleccionando el botón de información (i) junto al nombre de usuario. |
| [!UICONTROL Correo electrónico] | Filtre por la dirección de correo electrónico de un usuario específico. El correo electrónico se puede encontrar seleccionando el botón de información (i) junto a un nombre de usuario. |
| [!UICONTROL ID de componente] | Filtre por un ID de componente específico. El ID de componente se puede encontrar seleccionando el botón de información (i) para un componente deseado. |
| [!UICONTROL Tipo de componente] | Filtre por cualquier tipo de componente enumerado anteriormente. |

{style="table-layout:auto"}

## Tipos de eventos capturados por los registros de auditoría

La siguiente tabla indica qué acciones sobre qué tipo de componentes se registran en los registros de auditoría:

| Tipo de componente | Acciones |
| --- | --- |
| [!UICONTROL Anotación] | <ul><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Audiencia] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li><li>Exportar</li><li>Actualizar</li></ul> |
| [!UICONTROL Métrica calculada] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Conexión] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Vista de datos] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Intervalo de fecha] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Filtro] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL IMS Org] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Proyecto] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Informe] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Proyecto programado] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Usuario] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |
| [!UICONTROL Grupo de usuarios] | <ul><li>API_Request</li><li>Crear</li><li>Eliminar</li><li>Editar</li></ul> |

{style="table-layout:auto"}

## Descargar registros de auditoría

Puede descargar registros de auditoría en los formatos CSV o JSON. Los filtros aplicados o las columnas seleccionadas se reflejan en los archivos descargados.

1. Haga clic en **[!UICONTROL Descargar]** en la parte superior derecha de la pantalla.
1. Especifique el formato.
1. Haga clic en **[!UICONTROL Descargar]** de nuevo.

## Administrar registros de auditoría en la API

Todas las acciones que puede realizar en la interfaz de usuario también se pueden realizar mediante llamadas a la API. Consulte el [documento de referencia de la API de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) para obtener más información.
