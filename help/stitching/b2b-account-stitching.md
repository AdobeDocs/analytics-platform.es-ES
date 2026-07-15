---
title: Vinculación de cuentas B2B
description: Descubra cómo la vinculación de cuentas B2B en Customer Journey Analytics enriquece los conjuntos de datos de evento con información de cuenta y permite un análisis de recorrido completo en los datos B2B.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2: id: d3f42e9e-bb51-4077-a732-358b801d8b29id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: ddbeb022f4850c2f872f612c86fb37a94b43a73d
workflow-type: tm+mt
source-wordcount: 1203
ht-degree: 20%

---

# Vinculación de cuentas B2B

La vinculación de cuentas B2B enriquece los conjuntos de datos de evento con información de cuenta y permite un análisis completo del recorrido completo del cliente en Customer Journey Analytics. Cuando los eventos carecen de un ID de cuenta, que Customer Journey Analytics B2B edition requiere para la ingesta, la vinculación de cuentas deriva y agrega esa información automáticamente mediante un [conjunto de datos de asignación de persona a cuenta](#prerequisites) que usted proporcione.

Sin la vinculación de cuentas, los eventos que no contengan un ID de cuenta se perderán durante la ingesta. La vinculación de cuentas resuelve esta limitación buscando la cuenta asociada con la persona en cada evento y añadiendo el ID de cuenta tanto cuando se incorpora el evento como de forma retroactiva.

>[!NOTE]
>
>La vinculación de cuentas B2B requiere que tenga derecho a [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) en su entorno para poder configurar la funcionalidad.

La vinculación de cuentas realiza las siguientes operaciones en los conjuntos de datos:

* **Elevar identidad de persona**: el ID de persona de cada evento se eleva al área de nombres de identidad configurada mediante el gráfico de identidades.
* **Agregar información de cuenta que falta**: Para los eventos que contienen un ID de persona, la asignación de persona a cuenta [3} se usa para derivar y agregar la información de cuenta. ](#prerequisites)Cualquier información de la cuenta en el propio evento se utiliza como método de reserva.

## Requisitos previos

Antes de habilitar la vinculación de cuentas B2B, prepare los siguientes conjuntos de datos en Adobe Experience Platform:

| Conjunto de datos | Requerido | Descripción |
|---|---|---|
| **conjunto de datos persona a cuenta** | Requerido | Un conjunto de datos de búsqueda (registro, serie no temporal) que contiene como mínimo un ID de persona (con área de nombres) y un ID de cuenta. Estos ID se utilizan para derivar el mapa de relación persona a cuenta. |

>[!IMPORTANT]
>
>El campo de ID de persona en el conjunto de datos **[!UICONTROL persona a cuenta]** debe marcarse como identidad en el esquema.

## Habilitar vinculación de cuentas {#enable-account-stitching}

Puede habilitar y configurar la vinculación de cuentas B2B en el nivel de conexión y, a continuación, activar la vinculación de cuentas en conjuntos de datos de evento individuales dentro de esa conexión.

### Configuración de vinculación B2B {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="Configuración de vinculación de cuentas B2B"
>abstract="Seleccione **[!UICONTROL Abrir configuración de vinculación B2B]** para configurar la vinculación de cuentas B2B. Si la conexión aún no se ha guardado, la configuración se etiquetará con **[!UICONTROL _Cambios no guardados_]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="Espacio de nombres de identificador de persona"
>abstract="Seleccione el área de nombres de identidad de la persona más relevante para la creación de informes. Por ejemplo, Correo electrónico."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="Conjunto de datos de persona a cuenta"
>abstract="Seleccione el campo del conjunto de datos que contiene los ID de persona. El área de nombres de este campo puede diferir o ser la misma que el área de nombres de identificador de persona seleccionada (configuración de vinculación B2B). Si las dos áreas de nombres son diferentes, vincule las áreas de nombres en el gráfico de identidad."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="Persona"
>abstract="Seleccione el campo del conjunto de datos que contiene el ID de persona. Ese campo debe marcarse como identidad y no puede ser el mismo que el campo **[!UICONTROL Cuenta]** ni el campo **[!UICONTROL Hora de inicio]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="Cuenta"
>abstract="Seleccione el campo del conjunto de datos que contiene los valores del identificador único de cuenta. La información del ID de cuenta estará disponible en las filas de cualquier conjunto de datos de evento con la vinculación habilitada."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="Hora de inicio"
>abstract="Seleccione un campo de marca de tiempo que indique cuándo se activó la relación persona a cuenta."
>additional-url=""
additional-url=""


1. En Customer Journey Analytics, vaya a **[!UICONTROL Conexiones]** y [cree una nueva conexión](/help/connections/create-connection.md#create-a-connection) o [edite una conexión existente](/help/connections/create-connection.md#edit-a-connection).

1. En **[!UICONTROL Configuración de conexión]**, establezca **[!UICONTROL ID principal]** en ![Creación](/help/assets/icons/Building.svg) **[!UICONTROL Cuenta]**.

1. Seleccione **[!UICONTROL Abrir configuración de vinculación B2B]**.

   ![Configuración de vinculación de cuentas B2B](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >Una configuración de vinculación B2B previamente configurada para una conexión no guardada se indica con **[!UICONTROL _Cambios no guardados_]**. No puede modificar **[!UICONTROL contenedores opcionales]** para una configuración de vinculación B2B previamente configurada.

1. En el cuadro de diálogo **[!UICONTROL Configuración de vinculación B2B]**:

   ![Configuración de vinculación B2B](assets/b2b-stitching-configuration.png)

   1. Configurar la sección **[!UICONTROL Persona]**:

      * Seleccione un **[!UICONTROL Área de nombres de identificador de persona]**, por ejemplo **[!UICONTROL Correo electrónico]**, al que desee elevar cualquier ID de persona. Este campo es obligatorio.

   1. Configure la sección **[!UICONTROL Cuenta]** debajo de **[!UICONTROL Persona a cuenta]**.

      | Campo | Requerido | Descripción |
      |---|:---:|---|
      | **[!UICONTROL Conjunto de datos de persona a cuenta]** | ![Requerido](/help/assets/icons/Required.svg) | Seleccione la búsqueda (registro o conjunto de datos de series no temporales) que asigna personas a las cuentas. |
      | **[!UICONTROL Persona]** | ![Requerido](/help/assets/icons/Required.svg) | Seleccione el campo del conjunto de datos que contiene el ID de persona. Ese campo debe marcarse como identidad y no puede ser el mismo que el campo **[!UICONTROL Cuenta]** ni el campo **[!UICONTROL Hora de inicio]**. |
      | **[!UICONTROL Cuenta]** | ![Requerido](/help/assets/icons/Required.svg) | Seleccione el campo del conjunto de datos que contiene el ID de cuenta. Ese campo no puede ser el mismo que el campo **[!UICONTROL Persona]** ni el campo **[!UICONTROL Hora de inicio]**. |
      | **Hora de inicio** | | Seleccione un campo de marca de tiempo que indique cuándo se activó la relación persona a cuenta. |

      >[!NOTE]
      >
      >Si se produce un error al cargar las opciones del campo, los menús desplegables aparecen vacíos y aparece un indicador de error debajo de cada campo afectado. Compruebe el esquema del conjunto de datos e inténtelo de nuevo.

   1. Seleccione **[!UICONTROL Guardar]** para cerrar el cuadro de diálogo **[!UICONTROL Configuración de vinculación B2B]** y volver a la configuración de conexión.

   1. El indicador **[!UICONTROL _Cambios no guardados_]** aparece junto al botón **Abrir configuración de vinculación B2B** hasta que [guarde](#save) la conexión.


### Habilitar vinculación B2B en conjuntos de datos de evento


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="Habilitar vinculación de persona a cuenta"
>abstract="Si se ha habilitado, este conjunto de datos utiliza la vinculación de cuentas B2B. Seleccione un **[!UICONTROL ID de persona]** obligatorio para buscar el ID de cuenta en función del conjunto de datos persona a cuenta.<br/>Si está deshabilitado, este conjunto de datos *no* utiliza la vinculación de cuentas B2B y tendrá que seleccionar un **[!UICONTROL ID de cuenta]** obligatorio en su lugar."
>additional-url=""
additional-url=""


Después de configurar la vinculación B2B en el nivel de conexión, debe habilitar la vinculación de cuentas B2B individualmente para cada conjunto de datos de evento que desee vincular.

1. En Configuración de conexión, seleccione **[!UICONTROL Agregar conjuntos de datos]** o abra la configuración de un conjunto de datos de evento existente.<br/>Consulte [Agregar conjuntos de datos](/help/connections/create-connection.md#add-datasets) o [Editar un conjunto de datos](/help/connections/create-connection.md#edit-a-dataset) para obtener más información.

1. Para el conjunto de datos de evento específico para el que desea configurar la vinculación de cuenta B2B, active **[!UICONTROL Habilitar la vinculación de persona a cuenta]**.

>[!BEGINTABS]

>[!TAB Activado]

Cuando **[!UICONTROL Habilitar la vinculación de persona a cuenta]** es **el**, ha configurado la vinculación de cuenta B2B para el conjunto de datos.

* Se requiere la configuración de un ID de persona. Ese ID de persona se usa para buscar el ID de cuenta en función del [conjunto de datos persona a cuenta](#prerequisites).
* La configuración de un ID de cuenta es opcional.

![Vinculación de cuenta B2B en el conjunto de datos de evento el](assets/b2b-event-dataset-stitching-on.png)

>[!TAB Desactivado]

Cuando **[!UICONTROL Habilitar la vinculación de persona a cuenta]** está **desactivado**, *no* ha configurado la vinculación de cuenta B2B para el conjunto de datos.

* Se requiere la configuración de un ID de cuenta.
* La configuración de un ID de persona es opcional.

![Vinculación de cuenta B2B en el conjunto de datos de evento de](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### Guardar

Una vez que haya configurado la configuración de vinculación B2B y haya terminado de agregar o editar conjuntos de datos, seleccione **[!UICONTROL Guardar]** para guardar la conexión.

>[!IMPORTANT]
>
>Una vez guardada una conexión, la configuración de vinculación B2B se vuelve inmutable. Para ver la configuración después de guardar, selecciona **Abrir configuración de vinculación B2B**. Todos los campos aparecen en estado de solo lectura. Además, si el conjunto de datos usado para la asignación de [persona a cuenta](#prerequisites) se elimina en Experience Platform, se eliminará esta conexión.

## Programación de actualización de datos

La vinculación de cuentas deriva el mapa de identidad de su [conjunto de datos persona a cuenta](#prerequisites) diariamente y utiliza esta información para actualizar los conjuntos de datos habilitados para la vinculación en la siguiente programación:

| Reproducción | Frecuencia | Ventana Datos |
|---|---|---|
| A corto plazo | Semanal | Últimos 7 días |
| A largo plazo | Mensual | Últimos 3 meses |

## Privacidad e higiene de los datos

La vinculación de cuentas respeta las solicitudes estándar de privacidad e higiene para las identidades de la persona, de acuerdo con el comportamiento de vinculación B2C. Si posteriormente se elimina un ID de persona mediante una solicitud de privacidad o higiene, se invierte la vinculación asociada realizada mediante el gráfico de identidad.

Las entidades B2B como cuentas, ID de cuenta e ID de cuenta globales añadidas a eventos mediante la vinculación no se eliminan durante las solicitudes de privacidad o higiene. Estos valores no contienen información personal, por lo que no existe ninguna obligación legal de eliminarlos.

>[!MORELIKETHIS]
>
>* [Información general sobre la vinculación](overview.md)
>* [Configurar una conexión para B2B](../connections/create-connection.md)
>* [Preguntas frecuentes sobre la vinculación](faq.md)

