---
title: Componentes de Content Analytics
description: Obtenga información acerca de los detalles de los componentes específicos de Content Analytics, como dimensiones, métricas (calculadas) y campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1023
ht-degree: 86%

---


# Componentes de Content Analytics

Content Analytics añade las siguientes categorías de componentes (dimensiones, métricas (calculadas), campos derivados) a los componentes ya disponibles en Customer Journey Analytics:

* [Metadatos de la experiencia](#experience-metadata)
* [Atributos de la experiencia](#experience-attributes)
* [Eventos de la experiencia](#experience-events)
* [Metadatos del recurso](#asset-metadata)
* [Atributos del recurso](#asset-attributes)
* [Eventos del recurso](#asset-events)
* [Métricas calculadas](#calculated-metrics)

En las tablas siguientes, ![Generado por IA](/help/assets/icons/AI.svg) indica un par atributo/valor generado por IA/ML.

## Metadatos de la experiencia

| Título | Descripción | Tipo |
|---|---|---|
| ID SOURCE | Para Content Analytics, el valor es `ContentAnalytics`. | Dimensión |
| Canal | Canal para la experiencia. El valor es `Web` o `Mobile`. | Dimensión |
| ID de experiencia de contenido | ID único de la experiencia. <br>Para **web**: URL de la página web. <br/>Para **web granular**: un hash calculado del lado del cliente basado en la carga útil de contenido (textos, imágenes, ctas) con el prefijo `web-`. <br/>Para **mobile**: un hash calculado del lado del cliente basado en la carga útil de contenido (textos, imágenes, ctas) con el prefijo `mobile-`. | Dimensión |
| Content Experience Source | Para **web**: la dirección URL de la página web.<br/>Para **móvil**: el nombre de pantalla, pasado a través de Experience Platform Mobile SDK. | Dimensión |
| Canal de experiencia (obsoleto) | Canal para la experiencia. El valor es `Web` o `Mobile`. | Dimensión |
| Extras de experiencia | Cualquier otro dato adicional que desee rastrear. Como ID externo o ubicación. | Dimensión |
| URL de miniatura de la experiencia | URL de la miniatura de la experiencia. | Dimensión |
| Profundidad porcentual horizontal de la experiencia | Valor cuantificable de la profundidad porcentual horizontal de la experiencia. | Campo derivado de Dimensión<br/> |
| Profundidad porcentual vertical de la experiencia | Valor cuantificable de la profundidad porcentual vertical de la experiencia. | Dimensión<br/>Campo derivado |

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

## Métricas calculadas

| Título | Descripción | Tipo |
|---|---|---|
| Tasa de clics del recurso | Clics del recursos/Vistas del recurso | Métrica calculada |
| Tasa de clics en la experiencia | Clics de la experiencias/Vistas de la experiencia | Métrica calculada |

{style="table-layout:fixed"}

