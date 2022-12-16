---
title: Estimar y administrar el uso de CJA
description: Muestra dos métodos para estimar el uso y uno para administrarlo.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 9ee3bbfe77d6134bee85d4f1844e40894e16a5c7
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 43%

---

# Estimar y administrar el uso de CJA

Para comprender el uso de CJA, puede utilizar 3 métodos:

* Agregue las filas de datos de evento para cada conexión. (Consulte **Estimar el tamaño de la conexión** a continuación) Es una forma sencilla de ver los datos de fila de evento, por conexión, para una marca de tiempo específica.
* Use Analysis Workspace para informar sobre los eventos del mes pasado. (Consulte **Creación de un proyecto de Workspace con todos los datos de evento** más abajo). Esto le permite realizar un análisis más profundo de los datos de uso, así como del historial de uso.
* Utilice la API de CJA para crear un informe automatizado. (Consulte **Creación de un informe en la API de CJA** más abajo).

Para administrar el uso de CJA:

* Defina una ventana de datos móviles. (Consulte **Definición de una ventana de datos móvil** más abajo).

## Cálculo del tamaño de la conexión {#estimate-size}

Es posible que necesite saber cuántas filas de datos de evento tiene en [!UICONTROL Customer Journey Analytics]. Para obtener una cuenta precisa del uso de los registros de datos de evento (filas de datos) de su organización, haga lo siguiente **para cada una de las conexiones creadas por su organización**.

>[!NOTE]
>
>Haga esto el primer viernes de cada mes, ya que Adobe ejecuta su último informe de uso ese día.

1. En [!UICONTROL Customer Journey Analytics], haga clic en la pestaña **[!UICONTROL Conexiones]**.

   Ahora puede ver una lista de todas sus conexiones actuales.

1. Haga clic en cada nombre de conexión para llegar al Administrador de conexiones.

1. Agregue el **[!UICONTROL Registros de datos de evento disponibles]** para cada conexión que haya creado su organización. (Según el tamaño de la conexión, el número puede tardar un tiempo en aparecer).

   ![datos de evento](assets/event-data.png)

   >[!CAUTION]
   >
   >   Este recuento se aplica solo a los datos de evento, no a los datos de perfil o búsqueda. Si tiene datos de perfil y búsqueda, el recuento será ligeramente mayor. Sin embargo, actualmente no hay forma de informar sobre el uso de los datos de perfil y búsqueda en la interfaz de usuario. Esta funcionalidad está prevista para 2023.

1. Una vez que tenga una suma de todas las filas de datos de evento, busque la asignación “Filas de datos” en el contrato de Customer Journey Analytics que su empresa firmó con Adobe.

   Esto le proporciona el número máximo de filas de datos autorizadas en el pedido de ventas. Si el número de filas de datos resultantes del paso 3 es mayor que este número, se producirá un exceso.

1. Para solucionar esta situación, tiene varias opciones:

   * Cambie la [configuración de retención de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=es#set-rolling-window-for-connection-data-retention).
   * [Elimine conexiones no utilizadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components).
   * [Elimine un conjunto de datos en AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components).
   * Póngase en contacto con el administrador de cuentas de Adobe para obtener una licencia de capacidad adicional.

## Creación de un proyecto de Workspace con todos los datos de evento {#workspace-event-data}

1. Antes de crear el proyecto en Workspace, [crear una vista de datos](/help/data-views/create-dataview.md) para cada una de las conexiones y no tiene filtros aplicados.

1. En Workspace, cree un nuevo proyecto y extraiga todos los eventos (desde la **[!UICONTROL Métricas]** lista desplegable) que va hasta el primer viernes del mes, a partir del primer día de su contrato actual de CJA.

   ![Eventos](assets/events-usage.png)

   Esto le dará una buena idea de cómo es que su uso es tendencia mes a mes.

1. Según sus necesidades, puede explorar en profundidad por conjunto de datos, etc.


## Creación de un informe automatizado en la API de CJA {#api-report}

1. Utilice la variable [API de informes de CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) para ejecutar un informe sobre todos los datos de evento, **para cada conexión**. Configúrelo para que el informe se ejecute

   * cada tres viernes de cada mes.
   * volviendo al primer día de su contrato actual de CJA.

   Esto le dará una buena idea de cómo es que su uso es tendencia mes a mes. Le proporcionará el número total de filas en todas sus conexiones de CJA.

1. Utilice Excel para personalizar aún más este informe.

## Definición de una ventana de datos móvil {#rolling}

Para administrar su uso, la variable [interfaz de usuario de conexiones](/help/connections/create-connection.md) permite definir la retención de datos de CJA como un período de tiempo variable en meses (1 mes, 3 meses, 6 meses, etc.), a nivel de conexión.

La principal ventaja es que solo almacena o genera informes sobre datos que son aplicables y útiles, y elimina los datos más antiguos que ya no son útiles. Le ayuda a mantenerse por debajo de los límites del contrato y reduce el riesgo de costes adicionales.

Si deja el valor predeterminado (sin marcar), el período de retención se sustituirá por la configuración de retención de datos de Adobe Experience Platform. Si tiene datos de 25 meses en Experience Platform, CJA recibirá 25 meses de datos mediante el relleno. Si eliminase 10 de esos meses en Platform, CJA conservaría los 15 meses restantes.

La retención de datos se basa en marcas de hora de conjuntos de datos de evento y se aplica solo a conjuntos de datos de evento. No existe ninguna configuración de ventana de datos móviles para conjuntos de datos de búsqueda o perfil, ya que no hay marcas de tiempo aplicables. Sin embargo, si la conexión incluye perfiles o conjuntos de datos de búsqueda (además de uno o más conjuntos de datos de evento), esos datos se conservarán durante el mismo período de tiempo.

