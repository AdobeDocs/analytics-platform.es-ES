---
title: Consideraciones de Data Mirror
description: Tenga en cuenta consideraciones adicionales a la hora de sincronizar datos entre las soluciones nativas de Data Warehouse y Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 93f38f57021bf66cacd700ce6fbc46338fd6a034
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Consideraciones de Experience Platform Data Mirror

Este artículo describe los factores que debe tener en cuenta al configurar conjuntos de datos de Data Mirror.

## Nueva columna en la tabla de origen

Cuando se agrega una nueva columna a una tabla de origen en un conjunto de datos reflejado de datos habilitado para CDC, ese cambio puede almacenar en déclencheur las actualizaciones de todas las filas existentes. Estas actualizaciones se procesan como cambios a través de los CDC, que:

* Puede comportarse como una reescritura de tabla completa desde una perspectiva de coste.
* Puede aumentar drásticamente el volumen de ingesta, especialmente con cualquier precio futuro de *multiplicador de cambio* (por ejemplo, las operaciones de combinación podrían cobrarse a tarifas más altas).

La estrategia recomendada para las columnas de la tabla de origen:

* Asegúrese de que la mayoría de las columnas relevantes, si no todas, se definan inicialmente.
* Asigne cada columna que pueda pensar que necesita inicialmente.

Esta estrategia:

* Evita una costosa evolución del esquema más adelante (actualizaciones masivas al añadir columnas).
* Mantiene el volumen de cambios más predecible que cuando se agregan o modifican columnas más adelante.
* Podría incurrir en algunos costes de cálculo adicionales en el lado de la base de datos externa, ya que el Data Warehouse podría interpretar todas las columnas como actualizaciones.

Para gestionar nuevas columnas en tablas externas del Data Warehouse, siga estos pasos:

1. Cree un nuevo esquema con la columna añadida.
1. Configure un nuevo conector de origen que incorpore los datos.
1. Cargue el relleno correctamente.
1. Utilice los cambios de CDC a partir de ahora.

Este enfoque minimiza el impacto en ambas partes.

## Privacy Service

Las solicitudes de privacidad deben producirse del mismo modo en que se gestionan hoy las solicitudes de privacidad para esquemas no relacionales, ya que las solicitudes de privacidad son indiferentes a cómo se estructuran los datos.

Los datos reflejados en un conjunto de datos a partir de datos externos basados en un esquema relacional pasan a formar parte del ecosistema de Adobe y se pueden compartir de muchas maneras. Por ejemplo, mediante la publicación de audiencias.

Por lo tanto, las solicitudes de privacidad no deben limitarse al conjunto de datos reflejado, sino que también deben implicar actualizaciones de los datos de origen en la base de datos externa.

## Comportamiento de higiene

El servicio de higiene funciona con *identidades principales*, pero las tablas de la base de datos externa que se reflejan tienen *claves principales*, no identidades principales.

Las consecuencias de la diferencia entre identidades principales y claves principales son que las eliminaciones de higiene no se pueden ejecutar directamente en estas tablas relacionales. Como resultado, debe:

* Elimine datos en sus propias tablas de origen dentro de la solución de almacén de datos y asegúrese de que las operaciones de eliminación fluyen a través de CDC (o la columna de cambio manual).
* Envíe solicitudes de higiene y privacidad a Adobe para cualquier conjunto de datos basado en XDM descendente con información de identidad (por ejemplo: vistas de Customer Journey Analytics, conjuntos de datos de Real-Time Customer Data Platform, conjuntos de datos específicos de Adobe Journey Optimizer y más).

La diferencia entre la identidad principal y la clave principal introduce un modelo de responsabilidad compartida:

* Adobe procesa la higiene donde hay identidades presentes.
* Usted, como cliente, es responsable de alinear sus propios procesos de higiene en la base de datos de origen con las solicitudes de higiene que se envían a Adobe.

## Diferencias de gobernanza

En XDM [schemas](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/composition) y conceptos subyacentes como [grupos de campos](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), un [campo](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) definido dentro de un grupo de campos propaga sus etiquetas en todos los conjuntos de datos donde se utiliza el grupo de campos. Por ejemplo, un campo de correo electrónico `emailID` en un grupo de campos `identities`, está etiquetado como el mismo en todos los conjuntos de datos donde se utiliza el grupo de campos `identities`.

En un esquema relacional, un nombre de columna es independiente. Una columna denominada `email` de la tabla `customers` es independiente y distinta de una columna denominada `email` de la tabla `prospects`. Este comportamiento implica que las etiquetas (como las etiquetas de uso DULE y las políticas) deben aplicarse individualmente a los campos de los conjuntos de datos reflejados. En función del ejemplo anterior, debe aplicar etiquetas tanto al campo `email` del conjunto de datos `customers` como al campo `email` del conjunto de datos `prospects`.

La diferencia de gobernanza tiene el siguiente impacto:

* Un control y una configuración más manuales funcionan para usted como cliente.
* Puede necesitar una guía explícita, por lo que no supone que el etiquetado único a través de grupos de campos sea suficiente para un control adecuado.
