---
title: Usar dimensiones de canal de marketing en Adobe Experience Platform
description: Utilice el conector de datos de Analytics para incorporar reglas de procesamiento de Marketing Canal a Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 3%

---


# Usar dimensiones de canal de marketing en Adobe Experience Platform

Si su organización utiliza el [conector de datos de Analytics](https://docs.adobe.com/content/help/es-ES/experience-platform/sources/connectors/adobe-applications/analytics.html) para llevar los datos del grupo de informes a CJA, puede configurar una conexión en CJA para informar sobre las dimensiones de Marketing Canal.

## Requisitos previos

* Los datos del grupo de informes ya deben importarse a Adobe Experience Platform mediante el [conector de datos de Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). No se admiten otras fuentes de datos, ya que los canales de marketing dependen de las reglas de procesamiento de un grupo de informes de Analytics.
* Las reglas de procesamiento de Marketing canal ya deben estar configuradas. Consulte [Reglas de procesamiento para Canales de marketing](https://docs.adobe.com/content/help/es-ES/analytics/components/marketing-channels/c-rules.html) en la guía Componentes de Analytics tradicionales.

## Elementos de esquema de Marketing Canal

Una vez que haya establecido el conector de datos de Analytics en un grupo de informes deseado, se creará un esquema XDM. Este esquema contiene todas las dimensiones y métricas de Analytics como datos sin procesar. Estos datos sin procesar no contienen atribución ni persistencia. En su lugar, cada evento se ejecuta mediante reglas de procesamiento de canal de marketing y registra la primera regla que coincide. Especifique la atribución y la persistencia al crear una vista de datos en CJA.

1. [Cree una ](/help/connections/create-connection.md) conexión que incluya un conjunto de datos basado en el conector de datos de Analytics.
2. [Cree una ](/help/data-views/create-dataview.md) vista de datos que incluya las siguientes dimensiones:
   * **`channel.typeAtSource`**:: Equivalente a la dimensión  [de canal ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) de marketing.
   * **`channel._id`**:: Equivalente al detalle del canal  [de marketing](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Si desea dimensiones de primer toque y de último toque, arrastre cada dimensión de canal de marketing al área de componentes varias veces. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Adobe también recomienda asignar un nombre para mostrar a cada dimensión para facilitar su uso en Workspace.
4. Cree la vista de datos.

Sus dimensiones de canal de marketing ya están disponibles para su uso en Analysis Workspace.

## Diferencias de procesamiento y arquitectura

>[!IMPORTANT]
>
>Existen varias diferencias fundamentales entre los datos del grupo de informes y los datos de la plataforma. Adobe recomienda encarecidamente ajustar las reglas de procesamiento de canales de mercadotecnia del grupo de informes para facilitar la recopilación adecuada de datos en la plataforma.

La configuración del canal de marketing funciona de forma diferente entre los datos de la plataforma y los datos del grupo de informes. Tenga en cuenta las siguientes diferencias al configurar canales de mercadotecnia para CJA:

* **Es la primera página de la visita**: Este criterio de regla es común en varias definiciones de canales de mercadotecnia predeterminadas. Cualquier regla de procesamiento que contenga este criterio se ignora en Plataforma (se seguirán aplicando otros criterios de la misma regla). Las sesiones se determinan en el momento de la consulta de datos en lugar de en el momento de la recopilación de datos, lo que impide que la Plataforma use estos criterios específicos de regla. Adobe recomienda eliminar el criterio &#39;Es la primera página de la visita&#39; de cada regla de procesamiento de canal de marketing.

   ![Primera página de la visita](assets/first-page-of-visit.png)

* **Anular Canal** de último toque: Esta configuración en el Administrador de Canales de mercadotecnia generalmente evita que ciertos canales obtengan crédito de canal de último toque. La plataforma ignora esta configuración, permitiendo que canales generales como &#39;Directo&#39; o &#39;Interno&#39; atribuyan métricas de formas potencialmente no deseadas. Adobe recomienda eliminar canales en los que tenga la opción &#39;Anular Canal de último toque&#39; desactivada.
   * Puede eliminar el canal de mercadotecnia &#39;Directo&#39; en el Administrador de Canales de mercadotecnia y, a continuación, confiar en el elemento de dimensión &#39;Sin valor&#39; de CJA para ese canal. También puede cambiar el nombre de este elemento de dimensión a &#39;Directo&#39; o excluir por completo el elemento de dimensión al configurar una vista de datos.
   * De forma alternativa, puede crear una clasificación de canal de marketing, clasificando cada valor en sí mismo excepto para los canales que desee excluir en CJA. A continuación, puede utilizar esta dimensión de clasificación al crear una vista de datos en lugar de `channel.typeAtSource`.

   ![Omitir canal de último toque](assets/override-last-touch-channel.png)

* **Caducidad** del Canal de mercadotecnia: Esta configuración del período de compromiso determina el período de inactividad antes de que un visitante pueda obtener un nuevo canal de primer toque en los datos del grupo de informes. Platform utiliza su propia configuración de atribución, por lo que esta configuración se ignora por completo en CJA.

   ![Caducidad del canal de marketing](assets/marketing-channel-expiration.png)

## Comparación de datos entre CJA y Analytics tradicional

Debido a que la arquitectura de Adobe Experience Platform es diferente a un grupo de informes tradicional de Analytics, no se garantiza que los resultados coincidan. Sin embargo, puede utilizar las siguientes sugerencias para facilitar esta comparación:

* Compruebe que las diferencias arquitectónicas enumeradas anteriormente no afectan a la comparación. Esto incluye eliminar canales que no anulan el canal de último toque y eliminar los criterios de regla que son la primera visita individual de una visita (sesión).
* Doble compruebe que su conexión utiliza el mismo grupo de informes que Analytics tradicional. Si la conexión CJA contiene varios grupos de informes con sus propias reglas de procesamiento de Marketing canal, no hay una manera fácil de compararla con Analytics tradicional. Desea crear una conexión independiente para cada grupo de informes a fin de comparar los datos.
* Asegúrese de comparar los mismos intervalos de fechas y de que la configuración del huso horario de la vista de datos sea la misma que la del grupo de informes.
* Utilice un modelo de atribución personalizado cuando visualice los datos del grupo de informes. Por ejemplo, utilice la dimensión [canal de mercadotecnia](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) con métricas que utilicen un modelo de atribución no predeterminado. Adobe aconseja no comparar las dimensiones predeterminadas [canal de primer toque](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) o [canal de último toque](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html), porque dependen de la atribución recopilada en el grupo de informes. CJA no se basa en los datos de atribución de un grupo de informes; en su lugar, se calcula cuando se ejecuta un informe CJA.
* Algunas métricas no tienen una comparación razonable debido a las diferencias de arquitectura entre los datos del grupo de informes y los datos de la plataforma. Algunos ejemplos son visitas/sesiones, visitantes/personas y ocurrencias/eventos.
