---
title: Crear y publicar audiencias en el Perfil del cliente en tiempo real
description: Obtenga información sobre cómo publicar audiencias desde Customer Journey Analytics
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 10%

---


# Crear y publicar audiencias

En este tema se explica cómo publicar audiencias descubiertas en Customer Journey Analytics (CJA) en [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) en Adobe Experience Platform para personalización y segmentación de clientes.

## Crear audiencia

1. Para crear audiencias, tiene tres formas de empezar:

   | Método de creación | Detalles |
   | --- | --- |
   | De **[!UICONTROL Componentes] > [!UICONTROL Audiencias]** | Se abre la página Administrador de audiencias . Haga clic en **[!UICONTROL Crear audiencia]** y [!UICONTROL Generador de audiencias] se abre. |
   | Desde una tabla improvisada | Haga clic con el botón derecho en un elemento de una tabla improvisada y seleccione **[!UICONTROL Crear una audiencia a partir de una selección]**. El uso de este método rellena previamente el filtro con la dimensión o el elemento de dimensión seleccionado en la tabla. |
   | Desde la interfaz de usuario de edición de filtros | Marque la casilla que dice **[!UICONTROL Crear una audiencia a partir de este filtro]**. El uso de este método rellena previamente el filtro. |

   {style=&quot;table-layout:auto&quot;}

1. Configure la audiencia.

   | Configuración | Descripción |
   | --- | --- |
   | [!UICONTROL Nombre] | Nombre de la audiencia. |
   | [!UICONTROL Etiquetas] | Cualquier etiqueta que desee asignar a la audiencia con fines organizativos. Puede utilizar una etiqueta preexistente o introducir una nueva. |
   | [!UICONTROL Descripción] | Añada una buena descripción de la audiencia para diferenciarla de otras. |
   | [!UICONTROL Frecuencia de actualización] | Frecuencia con la que desea actualizar la audiencia.<ul><li>Puede elegir crear una audiencia única (predeterminada) que no necesite ser actualizada, lo que sería útil para campañas únicas específicas, por ejemplo.</li><li>Puede seleccionar otros intervalos de actualización. Para la frecuencia de 4 horas, hay un límite de 150 audiencias, ya que esta frecuencia de actualización es muy intensiva en el procesamiento. Para otros intervalos, no hay un número máximo de audiencias.</li></ul> |
   | Fecha de caducidad | Cuándo dejará de actualizarse la audiencia. El valor predeterminado es 1 año a partir de la fecha de creación. |
   | Actualizar ventana de retrospección | Especifica cuánto tiempo atrás en la ventana de datos desea recorrer al crear esta audiencia. El máximo. es de 90 días. Las audiencias que caducan se tratan de manera similar a los informes programados que caducan: el administrador recibe un correo electrónico un mes antes de que caduque la programación. |
   | [!UICONTROL Intervalo de fecha de una sola vez] | Intervalo de fechas en el que desea que se publique la audiencia única. |
   | [!UICONTROL Filtro] | Los filtros son la entrada principal a la audiencia. Se pueden agregar hasta 20 filtros. Estos filtros se pueden unir con `And` o `Or` operadores. |

   {style=&quot;table-layout:auto&quot;}

1. Interpretar la vista previa de datos.

   La vista previa de la audiencia aparece en el carril derecho.

   | Configuración de vista previa | Descripción |
   | --- | --- |
   | Ventana de vista previa de datos | El intervalo de fechas de la audiencia. |
   | Total de personas en la audiencia | Número de resumen que puede llegar a los 100 millones. |
   | Límite de tamaño de audiencia | Muestra hasta dónde está el límite de 100 millones de audiencias. |
   | Retorno estimado de la audiencia |  |
   | Estimación de retorno | Un número de resumen... |
   | Previsualizar métricas |  |

   {style=&quot;table-layout:auto&quot;}


