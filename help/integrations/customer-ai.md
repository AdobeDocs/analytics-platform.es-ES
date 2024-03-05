---
description: Descubra cómo los datos de la inteligencia artificial aplicada al cliente de Adobe Experience Platform se integran con el espacio de trabajo de Customer Journey Analytics.
title: Integración de datos de inteligencia artificial aplicada al cliente con Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Experience Platform Integration
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: ht
source-wordcount: '968'
ht-degree: 100%

---

# Integración de datos de inteligencia artificial aplicada al cliente con Adobe Customer Journey Analytics

{{release-limited-testing}}

La [inteligencia artificial aplicada al cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=es), como parte de los servicios inteligentes de Adobe Experience Platform, proporciona a los expertos en marketing la capacidad de generar predicciones sobre clientes a nivel individual.

Con la ayuda de factores influyentes, la inteligencia artificial aplicada al cliente puede indicarle qué es lo más probable que haga un cliente y por qué. Además, los expertos en marketing pueden beneficiarse de las predicciones y perspectivas de la inteligencia artificial aplicada al cliente para personalizar las experiencias de los clientes y ofrecerles las ofertas y los mensajes más adecuados.

La inteligencia artificial aplicada al cliente se basa en datos de comportamiento individuales y en datos de perfil para la puntuación de tendencia. La inteligencia artificial aplicada al cliente es flexible, ya que puede incorporar varias fuentes de datos, como Adobe Analytics, Adobe Audience Manager, datos de evento de experiencias del consumidor y datos de evento de experiencias. Si utiliza el conector de la fuente Experience Platform para introducir datos de Adobe Audience Manager y Adobe Analytics, el modelo recoge automáticamente los tipos de evento estándar para entrenar y puntuar el modelo. Si introduce su propio conjunto de datos de evento de experiencias sin tipos de evento estándar, los campos relevantes deberán asignarse como eventos personalizados o atributos de perfil si desea usarlos en el modelo. Se puede llevar a cabo en el paso Configuración de la inteligencia artificial aplicada al cliente en Experience Platform.

La inteligencia artificial aplicada al cliente se puede integrar con Customer Journey Analytics en el sentido de que los conjuntos de datos habilitados para la inteligencia artificial aplicada al cliente se pueden aprovechar en las vistas de datos y los sistemas de informes de Customer Journey Analytics. Puede realizar lo siguiente:

* **Rastrear puntuaciones de tendencia para un segmento de usuarios a lo largo del tiempo**. 
   * Caso de uso: comprender la probabilidad de conversión de los clientes de un segmento específico.
   * Ejemplo: un experto en marketing de una cadena hotelera quiere comprender la probabilidad de que un cliente de un hotel compre una entrada para un espectáculo en el recinto de conciertos del hotel.
* **Analizar qué eventos o atributos de éxito están asociados con las puntuaciones de tendencia**.
   * Ejemplo de caso de uso: comprender los atributos o los eventos de éxito asociados con las puntuaciones de tendencia.
   * Ejemplo: un experto en marketing de una cadena hotelera quiere comprender cómo las compras de entradas para espectáculos en el recinto de conciertos de un hotel se asocian con las puntuaciones de tendencia.
* **Seguir el flujo de entrada de la tendencia de los clientes sobre diferentes ejecuciones de puntuación**. 
   * Ejemplo de caso de uso: entender a las personas que inicialmente eran usuarios de baja tendencia y, con el tiempo, se convirtieron en usuarios de alta tendencia.
   * Ejemplo: un experto en marketing de una cadena hotelera quiere comprender cuáles clientes de hotel se identificaron inicialmente como clientes con baja tendencia a comprar una entrada para un espectáculo, pero con el tiempo se convirtieron en clientes con una alta tendencia para comprar una entrada para un espectáculo.
* **Observe la distribución de la tendencia**. 
   * Caso de uso: comprender la distribución de las puntuaciones de tendencia para ser más precisos a la hora de definir segmentos.
   * Ejemplo: un minorista desea hacer una promoción específica de 50 dólares de descuento en un producto. Es posible que solo quiera hacer una promoción muy limitada debido al presupuesto, etc. Analiza los datos y decide segmentar solo a los clientes principales con un 80 % o más.
* **Observar la tendencia de realizar una acción para una cohorte en particular a lo largo del tiempo**. 
   * Caso de uso: rastrear una cohorte específica a lo largo del tiempo. 
   * Ejemplo: un experto en marketing puede rastrear su nivel bronce frente a su nivel plata, o su nivel plata frente a su nivel oro a lo largo del tiempo. Puede ver la tendencia de cada cohorte a reservar el hotel a lo largo del tiempo.

Para integrar realmente los datos de inteligencia artificial aplicada al cliente con Customer Journey Analytics, siga estos pasos:

>[!NOTE]
>
>Algunos de los pasos se realizan en Adobe Experience Platform antes de trabajar con la salida en Customer Journey Analytics.


## Paso 1: Configurar una instancia de inteligencia artificial aplicada al cliente

Una vez que haya preparado los datos y haya establecido todas sus credenciales y esquemas, comience por seguir la guía de [Configuración de una instancia de inteligencia artificial aplicada al cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=es) en Adobe Experience Platform.

## Paso 2: Configurar una conexión de Customer Journey Analytics a los conjuntos de datos de inteligencia artificial aplicada al cliente

En Customer Journey Analytics, ahora puede [crear una o más conexiones](/help/connections/create-connection.md) con conjuntos de datos de Experience Platform instrumentados para la inteligencia artificial aplicada al cliente. Cada predicción, como «Probabilidad de actualizar la cuenta», equivale a un conjunto de datos. Estos conjuntos de datos aparecen con el prefijo «Puntuaciones de inteligencia artificial aplicada al cliente en formato EE - nombre_de_la_aplicación».

>[!IMPORTANT]
>
>Cada instancia de inteligencia artificial aplicada al cliente tiene dos conjuntos de datos de salida si se activa la opción para habilitar puntuaciones para Customer Journey Analytics durante la configuración en el paso 1. Aparece un conjunto de datos de salida en formato XDM de perfil y uno en formato XDM de evento de experiencia.

![Puntuaciones de CAI](assets/cai-scores.png)

![Crear conexión](assets/create-conn.png)

A continuación se muestra un ejemplo de esquema de XDM que Customer Journey Analytics incorporaría como parte de un conjunto de datos existente o nuevo:

![Esquema de CAI](assets/cai-schema.png)

(Tenga en cuenta que el ejemplo es un conjunto de datos de perfil; el mismo conjunto de objetos de esquema formaría parte de un conjunto de datos de evento de Experience que Customer Journey Analytics obtendría. El conjunto de datos de evento de experiencia incluiría marcas de tiempo como fecha de la puntuación). Todos los clientes puntuados en este modelo tendrían una puntuación, una scoreDate, etc. asociadas a ellos.

## Paso 3: Crear vistas de datos en función de estas conexiones

En Customer Journey Analytics, ahora puede proceder a [crear vistas de datos](/help/data-views/create-dataview.md) con las dimensiones (como puntuación, fecha de puntuación, probabilidad, etc.) y las métricas que se han incluido como parte de la conexión que ha establecido.

![Crear ventana de vista de datos](assets/create-dataview.png)

## Paso 4: Informar sobre puntuaciones de CAI en e Workspace

En Customer Journey Analytics Workspace, ahora puede crear un nuevo proyecto y recibir visualizaciones.

### Puntuaciones de tendencia

A continuación, se muestra un ejemplo de un proyecto de Workspace con datos de CAI que ofrece puntuaciones de tendencia de un segmento de usuarios a lo largo del tiempo, en un gráfico de barras apiladas:

![Bloques de puntuación](assets/workspace-scores.png)

### Tabla con códigos de motivo

Esta es una tabla que muestra los códigos de motivo por los que un segmento tiene una tendencia alta o baja.

![Códigos de motivo](assets/reason-codes.png)

### Flujo de entrada para la tendencia del cliente

Este diagrama de flujo muestra el flujo de entrada de la tendencia del cliente en distintas ejecuciones de puntuación:

![Flujo de entrada](assets/flow.png)

### Distribución de las puntuaciones de tendencia

Este gráfico de barras muestra la distribución de las puntuaciones de tendencia:

![Distribución](assets/distribution.png)

### Superposiciones de tendencias

Este diagrama de Venn muestra las superposiciones de tendencias en diferentes ejecuciones de puntuación:

![Superposiciones de tendencias](assets/venn.png)
