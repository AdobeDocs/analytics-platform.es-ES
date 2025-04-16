---
title: Administrar el uso de Customer Journey Analytics
description: Explica cómo administrar el uso de Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 42%

---

# Administrar el uso de Customer Journey Analytics

>[!TIP]
>
>Use la interfaz [**[!UICONTROL Uso ]**](/help/connections/manage-connections.md#usage) para** ver **el uso de filas ingeridas y notificables en todas las conexiones de Customer Journey Analytics.



Puede administrar su uso de Customer Journey Analytics en la interfaz [**[!UICONTROL Conexiones ]**](/help/connections/create-connection.md). En esta interfaz, puede definir la retención de datos de Customer Journey Analytics como un período de tiempo variable en meses (1 mes, 3 meses, 6 meses, etc.), a nivel de conexión.

La principal ventaja es que solo almacena o genera informes sobre datos que son aplicables y útiles, y elimina los datos más antiguos que ya no son útiles. Le ayuda a mantenerse por debajo de los límites del contrato y reduce el riesgo de costes adicionales.

Si deja el valor predeterminado (sin marcar), el período de retención se sustituirá por la configuración de retención de datos de Adobe Experience Platform. Si tiene datos de 25 meses en Experience Platform, Customer Journey Analytics recibirá 25 meses de datos mediante el relleno. Si eliminase 10 de esos meses en Platform, Customer Journey Analytics conservaría los 15 meses restantes.

La retención de datos se basa en marcas de hora de conjuntos de datos de evento y se aplica solo a conjuntos de datos de evento. No existe ninguna configuración de ventana de datos móviles para conjuntos de datos de búsqueda o perfil, ya que no hay marcas de tiempo aplicables. Si la conexión incluye perfiles o conjuntos de datos de búsqueda, ya que están unidos a conjuntos de datos de evento, los datos se conservan en Customer Journey Analytics en función de la configuración de retención de datos en las marcas de tiempo de los conjuntos de datos de evento.


>[!MORELIKETHIS]
>
>[Ver su uso de Customer Journey Analytics](/help/connections/manage-connections.md#usage)

