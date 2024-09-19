---
title: Añadir datos de cuenta como un conjunto de datos de consulta
description: Obtenga información sobre cómo agregar datos de cuenta como un conjunto de datos de consulta al Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 36%

---

# Añadir datos de cuenta como un conjunto de datos de consulta

Este caso de uso de B2B se muestra cómo añadir datos de cuenta a un análisis de nivel de persona y de nivel de evento. Al agregar datos de cuenta, puede dar respuesta a preguntas como:

* ¿Qué nombre de compañía coincide con esta cuenta?
* ¿Qué funciones se representan en esta cuenta?
* ¿Hay funciones determinadas (como el administrador de TI) en una cuenta que se comportan de forma diferente a la misma función en una cuenta diferente?

Para agregar información de datos de cuenta, agrega y usa un conjunto de datos [lookup](/help/technotes/glossary.md) que contiene esta información.

Estos son los pasos necesarios:

1. [Crear un esquema de consulta](#create-lookup-schema) en el Experience Platform.
1. [Cree un conjunto de datos de consulta](#create-lookup-dataset) en el Experience Platform que le permita introducir datos de cuenta basados en CSV.
1. [Combine conjuntos de datos en una conexión](#combine-datasets-in-a-connection) en el Customer Journey Analytics, incluido el de búsqueda que creó.
1. [Crear una vista de datos](#create-a-data-view-from-this-connection) en el Customer Journey Analytics.
1. [Analizar estos datos](#analyze-the-data-in-workspace) en Workspace en Customer Journey Analytics.

>[!NOTE]
>
>Las tablas de consulta pueden tener un tamaño de hasta 1 GB.
>

## Crear esquema de búsqueda

Cuando crea su propio esquema para la tabla [lookup](/help/technotes/glossary.md), ese esquema garantiza que el conjunto de datos utilizado esté disponible en Customer Journey Analytics con la configuración correcta (tipo de registro). La práctica recomendada es [crear una clase de esquema personalizada](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) que se pueda reutilizar para todas las tablas de búsqueda.

![Cuadro de diálogo Crear nueva clase.](../assets/create-new-class.png)

## Crear conjunto de datos de búsqueda

Una vez creado el esquema, debe crear un conjunto de datos de consulta, basado en ese esquema, en Experience Platform. Este conjunto de datos de búsqueda contiene la información de la cuenta. Por ejemplo: nombre de la empresa, número total de empleados, nombre de dominio, sector al que pertenece la empresa, ingresos anuales, etc. Asegúrese de que los datos contengan un identificador de persona que pueda coincidir con el identificador de persona utilizado en los datos de evento.

1. En Experience Platform, vaya a **[!UICONTROL Administración de datos > Conjuntos de datos]**.
1. Haga clic en **[!UICONTROL + Crear conjunto de datos]**.
1. Haga clic en **[!UICONTROL Crear conjunto de datos a partir de esquema]**.
1. Seleccione la clase de Esquema de consulta que ha creado.
1. Haga clic en **[!UICONTROL Siguiente]**.
1. Asigne un nombre al conjunto de datos (por ejemplo, `B2B Info`) y proporcione una descripción.
1. Haga clic en **[!UICONTROL Finalizar]**.

## Ingesta de datos

Las instrucciones sobre cómo [asignar un archivo CSV a un esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) deberían ayudarle si está usando un archivo CSV.

[Otros métodos](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) también están disponibles.

La incorporación de los datos y el establecimiento de la consulta suelen llevar entre 2 y 4 horas, según el tamaño de la tabla de consulta.

## Combinación de conjuntos de datos en una conexión

Para este ejemplo, combina 3 conjuntos de datos en una conexión de Customer Journey Analytics:

| Nombre del conjunto de datos | Descripción | Clase de esquema Adobe Experience Platform | Detalles del conjunto de datos |
| --- | --- | --- | --- |
| Impresión B2B | Contiene datos de flujo de navegación a nivel de evento de la cuenta. Por ejemplo, contiene el ID de correo electrónico y el ID de cuenta correspondiente, así como el nombre de marketing para realizar campañas publicitarias. También incluye las impresiones de esas publicidades por usuario. | Basado en la clase de esquema XDM ExperienceEvent | El `emailID` se usa como identidad principal y se asigna un área de nombres de `Customer ID`. Como resultado, se muestra como el **[!UICONTROL ID de persona]** predeterminado en el Customer Journey Analytics. ![Impresiones](../assets/impressions-mixins.png) |
| Perfil B2B | Este conjunto de datos de perfil proporciona más información sobre los usuarios de una cuenta, como su puesto de trabajo, a qué cuenta pertenecen, su perfil de LinkedIn, etc. | Basado en la clase de esquema de Perfil individual XDM | Seleccione `emailID` como ID principal en este esquema. |
| Información B2B | Consulte &quot;Creación de un conjunto de datos de consulta&quot; más arriba. | Cuenta B2B (clase de esquema de consulta personalizada) | La relación entre `accountID` y el conjunto de datos de Impresiones B2B se crea automáticamente al conectar el conjunto de datos de información B2B con el conjunto de datos de Impresión B2B en Customer Journey Analytics, como se describe en los pasos siguientes. ![Búsqueda](../assets/lookup-mixins.png) |

Así se combinan los conjuntos de datos:

1. En Customer Journey Analytics, seleccione la opción **[!UICONTROL Conexiones]** para abrir el Navegador.
1. Seleccione los conjuntos de datos que desee combinar.
1. Para el conjunto de datos de B2B Info, seleccione la clave que se utiliza en la tabla de búsqueda (por ejemplo, `personKey.sourceKey`). A continuación, seleccione su clave coincidente (dimensión correspondiente), también en el conjunto de datos de evento (por ejemplo, p`ersonKey.sourceKey`).
1. Haga clic en **[!UICONTROL Siguiente]**.
1. Asigne un nombre a la conexión y describa su configuración según [estas instrucciones](/help/connections/create-connection.md).
1. Haga clic en **[!UICONTROL Guardar]**.

## Crear una vista de datos a partir de esta conexión

Siga las instrucciones de [creación de vistas de datos](/help/data-views/create-dataview.md).

* Añada todos los componentes (dimensiones y métricas) que necesite de los conjuntos de datos. Asegúrese de que, en el caso de las métricas que requieren anulación de duplicación para recuento excesivo, configure estas métricas en consecuencia (consulte [Configuración del componente de anulación de duplicación de métricas](/help/data-views/component-settings/metric-deduplication.md)). Algunos ejemplos de estas métricas son el número de empleados o los ingresos.

## Analizar los datos en Workspace

Ahora puede crear proyectos de Workspace basados en los datos de los 3 conjuntos de datos.

Por ejemplo, puede encontrar respuestas a las consultas planteadas en la introducción:

* Desglose emailID por accountID para averiguar a qué compañía pertenece un ID de correo electrónico.
* ¿Cuántos empleados se asignan a un ID de cuenta específico?
* ¿A qué sector pertenece un ID de cuenta?

>[!MORELIKETHIS]
>
>Consulte [Ejemplo de proyecto B2B](example.md) para obtener más información.

