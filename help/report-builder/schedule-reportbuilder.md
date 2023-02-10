---
title: Programación de libros mediante Report Builder en Customer Journey Analytics
description: Describe cómo utilizar la función de programación en Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: cd3ed8873619c7fb5281d42b1f74c32b245400d0
workflow-type: ht
source-wordcount: '1078'
ht-degree: 100%

---

# Programar libros de trabajo

Después de guardar un libro y completar el análisis, puede compartir fácilmente el libro con otros integrantes del equipo mediante la función de programación. La función Programación permite crear una programación que actualice automáticamente los datos del libro y envíe el archivo .xlsx del libro de Excel como datos adjuntos a la audiencia especificada en una fecha y hora específicas. La configuración de una programación proporciona a los destinatarios actualizaciones regulares de forma automática. También puede utilizar la función de programación para enviar el libro una vez sin programar actualizaciones automáticas.

Puede crear varias programaciones para un solo libro. Por ejemplo, puede enviar un libro a su equipo diariamente y enviarlo al administrador una vez a la semana creando dos programaciones diferentes.

La función Programación también permite configurar la protección con contraseña para un libro y editar los libros programados previamente.

>[!VIDEO](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on)

## Programar un libro

Utilice el botón Programar tarea del centro de Report Builder para crear rápidamente una programación de modo que pueda distribuir automáticamente un archivo de Excel de libro (.xlsx) a un individuo o a un grupo.

1. Haga clic en el botón Programar en el centro del Report Builder.

   ![](./assets/schedule-button.png){width="55%"}

1. Haga clic en Programar libro o en el botón de signo más en la parte superior izquierda para crear un nuevo libro programado.

   ![Descripción alt.](./assets/schedule-workbook.png){width="55%"}

   El panel de programación muestra información predefinida sobre el libro, como el nombre del libro y la última fecha de modificación del libro.

   ![Descripción alt.](./assets/schedule-pane.png){width="55%"}

1. (Opcional) Introduzca un nombre de archivo.

   El nombre de archivo del libro es el nombre predeterminado del libro, pero puede cambiarlo, si quiere. Si envía el mismo libro a varias audiencias y desea ponerle un nombre un poco más descriptivo para una audiencia determinada, puede cambiar el nombre.

1. (Opcional) Seleccione **Adjuntar marca temporal al nombre del archivo**.

   Puede adjuntar una marca temporal al nombre del archivo para identificar la fecha en que se actualizó el libro. Esto resulta útil para ver rápidamente qué versión de un libro se envió en una fecha específica. La **Vista previa del nombre de archivo** muestra cómo aparecerá el nombre del archivo del libro en el correo electrónico cuando se distribuya el libro. El formato de la marca temporal es AAAA-MM-DD.

1. (Opcional) Seleccione **Compresión .zip** para comprimir el archivo y configurar la protección con contraseña en el archivo.

   Cuando realice esta selección, se le pedirá que introduzca una contraseña para abrir el archivo. Esto resulta útil si le preocupa la seguridad de los datos y desea proteger el libro con contraseña. La protección del archivo con una contraseña requiere que seleccione **Compresión .zip**. La contraseña debe tener al menos ocho caracteres y contener un número y un carácter especial.

   ![Descripción alt.](./assets/zip-compression.png){width="55%"}

1. Introduzca los **Destinatarios**. Puede introducir el nombre de una persona reconocida en su organización, o una dirección de correo electrónico de una persona interna o externa de la organización.

1. Introduzca el **Asunto** del correo electrónico y una descripción para sus destinatarios. El asunto adopta como valor predeterminado el nombre de archivo del libro, pero puede modificarlo si es necesario. Puede agregar detalles en la sección de descripción.

   ![Descripción alt.](./assets/recipients-subject.png){width="55%"}

1. Configure las opciones de programación para establecer la fecha y la hora en que desea que el libro se envíe por correo electrónico a los destinatarios.

   Elija los intervalos de fecha y hora de inicio y fin. Puede ser la fecha de hoy o una fecha futura.

   Elija la **Frecuencia** en el menú desplegable. Puede establecer que la frecuencia sea horaria, diaria, semanal, mensual o anual en un día específico. Por ejemplo, puede configurar una programación para enviar el libro el primer domingo por la noche del mes de modo que los destinatarios tengan el correo electrónico en su bandeja de entrada el lunes por la mañana.

   ![Descripción alt.](./assets/frequency.png){width="55%"}

1. Después de configurar la programación, haga clic en **Enviar según lo programado**.

   ![Descripción alt.](./assets/send-on-schedule.png){width="55%"}

   Verá una notificación de confirmación en la parte inferior del centro de Report Builder y el libro programado se mostrará en la pestaña Libros.

   ![Descripción alt.](./assets/confirmation-toast.png){width="55%"}

## Enviar el libro solo una vez

También puede enviar el libro solo una vez.

1. Desmarque **Mostrar opciones de programación**.

   ![Descripción alt.](./assets/send-now.png){width="40%"}

1. Haga clic en **Enviar ahora**.

## Ver y editar libros programados

Puede ver y administrar todos los libros programados en un mismo lugar en la pestaña Libros.

1. En la sección Programación del centro de Report Builder, haga clic en la pestaña Libros. Utilice esta vista para ver una lista de todos los libros programados.

1. Seleccione un libro. Se muestran varias herramientas que permiten editar el libro de trabajo, cambiar la programación, pausar y reiniciar la programación o eliminar la programación.

   ![Descripción alt.](./assets/edit-icons.png){width="55%"}

* (Opcional) Haga clic en el icono de lápiz para editar la programación del libro de trabajo.

* (Opcional) Haga clic en el icono de reloj para ver el historial de cada tarea programada.

* (Opcional) Haga clic en el icono de pausa para pausar y reiniciar la programación de distribución. Esto resulta útil si necesita modificar el libro antes de enviarlo. Vuelva a hacer clic en el icono de pausa cuando desee reiniciar la distribución.

* (Opcional) Haga clic en la papelera para eliminar la programación.

## Revisar el estado de las tareas programadas

La vista de historial permite revisar el estado de cada tarea programada. Hay una fila independiente que documenta el cambio de estado para cada tarea programada. En el ejemplo que se muestra a continuación, *Nuevo programa por hora* se inició el 5 de enero a las 15:04. A las 15:05 se actualizó correctamente y se envió a los destinatarios. Con el libro siguiente, *Libro incorrecto*, se ha generado un error durante el proceso de actualización. Si un libro no se ha podido enviar, la pestaña del historial le ayuda a solucionar problemas al mostrar en qué parte del proceso se produjo el error. En este caso, es probable que se deba a algún error de bloque de datos, tal vez a un componente que falta, que evitó que el libro se actualizara correctamente.

Una marca de verificación verde indica que el libro se envió correctamente. Un signo de exclamación en un triángulo rojo indica que se ha producido un error.

Puede elegir las columnas que quiere mostrar en la pestaña historial haciendo clic en el icono de configuración de columnas, a la derecha de la barra de búsqueda.

![Descripción alt.](./assets/history.png){width="55%"}

Puede filtrar el historial para ver solo el de un único libro programado. Para ello, vaya a la pestaña Libros, seleccione el libro y haga clic en el icono de historial.

También puede ver el historial de un libro específico desde la pestaña Libros. En la pestaña Libros, seleccione el libro y haga clic en el icono de historial.

![Descripción alt.](./assets/history2.png){width="55%"}

El filtro de libro aparece en la parte superior del historial. Para volver a ver el historial de todas las tareas programadas, haga clic en la X junto al filtro.

![Descripción alt.](./assets/history3.png){width="55%"}
