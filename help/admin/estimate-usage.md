---
title: Ver y administrar el uso de Customer Journey Analytics
description: Muestra dos métodos para calcular el uso y uno para administrarlo.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 71%

---

# Ver y administrar el uso de Customer Journey Analytics

Para ver el uso del Customer Journey Analytics, puede utilizar varios métodos:

* Agregue las filas de datos de evento para cada conexión. Consulte [Calcular tamaño de conexión](#estimate-connection-size) más abajo. Esta es una forma sencilla de ver los datos de fila de evento, por conexión, para una marca de tiempo específica.

* Vea su uso de tres maneras, cada una de las cuales se describe con más detalle a continuación:
   * Utilizar Analysis Workspace para informar sobre los eventos del mes pasado.
   * Utilizar Report Builder para informar sobre los eventos del mes pasado.
   * Utilice la API de Customer Journey Analytics para crear un informe automatizado.

Para administrar el uso del Customer Journey Analytics:

* Defina una ventana de datos móviles.

## Cálculo del tamaño de la conexión {#estimate-size}

Es posible que necesite saber cuántas filas de datos de evento tiene actualmente en [!UICONTROL Customer Journey Analytics]. Para obtener una cuenta precisa del uso de los registros de datos de evento (filas de datos) de su organización, haga lo siguiente **para cada una de las conexiones creadas por su organización**.

>[!NOTE]
>
>Hágalo el primer viernes de cada mes, ya que Adobe ejecuta su último informe de uso ese día.

1. En [!UICONTROL Customer Journey Analytics], haga clic en la pestaña **[!UICONTROL Conexiones]**.

   Ahora puede ver una lista de todas sus conexiones actuales.

1. Haga clic en cada nombre de conexión para llegar al Administrador de conexiones.

1. Agregue los **[!UICONTROL Registros de datos de evento disponibles]** para cada conexión que haya creado su organización. (Según el tamaño de la conexión, el número puede tardar un tiempo en aparecer).

   ![Registros de datos de evento disponibles.](./assets/event-data.png)

   >[!CAUTION]
   >
   >   Este recuento se aplica solo a los datos de evento, no a los datos de perfil o búsqueda. Si tiene datos de perfil y búsqueda, el recuento será ligeramente mayor. Sin embargo, actualmente no hay forma de informar sobre el uso de los datos de perfil y búsqueda en la interfaz de usuario. Esta funcionalidad está prevista para 2023.

1. Una vez que tenga una suma de todas las filas de datos de evento, busque la asignación “Filas de datos” en el contrato de Customer Journey Analytics que su empresa firmó con Adobe.

   Esto le proporciona el número máximo de filas de datos autorizadas en el pedido de ventas. Si el número de filas de datos resultantes del paso 3 es mayor que este número, se producirá un exceso.

1. Para solucionar esta situación, tiene varias opciones:

   * Cambie la [configuración de retención de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=es#set-rolling-window-for-connection-data-retention).
   * [Elimine conexiones no utilizadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components).
   * [Eliminar un conjunto de datos en Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components).
   * Póngase en contacto con el equipo de cuenta de Adobe para obtener una licencia de capacidad adicional.

## Creación de un proyecto de Workspace con todos los datos de evento {#workspace-event-data}

Este método le permite realizar un análisis más profundo de los datos de uso, así como del historial de su uso.

1. Antes de crear el proyecto en Workspace, [cree una vista de datos](/help/data-views/create-dataview.md) para cada una de las conexiones, sin ningún filtro aplicado.

>[!WARNING]
>
>    No cree una nueva conexión que abarque todos los datos solo para medir el uso, ya que el resultado sería que duplicaría el uso.

1. En Workspace, cree nuevos proyectos basados en cada una de las vistas de datos y extraiga todos los eventos (desde el **[!UICONTROL Métricas]** lista desplegable) hasta el primer viernes del mes, a partir del primer día del contrato de Customer Journey Analytics actual.

   ![Tabla de forma libre que muestra eventos.](./assets/events-usage.png)

   Esto le dará una buena idea de la tendencia de su uso mes a mes.

1. Según sus necesidades, puede profundizar por conjunto de datos, etc.

## Crear un bloque de datos en Report Builder {#arb}

En Report Builder, [cree un bloque de datos](/help/report-builder/create-a-data-block.md) para cada vista de datos, y posteriormente sume todos los bloques.

## Creación de un informe automatizado en la API de Customer Journey Analytics {#api-report}

1. Utilice el [API de informes de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) para ejecutar un informe con todos los datos de evento, **para cada conexión**. Configúrelo para que el informe se ejecute

   * cada primer viernes de cada mes.
   * volviendo al primer día de su contrato de Customer Journey Analytics actual.

   Esto le dará una buena idea de la tendencia de su uso mes a mes. Proporciona el número total de filas en todas las conexiones de Customer Journey Analytics.

1. Utilice Excel para personalizar adicionalmente este informe.

## Administre su uso definiendo una ventana de datos móviles {#rolling}

Para administrar su uso, la variable [IU de conexiones](/help/connections/create-connection.md) permite definir la retención de datos de Customer Journey Analytics como un período de tiempo variable en meses (1 mes, 3 meses, 6 meses, etc.), a nivel de conexión.

La principal ventaja es que solo almacena o genera informes sobre datos que son aplicables y útiles, y elimina los datos más antiguos que ya no son útiles. Le ayuda a mantenerse por debajo de los límites del contrato y reduce el riesgo de costes adicionales.

Si deja el valor predeterminado (sin marcar), el período de retención se sustituirá por la configuración de retención de datos de Adobe Experience Platform. Si tiene datos de 25 meses en Experience Platform, Customer Journey Analytics recibirá 25 meses de datos mediante el relleno. Si eliminase 10 de esos meses en Platform, Customer Journey Analytics conservaría los 15 meses restantes.

La retención de datos se basa en marcas de hora de conjuntos de datos de evento y se aplica solo a conjuntos de datos de evento. No existe ninguna configuración de ventana de datos móviles para conjuntos de datos de búsqueda o perfil, ya que no hay marcas de tiempo aplicables. Si la conexión incluye perfiles o conjuntos de datos de búsqueda, ya que se unen a conjuntos de datos de evento, los datos se conservan en Customer Journey Analytics en función de la configuración de retención de datos en las marcas de tiempo del conjunto de datos de evento.

