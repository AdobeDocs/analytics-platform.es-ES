---
description: Cómo configurar usuarios para que utilicen la aplicación móvil de Analytics
title: Configuración de ejecutivos para que utilicen tableros
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 100%

---

# Configuración de usuarios ejecutivos para que utilicen tableros

En algunos casos, puede que los usuarios ejecutivos necesiten asistencia adicional para acceder a la aplicación y utilizarla. Esta sección presenta información que ayudará a los responsables a proporcionar esa asistencia.

## Comprobar que los usuarios de la aplicación pueden acceder a Adobe Analytics

1. Configure nuevos usuarios en la [Admin Console de Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=es).

1. Para poder compartir los cuadros de resultados, debe conceder a los usuarios de la aplicación permisos para acceder a componentes del cuadro de resultados como Analysis Workspace, las vistas de datos en los que se basan los informes de valoración, así como segmentos, métricas y dimensiones.

## Requisitos previos del sistema de los usuarios de la aplicación

Para garantizar que los usuarios ejecutivos tengan acceso a sus informes de valoración en la aplicación, asegúrese de que:

* El requisito mínimo del sistema operativo móvil de sus dispositivos sea iOS versión 10 o posterior, o Android versión 4.4 (KitKat) o posterior
* Tengan unas credenciales de inicio de sesión válidas para Adobe Analytics.
* Haya creado y compartido correctamente los informes de valoración móviles de los usuarios.
* Los usuarios tengan acceso a los componentes que se incluyen en el cuadro de resultados. Tenga en cuenta que, al compartir los cuadros de resultados, puede seleccionar la opción **[!UICONTROL Compartir los componentes incrustados]**.

## Ayuda para que los ejecutivos descarguen e instalen la aplicación

**Para usuarios ejecutivos con iOS:**

Haga clic en el siguiente vínculo (también está disponible en Analytics en **[!UICONTROL Herramientas]** > **[!UICONTROL Paneles de Analytics (aplicación móvil)]**) y siga las indicaciones para descargar, instalar y abrir la aplicación:

`[iOS link](https://apple.co/2zXq0aN)`

**Para usuarios ejecutivos con Android:**

Haga clic en el siguiente vínculo (también está disponible en Analytics en **[!UICONTROL Herramientas]** > **[!UICONTROL Paneles de Analytics (aplicación móvil)]**) y siga las indicaciones para descargar, instalar y abrir la aplicación:

`[Android link](https://bit.ly/2LM38Oo)`

Una vez descargada e instalada, los usuarios ejecutivos pueden iniciar sesión en la aplicación con sus credenciales de Adobe Analytics; la aplicación es compatible con Adobe ID y con Enterprise/Federated ID.

![Pantalla de bienvenida de la aplicación](assets/welcome.png)

## Ayuda para que los ejecutivos accedan al informe de valoración que ha creado

1. Haga que los usuarios ejecutivos inicien sesión en la aplicación.

   Aparece la pantalla **[!UICONTROL Elija una compañía]**. En esta pantalla se muestran las empresas de inicio de sesión a las que pertenece el usuario ejecutivo.

1. Haga que pulsen el nombre de la compañía de inicio de sesión o de la organización de Experience Cloud con la que acceder al cuadro de resultados que ha compartido.

   A continuación, la lista de cuadros de resultados muestra todos los cuadros de resultados que se han compartido con el usuario ejecutivo y a los que este tiene acceso a través de las credenciales de la empresa.

1. Ayude al usuario ejecutivo a ordenar esta lista por **[!UICONTROL Últimas modificaciones]**, si procede.

1. Haga que pulsen el nombre de un cuadro de resultados para verlo.

   ![Seleccione una empresa](assets/accesscard.png)


### Explicación de la IU del cuadro de resultados

Explique al usuario ejecutivo cómo aparecen los mosaicos en los cuadros de resultados compartidos.

![Explicación de los mosaicos](assets/newexplain.png)

![Ejemplo de informe de valoración](assets/intro_scorecard.png)

Información adicional sobre los mosaicos:

* La granularidad de los minigráficos depende de la longitud del intervalo de fecha:
* Si se selecciona un día se muestra una tendencia horaria
   * Si se selecciona más de un día y menos de un año, se muestra una tendencia diaria
   * Si se selecciona un año o más se muestra una tendencia semanal
   * La fórmula de la variación del valor porcentual es el total de la métrica (intervalo de fecha actual) – el total de la métrica (intervalo de fecha de comparación) / el total de la métrica (intervalo de fecha de comparación).
   * Puede arrastrar la pantalla hacia abajo para actualizar el informe de valoración.


1. Pulse un mosaico para mostrar el funcionamiento de un desglose detallado del mosaico.

   ![Vista de desglose](assets/sparkline.png)

   * Pulse cualquier punto de un minigráfico para ver los datos asociados a ese punto en la línea.

   * Se incluye una tabla para mostrar los datos de las dimensiones agregadas al mosaico. Pulse en la flecha hacia abajo para seleccionar dimensiones. Si no se ha agregado ninguna dimensión al mosaico, la tabla muestra los datos del gráfico.

1. Para cambiar los intervalos de fechas del cuadro de resultados, pulse el encabezado Fecha y seleccione la combinación de intervalo de fechas principal y de comparación que desee ver.

   ![Cambio de fechas](assets/changedate.png)

## Cambio de preferencias de aplicación

Para cambiar las preferencias, pulse la opción **[!UICONTROL Preferencias]** que se muestra arriba. En las preferencias, puede activar el inicio de sesión biométrico o puede establecer el modo oscuro de la aplicación, tal y como se muestra a continuación:

![Modo oscuro](assets/darkmode.png)

## Resolución de problemas

Si el usuario ejecutivo inicia sesión y ve un mensaje que indica que no se ha compartido nada:

![No se ha compartido nada](assets/nothing.png)

* Es posible que el usuario ejecutivo haya seleccionado una instancia incorrecta de Analytics o
* Es posible que el cuadro de resultados no se haya compartido con el usuario ejecutivo.

Compruebe que el usuario ejecutivo puede iniciar sesión en la instancia correcta de Adobe Analytics y que se ha compartido el cuadro de resultados.
