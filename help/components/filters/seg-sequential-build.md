---
description: Los filtros secuenciales se crean mediante el operador THEN, en lugar de AND u OR. THEN implica que se produce un criterio de filtro, seguido de otro. De forma predeterminada, un filtro secuencial identifica todos los datos coincidentes y muestra el filtro "Incluir a todos". Los filtros secuenciales pueden filtrarse adicionalmente a un subconjunto de visitas coincidentes mediante las opciones "Solo antes de secuencia" y "Solo después de secuencia".
title: Generar filtros secuenciales
feature: Filters
source-git-commit: 2a9880148864140254d8acb0a53d701c2986dcb1
workflow-type: tm+mt
source-wordcount: '3918'
ht-degree: 65%

---

# Generar filtros secuenciales

Los filtros secuenciales se crean mediante el operador THEN, en lugar de AND u OR. THEN implica que se produce un criterio de filtro, seguido de otro. De forma predeterminada, un filtro secuencial identifica todos los datos coincidentes y muestra el filtro &quot;Incluir a todos&quot;. Los filtros secuenciales pueden filtrarse adicionalmente a un subconjunto de visitas coincidentes mediante las opciones &quot;Solo antes de secuencia&quot; y &quot;Solo después de secuencia&quot;.

![](assets/before-after-sequence.png)

Este es un vídeo sobre la segmentación secuencial:

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

## Incluir a todos {#include_everyone}

Al crear un filtro en el que se define &quot;Incluir a todos&quot;, el filtro identifica las rutas que coinciden con el patrón determinado como conjunto. Este es un ejemplo de filtro de secuencia básico que busca una visita individual (Página A) seguida de otra (Página B) según la visita del mismo visitante. El filtro está establecido en Incluir a todos.

![](assets/filter.png)
![70a875e2-0ef9-4459-8648-77c60081d64d](https://git.corp.adobe.com/storage/user/5902/files/d55be11f-4c4c-4198-bba5-ecad27ebcabf)

| Si el resultado... | Secuencia |
|--- | --- |
| Coincide | A entonces B<br>A entonces (en una visita diferente) BA entonces D entonces B |
| No coincide | B entonces A |

## Solo Antes de la Secuencia y Solo Después de la Secuencia {#only_before_after}

Las opciones **[!UICONTROL Solo Antes de la Secuencia]** y **[!UICONTROL Solo Después de la Secuencia]** filtre el filtro a un subconjunto de datos anterior o posterior a la secuencia especificada.

* **Solo Antes de la Secuencia**: incluye todas las visitas anteriores a la secuencia + la primera visita de la propia secuencia (consulte los ejemplos 1 y 3). Si la secuencia aparece varias veces en una ruta, “Solo antes de la secuencia” incluye la primera visita de la última aparición de la secuencia y todas las visitas anteriores (consulte el ejemplo 2).
* **Solo Después de la Secuencia**: incluye todas las visitas posteriores a la secuencia + la última visita de la propia secuencia (consulte los ejemplos 1 y 3). Si la secuencia aparece varias veces en una ruta, “Solo después de la secuencia” incluye la última visita de la primera aparición de la secuencia y todas las visitas posteriores (consulte el ejemplo 2).

Por ejemplo, si tenemos una secuencia de B -> D, los tres filtros identificarán las visitas del modo siguiente:

**Ejemplo 1: B entonces D aparece una vez**

| Ejemplo | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Incluir a todos | A | B | C | D | E | F |
| Solo Antes de la Secuencia | A | B |  |  |  |  |
| Solo Después de la Secuencia |  |  |  | D | E | F |

**Ejemplo 2: B entonces D aparece varias veces**

| Ejemplo | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Incluir a todos | A | B | C | D | B | C | D | E |
| Solo Antes de la Secuencia | A | B | C | D | B |  |  |  |
| Solo Después de la Secuencia |  |  |  | D | B | C | D | E |

Vamos a enmarcar también este concepto con la dimensión Profundidad de visita.

**Ejemplo 3: Profundidad de visita 3 entonces 5**

![](assets/hit-depth.png)

## Restricciones de dimensión {#constraints}

En una cláusula “En”, entre instrucciones THEN, se puede agregar, por ejemplo, “En 1 instancia de palabra clave de búsqueda”, “En 1 instancia de eVar 47”. Esto restringe el filtro a una instancia de una dimensión.

La configuración de una cláusula &quot;En el Dimension&quot; entre reglas permite a un filtro restringir los datos a secuencias en las que se cumpla la cláusula. Vea el ejemplo siguiente, en el cual la restricción se define en “En 1 página”:

![](assets/sequence-filter4.png)

| Si el resultado... | Secuencia |
|--- |--- |
| Coincide | A entonces B |
| No coincide | A then C then B (porque B no estaba dentro de 1 página de A)<br>**Nota:** Si se elimina la restricción de dimensión, tanto “A then B” como “A then C then B” coincidirán. |

## Secuencia de vista de página simple {#simple_sequence}

Identifique a los visitantes que vieron una página y luego vieron otra página. Los datos en el nivel de visita individual filtrarán esta secuencia independientemente de las sesiones de visita anteriores, pasadas o intermedias, o el tiempo o el número de vistas de página que se sucedan entre ellas.

**Ejemplo**: Visitante que vio la página A y luego la página B en la misma visita o en otra.

**Casos de uso**

A continuación se muestran ejemplos de cómo se puede utilizar el filtro.

1. Los visitantes de un sitio de deportes ven la página de aterrizaje de fútbol y luego ven la página de aterrizaje de baloncesto en orden secuencial, pero no necesariamente en la misma visita. Esto da lugar a una campaña para ofrecer contenido de baloncesto a los espectadores de fútbol durante la temporada de fútbol.
1. El dueño de un concesionario de automóviles ve una relación entre aquellos que aterrizan en la página de fidelidad del cliente y luego van a la página de vídeos en cualquier momento durante la visita o en otra visita.

**Crear este filtro**

Anide dos reglas de página dentro de un contenedor de [!UICONTROL visitante] de nivel superior y secuencie las visitas individuales de página utilizando el operador [!UICONTROL THEN].

![](assets/segment_sequential_1.png)

## Secuencia de visitante en varias visitas {#sequence_across}

Identifique a aquellos visitantes que no siguieron una campaña pero que luego volvieron a la secuencia de vistas de página en otra sesión.

**Ejemplo**: Visitante que vio la página A en una visita y luego vio la página B en otra visita.

**Casos de uso**

A continuación se muestran ejemplos de cómo se puede utilizar este tipo de filtro:

* Los visitantes ven la página de deportes de un sitio de noticias y vuelven a visitar la página de deportes en otra sesión.
* Un comerciante de ropa ve una relación entre los visitantes que aterrizan en una página de aterrizaje en una sesión y luego van directamente a la página de pago en otra sesión.

**Crear este filtro**

Este ejemplo anida dos **[!UICONTROL Visita]** contenedores dentro del nivel superior **[!UICONTROL Visitante]** contenedor y secuencias del filtro utilizando el [!UICONTROL THEN] operador.

![](assets/visitor_seq_across_visits.png)

## Secuencia de nivel mixto {#mixed_level}

Identifique a los visitantes que ven dos páginas en un número indeterminado de visitas, pero luego ven una tercera página en una visita separada.

**Ejemplo**: Visitantes que ven la página A y luego la página B en una o más visitas, seguido de una visita separada a la página C.

**Casos de uso**

A continuación se muestran ejemplos de cómo se puede utilizar este tipo de filtro:

* Los visitantes ven primero un sitio de noticias y luego la página de deportes en la misma visita. En otra visita, el visitante ve la página del tiempo.
* Un comerciante define a los visitantes que acceden a la página principal y luego a la página Mi cuenta. En otra visita, acceden a la página Ver carro.

**Crear este filtro**

1. Suelte dos dimensiones de página desde los paneles izquierdos dentro de un contenedor de [!UICONTROL visitante] de nivel superior.
1. Agregue entre ellos el operador THEN.
1. Haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor]** y agregue un contenedor de [!UICONTROL visita] bajo el nivel de [!UICONTROL visitante] y secuenciado utilizando el operador [!UICONTROL THEN].

![](assets/mixed_level_checkpoints.png)

## Contenedores agregados {#aggregate_containers}

Si agrega múltiples contenedores de [!UICONTROL visita individual] dentro de un contenedor de [!UICONTROL visitante], puede emplear los operadores adecuados entre el mismo tipo de contenedores, y usar reglas y dimensiones tales como página y número de visita para definir la vista de página y proporcionar una dimensión de secuencia dentro del contenedor de [!UICONTROL visita individual]. La aplicación de lógica al nivel de visita individual le permite restringir y combinar coincidencias de visitas individuales del mismo nivel dentro de la variable [!UICONTROL Visitante] contenedor para generar una variedad de tipos de filtros.

**Ejemplo**: visitantes que visitaron la página A después de la primera visita individual en la secuencia de vistas de página (página D en el ejemplo) y luego visitaron la página B o la página C independientemente del número de visitas.

**Casos de uso**

A continuación se muestran ejemplos de cómo se puede utilizar este tipo de filtro:

* Identificar a los visitantes que acceden a la página de aterrizaje principal en una visita, después ven la página de ropa masculina en otra visita, y después ven la página de aterrizaje de ropa femenina o infantil en otra visita.
* Una revista electrónica captura a los visitantes que acceden a la página de inicio en una visita, a la página de deportes en otra visita y a la página de opinión en otra visita.

**Crear este filtro**

1. Seleccione el contenedor de [!UICONTROL visitante] como contenedor de nivel superior.
1. Agregue dos contenedores de nivel de [!UICONTROL visita individual] (una dimensión con una dimensión numérica adecuada unida en el mismo nivel de [!UICONTROL visita individual] por el operador [!UICONTROL AND] y [!UICONTROL OR]).
1. Dentro del contenedor de [!UICONTROL visita], agregue otro contenedor de [!UICONTROL visita individual] y anide dos contenedores de [!UICONTROL visita individual] adicionales unidos con un operador [!UICONTROL OR] o [!UICONTROL AND].

   Secuencie estos contenedores de [!UICONTROL visita individual] anidados con el operador [!UICONTROL THEN].

![](assets/aggregate_checkpoints2.png)

## &quot;Anidado&quot; en filtros secuenciales {#nesting}

Colocando puntos de comprobación en ambos [!UICONTROL Visita] y [!UICONTROL Visita] A nivel de, puede restringir el filtro para satisfacer los requisitos dentro de una visita específica, así como una visita individual específica.

**Ejemplo**: Visitante que visitó la página A y luego la página B en la misma visita. En una nueva visita, el visitante fue después a la página C.

**Crear este filtro**

1. Bajo el contenedor de [!UICONTROL visita] de nivel superior, arrastre dos dimensiones de página.
1. Haga una selección múltiple de ambas reglas, haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor de selección]** y cambie a un contenedor de [!UICONTROL visita].
1. Únalas con un operador [!UICONTROL THEN].
1. Cree un contenedor de visita individual como homólogo del contenedor de [!UICONTROL visita] y arrastre una dimensión de página.
1. Una la secuencia anidada en el contenedor de [!UICONTROL visita] con el contenedor de [!UICONTROL visita individual] usando otro operador [!UICONTROL THEN].

![](assets/nesting_sequential_seg.png)

## Excluir visitas {#exclude}

Las reglas de segmentos incluyen todos los datos a menos que se excluyan específicamente los datos de [!UICONTROL visitantes], [!UICONTROL visitas] o [!UICONTROL visitas individuales] usando la regla [!UICONTROL Excluir]. Permite descartar datos comunes y crear filtros con más enfoque. O bien, le permite crear filtros que excluyan los grupos que se hayan encontrado para identificar el conjunto de datos restante, como crear una regla que incluya a los visitantes que hayan hecho un pedido y luego excluirlos para identificar a los &quot;no compradores&quot;. Sin embargo, en la mayoría de casos, es mejor crear reglas que excluyan valores amplios en vez de intentar usar la regla [!UICONTROL Excluir] para dirigirse a valores de inclusión específicos.

Por ejemplo:

* **Exclusión de páginas**. Utilice una regla de filtro para eliminar una página específica (como *`Home Page`*) de un informe, cree una regla de visita individual en la que página sea igual a &quot;Página de inicio&quot; y luego exclúyala. Esta regla incluye automáticamente todos los valores excepto la página de inicio.
* **Exclusión de dominios de referencia**. Use una regla que incluya solo los dominios de referencia de Google.com y excluya todos los demás.
* **Identificación de los no compradores**. Identifique el momento en que los pedidos son superiores a cero y luego excluya al [!UICONTROL visitante].

El operador [!UICONTROL Exclude] puede emplearse para identificar una secuencia en la que las visitas o visitas individuales específicas no son efectuadas por el visitante. [!UICONTROL Excluir puntos de comprobación] también se puede incluir dentro de un grupo lógico (ver a continuación).

### Exclusión entre puntos de comprobación {#exclude_between}

Aplique lógica para filtrar visitantes donde un punto de comprobación no se produjo explícitamente entre otros dos puntos de comprobación.

**Ejemplo**: Visitantes que visitaron la página A y luego la página C, pero que no visitaron la página B.

**Casos de uso**

A continuación se muestran ejemplos de cómo se puede utilizar este tipo de filtro:

* Los visitantes que accedieron a la página de estilo de vida y luego a la sección de teatro sin visitar la página de arte.
* El dueño de un concesionario de automóviles ve una relación entre las personas que visitan la página de aterrizaje principal y luego acceden directamente a la campaña &quot;Sin intereses&quot; sin visitar la página del vehículo.

**Crear este filtro**

Cree un filtro como lo haría para un filtro secuencial simple, de nivel mixto o anidado y luego establezca el [!UICONTROL EXCLUIR] para el elemento contenedor. El ejemplo siguiente es un filtro agregado donde los tres [!UICONTROL Visita] los contenedores se arrastran al lienzo, la variable [!UICONTROL THEN] asignado para unir la lógica del contenedor y, a continuación, excluir el contenedor de vista de página central para incluir solo los visitantes que fueron de la página A a C en la secuencia.

![](assets/exclude_between_checkpoints.png)

### Exclusión al inicio de la secuencia {#exclude_beginning}

Si el punto de comprobación de exclusión se encuentra al principio de un filtro secuencial, se garantiza que no se ha producido una vista de página excluida antes de la primera visita individual no excluida.

Por ejemplo, un restaurante quiere ver los usuarios que tienden a evitar la página de aterrizaje principal y acceden directamente a la página de pedidos. Para ver estos datos, excluya las visitas a la página de aterrizaje e incluya las visitas a la página Ordenar de forma secuencial.

**Crear este filtro**

Cree dos contenedores de visita individual separados dentro de un contenedor de visitante de nivel superior. Luego establezca el operador [!UICONTROL EXCLUDE] para el primer contenedor.

![](assets/exclude_beginning_sequence.png)

### Exclusión al final de la secuencia {#exclude_end}

Si el punto de comprobación de exclusión está al final de la secuencia, se garantiza que el punto de comprobación no se produjo entre el último punto de comprobación no excluido y el final de la secuencia del visitante.

Por ejemplo, una tienda de ropa quiere conocer todos los visitantes que vieron una página de producto, pero que no visitaron más tarde su carro de compras. Este ejemplo se puede simplificar con que un visitante va a la página A y nunca a la B en visitas actuales o posteriores.

**Crear este filtro**

Creación de un filtro de secuencia simple arrastrando dos [!UICONTROL Visita] contenedores al lienzo y conectarlos mediante el [!UICONTROL THEN] operador. Luego asigne el operador [!UICONTROL EXCLUDE] al segundo contenedor de [!UICONTROL visita individual] de la secuencia.

![](assets/exclude_end_sequence.png)

## Contenedores de grupo lógico {#logic_group}

Los contenedores de grupo lógico son necesarios para agrupar condiciones en un único punto de comprobación secuencial de filtro. El contenedor de grupo lógico especial solo está disponible en la segmentación secuencial, para garantizar que sus condiciones se cumplen después de cualquier punto de comprobación secuencial anterior y antes de cualquier punto de comprobación secuencial siguiente. Las condiciones dentro del propio punto de comprobación del grupo lógico pueden cumplirse en cualquier orden. Por otro lado, los contenedores no secuenciales (visita individual, visita, visitante) no requieren que se cumplan sus condiciones dentro de la secuencia global, lo que produce resultados poco intuitivos si se utilizan con un operador THEN.
El contenedor de [!UICONTROL grupo lógico] fue diseñado para tratar *varios puntos de comprobación como un grupo*, *sin ningún orden* entre los puntos de comprobación agrupados. En otras palabras, no nos importa el orden de los puntos de comprobación dentro de ese grupo. Por ejemplo, no puede anidar un contenedor de [!UICONTROL visitante] dentro de un contenedor de [!UICONTROL visitante]. Sin embargo, puede anidar un contenedor de [!UICONTROL grupo lógico] dentro de un contenedor de [!UICONTROL visitante] con puntos de comprobación de niveles de [!UICONTROL visita] y [!UICONTROL visita individual] específicos.

>[!NOTE]
>
>A [!UICONTROL Grupo de lógica] solo se puede definir en un filtro secuencial, lo que significa que la variable [!UICONTROL THEN] se utiliza dentro de la expresión.

| Jerarquía de contenedores | Ilustración | Definición |
|---|---|---|
| Jerarquía de contenedor estándar | ![](assets/nesting_container.png) | Dentro de [!UICONTROL Visitante] contenedor, el [!UICONTROL Visita] y [!UICONTROL Visita] los contenedores se anidan en secuencia para extraer los filtros en función de las visitas individuales, el número de visitas y el visitante. |
| Jerarquía de contenedor lógico | ![](assets/logic_group_hierarchy.png) | La jerarquía de contenedor estándar también se requiere fuera del contenedor de [!UICONTROL grupo lógico]. No obstante, dentro del contenedor de [!UICONTROL grupo lógico], los puntos de comprobación no requieren un orden o jerarquía establecidos; dichos puntos de comprobación solo tienen que ser satisfechos por parte del visitante en cualquier orden. |

Los grupos lógicos pueden resultar intimidantes. Aquí tiene algunas prácticas recomendadas sobre cómo utilizarlos:

**¿Grupo lógico o contenedor de visita/visita individual?**
Si desea agrupar puntos de comprobación secuenciales, su “contenedor” es un grupo lógico. Sin embargo, si estos puntos de comprobación secuenciales deben producirse en el ámbito de una sola visita o visita individual, se requiere un contenedor de visita individual o de visita. (Por supuesto, &#39;visita individual&#39; no tiene sentido para un grupo de puntos de comprobación secuenciales, cuando una visita no puede acreditar más de un punto de comprobación).

**¿Simplifican los grupos lógicos la creación de filtros secuenciales?**
Sí. Supongamos que está intentando identificar este filtro de visitantes: **Los visitantes que vieron la página A y luego vieron todas las páginas de B, C y D**

Puede generar este filtro sin un contenedor de grupo lógico, pero es complejo y laborioso. Debe especificar cada secuencia de páginas que el visitante podría ver:
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

Un contenedor de grupo lógico simplifica considerablemente la creación de este filtro, como se muestra a continuación:

![](assets/logic-grp-example.png)


### Generar un filtro de grupo lógico {#logic_group_filter}

Al igual que otros contenedores, los de [!UICONTROL grupo lógico] se pueden crear de varias formas dentro del [!UICONTROL Generador de segmentos]. A continuación se indica una de las mejores formas de anidar contenedores de [!UICONTROL grupo lógico]:

1. Arrastre dimensiones, eventos o filtros desde los paneles izquierdos.
1. Cambie el contenedor superior por un contenedor de [!UICONTROL visitante].
1. Cambie el operador [!UICONTROL AND] u [!UICONTROL OR] insertado de forma predeterminada al operador THEN.
1. Seleccione los contenedores de [!UICONTROL visita individual] (la dimensión, evento o elemento) y haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Agregar contenedor de selección]**.
1. Haga clic en el icono de contenedor y seleccione **[!UICONTROL grupo lógico]**.  ![](assets/logic_group_checkpoints.png)
1. Ahora puede establecer la [!UICONTROL visita individual] dentro del contenedor de [!UICONTROL grupo lógico] independientemente de la jerarquía.

### Puntos de comprobación de grupo lógico en cualquier orden {#any_order}

Usar el [!UICONTROL grupo lógico] le permite satisfacer las condiciones dentro de ese grupo que residen fuera de la secuencia. Esto le permite generar filtros en los que una [!UICONTROL Visita] o [!UICONTROL Visita] El contenedor de ocurre independientemente de la jerarquía normal.

**Ejemplo**: Los visitantes que visitaron la página A y luego visitaron la página B y C en cualquier orden.

**Crear este filtro**

Las páginas B y C están anidadas en un contenedor de [!UICONTROL grupo lógico] dentro del contenedor exterior de [!UICONTROL visitante]. Al contenedor de [!UICONTROL visita individual] para A lo sigue luego el contenedor de [!UICONTROL grupo lógico] con B y C identificadas usando el operador [!UICONTROL AND]. Como está en el [!UICONTROL grupo lógico], la secuencia no se define y visitar la página B o C hace que el argumento sea verdadero.

![](assets/logic_group_any_order2.png)

**Otro ejemplo**: Los visitantes que visitaron la página B o la página C y luego visitaron la página A.

![](assets/logic_group_any_order3.png)

El filtro debe coincidir al menos con uno de los puntos de comprobación del grupo lógico (B o C). Además, las condiciones de grupo lógico pueden cumplirse en la misma visita o en varias visitas individuales. &#x200B;

### Primera coincidencia del grupo lógico {#first_match}

Usar el [!UICONTROL grupo lógico] le permite satisfacer las condiciones dentro de ese grupo que residen fuera de la secuencia. En este filtro de primera coincidencia sin ordenar, la variable [!UICONTROL Grupo de lógica] Las reglas de se identifican primero como una vista de página de la página B o C y, a continuación, la vista requerida de la página A.

**Ejemplo**: Los visitantes que visitaron la página B o la página C y luego visitaron la página A.

**Crear este filtro**

Las dimensiones de la página B y la página C se agrupan dentro de un contenedor de [!UICONTROL grupo lógico] con el operador [!UICONTROL OR] seleccionado, luego el contenedor de [!UICONTROL visita individual] que identifica una vista de página de la página A como valor.

![](assets/logic_group_1st_match.png)

### Grupo lógico excluir AND {#lg_exclude_and}

Generar filtros utilizando [!UICONTROL Grupo de lógica] donde se agregan múltiples vistas de página para definir qué páginas fue necesario visitar mientras que otras páginas se omitieron específicamente. ****

**Ejemplo**: El visitante que visitó la página A y luego no visitó expresamente la página B ni C, pero sí la página D.

**Crear este filtro**

Cree este filtro arrastrando Dimension, eventos y filtros pregenerados desde los paneles izquierdos. Consulte la sección Creación de un filtro de grupo lógico.

Después de anidar los valores dentro del [!UICONTROL grupo lógico], haga clic en el botón **[!UICONTROL Excluir]** dentro del contenedor de [!UICONTROL grupo lógico].

![](assets/logic_exclude_and.png)

### Grupo lógico excluir OR {#lg_exclude_or}

Generar filtros utilizando [!UICONTROL Grupo de lógica] donde se agregan múltiples vistas de página para definir qué páginas fue necesario visitar mientras que otras páginas se omitieron específicamente.

**Ejemplo**: Los visitantes que visitaron la página A pero que no visitaron ni la página B ni C antes de la página A.

**Crear este filtro**

Las páginas B y C iniciales se identifican en un contenedor de [!UICONTROL grupo lógico] que se excluye y luego son seguidas por una visita a la página A por parte del visitante.

Cree este filtro arrastrando Dimension, eventos y segmentos pregenerados desde los paneles izquierdos.

Después de anidar los valores dentro del [!UICONTROL grupo lógico], haga clic en el botón **[!UICONTROL Excluir]** dentro del contenedor de [!UICONTROL grupo lógico].

![](assets/logic_exclude_or.png)

## Generar filtros de tiempo dentro y tiempo después {#time_within_after}

Use los operadores [!UICONTROL Within] y [!UICONTROL After] incorporados en el encabezado de cada contenedor para definir el tiempo, los eventos y recuentos.

![](assets/then_within_operators.png)

Puede limitar las coincidencias a una duración de tiempo especificada usando los contenedores [!UICONTROL En] y [!UICONTROL Después] y especificando la granularidad y el recuento. El operador [!UICONTROL Within] se usa para especificar un límite máximo de tiempo entre dos puntos de comprobación. El operador [!UICONTROL After] se usa para especificar un límite mínimo de tiempo entre dos puntos de comprobación.

>[!NOTE]
>
>Existen diferencias en la evaluación entre elementos con nombres similares, como **Día(s)** o **Día**. Para definiciones basadas en el tiempo de En y Después, utilice las opciones que aparecen primero en la ventana emergente:
>
>![imagen](https://git.corp.adobe.com/storage/user/5902/files/70a875e2-0ef9-4459-8648-77c60081d64d)
>
>Para definiciones basadas en dimensiones de En y Después, utilice las opciones del submenú *Otros Dimension*:
>
>![imagen](https://git.corp.adobe.com/storage/user/5902/files/b808eeb0-5e3f-499b-8096-c7eb0d51c57a)

### Operadores After y Within {#after_within}

La duración está especificada por una sola letra en mayúsculas que representa la granularidad seguida de un número que representa el recuento de repetición de la granularidad.

**[!UICONTROL En]** incluye el punto final (menor o igual que).

**[!UICONTROL Después]** no incluye el punto final (mayor que).

| Operadores | Descripción |
|--- |--- |
| AFTER | El operador After se usa para especificar un límite mínimo de tiempo entre dos puntos de comprobación. Al establecer los valores de After, el límite de tiempo empezará cuando se aplique el filtro. Por ejemplo, si el operador After se configura en un contenedor para identificar a los visitantes que visitan la página A pero no regresan a la página B hasta después de un día, ese día empezará cuando el visitante abandone la página A. Para que el visitante se incluya en el filtro, debe transcurrir un mínimo de 1440 minutos (un día) desde que se salió de la página A hasta que se visitó la página B. |
| WITHIN | El operador Within se usa para especificar un límite máximo de tiempo entre dos puntos de comprobación. Por ejemplo, si el operador Within se configura en un contenedor para identificar a los visitantes que visitan la página A y luego regresan para visitar la página B en un día, ese día empezará cuando el visitante abandone la página A. Para que se incluya en el filtro, el visitante tendrá un tiempo máximo de un día antes de abrir la página B. Para que el visitante se incluya en el filtro, la visita a la página B debe realizarse en un máximo de 1440 minutos (un día) desde que se salió de la página A hasta que se visitó la página B. |
| AFTER/WITHIN | Al usar los operadores After y Within, es importante entender que ambos operadores empezarán y finalizarán en paralelo, no en secuencia.   Por ejemplo, si genera un filtro con el contenedor establecido en:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>A continuación, las condiciones para identificar a los visitantes en el filtro solo se cumplen entre 1 y 2 semanas. Ambas condiciones se aplican desde el momento de la primera visita individual a la página. |

### Usar el operador After {#after}

* Después de tiempo le permite rastrear por año, mes, día, hora y minuto para hacer coincidir visitas.
* Después de tiempo solo puede aplicarse a un contenedor de [!UICONTROL visita individual] porque es el único nivel para el cual se define una granularidad tan fina.

**Ejemplo**: Los visitantes que visitaron la página A y luego visitaron la página B solo después de 2 semanas.****

![](assets/time_between_after_operator.png)

**Creación del segmento**: Este filtro se crea añadiendo una [!UICONTROL Visitante] contenedor con dos [!UICONTROL Visita] contenedores. Luego puede establecer el operador [!UICONTROL THEN] y abrir la lista desplegable del operador [!UICONTROL AFTER] y establecer el número de semanas.

![](assets/after_operator.png)

**Coincidencias**

En el caso de &quot;Después de 2 semanas&quot;, si una visita individual a una página A se produce el 1 de junio de 2019 a las 00:01 horas, entonces la siguiente visita individual a la página B coincidirá siempre y cuando se produzca antes del 15 de junio de 2019 a las 00:01 horas (14 días después).

| Visita individual A | Visita individual B | Coincidencia |
|--- |--- |--- |
| Visita individual **A**: 1 de junio de 2019, 00:01 | Visita individual **B**: 15 de junio de 2019, 00:01 | **Coincide**: Esta restricción temporal coincide porque es después del 1 de junio de 2019 (dos semanas). |
| Visita individual **A**: 1 de junio de 2019, 00:01 | Visita individual **B**: Visita individual B del 8 de junio de 2019 a las 00:01 Visita individual B del 15 de junio de 2019 a las 00:01 | **No coincide**: La primera visita individual a la página B no coincide porque está en conflicto con la restricción que requiere que sea después de dos semanas. |

### Usar el operador Within {#within}

* [!UICONTROL En] le permite rastrear por año, mes, día, hora y minuto para hacer coincidir visitas.
* [!UICONTROL En] solo puede aplicarse a un contenedor de [!UICONTROL visita individual] porque es el único nivel para el cual se define una granularidad tan fina.

>[!TIP]
>
>En una cláusula “En”, entre instrucciones THEN, se puede agregar, por ejemplo, “En 1 instancia de palabra clave de búsqueda”, “En 1 instancia de eVar 47”. Esto restringe el filtro a una instancia de una dimensión.

**Ejemplo**: Los visitantes que visitaron la página A y luego la página B en un plazo de 5 minutos.

![](assets/time_between_within_operator.png)

**Creación del filtro**: Este filtro se crea añadiendo una [!UICONTROL Visitante] contenedor y, a continuación, arrastre con dos [!UICONTROL Visita] contenedores. A continuación, puede establecer el operador [!UICONTROL THEN] y abrir la lista desplegable del operador [!UICONTROL AFTER] para establecer el intervalo: visitas individuales, vistas de página, visitas, minutos, horas, días, semanas, meses, trimestres o años.

![](assets/within_operator.png)

**Coincidencias**

Las coincidencias deben producirse dentro del límite temporal. Para la expresión, si una visita individual a la página A se produce a las 00:01 horas, una visita posterior a la página B producirá una coincidencia siempre que se produzca a las 00:06 o antes (cinco minutos después, incluido el mismo minuto). Las visitas individuales dentro del mismo minuto también serán una coincidencia.

### Los operadores Within y After {#within_after}

Uso [!UICONTROL En] y [!UICONTROL Después] para proporcionar un punto final máximo y mínimo en ambos extremos de un filtro.

**Ejemplos**: Los visitantes que visitaron la página A y luego la página B después de 2 semanas pero dentro del plazo de un mes.

![](assets/time_between_using_both_operators.png)

**Creación del segmento**: Cree el filtro secuenciando dos [!UICONTROL Visita] contenedores dentro de un [!UICONTROL Visitante] contenedor. Luego establezca los operadores [!UICONTROL After] y [!UICONTROL Within].

![](assets/within_after_together.png)

**Coincidencias**

Los visitantes que visiten la página A el 1 de junio de 2019 y vuelvan después del 15 de junio de 2019 a las 00:01 horas, pero *antes* El 1 de julio de 2019 se incluyen en el filtro. Compare con la sección Tiempo entre exclusiones.

El [!UICONTROL Después] y [!UICONTROL En] los operadores se pueden utilizar juntos para definir un filtro secuencial.

![](assets/time_between_within_after.png)

Este ejemplo muestra una segunda visita a la página B después de dos semanas pero dentro del plazo de 1 mes.
