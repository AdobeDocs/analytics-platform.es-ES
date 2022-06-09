---
description: Utilice la visualización de flujo en un proyecto de Workspace.
title: Configuración de una visualización de flujo
feature: Visualizations
role: User, Admin
source-git-commit: 62243ccd3d0f4b6ef09e57d850c0d7eb03f879e0
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 40%

---

# Configuración de una visualización de flujo

>[!NOTE]
>
>Esta nueva versión de [!UICONTROL Flujo] actualmente, la visualización está en prueba limitada. Se publicará el 15 de junio de 2022 .

La visualización de flujo actualizada permite comprender los recorridos que se derivan de un evento de conversión específico en el sitio web o la aplicación, o que se generan en él. Rastrea una ruta a través de sus dimensiones (y elementos de dimensión) o métricas. Flujo permite configurar el inicio o el final de la ruta que le interese o analizar todas las rutas que fluyen a través de una dimensión o elemento de dimensión.

El nuevo [!UICONTROL flujo] la experiencia mejora el flujo de trabajo de varias formas:

* Ahora puede elegir iniciar o finalizar la ruta con la combinación de una métrica y una dimensión de rutas.
* Contiene [!UICONTROL Configuración avanzada] para permitirle personalizar aún más el [!UICONTROL flujo].
* El nuevo botón &quot;Generar&quot; ahorra tiempo en análisis al permitirle configurar el recorrido de una sola vez, luego consultar y luego crear automáticamente varias columnas y nodos a la vez &#x200B;.

![nueva interfaz de usuario de flujo](assets/new-flow.png)

## Pasos de configuración {#configure}

1. Para empezar a crear un diagrama de flujo, agregue un panel en blanco al proyecto y haga clic en el icono de visualizaciones en el carril izquierdo. A continuación, arrastre la visualización Flujo al panel. O arrastre el [!UICONTROL Flujo] visualización en un proyecto existente.

1. Ancla la visualización Flujo mediante una de las tres opciones:

   * [!UICONTROL Comienza con] (métricas, dimensiones o elementos), o
   * [!UICONTROL Contiene] (dimensiones o elementos), o
   * [!UICONTROL Finaliza con] (métricas, dimensiones o elementos)

   Cada una de estas categorías se muestra como “zona de colocación”. Arrastre elementos de la lista de dimensiones o métricas y suéltelos en la zona de colocación deseada.

   Por ejemplo, supongamos que desea rastrear todo lo que conduce a un evento de cierre de compra. Puede arrastrar una dimensión o métrica relacionada con el cierre de compra (por ejemplo, [!UICONTROL El pedido existe]) en el **[!UICONTROL Finaliza con]** zona de colocación.

1. Si elige una métrica, también debe proporcionar una [!UICONTROL Dimension de rutas], como se muestra aquí, que utilizará para crear la ruta. El valor predeterminado es [!UICONTROL Página].

   ![dimensión de rutas](assets/pathing-dim.png)

   >[!IMPORTANT]
   >
   >Las métricas calculadas no se pueden colocar en la variable  **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]** zonas de colocación.

1. (Opcional) Haga clic en **[!UICONTROL Mostrar configuración avanzada]** para configurar la configuración avanzada:

   ![configuración avanzada](assets/adv-settings.png)

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Incluir instancias repetidas]** | Las visualizaciones de flujo se basan en instancias de una dimensión. Esta configuración le da la opción de incluir o excluir instancias repetidas, por ejemplo, recargas de página. Sin embargo, las repeticiones no se pueden eliminar de las visualizaciones de flujo que incluyen dimensiones multivalor, como listVars, listProps, s.product, eVars de comercialización, etc. Valor predeterminado = sin marcar. |
   | **[!UICONTROL Etiquetas de ajuste]** | Normalmente, las etiquetas de los elementos de flujo se truncan para ahorrar espacio en la pantalla, pero puede hacer la etiqueta entera visible al marcar esta casilla.  Valor predeterminado = sin marcar. |
   | **[!UICONTROL Limitar a la primera/última ocurrencia]** | Limite las rutas a aquellas que comienzan/finalizan con la primera/última incidencia de una dimensión, elemento/métrica. |
   | **[!UICONTROL Número de columnas]** | Determina cuántas columnas desea incluir en el diagrama de flujo. |
   | **[!UICONTROL Elementos expandidos por columna]** | ¿Cuántos elementos desea incluir en cada columna? |
   | **[!UICONTROL Contenedor de flujo]** | <ul><li>Visita</li><li>Visitante.</li></ul> Permite alternar entre visitas y visitantes para analizar las rutas seguidas por los visitantes. Estos ajustes le permiten comprender el compromiso del visitante a nivel de visitante (a lo largo de visitas) o restringir el análisis a una única visita. |

1. Haga clic en **[!UICONTROL Generar]**.

## Ver y cambiar la salida de flujo {#output}

![salida de flujo](assets/flow-output.png)

En la parte superior del diagrama aparece un resumen de la configuración de flujo. Las rutas del diagrama son proporcionales. Las rutas con más actividad se muestran más gruesas.

Para profundizar en los datos, tiene varias opciones:

* El diagrama de flujo es interactivo. Pase el ratón por encima del diagrama para cambiar los detalles que se muestran.

* Cuando hace clic en un nodo en el diagrama, se muestran los detalles de dicho nodo. Vuelva a hacer clic en el nodo para contraerlo.

   ![node-details](assets/node-details.png)

* Puede filtrar una columna para mostrar solo ciertos resultados, como incluir y excluir, especificar criterios, etc.

* Haga clic en el signo más (+) de la izquierda para expandir una columna.

* Utilice las opciones del botón derecho que se explican a continuación para personalizar aún más la salida.

* Haga clic en el icono de lápiz situado junto al resumen de la configuración para editar el flujo o reconstruirlo con diferentes opciones.

* También puede exportar y seguir analizando el diagrama de flujo como parte del archivo .CSV de un proyecto. Para ello, vaya a **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar CSV]**.


## Opciones con el botón derecho del ratón {#right-click}

| Opción | Descripción |
|--- |--- |
| [!UICONTROL Centrarse en este nodo] | Cambia el interés al nodo seleccionado. El nodo de interés aparece en el centro del diagrama de flujo. |
| [!UICONTROL Volver a empezar] | Le hace regresar al generador de diagramas improvisados, donde puede crear un nuevo diagrama de flujo. |
| [!UICONTROL Crear segmento desde este punto del flujo] | Creación de segmentos. Esto le lleva al Generador de segmentos, donde puede configurar el nuevo segmento. |
| [!UICONTROL Desglosar] | Desglosa el nodo mediante las dimensiones, métricas o tiempo disponibles. |
| [!UICONTROL Tendencia] | Crea un diagrama de tendencia para el nodo. |
| [!UICONTROL Expandir toda la columna] | Expande una columna para mostrar todos los nodos. De forma predeterminada, únicamente se muestran los cinco nodos principales. |
| [!UICONTROL Contraer toda la columna] | Oculta todos los nodos de una columna. |

>[!MORELIKETHIS]
>[Resumen de flujos](/help/analysis-workspace/visualizations/c-flow/flow.md)


