---
description: Envíe un proyecto de Analysis Workspace por correo electrónico o programe su entrega.
keywords: Analysis Workspace
title: Programar proyectos
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: eba2eb71ca434e0306c018b80209caf52266ee15
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 63%

---

# Programar proyectos

En el **menú Compartir** de Workspace, puede enviar proyectos de Analysis Workspace por correo electrónico a destinatarios seleccionados. Los archivos se pueden enviar en formato CSV o PDF.

## Enviar archivo ahora {#now}

Para enviar un archivo inmediatamente a los destinatarios por correo electrónico:

1. Haga clic en **Compartir > Enviar archivo ahora**.
1. Especifique el tipo de archivo (CSV o PDF).
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. (Sólo para clientes de Healthcare Shield) Proporcione una contraseña. Consulte la sección Proteger con contraseña un informe programado .
1. Haga clic en **Enviar ahora**.
1. (Opcional) Haga clic en **Mostrar opciones de programación** para especificar una programación de entregas.

![Enviar archivo ahora](assets/send-file-no-scheduling-options.JPG)

## Enviar archivo según lo programado {#schedule}

Para enviar un archivo en una programación recurrente a los destinatarios por correo electrónico:

1. Haga clic en **Compartir > Enviar archivo según lo programado**.
1. Especifique el tipo de archivo (CSV o PDF).
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. (Sólo para clientes de Healthcare Shield) Proporcione una contraseña. Consulte la sección Proteger con contraseña un informe programado .
1. Especifique el rango en el que debe entregarse la programación mediante la modificación de las entradas Inicio en y Finalización en. La fecha de finalización debe ser de un año a partir del día en el que se crea o modifica la programación.
1. Especifique la frecuencia de entrega. Cada frecuencia permite diferentes personalizaciones.
1. Haga clic en **Enviar según lo programado**.

![](assets/send-file.JPG)

## Administrador de proyectos programados {#manager}

Los proyectos programados de Analysis Workspace se pueden administrar en **Analytics > Componentes > Proyectos programados**.

En el Administrador de proyectos programados, puede editar y eliminar la programación recurrente de proyectos. Busque una programación en la barra de búsqueda o utilizando las opciones de filtro en el carril izquierdo. Puede filtrar por etiqueta, programaciones aprobadas, propietarios, etc.

Las siguientes son acciones comunes en el administrador de proyectos programados:

| Acción | Descripción |
|---|---|
| **Editar programación** | Haga clic en el título de la programación para actualizar su configuración de entrega. |
| **Eliminar programación** | Seleccione el proyecto programado en la lista y, a continuación, haga clic en Eliminar en el menú. Esto eliminará la programación seleccionada para el proyecto; el proyecto en sí no se eliminará. |
| **Añadir etiquetas** | Seleccione el proyecto programado en la lista y, a continuación, elija “Etiqueta” o “Aprobar” para organizar las programaciones y facilitar su búsqueda. |
| **Ver las programaciones fallidas** | Vaya al carril izquierdo > Otros filtros > No se han podido ver las programaciones que han fallado. |
| **Ver las programaciones caducadas** | Vaya al carril izquierdo > Otros filtros > Caducado para ver las programaciones que han caducado. Haga clic en el título de la programación para configurar una nueva programación de entrega. |
| **Ver el ID de programación** | Vaya a las opciones de columna en la parte superior derecha y añada la columna ID de programación a la tabla. El ID de programación suele ser útil para la depuración. |

El Administrador de programación de proyectos muestra los artículos que ha creado un usuario en particular. Si la cuenta del usuario está desactivada en la aplicación, se detienen todos los envíos programados.

## Protección mediante contraseña de un proyecto programado {#password}

>[!NOTE]
>
>La opción de proteger con contraseña un proyecto programado solo aparece para los clientes de CJA que hayan adquirido la variable [Escudo sanitario](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) producto adicional.

Adobe utiliza la contraseña para cifrar proyectos programados, independientemente de si se envían en formato .pdf o .csv.

Una vez que su empresa ha adquirido el SKU del Escudo de salud y se ha habilitado para él, aparece el mensaje para crear una contraseña para un proyecto programado en dos circunstancias:

* Cuando alguien crea un nuevo proyecto programado.

* Cuando un proyecto programado existente está a punto de enviarse. El proyecto programado actualmente se deshabilitará hasta que se establezca la protección con contraseña. El propietario del proyecto programado recibirá un correo electrónico con este fin.

![protección de contraseña](assets/password.png)

### Requisitos de contraseña

Los requisitos de contraseña se ajustan al estándar de Adobe y requieren un mínimo de 8 caracteres con al menos un número y un carácter especial.

### Nuevo proyecto programado

1. Una vez guardado el proyecto, vaya a Compartir > Enviar archivo ahora o Compartir > Enviar archivo según lo programado.
1. Siga las instrucciones anteriores, en Compartir archivo ahora o Compartir archivo según lo programado.

### Proyecto programado existente

Antes de la hora en la que se programa un proyecto, el propietario del proyecto recibirá un correo electrónico similar al siguiente:

![email](assets/email-password.png)

1. Haga clic en **[!UICONTROL Ver proyecto programado]**.
1. En el **[!UICONTROL Editar proyecto programado]** , introduzca y vuelva a introducir una contraseña.
1. Informar (solo) a los destinatarios del proyecto programado de esta contraseña.


