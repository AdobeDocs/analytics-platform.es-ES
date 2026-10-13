---
title: Configuración de integración entrante de visibilidad de la marca
description: Obtenga información sobre cómo configurar la integración de Brand Visibility con Customer Journey Analytics
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '2118'
ht-degree: 0%
---
# Configuración de la integración entrante

Este artículo detalla los [requisitos previos](#prerequisites), [responsabilidades](#responsibilities), [pasos para comprobar](#verification), [pasos para solucionar problemas](#troubleshoot) y [criterios de finalización](#completion-criteria) para configurar la integración entrante de la Visibilidad de la marca con Customer Journey Analytics.

## Requisitos previos

Tenga en cuenta los siguientes requisitos previos antes de habilitar la integración entrante. Use el [procedimiento de verificación](#verification) a continuación para confirmar cada requisito previo.

### Reenvío de registros BYOCDN

Adobe Brand Visibility debe reenviar y recibir los registros de acceso de CDN para cada sitio de Visibilidad de la marca antes de que el conector de origen de Visibilidad de la marca pueda ser viable.

Este requisito se aplica a cada lugar de Visibilidad de la marca. Una configuración de CDN o fuente de registro para un sitio, dominio o subdominio cubre solo ese sitio.

Confirme ambas partes del envío:

1. Ha configurado la CDN o la canalización de registro relevantes para reenviar los registros de acceso necesarios al destino de Amazon S3 proporcionado por Adobe.
1. La visibilidad de la marca de está recibiendo y detectando los registros del sitio correspondiente. A continuación, el sitio está disponible para su selección en la fuente de Adobe Brand Visibility en Experience Platform.

El reenvío de registros de BYOCDN proporciona los datos de solicitud de CDN del lado del servidor que se utilizan para el análisis del tráfico de agente automatizado. Los datos no dependen de las etiquetas de JavaScript que se ejecuten en un explorador. El requerido
La fuente de registro de CDN garantiza que el conjunto de datos de resumen descendente contenga la Visibilidad de la marca de datos de tráfico auténtico. Consulte la [referencia de reenvío de registro BYOCDN](https://experienceleague.adobe.com/es/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) para obtener más información.

### Información requerida

Asegúrese de que tiene valores para todos los detalles necesarios enumerados en la siguiente tabla para cada sitio de Visibilidad de la marca.

| Valor requerido | Verificación o notas |
|---|---|
| sitio o dominio de visibilidad de la marca | Confirme el sitio cubierto por el reenvío de registros de CDN. |
| Proveedor de CDN | Identifique la CDN que sirve al sitio. |
| Estado de reenvío de registro de CDN | Prueba de que la Visibilidad de la marca reenvía y detecta los registros del sitio. |
| Sitio disponible en la fuente de Visibilidad de la marca | Confirme que el sitio está disponible para seleccionar en el origen de Visibilidad de la marca. Hay un sitio disponible en función de la disponibilidad de los registros de CDN analizados en la Visibilidad de la marca. |
| Organización IMS | Utilice la organización IMS exacta asociada con Brand Visibility, Experience Platform. |
| Zona protegida | Utilice el nombre exacto de la zona protegida designado para la integración entrante. |
| Conexión | Identifique la conexión de Recorrido del cliente que debe incluir el conjunto de datos. |
| Vista de datos | Identifique una vista de datos de Customer Journey Analytics nueva o existente que deba incluir los componentes. |
| Administrador o propietario | Proporcione el nombre o el equipo que sea el contacto de configuración. |

Antes de continuar, confirme que cada sitio está disponible para su selección en la fuente de Adobe Brand Visibility.

### Zona protegida

Puede agregar el conjunto de datos a la conexión de CJA después de que el conjunto de datos aparezca en **[!UICONTROL Conjuntos de datos]** en esa zona protegida.

Confirme lo siguiente:

* Organización de IMS
* Entorno aislado de Experience Platform de Target

La zona protegida de AEP de destino es la misma zona protegida con nombre utilizada por la conexión o conexiones de Customer Journey Analytics correspondientes que incluyen el conjunto de datos.

El cliente puede agregar el conjunto de datos a la conexión de CJA adecuada solo después de que Adobe confirme que se ha creado el conjunto de datos administrado.

### Conjunto de datos resumidos

La integración entrante proporciona un conjunto de datos de resumen agregado en Experience Platform que contiene información de solicitud de CDN del lado del servidor asociada a LLM, bot y automated-agent
tráfico.

La visibilidad de la marca de utiliza registros de acceso de CDN para identificar solicitudes de bots y agentes automatizados. Este tráfico no activa las etiquetas JavaScript del explorador y, por lo tanto, no se captura a través de una implementación convencional de análisis web.

Para obtener la descripción detallada de la integración entrante, la estructura del conjunto de datos y los campos disponibles, consulte [información sobre el conjunto de datos](#about-the-dataset).

El origen de Visibilidad de la marca crea el conjunto de datos de resumen en Experience Platform mediante:

* La clase **[!UICONTROL Métricas de resumen de XDM]**
* El grupo de campos **[!UICONTROL Resumen de solicitudes de CDN]**
* Campos organizados bajo un objeto **[!UICONTROL cdn]**

El conector crea el conjunto de datos para cada sitio de Visibilidad de la marca, utilizando el siguiente patrón de nomenclatura: <code>Conjunto de datos de Adobe Brand Visibility (ABV) - _baseUrl sin esquema_</code>. <br/>Por ejemplo `Adobe Brand Visibility (ABV) Dataset - example.com` para el sitio <https://example.com>.

Los conjuntos de datos creados antes de que se adoptara esta convención de nomenclatura muestran el conjunto de datos de optimización de LLM (LLMO) de patrón anterior: _baseUrl sin esquema_<code></code>.

Busque el conjunto de datos en **[!UICONTROL Conjuntos de datos]** dentro de la zona protegida donde creó el flujo de datos.

El conjunto de datos es un resumen de datos agregado. Al analizar el volumen de solicitudes en Customer Journey Analytics, utilice la métrica **[!UICONTROL Recuento de solicitudes de CDN]** proporcionada en lugar de contar las filas del conjunto de datos.

Compruebe los campos disponibles en el esquema del conjunto de datos creado para el sitio de Visibilidad de la marca específico. Para planificar la configuración de la vista de datos, revise los campos.

## Responsabilidades

Después de habilitar el origen de Visibilidad de la marca, haga lo siguiente en Visibilidad de la marca:

* Envía el conjunto de datos de resumen del sitio seleccionado.
* Aterriza el conjunto de datos en el entorno limitado en el que ha creado el flujo de datos.

Sus responsabilidades como cliente son:

* Para asegurarse de que los registros de CDN se reenvíen y reciban por Visibilidad de la marca para cada sitio de Visibilidad de la marca.
* Para habilitar el origen de la Visibilidad de la marca en el entorno limitado correcto, confirme que el sitio está disponible para seleccionarlo.
* Para seleccionar la conexión de Customer Journey Analytics que debe incluir el conjunto de datos.
* Para agregar el conjunto de datos a esa conexión.
* Para seleccionar los campos que se van a exponer como componentes en la vista de datos de Customer Journey Analytics correspondiente.
* Para validar que las dimensiones y métricas resultantes admiten el análisis deseado.

>[!IMPORTANT]
>
>El conector administrado se detiene intencionadamente después de crear y rellenar el conjunto de datos de Experience Platform. Adobe no modifica las conexiones de Customer Journey Analytics ni las vistas de datos.

El conjunto de datos no está disponible para el análisis de Customer Journey Analytics hasta que se agrega el conjunto de datos a una conexión. Los datos
no está disponible para los usuarios a través de una vista de datos hasta que se hayan agregado los campos relevantes a esa vista de datos.

Para habilitar el origen:

1. En Experience Platform, seleccione la zona protegida en la que desea el conjunto de datos. Un sitio se puede asignar solo una vez, por lo que asegúrese de que esta zona protegida sea la que desee.
1. Vaya a **[!UICONTROL Sources]**, luego a **[!UICONTROL Catalog]** y después a las aplicaciones de Adobe. En la tarjeta **[!UICONTROL Adobe Brand Visibility]**, selecciona **[!UICONTROL Configurar]** la primera vez. Después, la tarjeta muestra **[!UICONTROL Agregar datos]**.

   ![Seleccionar Visibilidad de la marca de orígenes](assets/aep-sources-select-bv.png)

1. Seleccione **[!UICONTROL Agregar datos]**.

   ![Agregar datos al origen de Visibilidad de la marca](assets/aep-sources-bv-add-data.png)

1. En el paso ➊ **[!UICONTROL Seleccionar datos]**:

   1. Seleccione el sitio de la tabla **[!UICONTROL Nombre del sitio]**. Una vez que un sitio se asigna a un flujo de datos, no se puede volver a seleccionar en ese sitio o en cualquier otro entorno limitado.

      ![Paso 1 de la configuración del origen de Visibilidad de la marca](assets/bv-source-step-1.png)

   1. Seleccione **[!UICONTROL Siguiente]**.

1. En el paso ➋ **[!UICONTROL Detalle del flujo de datos]**:

   1. Escriba un **[!UICONTROL nombre de flujo de datos]** y una **[!UICONTROL descripción]** opcional. También puede suscribirse a las alertas **[!UICONTROL Inicio de ejecución del flujo de datos de origen]**, **[!UICONTROL Éxito de ejecución del flujo de datos de origen]** y **[!UICONTROL Error de ejecución del flujo de datos de origen]**.

      ![Paso 2 de la configuración de origen de visibilidad de marca](assets/bv-source-step-2.png)

   1. Seleccione **[!UICONTROL Siguiente]**.

1. En el paso ➌ **[!UICONTROL Revisar]**:

   1. Compruebe la conexión y la asignación del conjunto de datos.

      ![Paso 3 de la configuración del origen de Visibilidad de la marca](assets/bv-source-step-3.png)

   1. seleccione **[!UICONTROL Finalizar]**.

El conjunto de datos se asigna automáticamente y no se requiere ninguna asignación de campo.

>[!IMPORTANT]
>
>Un sitio solo se puede asignar una vez. Para utilizar el sitio en una zona protegida diferente, elimine el flujo de datos al que está asignado el sitio. La eliminación del flujo de datos afecta a cualquier conexión de Customer Journey Analytics o vista de datos que dependa de los datos de este origen.
>


## Verificación

Utilice el siguiente procedimiento para verificar la integración entrante:

1. Confirme la preparación del sitio ABV y del registro de CDN.

   Para cada sitio ABV:

   * Confirme el sitio o dominio exacto cubierto por el reenvío de registro de CDN.
   * Confirme que el sitio está disponible para su selección en el origen de Visibilidad de la marca dentro de Experience Platform. Hay un sitio disponible en función de la disponibilidad de los registros de CDN analizados en la Visibilidad de la marca.
   * No continúe con una declaración general de que &quot;los registros de CDN están habilitados&quot;. Continúe cuando el sitio ABV específico esté disponible para su selección.
   * Confirme que la Visibilidad de la marca está recibiendo o detectando registros para ese sitio.
   * Obtenga de Adobe la confirmación de preparación para Visibilidades de la marca del sitio.

1. Compruebe el conjunto de datos en Experience Platform.

   Después de crear el flujo de datos:
   1. Inicie sesión en **[!UICONTROL Experience Platform]**.
   1. Seleccione la zona protegida en la que ha creado el flujo de datos.
   1. Busque el conjunto de datos de su sitio de Visibilidad de la marca en **[!UICONTROL Conjuntos de datos]**.
   1. Confirme que el conjunto de datos está asociado con el sitio de Visibilidad de la marca esperado.
   1. Registre el **[!UICONTROL ID del conjunto de datos]** y el **[!UICONTROL esquema]** vinculado.
   1. Revise el recuento de registros del conjunto de datos, la información de ingesta más reciente y los datos de ejemplo disponibles donde se permita.
   1. Abra el esquema vinculado y compruebe la estructura XDM esperada:
      * Clase: **[!UICONTROL Métricas de resumen de XDM]**
      * Grupo de campos: **[!UICONTROL Resumen de solicitudes de CDN]**
      * Objeto: **[!UICONTROL cdn]**
      * Dimensiones y métricas esperadas, como **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL requests]** y **[!UICONTROL timeToFirstByte]**.

1. Añadir el conjunto de datos a una conexión

   El administrador de Customer Journey Analytics debe agregar el conjunto de datos a la conexión deseada:

   1. Inicie sesión en Customer Journey Analytics.
   1. [Cree una nueva conexión o edite la conexión existente deseada](/help/connections/create-connection.md). Confirme que la conexión utiliza el mismo entorno limitado de Experience Platform en el que se creó el conjunto de datos.
   1. Busque el conjunto de datos por nombre o ID de conjunto de datos.
   1. Agregue el conjunto de datos a la conexión.
   1. Configure los ajustes del conjunto de datos según el diseño de Customer Journey Analytics del cliente.
   1. Guarde la conexión.
   1. Para confirmar que el conjunto de datos está incluido y que la ingesta está progresando, revise los detalles de conexión.

1. Configuración o actualización de la vista de datos

   Una vez que el conjunto de datos forme parte de la Conexión:
   1. Inicie sesión en Customer Journey Analytics.
   1. [Cree una nueva vista de datos o edite la vista de datos](/help/data-views/create-dataview.md) asociada con el caso de uso de creación de informes deseado.
   1. Seleccione la conexión que contiene el conjunto de datos de Visibilidad de la marca administrado.
   1. Añada los campos de esquema requeridos como dimensiones o métricas.
   1. Incluya los campos necesarios para el análisis planificado, como:
      * **[!UICONTROL Tipo de bot de CDN]**
      * **[!UICONTROL Proveedor de CDN]**
      * **[!UICONTROL URL DE CDN]**
      * **[!UICONTROL Host de CDN]**
      * **[!UICONTROL Estado HTTP de CDN]**
      * **[!UICONTROL Recuento de solicitudes de CDN]**
      * **[!UICONTROL Tiempo promedio de CDN a primer byte]**
   1. Guarde la vista de datos.
   1. Valide los campos de Analysis Workspace o el flujo de trabajo de creación de informes seleccionado del cliente.

1. Validación del resultado de extremo a extremo

   Utilice un período de informe reciente y compruebe que:

   * Se representa el sitio de Visibilidad de la marca esperado.
   * El proveedor de CDN y los valores de host esperados están presentes.
   * Se representa el tráfico de bots o de agentes automatizados.
   * Las dimensiones de URL y estado HTTP contienen los valores esperados.
   * Están disponibles las métricas de rendimiento y Recuento de solicitudes de CDN.
   * El conjunto de datos se incluye en la conexión deseada.
   * Los campos obligatorios se exponen en la vista de datos deseada.

El tiempo exacto necesario para que los datos estén disponibles depende de la ingesta y del flujo de trabajo de procesamiento de Customer Journey Analytics.

## Solucionar problemas

Revise los siguientes pasos si se producen problemas:

* El conjunto de datos no aparece en AEP.

  Compruebe que:

  * La organización de IMS es correcta.
  * La zona protegida de Experience Platform seleccionada es correcta.
  * El origen se habilitó después de que funcionara el reenvío de registro de CDN.
  * Se ha utilizado el nombre o ID del conjunto de datos proporcionado por Adobe.
  * El conjunto de datos se creó para el sitio de Visibilidad de la marca correcto.

* El conjunto de datos existe, pero no contiene los datos esperados.

  Compruebe que:
  * Los registros de CDN se están reenviando para el sitio de Visibilidad de la marca exacto.
  * La visibilidad de la marca está recibiendo o detectando registros para el sitio.
  * El sitio o dominio de la configuración de CDN coincide con el sitio de Visibilidad de la marca.
  * El conector administrado se habilitó después de que se confirmara la preparación del registro de CDN.
  * El intervalo de fechas seleccionado incluye el período posterior al inicio de la ingesta de registros.


* El conjunto de datos existe en Experience Platform, pero no está disponible en Customer Journey Analytics.

  Compruebe que:
  * La conexión de Customer Journey Analytics utiliza la misma zona protegida de Experience Platform.
  * El conjunto de datos se ha agregado explícitamente a la conexión.
  * El administrador de Customer Journey Analytics tiene los permisos necesarios.
  * La conexión se ha guardado después de agregar el conjunto de datos.

* El conjunto de datos está en la conexión, pero los campos no están disponibles para la creación de informes.

  Compruebe que:
  * La vista de datos selecciona la conexión de Customer Journey Analytics correcta.
  * Los campos de esquema esperados se agregaron como componentes de vista de datos.
  * Los campos se colocaron en la sección **[!UICONTROL Dimensiones]** o **[!UICONTROL Métricas]** deseada.
  * La vista de datos se guardó después de agregar los componentes.
  * El esquema del conjunto de datos coincide con la estructura del grupo de campos **[!UICONTROL Resumen de solicitudes de CDN]** esperado.

* El sitio no está en la lista.

  Compruebe que:

  * Hay un sitio disponible para seleccionar en función de la disponibilidad de los registros de CDN analizados en la Visibilidad de la marca.
  * El reenvío de registros de CDN está configurado y funciona para el sitio.

* No se puede seleccionar el sitio.

  Tenga en cuenta que una vez que un sitio se asigna a un flujo de datos, no se puede volver a seleccionar en ese sitio o en cualquier otra zona protegida. Para utilizar el sitio en una zona protegida diferente, elimine el flujo de datos al que está asignado el sitio. A continuación, se puede volver a seleccionar el sitio. La eliminación del flujo de datos afecta a cualquier conexión de Customer Journey Analytics o vista de datos que dependa de los datos de este origen.

* El flujo de datos muestra un estado de error.

  Use el panel **[!UICONTROL Supervisión]**. La descripción general de **[!UICONTROL Sources]** indica que un flujo de datos de origen que falla continuamente durante 30 días se deshabilita automáticamente.


## Criterios de finalización


La integración entrante está lista para la configuración de Customer Journey Analytics del lado del cliente cuando se confirmen todas las siguientes opciones:

* Los registros de CDN se reenvían y reciben por Visibilidad de la marca para cada sitio ABV solicitado.
* Cada sitio de Visibilidad de la marca está disponible para su selección en el origen de Adobe Brand Visibility.
* Ha habilitado la fuente de Adobe Brand Visibility en la zona protegida deseada.
* El conjunto de datos de resumen por sitio aparece en esa zona protegida.
* Ha verificado el conjunto de datos y su esquema XDM.
* Ha agregado el conjunto de datos a la conexión de CJA deseada.
* Ha configurado los componentes relevantes de la vista de datos de CJA.

