---
title: Preguntas más frecuentes sobre análisis de canal cruzado
description: Preguntas más frecuentes sobre Análisis de canales cruzados
translation-type: tm+mt
source-git-commit: dd4e7e5cd04db6483f0e4a1f3161f23f8a5a8294
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 20%

---


# Preguntas frecuentes

## ¿Cómo puedo usar la CCA para ver cómo la gente se mueve de un canal a otro?

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) y cree un proyecto de Workspace en blanco.
2. Haga clic en la pestaña Visualizaciones de la izquierda y arrastre una visualización de Flujo al lienzo de la derecha.
3. Haga clic en la ficha Componentes de la izquierda y arrastre la dimensión &quot;Id. de conjunto de datos&quot; a la ubicación central denominada &quot;Dimension o elemento&quot;.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Si desea cambiar el nombre de los elementos de dimensión de ID de conjunto de datos, puede utilizar un conjunto de datos de búsqueda.

## ¿Cuánto tiempo atrás remite la CCA a los visitantes clave?

La ventana retroactiva para la reintroducción de claves depende de la frecuencia deseada de datos [repetición](replay.md). Por ejemplo, si configura CCA para que reproduzca los datos una vez por semana, la ventana retroactiva para la remercadotecnia será de 7 días. Si configura CCA para que reproduzca los datos todos los días, la ventana retrospectiva para la reintroducción de claves será de 1 día.

## ¿Cómo se gestionan los dispositivos compartidos?

En algunas situaciones es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID transitorio anula el ID persistente, por lo que los dispositivos compartidos se consideran personas independientes (incluso si se originan en el mismo dispositivo).

## ¿Cómo gestiona CCA las situaciones en las que una sola persona tiene un gran número de ID persistentes?

En algunas situaciones, un usuario individual puede asociarse con un gran número de ID persistentes. Algunos ejemplos son: una persona que borra las cookies del navegador con frecuencia o que utiliza el modo privado/de incógnito del explorador.

El número de ID persistentes es irrelevante en favor del ID transitorio. Un solo usuario puede pertenecer a cualquier número de dispositivos sin afectar a la capacidad de la CCA para unir dispositivos.

## Una vez que me comunico con el administrador de mi cuenta con la información deseada, ¿cuánto tarda en estar disponible el conjunto de datos rekeyed?

La costura en vivo está disponible aproximadamente 1 semana después de que el Adobe active Análisis de canales cruzados. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1.000 millones de eventos por día) pueden tardar una semana o más.

## ¿Cómo gestiona Analytics entre canales las solicitudes de RGPD y CPA?

El Adobe se ocupa de las solicitudes del RGPD y de la CCPA de conformidad con las leyes locales e internacionales. Adobe oferta el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) para enviar solicitudes de acceso y eliminación de datos. Las solicitudes se aplican tanto a los conjuntos de datos originales como a los restringidos.
