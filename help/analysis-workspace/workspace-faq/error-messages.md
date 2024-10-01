---
description: Obtenga información sobre los mensajes de error y cómo solucionar problemas en Adobe Analysis Workspace
title: Errores y soluciones comunes en Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: ec32b7bca6fd4fc4b2652d1265048ec788f19718
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 74%

---

# Errores y solución de problemas

Puede encontrar errores al interactuar con Analysis Workspace que pueden influir en su funcionalidad o rendimiento. A continuación se enumeran los tipos de error más comunes, por qué se producen y las optimizaciones que se pueden realizar.

## Mensajes de error

Algunos mensajes de error comunes que puede ver al utilizar Analysis Workspace:

| Mensaje de error | ¿Por qué se produce el error? | Optimización |
| --- | --- | --- |
| [!UICONTROL La vista de datos está experimentando una creación de informes inusualmente alta. Inténtelo nuevamente más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en una vista de informes específica. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados, los informes programados, las alertas programadas y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones de la vista de informes de forma más uniforme durante todo el día.<p>Los administradores pueden usar el [Administrador de actividades de creación de informes para identificar y cancelar las solicitudes](/help/reporting-activity-manager/reporting-activity-overview.md) que consumen capacidad de creación de informes.</p> |
| [!UICONTROL Este informe es demasiado complejo. Consulte las prácticas recomendadas para generar informes de Analysis Workspace.] | La solicitud de creación de informes es demasiado grande y no se puede ejecutar. Los factores que contribuyen a este error son los tiempos de espera debido a la complejidad de la solicitud. | Simplifique su solicitud. Por ejemplo, acortar el intervalo de fechas, simplificar los criterios de filtro o quitar algunas columnas o filas de la tabla. También puede considerar la posibilidad de dividir la tabla en solicitudes independientes. |
| [!UICONTROL Actualmente, la vista de datos supera su capacidad de creación de informes. Simplifique la solicitud o inténtelo de nuevo más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en una vista de informes específica. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones de la vista de informes de forma más uniforme durante todo el día. |
| [!UICONTROL Se ha producido un error del sistema. Registre una solicitud del Servicio de atención al cliente en **[!UICONTROL Ayuda > Enviar ticket de asistencia técnica]** e incluya su código de error.] | Adobe está experimentando un problema que debe resolverse. | Envíe el código de error al Servicio de atención al cliente. |
| [!UICONTROL Error 500: No se pudo cargar la página] | Los problemas con la red local, como la [configuración del firewall](https://experienceleague.adobe.com/en/docs/analytics/technotes/ip-addresses) de la compañía, son un factor que contribuye a este error. Además, es posible que el Adobe esté experimentando un problema que debe resolverse. | Intente iniciar sesión nuevamente después de varios minutos. Si el problema persiste, envíe el código de ID de instancia de EIM al Servicio de atención al cliente. |
| [!UICONTROL Su solicitud falló como resultado de demasiadas columnas o filas preconfiguradas.] | La tabla tiene demasiadas celdas improvisadas (columnas de fila *). | Elimine columnas o filas de la tabla, o bien considere la posibilidad de dividir la tabla en solicitudes independientes. |


## Resolución de problemas

Al utilizar Analysis Workspace, puede utilizar la información siguiente para solucionar algunos problemas comunes.

| Problema | Cómo solucionar problemas |
|---|---|
| Cuando arrastro una métrica, indica *datos no válidos*. | Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra. |
| Cuando arrastro una métrica, no veo ningún dato real, solo ceros. | Si ha creado correctamente un informe de Workspace pero no hay datos, puede comprobar algunas cosas:<ul><li>Si aplicó un filtro en el informe, es posible que los criterios de filtro no coincidan con ningún dato. Intente eliminar el filtro o ajustar su definición.</li><li>Compruebe el intervalo de fechas en la esquina superior derecha y asegúrese de que está establecido en un valor que espera.</li><li>Vaya al sitio web y utilice [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es) para validar que se están recopilando datos.</li></ul> |
