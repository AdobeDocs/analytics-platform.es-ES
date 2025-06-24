---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cbe5f3894a01f662a6ebe9c380583d0a039863fd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 42%

---

# Notas de la versión actual de Adobe Customer Journey Analytics (junio de 2025)

**Última actualización**: 18 de junio de 2025


Estas notas de la versión abarcan el periodo de lanzamiento del martes, 02 de junio de 2025 al miércoles, 15 de julio de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **El panel izquierdo de Analysis Workspace ya no se abre y se cierra al pasar el puntero por encima** | El panel izquierdo de Analysis Workspace se utiliza para añadir elementos como componentes, paneles y visualizaciones al proyecto. La opción para abrir temporalmente el panel izquierdo pasando el puntero por encima de uno de los iconos del extremo izquierdo ya no está disponible. En su lugar, simplemente haga clic en uno de estos iconos para mantener el panel abierto y, a continuación, haga clic en el mismo icono para cerrarlo. |  | martes, 02 de junio de 2025 <p>(Originalmente planeado para su lanzamiento el 29 de mayo de 2025)</p> |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition ayuda a las empresas B2B a alinear sus equipos de marketing, ventas y productos al proporcionar perspectivas de cuenta procesables que impulsan el crecimiento de los ingresos. Con la cuenta en el centro del modelo de datos, todo el análisis se centra en el recorrido de la cuenta. Al añadir una nueva capa de entidades (cuentas, oportunidades y grupos de compra) sobre los eventos basados en personas y tiempo, se crea una imagen completa del ciclo vital de ingresos y marketing B2B. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 de junio de 2025 |
| **Compatibilidad con destinos de nube segura en Report Builder** | Ahora puede exportar informes desde Report Builder a los siguientes destinos de almacenamiento en la nube:<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>Anteriormente, se podían compartir libros con otros usuarios por correo electrónico, pero no se podían exportar informes desde Report Builder a destinos en la nube.</p><p>Para obtener más información, vea [Programar libros exportándolos a destinos en la nube](/help/report-builder/report-builder-export.md).</p> |  | 19 de junio de 2025 (originalmente el 18 de junio de 2025) |
| **Nueva experiencia de vista previa** | El panel de vista previa, que se utiliza al crear un segmento o configurar los ajustes de una vista de datos, ahora utiliza una visualización de barras horizontales en lugar de una visualización de anillo. |  | 18 de junio de 2025 |
| **Cuadro de diálogo del modelo de atribución modificado** | Ahora puede definir el contenedor y el período de tiempo por separado en el cuadro de diálogo del modelo de atribución. |  | 18 de junio de 2025 |
| **Mapa de conexión** | Hay una nueva [interfaz de mapa de conexión](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-connections/create-connection#connection-map) disponible para mostrar visualmente la configuración de la conexión. |  | 18 de junio de 2025 |
| **Agregar y ver comentarios en proyectos de Analysis Workspace** | Una nueva característica de [comentarios](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) en Analysis Workspace le permite compartir información y hacer preguntas en el contexto de un proyecto de Analysis Workspace. Esto puede agilizar los debates sobre los datos, manteniendo las conversaciones en el contexto de los datos que se están debatiendo. Puede <ul><li>Comente cualquier proyecto de Analysis Workspace al que tenga acceso</li><li>Comentar un punto específico en una visualización o hacer comentarios generales sobre un proyecto</li><li>Etiquete a otros usuarios para notificarles sus comentarios</li><li>Administrar comentarios existentes (editar, fijar, resolver, etc.)</li></ul>Los administradores de Customer Journey Analytics pueden [deshabilitar los comentarios en el nivel de organización](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Los propietarios del proyecto pueden [deshabilitar los comentarios en el nivel de proyecto](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). | 25 de junio de 2025 | sábado, 11 de julio de 2025 <p>(Originalmente planeado para su lanzamiento el 29 de mayo de 2025)</p> |
| **Compatibilidad con el procesamiento previo de Chrome** | Controle cómo se comportan las bibliotecas de recopilación de datos cuando Chrome realiza un procesamiento previo de una página. (Vínculo a la documentación a continuación) |  | 30 de junio de 2025 |

## Correcciones en Customer Journey Analytics

**Alertas**: AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**Extensión de BI para Tableau**: AN-377488
**Componentes**: AN-376174
**Vistas de datos**: AN-379011
**Ubicaciones de exportación**: AN-382191
**Exportación de tabla completa**: AN-375646; AN-376986; AN-380355; AN-381310
**Lienzo de Recorrido**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**Informes**: AN-372615; AN-378578;


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
