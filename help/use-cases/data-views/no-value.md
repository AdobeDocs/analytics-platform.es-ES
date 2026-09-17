---
title: Gestión de Sin Valor en Informes de Customer Journey Analytics
description: Aprenda cuándo se esperan **[!UICONTROL No se esperan entradas de valor]** en los informes de Customer Journey Analytics y cuándo indican un problema de recopilación de datos que requiere atención.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: bc1e610ccf13ca831f40b2819a4665fe8ea21b7b
workflow-type: tm+mt
source-wordcount: '1936'
ht-degree: 0%
---

# Cómo controlar Ningún valor

Cuando se trabaja con Customer Journey Analytics, encontrar **[!UICONTROL entradas sin valor]** en informes y paneles plantea preguntas importantes acerca de la calidad de los datos, los métodos de recopilación y la precisión de los informes. Estas instancias requieren una monitorización cuidadosa, ya que revelan lagunas ocultas en la recopilación de datos. El desafío consiste en distinguir entre dos situaciones: cuando las entradas **[!UICONTROL Sin valor]** necesitan ser investigadas por los proveedores de fuentes de datos y cuando las entradas **[!UICONTROL Sin valor]** reflejan el flujo natural de datos a Customer Journey Analytics. Comprender esta distinción es crucial para mantener operaciones de análisis eficientes. Esta guía le ayuda a tomar decisiones informadas sobre las apariciones de **[!UICONTROL No value]** en su implementación de Customer Journey Analytics.

## Comprender Ningún valor

**[!UICONTROL No aparece ningún valor]** cuando una dimensión no tiene un valor correspondiente para un evento que, de lo contrario, contiene una métrica. Ver **[!UICONTROL Ningún valor]** en un informe no siempre es un problema. En muchos casos, refleja la estructura esperada del conjunto de datos.

Los elementos de Dimension se dividen en tres categorías:

* **No se esperaba [!UICONTROL ningún valor]**: un resultado natural de cómo se mueven los usuarios por los datos, como los visitantes que aún no han iniciado sesión o las dimensiones que no se aplican a todos los eventos
* **Problema [!UICONTROL Sin valor]**: el resultado de una recopilación de datos fallida o un error de implementación, donde un valor existe pero falta
* **Valor válido**: La dimensión capturó correctamente un valor

El diagrama siguiente muestra cómo Customer Journey Analytics llega a cada una de estas categorías a medida que los datos se mueven desde el origen a través de Adobe Experience Platform.

El diagrama de flujo ilustra cómo las evaluaciones de Customer Journey Analytics se centran en los datos entrantes comprobando primero la presencia de valores y, a continuación, determinando si los valores que faltan son esperados o problemáticos. Esta evaluación clara ayuda a los administradores y analistas a diferenciar entre los casos de **[!UICONTROL Sin valor]** que requieren investigación de origen y los que representan operaciones normales.

![Flujo de decisión que muestra los datos de origen que se mueven a través de Adobe Experience Platform a Customer Journey Analytics, que comprueba si un valor de dimensión está presente, si un valor que falta es un escenario esperado, lo que da como resultado un valor No natural, un valor No problemático o un valor válido](assets/no-value-flow.svg)

## Cuando no se espera ningún valor

Los siguientes son motivos comunes y esperados por los que **[!UICONTROL Ningún valor]** aparece en un informe:

* Una dimensión solo se aplica a escenarios específicos, como la fuente de tráfico o el tipo de dispositivo
* Todavía no se ha asignado un identificador a un visitante primerizo
* Un visitante está en estado previo al inicio de sesión y no ha proporcionado información del usuario
* Una interacción de función o producto no se aplica a un recorrido de usuario en particular
* Un escenario entre dispositivos no transmite valores de dimensión entre dispositivos

En estos casos, **[!UICONTROL Ningún valor]** indica dónde se encuentra un usuario en su recorrido de autenticación durante la transición de un estado no identificado a un estado identificado, como se muestra a continuación.

![recorrido de autenticación de usuario que muestra a un usuario que visita el sitio e introduce un estado previo al inicio de sesión sin información de usuario disponible; a continuación, un evento de inicio de sesión que rellena la información del usuario](assets/no-value-login-flow.svg)


## Cuando Ningún valor necesita atención

Investigue las entradas **[!UICONTROL Sin valor]** cuando sean el resultado de cualquiera de las siguientes acciones:

**Problemas de implementación en el origen de datos:**

* Faltan datos o valores nulos
* Asignación de variables incorrecta
* Una capa de datos configurada incorrectamente
* Error de recopilación de datos
* Discrepancia entre los datos entrantes y el esquema definido

**Problemas de calidad de datos:**

* Código de seguimiento dañado
* Recopilación de datos incompleta
* Errores de integración
* Errores introducidos durante la transformación de datos
* Interrupciones en la canalización de datos

## Administrar Ningún valor en la configuración de vista de datos

La configuración de vista de datos le permite controlar cómo se muestran los elementos **[!UICONTROL Sin valor]** en los informes. Esto incluye cambiar el nombre de la etiqueta, mostrar u ocultar los elementos de forma predeterminada y tratar **[!UICONTROL Sin valor]** como un valor de cadena legítimo. Consulte [Configuración del componente Opciones sin valor](/help/data-views/component-settings/no-value-options.md) para obtener una lista completa de las opciones y cómo afectan a las distribuciones de porcentaje, al filtrado y a la segmentación.

Al configurar esta configuración, evalúe los requisitos de informes y cómo la presencia de **[!UICONTROL Ningún valor]** afecta a su análisis. Considere tanto los efectos inmediatos en la visibilidad de los datos como los impactos a largo plazo en el análisis de tendencias y la coherencia de la creación de informes. Las configuraciones bien elegidas mejoran la claridad de los datos al tiempo que mantienen las perspectivas comerciales accesibles y procesables, independientemente de cómo aparezcan las entradas de **[!UICONTROL Sin valor]** en los informes. La configuración ideal equilibra la representación de datos con las necesidades analíticas prácticas, creando un entorno de informes que ofrece perspectivas precisas y significativas incluso cuando **[!UICONTROL No hay ningún valor]** datos presentes.

La siguiente tabla resume las distintas configuraciones disponibles.

<table>
<thead>
<tr>
<th>Categoría</th>
<th>Configuración</th>
<th>Qué hace</th>
<th>Impacto</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="2">Mostrar opciones</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Se puede incluir o excluir mediante la selección de casillas de verificación en el filtro de búsqueda de tabla de forma libre.</td>
<td rowspan="2">Visibilidad</td>
</tr>
<tr>
<td><img src="assets/dont-show-no-value-default.png"/></td>
</tr>
<tr>
<td rowspan="2">Nomenclatura personalizada</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Afecta a la visualización del valor de dimensión de informes y a la consolidación de valores y agregación de métricas potenciales.</td>
<td rowspan="2">Nombre</td>
</tr>
<tr>
<td><img src="assets/show-unknown-as-value.png"/></td>
</tr>
<tr>
<td rowspan="3">Opciones de tratamiento</td>
<td><img src="assets/treat-no-value-as-value.png"/></td>
<td>Solo se aplica a dimensiones no numéricas.
Afecta tanto a la atribución como a la opción de inclusión **[!UICONTROL Ningún valor]** en el filtro de búsqueda de tabla de forma libre.</td>
<td>Administración de valores y visibilidad</td>
</tr>
<tr>
<td rowspan="2">Compatibilidad con dimensiones numéricas:<br><img src="assets/dont-show-no-value-default.png"/><br/><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Se puede incluir o excluir mediante la selección de casillas de verificación en el filtro de búsqueda de tabla de forma libre</td>
<td rowspan="2">Visibilidad</td>
</tr>
<tr>
</tr>
</tbody>
</table>


### Si se muestra, solicite Sin valor

Esta configuración le permite personalizar la forma en que se muestran las filas **[!UICONTROL Sin valor]** en los informes. Puede escribir un nombre personalizado para el elemento de dimensión **[!UICONTROL Sin valor]** en el campo de texto, lo que proporciona un contexto más significativo mediante **[!UICONTROL Si se muestra, llame a &quot;Sin valor&quot;]**. El uso de términos claros y prácticos en lugar de `No value` ayuda a su organización a comprender mejor los valores de los informes. Aunque no puede usar **[!UICONTROL Ningún valor]** directamente como cadena en segmentos, puede lograr el mismo efecto usando el operador **[!UICONTROL no existe]**.

Puede reemplazar `No value` con términos descriptivos como `Pre-login User` para el estado de autenticación, `No Customer Tier` para clientes sin niveles o `No Tracked Marketing Channel` para orígenes de marketing no identificados. Esto crea informes más intuitivos. `Pre-login User` muestra claramente dónde se encuentra un cliente en su recorrido, mientras que `No Customer Tier` proporciona un contexto específico. Recuerde que la descripción elegida se aplica a todas las instancias de **[!UICONTROL Sin valor]** para esa dimensión, por lo que debe seleccionar términos que reflejen con precisión todos los escenarios en los que los valores de dimensión estén ausentes.

### No mostrar Ningún valor de forma predeterminada

Esta configuración determina si se deben ocultar **[!UICONTROL Sin valor]** filas de forma predeterminada en los informes. Cuando se habilita, estas filas se filtran inicialmente, pero se pueden mostrar dentro de una tabla de forma libre si es necesario activando la casilla de verificación dentro del filtro de búsqueda de la tabla de forma libre. Tenga en cuenta que ocultar **[!UICONTROL Sin valor]** filas afecta la distribución porcentual de los valores restantes, ya que los porcentajes se recalculan basándose únicamente en los elementos visibles.

### Mostrar Ningún valor de forma predeterminada

Esta opción controla si **[!UICONTROL Ningún valor]** aparece de forma predeterminada en los informes. Cuando está habilitada, **[!UICONTROL No hay entradas con valor]** visibles, aunque los usuarios pueden excluirlas usando la casilla de verificación del filtro de búsqueda de tabla de forma libre. Incluir o excluir **[!UICONTROL No value]** rows afecta a las distribuciones de porcentaje, ya que los porcentajes se calculan basándose únicamente en los elementos visibles.

### Tratar Ningún valor como valor

Esta configuración trata **[!UICONTROL Ningún valor]** como un valor de cadena (excepto para dimensiones numéricas), lo que le permite personalizar su representación como un valor de dimensión. Esta personalización afecta tanto a la atribución como a la opción **[!UICONTROL Incluir sin valor]** en el filtro de búsqueda de tablas de forma libre. Tenga en cuenta que cuando asigna un valor de cadena personalizado, todos los valores coincidentes del conjunto de datos se consolidan en el mismo valor de cadena de dimensión.

La configuración **[!UICONTROL Tratar &quot;Sin valor&quot; como un valor]** tiene un propósito diferente a mostrar **[!UICONTROL Sin valor]** de manera predeterminada. Mientras que mostrar de forma predeterminada solo controla la visibilidad, tratar como un valor cambia la forma en que Customer Journey Analytics gestiona lógicamente estas entradas. Por este motivo, esta distinción es importante:

* Permite un control más granular en el filtrado y la segmentación, lo que hace de **[!UICONTROL Ningún valor]** un valor de dimensión distinto y procesable.
* Mantiene una atribución y representación coherentes en todo el análisis al tratar **[!UICONTROL Ningún valor]** como un valor de dimensión legítimo tanto en los modelos de atribución como en las visualizaciones.

Tratará **[!UICONTROL Ningún valor]** como un valor cuando:

* La ausencia de datos en sí misma es significativa para el análisis (como los estados previos al inicio de sesión o el tráfico no atribuido).
* Debe crear segmentos o métricas calculadas que dirijan o excluyan específicamente estos casos.

Por el contrario, mostrar **[!UICONTROL Ningún valor]** de forma predeterminada es más adecuado cuando necesita visibilidad básica de los datos que faltan sin la complejidad de la lógica y la atribución adicionales que conlleva tratarlo como un valor.

### No se admite ningún valor para dimensiones numéricas

Para las dimensiones numéricas, hay varias opciones de configuración disponibles. En la configuración de las dimensiones de vista de datos, puede configurar todas las opciones de **[!UICONTROL Sin valor]** excepto **[!UICONTROL Tratar &quot;Sin valor&quot; como un valor]**. También puede administrar **[!UICONTROL Incluir &quot;Sin valor&quot;]** para dimensiones numéricas mediante la selección de la casilla de verificación dentro del filtro de búsqueda de tabla de forma libre. Al crear segmentos, puede usar los operadores **[!UICONTROL exists]** o **[!UICONTROL does not exist]** con dimensiones numéricas.

### Sin dimensiones de nivel de valor y elemento

Algunas dimensiones se aplican en el nivel de elemento dentro de una matriz, en lugar de en el nivel superior de un evento. Por ejemplo, `productListItems.SKU`, solo tiene un valor cuando existe un elemento de lista de productos para ese evento. Esta diferencia en el granulado de datos cambia el comportamiento de **[!UICONTROL Ningún valor]**.

Para una dimensión de nivel superior estándar, Customer Journey Analytics puede colocar una métrica en un bloque **[!UICONTROL Sin valor]** siempre que falte esa dimensión o tenga un valor nulo en un evento que, de lo contrario, lleve una métrica. Una dimensión de nivel de elemento depende del elemento existente en primer lugar. Si un evento lleva una métrica pero carece de elementos de lista de productos, Customer Journey Analytics no tiene ninguna fila a la que adjuntar esa métrica o marcar los datos como **[!UICONTROL Ningún valor]**.

Customer Journey Analytics no crea un marcador de posición ni una fila vacía para las matrices que faltan o están vacías. Como resultado, puede configurar correctamente la configuración de la vista de datos **[!UICONTROL Sin valor]** y seguir sin ver las entradas **[!UICONTROL Sin valor]** en un informe de nivel de elemento, como un desglose de SKU. La falta de entradas es una diferencia de granularidad de datos y no un problema de configuración. La configuración de **[!UICONTROL Sin valor]** rige la forma en que se muestran las filas existentes, y una matriz vacía significa que no existen filas en ese nivel de granularidad de datos.

Cuando los recuentos de elementos **[!UICONTROL Sin valor]** se ven más bajos de lo esperado, compruebe si los datos de matriz que faltan explican el espacio antes de asumir que es necesario ajustar la configuración de la vista de datos.

## Prácticas recomendadas

Una vez que haya identificado **[!UICONTROL instancias sin valor]** problemáticas, deberá desarrollar e implementar una estrategia de corrección. Esta corrección se puede realizar de dos maneras:

* Ajuste la configuración de opciones del componente de vista de datos **[!UICONTROL Sin valor]**, o
* Solucionar problemas en el origen de recopilación de datos.

Elija su enfoque con cuidado, ya que cada ruta tiene diferentes implicaciones tanto para las correcciones rápidas como para la calidad de los datos a largo plazo. La implementación sigue un proceso metódico que corrige los problemas actuales y evita los futuros. El éxito depende de la planificación, la ejecución sistemática y la monitorización continua.

Estas son las consideraciones estratégicas clave para el plan de corrección:

### Evitar problemas de Sin valor

* Validar los datos antes de procesarlos.
* Establezca los valores de dimensión predeterminados cuando corresponda (nunca para un ID de persona)
* Documentar los escenarios donde se espera **[!UICONTROL Ningún valor]**
* Añadir comprobaciones de calidad en el punto de recopilación de datos
* Monitorización del cumplimiento del modelo de datos
* Registrar errores durante la recopilación de datos
* Añadir pruebas automatizadas para la implementación
* Requerir campos de esquema donde siempre existe un valor

### Validación Ningún valor en los informes

* Crear segmentos que aíslan **[!UICONTROL patrones sin valor]**
* Cree un panel de control de calidad que supervise las tendencias de **[!UICONTROL Ningún valor]** a lo largo del tiempo
* Configurar alertas que hagan un seguimiento de los cambios en el volumen **[!UICONTROL Sin valor]**
* Generar informes automatizados que resalten los cambios de patrón significativos.
* Referencia cruzada **[!UICONTROL Sin patrones de valor]** en dimensiones relacionadas
* Realice auditorías regulares de la configuración de la vista de datos
* Mantener un registro de cambios de cambios en su estrategia **[!UICONTROL Sin valor]**
* Creación de procedimientos operativos estándar y plantillas de documentación para las partes interesadas

## Conclusión

No todas las **[!UICONTROL entradas sin valor]** indican un problema. La interpretación correcta de **[!UICONTROL Sin valor]** requiere comprender la arquitectura de datos de Adobe Experience Platform y Customer Journey Analytics, así como el modo en que los usuarios se desplazan por el producto o sitio. En lugar de intentar eliminar cada instancia de **[!UICONTROL Sin valor]**, establezca reglas documentadas para toda la organización que distingan entre **[!UICONTROL Sin valor]** y **[!UICONTROL Sin valor]** problemático, basándose en sus propios recorridos de usuario y casos comerciales.

>[!MORELIKETHIS]
>
>[El manual de implementación completo para administrar **[!UICONTROL Ningún valor]** en Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/the-complete-playbook-for-handling-no-value-in-adobe-cja-12769)
