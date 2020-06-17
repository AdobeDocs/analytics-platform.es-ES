---
title: Crear un intervalo de fecha
description: Cree un intervalo de fechas para utilizarlo en sistema de informes.
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---


# Crear un intervalo de fecha

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Puede crear un intervalo de fechas personalizado mediante cualquiera de los dos métodos siguientes:

* Directamente en un proyecto de área de trabajo haciendo clic en el botón &#39;`+`&#39; al lado de la lista de los componentes de intervalo de fechas a la izquierda
* Dentro del administrador de intervalos de fechas

Para crear un intervalo de fechas en el administrador de intervalos de fechas:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Vaya a [!UICONTROL Componentes] > Intervalos [!UICONTROL de fechas].
1. Haga clic en el botón [!UICONTROL Añadir] para abrir la ventana modal que crea un intervalo de fechas.

## Creación de una ventana modal de intervalo de fechas

La ventana modal tiene cuatro campos que puede editar:

* **Intervalo** de fechas: Intervalo de fechas deseado para este componente.
* **Título**: El nombre que desea para este componente. El título se utiliza en proyectos de espacio de trabajo.
* **Descripción**: La descripción que desea para este componente. La descripción se muestra al hacer clic en el icono ![i](../assets/i.png) .
* **Etiquetas**: Utilice las etiquetas para organizar los intervalos de fechas. Un intervalo de fechas puede pertenecer a varias etiquetas.

## Selección de un intervalo de fechas

Al hacer clic en el intervalo de fechas en la ventana modal, tiene varias opciones:

* **Calendario**: Seleccione el inicio y la fecha de finalización.
* **Usar fechas** móviles: Marque esta casilla si desea que el intervalo de fechas cambie con el transcurso del tiempo. No marque esta casilla si desea que el intervalo de fechas permanezca estático.
* **Seleccionar ajuste preestablecido**: Utilice este menú desplegable si desea un intervalo de fechas personalizado basado en un intervalo que Adobe oferta de forma predeterminada. Al seleccionar un ajuste preestablecido, puede personalizar aún más el intervalo de fechas para adaptarlo a sus necesidades. No afecta al ajuste preestablecido que Adobe oferta.

## Intervalos de fechas móviles

Si desea un intervalo de fechas móvil, puede personalizar el momento en que se desplaza. Puede controlar cuándo se rompen las fechas de inicio y finalización de forma independiente.

* **Cuando la fecha inicio**: Seleccione si la fecha inicio al comienzo de un período de tiempo, al final de un período de tiempo o utiliza un día fijo.
* **Período de tiempo que se debe utilizar**: Elija la frecuencia con la que se desplaza el intervalo de fechas. Se puede hacer rodar todos los días, cada semana, cada mes, cada trimestre o cada año.
* **Desplazamiento**: Elija el desplazamiento del intervalo de fechas. Puede agregar o restar días, semanas, meses, trimestres o años.

## Ejemplos de fechas móviles

Algunos intervalos de fechas pueden ser útiles en ciertos informes.

Año hasta la fecha:

```text
Start: Start of current year
End: End of current day
```

Último jueves a este jueves:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Ejercicio fiscal (por ejemplo, si un año fiscal inicio en diciembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
