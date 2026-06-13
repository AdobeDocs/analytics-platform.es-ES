---
title: Informes GA4 en Customer Journey Analytics
description: Busque el equivalente de Customer Journey Analytics para cada sección de informes de GA4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# Informes GA4 en Customer Journey Analytics

Utilice esta página como referencia de búsqueda cuando sepa qué informe de GA4 está viendo y desee volver a crear su equivalente aproximado en Analysis Workspace. Los informes están organizados por las secciones de navegación de GA4. Para ver los escenarios avanzados de creación de informes entre canales que están disponibles después de migrar datos de GA a Customer Journey Analytics, consulte [Informe sobre datos de Google Analytics](/help/use-cases/third-party/ga/report.md).

## Tiempo real

+++Tiempo real

El informe en tiempo real de GA4 muestra la actividad de los últimos 30 minutos: usuarios activos, los eventos que se activan, dónde están los usuarios, qué está impulsando el tráfico y en qué páginas están.

Customer Journey Analytics no tiene un área de informes en tiempo real independiente. En su lugar, cree un panel en Analysis Workspace y habilite la opción **[!UICONTROL Actualización en tiempo real]** (parte del paquete **Ultimate**) para que sus visualizaciones se actualicen cada minuto:

1. Cree un panel [improvisado](/help/analysis-workspace/c-panels/freeform-panel.md) (la opción también funciona en los paneles [En blanco](/help/analysis-workspace/c-panels/blank-panel.md), [Atribución](/help/analysis-workspace/c-panels/attribution.md) y [Elemento siguiente o anterior](/help/analysis-workspace/c-panels/next-previous.md)) con las dimensiones y métricas que desee monitorizar. Para imitar las tarjetas en tiempo real de GA4, usa **[!UICONTROL Página]**, **[!UICONTROL Tipo de evento]**, **[!UICONTROL Dominio de referencia]** o **[!UICONTROL Países]** como dimensión, con **[!UICONTROL Sesiones]** como métrica.
2. Habilite la opción **[!UICONTROL Actualización en tiempo real]** y elija un período de **[!UICONTROL Últimos 15 minutos]** a **[!UICONTROL Últimas 24 horas]**. Los datos están limitados a un intervalo móvil de 24 horas y el panel se actualiza cada minuto durante un máximo de 30 minutos.

Los informes en tiempo real favorecen los datos en el nivel de evento y de sesión, y no pueden usar la vinculación, así que prefiere **[!UICONTROL Sesiones]** sobre **[!UICONTROL Personas]**. Consulte [Usar informes en tiempo real](/help/components/real-time/use-real-time.md) para ver el procedimiento completo y [Resumen de informes en tiempo real](/help/components/real-time/real-time.md) para ver los detalles de asignación de derechos y latencia.

+++

## Adquisición

+++Adquisición de usuarios (primer contacto)

El informe de adquisición de usuarios de GA4 atribuye a cada usuario al canal, la fuente y el medio que lo llevó a su sitio por primera vez, mediante atribución de primer contacto.

En Analysis Workspace, aplique un modelo de atribución **[!UICONTROL Primer contacto]** a la dimensión **[!UICONTROL Canal de marketing]**. Los canales de marketing deben configurarse antes de usarlos. Consulte [Crear un campo derivado de canal de marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md).

1. Arrastre la dimensión **[!UICONTROL Canal de marketing]** a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Haga clic con el botón derecho en el encabezado de una columna de métrica y seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]**.
3. Seleccione **[!UICONTROL Primer contacto]** con una ventana retrospectiva adecuada para su análisis.

También puede usar el panel [[!UICONTROL Atribución]](/help/analysis-workspace/c-panels/attribution.md) para ver una comparación en paralelo del rendimiento de los canales de primer toque y de último toque.

+++

+++Adquisición de tráfico (basada en sesión)

El informe Adquisición de tráfico de GA4 atribuye cada sesión al canal, la fuente y el medio que la inició, mediante una atribución basada en sesión. Puede desglosarlo por grupo de canales, fuente/medio, referente o campaña predeterminados.

En Analysis Workspace, la dimensión **[!UICONTROL Canal de marketing]** con el modelo de atribución predeterminado de **[!UICONTROL Último contacto]** proporciona informes de canal basados en sesión:

1. Arrastre la dimensión **[!UICONTROL Canal de marketing]** a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Arrastre las métricas deseadas junto con la métrica predeterminada **[!UICONTROL Eventos]**.

Los desgloses de GA4 se asignan a estas dimensiones de Customer Journey Analytics:

* **Canal**: **[!UICONTROL Canal De Marketing]**. Customer Journey Analytics no tiene agrupaciones de canales integradas: definirlas como un [campo derivado](/help/data-views/derived-fields/derived-fields.md) mediante la plantilla de función **[!UICONTROL Canales de mercadotecnia]** o transferir reglas de Adobe Analytics al usar el conector de origen de Analytics (consulte [Usar dimensiones de canal de mercadotecnia](/help/use-cases/aa-data/marketing-channels.md)).
* **Source / medio y referencias**: **[!UICONTROL Dominio de referencia]** y **[!UICONTROL Tipo de referente]**.
* **Campaign**: los `utm_*` parámetros de GA4 no se recopilan automáticamente; cada uno debe asignarse a un campo XDM durante la implementación antes de que aparezca como dimensión. Si los valores de campaña llegan como código de seguimiento, use la dimensión **[!UICONTROL Código de seguimiento]**.

+++

+++Rutas de atribución y conversión

Los informes de Atribución de GA4 (en Advertising) muestran cómo los distintos canales contribuyen a las conversiones y permiten comparar modelos y analizar rutas de conversión.

En Analysis Workspace, use el panel [[!UICONTROL Atribución]](/help/analysis-workspace/c-panels/attribution.md):

1. Seleccione el icono Paneles y arrastre un panel **[!UICONTROL Atribución]** al lienzo.
2. Arrastre la dimensión **[!UICONTROL Canal de marketing]** al cuadro **[!UICONTROL Agregar Dimension]**.
3. Arrastre su métrica de conversión (por ejemplo, un evento de compra) al cuadro **[!UICONTROL Agregar métrica]**.
4. Seleccione **[!UICONTROL Generar]**.

El [!UICONTROL panel de atribución] produce una tabla de comparación de modelos y una visualización de [!UICONTROL Flujo de canal] que muestra las rutas principales que tomaron los visitantes antes de la conversión. Seleccione **[!UICONTROL Agregar modelo]** para comparar varios modelos de atribución simultáneamente.

+++

## Participación

+++Páginas y pantallas

El informe Pages and screens de GA4 muestra métricas de rendimiento para páginas individuales y pantallas de aplicación.

En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página]** a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) y agregue las métricas que desee. Las métricas comunes incluyen **[!UICONTROL Sesiones]**, **[!UICONTROL Personas]**, **[!UICONTROL Tasa de salida hacia otro sitio]** y **[!UICONTROL Tiempo empleado por sesión]**.

Para agrupar páginas por estructura de ruta de dirección URL (por ejemplo, `/blog/` o `/products/`), use la dimensión **[!UICONTROL Sección del sitio]** si su implementación la define, o cree un [campo derivado](/help/data-views/derived-fields/derived-fields.md) que analice la dirección URL de la página con la función **[!UICONTROL Análisis de dirección URL]**. Si mantiene una asignación explícita de página a sección, un [conjunto de datos de consulta](/help/connections/standard-lookups.md) puede proporcionar la agrupación en su lugar.

+++

+++Páginas de aterrizaje

El informe de página de aterrizaje de GA4 muestra a qué páginas llegan los usuarios cuando inician una sesión.

En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página de entrada]** a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). **[!UICONTROL Sesiones]** es la métrica más relevante para esta dimensión.

+++

+++Eventos

El informe Eventos de GA4 muestra cuántas veces se activó cada evento con métricas de nivel de evento.

En GA4, los eventos tienen un nombre y parámetros opcionales (por ejemplo, evento `video_play` con parámetro `video_title`). En Customer Journey Analytics, la dimensión estándar para el nombre de evento es **[!UICONTROL Tipo de evento]** (procedente de `xdm.eventType`). Los parámetros de evento se asignan a otros campos XDM, cuyos nombres dependen de la implementación.

Arrastre la dimensión **[!UICONTROL Tipo de evento]** a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) para enumerar todos los tipos de eventos, junto con la métrica **[!UICONTROL Eventos]**.

+++

+++Eventos clave (conversiones)

El informe Eventos clave de GA4 (anteriormente Conversiones) enumera cada evento clave por nombre con su recuento: eventos marcados como críticos para el negocio en la configuración de propiedades de GA4.

Customer Journey Analytics no tiene un indicador de &quot;evento clave&quot;; cada interacción es un evento, por lo que no hay una lista preestablecida de conversiones para abrir.

Para volver a crear la lista de conversiones de GA4 por nombre, use **segmentos como filas**. Una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) no puede colocar una métrica en la posición de fila, pero sí puede colocar un segmento allí:

1. Para cada conversión, cree un segmento que aísle sus eventos; por ejemplo, un segmento con alcance de evento donde `xdm.eventType` sea igual a `commerce.purchases`. Asigne un nombre a cada segmento después de la conversión que represente (por ejemplo, **Compras**).
2. Arrastre cada segmento de conversión al área de fila de una [!UICONTROL tabla de forma libre], uno por fila.
3. Agregue la métrica **[!UICONTROL Eventos]** como columna. Cada fila muestra el recuento de esa conversión, reflejando la lista de eventos clave de GA4. Usa **[!UICONTROL Personas]** en su lugar para contar convertidores únicos.

Para agregar una tasa de conversión, cree una métrica calculada (seleccione el icono **+** cerca de la lista de métricas) definida como una métrica de conversión dividida por **[!UICONTROL Sesiones]** o **[!UICONTROL Personas]**.

Cada conversión que aísle aquí también puede definirse como una métrica reutilizable en la vista de datos. Consulte la entrada **Eventos clave → métricas de eventos personalizados** en [Métricas comunes](#common-metrics) para saber cómo configurarlas.

+++

## Monetización

+++Compras de comercio electrónico

El informe de compras en comercio electrónico de GA4 muestra los datos de compra a nivel de producto, incluidos los artículos, los ingresos y la cantidad.

En Customer Journey Analytics, los informes de comercio electrónico utilizan la dimensión **[!UICONTROL Product]** junto con las métricas de compra. Este informe requiere que la implementación envíe datos de comercio de XDM (como `xdm.commerce.purchases`, `xdm.commerce.order` y `xdm.productListItems`).

1. Arrastre la dimensión **[!UICONTROL Product]** a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Arrastre métricas de comercio electrónico como **[!UICONTROL Pedidos]**, **[!UICONTROL Ingresos]** y **[!UICONTROL Unidades]** junto con la métrica predeterminada **[!UICONTROL Eventos]**.

+++

+++Recorridos de compra (funnel)

El informe recorrido de compras de GA4 muestra cómo se mueven los usuarios por su funnel de compras (por ejemplo, de agregar al carro de compras para comenzar el cierre de compra a comprar) y dónde caen.

En Analysis Workspace, use la visualización [**[!UICONTROL Visitas en el orden previsto]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md):

1. Seleccione el icono Visualizaciones y arrastre una visualización **[!UICONTROL Visitas en el orden previsto]** al lienzo.
2. Busque la dimensión **[!UICONTROL Página]** y expándala para mostrar valores de página individuales.
3. Arrastre el primer paso de funnel (por ejemplo, una página de producto) a la primera ranura de **[!UICONTROL Agregar punto de contacto]**.
4. Continúe añadiendo puntos de contacto para cada paso.

La visualización de visitas en el orden previsto acepta cualquier dimensión, métrica o segmento como punto de contacto, no solo páginas, por lo que coincide con los canales basados en eventos de GA4 y se extiende a secuencias que mezclan eventos, páginas y segmentos.

+++

+++Promociones

El informe Promociones de GA4 muestra cómo las promociones internas (titulares, ubicaciones destacadas) impulsan las interacciones de productos.

En Customer Journey Analytics, los datos de promoción requieren que capture las impresiones y clics de la promoción en los campos de esquema XDM. Una vez recopilada, cree una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que incluya la dimensión de nombre de promoción con métricas de impresión y clics. Póngase en contacto con el administrador de Customer Journey Analytics para confirmar qué datos de promoción están disponibles en la vista de datos.

+++

+++Anuncios de Publisher

El informe de anuncios de Publisher de GA4 muestra los ingresos publicitarios de Google Ad Manager o AdMob en propiedades monetizadas por el editor.

Customer Journey Analytics no cuenta con una integración nativa de ingresos publicitarios de editor. Para informar sobre estos datos, introduzca las cifras de ingresos de su plataforma de monetización de anuncios (como Google Ad Manager o AdMob) en Adobe Experience Platform como un conjunto de datos, mediante un conector de origen o una ingesta directa de datos. Una vez introducidos, los datos están disponibles para la creación de informes en Customer Journey Analytics.

+++

## Retención

+++Resumen de retención

El informe de resumen de retención de GA4 combina varias vistas de retención: usuarios nuevos frente a recurrentes, y un gráfico de cohorte que muestra cuántos usuarios regresan con el tiempo.

**Usuarios nuevos y recurrentes**: use los segmentos **[!UICONTROL Primera sesión]** y **[!UICONTROL Sesiones de retorno]** como filas en una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md):

1. Arrastre el segmento **[!UICONTROL Primera sesión]** del panel Componentes al área de filas de la tabla y, a continuación, arrastre el segmento **[!UICONTROL Sesiones de retorno]** debajo de él.
2. Agregue las métricas que desee junto con la métrica predeterminada **[!UICONTROL Eventos]**.
3. Para cambiar la tendencia con el tiempo, arrastre una visualización [**[!UICONTROL Line]**](/help/analysis-workspace/visualizations/line.md) sobre la tabla y, a continuación, presione Ctrl+clic (Windows) o Cmd+clic (Mac) en cada fila para resaltar ambos segmentos.

**Retención en el tiempo**: use la visualización [**[!UICONTROL Tabla de cohorte]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Seleccione el icono Visualizaciones y arrastre una **[!UICONTROL Tabla de cohorte]** al lienzo.
2. Arrastre la métrica **[!UICONTROL Personas]** a los campos Inclusión y Criterios de retorno y, a continuación, seleccione **[!UICONTROL Generar]**.

La [!UICONTROL tabla de cohorte] agrupa a las personas por su periodo inicial y rastrea el comportamiento de regreso en periodos subsiguientes; los criterios de inclusión, regreso y granularidad se pueden configurar.

+++

## Usuario

+++Datos demográficos

El informe Detalles demográficos de GA4 cubre las características del usuario: edad, sexo e intereses (con tecnología de Google Signals, que requiere que los usuarios inicien sesión en una cuenta de Google con la personalización habilitada), junto con la ubicación (país, región, ciudad) y el idioma.

**La ubicación** se asigna directamente a las dimensiones de Customer Journey Analytics: usa **[!UICONTROL Países]**, **[!UICONTROL Regiones]** o **[!UICONTROL Ciudades]** en una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), o la visualización de [[!UICONTROL Mapa]](/help/analysis-workspace/visualizations/map.md) para obtener una descripción general geográfica (arrastra la métrica **[!UICONTROL Personas]** a la ranura **[!UICONTROL Agregar métrica]** y selecciona **[!UICONTROL Generar]**).

**La edad, el sexo y los intereses** requieren datos de origen. Si su organización recopila datos demográficos a través de CRM, formularios de registro o encuestas basadas en consentimiento, ingréselos como un [conjunto de datos de perfil](/help/connections/create-connection.md#profile-dataset) y únalos a los datos de evento. Este enfoque produce datos más fiables que el modelo de Google Signals deducido por GA4, ya que utiliza atributos de origen consentidos.

+++

+++Detalles técnicos

El informe técnico de GA4 muestra el explorador, el sistema operativo, la resolución de pantalla y la categoría del dispositivo.

En Analysis Workspace, las siguientes dimensiones se asignan a las dimensiones Tech de GA4, cada una originada en un campo XDM estándar:

| Dimensión técnica de GA4 | Dimensión Analysis Workspace | Campo XDM |
|---|---|---|
| Explorador | **[!UICONTROL Explorador]** | `xdm.environment.browserDetails.name` |
| Sistema operativo | **[!UICONTROL Sistema operativo]** | `xdm.environment.operatingSystem` |
| Resolución de pantalla | **[!UICONTROL Resolución del monitor]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| Categoría del dispositivo (móvil, escritorio, tableta) | **[!UICONTROL Tipo de dispositivo móvil]** | `xdm.device.type` |
| Modelo de dispositivo | **[!UICONTROL Dispositivo móvil]** | `xdm.device.model` |

Arrastre cualquiera de estas dimensiones del panel Componentes a una [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

>[!NOTE]
>
>Debido a que los exploradores modernos han reducido los detalles en la cadena del agente de usuario, los valores completos y precisos dependen de la recopilación de [sugerencias del cliente del agente de usuario](https://experienceleague.adobe.com/es/docs/experience-platform/collection/use-cases/client-hints) en la configuración de su Web SDK.

+++

## Explorar

+++Exploración de forma libre

La exploración de forma libre de GA4 es una tabla de lienzo en blanco con filas, columnas y superposiciones de gráficos opcionales que se pueden configurar.

[**[!UICONTROL Tabla de forma libre]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) de Analysis Workspace es el equivalente directo y la base de la mayoría de los proyectos de Workspace. Arrastre cualquier dimensión a las filas, cualquier métrica a las columnas y cualquier segmento a la zona de colocación de segmentos sobre la tabla.

Consulte [Introducción en Analysis Workspace](home.md#getting-started-in-analysis-workspace) para la asignación de terminología entre el Explorador de GA4 y Workspace.

+++

+++Exploración de funnel

La exploración de Funnel de GA4 define una secuencia de pasos y mide la finalización y la entrega en cada paso.

En Analysis Workspace, use la visualización [**[!UICONTROL Visitas en el orden previsto]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md):

1. Seleccione el icono Visualizaciones y arrastre una visualización **[!UICONTROL Visitas en el orden previsto]** al lienzo.
2. Arrastre la dimensión, métrica o segmento que representa su primer paso a la primera ranura de **[!UICONTROL Agregar punto de contacto]**.
3. Continúe añadiendo un punto de contacto para cada paso siguiente de la secuencia.

Dado que cualquier dimensión, métrica o segmento puede servir como punto de contacto, [!UICONTROL Visitas en el orden previsto] coincide con los canales basados en eventos de GA4 y se extiende a secuencias multicanal que mezclan eventos, páginas y segmentos.

+++

+++Exploración de rutas

La exploración de rutas de GA4 (Universal Analytics denominada Flujo de usuarios) visualiza las secuencias de páginas o eventos por las que navegan los usuarios.

En Analysis Workspace, use la visualización [**[!UICONTROL Flujo]**](/help/analysis-workspace/visualizations/c-flow/flow.md):

1. Seleccione el icono Visualizaciones y arrastre una visualización **[!UICONTROL Flujo]** al lienzo.
2. Arrastre un valor de la dimensión en la que desee establecer la ruta de acceso (por ejemplo, un valor de **[!UICONTROL Página]** o **[!UICONTROL Tipo de evento]**) al centro del flujo.
3. La visualización muestra qué hicieron los usuarios antes y después de ese punto.

La visualización [!UICONTROL Flow] es interactiva: seleccione cualquier nodo para expandir las rutas en cualquier dirección. Se puede utilizar cualquier dimensión, por lo que puede establecer la ruta de acceso a páginas, eventos, canales de marketing o vínculos personalizados.

+++

+++Superposición de segmentos

La exploración de superposición de segmentos de GA4 muestra cómo se intersectan varios segmentos de usuario, visualizados como un diagrama de Venn.

En Analysis Workspace, use la visualización [**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md):

1. Seleccione el icono Visualizaciones y arrastre una visualización **[!UICONTROL Venn]** al lienzo.
2. Arrastre hasta tres segmentos desde el panel Componentes a la visualización.

El diagrama de Venn muestra los tamaños de intersección y la [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) debajo muestra los datos subyacentes.

+++

+++Exploración de cohorte

La exploración de cohorte de GA4 agrupa a los usuarios por una característica compartida (normalmente, fecha de adquisición) y rastrea su comportamiento a lo largo del tiempo.

En Analysis Workspace, use la visualización [**[!UICONTROL Tabla de cohortes]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Seleccione el icono Visualizaciones y arrastre una **[!UICONTROL Tabla de cohorte]** al lienzo.
2. Arrastre la métrica **[!UICONTROL Personas]** a los campos Inclusión y Criterios de retorno.
3. Seleccione **[!UICONTROL Generar]**.

La [!UICONTROL tabla de cohorte] agrupa a las personas por su período inicial y rastrea el comportamiento de retorno en períodos subsiguientes. De forma predeterminada, se cohorte en la fecha de adquisición, pero los criterios de inclusión, regreso y granularidad se pueden configurar.

+++

+++Explorador de usuarios

El explorador de usuarios de GA4 muestra los usuarios individuales, el historial de sus sesiones y una cronología de los eventos.

Customer Journey Analytics admite el análisis a nivel de persona de dos formas:

* **Con la vinculación habilitada**: cree un ámbito de segmento para un valor de ID de persona específico y aplíquelo a cualquier proyecto de Workspace. El contenedor **[!UICONTROL Persona]** aísla la actividad vinculada de ese individuo en varias sesiones y canales.
* **Datos de evento sin procesar**: use **vistas previas de conjuntos de datos** en la interfaz de usuario de Adobe Experience Platform para inspeccionar los registros de evento XDM sin procesar. Esta vista es útil para validar la implementación y depurar eventos individuales.

+++

+++Duración del usuario

La exploración de duración del usuario de GA4 mide el valor acumulado y la participación de cada usuario en toda su relación con su negocio, en lugar de dentro de un intervalo de fechas fijo. Combina métricas históricas de por vida con predicciones de aprendizaje automático de Google para probabilidad de compra, probabilidad de pérdida e ingresos predichos.

Estos se asignan a Customer Journey Analytics en dos partes:

**El valor histórico de duración** se puede conseguir de forma nativa. Como Customer Journey Analytics realiza informes sobre el período de retención de datos completo, puede establecer un intervalo de fechas largo y acumular los ingresos y la participación acumulados de cada persona en esa retrospectiva. Si se vincula o se usa un ID de persona persistente, el contenedor **[!UICONTROL Persona]** vincula esa actividad con un individuo y las métricas calculadas expresan el valor por persona. El resultado no es una duración ilimitada, sino una retrospectiva larga y configurable que se aproxima a una.

**El valor predictivo de duración** no está integrado. Customer Journey Analytics no tiene un modelo de probabilidad de compra, pérdida o ingresos predichos en el producto. Para utilizar puntuaciones predictivas, calcúlelas externamente (por ejemplo, en un flujo de trabajo de CRM o de ciencia de datos) e introdúzcalas en Customer Journey Analytics como un conjunto de datos de perfil y, a continuación, suéltelas como dimensiones o métricas. Adobe recomienda trabajar con un consultor de implementación para diseñar este enfoque.

+++

## Métricas comunes

+++Usuarios activos → Personas

**Usuarios activos** de GA4 cuenta usuarios que tuvieron al menos una sesión comprometida en el intervalo de fechas.

En Customer Journey Analytics, el equivalente más cercano es **[!UICONTROL Personas]**, un recuento de ID de persona únicos en el intervalo de fechas. [!UICONTROL Personas] incluye todas las personas identificadas independientemente del nivel de participación, por lo que generalmente es mayor que los usuarios activos de GA4 para los sitios con tráfico pasivo significativo.

Para una comparación de comportamiento más cercana, aplique un [segmento de sesiones comprometidas](compare-data.md#engaged-sessions) para ampliar el ámbito de la métrica [!UICONTROL Personas] a los usuarios que cumplan con sus criterios de participación.

+++

+++Sesiones comprometidas → métrica calculada

Las **sesiones comprometidas** de GA4 cuentan sesiones que duraron 10 o más segundos, tuvieron 2 o más vistas de página o incluyeron al menos un evento clave.

Customer Journey Analytics no tiene una métrica de sesiones comprometidas integrada: usted la define como un segmento que captura sus criterios de participación y luego la utiliza junto con la métrica **[!UICONTROL Sesiones]**. Consulte [Sesiones comprometidas](compare-data.md#engaged-sessions) para ver el enfoque recomendado y cómo obtener una tasa de participación de ella.

+++

+++Tasa de participación → métrica calculada

**Tasa de participación** de GA4 es el porcentaje de sesiones que se comprometieron: sesiones comprometidas divididas por el total de sesiones.

En Customer Journey Analytics, créela como una métrica calculada a partir de la definición de sesiones comprometidas. Consulte [Sesiones involucradas](compare-data.md#engagement-rate) para obtener instrucciones paso a paso.

+++

+++Tiempo promedio de participación → Tiempo empleado por sesión

El **tiempo promedio de participación** de GA4 mide el tiempo promedio que el navegador o la aplicación estuvo en primer plano durante las sesiones comprometidas.

En Customer Journey Analytics, use **[!UICONTROL Duración de la sesión (segundos)]**, que mide el tiempo transcurrido desde el primer evento hasta el último de una sesión. Este componente incluye periodos en los que el usuario puede no haber participado activamente, por lo que los valores pueden diferir de la medición de GA4. Es el equivalente integrado más cercano.

+++

+++Recuento de eventos → eventos

**Recuento de eventos** de GA4 es la cantidad total de veces que se registró un evento.

En Customer Journey Analytics, la métrica equivalente es **[!UICONTROL Events]**: el número total de registros de eventos en el conjunto de datos para el intervalo de fechas seleccionado y los segmentos aplicados.

+++

+++Sesiones → sesiones

Las **sesiones** de GA4 y las **[!UICONTROL sesiones]** de Customer Journey Analytics miden el número de sesiones en un intervalo de fechas. Los recuentos pueden variar debido a las distintas reglas de definición de sesión. Consulte [Por qué difieren los datos de GA4 y Customer Journey Analytics](compare-data.md#sessions) para obtener más información.

+++

+++Nuevos usuarios → el segmento Primera sesión aplicado a Personas

**Nuevos usuarios** de GA4 cuenta usuarios que tuvieron su primera sesión en el intervalo de fechas seleccionado.

En Analysis Workspace:

1. Busque el segmento **[!UICONTROL Primera sesión]** en el panel Componentes.
2. Arrástrela a la zona de colocación de segmentos sobre la [[!UICONTROL tabla de forma libre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
3. Utilice la métrica **[!UICONTROL Personas]** para contar las personas nuevas únicas.

+++

+++Tasa de salida hacia otro sitio → Tasa de salida hacia otro sitio (con advertencias)

**Tasa de salida hacia otro sitio** de GA4 es el porcentaje de sesiones que no se realizaron (en menos de 10 segundos, sin evento clave, menos de 2 vistas de página). Es el inverso de Tasa de participación.

La métrica **[!UICONTROL Tasa de salida hacia otro sitio]** de Customer Journey Analytics usa una definición diferente de manera predeterminada y se puede configurar por vista de datos. Estas diferencias producen números materialmente diferentes que miden comportamientos diferentes.

Para aproximarse a la tasa de salida hacia otro sitio de GA4 en Customer Journey Analytics, cree una métrica Tasa de participación e inviértala con una segunda métrica calculada definida como `1 - Engagement Rate`. Consulte [Sesiones involucradas](compare-data.md#engagement-rate) para ver la compilación paso a paso.

Consulte [Por qué difieren los datos de GA4 y Customer Journey Analytics](compare-data.md#bounce-rate) para obtener una explicación detallada de la diferencia en la definición.

+++

+++Eventos clave → métricas de eventos personalizados

Los **eventos clave** de GA4 (anteriormente denominados Conversiones) son eventos designados como resultados comerciales importantes en la configuración de propiedades de GA4.

En Customer Journey Analytics, una conversión es una métrica de evento personalizada que se configura en la vista de datos. Cualquier evento XDM puede exponerse como métrica y una métrica puede configurarse para incrementarse condicionalmente en un valor de campo XDM; por ejemplo, una métrica **[!UICONTROL Compras]** que se incrementa cuando `xdm.eventType` es igual a `commerce.purchases`. Busque la métrica relevante por su etiqueta en el panel Componentes de Analysis Workspace; el nombre refleja la configuración que realizó el administrador.

Para reproducir el *informe* de eventos clave de GA4 (una lista de todas las conversiones con su recuento), consulte la entrada **Eventos clave (conversiones)** en [Participación](#engagement) en esta página.

+++

>[!MORELIKETHIS]
>
>* [Informe sobre datos de Google Analytics](/help/use-cases/third-party/ga/report.md)
