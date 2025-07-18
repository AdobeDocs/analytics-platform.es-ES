---
title: Uso de dimensiones de canal de marketing
description: Aprenda a utilizar el conector de origen de Analytics para incorporar reglas de procesamiento del canal de marketing a Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 49%

---

# Uso de dimensiones del canal de marketing

Si su organización utiliza el [conector de origen de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics) para llevar los datos del grupo de informes a Customer Journey Analytics, puede configurar una conexión en Customer Journey Analytics para informar sobre las dimensiones del canal de marketing.

>[!IMPORTANT]
>
>Consulte los [Campos derivados - Plantilla de canales de mercadotecnia](/help/data-views/derived-fields/derived-fields.md#marketing-channels) para obtener funcionalidad de producto nativa para informar sobre dimensiones de canal de mercadotecnia.
>


## Requisitos previos

* Los datos del grupo de informes ya deben estar importados en Adobe Experience Platform usando el [conector de origen de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics). No se admiten otras fuentes de datos, ya que los canales de marketing dependen de las reglas de procesamiento de un grupo de informes de Analytics.
* Las reglas de procesamiento de canal de marketing ya deben estar configuradas. Consulte [Reglas de procesamiento para canales de marketing](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) en la guía Componentes de Adobe Analytics.

## Elementos de esquema de canal de marketing

Una vez que haya establecido el conector de origen de Analytics en un grupo de informes deseado, se creará un esquema XDM. Este esquema contiene todas las dimensiones y métricas de Analytics como datos sin procesar. Estos datos sin procesar no contienen atribución ni persistencia. En su lugar, cada evento se ejecuta mediante reglas de procesamiento de canal de marketing y registra la primera regla que coincide. La atribución y la persistencia se especifican al crear una vista de datos en Customer Journey Analytics.

1. [Cree una conexión](/help/connections/create-connection.md) que incluya un conjunto de datos basado en el conector de origen de Analytics.
2. [Cree una vista de datos](/help/data-views/create-dataview.md) que incluya las siguientes dimensiones:
   * **`channel.typeAtSource`**: equivalente a la dimensión [Canal de marketing](https://experienceleague.adobe.com/es/docs/analytics/components/dimensions/marketing-channel).
   * **`channel._id`**: equivalente a los [Detalles de canal de marketing](https://experienceleague.adobe.com/es/docs/analytics/components/dimensions/marketing-detail)
3. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Si desea dimensiones de primer toque y de último toque, arrastre cada dimensión de canal de marketing al área de componentes varias veces. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Adobe también recomienda asignar a cada dimensión un nombre para mostrar para facilitar su uso el Espacio de trabajo.
4. Cree la vista de datos.

Sus dimensiones de canal de marketing ya están disponibles para su uso en Analysis Workspace.

>[!NOTE]
>
> El conector de origen de Analytics requiere que se rellenen `channel.typeAtSource` (canal de marketing) y `channel._id` (detalle del canal de marketing). De lo contrario, ninguno de los dos se transferirá a ExperienceEvent en XDM. Un detalle de canal de mercadotecnia en blanco en el grupo de informes de origen genera un `channel._id` en blanco y el conector de origen de Analytics también dejará en blanco a `channel.typeAtSource`. Estos espacios en blanco pueden provocar diferencias en los informes entre Adobe Analytics y Customer Journey Analytics.

## Diferencias de procesamiento y arquitectura

>[!IMPORTANT]
>
>Existen varias diferencias fundamentales entre los datos del grupo de informes y los datos de Platform. Adobe recomienda encarecidamente ajustar las reglas de procesamiento de canales de marketing del grupo de informes para facilitar una recopilación de datos adecuada en Experience Platform.

>[!NOTE]
>
>Para maximizar la efectividad de los canales de marketing para Attribution y Customer Journey Analytics, hay disponibles [prácticas recomendadas revisadas](https://experienceleague.adobe.com/es/docs/analytics/components/marketing-channels/mchannel-best-practices).

La configuración del canal de marketing funciona de forma diferente entre los datos de Platform y los datos del grupo de informes. Tenga en cuenta las siguientes diferencias al configurar canales de marketing para Customer Journey Analytics:

* **Es la primera página de la visita**: este criterio de regla es común en varias definiciones predeterminadas de canales de marketing. Cualquier regla de procesamiento que contenga este criterio se ignora en Platform (se seguirán aplicando otros criterios de la misma regla). Las sesiones se determinan en el momento de la consulta de datos en lugar de en el momento de la recopilación de datos, lo que impide que Platform use estos criterios específicos de regla. Adobe recomienda volver a evaluar cualquier regla de procesamiento de canal de marketing que contenga el criterio “Es la primera página de la visita”, optando por enfoques alternativos que logren sus objetivos.

  ![Es la primera página de la visita](../assets/first-page-of-visit.png)

* **Anular canal de último contacto**: esta configuración del Administrador de canal de marketing normalmente impide que determinados canales obtengan crédito de canal de último contacto. Platform ignora esta configuración, lo que permite que canales generales como Directo o Interno atribuyan métricas de formas potencialmente no deseadas. Adobe recomienda eliminar canales en los que tenga la opción Anular canal de último contacto desactivada.
   * Puede eliminar el canal de marketing Directo en el Administrador de canales de marketing y, a continuación, basarse en el elemento de dimensión Sin valor de Customer Journey Analytics para ese canal. También puede cambiar el nombre de este elemento de dimensión a Directo o excluir por completo el elemento de dimensión al configurar una vista de datos.
   * También puede crear una clasificación de canal de marketing que clasifique cada valor en sí mismo excepto para los canales que desee excluir en Customer Journey Analytics. A continuación, puede utilizar esta dimensión de clasificación al crear una vista de datos en lugar de `channel.typeAtSource`.

  ![Anular canal de último toque](../assets/override-last-touch-channel.png)

* **Caducidad de canal de mercadotecnia**: esta configuración del período de participación determina el período de inactividad antes de que una persona pueda obtener un nuevo canal de primer contacto en los datos del grupo de informes. Platform utiliza su propia configuración de atribución, por lo que esta configuración se ignora por completo en Customer Journey Analytics.

  ![Caducidad del canal de marketing](../assets/marketing-channel-expiration.png)

## Comparación de datos entre Customer Journey Analytics y Adobe Analytics

Como la arquitectura de Adobe Experience Platform es diferente a un grupo de informes de Adobe Analytics, no se garantiza que los resultados coincidan. Sin embargo, puede utilizar las siguientes sugerencias para facilitar esta comparación:

* Compruebe que las diferencias arquitectónicas enumeradas anteriormente no afectan a la comparación. Estas diferencias incluyen la eliminación de canales que no anulan el canal de último contacto y la eliminación de los criterios de regla que son el primer resultado de una visita (sesión).
* Compruebe que su conexión utiliza el mismo grupo de informes que Adobe Analytics. Si la conexión de Customer Journey Analytics contiene varios grupos de informes con sus propias reglas de procesamiento de canal de marketing, no hay una manera fácil de compararla con Adobe Analytics. Desea crear una conexión independiente para cada grupo de informes con el fin de comparar los datos.
* Asegúrese de comparar los mismos intervalos de fechas y de que la configuración de la zona horaria de su vista de datos sea la misma que la del grupo de informes.
* Utilice un modelo de atribución personalizado cuando visualice los datos del grupo de informes. Por ejemplo, utilice la dimensión [Canal de marketing](https://experienceleague.adobe.com/es/docs/analytics/components/dimensions/marketing-channel) con métricas que utilicen un modelo de atribución no predeterminado. Adobe aconseja no comparar las dimensiones predeterminadas [Canal de primer contacto](https://experienceleague.adobe.com/es/docs/analytics/components/dimensions/first-touch-channel) o [Canal de último contacto](https://experienceleague.adobe.com/es/docs/analytics/components/dimensions/last-touch-channel), porque dependen de la atribución recopilada en el grupo de informes. Customer Journey Analytics no se basa en los datos de atribución de un grupo de informes sino que se calcula cuando se ejecuta un informe de Customer Journey Analytics.
* Algunas métricas no tienen una comparación razonable debido a las diferencias de arquitectura entre los datos del grupo de informes y los datos de Platform. Algunos ejemplos son visitas/sesiones, personas/personas y ocurrencias/eventos.
