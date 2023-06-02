---
title: Crear un intervalo de fecha
description: Crear un intervalo de fecha para utilizarlo en los informes.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: be49bcbbc9d1b7d3989e15a30114da8cbc5e4851
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 91%

---

# Crear un intervalo de fecha

Puede crear un intervalo de fechas utilizando cualquiera de los dos métodos siguientes:

* Directamente en un proyecto de Workspace al hacer clic en el botón `+` situado junto a la lista de componentes de intervalo de fecha, a la izquierda.
* Dentro del administrador de intervalos de fechas

Para crear un intervalo de fecha en el administrador de intervalos de fechas:

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) con sus credenciales de Adobe ID.
1. Vaya a [!UICONTROL Componentes] > [!UICONTROL Intervalos de fechas].
1. Haga clic en el botón [!UICONTROL Añadir] para abrir la ventana modal que crea un intervalo de fecha.

## Crear una ventana modal de intervalo de fecha

La ventana modal tiene cuatro campos que se pueden editar:

* **Intervalo de fecha**: el intervalo de fecha que desee para este componente.
* **Título**: el nombre que desee para este componente. El título se utiliza en proyectos de Workspace.
* **Descripción**: la descripción que desee para este componente. La descripción se ve al hacer clic en el icono ![i](../assets/i.png).
* **Etiquetas**: utilice las etiquetas para organizar los intervalos de fechas. Un intervalo de fecha puede pertenecer a varias etiquetas.

## Seleccionar un intervalo de fecha

Al hacer clic en el intervalo de fecha en la ventana modal, tiene varias opciones:

* **Calendario**: seleccione la fecha de inicio y la de finalización.
* **Usar fechas móviles**: marque esta casilla si desea que el intervalo de fecha cambie con el transcurso del tiempo. No marque esta casilla si desea que el intervalo de fecha permanezca estático.
* **Seleccionar ajuste preestablecido**: utilice esta selección desplegable si desea un intervalo de fechas personalizado basado en un intervalo que ofrezca el Adobe de forma predeterminada. Al seleccionar un ajuste preestablecido, puede personalizar aún más el intervalo de fecha para adaptarlo a sus necesidades. No afecta al ajuste preestablecido que ofrece Adobe.

## Intervalos de fechas móviles

Si desea un intervalo de fecha móvil, puede personalizar el momento en que se desplaza. Puede controlar cuándo varían las fechas de inicio y finalización de forma independiente.

* **Cuando comienza la fecha**: seleccione si la fecha comienza al principio de un periodo de tiempo, al final de un periodo de tiempo o establezca un día fijo.
* **El periodo de tiempo que se va a usar**: elija la frecuencia con la que se desplaza el intervalo de fecha. Puede variar todos los días, cada semana, cada mes, cada trimestre o cada año.
* **Desplazamiento**: elija el desplazamiento del intervalo de fechas. Puede añadir o restar días, semanas, meses, trimestres o años.

## Ejemplos de fechas móviles

Algunos intervalos de fechas pueden ser útiles en ciertos informes.

Año hasta la fecha:

```text
Start: Start of current year
End: End of current day
```

Del jueves pasado a este jueves:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Ejercicio fiscal (por ejemplo, si un año fiscal comienza en diciembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
