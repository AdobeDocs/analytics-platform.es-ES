---
title: Por qué difieren los datos de GA4 y Customer Journey Analytics
description: Comprenda por qué pueden diferir los datos entre GA4 y Customer Journey Analytics y cómo auditar las discrepancias.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# Por qué difieren los datos de GA4 y Customer Journey Analytics

Es normal que GA4 y Customer Journey Analytics informen números diferentes para el mismo período de tiempo y la misma métrica aparente. Los distintos métodos de recopilación de datos, definiciones de métricas, modelos de identidad y reglas de sesión contribuyen a producir discrepancias. Esta página explica las fuentes más comunes de diferencia y proporciona orientación para auditar brechas inexplicables.

## Sesiones comprometidas

GA4 trata una sesión como **comprometida** si duró 10 o más segundos, si incluyó al menos un evento clave o si tuvo 2 o más vistas de página. Esta sola definición sustenta varias métricas de GA4, incluidas la Tasa de participación, la Tasa de salida hacia otro sitio y el umbral de participación detrás de los usuarios activos.

Customer Journey Analytics no tiene métrica ni dimensión de sesión comprometida integrada; usted define la participación para que coincida con su negocio. Adobe recomienda crear un segmento que capture sus criterios de participación y reutilice ese segmento siempre que la participación sea importante. El administrador también puede promocionar esta definición a una métrica en la vista de datos para que esté disponible para todos.

Al formular sus propios criterios, elija las señales que realmente indiquen el valor de su sitio. Tres componentes básicos comunes para la participación son:

* **Duración**: Una duración mínima de sesión, como 10 segundos o más
* **Profundidad**: Un número mínimo de eventos o vistas de página, como 2 o más
* **Acción**: la presencia de una conversión o un evento clave, como un registro o una compra

Puede combinarlas con `OR` para que una sesión se considere comprometida si cumple cualquiera de las condiciones (como lo hace GA4) o combinarlas con `AND` para obtener un requisito más estricto. Si su objetivo es la paridad con GA4, empiece desde sus valores predeterminados y ajuste desde allí.

### Tasa de participación

Una vez que tenga una definición de sesiones comprometidas, la tasa de participación es la proporción de sesiones que participaron. Para crearla como métrica calculada:

1. En Analysis Workspace, seleccione el icono **[!UICONTROL +]** cerca de la lista de métricas para abrir el Creador de métricas calculadas.
2. Asígnele el nombre &quot;Tasa de participación&quot; y establezca el formato en **[!UICONTROL Porcentaje]**.
3. Defina la fórmula como el segmento de sesiones comprometidas dividido por **[!UICONTROL Sesiones]**.
4. Seleccione **[!UICONTROL Guardar]**.

### Porcentaje de rebote

En GA4, una devolución es lo contrario a una sesión iniciada, por lo que la tasa de devolución de GA4 es igual a `1 - Engagement Rate`. Compruébelo en Customer Journey Analytics como una segunda métrica calculada mediante esa fórmula.

Customer Journey Analytics también proporciona una métrica **[!UICONTROL Tasa de salida hacia otro sitio]** integrada, pero su definición predeterminada difiere: cuenta sesiones en las que solo se registró un evento, lo que es opuesto a la definición de GA4 para muchos sitios. La comparación de la tasa de salida hacia otro sitio de GA4 con la métrica predeterminada [!UICONTROL Tasa de salida hacia otro sitio], en lugar del cálculo de `1 - Engagement Rate`, produce números sustancialmente diferentes.

>[!TIP]
>
>La definición de sesión en Customer Journey Analytics se puede configurar por cada vista de datos. Las definiciones de rechazo y participación se pueden ajustar para que coincidan con los criterios de GA4 (duración de 10 segundos, vistas de página de más de 2 segundos o un evento clave) si esa paridad es un requisito de sistema de informes para su organización.

## Sesiones

Tanto GA4 como Customer Journey Analytics establecen de forma predeterminada un tiempo de espera de inactividad de 30 minutos, y ambos mantienen una sesión durante la medianoche y en un cambio de campaña a mitad de la sesión. (Las sesiones de restablecimiento de Universal Analytics en ambos casos, por lo que son una fuente común de confusión, pero no son diferencias entre GA4 y Customer Journey Analytics). Las reglas que sí difieren son las siguientes:

| Regla | GA4 | Customer Journey Analytics |
|---|---|---|
| Tiempo de espera de inactividad | Ajustable en toda la propiedad (valor predeterminado de 30 minutos, hasta 7 horas y 55 minutos) | Configurable por vista de datos |
| Eventos de inicio de sesión | solo `session_start` (automático) | Configurable; cualquier evento puede iniciar una sesión |
| Eventos de fin de sesión | Ninguno | Configurable; cualquier evento puede finalizar una sesión |

Como la definición de sesión de Customer Journey Analytics es configurable, los recuentos de sesiones dependen de cómo se configure la vista de datos. La coincidencia del tiempo de espera de una vista de datos y los eventos de inicio de sesión con la propiedad GA4 acerca los recuentos de sesión entre plataformas.

## Personas y usuarios activos

La métrica de usuario principal de GA4, **Usuarios activos**, cuenta usuarios que tuvieron al menos una sesión involucrada en el intervalo de fechas. La métrica **[!UICONTROL Personas]** de Customer Journey Analytics cuenta ID de persona únicos en el intervalo de fechas.

Es de esperar que estas métricas difieran por varios motivos:

* **Umbral de participación**: Los usuarios activos de GA4 excluyen a los visitantes que no tuvieron [sesión comprometida](#engaged-sessions). La métrica [!UICONTROL Personas] en Customer Journey Analytics incluye a todos independientemente del nivel de participación.
* **[!UICONTROL Vinculación]**: si la vinculación está habilitada, una persona que visitó desde un dispositivo móvil y un equipo de escritorio se puede contar como una persona en Customer Journey Analytics, pero como dos usuarios en GA4. La vinculación suele hacer que la métrica [!UICONTROL Personas] sea menor que los usuarios de GA4 en conjuntos de datos vinculados.
* **Modelo de identidad**: GA4 usa un modelo de identidad en cascada; Customer Journey Analytics usa el ID de la persona que se haya definido en el conjunto de datos. Estas diferencias afectan a los recuentos de personas independientemente de la vinculación.

## Identidad y vinculación

GA4 utiliza un modelo de identidad en cascada para identificar usuarios:

1. ID de usuario (si lo establece su implementación)
2. Señales de Google (si el usuario ha iniciado sesión en una cuenta de Google con la personalización habilitada)
3. ID de dispositivo (ID de cliente basado en cookies)

En la mayoría de las implementaciones, ese ID de persona es un ECID (Experience Cloud ID). La característica opcional **[!UICONTROL vinculación]** puede resolver identidades entre dispositivos y entre canales mediante métodos basados en campos o gráficos, lo que permite asociar una sesión de aplicación móvil y una sesión de explorador de escritorio con la misma persona.

Dado que la resolución de identidad difiere entre plataformas, los recuentos a nivel de usuario rara vez coinciden exactamente. Esta discrepancia es predecible y no indica un problema de calidad de los datos.

## Atribución

GA4 aplica un modelo de atribución de informes configurado en el nivel de propiedad (en Administración), con atribución controlada por datos como predeterminada. Al igual que Customer Journey Analytics, GA4 evalúa este modelo en el momento del informe, por lo que al cambiarlo se actualizan los informes históricos y futuros de forma retroactiva. En GA4, sin embargo, el modelo es para toda la propiedad y afecta solo a los informes de eventos clave que utilizan dimensiones de tráfico con alcance de evento (como Source, Medium y Campaign).

Customer Journey Analytics también aplica la atribución en el momento del informe, pero con un control más granular. Hay dos lugares para configurarlo:

* **Configuración de vista de datos**: se puede establecer un [modelo de atribución](/help/data-views/component-settings/attribution.md) en cualquier componente de métrica de la vista de datos, estableciendo el valor predeterminado para esa métrica en todos los informes. De forma predeterminada, no se aplica ningún modelo de atribución. Puede configurar una vista de datos para que contenga varias copias de la misma métrica, cada una con un modelo de atribución predeterminado diferente.
* **Anulación a nivel de componente**: Después de arrastrar una métrica a una [!UICONTROL tabla de forma libre], haga clic con el botón secundario en el encabezado de su columna y seleccione **[!UICONTROL Usar modelo de atribución no predeterminado]** para invalidarla en esa instancia. También puede arrastrar la misma métrica a la tabla varias veces, cada una con un modelo de atribución diferente para una comparación directa en paralelo.

Como GA4 toma como valor predeterminado la atribución basada en datos mientras que Customer Journey Analytics no aplica ningún modelo a menos que configure uno, es probable que las métricas de conversión y canal difieran hasta que las alinee. Configurar GA4 en un modelo de último clic y un modelo de último contacto coincidente en Customer Journey Analytics es la manera más confiable de establecer una línea de base similar. Cualquier cambio de modelo en Customer Journey Analytics se aplica de forma retroactiva a todos los datos históricos sin necesidad de volver a procesar.

## Auditoría de discrepancias

Cuando los números difieren más de lo esperado, hay tres rutas de auditoría disponibles:

* **Assurance**: la herramienta de validación del producto de Adobe confirma que los eventos XDM se activan correctamente, llegan a Edge Network y se escriben en conjuntos de datos de Platform. Utilice esta herramienta para verificar la implementación de antes de comparar los números de los informes.
* **Vistas previas de conjuntos de datos**: en la interfaz de usuario de Platform, puede obtener una vista previa de las filas sin procesar de cualquier conjunto de datos. Compare estos datos con la exportación de DebugView o BigQuery de GA4 para verificar la precisión de nivel de campo.
* **Adobe Consulting**: Para discrepancias persistentes sin explicación, su equipo de cuenta de Adobe puede organizar una auditoría de implementación formal con un consultor de Adobe.
* **Revisión de ingesta**: Si cree que la discrepancia se origina en cómo se introdujeron los datos de GA en Platform en lugar de en las definiciones de informes, revise la configuración de ingesta en [Migrar datos de Google Analytics](/help/use-cases/third-party/ga/overview.md).
