---
description: Envíe un proyecto de Analysis Workspace por correo electrónico o programe su envío.
keywords: Analysis Workspace
title: Enviar informes a otras personas por correo electrónico
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: ht
source-wordcount: '1034'
ht-degree: 100%

---

# Enviar archivos a otras personas

Puede enviar informes de Customer Journey Analytics como archivos a las personas seleccionadas por correo electrónico. Puede enviar archivos ad hoc o configurar los archivos para que se envíen según una programación. Los archivos se pueden enviar en formato CSV o PDF.

Todas las etiquetas aplicadas al proyecto se aplicarán automáticamente a la exportación.

También están disponibles otros métodos de exportación de datos de Customer Journey Analytics, como se describe en [Información general sobre la exportación](/help/analysis-workspace/export/export-project-overview.md).

## Enviar archivo ahora {#now}

Para enviar un archivo inmediatamente a los destinatarios por correo electrónico:

1. Haga clic en **[!UICONTROL Compartir] > [!UICONTROL Exportar archivo]**.
1. Especifique el tipo de archivo:
   * [!UICONTROL **CSV**]: elija esta opción si desea datos de texto sin formato.
   * [!UICONTROL **PDF**]: elija esta opción si desea que el archivo descargado contenga todas las tablas y visualizaciones mostradas (visibles) en el proyecto.
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. (Solo para clientes de Healthcare Shield) Proporcione una contraseña. Consulte la sección Proteger un informe programado con contraseña.
1. (Opcional) Haga clic en **[!UICONTROL Mostrar opciones de programación]** para especificar una programación de entregas.
1. Haga clic en **[!UICONTROL Enviar ahora]**.

![Ventana Enviar archivo y botón Enviar ahora.](assets/send-file-no-scheduling-options.JPG)

## Enviar archivo según lo programado {#schedule}

Para enviar un archivo según una programación recurrente a los destinatarios por correo electrónico:

1. Haga clic en **[!UICONTROL Compartir] > [!UICONTROL Programar exportación de archivos]**.
1. Especifique el tipo de archivo (CSV o PDF).
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. (Solo para clientes de Healthcare Shield) Proporcione una contraseña. Consulte la sección Proteger un informe programado con contraseña.
1. Especifique el rango en el que debe entregarse la programación mediante la modificación de las entradas Inicio en y Finalización en. La fecha de finalización debe ser de un año a partir del día en el que se crea o modifica la programación.
1. Especifique la frecuencia de entrega. Cada frecuencia permite diferentes personalizaciones.
1. Haga clic en **[!UICONTROL Enviar según lo programado]**.

![Se muestran la ventana Enviar archivo y las opciones de programación para mostrar las opciones Fecha de inicio, Fecha de finalización y la frecuencia diaria.](assets/send-file.JPG)

## Administrador de proyectos programados {#manager}

Los proyectos programados de Analysis Workspace se pueden administrar en **[!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Proyectos programados]**.

En el Administrador de proyectos programados, puede editar y eliminar la programación recurrente de proyectos. Busque una programación en la barra de búsqueda o utilizando las opciones de filtro en el panel izquierdo. Puede filtrar por etiqueta, programaciones aprobadas, propietarios, etc.

| Campo | Descripción |
| --- | --- |
| [!UICONTROL Favoritos] | Al seleccionar el icono de estrella, marca esta programación como favorita. |
| [!UICONTROL ID de programación] | Este ID se utiliza principalmente con fines de depuración. |
| [!UICONTROL Título y descripción] | Título y descripción de este proyecto. |
| [!UICONTROL Propietario] | La persona que creó el proyecto y es propietaria de él. |
| [!UICONTROL Etiquetas] | (opcional) El etiquetado es una buena forma de organizar los proyectos. Todos los usuarios pueden crear etiquetas y aplicar una o más a un proyecto. Sin embargo, solo verá las etiquetas de los proyectos que sean suyos o que se hayan compartido con usted. |
| [!UICONTROL Enviado a] | Las personas destinatarias de este proyecto programado. |
| [!UICONTROL Fecha de caducidad] | Puede establecer la fecha de caducidad en un máximo de un año, independientemente de la frecuencia de programación. |
| [!UICONTROL Frecuencia] | La frecuencia con la que desea que este proyecto programado se envíe a las personas destinatarias. |
| [!UICONTROL Hora de ejecución] | A qué hora del día se envía este proyecto programado. |
| [!UICONTROL Cantidad de consultas] | Número de consultas de este proyecto. |

Las siguientes son acciones comunes en el administrador de proyectos programados:

| Acción | Descripción |
|---|---|
| **[!UICONTROL Editar programación]** | Haga clic en el título de la programación para actualizar su configuración de entrega. |
| **[!UICONTROL Eliminar programación]** | Seleccione el proyecto programado en la lista y, a continuación, haga clic en Eliminar en el menú. Esto eliminará la programación seleccionada para el proyecto; el proyecto en sí no se eliminará. |
| **[!UICONTROL Añadir etiquetas]** | Seleccione el proyecto programado en la lista y, a continuación, elija “Etiqueta” o “Aprobar” para organizar las programaciones y facilitar su búsqueda. |
| **[!UICONTROL Ver las programaciones fallidas]** | Vaya al panel izquierdo > Otros filtros > Con error para ver las programaciones que han fallado. |
| **[!UICONTROL Ver las programaciones caducadas]** | Vaya al panel izquierdo > Otros filtros > Caducados para ver las programaciones que han caducado. Haga clic en el título de la programación para configurar una nueva programación de envío. |
| **[!UICONTROL Ver el ID de programación]** | Vaya a las opciones de columna en la parte superior derecha y añada la columna ID de programación a la tabla. El ID de programación suele ser útil para la depuración. |

El Administrador de programación de proyectos muestra los artículos que ha creado un usuario en particular. Si la cuenta del usuario está desactivada en la aplicación, se detendrán todos los envíos programados.
Para obtener más información, consulte [Proyectos programados](/help/components/scheduled-projects-manager.md)

## Proteger un proyecto programado con contraseña {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Cifrado con contraseña"
>abstract="La contraseña proporcionada se utilizará para cifrar el archivo del proyecto programado. Los requisitos de seguridad para su organización requieren el cifrado con contraseña."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>La opción de proteger con contraseña un proyecto programado solo aparece para los clientes de Customer Journey Analytics que hayan adquirido el producto de complemento [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html?lang=es).

Adobe utiliza la contraseña para cifrar proyectos programados, independientemente de si se envían en formato .pdf o .csv.

Después de que su compañía haya adquirido la SKU de Healthcare Shield y haya sido habilitada para ello, aparecerá la solicitud para crear una contraseña para un proyecto programado en las siguientes circunstancias:

* Cuando alguien crea un nuevo proyecto programado.

* Cuando un proyecto programado existente está a punto de enviarse. El proyecto programado actualmente está deshabilitado hasta que se establezca la protección con contraseña. El propietario del proyecto programado recibe un correo electrónico que le informa de este requisito.

![La ventana Editar proyecto programado y la notificación de cifrado de contraseña que indican que su organización requiere cifrado de contraseña.](assets/password.png)

### Requisitos de contraseña

Los requisitos de contraseña cumplen con los estándares de Adobe y requieren un mínimo de 8 caracteres con al menos un número y un carácter especial.

### Proteger con contraseña un proyecto programado nuevo

1. Una vez guardado el proyecto, vaya a **[!UICONTROL Compartir]** > **[!UICONTROL Enviar archivo ahora]** o **[!UICONTROL Compartir]** > **[!UICONTROL Enviar archivo según lo programado]**.
1. Siga las instrucciones anteriores, en [Enviar archivo ahora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#now) o [Enviar archivo según lo programado](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#schedule).

### Proteger con contraseña un proyecto programado existente

Antes de programar un proyecto, su propietario recibe un correo electrónico similar al siguiente:

![Notificación por correo electrónico de Customer Journey Analytics indicando que su organización necesita cifrado con contraseña.](assets/email-password.png)

1. Inicie sesión en Customer Journey Analytics. 
1. Seleccione **[!UICONTROL Ver proyecto programado]**.
1. En el diálogo **[!UICONTROL Editar proyecto programado]**, introduzca una contraseña y vuelva a introducirla.
1. Informe a los destinatarios del proyecto programado sobre esta contraseña. No distribuya la contraseña a personas que no sean destinatarios del proyecto programado.
