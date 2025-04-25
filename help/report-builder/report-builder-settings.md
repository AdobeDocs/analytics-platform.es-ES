---
title: Configuración de Report Builder en Customer Journey Analytics
description: Describe cómo establecer la configuración del modo sin conexión, idioma, fecha y resolución de problemas.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '258'
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

Para activar el modo sin conexión

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
