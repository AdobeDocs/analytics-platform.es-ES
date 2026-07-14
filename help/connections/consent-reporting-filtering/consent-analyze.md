---
title: Analizar datos de directivas de consentimiento en Customer Journey Analytics
description: Aprenda a utilizar dimensiones, métricas y plantillas de directivas de consentimiento para informar sobre la pertenencia a directivas de consentimiento de visitantes en Analysis Workspace.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 2%

---

# Analizar datos de directivas de consentimiento

Puede introducir datos de directivas de consentimiento de conjuntos de datos de perfil de Experience Platform en una conexión de Customer Journey Analytics.

Después de [crear una configuración de filtrado y creación de informes de consentimiento](/help/connections/consent-reporting-filtering/consent-configure.md), los datos de la directiva de consentimiento estarán disponibles como componentes nuevos en las vistas de datos en la conexión configurada. Puede utilizar estos componentes en cualquier lugar de Analysis Workspace si tiene acceso a una vista de datos donde existan.

## Componentes de política de consentimiento

La creación de informes de consentimiento agrega los siguientes componentes a las vistas de datos. Estos componentes leen el campo `consentPoliciesIDMap` del conjunto de datos de perfil, y los nombres y las descripciones de las directivas provienen del conjunto de datos de búsqueda de la directiva de consentimiento.

### Dimensiones

| Dimensión | Descripción |
|---------|----------|
| **[!UICONTROL Id. de directiva de consentimiento]** | El identificador de una política de consentimiento con la que coincide un visitante. |
| **[!UICONTROL Nombre de directiva]** | Nombre descriptivo de la directiva de consentimiento, del conjunto de datos de búsqueda de la directiva de consentimiento. |
| **[!UICONTROL Descripción de directiva]** | La descripción de la política de consentimiento, del conjunto de datos de búsqueda de la política de consentimiento. |

### Métricas

| Métrica | Descripción |
|---------|----------|
| **[!UICONTROL Visitantes con consentimiento]** | El número de visitantes que coinciden con una directiva de consentimiento. |
| **[!UICONTROL Eventos con consentimiento]** | El número de eventos asociados con visitantes que coinciden con una política de consentimiento. |
| **[!UICONTROL Políticas de consentimiento único]** | Número de directivas de consentimiento distintas representadas en la ventana de creación de informes. |

### Campo derivado

Un campo derivado hace referencia al campo `consentPoliciesIDMap` para extraer los identificadores de directiva de consentimiento. Puede utilizar este campo derivado como base para dimensiones adicionales basadas en consentimiento. Para obtener más información acerca de los campos derivados, vea [Campos derivados](/help/data-views/derived-fields/derived-fields.md).

## Uso de componentes de política de consentimiento en Analysis Workspace

Para informar sobre la pertenencia a la directiva de consentimiento:

1. En Analysis Workspace, abra un proyecto que utilice una vista de datos configurada para la creación de informes de consentimiento.

1. En el panel Componentes, arrastre una dimensión de directiva de consentimiento, como **[!UICONTROL Nombre de directiva]**, a una tabla de forma libre.

1. Agregue una métrica de consentimiento, como **[!UICONTROL Visitantes con consentimiento]**, a la tabla.

1. Desglose los resultados por cualquier otra dimensión, como Página o Canal, para comprender cómo se comportan los visitantes que consienten.

## Uso de la plantilla de análisis de política de consentimiento

Cuando se configura una vista de datos para la creación de informes de consentimiento, Customer Journey Analytics pone automáticamente a disposición de Analysis Workspace una plantilla de análisis de política de consentimiento. Esta plantilla proporciona un punto de partida para la creación de informes sobre la pertenencia a directivas de consentimiento de visitantes.

Para obtener información sobre cómo tener acceso a las plantillas, vea [Obtener acceso y ejecutar una plantilla](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template).
