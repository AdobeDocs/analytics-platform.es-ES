---
title: Configuración de Report Builder en Customer Journey Analytics
description: Describe cómo configurar el Report Builder en CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: e76f6cbb8ecf2032a8211d1c6bd18a79c2a6f5d2
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---


# Configuración del Report Builder

Puede acceder rápidamente al Report Builder mediante el menú Complemento de Excel.

## Requisitos

Report Builder para Customer Journey Analytics es compatible con los siguientes sistemas operativos y navegadores web.

### macOS

- macOS versión 10.x o posterior
- Todas las versiones de Excel

### Windows

- Windows 10, versión 1904 o posterior
- Excel versión 2106 o posterior

   Todos los usuarios de Excel de escritorio de Windows deben instalar Microsoft Edge Webview2 para utilizar el complemento. Para instalar el controlador:

   1. Vaya a <http://aka.ms/webview2installer>.
   1. Seleccione y descargue el instalador independiente Evergreen.
   1. Siga las instrucciones de instalación.

### Web Office

- Admite todos los exploradores y versiones


## Complemento de Excel de Report Builder

Debe instalar el complemento de Excel de Report Builder para utilizar Report Builder para Customer Journey Analytics. Una vez instalado el complemento de Excel de Report Builder, puede acceder a Report Builder desde un libro de Excel abierto.

### Descargar e instalar el complemento de Report Builder

Para descargar e instalar el complemento de Report Builder

1. Inicie Excel y abra un nuevo libro.

1. Seleccione Insertar > Obtener complementos.

1. En el cuadro de diálogo Complementos de Office, seleccione la ficha Almacenar .

1. Busque &quot;Report Builder&quot; y haga clic en Agregar.

1. En el cuadro de diálogo Términos de licencia y política de privacidad, haga clic en Continuar.

**Si no se muestra la pestaña Tienda**

1. En Excel, seleccione Archivo > Cuenta > Administrar configuración.

1. Marque la casilla junto a &quot;Habilitar experiencias conectadas opcionales&quot;.

1. Reinicie Excel.

**Si su organización bloquea el acceso a la tienda Microsoft**

Póngase en contacto con su equipo de TI o de seguridad para solicitar la aprobación del complemento del Report Builder. Una vez concedida la aprobación, en el cuadro de diálogo Complementos de Office, seleccione la pestaña Administración administrada .

![](./assets/image1.png)

Después de instalar el complemento del Report Builder, el icono del Report Builder se muestra en la cinta de Excel debajo de la ficha Inicio.

![](./assets/rb_app_icon.png)

## Iniciar sesión en el Report Builder

Después de instalar el complemento de Report Builder for Excel para su plataforma operativa o explorador, siga estos pasos para iniciar sesión en Report Builder.

1. Abra un libro de Excel.

1. Haga clic en el icono del Report Builder para iniciar el Report Builder.

1. En la barra de herramientas de Adobe Report Builder, haga clic en **Login**.

   ![](./assets/rb_login.png)

1. Introduzca la información de la cuenta de Adobe Experience ID. La información de la cuenta debe coincidir con las credenciales del Customer Journey Analytics.

   ![](./assets/image4.png)

Después de iniciar sesión, el icono de inicio de sesión y la organización aparecerán en la parte superior del panel

## Cambiar organizaciones

La primera vez que inicie sesión, iniciará sesión en la organización predeterminada asignada a su perfil.

1. Haga clic en el nombre de la organización que se muestra cuando inicia sesión.

1. Seleccione una organización de la lista de organizaciones disponibles. Solo aparecen en la lista las organizaciones a las que tiene acceso.

   ![](./assets/image5.png)

## Cerrar sesión

Puede cerrar la sesión desde el Report Builder desde el perfil de usuario.

1. Guarde los cambios en los libros abiertos.

1. Haga clic en el icono de avatar para mostrar su perfil de usuario.

   ![](./assets/image6.png)

1. Haga clic en **Cerrar sesión**.
