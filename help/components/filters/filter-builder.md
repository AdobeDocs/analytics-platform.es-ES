---
description: El Generador de filtros proporciona un lienzo al que arrastrar y en el que soltar los Dimension de métricas, los filtros y los eventos para filtrar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar filtros simples o complejos que identifican atributos y acciones de visitantes en visitas y eventos.
title: Generar filtros
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 36%

---

# Generador de filtros

El [!UICONTROL Generador de filtros] permite generar filtros simples o complejos que identifican atributos y acciones de visitantes en visitas y eventos. Proporciona un lienzo al que arrastrar y en el que soltar las dimensiones de métricas, los eventos u otros filtros para filtrar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía.

Para obtener información sobre cómo crear filtros rápidos que se apliquen únicamente al proyecto en el que se han creado, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

## Acceso al Generador de filtros

Puede acceder al Generador de filtros de cualquiera de las siguientes maneras:

* **Navegación superior de Analytics**: haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Filtros]**.
* **[!UICONTROL Analysis Workspace]**: Con un proyecto abierto en Analysis Workspace, seleccione **[!UICONTROL + Componentes]** > **[!UICONTROL Crear filtro]**.
* **[!UICONTROL Reports &amp; Analytics]**: haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Informes]**, abra un informe existente y haga clic en **Filtrar** en el panel de navegación izquierdo y haga clic en **[!UICONTROL Añadir]**.
* **[!UICONTROL Report Builder]**: [Adición o edición de filtros en el Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=es).

## Resumen de criterios del generador {#section_F61C4268A5974C788629399ADE1E6E7C}

Puede agregar definiciones de reglas y contenedores para definir los filtros. (Para obtener información sobre el acceso al Generador de filtros, consulte [Acceso al Generador de filtros](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Título]**: Asigne un nombre al filtro.
1. **[!UICONTROL Descripción]**: proporcione una descripción para el filtro.
1. **[!UICONTROL Etiquetas]**: [Etiquetado del filtro](/help/components/filters/manage-filters.md) para crear, seleccione una lista de etiquetas existentes o cree una etiqueta nueva.
1. **[!UICONTROL Definiciones]**: Aquí es donde [generación y configuración de filtros](/help/components/filters/filters-overview.md), agregue reglas y anide y secuencie contenedores.
1. **[!UICONTROL Mostrar]**: (Selector de contenedor superior). Permite seleccionar el nivel superior [contenedor](/help/components/filters/filters-overview.md) ( [!UICONTROL Persona], [!UICONTROL Session], [!UICONTROL Evento]). El contenedor de nivel superior predeterminado es el contenedor Evento.
1. Icono de **[!UICONTROL opciones]** (engranaje)

   * **[!UICONTROL + Agregar contenedor]**: le permite agregar un nuevo contenedor (debajo del contenedor de nivel superior) a la definición del filtro.
   * **[!UICONTROL Excluir]**: permite definir el filtro excluyendo una o más dimensiones, filtros o métricas.

1. **[!UICONTROL Dimensiones]**: Las dimensiones se arrastran y sueltan desde la lista Dimensiones (barra lateral naranja).
1. **[!UICONTROL Operador]**: Puede comparar y restringir valores utilizando una selección de operadores.
1. **[!UICONTROL Valor]**: El valor introducido o seleccionado para la dimensión, el filtro o la métrica.
1. **[!UICONTROL Modelos de atribución]**: Disponible solo para dimensiones, estos modelos determinan qué valores de una dimensión se filtran. Los modelos de Dimension son especialmente útiles en filtros secuenciales.

   * **[!UICONTROL Repetido]** (por defecto): Incluye instancias y valores persistentes para la dimensión.
   * **[!UICONTROL Instancia]**: Incluye instancias para la dimensión.
   * **[!UICONTROL Instancia no repetida]**: Incluye instancias únicas (no repetitivas) para la dimensión. Este es el modelo aplicado en Flujo cuando se excluyen instancias repetidas.

   ![](assets/attribution-models.jpg)

   **Ejemplo: Filtro de eventos donde eVar 1 = A**

   | Ejemplo | A | A | A (persistió) | B | A | C |
   |---|---|---|---|---|---|---|
   | Repetido | X | X | X | - | X | - |
   | Instancia | X | X | - | - | X | - |
   | Instancia no repetida | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: Asigna los operadores [!UICONTROL AND/OR/THEN] entre contenedores o reglas. El operador THEN le permite [definir filtros secuenciales](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Métrica]**: Métrica arrastrada y soltada a partir de la lista Métricas.
1. Operador de **[!UICONTROL comparación]**: Puede comparar y restringir valores utilizando una selección de operadores.
1. **[!UICONTROL Valor]**: El valor introducido o seleccionado para la dimensión, el filtro o la métrica.
1. **[!UICONTROL X]**: (Eliminar) Permite eliminar esta parte de la definición del filtro.
1. **[!UICONTROL publicación de Experience Cloud]**: La publicación de un filtro de Adobe Analytics en el Experience Cloud permite utilizarlo para la actividad de marketing en [!DNL Audience Manager] y en otros canales de activación. [Más información...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=es)
1. **[!UICONTROL Biblioteca de audiencias]**: los servicios de audiencia de Adobe administran la traducción de datos sobre visitantes en filtros de audiencia. De este modo, la creación y gestión de audiencias es similar a la creación y uso de filtros, con la capacidad añadida de compartir filtros de audiencia con el Experience Cloud. [Más información...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es)
1. **[!UICONTROL Buscar]**: Busca en la lista de dimensiones, filtros o métricas.
1. **[!UICONTROL Dimensiones]**: (Lista) Haga clic en el encabezado para ampliarlo.
1. **[!UICONTROL Métricas]**: Haga clic en el encabezado para ampliarlo.
1. **[!UICONTROL Filtros]**: haga clic en el encabezado para ampliarlo.
1. **[!UICONTROL Selector de vista de datos]**: le permite seleccionar el grupo de informes en el que se guardará este filtro. Puede seguir utilizando el filtro en todas las vistas de datos.
1. **[!UICONTROL Previsualización de filtro]**: Permite obtener una vista previa de las métricas clave para ver si tiene un filtro válido y su amplitud. Representa el desglose del conjunto de datos que verá si aplica este filtro. Muestra tres círculos concéntricos y una lista para indicar el número y el porcentaje de coincidencias [!UICONTROL Evento], [!UICONTROL Persona], y [!UICONTROL Session] para un filtro ejecutado con un conjunto de datos. Este gráfico se actualiza inmediatamente después de crear o realizar cambios en la definición del filtro.
1. **[!UICONTROL Compatibilidad del producto]**: Proporciona una lista de los productos de Adobe Analytics (Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Data Warehouse) con el que es compatible el filtro que ha creado. La mayoría de los filtros son compatibles con todos los productos. Sin embargo, no todos los operadores y dimensiones son compatibles con todos los productos de Analytics, en especial [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Esta tabla se actualiza inmediatamente después de realizar cambios en la definición del filtro.
1. **[!UICONTROL Guardar]** o **[!UICONTROL Cancelar]**: guarda o cancela el filtro. Después de hacer clic **[!UICONTROL Guardar]**, se le redirigirá al Administrador de filtros, donde podrá administrar el filtro.

Los filtros con intervalos de fechas incorporados siguen operando en Analysis Workspace de forma diferente a [!UICONTROL Reports &amp; Analytics]: en Workspace, un filtro con un intervalo de fechas incrustado anula el intervalo de fechas del panel. Por el contrario, [!UICONTROL Reports &amp; Analytics] proporciona la intersección del intervalo de fechas del informe y el intervalo de fechas incrustado del filtro.

## Generar un filtro {#build-filters}

1. Basta con arrastrar un Dimension, un filtro o un evento de métrica del panel izquierdo al [!UICONTROL Definiciones] field.

   ![](assets/drag_n_drop_dimension.png)

1. Establezca el [operador](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=es) en el menú desplegable.
1. Introduzca o seleccione un valor para el elemento seleccionado.
1. Agregue contenedores adicionales si es necesario, utilizando las reglas **[!UICONTROL AND]**, **[!UICONTROL OR]** o **[!UICONTROL THEN]**.
1. Después de colocar los contenedores y configurar las reglas, consulte los resultados del filtro en la tabla de validación, en la parte superior derecha. El validador indica el porcentaje y el número absoluto de vistas de página, visitas y visitantes únicos que coinciden con el filtro que ha creado.
1. En **[!UICONTROL Etiquetas]**, [etiqueta](/help/components/filters/manage-filters.md) Seleccione el contenedor seleccionando una etiqueta existente o creando una nueva.
1. Clic **[!UICONTROL Guardar]** para guardar el filtro.

   Se le redirige a la [Administrador de filtros](/help/components/filters/manage-filters.md), donde puede etiquetar, compartir y administrar el filtro de varias formas.

## Añadir contenedores {#section_1C38F15703B44474B0718CEF06639EFD}

Puede [generar un marco de contenedores](/help/components/filters/filters-overview.md) y luego colocar reglas lógicas y operadores entre medias.

1. Clic **[!UICONTROL Opciones > Agregar contenedor]**.

   Un nuevo [!UICONTROL **Evento**] el contenedor se abre sin un [!UICONTROL **Evento**] (Vista de página) identificados.

   ![](assets/new_container.png)

1. Cambie el tipo de contenedor según sea necesario.
1. Arrastre un Dimension, un filtro o un evento desde el panel izquierdo al contenedor.
1. Siga agregando nuevos contenedores desde el botón **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor]** del nivel superior situado en la parte superior de la definición, o agregue contenedores desde dentro de un contenedor para anidar la lógica.

   **OR**

   Seleccione una o más reglas y luego haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor de selección]**. Esto convierte su selección en un contenedor separado.

## Usar intervalos de fechas {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puede generar filtros que contengan intervalos de fechas móviles para responder a preguntas sobre campañas o eventos en curso.

Por ejemplo, puede crear fácilmente un filtro que incluya a &quot;todas las personas que hayan realizado una compra en los últimos 60 días&quot;.

Cree un contenedor de sesión y, dentro de él, agregue [!UICONTROL Últimos 60 días] intervalo de tiempo y métrica [!UICONTROL Pedidos es bueno o igual a 1], con un operador AND.

Aquí tiene un vídeo sobre el uso de intervalos de fechas móviles en los filtros:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Apilado de filtros {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

El apilamiento de filtros funciona mediante la combinación de criterios en cada filtro utilizando un operador &quot;and&quot;, y luego aplicando los criterios combinados. Esto se puede hacer directamente en un proyecto de Workspace o en el Generador de filtros.

Por ejemplo, apilar un filtro &quot;usuarios de teléfonos móviles&quot; y un filtro &quot;geografía de Estados Unidos&quot; devolvería datos solo para usuarios de teléfonos móviles en Estados Unidos.

Piense en estos filtros como bloques de creación o módulos que puede incluir en una biblioteca de filtros para que los usuarios los utilicen como les parezca adecuado. De este modo, puede reducir drásticamente el número de filtros necesarios. Por ejemplo, supongamos que tiene 40 filtros:

* 20 para usuarios de teléfonos móviles en diferentes países (EEUU_móvil, Alemania_móvil, Francia_móvil, Brasil_móvil, etc.).
* 20 para usuarios de tabletas en diferentes países (EEUU_tableta, Alemania_tableta, Francia_tableta, Brasil_tableta, etc.).

Al utilizar el apilamiento de filtros, puede reducir el recuento de filtros a 22 y apilarlos según sea necesario. Debe crear estos filtros:

* un filtro para usuarios móviles
* un filtro para usuarios de tablet
* 20 filtros para las diferentes regiones geográficas

>[!NOTE]
>
>Al apilar dos filtros, se unen de forma predeterminada con una instrucción AND. No es posible cambiarlo a una instrucción OR.

1. Vaya al Generador de filtros.

1. Proporcione un título y una descripción para el filtro.

1. Clic **[!UICONTROL Mostrar filtros]** para que aparezca la lista de filtros en el panel de navegación izquierdo.

1. Arrastre los filtros que desee apilar al lienzo de definición del filtro.

1. Seleccione [!UICONTROL **Guardar**].

## Filtrar plantillas {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Las plantillas de filtro se proporcionan para casos de uso de filtros comunes, como &quot;Visitas por primera vez&quot; o &quot;Visitas desde dispositivos móviles&quot;. Están disponibles en proyectos de Workspace y en el Generador de filtros como componentes básicos para nuevos filtros.

Las plantillas se identifican con el logotipo “A” de Adobe. A continuación puede consultar una muestra de las plantillas:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de plantilla </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandonar carro </td> 
   <td colname="col2">Ver datos de visitantes que agregaron elementos al carro pero no realizaron ningún pedido. En la Definición del filtro, el contenedor es Visita. La regla para este filtro secuencial es <p> Adiciones al carro no es nulo </p> <p>Entonces </p> <p>Pedidos es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas por primera vez </td> 
   <td colname="col2">Ver datos de visitantes que han visitado el sitio como máximo una [1] vez. En la Definición del filtro, el contenedor es Visita. La regla es: <p>Número de visitas es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No compradores </td> 
   <td colname="col2">Ver datos de los visitantes que no participaron en un evento de pedido. En la definición del filtro, el contenedor es Visitante. Este filtro utiliza la lógica Exclude. La regla es: <p>El pedido no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita de página no única (no rebotes) </td> 
   <td colname="col2">Ver datos de los visitantes que visitaron más de una vez. En la definición del filtro, el contenedor es Visitante. Este filtro utiliza la lógica Exclude. La regla es: <p>El acceso único no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Búsqueda de pago </td> 
   <td colname="col2">Ver datos de visitantes procedentes de una búsqueda de pago. En la Definición del filtro, el contenedor es Visita. La regla es: <p>La búsqueda de pago es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compradores </td> 
   <td colname="col2">Ver datos de los visitantes que participaron en un evento de pedido. En la definición del filtro, el contenedor es Visitante. La regla es: <p>El pedido no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno </td> 
   <td colname="col2">Ver datos de los visitantes que han visitado por lo menos una vez. En la Definición del filtro, el contenedor es Visita. La regla es: <p>Número de visitas es mayor que 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de página única </td> 
   <td colname="col2"> Ver datos de las visitas en las que se ve el valor de una sola página, aunque se envíen varias vistas de página durante esa visita. Las visitas a una sola página con eventos de vínculo de salida se incluyen en el filtro. En la Definición del filtro, el contenedor es Visita. La regla es: <p>Visitas de página única es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Producto visto no se agregó al carro </td> 
   <td colname="col2">Ver datos de los visitantes que vieron productos pero no agregaron nada al carro. En la Definición del filtro, el contenedor es Visita. La regla para este filtro secuencial es <p>Vistas de producto no es nulo </p> <p>Entonces </p> <p> Adiciones al carro es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde campaña </td> 
   <td colname="col2">Ver datos de visitantes remitidos desde campañas. En la Definición del filtro, el contenedor es Visita. La regla es: <p>El código de seguimiento no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde dispositivos móviles </td> 
   <td colname="col2">Ver datos de visitantes que utilizan dispositivos móviles. En la Definición del filtro, el contenedor es Visita. La regla es: <p>El dispositivo móvil no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de búsqueda natural </td> 
   <td colname="col2">Ver datos de visitantes que no proceden de una búsqueda de pago. En la Definición del filtro, el contenedor es Visita. La regla es: <p>La búsqueda de pago es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde un dispositivo no móvil </td> 
   <td colname="col2">Ver datos de visitantes que no utilizan dispositivos móviles. En la Definición del filtro, el contenedor es Visita. Este filtro utiliza la lógica Exclude. La regla es: <p>El tipo de dispositivo móvil es igual a teléfono móvil </p> <p>o </p> <p>El tipo de dispositivo móvil es igual a tableta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde teléfonos </td> 
   <td colname="col2">Ver datos de los visitantes que utilizan teléfonos. En la Definición del filtro, el contenedor es Visita. La regla es: <p>El tipo de dispositivo es igual a teléfono móvil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde motores de búsqueda </td> 
   <td colname="col2">Ver datos de visitantes remitidos desde motores de búsqueda. En la Definición del filtro, el contenedor es Visita. La regla es: <p>El tipo de referente es igual a motores de búsqueda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas provenientes de sitios sociales </td> 
   <td colname="col2">Ver datos de visitantes remitidos desde sitios sociales. En la Definición del filtro, el contenedor es Visita. La regla es: <p>El tipo de referente es igual a redes sociales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde tabletas </td> 
   <td colname="col2">Ver datos de los visitantes que utilizan tabletas. En la Definición del filtro, el contenedor es Visita. La regla es: <p>El tipo de dispositivo es igual a tableta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas con cookie de ID de visitante </td> 
   <td colname="col2">Ver datos de los visitantes del sitio con los que se requiere una cookie persistente. En la Definición del filtro, el contenedor es Visita. La regla es: <p>La cookie persistente es igual a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>