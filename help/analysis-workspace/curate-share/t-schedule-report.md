---
description: Envíe un proyecto de Analysis Workspace por correo electrónico o programe su entrega.
keywords: Analysis Workspace
title: Programar proyectos
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 79%

---

# Programar proyectos

Desde el espacio de trabajo **[!UICONTROL Compartir]** , puede enviar proyectos de Analysis Workspace por correo electrónico a destinatarios seleccionados. Los archivos se pueden enviar en formato CSV o PDF.

## Enviar archivo ahora {#now}

Para enviar un archivo inmediatamente a los destinatarios por correo electrónico:

1. Clic **[!UICONTROL Compartir] > [!UICONTROL Exportar archivo]**.
1. Especifique el tipo de archivo:
   * [!UICONTROL **CSV**]: elija esta opción si desea datos de texto sin formato.
   * [!UICONTROL **PDF**]: elija esta opción si desea que el archivo descargado contenga todas las tablas y visualizaciones mostradas (visibles) en el proyecto.
1. (Opcional) Añada una descripción para incluirla en el correo electrónico y explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. (Solo para clientes de Healthcare Shield) Proporcione una contraseña. Consulte la sección Proteger un informe programado con contraseña.
1. Haga clic en **[!UICONTROL Enviar ahora]**.
1. (Opcional) Haga clic en **[!UICONTROL Mostrar opciones de programación]** para especificar una programación de entregas.

![Enviar archivo ahora](assets/send-file-no-scheduling-options.JPG)

## Enviar archivo según lo programado {#schedule}

Para enviar un archivo en una programación recurrente a los destinatarios por correo electrónico:

1. Clic **[!UICONTROL Compartir] > [!UICONTROL Programar exportación de archivos]**.
1. Especifique el tipo de archivo (CSV o PDF).
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. (Solo para clientes de Healthcare Shield) Proporcione una contraseña. Consulte la sección Proteger un informe programado con contraseña.
1. Especifique el rango en el que debe entregarse la programación mediante la modificación de las entradas Inicio en y Finalización en. La fecha de finalización debe ser de un año a partir del día en el que se crea o modifica la programación.
1. Especifique la frecuencia de entrega. Cada frecuencia permite diferentes personalizaciones.
1. Haga clic en **[!UICONTROL Enviar según lo programado]**.

![](assets/send-file.JPG)

## Administrador de proyectos programados {#manager}

Los proyectos programados de Analysis Workspace se pueden administrar en **[!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Proyectos programados]**.

Para obtener más información, consulte [Proyectos programados](/help/components/scheduled-projects-manager.md)

## Proteger un proyecto programado con contraseña {#password}

>[!NOTE]
>
>La opción de proteger con contraseña un proyecto programado solo aparece para los clientes de Customer Journey Analytics que hayan adquirido [Healthcare Shield](https://business.adobe.com/es/solutions/experience-cloud-for-healthcare.html) producto de complemento.

Adobe utiliza la contraseña para cifrar proyectos programados, independientemente de si se envían en formato .pdf o .csv.

Una vez que su compañía ha adquirido la unidad de almacén de Healthcare Shield y se ha habilitado, aparece el mensaje para crear una contraseña para un proyecto programado en dos circunstancias:

* Cuando alguien crea un nuevo proyecto programado.

* Cuando un proyecto programado existente está a punto de enviarse. El proyecto programado actualmente se deshabilitará hasta que se establezca la protección con contraseña. El propietario del proyecto programado recibirá un correo electrónico con este fin.

![protección de contraseña](assets/password.png)

### Requisitos de contraseña

Los requisitos de la contraseña cumplen con el estándar de Adobe y requieren un mínimo de 8 caracteres con al menos un número y un carácter especial.

### Proteger con contraseña un proyecto programado nuevo

1. Una vez guardado el proyecto, vaya a **[!UICONTROL Compartir]** > **[!UICONTROL Enviar archivo ahora]** o [!UICONTROL Compartir] > **[!UICONTROL Enviar archivo según lo programado]**.
1. Siga las instrucciones anteriores, en [Enviar archivo ahora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#now) o [Enviar archivo según lo programado](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#schedule).

### Proteger con contraseña un proyecto programado existente

Antes de la hora en la que se programa un proyecto, el propietario del proyecto recibirá un correo electrónico similar al siguiente:

![email](assets/email-password.png)

1. Vuelva a iniciar sesión en el Customer Journey Analytics.
1. Haga clic en **[!UICONTROL Ver proyecto programado]**.
1. En el diálogo **[!UICONTROL Editar proyecto programado]**, introduzca una contraseña y vuelva a introducirla.
1. Informe (solo) a los destinatarios del proyecto programado sobre esta contraseña.


