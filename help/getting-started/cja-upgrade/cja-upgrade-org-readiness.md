---
title: Actualización de Adobe Analytics a Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bd19250e-91c0-49f6-b6dc-3abd641344aa
TQID: https://experienceleague.adobe.com/DtETa7Qh3l2X9YSjkX56zX8CmDTWVpGvvyrd9HFayt4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1186
ht-degree: 15%

---

# Prepare su organización para actualizar a Customer Journey Analytics

Parte de una actualización correcta (como se describe en [Actualización de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)) es preparar a su organización centrándose en ciertas consideraciones operativas. Para preparar a su organización, se recomienda que:

* Obtener la aprobación y la alineación de las partes interesadas clave

* Defina y documente sus objetivos

* Establezca plazos realistas y meditados

* Definir responsabilidades claras para los colaboradores

## Adhesión y alineación de las partes interesadas

Las partes interesadas clave y los responsables de la toma de decisiones de su organización deben alinearse en la actualización a Customer Journey Analytics.

En las secciones siguientes se describen las formas de alinearse con las partes interesadas.

### Enfoque en el valor

Céntrese en el valor que Customer Journey Analytics aportará a su organización y en cómo acelerará la consecución de sus objetivos empresariales.

En la tabla siguiente se describen algunas de las características principales que puede que desee resaltar.

| Función | Ventaja | Ejemplo |
|---------|----------|---------|
| **[Alojamiento para todo tipo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home)** | Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y datos. | Una organización minorista podría proporcionar visibilidad al recorrido completo del cliente integrando los siguientes tipos de datos en una sola vista: <ul><li>Transacciones del flujo de navegación web</li><li>Transacciones de aplicaciones móviles</li><li>Transacciones en tienda</li><li>CRM y datos de fidelidad</li></ul> |
| **[Análisis en canales múltiples](/help/use-cases/cross-channel/cross-channel.md)** | Habilita una sola vista consolidada del comportamiento de los clientes en varios canales mediante la unificación de datos de varias propiedades web, móviles y sin conexión. | Una organización minorista que recopile datos de varios canales puede realizar el siguiente tipo de análisis:<p>Un comprador hace clic en un anuncio de búsqueda de pago, navega por Internet, recibe una notificación push y compra en la tienda dos días después. Esta perspectiva unificada permite una atribución precisa entre canales, lo que muestra cómo los puntos de contacto digitales contribuyen a las ventas en la tienda. También admite una segmentación más precisa, como dirigirse a clientes &quot;navegados en línea, comprados en la tienda&quot; con ofertas adaptadas. Además, ofrece informes de ingresos claros y multicanal en un tablero, sustituyendo las perspectivas fragmentadas y aisladas por una comprensión integral del comportamiento de los clientes. |
| **[Procesamiento de intervalo de tiempo](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Aplique configuraciones retroactivas y cree varias versiones de persistencia de variables sin necesidad de cambiar la forma en que se recopilan los datos subyacentes. | Dado que Customer Journey Analytics le permite crear y ajustar métricas, dimensiones y modelos de atribución sobre la marcha sin reingerir ni reprocesar datos, una organización minorista podría ver cómo una campaña social reciente influyó en las ventas en línea y en las tiendas sin necesidad de pedir a los ingenieros que reconstruyeran conjuntos de datos. Podrían cambiar instantáneamente el modelo de atribución de último contacto a primer contacto o atribución personalizada basada en reglas. |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | Ayuda a los especialistas en marketing a comprender cómo afecta el contenido a los indicadores de rendimiento clave que ha definido una empresa. Además de los datos de comportamiento, Content Analytics recopila datos sobre cómo se consume el contenido y cómo este genera impacto. | Al integrar datos web, de aplicaciones, de correo electrónico e incluso de tiendas, una organización minorista podría ver exactamente cómo contribuye cada parte del contenido digital que crea al recorrido y la conversión de los clientes. <p>La organización minorista podría ver que una &quot;Guía de estilo de mezclilla de verano&quot; en una popular plataforma de medios sociales genera una alta participación entre los miembros más fieles, y que esos miembros tienen un 40% más de probabilidades de comprar mezclilla en la tienda en una semana.</p> |

### Nombrar un patrocinador ejecutivo

Busque y designe un patrocinador ejecutivo dentro de su organización. Este patrocinador ejecutivo debe comprender cómo Customer Journey Analytics acelerará el logro de sus objetivos empresariales.

El patrocinador ejecutivo es crucial, ya que:

* Campeón Customer Journey Analytics dentro de la organización

* Eliminar obstáculos

* Aprobación de recursos

### Obtenga asistencia de los líderes clave de su organización

Con la ayuda de su patrocinador ejecutivo, consiga el apoyo de otros líderes clave de su organización. Es fundamental que los líderes de las siguientes áreas de su organización comprendan las ventajas de Customer Journey Analytics y que estén dispuestos a contribuir a una implementación exitosa:

* Analytics

* Marketing

* IT

* Legal y cumplimiento

* Unidades de negocio individuales

## Desarrollar un plan de actualización y comunicación

### Desarrollar un plan de actualización y distribuirlo a las partes interesadas

Un plan de actualización puede incluir la siguiente información:

* Una descripción clara de por qué se está realizando la actualización. Por ejemplo, describa las ventajas para los usuarios y para la organización o la empresa en su conjunto. Para obtener más información acerca de los beneficios, vea [Centrarse en el valor](#focus-on-value).

* Una cronología general, como cuándo se planea comenzar la actualización, una descripción de los hitos clave y una estimación de cuándo se ha programado la actualización para completarse.

* Una indicación de cuándo pueden empezar los usuarios a realizar cursos de formación oficiales para aprender a utilizar Customer Journey Analytics. Para obtener más información, consulte [Capacitar a usuarios finales en toda la organización](#train-end-users-throughout-your-organization).

* Información sobre quién lidera la actualización y cómo o cuándo las personas pueden ponerse en contacto con nosotros si tienen alguna pregunta.

### Crear un plan de comunicación

Un plan de comunicación puede incluir las siguientes consideraciones:

* Una cadencia definida sobre cuándo se enviarán las comunicaciones a las partes interesadas y a los usuarios

* Descripción del tipo de información que se enviará

* Un plan para quién enviará las comunicaciones

* Se han definido bucles de comentarios para permitir que las partes interesadas y los usuarios hagan preguntas o proporcionen comentarios

## Evaluación y auditoría de la implementación de Adobe Analytics

Realice una evaluación y una auditoría exhaustivas de la implementación de Adobe Analytics, centrándose en las siguientes áreas clave:

* Usuarios actuales

* Acceso de usuarios

* Proyectos

* Procesos empresariales

* Componentes personalizados

Consulte los siguientes recursos para recopilar esta información:

* [Inventario de Analytics](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/analytics-inventory)

  Proporciona información sobre el número de proyectos, segmentos, métricas calculadas, grupos de informes y usuarios dentro de su organización.

* [Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Proporciona información sobre cómo prepararse para migrar componentes, proyectos y usuarios.

## Identificación de los campeones y los primeros usuarios

Identifique a los Campeones en toda su organización. Estos campeones deben ser:

* Usuarios avanzados de Adobe Analytics

* Capaz de obtener rápidamente la competencia en Customer Journey Analytics

* Disponible para ayudar y ayudar a otros, ya que Customer Journey Analytics se está implementando de forma más amplia

## Forme a los usuarios finales en toda la organización

* Proporcione formación práctica que se centre en las diferencias en los modelos de datos, los paradigmas de creación de informes y las nuevas funciones de Customer Journey Analytics.

* Ofrecer sesiones en directo (talleres u horas de oficina) y recursos bajo demanda (tutoriales de vídeo, páginas wiki dinámicas y documentación interna).

* Dirija a los usuarios a cursos de formación, tutoriales y documentación relevantes sobre Experience League.

  Los siguientes recursos pueden ayudarle a empezar:

   * [Tutoriales de Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/customer-journey-analytics-learn/tutorials/overview)

   * [¿Qué es Customer Journey Analytics?](https://experienceleague.adobe.com/es/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Introducción a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Compatibilidad con las funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)

## Siga los pasos de actualización recomendados

Cuando esté listo para iniciar el proceso de actualización, siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los pasos de actualización generados dinámicamente en la Guía de actualización de Customer Journey Analytics. Para acceder a la guía desde Customer Journey Analytics, seleccione la pestaña **[!UICONTROL Workspace]** y, a continuación, seleccione **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en la pantalla.
