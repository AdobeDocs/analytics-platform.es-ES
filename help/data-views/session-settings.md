---
title: Configuración de sesión
description: Obtenga información acerca de la configuración de una vista de datos que puede utilizar para definir la duración de una sesión y el déclencheur para iniciar una nueva
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
autotag-review: '2026-05-19T08:57:43.886Z'
TQID: 'https://experienceleague.adobe.com/79GGBxPwVb2uQytFBwgAP2QTd57VbjXuwQqq4oKGGUY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 65%

---

# Configuración de sesión {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="Previsualización de datos"
>abstract="Compara los datos de esta vista de datos con los datos de la conexión. El porcentaje de vista previa se basa en el número total de la conexión de los **últimos 90 días**.<br><br/>Si la vista previa no se carga, es posible que la conexión aún esté reponiendo los datos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


En Customer Journey Analytics, puede definir una sesión del mismo modo en que las personas interactúan con las experiencias digitales. La configuración de sesión se establece en una vista de datos.

Las definiciones de configuración de sesiones son inofensivas y no modifican los datos subyacentes. Puede configurar varias vistas de datos (cada una con su definición de configuración de sesiones específica) como base para sus proyectos de Espacio de trabajo.

Para definir el contexto de una sesión en una vista de datos:

1. Seleccione **[!UICONTROL Vistas de datos]**, opcionalmente desde la **[!UICONTROL Administración de datos]**, en la navegación principal de la interfaz de usuario de Customer Journey Analytics.

1. Cree una nueva vista de datos o edite una existente. Consulte [Creación o edición de una vista de datos](create-dataview.md) para obtener más información.

1. Seleccione la pestaña **[!UICONTROL Configuración.]** Debajo de [!UICONTROL Configuración de sesión]:

   1. Escriba un valor para **[!UICONTROL tiempo de espera de sesión]** en [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL día(s)] o [!UICONTROL semana(s)]. El tiempo de espera de sesión determina cuánto tiempo puede estar inactiva una sesión (sin que se produzcan eventos) antes de iniciar una nueva.

      Elija un tiempo de espera de sesión breve (por ejemplo, 30 minutos) si le interesa analizar principalmente interacciones en línea. Por ejemplo, analizar si los perfiles que visitan las páginas de producto de su tienda en línea agregaron productos al carro de compras o incluso los compraron en línea.

      Elija un tiempo de espera de sesión largo (por ejemplo, 3 meses) si combina datos en línea y sin conexión y desea analizar si sus clientes que han adquirido uno o más productos han llamado a su centro de contacto en los tres primeros meses después de la compra.

   1. Seleccione un segmento del menú desplegable **[!UICONTROL Agregar segmentos]** si desea segmentar una vista de datos. También puede arrastrar y soltar un segmento de ![Segmentación](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]** en el panel izquierdo de **[!UICONTROL _Colocar un segmento aquí_]**.

      Solo se enumeran los segmentos que están compartidos, a los que no tiene acceso y que pueden evaluarse en función de los componentes definidos para la vista de datos.

   1. Seleccione una métrica del menú desplegable **[!UICONTROL Iniciar nueva sesión con una métrica]** También puede arrastrar y soltar una métrica de ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Métricas]** en el panel izquierdo de **[!UICONTROL _Colocar una métrica aquí_]**. La métrica seleccionada define el inicio de una nueva sesión. Puede definir más de una métrica.

      Puede emplear cualquier tipo de métrica para definir una nueva sesión. Por ejemplo, imagine que desea definir una nueva sesión cada vez que un perfil inicia la aplicación móvil. En **[!UICONTROL Vista de datos]** > **[!UICONTROL Componentes]**, define un componente de tipo métrica, denominado **[!UICONTROL Launch]**, basado en un campo de esquema **[!UICONTROL appInteraction]** **[!UICONTROL Name]**. Además, especifique el componente de métrica **[!UICONTROL Launch]** para contar solo el valor cuando el valor coincida con `launch`.

      ![Lanzamientos del componente de métrica de interacción de aplicación](assets/component-launches.png)

      A continuación, arrastre y suelte o seleccione la métrica **[!UICONTROL Launch]** como métrica para definir una nueva sesión.

      ![Lanzamientos de configuración de sesión](assets/session-settings-launches-metric.png)



1. Seleccione **[!UICONTROL Guardar]** o **[!UICONTROL Guardar y finalizar]** para guardar la definición de configuración de sesiones.
