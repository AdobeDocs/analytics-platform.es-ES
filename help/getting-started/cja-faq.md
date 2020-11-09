---
title: Preguntas frecuentes de Customer Journey Analytics
description: 'Customer Journey Analytics: Preguntas frecuentes.'
translation-type: tm+mt
source-git-commit: 830e7d71ad38539d1a73fe2df9f8886956f57acc
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 42%

---


# Preguntas frecuentes

## Requisitos previos

| Pregunta | Respuesta |
| --- | --- |
| Necesito [!UICONTROL Gráfico de dispositivos privados] o [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Gráfico de dispositivos privados] o [!UICONTROL Device Coop] no son obligatorios para [!UICONTROL Customer Journey Analytics]. De hecho, todavía no son compatibles. |
| Necesito [!UICONTROL ID de Experience Cloud] (ECID) para [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] admite cualquier ID de un conjunto de datos, ya sea ECID o cualquier otro ID de su elección. |
| ¿Qué sucede si necesito ETL (Extraer, Transformar, Cargar) mis datos antes de [!UICONTROL Customer Journey Analytics]? | Actualmente, debe trabajar con un socio que extraiga, transforme o cargue sus datos (Unifi o Informatica) si necesita transformarlos antes de ponerlos en AEP. Si necesita ETL después de que los datos ya se hayan ingerido, [!UICONTROL Adobe Experience Platform Consulta Services] proporciona algunas opciones limitadas. |

## Configuración de datos

| Pregunta | Respuesta |
| --- | --- |
| ¿Puede [!UICONTROL Customer Journey Analytics] “unir” varios dispositivos o conjuntos de datos? | Sí. [!UICONTROL Customer Journey Analytics] es un sistema de análisis que trabaja con ID propios. Lanzamos una solución de costura en noviembre de 2020. Más información. |
| ¿Se admite la unión del comportamiento anónimo al comportamiento autenticado? | Todavía no. |

## Introducción de datos en [!UICONTROL Customer Journey Analytics]

| Pregunta | Respuesta |
| --- | --- |
| Puedo combinar datos de diferentes [!UICONTROL Adobe Experience Platform] entornos limitados en uno [!UICONTROL Customer Journey Analytics] conexión? | No. No puede acceder a los datos de entornos limitados. Solo se pueden combinar conjuntos de datos ubicados en el mismo entorno limitado. [Más información...](https://docs.adobe.com/content/help/es-ES/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| ¿Cuál es la latencia esperada para [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>En carga normal: &lt; 60 minutos <br>**Nota:** En caso de que sea un volumen inusualmente alto de flujo de datos a través de la canalización, podría durar hasta 24 horas.</li><li>Datos de relleno (hasta 13 meses de datos, independientemente del tamaño): &lt;4 semanas</li></ul> |
| ¿Cómo puede conectar datos en línea con datos sin conexión en [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] es un sistema de análisis que trabaja con ID propios. Siempre que el ID de usuario coincida entre conjuntos de datos, [!UICONTROL Customer Journey Analytics] puede conectar segmentos, atribuciones, flujos, visitas en orden previsto, etc. entre conjuntos de datos. |
| ¿Cómo se llevan los datos sin conexión a [!UICONTROL Customer Journey Analytics]? | Antes de poder usar los datos con el Experience Platform, primero debe enviarlos. [!UICONTROL Customer Journey Analytics]. El equipo de incorporación de datos de Experience Platform puede ofrecer recomendaciones o asesoría a los clientes si lo necesitan. |
| ¿Cómo puedo obtener [!UICONTROL Adobe Analytics] datos en [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] los datos se pueden conectar al Experience Platform a través del [Conector de Adobe Analytics Source](https://docs.adobe.com/content/help/es-ES/experience-platform/sources/connectors/adobe-applications/analytics.html). Más [!UICONTROL Adobe Analytics] los campos se recuperan en formato XDM, pero otros campos aún no están disponibles (como [!UICONTROL Canales de mercadotecnia] dimensiones). |
| ¿Cuánto tiempo se tarda en ensamblar elementos de conjuntos de datos a una vista de datos? | Tarda unas pocas horas en empezar y unos días en rellenar los últimos 13 meses de datos. |
| ¿Es necesario introducir datos PII para establecer conexiones entre ellos? | No, puede utilizar cualquier ID, incluido un hash de un ID de cliente, que no es PII. |

## Tradicional [!UICONTROL Adobe Analytics] componentes

| Pregunta | Respuesta |
| --- | --- |
| ¿Qué significa esto para nuestra tradición? [!UICONTROL Adobe Analytics] product? | [!UICONTROL Customer Journey Analytics es nuestro producto de análisis de próxima generación. ] Evolucionando de nuestros productos actuales a [!UICONTROL Customer Journey Analytics] tomará años y mucha coordinación. Para obtener más información, consulte [Compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| ¿Puedo compartir segmentos desde [!UICONTROL Customer Journey Analytics] ¿AEP u otras soluciones? | Todavía no. Estamos buscando nuevas e innovadoras formas de compartir segmentos de [!UICONTROL Customer Journey Analytics] a AEP en el futuro que no tengan un retraso tan largo. Dicho esto, puede compartir el resultado de los servicios de consulta con el Perfil unificado como una solución alternativa. |
| ¿Qué ha pasado con mi antigua configuración de eVar? | Ya no existen eVars, propiedades y eventos en el sentido tradicional de Adobe Analytics en [!UICONTROL Customer Journey Analytics]. Tiene un número ilimitado de elementos de esquema (dimensiones, métricas, campos de lista). De modo que todos los ajustes de atribución que se aplicaron durante el proceso de recopilación de datos se aplican ahora en tiempo de consulta. |
| ¿Dónde están ahora todas las configuraciones de persistencia de la variable y sesiones? | [!UICONTROL Customer Journey Analytics aplica todas estas configuraciones en el momento del informe y estas se encuentran ahora en Vistas de datos. ] Los cambios en esta configuración ahora son retroactivos y puede tener varias versiones con varias Vistas de datos. |
| ¿Qué les sucede a nuestros segmentos o métricas calculadas existentes? | [!UICONTROL Customer Journey Analytics ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier esquema de AEP. ] Esto significa que ninguna de las métricas de cálculo o segmentos existentes son compatibles con [!UICONTROL Customer Journey Analytics]. |
| ¿Cómo se hace? [!UICONTROL Customer Journey Analytics] control `Uniques Exceeded` limitaciones? | [!UICONTROL Customer Journey Analytics no tiene limitaciones de valor únicas, por lo que no es necesario preocuparse por ellas.] |
| Si soy un cliente de [!DNL Data Workbench], ¿puedo pasar a Customer Journey Analytics ahora mismo? | Depende. Si se basa principalmente en el proceso de cliente unificado (UCP), tendrá que esperar hasta que se haya implementado la unión. Si ya tiene tasas de autenticación de clientes altas, o si desea que todos los datos estén en un solo lugar o quiere deshacerse de las eVars, puede que Customer Journey Analytics sea lo que está buscando. |

## Implicaciones de la eliminación de componentes de datos

En cuanto a la eliminación, nos preocupan 6 componentes: simulación de pruebas, esquema, conjunto de datos, conexión, vista de datos y proyectos de Workspace. Estos son algunos de los escenarios posibles para eliminar cualquiera de estos componentes:

| Y si... | Esto sucede... |
| --- | --- |
| Eliminar un entorno limitado en [!UICONTROL Adobe Experience Platform]? | La eliminación de un simulador para pruebas detendrá el flujo de datos a cualquier [!UICONTROL Customer Journey Analytics] conexiones a conjuntos de datos en ese entorno limitado. Actualmente, las conexiones en CJA vinculadas a ese entorno limitado no se eliminarán automáticamente. |
| Eliminar un esquema en [!UICONTROL Adobe Experience Platform], pero no los conjuntos de datos asociados con este esquema? | [!UICONTROL Adobe Experience Platform] no permite la eliminación de esquemas que tienen uno o más conjuntos de datos asociados a ellos. Sin embargo, un administrador con el conjunto de derechos adecuado puede eliminar primero los conjuntos de datos y, a continuación, eliminar el esquema. |
| Eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform]? | Al eliminar un conjunto de datos en AEP, se detendrá el flujo de datos desde ese conjunto de datos a cualquier conexión que incluya dicho conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones CJA asociadas. |
| Eliminar un conjunto de datos en [!UICONTROL Customer Journey Analytics]? | Actualmente, no puede eliminar un conjunto de datos dentro de una conexión que se haya guardado. Tendrías que borrar toda la conexión y el inicio. (Sin embargo, puede eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform].) |
| Eliminar un lote de un conjunto de datos (en [!UICONTROL Adobe Experience Platform])? | Si se elimina un lote de un conjunto de datos AEP, el mismo lote se eliminará de cualquier conexión CJA que contenga ese lote específico. |
| Eliminar un lote **mientras se está ingeriendo** into [!UICONTROL Customer Journey Analytics]? | Si solo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de ese lote en [!UICONTROL Customer Journey Analytics]. La ingestión se revertirá. Si, por ejemplo, hay 5 lotes en el conjunto de datos y 3 de ellos ya se han ingerido cuando se eliminó el conjunto de datos, los datos de esos 3 lotes aparecerán en [!UICONTROL Customer Journey Analytics]. |
| Eliminar una conexión en [!UICONTROL Customer Journey Analytics]? | Un mensaje de error indicará que:<ul><li>Las vistas de datos creadas para la conexión eliminada ya no funcionarán.</li><li> Del mismo modo, cualquier proyecto de Workspace que dependa de vistas de datos en la conexión eliminada dejará de funcionar.</li></ul> |
| Eliminar una vista de datos en [!UICONTROL Customer Journey Analytics]? | Un mensaje de error indicará que cualquier proyecto de Workspace que dependa de esta vista de datos eliminada dejará de funcionar. |
| Eliminar un proyecto de Workspace en [!UICONTROL Customer Journey Analytics]? | Puede volver a crear el proyecto o puede usar una solución para recuperarlo. Sólo vaya a [!UICONTROL Administración > Registros > Registro de uso y acceso], busque el proyecto eliminado y copie su ID. A continuación, abra cualquier proyecto de Workspace y actualice el ID en la URL con el copiado. A continuación, guarde el proyecto. |
