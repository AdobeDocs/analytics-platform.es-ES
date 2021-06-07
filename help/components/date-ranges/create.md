---
title: Crear un intervalo de fecha
description: Cree un intervalo de fechas para utilizarlo en los informes.
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 8%

---

# Crear un intervalo de fecha

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Puede crear un intervalo de fechas personalizado mediante cualquiera de los dos métodos siguientes:

* Directamente en un proyecto de espacio de trabajo haciendo clic en el botón &#39;`+`&#39; situado junto a la lista de componentes de intervalo de fechas a la izquierda
* Dentro del administrador de intervalos de fechas

Para crear un intervalo de fechas en el administrador de intervalos de fechas:

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) con sus credenciales de Adobe ID.
1. Vaya a [!UICONTROL Componentes] > [!UICONTROL Intervalos de fechas].
1. Haga clic en el botón [!UICONTROL Add] para abrir la ventana modal que crea un intervalo de fechas.

## Creación de una ventana modal de intervalo de fechas

La ventana modal tiene cuatro campos que se pueden editar:

* **Intervalo** de fechas: El intervalo de fechas que desee para este componente.
* **Título**: El nombre que desea para este componente. El título se utiliza en proyectos de espacio de trabajo.
* **Descripción**: La descripción que desea para este componente. La descripción se ve al hacer clic en el icono ![i](../assets/i.png).
* **Etiquetas**: Utilice las etiquetas para organizar los intervalos de fechas. Un intervalo de fechas puede pertenecer a varias etiquetas.

## Selección de un intervalo de fechas

Al hacer clic en el intervalo de fechas en la ventana modal, tiene varias opciones:

* **Calendario**: Seleccione la fecha de inicio y la de finalización.
* **Usar fechas** móviles: Marque esta casilla si desea que el intervalo de fechas cambie con el transcurso del tiempo. No marque esta casilla si desea que el intervalo de fechas permanezca estático.
* **Seleccionar ajuste preestablecido**: Utilice este menú desplegable si desea un intervalo de fechas personalizado basado en un intervalo que ofrezca el Adobe de forma predeterminada. Al seleccionar un ajuste preestablecido, puede personalizar aún más el intervalo de fechas para adaptarlo a sus necesidades. No afecta al ajuste preestablecido que ofrece el Adobe.

## Intervalos de fechas móviles

Si desea un intervalo de fechas móvil, puede personalizar el momento en que se desplaza. Puede controlar cuándo se rompen las fechas de inicio y finalización de forma independiente.

* **Cuando comienza** la fecha: Seleccione si la fecha comienza al principio de un período de tiempo, al final de un período de tiempo o utiliza un día fijo.
* **El periodo de tiempo que se va a usar**: Elija la frecuencia con la que se desplaza el intervalo de fechas. Se puede hacer rodar todos los días, cada semana, cada mes, cada trimestre o cada año.
* **Desplazamiento**: Elija el desplazamiento del intervalo de fechas. Puede agregar o restar días, semanas, meses, trimestres o años.

## Ejemplos de fechas móviles

Algunos intervalos de fechas pueden ser útiles en algunos informes.

Año hasta la fecha:

```text
Start: Start of current year
End: End of current day
```

El jueves pasado a este jueves:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Ejercicio fiscal (por ejemplo, si un año fiscal comienza en diciembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
