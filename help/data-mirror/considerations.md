---
title: Consideraciones de Data Mirror
description: Tenga en cuenta consideraciones adicionales a la hora de sincronizar datos entre las soluciones nativas de Data Warehouse y Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 888
ht-degree: 1%

---

# Consideraciones de Experience Platform Data Mirror

Este artículo describe los factores que debe tener en cuenta al configurar conjuntos de datos de Data Mirror.

## Nueva columna en la tabla de origen

Cuando se agrega una nueva columna a una tabla de origen en un conjunto de datos reflejado de datos habilitado para CDC, ese cambio puede almacenar en déclencheur las actualizaciones de todas las filas existentes. Estas actualizaciones se procesan como cambios a través de los CDC, que:

* Puede comportarse como una reescritura de tabla completa desde una perspectiva en curso.
* Puede aumentar drásticamente el volumen de ingesta, lo que podría hacer que la actualización exceda sus derechos de ingesta.

La estrategia recomendada para las columnas de la tabla de origen:

* Asegúrese de que todas las columnas relevantes se hayan definido inicialmente.
* Asigne cada columna que pueda pensar que necesita inicialmente.

Si desea agregar una columna nueva, existen dos opciones, en función de si se requiere relleno retroactivo:

* Relleno retroactivo:

   * Elimine el conjunto de datos actual.
   * Vuelva a configurar el conector con la columna actualizada.

  Esto garantiza que los datos se rellenen de forma más eficiente y oportuna.

* Sin relleno retroactivo:

   * Agregue la columna en la tabla de origen.
   * Añada la columna en el esquema del conjunto de datos de destinatario.
   * Actualice la asignación para incluir el nuevo campo (columna) de la tabla de origen al conjunto de datos de destino.

Esta estrategia:

* Evita una costosa evolución del esquema más adelante (actualizaciones masivas al añadir columnas).
* Mantiene el volumen de cambios más predecible que cuando se agregan o modifican columnas más adelante.
* Ayuda a limitar los posibles costes de cálculo en la base de datos externa, ya que el Data Warehouse podría interpretar la nueva columna como una actualización de todas las filas.


## Privacy Service

Las solicitudes de privacidad deben producirse del mismo modo en que se gestionan hoy las solicitudes de privacidad para esquemas no relacionales, ya que las solicitudes de privacidad son indiferentes a cómo se estructuran los datos.

Los datos reflejados desde un esquema relacional externo forman parte del ecosistema de Adobe y se pueden compartir en todo el ecosistema, por ejemplo, mediante la publicación de audiencias de Customer Journey Analytics. El envío de una solicitud de privacidad garantiza que las identidades y los datos asociados se gestionen correctamente en todo el ecosistema de Adobe.

Por lo tanto, las solicitudes de privacidad no deben limitarse al conjunto de datos reflejado, sino que también deben implicar actualizaciones de los datos de origen en la base de datos externa.

## Comportamiento de higiene

El servicio de higiene funciona con *identidades principales*, pero las tablas de la base de datos externa que se reflejan tienen *claves principales*, no identidades principales.

Las consecuencias de la diferencia entre identidades principales y claves principales son que las eliminaciones de higiene no se pueden ejecutar directamente en estas tablas relacionales. Como resultado, debe:

* Elimine datos en sus propias tablas de origen dentro de la solución de almacén de datos y asegúrese de que las operaciones de eliminación fluyen a través de CDC (o la columna de cambio manual).
* Envíe solicitudes de higiene y privacidad a Adobe para cualquier conjunto de datos basado en XDM descendente con información de identidad (por ejemplo: vistas de Customer Journey Analytics, conjuntos de datos de Real-Time Customer Data Platform, conjuntos de datos específicos de Adobe Journey Optimizer y más).

La diferencia entre la identidad principal y la clave principal introduce un modelo de responsabilidad compartida:

* Adobe procesa la higiene donde hay identidades presentes.
* Usted, como cliente, es responsable de alinear sus propios procesos de higiene en la base de datos de origen con las solicitudes de higiene enviadas a Adobe.

## Diferencias de gobernanza

En XDM [schemas](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/composition) y conceptos subyacentes como [grupos de campos](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), un [campo](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) definido dentro de un grupo de campos propaga sus etiquetas en todos los conjuntos de datos donde se utiliza el grupo de campos. Por ejemplo, un campo de correo electrónico `emailID` en un grupo de campos `identities`, está etiquetado como el mismo en todos los conjuntos de datos donde se utiliza el grupo de campos `identities`.

En un esquema relacional, un nombre de columna es independiente. Una columna denominada `email` de la tabla `customers` es independiente y distinta de una columna denominada `email` de la tabla `prospects`. Este comportamiento implica que las etiquetas (como las etiquetas de uso DULE y las políticas) deben aplicarse individualmente a los campos de los conjuntos de datos reflejados. En función del ejemplo anterior, debe aplicar etiquetas tanto al campo `email` del conjunto de datos `customers` como al campo `email` del conjunto de datos `prospects`.

La diferencia de gobernanza tiene el siguiente impacto:

* Un control y una configuración más manuales funcionan para usted como cliente.
* Puede necesitar una guía explícita, por lo que no supone que el etiquetado único a través de grupos de campos sea suficiente para un control adecuado.

## Unión

Los esquemas relacionales tienen las siguientes consideraciones en relación con la vinculación:

* Se admite parcialmente la vinculación basada en gráficos. No se pueden habilitar los esquemas relacionales para el perfil o la contribución al gráfico.
* La vinculación basada en el campo es totalmente compatible.


## Campos y claves del sistema

Las siguientes consideraciones se aplican a las claves y los campos del sistema:

* La clave principal, el descriptor de versión y el descriptor de marca de tiempo deben ser campos de nivel raíz en el esquema XDM relacional. Use [asignación de campos](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) durante la ingesta para admitir este requisito.
* Puede omitir los campos de origen apropiados durante la [fase de asignación](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema).

## Tamaño del lote de datos reflejados

Para cualquier conjunto de datos reflejado que esté configurado como parte de una conexión, debe asegurarse de que cada uno de los lotes para introducir datos para el conjunto de datos reflejado no supere los 100 GB. Consulte las [protecciones para la ingesta por lotes](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/guardrails#guardrails-for-batch-ingestion){target="_blank"} para obtener más información.
