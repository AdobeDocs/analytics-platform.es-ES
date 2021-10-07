---
title: Configuración de Report Builder en CJA
description: Describe cómo establecer los ajustes de modo sin conexión, idioma, fecha y resolución de problemas.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: b655813816b2a8e0d47b035eefa11926f106ee0e
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---


# Configuración del Report Builder

Utilice el panel **Settings** para configurar las opciones de nivel de aplicación, como el idioma mostrado por la interfaz de usuario o si se va a trabajar o no en modo sin conexión. La configuración se aplica inmediatamente y se establece para todas las sesiones futuras hasta que se cambia.

Para cambiar la configuración del Report Builder

1. Haga clic en el icono **Settings**.

1. Realice cambios en el modo Activar sin conexión, seleccione un idioma o habilite la configuración del registro de resolución de problemas.

1. Haga clic en **Aplicar**.

   ![](./assets/image38.png)

## Modo sin conexión

Al crear y editar un bloque de datos en modo sin conexión, no se recuperan los datos. En su lugar, se utilizan datos de simulación para que se pueda crear y editar rápidamente un bloque de datos sin esperar a que se ejecute la solicitud. Cuando vuelva a estar en línea, el comando *Refresh data block* o *Refresh all data blocks* actualiza los bloques de datos que ha creado con los datos reales.

Para activar el modo sin conexión

1. Haga clic en el icono **Settings**.

1. Seleccione **Habilitar el modo sin conexión**.

1. Introduzca un entero positivo en el campo **Display metric data as**.

1. Haga clic en **Aplicar**.

## Idioma

Puede elegir el idioma de la IU del Report Builder. Todos los idiomas de Adobe Analytics admitidos están disponibles.

Para seleccionar el idioma utilizado en la interfaz de usuario del Report Builder

1. Haga clic en Configuración .

1. Seleccione un idioma en el menú desplegable **Language**.

   ![](./assets/image39.png)

1. Haga clic en **Aplicar.**

## Resolución de problemas

Utilice la configuración Resolución de problemas para registrar todos los datos de cliente/servidor en un archivo local. Utilice esta opción para ayudar a resolver los tickets de asistencia.

Para habilitar la opción Resolución de problemas, seleccione **Registrar solicitud del creador de informes en el archivo local**.
