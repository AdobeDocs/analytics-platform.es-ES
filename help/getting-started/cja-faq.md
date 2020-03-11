---
title: Preguntas más frecuentes sobre Análisis de Viaje del Cliente
description: 'Análisis del viaje del cliente: Preguntas más frecuentes.'
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| **Requisitos previos** |  |
| ¿Necesita Device Graph o Device Coop para el análisis de viajes del cliente? | No, Device Graph o Device Coop no son obligatorios para los análisis de viajes del cliente. De hecho, todavía no son compatibles. |
| ¿Necesita el ID de Experience Cloud (ECID) para el análisis de viajes del cliente? | No, Customer Journey Analytics admite cualquier ID de un conjunto de datos, ya sea ECID o cualquier otro ID que elija. |
| ¿Qué sucede si necesita ETL (Extraer, Transformar, Cargar) sus datos antes de que el cliente haga un análisis de viajes? | Hoy en día, debe trabajar con un socio de ETL (Unifi o Informatica) si necesita transformar sus datos antes de ponerlos en AEP. Si necesita ETL después de que los datos ya se hayan ingestado, AEP Query Services proporciona algunas opciones limitadas. |
| **Stitching** |  |
| ¿Puede el análisis de viajes del cliente &quot;unir&quot; varios dispositivos o conjuntos de datos? | No. Customer Journey Analytics es un sistema de análisis de &quot;traer su propio ID&quot;. Los planes para un buen enfoque de costura están en marcha. |
| ¿Se admite la vinculación del comportamiento anónimo al comportamiento autenticado? | No, todavía no. |
| **Introducción de datos en el análisis de viajes del cliente** |  |
| ¿Cuál es la latencia esperada para Customer Journey Analytics en la plataforma? | <ul><li>Bajo carga normal: &lt; 60<br>**minutosNota:**En el caso de un volumen inusualmente alto de flujo de datos a través de la canalización, podría tomar hasta 24 horas.</li><li>Datos de relleno (hasta 10.000 millones de eventos): &lt; 4 semanas</li></ul> |
| ¿Cómo conecta datos en línea con datos sin conexión en el análisis de viajes del cliente? | Customer Journey Analytics es un sistema de análisis de &quot;traer su propio ID&quot;. Siempre que el ID de persona coincida entre conjuntos de datos, el análisis de recorrido del cliente puede conectar segmentos, atribución, flujo, visitas en el orden previsto, etc. entre conjuntos de datos. |
| ¿Cómo puedo llevar mis datos sin conexión a Análisis de viajes del cliente? | Los clientes deben primero traer cualquier dato a AEP para poder utilizarlo con el análisis de viajes del cliente. El equipo de integración de datos de la plataforma de experiencia puede ayudar a ofrecer recomendaciones o asesoría a los clientes si es necesario. |
| ¿Cómo puedo obtener datos de Analytics en el análisis de viajes del cliente? | Los datos de Analytics se pueden conectar a AEP mediante el conector de datos de Analytics. La mayoría de los campos de Analytics se transfieren en formato XDM, pero otros campos aún no están disponibles (como las dimensiones de los canales de mercadotecnia). |
| ¿Cuánto tiempo se tarda en ensamblar elementos de conjuntos de datos en una vista de datos? | Unas pocas horas para empezar, y unos días para rellenar los últimos 13 meses de datos. |
| ¿Es necesario introducir datos PII para establecer conexiones entre los datos? | No, puede utilizar cualquier ID, incluido un hash de un ID de cliente, que no es PII. |
| **Componentes tradicionales de Analytics** |  |
| ¿Qué significa esto para nuestro producto tradicional de Adobe Analytics? | Customer Journey Analytics es nuestro producto de análisis de próxima generación. Pasar de nuestros productos actuales a Customer Journey Analytics llevará años y mucha coordinación juntos. Esta versión es un gran paso de muchos en esta dirección. |
| ¿Puedo compartir segmentos de Análisis de viajes del cliente con AEP u otras soluciones? | Todavía no. Estamos buscando nuevas e innovadoras formas de compartir segmentos desde Análisis del viaje del cliente a AEP en el futuro que no tengan un retraso tan prolongado. Dicho esto, puede compartir el resultado de Query Services con Unified Profile como una solución alternativa potencial. |
| ¿Qué ha pasado con mi configuración de eVar antigua? | Las eVars, las propiedades y los eventos de la sensación tradicional de Adobe Analytics ya no existen en el análisis de viajes del cliente. Tiene un número ilimitado de elementos de esquema (dimensiones, métricas, campos de lista). De modo que todos los ajustes de atribución que se aplicaron durante el proceso de recopilación de datos ahora se aplican en el momento de la consulta. |
| ¿Dónde están ahora todas las configuraciones de persistencia de variables y sesiones? | El análisis de viaje del cliente aplica todas estas configuraciones en el momento del informe, y estas opciones ahora están activas en las vistas de datos. Los cambios en esta configuración ahora son retroactivos y puede tener varias versiones con varias vistas de datos. |
| ¿Qué les sucede a nuestros segmentos o métricas calculadas existentes? | Customer Journey Analytics ya no utiliza eVars, props ni eventos y, en su lugar, utiliza ningún esquema AEP. Esto significa que ninguno de los segmentos existentes o las métricas de cálculo son compatibles con el análisis de viajes del cliente. |
| ¿Cómo gestiona Customer Journey Analytics `Uniques Exceeded` las limitaciones? | Customer Journey Analytics no tiene limitaciones de valor únicas, por lo que no es necesario preocuparse por ellas. |
| Si soy un cliente [!DNL Data Workbench] existente, ¿puedo pasar a Customer Journey Analytics ahora mismo? | Depende. Si se basa en gran medida en el proceso de cliente unificado (UCP), tendrá que esperar hasta que se haya implementado la vinculación. Si ya tiene tasas de autenticación de clientes altas, o si desea que todos los datos estén en un solo lugar o desea deshacerse de las eVars, puede que el análisis de viajes de clientes sea un buen ajuste. |

