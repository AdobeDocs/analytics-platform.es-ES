---
title: Crear y publicar audiencias en el Perfil del cliente en tiempo real
description: Obtenga información sobre cómo publicar audiencias desde Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: e117775aa949b3d471e708ca5559474af76d28bc
workflow-type: tm+mt
source-wordcount: '1389'
ht-degree: 70%

---

# Crear y publicar audiencias

En este tema se explica cómo crear y publicar audiencias identificadas en Customer Journey Analytics (CJA) para el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) en Adobe Experience Platform para la segmentación y personalización de clientes.

Lea esta [información general](/help/components/audiences/audiences-overview.md) para familiarizarse con el concepto de audiencias de CJA.

## Crear audiencias {#create}

1. Para crear audiencias, tiene tres maneras de empezar:

   | Método de creación | Detalles |
   | --- | --- |
   | Desde el menú principal **[!UICONTROL Componentes] > [!UICONTROL Audiencias]** | Se abre la página Administrador de audiencias. Haga clic en **[!UICONTROL Crear audiencia]** para que se abra el [!UICONTROL Generador de audiencias]. |
   | Desde una tabla de forma libre | Haga clic con el botón derecho en un elemento de una tabla de forma libre y seleccione **[!UICONTROL Crear una audiencia a partir de la selección]**. Mediante este método se rellena previamente el filtro con la dimensión o el elemento de dimensión que haya seleccionado en la tabla. |
   | Desde la interfaz de usuario de creación/edición de filtros | Marque la casilla que dice **[!UICONTROL Crear una audiencia a partir de este filtro]**. Mediante este método se rellena previamente el filtro. |

   {style=&quot;table-layout:auto&quot;}

1. Cree la audiencia.

   Configure estos ajustes para poder publicar la audiencia.

   ![](assets/create-audience.png)

   | Configuración | Descripción |
   | --- | --- |
   | [!UICONTROL Nombre] | El nombre de la audiencia. |
   | [!UICONTROL Etiquetas] | Las etiquetas que quiera asignar a la audiencia con fines organizativos. Puede utilizar una etiqueta preexistente o introducir una nueva. |
   | [!UICONTROL Descripción] | Agregue una buena descripción de la audiencia para diferenciarla de otras. |
   | [!UICONTROL Frecuencia de actualización] | La frecuencia con la que desea actualizar la audiencia.<ul><li>Puede elegir crear una audiencia única (opción predeterminada) que no necesite ninguna actualización. Por ejemplo, esto podría resultar útil para campañas únicas concretas.</li><li>Puede seleccionar otros intervalos de actualización. Para la frecuencia de actualización de 4 horas, hay un límite de 75 a 150 actualizaciones de audiencia, según la asignación de CJA.</li></ul> |
   | Fecha de caducidad | Cuando la audiencia deje de actualizarse. El valor predeterminado es 1 año a partir de la fecha de creación. Las audiencias que caducan se tratan de manera similar a los informes programados que caducan: el administrador recibe un correo electrónico un mes antes de que la audiencia caduque. |
   | Actualizar ventana de retrospección | Especifica cuánto tiempo en la ventana de datos va a retroceder al crear la audiencia. El máximo es de 90 días. |
   | [!UICONTROL Intervalo de fecha único] | Intervalo de fecha en el que desea que se publique la audiencia única. |
   | [!UICONTROL Filtro] | Los filtros son la entrada principal a la audiencia. Se pueden agregar hasta 20 filtros. Estos filtros se pueden unir con los operadores `And` o `Or`. |
   | [!UICONTROL Ver ID de muestra] | Una muestra de los ID de esta audiencia. Utilice la barra de búsqueda para buscar ID de ejemplo. |

   {style=&quot;table-layout:auto&quot;}

1. Interprete la vista previa de datos.

   La vista previa de la audiencia aparece en el carril derecho. Permite realizar un análisis resumido de la audiencia que ha creado.

   ![](assets/data-preview.png)

   | Configuración de la vista previa | Descripción |
   | --- | --- |
   | Ventana [!UICONTROL Vista previa de datos] | El intervalo de fecha de la audiencia. |
   | [!UICONTROL Personas totales] | Un número de resumen del total de personas en esta audiencia. Puede llegar a los 20 millones de personas. Si la audiencia supera los 20 millones de personas, debe reducir el tamaño de la audiencia para poder publicarla. |
   | [!UICONTROL Límite de tamaño de audiencia] | Muestra a qué distancia del límite de 20 millones está esta audiencia. |
   | [!UICONTROL Retorno estimado de la audiencia] | Esta configuración es útil para volver a dirigirse a los clientes de esta audiencia que regresan al sitio. (En otras palabras, que se ven de nuevo en este conjunto de datos). <p>Aquí puede seleccionar el lapso de tiempo (7 días siguientes, 2 semanas siguientes, mes siguiente) para la cantidad estimada de clientes que es posible que regresen. |
   | [!UICONTROL Estimación de retorno] | Este número proporciona un número estimado de clientes que regresan durante el lapso de tiempo seleccionado en la lista desplegable. Para predecir este número, miramos la tasa de pérdida histórica para esta audiencia. |
   | [!UICONTROL Previsualizar métricas] | Esta configuración le permite mirar métricas concretas para ver si esta audiencia contribuye en una cantidad desproporcionada a esta métrica, como «[!UICONTROL Ingresos]» o «[!UICONTROL Promedio de tiempo en el sitio]». Proporciona el recuento agregado de la métrica, así como el porcentaje del total que representa. Puede seleccionar cualquier métrica que esté disponible en la vista de datos. |
   | [!UICONTROL Espacios de nombres incluidos] | Los espacios de nombres específicos asociados a las personas de la audiencia. Algunos ejemplos son ECID, CRM ID, direcciones de correo electrónico, etc. |
   | [!UICONTROL Zona protegida] | La [zona protegida de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) en la que reside esta audiencia. Cuando publica esta audiencia en Platform, solo puede trabajar con ella dentro de los límites de esta zona protegida. |

   {style=&quot;table-layout:auto&quot;}

1. Compruebe la configuración de la audiencia y haga clic en **[!UICONTROL Publicar]**.

   Si todo salió bien, recibirá un mensaje de confirmación conforme se ha publicado la audiencia. La audiencia solo tardará un minuto o dos en mostrarse en Experience Platform. (Incluso las audiencias con millones de miembros deberían tardar menos de 5 minutos).

1. Haga clic en **[!UICONTROL Ver la audiencia en AEP]** dentro del mismo mensaje y se le redirigirá a la [Interfaz de usuario de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=es) en Adobe Experience Platform. Para obtener más información, vaya más abajo.

## ¿Qué sucede después de crear una audiencia? {#after-audience-created}

Después de crear una audiencia, Adobe crea un segmento de flujo continuo de Experience Platform para cada nueva audiencia de CJA. Solo se creará un segmento de flujo continuo de AEP si su organización está configurada para la segmentación de flujo continuo.

* El segmento de AEP comparte el mismo nombre/descripción que la audiencia de CJA, pero el nombre se adjuntará con el ID de audiencia de CJA para garantizar que sea único.
* Si cambia el nombre o la descripción de la audiencia de CJA, el nombre o la descripción del segmento de AEP también reflejarán ese cambio.
* Si un usuario elimina una audiencia de CJA, el segmento de AEP NO se elimina. La razón es que la audiencia de CJA puede ser posteriormente deseliminada.

## Consideraciones de latencia {#latency}

En varios puntos antes, durante y después de la publicación de la audiencia, pueden producirse latencias. A continuación se muestra una descripción general de las posibles latencias.

![](assets/latency-diagram.png)

| Punto de latencia | Duración de la latencia |
| --- | --- |
| Ingesta de datos en Data Lake | Hasta 30 minutos |
| Ingesta de datos de Experience Platform a CJA | Hasta 60 minutos |
| Publicación de audiencias en el Perfil del cliente en tiempo real | Menos de 5 minutos (según el tamaño de la audiencia) |
| Frecuencia de actualización para audiencias | <ul><li>Actualización única (latencia inferior a 5 minutos)</li><li>Actualizar cada 4 horas, diariamente, semanalmente, mensualmente (la latencia va de la mano con la velocidad de actualización) |

## Usar audiencias de CJA en Experience Platform {#audiences-aep}

CJA toma todas las combinaciones de espacio de nombres e ID de la audiencia publicada y las transmite al Perfil del cliente en tiempo real (RTCP). CJA envía la audiencia al Experience Platform con el conjunto de identidades principal, según lo que se haya seleccionado como [!UICONTROL ID de persona] cuando se configuró la conexión.

A continuación, el RTCP examina cada combinación de área de nombres e ID y busca un perfil del que pueda formar parte. Un perfil es básicamente un clúster de áreas de nombres, ID y dispositivos vinculados. Si encuentra un perfil, agregará el área de nombres y el ID a los demás ID de este perfil como un atributo de pertenencia a un segmento. Ahora, por ejemplo, «user@adobe.com» se puede dirigir a todos sus dispositivos y canales. Si no se encuentra un perfil, se crea uno nuevo.

Para ver las audiencias de CJA en Platform; para ello, vaya a **[!UICONTROL Segmentos]** > **[!UICONTROL Crear segmentos]** > pestaña **[!UICONTROL Audiencias]** > **[!UICONTROL Audiencias de CJA]**.

Puede arrastrar audiencias de CJA a la definición del segmento para segmentos de AEP.

![](assets/audiences-aep.png)

## Preguntas frecuentes {#faq}

Preguntas más frecuentes sobre la publicación de audiencias.

+++**¿Qué sucede si un usuario ya no es miembro de una audiencia en CJA?**

En este caso, se envía un evento de salida al Experience Platform desde CJA.

+++

+++**¿Qué sucede si elimina una audiencia en CJA?**

Cuando se elimina una audiencia de CJA, esta ya no aparecerá en la IU de Experience Platform. Sin embargo, en Platform no se eliminan perfiles asociados a esa audiencia.

+++

+++**Si no existe un perfil correspondiente en RTCDP, ¿se creará un nuevo perfil?**

Sí, lo hará.

+++

+++**¿CJA envía los datos de audiencia como eventos de canalización o como un archivo plano que también se dirige a un lago de datos?**

CJA transmite los datos a RTCP mediante canalización y estos datos también se recopilan en un conjunto de datos del sistema en el lago de datos.

+++

+++**¿Qué identidades envía CJA?**

Los pares de identidad/área de nombres que se usaron en la variable [Configuración de la conexión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#create-connection). Específicamente, el paso cuando un usuario selecciona el campo que desea utilizar como &quot;ID de persona&quot;.

+++

+++**¿Qué ID se elige como identidad principal?**

Véase más arriba. Solo enviamos una identidad por cada &quot;persona&quot; de CJA.

+++

+++**¿RTCP también procesa los mensajes CJA? ¿Puede CJA añadir identidades a un gráfico de identidad de perfil mediante el uso compartido de audiencias?**

No. Solo enviamos una identidad por &quot;persona&quot;, por lo que no habría bordes de gráficos para que el RTCP lo consuma.

+++

## Pasos siguientes

* Para administrar esta audiencia, vaya a la [interfaz de usuario de administración](/help/components/audiences/manage.md).
