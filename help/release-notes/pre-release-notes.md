---
title: Notas previas al lanzamiento de Customer Journey Analytics
description: Vea las notas previas al lanzamiento de Customer Journey Analytics más recientes
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 80%

---

# Notas previas al lanzamiento de Adobe Customer Journey Analytics

>[!IMPORTANT]
>
>Este documento está diseñado como **vista previa** de las notas de la versión del mes actual. Los elementos de la versión están sujetos a cambios y se pueden añadir o eliminar en la versión final.

Estas notas de la versión abarcan el período de lanzamiento del 2 de junio de 2025 al 15 de julio de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones.

Consulte la siguiente documentación para ver las notas de la versión de Adobe Experience Platform y sus otras aplicaciones:

* [Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [Composición de público federado](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **El panel izquierdo de Analysis Workspace ya no se abre y se cierra al pasar el ratón por encima** | El panel izquierdo de Analysis Workspace se utiliza para añadir elementos como componentes, paneles y visualizaciones al proyecto. La opción para abrir temporalmente el panel izquierdo pasando el puntero sobre uno de los iconos del extremo izquierdo ya no está disponible. En su lugar, simplemente haga clic en uno de estos iconos para mantener el panel abierto y, a continuación, haga clic en el mismo icono para cerrarlo. |  | 2 de junio de 2025 <p>(Originalmente planificado para su lanzamiento el 29 de mayo de 2025)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition ayuda a las empresas B2B a alinear sus equipos de marketing, ventas y productos al proporcionar perspectivas de cuenta procesables que impulsan el crecimiento de los ingresos. Con la cuenta en el centro del modelo de datos, todo el análisis se centra en el recorrido de la cuenta. Al añadir una nueva capa de entidades (cuentas, oportunidades y grupos de compra) sobre los eventos basados en personas y tiempo, se crea una imagen completa del ciclo vital de ingresos y marketing B2B. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 de junio de 2025 |
| **Compatibilidad con destinos seguros en Report Builder** | Se han añadido nuevos destinos de exportación al complemento Report Builder. Se admiten los siguientes destinos de almacenamiento en la nube: <ul><li>ARN de función de Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 18 de junio de 2025 |
| **Nueva experiencia de vista previa** | El panel de vista previa, utilizado para previsualizar segmentos, métricas calculadas, etc., utiliza ahora una visualización de barras horizontales en lugar de una visualización de anillo. |  | 18 de junio de 2025 |
| **Cuadro de diálogo del modelo de atribución modificado** | Ahora puede definir el contenedor y el período de tiempo por separado en el cuadro de diálogo del modelo de atribución. |  | 18 de junio de 2025 |
| **Mapa de conexión** | El [mapa de conexión tiene una interfaz](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-connections/create-connection#connection-map) nueva que muestra la configuración de la conexión. |  | 18 de junio de 2025 |
| **Añadir y ver comentarios en proyectos de Analysis Workspace** | Una nueva [característica de comentarios](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) en Analysis Workspace le permite compartir información y hacer preguntas en el contexto de un proyecto de Analysis Workspace. Esto puede agilizar los debates sobre los datos, manteniendo las conversaciones en el contexto de los datos que se están debatiendo. Puede <ul><li>Comentar cualquier proyecto de Analysis Workspace al que tenga acceso</li><li>Comentar un punto específico en una visualización o hacer comentarios generales sobre un proyecto</li><li>Etiquetar a otros usuarios para notificarles sus comentarios</li><li>Administrar comentarios existentes (editar, fijar, resolver, etc.)</li></ul>Los administradores de Customer Journey Analytics pueden [deshabilitar los comentarios en el nivel de organización](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Los propietarios del proyecto pueden [deshabilitar los comentarios en el nivel de proyecto](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | 25 de junio de 2025 <p>(Originalmente planificado para su lanzamiento el 29 de mayo de 2025)</p> |
