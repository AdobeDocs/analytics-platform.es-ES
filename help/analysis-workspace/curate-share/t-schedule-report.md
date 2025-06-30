---
description: Obtenga información sobre cómo enviar un proyecto de Analysis Workspace directamente o según una programación para su envío por correo electrónico.
keywords: Analysis Workspace
title: Envío Y Programación De Proyectos
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 50%

---

# Envío y programación

Puede enviar proyectos de Customer Journey Analytics como archivos a usuarios seleccionados por correo electrónico. Puede enviar archivos ad hoc o configurar proyectos para que se envíen según una programación. Los proyectos se pueden enviar en formato CSV o PDF.

Todas las etiquetas aplicadas al proyecto se aplicarán automáticamente a la exportación.

También están disponibles otros métodos de exportación de datos de Customer Journey Analytics, como se describe en [Información general sobre la exportación](/help/analysis-workspace/export/export-project-overview.md).

![Enviar archivo](assets/send-file.png)

## Enviar archivo

Para enviar un archivo a los destinatarios por correo electrónico:

1. Seleccione **[!UICONTROL Compartir] > [!UICONTROL Enviar archivo]**.
1. Especifique el tipo de archivo:
   * [!UICONTROL **CSV**]: elija esta opción si desea datos de texto sin formato.
   * [!UICONTROL **PDF**]: elija esta opción si desea que el archivo descargado contenga todas las tablas y visualizaciones mostradas (visibles) en el proyecto.
1. (Opcional) Use **[!UICONTROL Descripción]** para agregar una descripción que incluir en el correo electrónico.
1. Añadir destinatarios o grupos. También puede introducir direcciones de correo electrónico.
1. (Solo para clientes de Healthcare Shield) Proporcione una contraseña para [proteger con contraseña un informe programado](#password-protect-a-new-scheduled-project).
1. (Opcional) Seleccione **[!UICONTROL Mostrar opciones de programación]** para [programar la exportación de un archivo](#schedule-file-export).
1. Haga clic en **[!UICONTROL Enviar ahora]**. Seleccione **[!UICONTROL Cancelar]** para cancelar.


## Programar la exportación del archivo {#schedule}

Para enviar un archivo según una programación a los destinatarios por correo electrónico

1. Seleccione **[!UICONTROL Compartir] > [!UICONTROL Programar exportación de archivos]**.
1. Especifique el tipo de archivo:
   * [!UICONTROL **CSV**]: elija esta opción si desea datos de texto sin formato.
   * [!UICONTROL **PDF**]: elija esta opción si desea que el archivo descargado contenga todas las tablas y visualizaciones mostradas (visibles) en el proyecto.
1. (Opcional) Use **[!UICONTROL Descripción]** para agregar una descripción que incluir en el correo electrónico.
1. Añadir destinatarios o grupos. También puede introducir direcciones de correo electrónico.
1. (Solo para clientes de Healthcare Shield) Proporcione una contraseña para [proteger con contraseña un informe programado](#password-protect-a-new-scheduled-project).
1. Asegúrese de que **[!UICONTROL Mostrar opciones de horario]** esté seleccionado.
1. Seleccione una **[!UICONTROL frecuencia]**. Puede seleccionar entre:

   | Frecuencia | Opciones |
   |---|---|
   | **[!UICONTROL Enviar por hora]** | Escriba un valor para **[!UICONTROL Enviar cada número de horas]**. |
   | **[!UICONTROL Enviar diariamente]** | Seleccione una **[!UICONTROL Frecuencia diaria]**: **[!UICONTROL Enviar todos los días]**, **[!UICONTROL Enviar todos los días de la semana]** o **[!UICONTROL Frecuencia personalizada]**.<br/>Si selecciona **[!UICONTROL Frecuencia personalizada]**, escriba un valor para **[!UICONTROL Enviar cada número de días]**. |
   | **[!UICONTROL Enviar semanalmente]** | Escriba un valor para **[!UICONTROL Enviar cada número de semanas]**. Y selecciona **[!UICONTROL Día de la semana]**. |
   | **[!UICONTROL Enviar mensualmente por día de la semana]** | Seleccione un **[!UICONTROL Día de la semana]** y una **[!UICONTROL Semana del mes]**. |
   | **[!UICONTROL Enviar mensualmente por día del mes]** | Seleccione un valor de **[!UICONTROL Enviar en este día del mes]**. |
   | **[!UICONTROL Enviar anualmente por día del mes]** | Seleccione un **[!UICONTROL Día de la semana]**, una **[!UICONTROL Semana del mes]** y un **[!UICONTROL Mes del año]**. |
   | **[!UICONTROL Enviar anualmente por fecha específica]** | Seleccione un **[!UICONTROL Mes del año]** y elija un valor entre **[!UICONTROL Enviar en este día del mes]**. |

1. Escriba una fecha de inicio en **[!UICONTROL A partir del]**. Como alternativa, seleccione ![Calendario](/help/assets/icons/Calendar.svg) para elegir una fecha de inicio del calendario.

1. Escriba una fecha de finalización en **[!UICONTROL Que termine el]**. Como alternativa, seleccione ![Calendario](/help/assets/icons/Calendar.svg) para elegir una fecha de finalización del calendario.
1. Seleccione **[!UICONTROL Enviar según lo programado]**. Seleccione **[!UICONTROL Cancelar]** para cancelar.


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

### Requisitos de contraseña

Los requisitos de contraseña cumplen con los estándares de Adobe y requieren un mínimo de 8 caracteres con al menos un número y un carácter especial.

### Proteger con contraseña un proyecto programado nuevo

1. Una vez guardado el proyecto, vaya a **[!UICONTROL Compartir]** > **[!UICONTROL Enviar archivo ahora]** o **[!UICONTROL Compartir]** > **[!UICONTROL Enviar archivo según lo programado]**.
1. Siga las instrucciones anteriores, en [Enviar archivo ahora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#now) o [Enviar archivo según lo programado](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#schedule).

### Proteger con contraseña un proyecto programado existente

Al proteger con contraseña un proyecto programado existente, el propietario del proyecto recibe un correo electrónico similar al siguiente:

![Notificación por correo electrónico de Customer Journey Analytics indicando que su organización necesita cifrado con contraseña.](assets/email-password.png)

1. Inicie sesión en Customer Journey Analytics. 
1. Seleccione **[!UICONTROL Ver proyecto programado]**.
1. En el diálogo **[!UICONTROL Editar proyecto programado]**, introduzca una contraseña y vuelva a introducirla.
1. Informe a los destinatarios del proyecto programado sobre esta contraseña. No distribuya la contraseña a personas que no sean destinatarios del proyecto programado.



## Administrador de proyectos programados {#manager}

Los proyectos programados de Analysis Workspace se pueden administrar desde la interfaz principal mediante **[!UICONTROL Componentes]** > **[!UICONTROL Proyectos programados]**. Para obtener más información, consulte [Proyectos programados](/help/components/scheduled-projects-manager.md)
