---
title: Componentes de análisis de contenido
description: Detalles sobre los componentes específicos de Content Analytics, como dimensiones, métricas (calculadas) y campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
source-git-commit: 2958efb16ed2f5dbd754b407ddb3b6bc2f7c1ee1
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 17%

---

# Componentes de análisis de contenido

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Análisis de contenido. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

Content Analytics agrega las siguientes categorías de componentes (dimensiones, métricas (calculadas), campos derivados) a los componentes ya disponibles en Customer Journey Analytics:

* [Metadatos de experiencia](#experience-metadata)
* [Atributos de la experiencia](#experience-attributes)
* [Eventos de experiencia](#experience-events)
* [Metadatos de recursos](#asset-metadata)
* [Atributos del recurso](#asset-attributes)
* [Eventos de Assets](#asset-events)
* [Métricas calculadas ](#calculated-metrics)

En las tablas siguientes, ![IA generada](/help/assets/icons/AI.svg) indica un valor generado por AI/ML.

## Metadatos de experiencia

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Canal de la experiencia | Canal para la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Fuente de la experiencia | URL de Source de la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| ID de la experiencia | ID único de la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Nombre de la experiencia | Nombre de la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Descripción de la experiencia | Descripción de la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| URL de miniatura de la experiencia | URL de la miniatura de la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Profundidad porcentual horizontal de la experiencia | Valor cuantificable de la profundidad porcentual horizontal de la experiencia. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Profundidad porcentual vertical de la experiencia | Valor cuantificable de la profundidad porcentual vertical de la experiencia. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Profundidad de píxeles horizontales de la experiencia | Valor cuantificable de la profundidad de píxel horizontal de la experiencia. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Profundidad de píxeles verticales de la experiencia | Valor cuantificable de la profundidad de píxel vertical de la experiencia. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |


## Atributos de la experiencia

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Puntuación de legibilidad de la experiencia | ![AI generó](/help/assets/icons/AI.svg) puntuación de legibilidad para la experiencia. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Palabras clave de la experiencia | ![IA generó](/help/assets/icons/AI.svg) palabras clave para la experiencia. | Campo derivado de Dimension<br> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Estrategias de persuasión de la experiencia | ![AI generó](/help/assets/icons/AI.svg) estrategias de persuasión presentes en la experiencia dada. Los valores posibles son: Identidad social, Prueba social, Autoridad, Concreción, Pie en la puerta, Superación de la reacción, Reciprocidad, Anclaje y comparación, Impacto social, Escasez y Antropomorfismo. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Narrativas de la experiencia | ![IA generó](/help/assets/icons/AI.svg) narrativas que la experiencia está generando en función de la relevancia desde el punto de vista de un experto en marketing. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Tonos de la experiencia | ![IA generó](/help/assets/icons/AI.svg) tonos que la experiencia está creando según la relevancia desde el punto de vista de un experto en marketing | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Emociones de marketing de la experiencia | ![IA generada](/help/assets/icons/AI.svg) La emoción invocada en el lector al leer la experiencia: Urgencia, Exclusividad, Aliento, Desafío, Curiosidad, Logro, Confianza, Simplicidad y Fascinación. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Recuento de emojis de la experiencia | ![IA generó](/help/assets/icons/AI.svg) número de emojis para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Recuento de Experience Hashtags | ![IA generó](/help/assets/icons/AI.svg) número de hashtags para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Recuento de frases de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de frases para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Proporción de palabras de detención de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de palabras de detención para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Recuento de citas de texto de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de comillas de texto para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Recuento de palabras de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de palabras para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Recuento de palabras por frase de la experiencia | ![IA generada](/help/assets/icons/AI.svg) Número de palabras por frase para la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |


## Eventos de experiencia

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Vistas de experiencias | Medida cuantificable del número de vistas de la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Clics de experiencia | Medida cuantificable del número de clics de la experiencia. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |


## Metadatos de recursos

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Origen de recursos | URL de origen pública y accesible para el recurso. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| ID del recurso | Identificador único del recurso. El binario de recursos determina la exclusividad. Si el binario del recurso cambia, el ID sí cambia. El ID único puede ser la dirección URL, pero también puede ser un hash creado. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Nombre del recurso | Nombre del recurso. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Tipo de recurso | Tipo de recurso. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| URL de miniatura del recurso | URL de la miniatura del recurso. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Ruta HTML del recurso | Ruta de HTML concatenada para el recurso. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| URL de vínculo del recurso | Anclaje de página más cercano del recurso. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Anchura de visualización del recurso | Anchura de visualización del recurso de contenido. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Altura de visualización del recurso | Altura de visualización del recurso de contenido. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Resto absoluto de recurso | Resto absoluto del recurso de contenido. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Máximo absoluto del recurso | Máximo absoluto del recurso de contenido. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Recurso creado por | Identificador para la creación de recursos. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Fecha de creación del recurso | Fecha de creación del recurso. | Dimensión | \| Más reciente Session |
| Última actualización del recurso por | Identificador para la actualización de recursos. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Fecha de última actualización del recurso | Fecha de actualización del recurso. | Dimensión | \| Más reciente Session |


## Atributos del recurso

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Orientación del recurso | ![IA generada](/help/assets/icons/AI.svg) Orientación del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Tono general del recurso | ![IA generada](/help/assets/icons/AI.svg) Tono general del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Colores de primer plano de recursos | ![IA generada](/help/assets/icons/AI.svg) Colores de primer plano del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Color de fondo del recurso | ![IA generada](/help/assets/icons/AI.svg) colores de fondo del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Etiquetas del recurso | ![IA generó](/help/assets/icons/AI.svg) etiquetas para el recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Escenas del recurso | ![IA generó](/help/assets/icons/AI.svg) escenas para el recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Objetos del recurso | ![IA generó](/help/assets/icons/AI.svg) objetos del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Estilos de fotografía del recurso | ![IA generó](/help/assets/icons/AI.svg) estilos fotográficos del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Tipo de imagen del recurso | ![IA generada](/help/assets/icons/AI.svg) Tipo de imagen del recurso. Los valores posibles son: photo, sketch, paint, digital_cartoon, infographics, graphic_design, collage y software_screenshot. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Posiciones de cámara del recurso | ![IA generada](/help/assets/icons/AI.svg) posiciones de cámara del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Proximidades de la cámara de recursos | ![IA generó](/help/assets/icons/AI.svg) proximidad de la cámara del recurso. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Categorías de personas del recurso | ![IA generó](/help/assets/icons/AI.svg) categorías de personas para el recurso. Los valores posibles son: persona, hombre, mujer, grupo social, multitud, personas, niño, niña y niño. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Densidad de contenido visual del recurso | ![IA generada](/help/assets/icons/AI.svg) Densidad del contenido visual del recurso. Los valores posibles son: bajo, medio o alto. Una baja densidad de contenido implica una pequeña cantidad de información presente por unidad de área de la imagen. | Dimensión | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Dispersión de la atención visual del recurso | ![IA generada](/help/assets/icons/AI.svg): difusión de atención visual del recurso. Los valores posibles son: bajo, medio o alto. La dispersión de la atención se refiere al grado en que la atención de un espectador se divide entre diferentes partes de una imagen. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Condiciones de iluminación del recurso | ![IA generada](/help/assets/icons/AI.svg) Condición de iluminación del recurso. Los valores posibles son: hora dorada, hora azul, mediodía, nublado, noche, clave alta, clave baja, luz diurna, incandescente, fluorescente, colorido y estudio. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |
| Configuración de cámara del recurso | ![IA generada](/help/assets/icons/AI.svg) Configuración de cámara del recurso. Los valores posibles son: velocidad de obturación rápida, exposición prolongada. desenfoque de bokeh, desenfoque de movimiento, desenfoque de inclinación-cambio, flash, gran angular, blanco y negro, surrealista, doble exposición, macro y modo normal. | Campo derivado de Dimension<br/> | Mostrar \| Sin valor<br/>Más reciente \| Session |


## Eventos de recursos

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Vistas de recursos | Medida cuantificable del número de vistas del recurso. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |
| Clics en recursos | Medida cuantificable del número de clics del recurso. | Métrica | Contar valores<br/>Decimal \| Lugares decimales: 0 |


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |
-->

## Métricas calculadas 

| Título | Descripción | Tipo | Configuración |
|---|---|---|---|
| Tasa de clics en recursos | Clics en recursos/Vistas de recursos | Métrica calculada | |
| tasa de clics de experiencia | Clics en experiencias/Vistas de experiencias | Métrica calculada | |
