---
title: Configuración De Report Builder
description: Obtenga información sobre cómo establecer la configuración de Report Builder.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/voTu-CKMtY-0dWvxQd2RzGF8bU9xcuc7J1206kB-3Ao
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 257
ht-degree: 29%

---

# Configuración de Report Builder

Utilice la variable **Configuración** para configurar los ajustes de nivel de aplicación, como el idioma mostrado por la IU o si se va a trabajar o no en modo sin conexión. La configuración se aplica inmediatamente y se establece para todas las sesiones futuras hasta que se cambia.

Para cambiar la configuración de Report Builder

1. Seleccione el icono **Configuración**.

1. Realice cambios en [habilitar el modo sin conexión de deshabilitación](#off-line-mode), [seleccionar un idioma](#language) o [habilitar solución de problemas](#troubleshooting).

1. Seleccione **[!UICONTROL Aplicar]**.

   ![Panel de intervalo de fechas de Report Builder que muestra el botón Cancelar y aplicar.](./assets/report-builder-settings.png){zoomable="yes"}

## Modo sin conexión

Cuando se crea y edita un bloque de datos en modo sin conexión, los datos no se recuperan. En su lugar, se utilizan datos de simulación para que pueda trabajar rápidamente sin esperar a que se ejecute la solicitud. Cuando vuelva a estar en línea, seleccione ![Actualizar](/help/assets/icons/Refresh.svg) **[!UICONTROL Actualizar el bloque de datos]** o ![ActualizarDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Actualizar todos los bloques de datos]** para actualizar los bloques de datos con datos reales.

Para habilitar el modo sin conexión

1. Seleccione ![Configuración](/help/assets/icons/Setting.svg).

1. Active **[!UICONTROL Activar el modo sin conexión]**.

1. Escriba un entero positivo en el campo **[!UICONTROL Mostrar datos de métricas]** como.

1. Seleccione **[!UICONTROL Aplicar]**.


## Idioma

Puede elegir el idioma de la interfaz de Report Builder. Todos los idiomas de Customer Journey Analytics admitidos están disponibles.

Para seleccionar el idioma utilizado en la interfaz de Report Builder:

1. Seleccione un idioma en el menú desplegable **[!UICONTROL Idioma]**.

1. Seleccionar **Aplicar.**

## Resolución de problemas

La configuración **[!UICONTROL registros de solución de problemas]** registra todos los datos de cliente/servidor en un archivo local. Utilice esta opción para resolver los tickets de asistencia.

Para habilitar los registros de solución de problemas, marque **[!UICONTROL Registrar la solicitud del Report Builder en el archivo local]**.
