---
description: Plantillas en Workspace
title: Plantillas
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 99%

---


# Plantillas

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Puede elegir crear un proyecto a partir de:

* **Proyecto en blanco (predeterminado)**: para obtener instrucciones, consulte [Creación de un proyecto de Analysis Workspace](/help/analysis-workspace/home.md).
* **Plantilla estándar**: estas plantillas son creadas por Adobe y se envían con el producto.
* **Plantilla personalizada**: estas plantillas pueden ser creadas, compartidas o eliminadas por usuarios con derechos de administrador o por usuarios que no sean administradores, siempre que se les haya otorgado el permiso [!UICONTROL Analysis Workspace: Guardar como plantilla] en Admin Console. [Más información...](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Creación de una plantilla personalizada {#create-custom-template}

Los usuarios que tengan derechos de administrador pueden convertir cualquier proyecto que creen en una plantilla personalizada. A continuación se muestra cómo:

1. Abra el proyecto.
1. Vaya a **[!UICONTROL Proyecto]** > **[!UICONTROL Guardar como plantilla]**.

   ![](assets/save_project_template.png)

   El proyecto se guardará con el nombre del proyecto actual, seguido de la palabra “plantilla” entre paréntesis. Los administradores pueden cambiar este nombre editando la plantilla.

   >[!NOTE]
   >
   >De forma predeterminada, las plantillas de proyecto son visibles para todos los miembros de su organización. Puede ordenarlas mediante etiquetas. (Vaya a **[!UICONTROL Proyecto]** > **[!UICONTROL Información y configuración del proyecto]** para editar las etiquetas y las descripciones).

### Acciones que se pueden llevar a cabo en las plantillas personalizadas

![](assets/custom_templates.png)

| Acción | Descripción |
|--- |--- |
| Editar  plantilla | Permite que el administrador edite la plantilla cambiando la fuente de datos, los componentes, las visualizaciones, los intervalos de fechas, etc.  Para editar una plantilla personalizada, puede:<ul><li>Buscar la lista de plantillas personalizadas en Analysis Workspace, seleccionar una y hacer clic en Editar plantilla.</li><li>En Analytics, ir a Componentes > Proyectos y filtrar por Plantillas. Acto seguido, puede hacer clic en el nombre de la plantilla que quiera editar.</li></ul>**Nota:** Tras editar una plantilla, y según la situación, tiene dos opciones: Guardar o Guardar como. A continuación se indican las diferencias entre ambas opciones.<ul><li>**Guardar:** actualiza la plantilla personalizada para todos los usuarios. Cuando otra persona cree un proyecto a partir de esta plantilla personalizada, verá los cambios que ha hecho usted.</li><li>**Guardar como:** crea una copia de la plantilla personalizada con sus cambios. (Sabrá que está en el modo de edición cuando el elemento de menú Compartir > Compartir proyecto esté desactivado).</li></ul> |
| Buscar en plantillas | En el cuadro de diálogo Plantillas personalizadas, haga clic en Buscar plantillas. |
| Ordenar plantillas | Puede ordenar las plantillas alfabéticamente, por su relevancia o por la fecha de creación.  En el cuadro de diálogo Plantillas personalizadas, haga clic en Ordenar. |
| Aplicar etiquetas a una plantilla | Abra la plantilla y vaya a Proyecto > Información y configuración del proyecto. Haga clic en Añadir etiquetas. |
| Modificar la descripción de la plantilla | Abra la plantilla y vaya a Proyecto > Información y configuración del proyecto. Haga doble clic en la descripción y edítela. |


## Plantillas estándar

Al abrir un Workspace por primera vez, las plantillas aparecen en el panel izquierdo. Las plantillas de Analysis Workspace cubren casos de uso comunes. Están agrupadas por la vertical a la que pertenecen y se rellenan con distintas dimensiones, segmentos, métricas y visualizaciones, según el grupo de informes que haya seleccionado.

Puede utilizar estas plantillas rellenadas previamente tal cual, o puede adaptarlas a sus necesidades (mediante la adición o sustitución de métricas o visualizaciones, por ejemplo) y guardarlas con un nuevo nombre.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Estas son las plantillas disponibles y las preguntas que cada plantilla ayuda a responder.

### Capacitación

Estas plantillas estándar le guían a través de la terminología común y de los pasos para crear su primer análisis en Workspace. Está disponible como plantilla estándar en el modo Nuevo proyecto y reemplaza el proyecto de muestra actual para los usuarios nuevos que no tienen otros proyectos en su lista.

* **Tutorial de capacitación - Análisis de búsqueda interna**: el tutorial de búsqueda interna ayuda a comprender qué buscan los visitantes en el sitio web o la aplicación, pero no qué encuentran. Analizar este tipo de datos puede brindar oportunidades de optimización de contenido.

* **Tutorial de capacitación - Análisis de marketing**: este tutorial muestra cómo crear un análisis de marketing para los ejecutivos, incluidas las dimensiones y métricas personalizadas que son importantes.

### Publicidad

>[!IMPORTANT]
>
>Las plantillas de publicidad solo están disponibles si el grupo de informes está habilitado para Advertising Cloud.

* **Motores de búsqueda de pago**: esta plantilla desglosa las tendencias publicitarias, las plataformas de publicidad, las palabras clave, las cuentas, las campañas y mucho más.

### Comercio

* **Magento - Marketing and Commerce**: esta plantilla desglosa la conversión del comercio electrónico según la atribución del canal de marketing. También proporciona perspectivas por palabra clave de búsqueda, página de aterrizaje, ubicación geográfica y mucho más. Para ver un vídeo introductorio, consulte:

>[!VIDEO](https://video.tv.adobe.com/v/28164)

### Medios

* **Consumo de audio**: ¿Qué contenido se consume más y resulta más atractivo para los usuarios?
* **Actualización, Frecuencia, Lealtad**: ¿Quiénes son mis lectores más fieles?

### Mobile

>[!IMPORTANT]
>
>Las plantillas móviles están disponibles únicamente si el grupo de informes está activado para móvil.

* **Mensajería:** Se centra en el rendimiento de la mensajería en la aplicación y mensajería push.
* **Ubicación:** Incluye un mapa que muestra los datos de ubicación.
* **Métricas clave:** Observar las métricas clave de su aplicación.
* **Uso de la aplicación:** ¿Cuántos usuarios de la aplicación, ejecuciones y ejecuciones por primera vez ha tenido la aplicación y cuál es la longitud promedio de cada sesión?
* **Adquisición:** Consulte el rendimiento de los vínculos de adquisición móvil.
* **Rendimiento:** ¿Qué rendimiento tiene la aplicación y dónde tienen problemas los usuarios?
* **Retención:** ¿Quiénes son mis usuarios más fieles y qué hacen?
* **Recorridos:** ¿Cuáles son los patrones de uso más destacados de mi aplicación?

### Comercial

* **Rendimiento de la campaña:** ¿Qué campañas consiguen el máximo de ingresos?
* **Productos:** ¿Qué productos tienen el mejor rendimiento?

### Web

* **Adquisición:** ¿Cuáles son los principales impulsores de tráfico a mi sitio web?
* **Consumo de contenido:** ¿Cuáles son los principales lugares que visitan los usuarios en mi sitio web?
* **Retención:** ¿Qué tipo de usuarios es más probable que sea leal a mi sitio?
* **Tecnología:** ¿Qué tecnología utilizan los usuarios para acceder a mi sitio?

### Personas

>[!NOTE]
>
>La plantilla Personas y su métrica asociada Personas solo se pueden usar como parte de [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/es-ES/device-co-op/using/data/people.html).

Esta plantilla se basa en la métrica Personas que es una versión deduplicada de la métrica Visitantes únicos. La métrica Personas proporciona una medida de la frecuencia con la que los consumidores que usan varios dispositivos interactúan con la marca. Esta plantilla le permite hacer lo siguiente:

* Segmentar sus datos para EE. UU./Canadá frente al resto del mundo. En estos momentos, la funcionalidad de cooperación entre dispositivos solo está disponible en Norteamérica.
* Comparar en paralelo las métricas Personas y Visitantes únicos.
* Consultar la “tasa de compresión”, una métrica calculada que analiza en qué medida la métrica Personas es inferior como porcentaje de Visitantes únicos.
* Comparar los totales por tipo de dispositivo que utilizan sus clientes.
* Consultar cuántos dispositivos se utilizan de media por persona.
* Aprender a utilizar la función para apilas segmentos con la métrica Personas.
* Descubra cómo mejorar la eficacia de la métrica Personas con el uso del Experience Cloud ID en su entorno.

### Journey IQ: plantilla de análisis entre dispositivos

<!--This content is mirrored in the CDA doc.-->

Esta plantilla le permite ver datos de rendimiento vitales entre dispositivos. Solo está disponible para clientes que tienen acceso al [análisis entre dispositivos](https://docs.adobe.com/content/help/es-ES/analytics/components/cda/cda-home.html) (CDA).

* **Nota especial para los miembros del gráfico de cooperación**: muestra qué parte del grupo de informes contiene visitantes en regiones donde se admite el gráfico de cooperación y en regiones donde no se admite.
* **Identificación de los usuarios**: muestra la frecuencia con la que se identifican los visitantes del sitio mediante métodos basados en el análisis entre dispositivos.
* **Medición del tamaño de la audiencia**: muestra una comparación de &#39;Dispositivos únicos&#39; con &#39;Personas&#39;. La proporción de estos dos números se conoce como &#39;compresión entre dispositivos&#39;, una métrica calculada visible en este panel. Esta métrica de compresión depende de varios factores:
   * **Uso del gráfico de colaboración o del gráfico privado**: en términos generales, las organizaciones que utilizan la colaboración entre dispositivos tienden a ver mejores tasas de compresión que las organizaciones que utilizan el gráfico privado.
   * **Velocidad de inicio de sesión**: cuantos más usuarios inicien sesión en el sitio, más podrá Adobe identificar y unir a los visitantes entre dispositivos. Los sitios con una tasa de inicio de sesión baja también tienen tasas de compresión bajas.
   * **Cobertura de Experience Cloud ID**: solo se pueden vincular los visitantes con un ECID. Un porcentaje menor de visitantes que utilizan un ECID se correlaciona con tasas de compresión más bajas.
   * **Uso de varios dispositivos**: si los visitantes del sitio no utilizan varios dispositivos, puede ver tasas de compresión más bajas.
   * **Granularidad de informes**: la compresión por día suele ser menor que la compresión por mes o año. Las posibilidades de que un individuo utilice varios dispositivos se reducen en un solo día en comparación con todo un mes. Segmentar, filtrar o utilizar dimensiones de desglose también puede mostrar una tasa de compresión más baja.
* **Segmentos basados en personas**: contiene una lista desplegable de segmentos que le permite ver datos específicos del dispositivo. Este panel promueve la experimentación con segmentos para ver cómo la inclusión o la exclusión de tipos de dispositivos afectan los informes.
* **Análisis del viaje entre dispositivos**: proporciona informes de flujo y visitas en el orden previsto en función del tipo de dispositivo.
* **Atribución entre dispositivos**: combine las características de Journey IQ y Attribution IQ.
* **Otros consejos y trucos**: temas útiles en torno a CDA que le permite aprovecharlo al máximo.