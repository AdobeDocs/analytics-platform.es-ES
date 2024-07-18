---
description: Administración de exportaciones existentes
keywords: Analysis Workspace
title: Administración de exportaciones
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 6f8a43acfba23d6faeff078873742315f1506699
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 4%

---

# Administración de exportaciones

Después de exportar una tabla completa como se describe en [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md), las exportaciones están disponibles en la ficha [!UICONTROL Exportaciones] de la página [!UICONTROL Exportaciones].

Solo puede ver las exportaciones que cree.

## Filtrado y búsqueda de exportaciones

Para encontrar la información que necesita, puede filtrar la lista de exportaciones o buscar una exportación.

### Filtrado de la lista de exportaciones

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. Seleccione la ficha [!UICONTROL **Exportaciones**].

1. Seleccione el icono **Filter**.

   <!--add screenshot -->

   Puede filtrar por los siguientes criterios:

   | Filtro | Descripción |
   |---------|----------|
   | [!UICONTROL **Tipo de cuenta**] | El tipo de cuenta al que está asociada la exportación. Están disponibles los siguientes tipos de cuenta: <ul><li>[!UICONTROL **Zona de aterrizaje de datos de AEP**]</li><li>[!UICONTROL **ARN de la función Amazon S3**]</li><li>[!UICONTROL **SAS de Azure**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Plataforma de Google Cloud**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Estado**] | El estado de la exportación. Los siguientes estados están disponibles: <ul><li>[!UICONTROL **Activo**]: indica que una exportación programada aún no ha caducado o que una exportación única aún no ha finalizado. </li><li>[!UICONTROL **Completado**]: indica que una exportación se ha exportado correctamente. En el caso de las exportaciones programadas, esto indica que la programación ha caducado.</li><li>[!UICONTROL **Fallido**]<p>Las siguientes situaciones pueden provocar un error en la exportación. Pase el ratón sobre el estado [!UICONTROL **Error**] para ver los detalles del error. <ul><li>Caducidad de exportación programada</li><li>Se alcanzó el límite de filas para la exportación programada </li></ul> </p></li></ul> |
   | [!UICONTROL **Frecuencia**] | La frecuencia con la que se produce la exportación. Las frecuencias disponibles son las siguientes: <ul><li>[!UICONTROL **Una vez**]</li><li>[!UICONTROL **Diario**]</li><li>[!UICONTROL **Semanalmente**]</li><li>[!UICONTROL **Mensual**]</li><li>[!UICONTROL **Anual**]</li></ul> |

   {style="table-layout:auto"}

### Buscar exportaciones

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. Seleccione la ficha [!UICONTROL **Exportaciones**].

1. En el campo de búsqueda, empiece a escribir cualquier información asociada con la exportación que está buscando. Puede buscar datos de cualquier columna disponible en la tabla.

## Edición de una exportación

Puede editar las propiedades, el formato, la programación y la información de ubicación de una exportación.

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. En la ficha [!UICONTROL **Exportaciones**], active la casilla de verificación situada junto a la exportación que desee editar.

   Esta opción no está disponible cuando se seleccionan varias exportaciones.

1. Seleccione [!UICONTROL **Editar**].

   Se muestra el cuadro de diálogo [!UICONTROL **Exportar tabla completa**].

1. Actualice cualquiera de las opciones disponibles. Para obtener información sobre cada opción, consulte [Exportar tablas completas desde Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) en [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md).

## Duplicación de una exportación

Puede duplicar una exportación existente.

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. En la ficha [!UICONTROL **Exportaciones**], active la casilla que hay junto a la exportación que desea duplicar.

   Esta opción no está disponible cuando se seleccionan varias exportaciones.

1. Seleccione [!UICONTROL **Duplicado**].

   Se crea un duplicado de la exportación. El nombre de la nueva exportación coincide con el nombre de la exportación original, con _[!UICONTROL - Copiar]_ anexado al nombre del archivo.

1. (Opcional) [Edite la nueva exportación](#edit-an-export), incluido el nombre de archivo y cualquier otra propiedad que desee cambiar.

## Iniciar manualmente una exportación

Puede iniciar manualmente una exportación, ya sea para una exportación programada o para una exportación única que se haya completado anteriormente.

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. En la ficha [!UICONTROL **Exportaciones**], active la casilla de verificación situada junto a la exportación que desee ejecutar.

   Esta opción no está disponible cuando se seleccionan varias exportaciones.

1. Seleccione [!UICONTROL **Exportar ahora**].

## Etiquetado de una exportación

Al aplicar etiquetas a una exportación, puede verlas en la columna [!UICONTROL Etiquetas] de la página [!UICONTROL Exportaciones]. Consulte [Configurar columnas](#configure-columns) para obtener más información.

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. En la ficha [!UICONTROL **Exportaciones**], active la casilla que hay junto a una o varias exportaciones que desea etiquetar.

1. Seleccione [!UICONTROL **Editar etiquetas**].

1. En el cuadro de diálogo [!UICONTROL **Exportación de etiquetas**], escriba el nombre de una etiqueta para crear una etiqueta nueva o elija una etiqueta existente en el menú desplegable.

   Cualquier etiqueta común entre las exportaciones seleccionadas se muestra en el cuadro de diálogo de etiquetas. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Seleccione [!UICONTROL **Aplicar etiquetas**].

## Eliminación de una exportación

Puede eliminar las exportaciones desde la página Exportaciones. Las exportaciones programadas que se eliminan ya no se enviarán.

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. En la ficha [!UICONTROL **Exportaciones**], active la casilla que hay junto a una o varias exportaciones que desea eliminar.

1. Seleccione [!UICONTROL **Eliminar**] y, a continuación, seleccione [!UICONTROL **Eliminar**] cuando vea el mensaje de confirmación.

## Configurar columnas en la página [!UICONTROL Exportaciones]

Puede agregar o quitar columnas en la ficha [!UICONTROL Exportaciones] para configurar la información que se muestra.

Seleccione un encabezado de columna para ordenar las exportaciones por esa columna. De forma predeterminada, las exportaciones se ordenan por la fecha y la hora de la última modificación de la exportación.

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. En la ficha [!UICONTROL **Exportaciones**], seleccione el icono **Personalizar tabla** ![personalizar tabla](assets/customize-table-icon.png) en la parte superior derecha de la página [!UICONTROL Exportaciones].

   Las columnas disponibles son las siguientes:

   | Columna disponible | Descripción |
   |---------|----------|
   | Nombre | Nombre de la exportación. Los usuarios asignan un nombre a las exportaciones cuando las crean, tal como se describe en [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md). |
   | ID | El ID asignado automáticamente a la exportación cuando se crea. <!-- True? --> |
   | Nombre de la vista de datos | Nombre de la vista de datos asociada con la exportación. Los usuarios pueden seleccionar la vista de datos cuando creen la exportación, tal como se describe en [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md). |
   | Estado | El estado de la exportación. Los estados disponibles son [!UICONTROL Activo], [!UICONTROL Completado] y [!UICONTROL Fallido].<p> **Nota:** Para obtener información acerca de la solución de problemas de exportaciones con errores, consulte [Solucionar problemas de exportaciones con errores](/help/components/exports/troubleshoot-exports.md).</p> |
   | Etiquetas | Muestra todas las etiquetas aplicadas a la exportación. Para obtener información sobre cómo aplicar etiquetas a una exportación, consulte [Etiquetar una exportación](#tag-an-export). |
   | Tamaño de la tabla (último envío) | El tamaño de la exportación la última vez que se envió. |
   | Creado por | El usuario que creó la exportación. |
   | Creado | Fecha y hora de creación de la exportación. <!-- true? --> |
   | Ubicación | Ubicación de la cuenta donde se exportaron los datos. |
   | Cuenta | Cuenta en la que se exportaron los datos. |
   | Frecuencia | La frecuencia con la que se envía la exportación. Las opciones disponibles son [!UICONTROL Una vez], [!UICONTROL Diario], [!UICONTROL Semanal], [!UICONTROL Mensual por día de la semana], [!UICONTROL Mensual por día del mes], [!UICONTROL Anual por día del mes] y [!UICONTROL Anual por fecha específica]. |
   | Hora de envío | La hora a la que se envió la exportación. |
   | Enviado por última vez | La última vez que se envió la exportación. |
   | Última modificación | La última vez que se modificó la exportación. Los elementos de la página Exportaciones se ordenan por esta columna de forma predeterminada. |
   | Tipo de cuenta | El tipo de cuenta de nube donde se exportaron los datos. Los tipos de cuenta disponibles son [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] y [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. Asegúrese de que todas las columnas que desee mostrar estén seleccionadas. Las columnas seleccionadas aparecen en la página Exportaciones y muestran la información relevante.
