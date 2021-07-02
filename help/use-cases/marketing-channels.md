---
title: Uso de dimensiones de canal de marketing en Adobe Experience Platform
description: Utilice el conector de datos de Analytics para incorporar reglas de procesamiento de canal de marketing a Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: ht
source-wordcount: '920'
ht-degree: 100%

---

# Uso de dimensiones de canal de marketing en Adobe Experience Platform

Si su organización utiliza el [conector de datos de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es) para llevar los datos del grupo de informes a CJA, puede configurar una conexión en CJA para informar sobre las dimensiones de canal de marketing.

## Requisitos previos

* Los datos del grupo de informes ya deben estar importados en Adobe Experience Platform mediante el [conector de datos de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). No se admiten otras fuentes de datos, ya que los canales de marketing dependen de las reglas de procesamiento de un grupo de informes de Analytics.
* Las reglas de procesamiento de canal de marketing ya deben estar configuradas. Consulte [Reglas de procesamiento para canales de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=es) en la guía tradicional de componentes de Analytics.

## Elementos de esquema de canal de marketing

Una vez que haya establecido el conector de datos de Analytics en un grupo de informes deseado, se creará para usted un esquema XDM. Este esquema contiene todas las dimensiones y métricas de Analytics como datos sin procesar. Estos datos sin procesar no contienen atribución ni persistencia. En su lugar, cada evento se ejecuta mediante reglas de procesamiento de canal de marketing y registra la primera regla que coincide. Especifique la atribución y la persistencia al crear una vista de datos en CJA.

1. [Cree una conexión](/help/connections/create-connection.md) que incluya un conjunto de datos basado en el conector de datos de Analytics.
2. [Cree una vista de datos](/help/data-views/create-dataview.md) que incluya las siguientes dimensiones:
   * **`channel.typeAtSource`**: equivalente a la dimensión [Canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=es-ES).
   * **`channel._id`**: equivalente a los [Detalles de canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=es)
3. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Si desea dimensiones de primer toque y de último toque, arrastre cada dimensión de canal de marketing al área de componentes varias veces. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Adobe también recomienda asignar a cada dimensión un nombre para mostrar para facilitar su uso en Workspace.
4. Cree la vista de datos.

Sus dimensiones de canal de marketing ya están disponibles para su uso en Analysis Workspace.

## Diferencias de procesamiento y arquitectura

>[!IMPORTANT]
>
>Existen varias diferencias fundamentales entre los datos del grupo de informes y los datos de Platform. Adobe recomienda encarecidamente ajustar las reglas de procesamiento de canales de marketing del grupo de informes para facilitar una recopilación de datos adecuada en Platform.

La configuración del canal de marketing funciona de forma diferente entre los datos de Platform y los datos del grupo de informes. Tenga en cuenta las siguientes diferencias al configurar canales de marketing para CJA:

* **Es la primera página de la visita**: este criterio de regla es común en varias definiciones predeterminadas de canales de marketing. Cualquier regla de procesamiento que contenga este criterio se ignora en Platform (se seguirán aplicando otros criterios de la misma regla). Las sesiones se determinan en el momento de la consulta de datos en lugar de en el momento de la recopilación de datos, lo que impide que Platform use estos criterios específicos de regla. Adobe recomienda eliminar el criterio &quot;Es la primera página de la visita&quot; de cada regla de procesamiento de canal de marketing.

   ![Es la primera página de la visita](assets/first-page-of-visit.png)

* **Anular canal de último contacto**: esta configuración del Administrador de canal de marketing normalmente impide que determinados canales obtengan crédito de canal de último contacto. Platform ignora esta configuración, lo que permite que canales generales como Directo o Interno atribuyan métricas de formas potencialmente no deseadas. Adobe recomienda eliminar canales en los que tenga la opción Anular canal de último contacto desactivada.
   * Puede eliminar el canal de marketing Directo en el Administrador de canal de marketing y, a continuación, basarse en el elemento de dimensión Sin valor de CJA para ese canal. También puede cambiar el nombre de este elemento de dimensión a Directo o excluir por completo el elemento de dimensión al configurar una vista de datos.
   * De forma alternativa, puede crear una clasificación de canal de marketing, que clasifica cada valor en sí mismo excepto para los canales que desee excluir en CJA. A continuación, puede utilizar esta dimensión de clasificación al crear una vista de datos en lugar de `channel.typeAtSource`.

   ![Anular canal de último toque](assets/override-last-touch-channel.png)

* **Caducidad de canal de marketing**: esta configuración del período de participación determina el período de inactividad antes de que un visitante pueda obtener un nuevo canal de primer contacto en los datos del grupo de informes. Platform utiliza su propia configuración de atribución, por lo que esta configuración se ignora por completo en CJA.

   ![Caducidad del canal de marketing](assets/marketing-channel-expiration.png)

## Comparación de datos entre CJA y Analytics tradicional

Debido a que la arquitectura de Adobe Experience Platform es diferente a un grupo de informes tradicional de Analytics, no se garantiza que los resultados coincidan. Sin embargo, puede utilizar las siguientes sugerencias para facilitar esta comparación:

* Compruebe que las diferencias arquitectónicas enumeradas anteriormente no afectan a la comparación. Esto incluye eliminar canales que no anulan el canal de último contacto, así como eliminar los criterios de regla que son el primer resultado de una visita (sesión).
* Asegúrese de que su conexión utiliza el mismo grupo de informes que Analytics tradicional. Si la conexión de CJA contiene varios grupos de informes con sus propias reglas de procesamiento de canal de marketing, no hay una manera fácil de compararla con Analytics tradicional. Desea crear una conexión independiente para cada grupo de informes con el fin de comparar los datos.
* Asegúrese de comparar los mismos intervalos de fechas y de que la configuración de la zona horaria de su vista de datos sea la misma que la del grupo de informes.
* Utilice un modelo de atribución personalizado cuando visualice los datos del grupo de informes. Por ejemplo, utilice la dimensión [Canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=es-ES) con métricas que utilicen un modelo de atribución no predeterminado. Adobe aconseja no comparar las dimensiones predeterminadas [Canal de primer contacto](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=es-ES) o [Canal de último contacto](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=es-ES), porque dependen de la atribución recopilada en el grupo de informes. CJA no se basa en los datos de atribución de un grupo de informes; en su lugar, se calcula cuando se ejecuta un informe de CJA.
* Algunas métricas no tienen una comparación razonable debido a las diferencias de arquitectura entre los datos del grupo de informes y los datos de Platform. Algunos ejemplos son visitas/sesiones, visitantes/personas y ocurrencias/eventos.
