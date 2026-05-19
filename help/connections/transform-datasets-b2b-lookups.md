---
title: Transformar Conjuntos De Datos Para Búsquedas B2B
description: Describe cómo transformar datos en conjuntos de datos de esquemas de búsqueda B2B específicos
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
autotag-review: '2026-05-19T08:48:44.273Z'
TQID: 'https://experienceleague.adobe.com/hE-nAiD8K4lHdZkC2YJpqpqfh2d3CY6tq4KiTJjEXs0'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: cf731116-8803-4027-85aa-9c0a126e8321
  - id: e0cfe18a-f68c-495b-bafc-f6bcc0392d6c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 9%

---

# Transformar el conjunto de datos para búsquedas B2B

Para admitir búsquedas basadas en personas en datos B2B (incluidas cuentas, oportunidades, listas de marketing y campañas), la transformación de los conjuntos de datos de búsqueda B2B puede mejorar la precisión de los datos.

Esta transformación solo está disponible para conjuntos de datos con datos para esquemas de búsqueda B2B, según las siguientes clases:

* [Relación de persona de cuenta empresarial de XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [Relación de persona de oportunidad empresarial de XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [Miembros de lista de marketing empresarial de XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [Miembros de campaña empresarial de XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>Hay un límite de no más de 10 000 elementos por cada ID. Esta limitación implica que para cualquier ID de persona solo puede tener 10 000 cuentas, 10 000 oportunidades, 10 000 listas de marketing o 10 000 campañas.

>[!PREREQUISITES]
>
>Para que la ingesta funcione correctamente, debe validar que los conjuntos de datos de búsqueda B2B tengan datos rellenados para los siguientes campos (tal como se definen en los esquemas de búsqueda B2B):
>
>| Conjunto de datos que contiene datos que se ajustan al esquema | Campo rellenado con datos |
>|---|---|
>| Relación de persona de cuenta empresarial de XDM | `accountPersonID` |
>| Persona de oportunidad empresarial de XDM | `opportunityPersonID` |
>| Lista de marketing empresarial de XDM | `marketingListMemberID` |
>| Miembros de campaña empresarial de XDM | `campaign.sourceKey` |
>

Para habilitar la transformación para un conjunto de datos de búsqueda B2B:

![Habilitar conjunto de datos de transformación](/help/connections/assets/transform.gif)

* Compruebe para cada conjunto de datos los valores sugeridos para **[!UICONTROL Key]** y **[!UICONTROL Matching key]**. Si cambia los valores de los valores sugeridos, verá una advertencia que le pedirá que continúe. Debe estar seguro de que:

   * El valor que seleccionó para **Clave** se basa en el tipo de datos de ID de persona.
   * El valor que seleccione para **Clave de coincidencia** se define como el campo de identidad principal para el conjunto de datos de evento.

* Seleccione las opciones para importar nuevos datos y el relleno del conjunto de datos.

* Seleccione **[!UICONTROL Transformar conjunto de datos para búsquedas B2B]**.

  Esta opción transformará el conjunto de datos para que pueda emplearse para búsquedas basadas en personas en escenarios B2B.


  >[!IMPORTANT]
  >
  >Una vez activada y guardada la conexión, la transformación es irreversible. No puede modificar la configuración Clave, Clave de coincidencia y Transformar conjunto de datos. Solo puede quitar, agregar y volver a configurar el conjunto de datos.

Para habilitar la transformación para uno o varios conjuntos de datos que ya forman parte de una conexión existente:

1. Elimine los conjuntos de datos de la conexión.
1. Guarde la conexión.
1. Agregue los conjuntos de datos a la conexión mientras activa la transformación de los conjuntos de datos.

## Información básica

Los conjuntos de datos no transformados, para esquemas basados en las cuatro clases de esquema mencionadas anteriormente, pueden contener varias filas para un único identificador de persona. Las búsquedas basadas en personas solo coinciden con la incidencia más reciente de ese identificador de persona, lo que impide una búsqueda adecuada basada en el ID de persona de cuentas, oportunidades, listas de marketing o campañas.

La transformación modifica el conjunto de datos de cada una de las cuatro clases de esquema (naranja en la ilustración siguiente), de modo que para cada identificador de persona se crea una matriz (objeto) para los datos relevantes (cuentas, oportunidades, listas de marketing o campañas) en los conjuntos de datos de búsqueda (rosa en la ilustración siguiente). Esta transformación permite un funcionamiento correcto de las búsquedas basadas en el ID de la persona.

![Esquemas B2B](./assets/b2b-schemas.png)
