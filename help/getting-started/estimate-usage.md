---
title: Estimar y administrar el uso de CJA
description: Muestra dos métodos para estimar el uso y uno para administrarlo.
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 68%

---


# Estimar y administrar el uso de CJA

Para comprender el uso de CJA, puede utilizar dos métodos:

* Añadir los datos de evento para cada conexión (consulte **Estimar el tamaño de la conexión** más abajo)
* Usar Analysis Workspace para...

Para administrar el uso de CJA:

* Usar la API de CJA

## Cálculo del tamaño de la conexión {#estimate-size}

Es posible que necesite saber cuántas filas de datos de evento tiene en [!UICONTROL Customer Journey Analytics]. Para obtener una cuenta precisa del uso de los registros de datos de evento (filas de datos) de su organización, haga lo siguiente **para cada una de las conexiones creadas por su organización**.

>[!NOTE]
>
>Haga esto el primer viernes de cada mes, ya que Adobe ejecuta su último informe de uso ese día.

1. En [!UICONTROL Customer Journey Analytics], haga clic en la pestaña **[!UICONTROL Conexiones]**.

   Ahora puede ver una lista de todas sus conexiones actuales.

1. Haga clic en cada nombre de conexión para llegar al Administrador de conexiones.

1. Agregue los **[!UICONTROL Registros de datos de evento disponibles]** para todas las conexiones creadas. (Según el tamaño de la conexión, el número puede tardar un tiempo en aparecer).

   ![datos de evento](assets/event-data.png)

1. Una vez que tenga una suma de todas las filas de datos de evento, busque la asignación “Filas de datos” en el contrato de Customer Journey Analytics que su empresa firmó con Adobe.

   Esto le proporciona el número máximo de filas de datos autorizadas en el pedido de ventas. Si el número de filas de datos resultantes del paso 3 es mayor que este número, se producirá un exceso.

1. Para solucionar esta situación, tiene varias opciones:

   * Cambie la [configuración de retención de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=es#set-rolling-window-for-connection-data-retention).
   * [Elimine conexiones no utilizadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components).
   * [Elimine un conjunto de datos en AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components).
   * Póngase en contacto con el administrador de cuentas de Adobe para obtener una licencia de capacidad adicional.
