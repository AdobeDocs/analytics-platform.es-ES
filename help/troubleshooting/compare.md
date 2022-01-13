---
title: Comparar los datos de AA con los datos de CJA
description: Obtenga información sobre cómo comparar sus datos de Adobe Analytics con los de Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: d970539d19fad6f274245dcc7bac6b3f13e7b7a2
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 4%

---

# Comparar los datos de Adobe Analytics con los datos de CJA

A medida que su organización adopta CJA, es posible que observe algunas diferencias en los datos entre Adobe Analytics y CJA. Esto es normal y puede ocurrir por varios motivos. CJA está diseñado para permitirle mejorar algunas de las limitaciones de sus datos en AA. Sin embargo, pueden producirse discrepancias inesperadas/no deseadas. Este artículo está diseñado para ayudarle a diagnosticar y resolver esas diferencias, de modo que usted y su equipo puedan utilizar CJA sin impedimentos por motivos de integridad de los datos.

Supongamos que ha ingerido datos de Adobe Analytics en AEP a través del conector de origen de Analytics y, a continuación, ha creado una conexión de CJA utilizando este conjunto de datos.

![flujo de datos](assets/compare.png)

A continuación, creó una vista de datos y, mientras informaba posteriormente de estos datos en CJA, observó discrepancias con los resultados de los informes en Adobe Analytics.

A continuación se indican algunos pasos a seguir para comparar los datos originales de Adobe Analytics con los datos de Adobe Analytics que ahora están en Customer Journey Analytics.

## Requisitos previos

* Asegúrese de que el conjunto de datos de Analytics en AEP contenga datos para el intervalo de fechas que está investigando.

* Asegúrese de que el grupo de informes seleccionado en Analytics coincide con el grupo de informes introducido en Adobe Experience Platform.

## Paso 1: Ejecute la métrica Ocurrencias en Adobe Analytics

La variable [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/ocurrences.html?lang=es) muestra el número de visitas en las que se estableció o persistió una dimensión determinada.

1. En Analytics > [!UICONTROL Espacio de trabajo], arrastre el intervalo de fechas sobre el que desee crear el informe como dimensión a una [!UICONTROL Forma libre] tabla.

1. La variable [!UICONTROL Ocurrencias] se aplica automáticamente a ese intervalo de fechas.

1. Guarde este proyecto para que pueda utilizarlo en la comparación.

## Paso 2: Comparar los resultados con [!UICONTROL Total de registros por marcas de hora] en CJA

Ahora compare el [!UICONTROL Ocurrencias] en Analytics para el total de registros por marcas de hora en Customer Journey Analytics.

Los registros totales por marcas de hora deben coincidir con Ocurrencias, siempre que el conector de origen de Analytics no haya caído ningún registro; consulte la sección siguiente.

>[!NOTE]
>
>Esto solo funciona para conjuntos de datos de valores medios normales, no para conjuntos de datos (a través de [Análisis en canales múltiples](/help/connections/cca/overview.md)). Tenga en cuenta que la contabilidad del ID de persona que se utiliza en CJA es crítica para hacer que la comparación funcione. Puede que no siempre sea fácil replicarlo en AA, especialmente si se ha activado el análisis en todos los canales.

1. En Adobe Experience Platform [Servicios de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html), ejecute lo siguiente [!UICONTROL Registros totales por marcas de hora] consulta:

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. En [Fuentes de datos de Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es), identifique, a partir de los datos sin procesar, si el conector de origen de Analytics puede haber soltado algunas filas.

   La variable [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) podría soltar filas durante la transformación al esquema XDM. Puede haber varias razones para que toda la fila no sea apta para la transformación. Si alguno de los campos de Analytics siguientes tiene estos valores, se perderá toda la fila.

   | Campo de Analytics | Valores que hacen que se borre |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | No 0 |
   | Exclude_hit | No 0 |
   | Bot_id | No 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53,63 |

1. Si el conector suelta filas, reste esas filas del [!UICONTROL Ocurrencias] métrica. El número resultante debe coincidir con el número de eventos de los conjuntos de datos de Adobe Experience Platform.

## Por qué se pueden perder o omitir registros durante la ingesta desde AEP

CJA [Conexiones](/help/connections/create-connection.md) le permite unir varios conjuntos de datos en función de un ID de persona común en todos los conjuntos de datos. En el servidor, se aplica la deduplicación: unión externa completa o unión en conjuntos de datos de evento basados en marcas de tiempo y, a continuación, unión interna en el perfil y el conjunto de datos de búsqueda, según el ID de persona.

A continuación se indican algunas de las razones por las que se pueden omitir registros al ingerir datos de AEP.

* **Marcas de hora que faltan** - Si faltan marcas de hora en los conjuntos de datos de evento, esos registros se ignorarán o omitirán por completo durante la ingesta.

* **ID de persona que faltan** : los ID de persona que faltan (del conjunto de datos de eventos o del perfil o conjunto de datos de búsqueda) hacen que esos registros se ignoren o se omitan. El motivo es que no hay ID comunes ni claves coincidentes para unirse a los registros.

* **ID de persona grande o no válida** : con ID no válidos, el sistema no puede encontrar un ID común válido entre los conjuntos de datos para unirse. En algunos casos, la columna ID de persona tiene ID de persona no válidos, como &quot;indefinido&quot; o &quot;0000000&quot;. Un ID de persona (con cualquier combinación de números y letras) que aparezca en un evento más de 1 millón de veces al mes no se puede atribuir a ningún usuario o persona en particular. Se clasificará como no válido. Estos registros no se pueden ingerir en el sistema y generar informes e ingesta propensos a errores.
