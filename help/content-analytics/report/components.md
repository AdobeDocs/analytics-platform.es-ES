---
title: Componentes de Content Analytics
description: Obtenga información acerca de los detalles de los componentes específicos de Content Analytics, como dimensiones, métricas (calculadas) y campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 3e9a9042bfe707971c4e37d319a23ab9bdc80075
workflow-type: tm+mt
source-wordcount: 1869
ht-degree: 56%

---


# Componentes de Content Analytics

Content Analytics añade las siguientes categorías de componentes (dimensiones, métricas (calculadas), campos derivados) a los componentes ya disponibles en Customer Journey Analytics:

* [Metadatos de la experiencia](#experience-metadata)
* [Atributos de la experiencia](#experience-attributes)
* [Eventos de la experiencia](#experience-events)
* [Metadatos del recurso](#asset-metadata)
* [Atributos del recurso](#asset-attributes)
* [Eventos del recurso](#asset-events)
* [Medios de pago](#paid-media)
* [Métricas calculadas](#calculated-metrics)

En las tablas siguientes, ![Generado por IA](/help/assets/icons/AI.svg) indica un par atributo/valor generado por IA/ML.

## Metadatos de la experiencia

| Título | Descripción | Tipo |
|---|---|---|
| ID SOURCE | Para Content Analytics, el valor es `ContentAnalytics`. | Dimensión |
| Canal | Canal para la experiencia. El valor es `Web`, `Mobile` o `Paid Media`. | Dimensión |
| ID de experiencia de contenido | ID único de la experiencia. <br>Para **web**: URL de la página web. <br/>Para **web granular**: un hash calculado del lado del cliente basado en la carga útil de contenido (textos, imágenes, ctas) con el prefijo `web-`. <br/>Para **mobile**: un hash calculado del lado del cliente basado en la carga útil de contenido (textos, imágenes, ctas) con el prefijo `mobile-`. | Dimensión |
| Content Experience Source | Para **web**: la dirección URL de la página web.<br/>Para **móvil**: el nombre de pantalla, pasado a través de Experience Platform Mobile SDK. | Dimensión |
| Canal de experiencia (obsoleto) | Canal para la experiencia. El valor es `Web` o `Mobile`. | Dimensión |
| Extras de experiencia | Cualquier otro dato adicional que desee rastrear. Como ID externo o ubicación. | Dimensión |
| URL de miniatura de la experiencia | URL de la miniatura de la experiencia. | Dimensión |
| Profundidad porcentual horizontal de la experiencia | Valor cuantificable de la profundidad porcentual horizontal de la experiencia. | Campo derivado de Dimensión<br/> |
| Profundidad porcentual vertical de la experiencia | Valor cuantificable de la profundidad porcentual vertical de la experiencia. | Campo derivado de Dimensión<br/> |

{style="table-layout:fixed"}



## Atributos de la experiencia

| Título | Descripción | Tipo |
|---|---|---|
| Atributos de la experiencia | ![Generado por IA](/help/assets/icons/AI.svg) Lista completa de todos los nombres y valores de atributos de experiencia | Campo derivado de Dimensión<br> |
| Puntuación de legibilidad de la experiencia | ![Generado por IA](/help/assets/icons/AI.svg) Puntuación de legibilidad para la experiencia | Dimensión |
| Palabras clave de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Palabras clave para la experiencia. | Campo derivado de Dimensión<br> |
| Estrategias de persuasión de la experiencia | ![Generado por IA](/help/assets/icons/AI.svg)  Estrategias de persuasión presentes en la experiencia dada. Los valores posibles son: Identidad social, Prueba social, Autoridad, Concreción, Pie en la puerta, Superación de la reacción, Reciprocidad, Anclaje y comparación, Impacto social, Escasez y Antropomorfismo. | Campo derivado de Dimensión<br/> |
| Narrativas de la experiencia | ![Generado por IA](/help/assets/icons/AI.svg) Narrativas que la experiencia está generando en función de la relevancia desde el punto de vista de un experto en marketing. | Campo derivado de Dimensión<br/> |
| Tonos de la experiencia | ![Generado por IA](/help/assets/icons/AI.svg) tonos que la experiencia está creando según la relevancia desde el punto de vista de un experto en marketing | Campo derivado de Dimensión<br/> |
| Emociones de marketing de la experiencia | ![Generado por IA](/help/assets/icons/AI.svg) La emoción invocada en el lector al leer el texto utilizado como parte de la experiencia: urgencia, exclusividad, estímulo, desafío, curiosidad, logro, confianza, simplicidad y fascinación. | Campo derivado de Dimensión<br/> |
| Recuento de emojis de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de emojis de la experiencia. | Métrica |
| Recuento de hashtags de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de hashtags de la experiencia. | Métrica |
| Recuento de frases de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de frases de la experiencia. | Métrica |
| Proporción de palabras de detención de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de palabras de detención de la experiencia. | Métrica |
| Recuento de citas de texto de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de comillas de texto de la experiencia. | Métrica |
| Recuento de palabras de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de palabras de la experiencia. | Métrica |
| Recuento de palabras por frase de la experiencia | ![Generado con IA](/help/assets/icons/AI.svg) Número de palabras por frase de la experiencia. | Métrica |

{style="table-layout:fixed"}


## Eventos de la experiencia

| Título | Descripción | Tipo |
|---|---|---|
| Vistas de la experiencia | Medida cuantificable del número de vistas de la experiencia. | Métrica |
| Clics de la experiencia | Medida cuantificable del número de clics de la experiencia. | Métrica |

{style="table-layout:fixed"}


## Metadatos del recurso

| Título | Descripción | Tipo |
|---|---|---|
| ID del recurso | Identificador único del recurso. El binario de recursos determina la exclusividad. Si el binario del recurso cambia, el ID sí cambia. El ID único puede ser la dirección URL, pero también puede ser un hash creado. | Dimensión |
| Origen de recursos | | Dimensión |
| Ruta HTML del recurso | Ruta de HTML concatenada para el recurso. | Dimensión |
| URL de vínculo del recurso | Anclaje de página más cercano del recurso. | Dimensión |
| Anchura de visualización del recurso | Anchura de visualización del recurso de contenido. | Dimensión |
| Altura de visualización del recurso | Altura de visualización del recurso de contenido. | Dimensión |
| Resto absoluto de recurso | Resto absoluto del recurso de contenido. | Dimensión |
| Máximo absoluto del recurso | Máximo absoluto del recurso de contenido. | Dimensión |
| Extras de recursos | Cualquier otro dato adicional que desee rastrear. Como ID externo o ubicación. | Dimensión |

{style="table-layout:fixed"}


## Atributos del recurso

| Título | Descripción | Tipo |
|---|---|---|
| Atributos del recurso | ![IA generada](/help/assets/icons/AI.svg) Lista completa de todos los nombres y valores de atributos del recurso | Dimensión<br>Campo derivado |
| Orientación del recurso | ![IA generada](/help/assets/icons/AI.svg) Orientación del recurso. | Dimensión<br/>Campo derivado |
| Tono general del recurso | ![IA generada](/help/assets/icons/AI.svg) Tono general del recurso. | Dimensión<br/>Campo derivado |
| Colores de primer plano de recursos | ![IA generada](/help/assets/icons/AI.svg) Colores de primer plano del recurso. | Dimensión<br/>Campo derivado |
| Colores de fondo de recursos | ![IA generada](/help/assets/icons/AI.svg) Colores de fondo del recurso. | Dimensión<br/>Campo derivado |
| Etiquetas del recurso | ![IA generada](/help/assets/icons/AI.svg) Etiquetas para el recurso. | Dimensión<br/>Campo derivado |
| Escenas del recurso | ![IA generada](/help/assets/icons/AI.svg) Escenas para el recurso. | Dimensión<br/>Campo derivado |
| Objetos del recurso | ![IA generada](/help/assets/icons/AI.svg) Objetos del recurso. | Dimensión<br/>Campo derivado |
| Estilos de fotografía del recurso | ![IA generada](/help/assets/icons/AI.svg) Estilos fotográficos del recurso. | Dimensión<br/>Campo derivado |
| Tipo de imagen del recurso | ![IA generada](/help/assets/icons/AI.svg) Tipo de imagen del recurso. Los valores posibles son: fotografía, boceto, pintura, dibujos_animados_digitales, infografía, diseño_gráfico, collage y captura_de_pantalla_de_software. | Dimensión<br/>Campo derivado |
| Posiciones de cámara del recurso | ![IA generada](/help/assets/icons/AI.svg) Posiciones de la cámara de recursos. | Dimensión<br/>Campo derivado |
| Proximidades de la cámara de recursos | ![IA generada](/help/assets/icons/AI.svg) Proximidades de la cámara de recursos. | Dimensión<br/>Campo derivado |
| Categorías de personas del recurso | ![IA generada](/help/assets/icons/AI.svg) Categorías de personas del recurso. Los valores posibles son: persona, hombre, mujer, grupo social, multitud, personas, niño, niña y chaval. | Dimensión<br/>Campo derivado |
| Densidad de contenido visual del recurso | ![IA generada](/help/assets/icons/AI.svg) Densidad de contenido visual del recurso. Los valores posibles son: bajo, medio o alto. Una baja densidad de contenido implica una pequeña cantidad de información presente por unidad de área de la imagen. | Dimensión |
| Dispersión de la atención visual del recurso | ![IA generada](/help/assets/icons/AI.svg) Dispersión de la atención visual del recurso. Los valores posibles son: bajo, medio o alto. La dispersión de la atención se refiere al grado en que la atención de un espectador se divide entre diferentes partes de una imagen. | Dimensión<br/>Campo derivado |
| Condiciones de iluminación del recurso | ![IA generada](/help/assets/icons/AI.svg) Condición de iluminación del recurso. Los valores posibles son: hora dorada, hora azul, mediodía, nublado, noche, perfil alto, perfil bajo, luz diurna, incandescente, fluorescente, colorido y estudio. | Dimensión<br/>Campo derivado |
| Configuración de cámara del recurso | ![IA generada](/help/assets/icons/AI.svg) Configuración de cámara de recursos. Los valores posibles son los siguientes: velocidad del obturador rápida, exposición prolongada. desenfoque Bokeh, desenfoque de movimiento, desenfoque por inclinación, flash, gran angular, blanco y negro, surrealista, doble exposición, macro y modo normal. | Dimensión<br/>Campo derivado |

{style="table-layout:fixed"}


## Eventos del recurso

| Título | Descripción | Tipo |
|---|---|---|
| Vistas del recurso | Medición cuantificable del número de vistas del recurso. | Métrica |
| Clics en recursos | Medición cuantificable del número de clics del recurso. | Métrica |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## Medios de pago

Estos componentes se agregan a una vista de datos cuando el canal **Medios de pago** está habilitado a través de un conector de origen de [Adobe Experience Platform Medios de pago](https://experienceleague.adobe.com/es/docs/experience-platform/sources/home) (por ejemplo, Meta Ads o Google Ads). Permiten informar sobre entidades de medios de pago, contenido creativo y gasto junto con el contenido web y móvil.

Los **atributos de activos** y los **atributos de experiencia** generados por IA que se han descrito anteriormente también están disponibles para los creativos de medios de pago; la misma característica se ejecuta en los canales web, móvil y de medios de pago.

### Dimensiones de medios de pago

| Título | Descripción | Tipo |
|---|---|---|
| Red de anuncios | La plataforma de publicidad desde la que se ingirieron los datos de medios de pago. | Dimensión |
| Nombre de la cuenta | Nombre de la cuenta de publicidad. | Dimensión |
| Nombre de la campaña | Nombre de la campaña de medios de pago. | Dimensión |
| Nombre del grupo de publicidad | Nombre del grupo de anuncios (conjunto de anuncios de Meta / grupo de anuncios de Google). | Dimensión |
| Nombre de publicidad | Nombre del anuncio individual. | Dimensión |
| Nombre de la experiencia | Nombre de la experiencia publicitaria (composición creativa). | Dimensión |
| Nombre del recurso | Nombre del recurso creativo. | Dimensión |
| Estado de la campaña | Estado de la campaña. | Dimensión |
| Estado del grupo de publicidad | Estado del grupo de publicidad. | Dimensión |
| Estado de la publicidad | Estado del anuncio. | Dimensión |
| Estado de servicio | Estado detallado del servicio que indica si la entidad está realizando las entregas actualmente. | Dimensión |
| Divisa de cuenta | Moneda de la cuenta de publicidad. | Dimensión |
| Zona horaria de cuenta | Zona horaria de la cuenta de publicidad. | Dimensión |
| Tipo de cuenta | Tipo de cuenta de publicidad. | Dimensión |
| Nombre de empresa de cuenta | Nombre de la empresa asociada a la cuenta de publicidad. | Dimensión |
| Tipo de campaña | Tipo de canal principal de la campaña. | Dimensión |
| Objetivo de campaña | Objetivo o meta de la campaña. | Dimensión |
| Estrategia de oferta de campaña | Estrategia de oferta para la campaña. | Dimensión |
| Tipo de presupuesto de campaña | Tipo de asignación presupuestaria de la campaña. | Dimensión |
| Presupuesto diario de campaña | Importe de presupuesto diario, en la divisa de la cuenta del anuncio. | Dimensión |
| Presupuesto de duración de campaña | Importe del presupuesto de duración, en la divisa de la cuenta de publicidad. | Dimensión |
| Hora de inicio de campaña | Cuando comenzó la campaña. | Dimensión |
| Hora de finalización de campaña | Cuando terminó la campaña. | Dimensión |
| Tipo de grupo de publicidad | Tipo del grupo de publicidad. | Dimensión |
| Estrategia de oferta de grupo de anuncios | Estrategia de oferta para el grupo de anuncios. | Dimensión |
| Objetivo de optimización del grupo de anuncios | Objetivo de optimización para el grupo de anuncios. | Dimensión |
| Hora de inicio del grupo de anuncios | Cuando comenzó el grupo de publicidad. | Dimensión |
| Hora de finalización del grupo de anuncios | Cuando finalizó el grupo de publicidad. | Dimensión |
| Tipo de anuncio | Tipo/formato del anuncio. | Dimensión |
| Estado de revisión de anuncio | Estado de revisión/aprobación del anuncio. | Dimensión |
| Tipo de Creative de anuncio | Tipo de elemento creativo utilizado por el anuncio. | Dimensión |
| Título del anuncio | Titular/título del creativo de publicidad. | Dimensión |
| Ad Call to action | Call-to-action del creativo de publicidad. | Dimensión |
| URL de destino del anuncio | URL de destino/aterrizaje del anuncio. | Dimensión |
| URL mostrada de anuncio | Mostrar la URL mostrada en el anuncio. | Dimensión |
| Tipo de experiencia | Tipo/formato de la experiencia publicitaria. | Dimensión |
| URL de página de aterrizaje de experiencia | URL de la página de aterrizaje para la experiencia. | Dimensión |
| Experience Call to action | Call-to-action de la experiencia. | Dimensión |
| Tipo de recurso | Tipo de recurso creativo (por ejemplo, imagen o vídeo). | Dimensión |
| Anchura del recurso | Anchura del recurso, en píxeles. | Dimensión |
| Altura del recurso | Altura del recurso, en píxeles. | Dimensión |
| Proporción de aspecto del recurso | Proporción de aspecto del recurso. | Dimensión |
| Orientación del recurso | Orientación del recurso. | Dimensión |
| Tipo de dispositivo | Desglose por tipo de dispositivo para las métricas del informe. | Dimensión |
| Ubicación | Desglose de la ubicación de las métricas recogidas en el informe. | Dimensión |
| Plataforma | Desglose de plataforma para las métricas del informe. | Dimensión |
| País | Desglose por país de las métricas comunicadas. | Dimensión |
| Región | Desglose de región para las métricas del informe. | Dimensión |

{style="table-layout:fixed"}

### Métricas de medios de pago

| Título | Descripción | Tipo |
|---|---|---|
| Impresiones | Número de veces que se ha mostrado el anuncio. | Métrica |
| Clics | Número de clics en el anuncio. | Métrica |
| Gastar | Importe gastado, en la divisa de la cuenta de publicidad. | Métrica |
| Conversiones | Número total de conversiones. | Métrica |
| Valor de conversión | Valor total de las conversiones. | Métrica |
| Alcance | Número de personas únicas que vieron el anuncio. | Métrica |
| Participaciones | Número de interacciones con el anuncio. | Métrica |
| Vistas de videos | Número de visualizaciones de vídeo. | Métrica |
| Finalizaciones de vídeo | Número de vídeos vistos hasta su finalización. | Métrica |
| Reproducciones de vídeo | Número de reproducciones de vídeo. | Métrica |
| Compras | Número de conversiones de compra. | Métrica |
| Añadir al carro | Número de conversiones de complementos al carro de compras. | Métrica |
| Posibles clientes | Número de conversiones de posibles clientes. | Métrica |
| Registros | Número de conversiones de registro. | Métrica |
| Descargas | Número de conversiones de descarga. | Métrica |
| Suscripciones | Número de conversiones de suscripción. | Métrica |
| Vistas de páginas de destino | Número de vistas de página de aterrizaje. | Métrica |
| Conversiones posteriores al clic | Conversiones atribuidas a un clic. | Métrica |
| Conversiones posteriores a la vista | Conversiones atribuidas a una vista. | Métrica |
| Valor de pedido total | Valor total de los pedidos. | Métrica |
| Clics en vínculos | Número de clics en vínculos. | Métrica |
| Clics de salida | Número de clics salientes. | Métrica |
| Instalaciones de aplicación | Número de instalaciones de la aplicación. | Métrica |
| Envíos de posibles clientes | Número de envíos de formularios de posibles clientes. | Métrica |

{style="table-layout:fixed"}

### Métricas calculadas de medios de pago

| Título | Descripción | Tipo |
|---|---|---|
| Tasa de clics | Clics divididos por impresiones. | Métrica calculada |
| Costo por clic | Gasto dividido por clics. | Métrica calculada |
| Costo por kilómetro | Coste por cada mil impresiones. | Métrica calculada |
| Costo por conversión | Gasto dividido por conversiones. | Métrica calculada |
| Retorno de la inversión en publicidad | Valor de conversión dividido por el gasto. | Métrica calculada |
| Frecuencia | Impresiones divididas por alcance. | Métrica calculada |
| Tasa de participación | Interacciones divididas por impresiones. | Métrica calculada |
| Tasa de vídeo finalizado | Finalizaciones de vídeo divididas por reproducciones de vídeo. | Métrica calculada |
| Tasa de conversión | Conversiones divididas por clics. | Métrica calculada |
| Valor de pedido promedio | Valor total del pedido dividido por compras. | Métrica calculada |

{style="table-layout:fixed"}


## Métricas calculadas

| Título | Descripción | Tipo |
|---|---|---|
| Tasa de clics del recurso | Clics del recursos/Vistas del recurso | Métrica calculada |
| Tasa de clics en la experiencia | Clics de la experiencias/Vistas de la experiencia | Métrica calculada |

{style="table-layout:fixed"}

