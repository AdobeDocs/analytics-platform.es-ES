---
description: Comprenda las funcionalidades de creación de informes en tiempo real en Customer Journey Analytics.
title: Información general de informes en tiempo real
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: e7a7a297e303a410c73598f373219644e50ede74
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Resumen de informes en tiempo real

La creación de informes en tiempo real en Customer Journey Analytics muestra y actualiza datos y visualizaciones en uno o varios paneles de Analysis Workspace en tiempo real.

{{release-limited-testing}}

{{ultimate-package}}

## Casos de uso

Esta sección proporciona información general sobre los casos de uso habituales y menos valiosos. Y también información sobre cuándo no considerar la creación de informes en tiempo real.

* Los casos de uso más valiosos para los informes en tiempo real son las principales ventas, promociones o lanzamientos de productos.
Como parte de ese lanzamiento, desea saber lo siguiente:

   * ¿Cómo se comparan las ventas con su última venta?
   * ¿En qué se diferencia este lanzamiento de producto del último?
   * ¿Funcionan realmente tus promociones para este importante día o evento?

* Los casos de uso relevantes, pero menos valiosos, para la creación de informes en tiempo real son los casos de uso de validación.
Desea validar, por ejemplo:

   * ¿Funciona realmente el recorrido de campaña que ha iniciado recientemente?
   * Cuando se lanzó la nueva página de productos, ¿está recopilando datos de clientes de la página?
   * ¿Funciona correctamente su evento de medios en directo?

No considere la creación de informes en tiempo real para las operaciones que supervisan casos de uso. Por ejemplo, para responder a la pregunta: ¿está funcionando realmente un sitio?


## Definición

El aspecto en tiempo real de los informes en tiempo real para Customer Journey Analytics se define como los datos y las visualizaciones que se actualizan en un plazo aproximado de 5 minutos desde el momento en que se incorporan los datos subyacentes a través de la conexión asociada.

## Limitaciones

Debe tener en cuenta la siguiente limitación para los informes en tiempo real:

* Los informes en tiempo real solo incluyen datos disponibles en un periodo móvil de 24 horas. Los datos que cruzan este periodo móvil de 24 horas no están disponibles.
* La atribución, la segmentación, las métricas calculadas y mucho más solo funcionan en los datos disponibles dentro del período móvil de 24 horas.
* La creación de informes en tiempo real funciona mejor con datos de nivel de evento y sesión, y debe tener cuidado al utilizar la creación de informes en tiempo real con datos de nivel de persona. <!--Need to explain this a bit better --> Dado que solo los eventos del período móvil de 24 horas están disponibles para los informes en tiempo real, el historial de eventos de una persona también se limita a esta ventana. Tenga en cuenta la preferencia para los datos de nivel de evento y de sesión al seleccionar dimensiones y métricas (calculadas). Y cuando utiliza funcionalidades como desgloses, siguiente o anterior, y más en el panel habilitado para la actualización en tiempo real.
* No se puede combinar la vinculación con los informes en tiempo real. <!-- Do we need to explain this in more detail, why? --> Como se mencionó anteriormente, los informes en tiempo real se refieren a los datos de nivel de evento y sesión, y no tanto a los datos basados en personas.
* No hay métricas de medios recopilados de Heartbeat disponibles, a excepción de las métricas de inicio y cierre de medios. Por lo tanto, puede seguir utilizando los informes en tiempo real para habilitar un caso de uso de medios.
