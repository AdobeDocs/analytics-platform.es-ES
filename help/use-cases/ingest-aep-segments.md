---
title: Ingesta de audiencias de AEP en Customer Journey Analytics
description: Explica cómo incorporar audiencias de AEP a Customer Journey Analytics para un análisis más detallado.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: ed01fd0899cac21fff156e0c31dc2b52ff7c8cca
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 2%

---


# Ingesta de audiencias de AEP en Customer Journey Analytics (CJA)

>[!NOTE]
>
>Este tema está en construcción.

(Brandon, fyi, &quot;Perfil unificado&quot; es un término obsoleto para &quot;Perfil del cliente en tiempo real&quot;, según el administrador de documentos de AEP. No encontrará ningún documento en UP en el conjunto de documentos de AEP).

Este caso de uso explora una forma provisional y manual de incorporar audiencias de Adobe Experience Platform (AEP) a CJA. Es posible que estas audiencias se hayan creado en el Generador de segmentos de AEP, Adobe Audience Manager u otras herramientas, y se almacenen en el Perfil del cliente en tiempo real (RTCP). Las audiencias constan de listas de ID de persona, ID de perfil, etc. y queremos incluirlos en CJA Workspace para su análisis.

## Requisitos previos

* Acceso a Adobe Experience Platform (AEP), específicamente Perfil del cliente en tiempo real.
* Acceso al Customer Journey Analytics
* ¿Capacidad para escribir código personalizado?
* Qué más.

## Paso 1: Elija la audiencia en el perfil del cliente en tiempo real {#audience}

Adobe Experience Platform [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) (RTCP) le permite ver una vista holística de cada cliente individual combinando datos de varios canales, incluidos en línea, sin conexión, CRM y de terceros. Es probable que ya tenga audiencias en RTCP que puedan provenir de varias fuentes. Elija una o más audiencias.

## Paso 2: Creación de un conjunto de datos de unión de perfiles para la exportación

Para exportar la audiencia a un conjunto de datos que luego pueda establecer una conexión con CJA, debe crear un conjunto de datos cuyo esquema sea un perfil [Esquema de unión](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Los esquemas de unión están compuestos por varios esquemas que comparten la misma clase y que se han habilitado para Perfil. El esquema de unión permite ver una amalgamación de todos los campos contenidos en esquemas que comparten la misma clase. El perfil del cliente en tiempo real utiliza el esquema de unión para crear una vista holística de cada cliente individual.

## Paso 3: Exportación de una audiencia a un conjunto de datos mediante una llamada de API {#export}

Para poder introducir una audiencia en CJA, debe exportarla a un conjunto de datos en AEP. Esto solo se puede hacer con la API de segmentación y, específicamente, con la variable [Exportar extremo de API de trabajos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Puede crear un trabajo de exportación y poner los resultados en el conjunto de datos de AEP de unión de perfiles que creó en el paso 2.

## Paso 4: Editar la salida de exportación

Al crear el trabajo de exportación para una audiencia, solo necesitamos el ID de persona y el ID de audiencia para realizar el informe en CJA. Sin embargo, el trabajo de exportación estándar contiene más datos y, por lo tanto, es necesario editar este resultado para eliminar datos superfluos.

A continuación, se muestra un ejemplo de la salida de exportación en el conjunto de datos de unión de perfiles , **before** cualquier edición:

![Salida sin editar](assets/export-unedited.png)

Recuerde lo siguiente:

* El ID de audiencia se encuentra en `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* El estado debe ser &quot;realizado&quot; o &quot;introducido&quot;, pero no &quot;salido&quot;. Sustituya &quot;salir&quot; por &quot;en blanco&quot;.

Este es el formato del conjunto de datos de perfil que puede enviar a CJA.

![Salida editada](assets/export-edited.png)

Estos son los elementos de datos que deben estar presentes:

* `_aresprodvalidation`: Hace referencia a su ID de organización. El tuyo será diferente.
* `personID`: En este caso, un nombre descriptivo
* `audienceMembershipIdList` campo de cadena: El ID de audiencia
* Añada un nombre descriptivo para la audiencia (`audienceMembershipIdName`), como

   ![Nombre descriptivo de la audiencia](assets/audience-name.png)

## Paso 5: Crear una conexión en CJA con este conjunto de datos de perfil

[Crear una conexión](/help/connections/create-connection.md)

## Paso 6: Crear una vista de datos

Agregar `audienceMembershipIdName` y `personID` a la vista de datos.

## Paso 7: Informes en Workspace

Ahora puede informar sobre `audienceMembershipIdName` y `personID` en Workspace.
La captura de pantalla sería buena.

Para ello:

escriba más pasos para cuando esté tratando con personas que son miembros de varias audiencias.




