---
title: Casos de uso de filtrado e informes de consentimiento
description: Explore casos de uso para informar sobre la pertenencia a la política de consentimiento de visitantes y filtrar los visitantes sin consentimiento en el momento de la ingesta en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 585
ht-degree: 0%

---

# Casos de uso de filtrado y creación de informes de consentimiento

El filtrado y la creación de informes de consentimiento le ayudan a generar informes sobre la pertenencia a directivas de consentimiento de visitantes y, opcionalmente, a excluir a los visitantes que no dan su consentimiento antes de que sus datos entren en Customer Journey Analytics. Para obtener información general, consulte [Información general sobre la creación de informes y el filtrado de consentimiento](/help/connections/consent-reporting-filtering/consent-overview.md).

Este artículo describe casos de uso de ejemplo. Antes de revisarlos, familiarícese con las consideraciones siguientes, ya que afectan a los resultados que ve en los informes.

## Consideraciones del informe

* **El filtrado se aplica en el nivel de conexión**: cuando habilita el filtrado, todas las vistas de datos de la conexión configurada heredan el mismo comportamiento. No puede filtrar una vista de datos en una conexión de forma diferente a otra.

* **El filtrado usa lógica de inclusión**: los datos de un visitante se incorporan solamente si el visitante coincide con todas las directivas de consentimiento que se aplican a las acciones de marketing habilitadas. Se excluye a los visitantes a los que les falta alguna política aplicable.

* **Los datos excluidos no se pueden recuperar**: Como el filtrado se produce en el momento de la ingesta, los datos excluidos no se almacenan en Customer Journey Analytics. Cambiar la configuración más adelante no recupera los datos excluidos de fechas pasadas.

* **La pertenencia a la directiva de consentimiento proviene del conjunto de datos de perfil**: los informes reflejan la pertenencia a la directiva de consentimiento presente en el campo `consentPoliciesIDMap` del conjunto de datos de perfil. Un visitante debe tener un evento correspondiente en la conexión para que aparezca en los informes.

## Casos de uso de ejemplo

### Caso de uso 1: Informe sobre el consentimiento sin filtrar los datos

Comprenda cuántos visitantes coinciden con cada directiva de consentimiento antes de decidir si desea filtrar o responder preguntas como las siguientes:

* _&quot;¿Cuántos de nuestros visitantes han aceptado usar Analytics?&quot;_
* _&quot;¿Qué directivas de consentimiento tienen la mayor y la menor cobertura entre nuestros visitantes?&quot;_

**Flujo de configuración:**

1. Cree una configuración y seleccione la zona protegida, el conjunto de datos de perfil y la conexión que contienen los datos de pertenencia a la directiva de consentimiento.

1. Deje desactivado el filtrado de **[!UICONTROL Analytics]** y **[!UICONTROL Ciencia de datos]**.

1. En Analysis Workspace, cree una tabla de forma libre con la dimensión **[!UICONTROL Nombre de directiva]** y la métrica **[!UICONTROL Visitantes con consentimiento]** para ver la cobertura por directiva.

Utilice estas perspectivas para decidir si desea habilitar el filtrado y para qué acciones de marketing.

### Caso de uso 2: Excluir de la creación de informes de Analytics a los visitantes que no dan su consentimiento

Asegúrese de que los informes estándar incluyan solo los visitantes que hayan aceptado usar Analytics para responder preguntas como las siguientes:

* _&quot;¿Cómo se comporta nuestra audiencia cuando informamos solo sobre visitantes que han dado su consentimiento?&quot;_
* _&quot;¿Podemos asegurarnos de que los datos de visitantes sin consentimiento nunca entren en nuestros informes de análisis?&quot;_

**Flujo de configuración:**

1. Cree o edite una configuración para la conexión que alimente los informes de Analytics.

1. Habilite la opción de filtrado **[!UICONTROL Analytics]**.

1. Confirme la configuración. A partir de este momento, Customer Journey Analytics únicamente ingiere los datos de un visitante si coinciden con todas las directivas de consentimiento aplicables a la acción de marketing analítica.

Dado que el filtrado se produce en el momento de la ingesta, los informes descendentes, las exportaciones y las API reflejan automáticamente solo los visitantes que dan su consentimiento, sin que se requieran cambios en el tiempo de los informes.

### Caso de uso 3: Filtrar casos de uso de análisis y ciencia de datos de forma independiente

Aplique diferentes requisitos de consentimiento a los informes estándar y a los casos de uso de la ciencia de datos para responder preguntas como las siguientes:

* _&quot;¿Podemos incluir un conjunto más amplio de visitantes en Analytics al aplicar un consentimiento más estricto para el aprendizaje automático?&quot;_

**Flujo de configuración:**

1. Cree o edite una configuración para la conexión correspondiente.

1. Habilite la opción **[!UICONTROL Analytics]**, la opción **[!UICONTROL Ciencia de datos]** o ambas, según los requisitos de consentimiento de cada caso de uso.

1. Confirme la configuración. Customer Journey Analytics evalúa de forma independiente las políticas de consentimiento que se aplican a cada acción de marketing habilitada.

Utilice este método cuando su organización aplique distintos requisitos de consentimiento a diferentes categorías de uso de datos.
