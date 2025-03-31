---
title: Componentes de Content Analytics
description: Detalles sobre los componentes específicos de Content Analytics, como dimensiones, métricas (calculadas) y campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 0731eadd403ecb428d36492b83351aa0e696b41f
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 22%

---

# Componentes de Content Analytics

{{release-limited-testing}}

Content Analytics agrega las siguientes categorías de componentes (dimensiones, métricas (calculadas), campos derivados) a los componentes ya disponibles en Customer Journey Analytics:

* [Metadatos de experiencia](#experience-metadata)
* [Atributos de la experiencia](#experience-attributes)
* [Eventos de experiencia](#experience-events)
* [Metadatos de recursos](#asset-metadata)
* [Atributos del recurso](#asset-attributes)
* [Eventos de Assets](#asset-events)
* [Métricas calculadas ](#calculated-metrics)

En las tablas siguientes, ![IA generada](/help/assets/icons/AI.svg) indica un par atributo/valor generado por AI/ML.

## Metadatos de experiencia

| Título | Descripción | Tipo |
|---|---|---|
| Canal de la experiencia | Canal para la experiencia. | Dimensión |
| ID de la experiencia | ID único de la experiencia. | Dimensión |
| URL de miniatura de la experiencia | URL de la miniatura de la experiencia. | Dimensión |
| Profundidad porcentual horizontal de la experiencia | Valor cuantificable de la profundidad porcentual horizontal de la experiencia. | Campo derivado de Dimension<br/> |
| Profundidad porcentual vertical de la experiencia | Valor cuantificable de la profundidad porcentual vertical de la experiencia. | Campo derivado de Dimension<br/> |

{style="table-layout:fixed"}



## Atributos de la experiencia

| Título | Descripción | Tipo |
|---|---|---|
| Atributos de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Lista completa de todos los nombres y valores de atributos de experiencia | Campo derivado de Dimension<br> |
| Puntuación de legibilidad de la experiencia | ![AI generada](/help/assets/icons/AI.svg) puntuación de legibilidad para la experiencia | Dimensión |
| Palabras clave de la experiencia | ![IA generó](/help/assets/icons/AI.svg) palabras clave para la experiencia. | Campo derivado de Dimension<br> |
| Estrategias de persuasión de la experiencia | ![AI generó](/help/assets/icons/AI.svg) estrategias de persuasión presentes en la experiencia dada. Los valores posibles son: Identidad social, Prueba social, Autoridad, Concreción, Pie en la puerta, Superación de la reacción, Reciprocidad, Anclaje y comparación, Impacto social, Escasez y Antropomorfismo. | Campo derivado de Dimension<br/> |
| Narrativas de la experiencia | ![IA generó](/help/assets/icons/AI.svg) narrativas que la experiencia está generando en función de la relevancia desde el punto de vista de un experto en marketing. | Campo derivado de Dimension<br/> |
| Tonos de la experiencia | ![IA generó](/help/assets/icons/AI.svg) tonos que la experiencia está creando según la relevancia desde el punto de vista de un experto en marketing | Campo derivado de Dimension<br/> |
| Emociones de marketing de la experiencia | ![IA generada](/help/assets/icons/AI.svg): la emoción invocada en el lector al leer el texto utilizado como parte de la experiencia: urgencia, exclusividad, estímulo, desafío, curiosidad, logro, confianza, simplicidad y fascinación. | Campo derivado de Dimension<br/> |
| Recuento de emojis de la experiencia | ![IA generó](/help/assets/icons/AI.svg) número de emojis para la experiencia. | Métrica |
| Recuento de Experience Hashtags | ![IA generó](/help/assets/icons/AI.svg) número de hashtags para la experiencia. | Métrica |
| Recuento de frases de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de frases para la experiencia. | Métrica |
| Proporción de palabras de detención de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de palabras de detención para la experiencia. | Métrica |
| Recuento de citas de texto de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de comillas de texto para la experiencia. | Métrica |
| Recuento de palabras de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de palabras para la experiencia. | Métrica |
| Recuento de palabras por frase de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de palabras por frase para la experiencia. | Métrica |

{style="table-layout:fixed"}


## Eventos de experiencia

| Título | Descripción | Tipo |
|---|---|---|
| Vistas de la experiencia | Medida cuantificable del número de vistas de la experiencia. | Métrica |
| Clics de la experiencia | Medida cuantificable del número de clics de la experiencia. | Métrica |

{style="table-layout:fixed"}


## Metadatos de recursos

| Título | Descripción | Tipo |
|---|---|---|
| ID del recurso | Identificador único del recurso. El binario de recursos determina la exclusividad. Si el binario del recurso cambia, el ID sí cambia. El ID único puede ser la dirección URL, pero también puede ser un hash creado. | Dimensión |
| Ruta HTML del recurso | Ruta de HTML concatenada para el recurso. | Dimensión |
| URL de vínculo del recurso | Anclaje de página más cercano del recurso. | Dimensión |
| Anchura de visualización del recurso | Anchura de visualización del recurso de contenido. | Dimensión |
| Altura de visualización del recurso | Altura de visualización del recurso de contenido. | Dimensión |
| Resto absoluto de recurso | Resto absoluto del recurso de contenido. | Dimensión |
| Máximo absoluto del recurso | Máximo absoluto del recurso de contenido. | Dimensión |

{style="table-layout:fixed"}


## Atributos del recurso

| Título | Descripción | Tipo |
|---|---|---|
| Atributos del recurso | ![IA generada](/help/assets/icons/AI.svg) Lista completa de todos los nombres y valores de atributos de recursos | Campo derivado de Dimension<br> |
| Orientación del recurso | ![IA generada](/help/assets/icons/AI.svg) Orientación del recurso. | Campo derivado de Dimension<br/> |
| Tono general del recurso | ![IA generada](/help/assets/icons/AI.svg) Tono general del recurso. | Campo derivado de Dimension<br/> |
| Colores de primer plano de recursos | ![IA generada](/help/assets/icons/AI.svg) Colores de primer plano del recurso. | Campo derivado de Dimension<br/> |
| Colores de fondo de recursos | ![IA generada](/help/assets/icons/AI.svg) colores de fondo del recurso. | Campo derivado de Dimension<br/> |
| Etiquetas del recurso | ![IA generó](/help/assets/icons/AI.svg) etiquetas para el recurso. | Campo derivado de Dimension<br/> |
| Escenas del recurso | ![IA generó](/help/assets/icons/AI.svg) escenas para el recurso. | Campo derivado de Dimension<br/> |
| Objetos del recurso | ![IA generó](/help/assets/icons/AI.svg) objetos del recurso. | Campo derivado de Dimension<br/> |
| Estilos de fotografía del recurso | ![IA generó](/help/assets/icons/AI.svg) estilos fotográficos del recurso. | Campo derivado de Dimension<br/> |
| Tipo de imagen del recurso | ![IA generada](/help/assets/icons/AI.svg) Tipo de imagen del recurso. Los valores posibles son: photo, sketch, paint, digital_cartoon, infographics, graphic_design, collage y software_screenshot. | Campo derivado de Dimension<br/> |
| Posiciones de cámara del recurso | ![IA generada](/help/assets/icons/AI.svg) posiciones de cámara del recurso. | Campo derivado de Dimension<br/> |
| Proximidades de la cámara de recursos | ![IA generó](/help/assets/icons/AI.svg) proximidad de la cámara del recurso. | Campo derivado de Dimension<br/> |
| Categorías de personas del recurso | ![IA generó](/help/assets/icons/AI.svg) categorías de personas para el recurso. Los valores posibles son: persona, hombre, mujer, grupo social, multitud, personas, niño, niña y niño. | Campo derivado de Dimension<br/> |
| Densidad de contenido visual del recurso | ![IA generada](/help/assets/icons/AI.svg) Densidad del contenido visual del recurso. Los valores posibles son: bajo, medio o alto. Una baja densidad de contenido implica una pequeña cantidad de información presente por unidad de área de la imagen. | Dimensión |
| Dispersión de la atención visual del recurso | ![IA generada](/help/assets/icons/AI.svg): difusión de atención visual del recurso. Los valores posibles son: bajo, medio o alto. La dispersión de la atención se refiere al grado en que la atención de un espectador se divide entre diferentes partes de una imagen. | Campo derivado de Dimension<br/> |
| Condiciones de iluminación del recurso | ![IA generada](/help/assets/icons/AI.svg) Condición de iluminación del recurso. Los valores posibles son: hora dorada, hora azul, mediodía, nublado, noche, clave alta, clave baja, luz diurna, incandescente, fluorescente, colorido y estudio. | Campo derivado de Dimension<br/> |
| Configuración de cámara del recurso | ![IA generada](/help/assets/icons/AI.svg) Configuración de cámara del recurso. Los valores posibles son: velocidad de obturación rápida, exposición prolongada. desenfoque de bokeh, desenfoque de movimiento, desenfoque de inclinación-cambio, flash, gran angular, blanco y negro, surrealista, doble exposición, macro y modo normal. | Campo derivado de Dimension<br/> |

{style="table-layout:fixed"}


## Eventos de recursos

| Título | Descripción | Tipo |
|---|---|---|
| Vistas de recurso | Medida cuantificable del número de vistas del recurso. | Métrica |
| Clics en recursos | Medida cuantificable del número de clics del recurso. | Métrica |

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
| Tasa de clics en recursos | Clics en recursos/Vistas de recursos | Métrica calculada |
| tasa de clics de experiencia | Clics en experiencias/Vistas de experiencias | Métrica calculada |

{style="table-layout:fixed"}

