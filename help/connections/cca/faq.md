---
title: Preguntas más frecuentes sobre análisis de Canal cruzado
description: Preguntas más frecuentes sobre Análisis de Canales cruzados
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 93%

---


# Preguntas frecuentes

## ¿Cómo puedo usar CCA para ver cómo se mueve la gente de un canal a otro?

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) y cree un proyecto de Workspace en blanco.
2. Haga clic en la pestaña Visualizaciones de la izquierda y arrastre una visualización de Flujo al lienzo de la derecha.
3. Haga clic en la pestaña Componentes de la izquierda y arrastre la dimensión ID de conjunto de datos a la ubicación central denominada Dimensión o elemento.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Puede utilizar un conjunto de datos de búsqueda si desea cambiar el nombre de los elementos de la dimensión de ID de conjunto de datos.

## ¿Cuánto tiempo atrás vuelve CCA a generar las claves de los visitantes?

La ventana retrospectiva para la regeneración de claves depende de la frecuencia deseada de [reproducción](replay.md) de los datos. Por ejemplo, si configura CCA para que reproduzca los datos una vez por semana, la ventana retrospectiva para la regeneración de claves será de 7 días. Si configura CCA para que reproduzca datos todos los días, la ventana retrospectiva para la regeneración de claves será de 1 día.

## ¿Cómo se gestionan los dispositivos compartidos?

En algunas situaciones es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID transitorio anula al ID persistente, por lo que los dispositivos compartidos se consideran personas independientes (incluso si se originan en el mismo dispositivo).

## ¿Cómo gestiona CCA las situaciones en las que una sola persona tiene un gran número de ID persistentes?

En algunas situaciones, un usuario individual puede tener asociado un gran número de ID persistentes. Algunos ejemplos de esto son las personas que borran las cookies del explorador con frecuencia o que utilizan el modo privado/de incógnito del explorador.

El número de ID persistentes es irrelevante en favor del ID transitorio. Un solo usuario puede pertenecer a numerosos dispositivos sin que ello afecte a la capacidad de CCA para crear vínculos entre los diferentes dispositivos.

## Tras contactar con el administrador de cuentas y proporcionarle la información deseada, ¿cuánto tarda en estar disponible el conjunto de datos cuya clave se ha vuelto a generar?

La costura en vivo está disponible aproximadamente 1 semana después de que el Adobe active Análisis de Canales cruzados. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1000 millones de eventos por día) pueden tardar una semana o más.

## ¿Cómo gestiona Analytics entre Canales las solicitudes de RGPD y CPA?

Adobe gestiona las solicitudes del RGPD y CCPA de conformidad con las leyes locales e internacionales. Adobe ofrece el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es-ES) para enviar solicitudes de acceso a datos y de eliminación. Las solicitudes se aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.
