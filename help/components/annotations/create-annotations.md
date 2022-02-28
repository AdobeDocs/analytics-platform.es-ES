---
title: Creación de anotaciones
description: Cómo crear anotaciones en Espacio de trabajo.
role: User, Admin
feature: Components
exl-id: 3cf9a0fd-11c9-4375-8bbe-9551ba86f86d
source-git-commit: dfd38a9f668dcb0434b107e947aa74b4f9b826a3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creación de anotaciones

>[!NOTE]
>
>Actualmente, esta función está en prueba limitada.

1. To create annotations, you have several ways to get started:

| Método de creación | Detalles |
| --- | --- |
| **Vaya a [!UICONTROL Componentes] > [!UICONTROL Anotación].** | Se abre la página Administrador de anotaciones. Haga clic en [!UICONTROL Crear nueva anotación] y se abrirá el Generador de anotaciones. |
| **Haga clic con el botón derecho en un punto de una tabla.** | [!UICONTROL Se abre el Generador de anotaciones. ] Tenga en cuenta que, de forma predeterminada, las anotaciones creadas de esta forma solo son visibles en el proyecto en el que se crearon. No obstante, puede ponerlas a disposición de todos los proyectos. Tenga en cuenta también que las fechas y cualquier métrica, etc., ya se han rellenado.<p>![](assets/annotate-table.png) |
| **Right-click a point in a [!UICONTROL Line] graph.** | La variable [!UICONTROL Generador de anotaciones] se abre. Tenga en cuenta que, de forma predeterminada, las anotaciones creadas de esta forma solo son visibles en el proyecto en el que se crearon. No obstante, puede ponerlas a disposición de todos los proyectos. Tenga en cuenta también que las fechas y cualquier métrica, etc., ya se han rellenado.<p>![](assets/annotate-line.png) |
| **En Espacio de trabajo, vaya a [!UICONTROL Componentes] > [!UICONTROL Crear anotación].** | The [!UICONTROL Annotation builder] opens. |
| **Utilice esta tecla de acceso directo** para abrir el Generador de anotaciones: (PC) `ctrl` `shift` + o, (Mac) `shift` + `command` + o | Tenga en cuenta que al utilizar la tecla de acceso directo para crear una anotación, se crea una anotación de un solo día para la fecha actual, sin ningún ámbito preseleccionado (métricas o dimensiones). |

1. Fill in the [!UICONTROL Annotation builder] elements.

   ![](assets/ann-builder.png)

   | Elemento | Descripción |
   | --- | --- |
   | [!UICONTROL Título] | Asigne un nombre a la anotación, por ejemplo, “Día de la Independencia”. |
   | [!UICONTROL Descripción] | (Opcional) Proporcione una descripción para la anotación, por ejemplo, “Día festivo celebrado en los Estados Unidos”. |
   | [!UICONTROL Etiquetas] | (Opcional) Organice las anotaciones creando o aplicando una etiqueta. |
   | [!UICONTROL Fecha de aplicación] | Seleccione la fecha o el intervalo de fechas que debe estar presente para que la anotación sea visible. |
   | [!UICONTROL Color] | Aplique un color a la anotación. La anotación aparece en el proyecto con el color seleccionado. El color se puede utilizar para categorizar anotaciones, como festivos, eventos externos, problemas de seguimiento, etc. |
   | [!UICONTROL Ámbito] | (Opcional) Arrastre y suelte las métricas que activan la anotación. A continuación, arrastre y suelte las dimensiones o segmentos que actúen como filtros (es decir, con los que la anotación será visible). Si no especifica un ámbito, la anotación se aplicará a todos los datos.<ul><li>**[!UICONTROL Cualquiera de estas métricas está presente]**: arrastre y suelte hasta 10 métricas que activarán la anotación para mostrar.</li><li>**[!UICONTROL Con todos estos filtros]**: arrastre y suelte hasta 10 dimensiones o segmentos que filtrarán cuando se muestre la anotación.</li></ul><p>Casos de uso: una eVar ha dejado de recopilar datos para un intervalo de fechas específico. Arrastre la eVar al diálogo **[!UICONTROL Cualquiera de estas métricas está presente]**. O la métrica [!UICONTROL Visitas] no genera informes de ningún dato; siga el mismo proceso.<p>**Nota:** Cualquier anotación aplicada a un componente que luego se utiliza como parte de una métrica calculada o definición de segmento NO hereda automáticamente la anotación. La métrica calculada deseada también debe agregarse a la sección de ámbito para mostrar la anotación. However, a new annotation should be created for any segment that you wish to annotate with the same information.<p>Ejemplo: Aplica una anotación a [!UICONTROL Pedidos] en un día específico. You then use [!UICONTROL Orders] in a calculated metric for the same date range. La nueva métrica calculada no mostrará automáticamente la anotación de los pedidos; la métrica calculada también debe agregarse a la sección ámbito para que se muestre la anotación. |
   | [!UICONTROL Aplicar a todos los conjuntos de informes] | De forma predeterminada, la anotación se aplica al grupo de informes de origen. Al marcar esta casilla, puede hacer que la anotación se aplique a todos los grupos de informes de la compañía. |
   | [!UICONTROL Aplicar a todos los proyectos] | De forma predeterminada, la anotación se aplica al proyecto actual. Al marcar esta casilla, puede hacer que la anotación se aplique a todos los proyectos que posea. Tenga en cuenta que esta casilla de verificación solo aparece al iniciar el Generador de anotaciones desde el Creador de anotaciones. |

1. Haga clic en **[!UICONTROL Guardar]**.
