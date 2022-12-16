---
title: Estimar y administrar el uso de CJA
description: Muestra dos métodos para estimar el uso y uno para administrarlo.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# Estimar y administrar el uso de CJA

Para comprender el uso de CJA, puede utilizar dos métodos:

* Agregue las filas de datos de evento para cada conexión. (Consulte **Estimar el tamaño de la conexión** más abajo)
* Use Analysis Workspace para informar sobre los eventos del mes pasado. (Consulte **Creación de un proyecto de Workspace con todos los datos de evento** más abajo).

Para administrar el uso de CJA:

* Utilice la API de CJA. (Consulte **Creación de un informe en la API de CJA** más abajo).

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

1. Antes de crear el proyecto en Workspace, [crear una vista de datos](/help/data-views/create-dataview.md) que extrae datos de TODAS sus conexiones y no tiene filtros aplicados. En otras palabras, incluye todos sus datos.

1. En Workspace, cree un nuevo proyecto y extraiga todos los eventos (desde la **[!UICONTROL Métricas]** lista desplegable) del mes anterior.

   ![Eventos](assets/events-usage.png)

1. haga esto

## Creación de un informe en la API de CJA {#api-report}

Utilice la variable [API de informes de CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) para ejecutar un informe sobre todos los datos de evento.