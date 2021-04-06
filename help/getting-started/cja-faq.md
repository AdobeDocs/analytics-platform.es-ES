---
title: Preguntas frecuentes de Customer Journey Analytics
description: 'Customer Journey Analytics: Preguntas frecuentes.'
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 95%

---

# Preguntas frecuentes

## Requisitos previos

| Pregunta | Respuesta |
| --- | --- |
| ¿Necesito [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] para [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] y [!UICONTROL Device Coop] no son necesarios para [!UICONTROL Customer Journey Analytics]. De hecho, todavía no son compatibles. |
| ¿Necesito un [!UICONTROL Experience Cloud ID] (ECID) para [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] admite cualquier ID de un conjunto de datos, ya sea [!UICONTROL ECID] o cualquier otro ID de su elección. |
| ¿Qué sucede si necesito extraer, transformar o cargar datos antes de utilizar [!UICONTROL Customer Journey Analytics]? | Actualmente, debe trabajar con un socio que extraiga, transforme o cargue sus datos (Unifi o Informatica) si necesita transformarlos antes de ponerlos en AEP. Si necesita extraer, transformar o cargar los datos después de haberlos introducido, los [!UICONTROL Servicios de consulta de Adobe Experience Platform] ofrecen algunas opciones limitadas. |

## Vinculación de datos

| Pregunta | Respuesta |
| --- | --- |
| ¿Puede [!UICONTROL Customer Journey Analytics] “unir” varios dispositivos o conjuntos de datos? | Sí. [!UICONTROL Customer Journey Analytics] es un sistema de análisis que trabaja con ID propios. En noviembre de 2020 se lanzó una solución de vinculación. Más información. |
| ¿Se admite la unión del comportamiento anónimo al comportamiento autenticado? | Todavía no. |

## Introducción de datos en [!UICONTROL Customer Journey Analytics]

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo combinar datos de diferentes simuladores de pruebas de [!UICONTROL Adobe Experience Platform] en una conexión de [!UICONTROL Customer Journey Analytics]? | No. No puede acceder a los datos de entornos limitados. Solo se pueden combinar conjuntos de datos ubicados en el mismo entorno limitado. [Más información...](https://docs.adobe.com/content/help/es-ES/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| ¿Cuál es la latencia esperada para [!UICONTROL Customer Journey Analytics] en [!UICONTROL Adobe Experience Platform]? | <ul><li>En carga normal: &lt; 60 minutos <br>**Nota:** En caso de que sea un volumen inusualmente alto de flujo de datos a través de la canalización, podría durar hasta 24 horas.</li><li>Datos de relleno (hasta 13 meses de datos, independientemente del tamaño): &lt;4 semanas</li></ul> |
| ¿Cómo puede conectar datos en línea con datos sin conexión en [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] es un sistema de análisis que trabaja con ID propios. Siempre que el ID de usuario coincida entre conjuntos de datos, [!UICONTROL Customer Journey Analytics] puede conectar filtros, atribuciones, flujos, visitas en el orden previsto, etc. entre conjuntos de datos. |
| ¿Cómo puedo llevar mis datos sin conexión a [!UICONTROL Customer Journey Analytics]? | En primer lugar, debe llevar los datos a Experience Platform para poder utilizarlos con [!UICONTROL Customer Journey Analytics]. El equipo de incorporación de datos de Experience Platform puede ofrecer recomendaciones o asesoría a los clientes si lo necesitan. |
| ¿Cómo puedo obtener datos de [!UICONTROL Adobe Analytics] en [!UICONTROL Customer Journey Analytics]? | Los datos de [!UICONTROL Adobe Analytics] se pueden conectar a Experience Platform mediante el [conector de origen de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/experience-platform/sources/connectors/adobe-applications/analytics.html). La mayoría de los campos de [!UICONTROL Adobe Analytics] se transfieren en formato XDM, pero otros campos todavía no están disponibles (como las dimensiones de [!UICONTROL canales de marketing]). |
| ¿Cuánto tiempo se tarda en ensamblar elementos de conjuntos de datos a una vista de datos? | Tarda unas pocas horas en empezar y unos días en rellenar los últimos 13 meses de datos. |
| ¿Es necesario introducir datos PII para establecer conexiones entre ellos? | No, puede utilizar cualquier ID, incluido un hash de un ID de cliente, que no es PII. |

## Componentes tradicionales de [!UICONTROL Adobe Analytics]

| Pregunta | Respuesta |
| --- | --- |
| ¿Qué significa esto para nuestro producto tradicional de [!UICONTROL Adobe Analytics]? | [!UICONTROL Customer Journey Analytics] es nuestro producto de análisis de próxima generación. Pasar de nuestros productos actuales a [!UICONTROL Customer Journey Analytics] nos llevará años y requerirá de una gran coordinación. Para obtener más información, consulte [Compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| ¿Puedo compartir filtros de [!UICONTROL Customer Journey Analytics] a AEP u otras soluciones? | Todavía no. Estamos buscando nuevas e innovadoras formas de compartir filtros desde [!UICONTROL Customer Journey Analytics] a AEP en el futuro que no tengan un retraso tan largo. Dicho esto, puede compartir el resultado de los servicios de consulta con el Perfil unificado como una solución alternativa. |
| ¿Qué ha pasado con mi antigua configuración de eVar? | Los eVars, las propiedades y los eventos en el sentido tradicional de Adobe Analytics ya no existen en [!UICONTROL Customer Journey Analytics]. Tiene un número ilimitado de elementos de esquema (dimensiones, métricas, campos de lista). De modo que todos los ajustes de atribución que se aplicaron durante el proceso de recopilación de datos se aplican ahora en tiempo de consulta. |
| ¿Dónde están ahora todas las configuraciones de persistencia de la variable y sesiones? | [!UICONTROL Customer Journey Analytics] aplica todas estas configuraciones en el momento del informe y estas se encuentran ahora en Vistas de datos. Los cambios en esta configuración ahora son retroactivos y puede tener varias versiones con varias Vistas de datos. |
| ¿Qué les sucede a nuestros segmentos o métricas calculadas existentes? | [!UICONTROL Customer Journey Analytics] ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier esquema de AEP. Esto significa que ninguno de los segmentos existentes ni las métricas de cálculo son compatibles con [!UICONTROL Customer Journey Analytics]. |
| ¿Cómo gestiona [!UICONTROL Customer Journey Analytics] las `Uniques Exceeded` limitaciones? | [!UICONTROL Customer Journey Analytics] no tiene limitaciones de valor único, por lo que no es necesario preocuparse por ellas. |
| Si soy un cliente de [!DNL Data Workbench], ¿puedo pasar a [!UICONTROL Customer Journey Analytics] ahora mismo? | Depende. Si se basa principalmente en el proceso de cliente unificado (UCP), tendrá que esperar hasta que se haya implementado la unión. Si ya tiene tasas de autenticación de clientes altas, o si desea que todos los datos estén en un solo lugar o quiere deshacerse de las eVars, puede que Customer Journey Analytics sea lo que está buscando. |

## Implicaciones de la eliminación de componentes de datos

En cuanto a la eliminación, nos preocupan 6 componentes: simulación de pruebas, esquema, conjunto de datos, conexión, vista de datos y proyectos de Workspace. Estos son algunos de los escenarios posibles en los que puede ser necesario eliminar cualquiera de estos componentes:

| Y si... | Esto sucede... |
| --- | --- |
| ¿Desea eliminar un simulador de pruebas en [!UICONTROL Adobe Experience Platform]? | Al eliminar un simulador de pruebas, se detendrá el flujo de datos a cualquier conexión de [!UICONTROL Customer Journey Analytics] a conjuntos de datos de dicho simulador de pruebas. Actualmente, las conexiones en CJA vinculadas a dicho simulador de pruebas no se eliminarán automáticamente. |
| ¿Desea eliminar un esquema en [!UICONTROL Adobe Experience Platform], pero no los conjuntos de datos asociados a dicho esquema? | [!UICONTROL Adobe Experience Platform] no permite la eliminación de esquemas que tienen uno o varios conjuntos de datos asociados. Sin embargo, un administrador que tenga el conjunto de derechos adecuado podrá eliminar primero los conjuntos de datos y, a continuación, el esquema. |
| ¿Desea eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform]? | Al eliminar un conjunto de datos en AEP, se detendrá el flujo de datos desde dicho conjunto de datos a cualquier conexión que incluya el conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones con CJA asociadas. |
| ¿Elimino un conjunto de datos en [!UICONTROL Customer Journey Analytics]? | Actualmente, no se puede eliminar un conjunto de datos de una conexión que se haya guardado. Tendría que eliminar toda la conexión y comenzar de nuevo. (Sin embargo, puede eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform].) |
| ¿Desea eliminar un lote de un conjunto de datos (en [!UICONTROL Adobe Experience Platform])? | Si se elimina un lote de un conjunto de datos de [!UICONTROL Adobe Experience Platform], se eliminará el mismo lote de cualquier conexión de CJA que contenga dicho lote específico. CJA recibirá una notificación de las eliminaciones de lotes que se produzcan en [!UICONTROL Adobe Experience Platform]. |
| ¿Desea eliminar un lote **mientras se está introduciendo** en [!UICONTROL Customer Journey Analytics]? | Si solo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de dicho lote en [!UICONTROL Customer Journey Analytics]. La introducción se revertirá. Si, por ejemplo, hay 5 lotes en el conjunto de datos y 3 de ellos ya se han introducido cuando se eliminó el conjunto de datos, los datos de esos 3 lotes aparecerán en [!UICONTROL Customer Journey Analytics]. |
| ¿Desea eliminar una conexión en [!UICONTROL Customer Journey Analytics]? | Aparecerá un mensaje de error para indicar lo siguiente:<ul><li>Las vistas de datos creadas para la conexión eliminada ya no funcionarán.</li><li> Del mismo modo, los proyectos de Workspace que dependan de vistas de datos en la conexión eliminada dejarán de funcionar.</li></ul> |
| ¿Desea eliminar una vista de datos en [!UICONTROL Customer Journey Analytics]? | Un mensaje de error indicará que dejarán de funcionar todos los proyectos de Workspace que dependan de esta vista de datos eliminada. |
