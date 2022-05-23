---
title: Modelos de atribución y ventanas retroactivas
description: Cómo los diferentes tipos de atribución dividen el crédito entre los valores de dimensión.
Feature: Attribution
exl-id: 2ab6add7-9dc8-419d-96f7-e0c12e6b4761
source-git-commit: d165b3aaca9f99bb23bcbfbcfbca9d2e96b3cfcb
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 100%

---

# Atribución modelos de atribución y ventanas retrospectivas

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). [Más información...](/help/getting-started/cja-aa.md)

El concepto de atribución en Customer Journey Analytics requiere dos componentes:

* **Modelo de atribución:** El modelo describe la distribución de conversiones a las visitas en un grupo. Por ejemplo, primer contacto o último contacto.
* **Ventana de retrospectiva de atribución:** Describe qué agrupamientos de visitas se tienen en cuenta para cada modelo. Por ejemplo: visita o visitante.

## Modelos de atribución

| Icono de la interfaz de usuario | Modelo de atribución | Definición | Uso |
| --- | --- | --- | --- |
| ![Último contacto](assets/last_touch1.png) | Último contacto | Otorga un 100% de crédito al punto de contacto que se produce más recientemente antes de la conversión. | El modelo de atribución más básico y común. Se utiliza con frecuencia para conversiones con un breve ciclo de consideración. Último toque lo utilizan comúnmente equipos que gestionan el marketing de búsqueda o que analizan palabras clave de búsqueda interna. |
| ![Primer contacto](assets/first_touch.png) | Primer contacto | Otorga un 100% de crédito al punto de contacto que se ve por primera vez en la ventana retrospectiva de atribución. | Otro modelo de atribución común que resulta útil para analizar canales de marketing destinados a impulsar la diferenciación de la marca o la adquisición de clientes. Lo suelen usar equipos de marketing de Visualización o Social, pero también es una herramienta excelente para evaluar la efectividad de recomendaciones de productos in situ. |
| ![Mismo contacto](assets/same_touch.png) | Mismo contacto | Otorga un 100% de crédito a la visita individual donde se produjo la conversión. Si un punto de contacto no se produce en la misma visita que una conversión, se agrupa en “Ninguno”. | Es un modelo útil al evaluar el contenido o la experiencia del usuario que se presentó inmediatamente en el momento de la conversión. Los equipos de producto o diseño a menudo utilizan este modelo para tener acceso a la efectividad de una página en la que tiene lugar la conversión. |
| ![Lineal](assets/linear.png) | Lineal | Otorga el mismo crédito a cada punto de contacto que se visualice y que conduzca a una conversión. | Este modelo es útil para conversiones con ciclos de consideración más largos o experiencias del usuario que necesitan interacción de clientes más frecuente. La suelen utilizar equipos que miden la efectividad de notificaciones de aplicaciones móviles o con productos por suscripción. |
| ![Forma de U](assets/u_shaped.png) | Forma de U | Otorga un 40% de crédito a la primera interacción, un 40% de crédito a la última interacción y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 50% de crédito a ambos. | Un gran modelo para aquellos que valoran las interacciones que introdujeron o cerraron una conversión, pero que aún desean reconocer las interacciones de asistencia. La atribución de Forma de U suele ser utilizada por equipos que adoptan un enfoque más equilibrado y desean dar más crédito a canales que encontraron o cerraron una conversión. |
| ![Forma de J](assets/j_shaped.png) | Forma de J | Otorga un 60% de crédito a la última interacción, un 20% de crédito a la primera interacción y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 75% de crédito a la última interacción y un 25% de crédito a la primera. | Este modelo es ideal para aquellos que dan prioridad a los buscadores y cerradores, pero que quieren centrarse en cerrar interacciones. La atribución de Forma de J la suelen utilizar equipos que adoptan un enfoque más equilibrado y desean dar más crédito a canales que cerraron una conversión. |
| ![Forma J inversa](assets/inverse_j.png) | J inversa | Otorga un 60% de crédito al primer contacto, un 20% al último contacto y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 75% de crédito a la primera interacción y un 25% de crédito a la última. | Este modelo es ideal para aquellos que dan prioridad a los buscadores y cerradores, pero que desean centrarse en encontrar interacciones. La atribución de J inversa la suelen utilizar equipos que adoptan un enfoque más balanceado y desean dar más crédito a canales que iniciaron una conversión. |
| ![Personalizado](assets/custom.png) | Personalizado | Permite especificar el valor que desea dar a los puntos de primer contacto, los puntos de último contacto y los puntos de contacto intermedios. Los valores especificados se normalizan al 100% incluso si los números introducidos no suman 100. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. En el caso de interacciones con dos puntos de contacto, se omite el parámetro central. Los puntos de primer y último contacto se normalizan al 100% y el crédito se asigna en consecuencia. | Este modelo es perfecto para aquellos que quieren un control total sobre su modelo de atribución y tienen necesidades específicas que otros modelos de atribución no satisfacen. |
| ![Deterioro de tiempo](assets/time_decay.png) | Declive temporal | Sigue un declive exponencial con un parámetro de semivida personalizado, con un valor predeterminado de 7 días. El valor de cada canal depende de la cantidad de tiempo que transcurra entre el inicio del punto de contacto y la conversión final. La fórmula utilizada para determinar el crédito es `2^(-t/halflife)`, donde `t` es la cantidad de tiempo entre un punto de contacto y una conversión. A continuación, todos los puntos de contacto se normalizan al 100%. | Ideal para equipos que periódicamente ejecutan campañas audiovisuales o que comercializan eventos con una fecha predeterminada. Cuanto más tardía sea la conversión después de un evento de marketing, menor será el crédito. |
| ![Participación](assets/participation.png) | Participación | Otorga un 100% de crédito a todos los puntos de contacto únicos. El número total de conversiones está incrementado en comparación con otros modelos de atribución. La participación anula la duplicación de los canales vistos varias veces. | Excelente para comprender con qué frecuencia se exponen los clientes a una determinada interacción. Los medios suelen utilizar este modelo para calcular la velocidad de contenido. Los comercios suelen utilizar este modelo para comprender qué partes de sus sitios son esenciales para la conversión. |
| ![Algorítmico](assets/algorithmic.png) | [Algorítmico](/help/analysis-workspace/attribution/algorithmic.md) | Utiliza técnicas estadísticas para determinar de manera dinámica la asignación óptima de crédito para la métrica seleccionada. | Es útil para evitar conjeturas o tareas de ensayo y error al elegir el modelo de atribución adecuado para su negocio. |

## Ventanas retrospectivas

Una ventana retrospectiva es la cantidad de tiempo que una conversión debe devolverse en el tiempo para incluir los puntos de contacto. Los modelos de atribución que dan más crédito a las primeras interacciones ven diferencias mayores al tener ventanas retrospectivas distintas.

* **Ventana retrospectiva de visita:** Revisa hasta el principio de una visita en la que se produjo una conversión. Las ventanas retrospectivas de visitas son estrechas, ya que no miran más allá de la visita. Las ventanas retrospectivas de visita respetan la definición de visita modificada en las vistas de datos.

* **Ventana retrospectiva de visitantes:** Busca todas las visitas hasta el primer día del mes del intervalo de fechas actual. Las ventanas retrospectivas de visitantes son amplias, ya que pueden abarcar muchas visitas. La ventana retrospectiva de visitantes tiene en cuenta todos los valores desde el comienzo del mes del intervalo de fechas del informe. Por ejemplo, si el intervalo de fechas del informe es del 15 de septiembre al 30 de septiembre, el intervalo de fechas de retrospectiva de visitante sería del 1 de septiembre al 30 de septiembre.

* **Ventana retrospectiva personalizada:** Permite expandir la ventana de atribución más allá del intervalo de fechas del sistema de informes hasta un máximo de 90 días. Las ventanas retrospectivas personalizadas se evalúan en cada conversión del periodo del sistema de informes. Por ejemplo, para una conversión que se produce el 20 de febrero, una ventana retrospectiva de 10 días evaluaría todos los puntos de contacto de la dimensión del 10 al 20 de febrero en el modelo de atribución.

## Ejemplo

Consideremos el siguiente ejemplo:

1. El 15 de septiembre, un visitante llega a su sitio a través de un anuncio de búsqueda de pago y luego lo abandona.
2. El 18 de setiembre, el visitante regresa a su sitio a través de un vínculo de medios sociales que obtuvo de un amigo. Agregan varios artículos al carro, pero no compran nada.
3. El 24 de septiembre, su equipo de marketing les enviará un correo electrónico con un cupón para algunos de los artículos del carrito. Aplican el cupón, pero visitan otros sitios para ver si hay otros cupones disponibles. Encontraron otro a través de un anuncio y finalmente hicieron una compra por valor de 50 dólares.

Según la ventana retrospectiva y el modelo de atribución, los canales reciben crédito diferente. Los siguientes son algunos ejemplos importantes:

* Con el **primer contacto** y una **ventana retrospectiva de visita**, la atribución solo se fijará en la tercera visita. Entre el correo electrónico y la visualización, el correo electrónico fue el primero, por lo que el correo electrónico recibe un 100% de crédito por la compra de 50 dólares.
* Con el **primer contacto** y una **ventana retrospectiva de visitantes**, la atribución se fijará en las tres visitas. La búsqueda de pago fue la primera, así que recibe un 100% de crédito por la compra de 50 dólares.
* Con un modelo **lineal** y una **ventana retrospectiva de visita**, el crédito se divide entre el correo electrónico y la visualización. Cada uno de estos canales recibe un crédito de 25 dólares.
* Con un modelo **lineal** y una **ventana retrospectiva de visitante**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Cada canal recibe un crédito de 12,50 dólares por esta compra.
* Con un modelo **Forma de J** y una **ventana retrospectiva de visitante**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización.
   * Se otorga un crédito del 60 % a la visualización, es decir, 30 dólares.
   * El 20 % de crédito se asigna a la búsqueda de pago, 10 dólares en este caso.
   * El 20% restante se divide entre el medio social y el correo electrónico, lo que otorga 5 dólares a cada uno.
* Con un modelo **Declive temporal** y una **ventana retrospectiva de visitante**, el crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Con la semivida de 7 días predeterminada:
   * Diferencia de 0 días entre el punto de contacto de visualización y la conversión. `2^(-0/7) = 1`
   * Diferencia de 0 días entre el punto de contacto del correo electrónico y la conversión. `2^(-0/7) = 1`
   * Diferencia de 6 días entre el punto de contacto social y la conversión. `2^(-6/7) = 0.552`
   * Diferencia de 9 días entre el punto de contacto de búsqueda de pago y la conversión. `2^(-9/7) = 0.41`
   * La normalización de estos valores resulta en lo siguiente:
      * Visualización: 33,8 %, 16,88 dólares
      * Correo electrónico: 33,8 % 16,88 dólares
      * Medio social: 18,6 %, 9,32 dólares
      * Búsqueda de pago: 13,8 %, 6,92 dólares

>[!NOTE]
>
>Otros eventos de conversión, como pedidos o eventos personalizados, también se dividen si el crédito pertenece a más de un canal. Por ejemplo, si dos canales contribuyen a un evento personalizado mediante un modelo de atribución lineal, ambos canales obtienen 0,5 del evento personalizado. Estas fracciones de evento se suman en todas las visitas y luego se redondean al entero más cercano para los informes.
