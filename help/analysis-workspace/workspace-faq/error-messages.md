---
description: Lista de mensajes de error en Adobe Analysis Workspace y componentes relacionados
title: Mensajes de error comunes en Analysis Workspace
translation-type: tm+mt
source-git-commit: 7f6afbb7c0376791c286021d9ffe4ac670ed7bd7
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# Mensajes de error frecuentes

Puede encontrar errores al interactuar con Analysis Workspace que también afectarán el rendimiento. A continuación se enumeran los tipos de error más comunes, por qué se producen y las optimizaciones que se pueden realizar.

| Mensaje de error | ¿Por qué ocurre esto? | Optimización |
| --- | --- | --- |
| [!UICONTROL Se ha producido un error del sistema. Registre una solicitud del Servicio de atención al cliente en **[!UICONTROL Ayuda > Enviar ticket de asistencia técnica]** e incluya su código de error.] | Adobe está experimentando un problema que debe resolverse. | Envíe el código de error al Servicio de atención al cliente. |
| [!UICONTROL Error 500: No se pudo cargar la página] | Los problemas con la red local, como la [configuración del firewall](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=es-ES) de la compañía, son un factor que contribuye a este error. Además, es posible que el Adobe esté experimentando un problema que debe resolverse. | Intente iniciar sesión nuevamente después de varios minutos. Si el problema persiste, envíe el código de ID de instancia de EIM al Servicio de atención al cliente. |
| [!UICONTROL Uno de los segmentos o la búsqueda en esta visualización contiene una búsqueda de texto que arrojó demasiados resultados.] | Los criterios del segmento o el filtro del informe son demasiado amplios. | Reduzca los criterios del texto de búsqueda y vuelva realizar la solicitud. |
| [!UICONTROL Está grupo de informes está experimentando una creación de informes inusualmente alta. Inténtelo de nuevo más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en un grupo de informes específico. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados, los informes programados, las alertas programadas y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones del grupo de informes de forma más uniforme durante todo el día. |
| [!UICONTROL La solicitud es demasiado compleja.] | La solicitud de informe es demasiado grande y no se puede ejecutar. Los contribuyentes a este error son los tiempos de espera debido al tamaño de la solicitud, demasiados elementos coincidentes en un segmento o filtro de búsqueda, demasiadas métricas incluidas, combinaciones incompatibles de dimensiones y métricas, etc. | Simplifique la solicitud eliminando algunas columnas o filas de la tabla, o considere la posibilidad de dividir la tabla en solicitudes independientes. |
| [!UICONTROL Actualmente, esta dimensión no admite modelos de atribución no predeterminados.] | No se admite la atribución no predeterminada para la dimensión que está utilizando. | Reemplace la dimensión de la tabla por una que sea compatible con [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Su solicitud falló como resultado de demasiadas columnas o filas preconfiguradas.] | La tabla tiene demasiadas celdas improvisadas (columnas de fila *). | Elimine columnas o filas de la tabla, o bien considere la posibilidad de dividir la tabla en solicitudes independientes. |

