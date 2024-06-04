---
title: Transformar conjuntos de datos para búsquedas B2B
description: Describe cómo transformar datos en conjuntos de datos de esquemas de búsqueda B2B específicos
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: ffa57c19174bf1618957efe7191c8486c8e3a900
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# Transformar conjuntos de datos para búsquedas B2B

Para admitir búsquedas basadas en personas en datos B2B (incluidas cuentas, oportunidades, listas de marketing y campañas), es necesaria la transformación de los conjuntos de datos de búsqueda B2B.

Esta transformación solo está disponible para conjuntos de datos con datos para esquemas de búsqueda B2B, según las siguientes clases:

* Relación de persona de cuenta empresarial de XDM
* Relación de persona de oportunidad empresarial de XDM
* Miembros de lista de marketing empresarial de XDM
* Miembros de campaña empresarial de XDM

Para habilitar la transformación para un conjunto de datos de este tipo:

![Habilitar conjunto de datos de transformación](assets/transform-dataset.gif)

* Asegúrese de seleccionar el identificador adecuado para **[!UICONTROL Clave]** y **[!UICONTROL Clave de coincidencia]**, por ejemplo `personKey.sourceKey`.

* Seleccione las opciones para importar nuevos datos y el relleno del conjunto de datos.

* Seleccionar **[!UICONTROL Transformar conjunto de datos para búsquedas B2B]**.

  Esta opción transforma el conjunto de datos para que se pueda utilizar para búsquedas basadas en personas en escenarios B2B.


  >[!IMPORTANT]
  >
  >Una vez activada y guardada la conexión, la transformación es irreversible. No puede modificar la configuración de transformación de un conjunto de datos una vez guardada una conexión, más allá de quitar y agregar el conjunto de datos una vez más a la conexión.

Para habilitar la transformación para uno o varios conjuntos de datos que ya forman parte de una conexión existente:

1. Elimine los conjuntos de datos de la conexión.
1. Guarde la conexión.
1. Agregue los conjuntos de datos a la conexión mientras activa la transformación de los conjuntos de datos

## Información básica

Los conjuntos de datos no transformados, para esquemas basados en las cuatro clases de esquema mencionadas anteriormente, pueden contener varias filas para un único identificador de persona. Las búsquedas basadas en personas solo coinciden con la incidencia más reciente de ese identificador de persona, lo que impide una búsqueda adecuada basada en el ID de persona de cuentas, oportunidades, listas de marketing o campañas.

La transformación modifica el conjunto de datos de cada una de las cuatro clases de esquema (naranja en la ilustración siguiente), de modo que para cada identificador de persona se crea una matriz (objeto) para los datos relevantes (cuentas, oportunidades, listas de marketing o campañas) en los conjuntos de datos de búsqueda (rosa en la ilustración siguiente). Esta transformación permite un funcionamiento correcto de las búsquedas basadas en el ID de la persona.

![Esquemas B2B](./assets/b2b-schemas.svg)
