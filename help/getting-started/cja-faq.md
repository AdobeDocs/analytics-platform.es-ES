---
title: Preguntas frecuentes de Customer Journey Analytics
description: 'Customer Journey Analytics: Preguntas frecuentes.'
translation-type: tm+mt
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| **Requisitos previos** |  |
| Do you need Device Graph or Device Coop for [!UICONTROL Customer Journey Analytics]? | No, Private Device Graph or Device Coop are not required for [!UICONTROL Customer Journey Analytics]. De hecho, todavía no son compatibles. |
| Do you need Experience Cloud ID (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that&#39;s ECID or any other ID you choose. |
| ¿Qué sucede si se necesita extraer, transformar o cargar datos antes de utilizar Customer Journey Analytics? | Actualmente, debe trabajar con un socio que extraiga, transforme o cargue sus datos (Unifi o Informatica) si necesita transformarlos antes de ponerlos en AEP. Si necesita extraer, transformar o cargar los datos después de haberlos ingestado, los servicios de consulta de AEP ofrecen algunas opciones limitadas. |
| **Unión** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; across devices or across datasets? | No. [!UICONTROL Customer Journey Analytics] es un sistema de análisis de &quot;traer su propio ID&quot;. Se está trabajando en planes para conseguir un buen sistema de unión. |
| ¿Se admite la unión del comportamiento anónimo al comportamiento autenticado? | Todavía no. |
| **Introducción de datos en[!UICONTROL Customer Journey Analytics]** |  |
| What is the expected latency for [!UICONTROL Customer Journey Analytics] on [!UICONTROL Experience Platform]? | <ul><li>En carga normal: &lt; 60 minutos <br>**Nota:** En caso de que sea un volumen inusualmente alto de flujo de datos a través de la canalización, podría durar hasta 24 horas.</li><li>Datos de relleno (hasta 10 000 millones de eventos): &lt; 4 semanas</li></ul> |
| How do you connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] es un sistema de análisis de &quot;traer su propio ID&quot;. As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. entre conjuntos de datos. |
| ¿Cómo puedo llevar mis datos sin conexión a Customer Journey Analytics? | Los clientes deben primero llevar cualquier dato a la plataforma de experiencias para poder utilizarlo con el análisis de viajes del cliente. El equipo de incorporación de datos de Experience Platform puede ofrecer recomendaciones o asesoría a los clientes si lo necesitan |
| ¿Cómo puedo obtener datos de Analytics en Customer Journey Analytics? | Los datos de Analytics se pueden conectar a la plataforma de experiencias a través del conector de datos de Analytics. La mayoría de los campos de Analytics se transfieren en formato XDM, pero otros todavía no están disponibles (como las dimensiones Canales de marketing). |
| ¿Cuánto tiempo se tarda en ensamblar elementos de conjuntos de datos a una vista de datos? | Tarda unas pocas horas en empezar y unos días en rellenar los últimos 13 meses de datos. |
| ¿Es necesario introducir datos PII para establecer conexiones entre ellos? | No, puede utilizar cualquier ID, incluido un hash de un ID de cliente, que no es PII. |
| **Componentes tradicionales de Analytics** |  |
| ¿Qué significa esto para nuestro producto tradicional de Adobe Analytics? | Customer Journey Analytics es nuestro producto de análisis de próxima generación. Pasar de nuestros productos actuales a Customer Journey Analytics nos llevará años y requerirá de una gran coordinación. Esta versión es el primer gran paso de los muchos que tomaremos. |
| ¿Puedo compartir segmentos desde Customer Journey Analytics a AEP u otras soluciones? | Todavía no. Estamos buscando nuevas e innovadoras formas de compartir segmentos desde Customer Journey Analytics a AEP en el futuro que no conlleven un tiempo de espera demasiado largo. Dicho esto, puede compartir el resultado de los servicios de consulta con el Perfil unificado como una solución alternativa. |
| ¿Qué ha pasado con mi antigua configuración de eVar? | Las eVars, las propiedades y los eventos en el sentido tradicional de Adobe Analytics ya no existen en Customer Journey Analytics. Tiene un número ilimitado de elementos de esquema (dimensiones, métricas, campos de lista). De modo que todos los ajustes de atribución que se aplicaron durante el proceso de recopilación de datos se aplican ahora en tiempo de consulta. |
| ¿Dónde están ahora todas las configuraciones de persistencia de la variable y sesiones? | Customer Journey Analytics aplica todas estas configuraciones en el momento del informe y estas se encuentran ahora en Vistas de datos. Los cambios en esta configuración ahora son retroactivos y puede tener varias versiones con varias Vistas de datos. |
| ¿Qué les sucede a nuestros segmentos o métricas calculadas existentes? | Customer Journey Analytics ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier esquema de AEP. Esto significa que ninguno de los segmentos existentes ni las métricas de cálculo son compatibles con Customer Journey Analytics. |
| ¿Cómo gestiona Customer Journey Analytics las limitaciones `Uniques Exceeded`? | Customer Journey Analytics no tiene limitaciones de valor únicas, por lo que no es necesario preocuparse por ellas. |
| Si soy un cliente de [!DNL Data Workbench], ¿puedo pasar a Customer Journey Analytics ahora mismo? | Depende. Si se basa principalmente en el proceso de cliente unificado (UCP), tendrá que esperar hasta que se haya implementado la unión. Si ya tiene tasas de autenticación de clientes altas, o si desea que todos los datos estén en un solo lugar o quiere deshacerse de las eVars, puede que Customer Journey Analytics sea lo que está buscando. |

