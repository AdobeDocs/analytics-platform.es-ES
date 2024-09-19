---
description: El Administrador de métricas calculadas ofrece numerosas maneras de conservar las métricas, como compartir, filtrar, etiquetar, aprobar, copiar, eliminar y marcar como favoritos.
title: Administrador de métricas calculadas
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: e994a53934ae25802fb16e912d0fdee32d5ea524
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 12%

---

# Administrador de métricas calculadas

La página Métricas calculadas ofrece numerosas maneras de conservar las métricas, como compartir, filtrar, etiquetar, aprobar, copiar, eliminar y marcar como favorito.

El Administrador de métricas calculadas le muestra todos los filtros que posee y que han compartido con usted. Los usuarios con nivel de administrador pueden ver todas las métricas personalizadas de la organización. Esta introducción presenta la interfaz de usuario y las capacidades del Administrador de métricas calculadas.

![Ventana de métricas calculadas que muestra los filtros disponibles.](assets/calc-metric-manager.png)

## Acceso al Administrador de métricas calculadas

1. En el Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Métricas calculadas**].

## Acciones disponibles en el Administrador de métricas calculadas

En el Administrador de métricas calculadas, puede:

* [Filtrar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Marcar una métrica calculada como favorita](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Aprobar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Etiquetar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Compartir métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportar una métrica calculada a un archivo CSV.

* [Copiar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Eliminar métricas calculadas

## Configuración de columnas

Puede configurar la información mostrada para cada métrica calculada en el Administrador de métricas calculadas configurando las columnas que se muestran.

Para configurar las columnas visibles en el Administrador de métricas calculadas:

1. En Customer Journey Analytics, seleccione la ficha **[!UICONTROL Componentes]** y, a continuación, seleccione **[!UICONTROL Métricas calculadas]**.

1. En el Administrador de métricas calculadas, seleccione el icono **Personalizar columnas** ![Personalizar icono de columnas](assets/customize-columns-icon.png) y, a continuación, seleccione las columnas que desea que se muestren en el Administrador de métricas calculadas.

   Las columnas disponibles son las siguientes:

   | Título de columna | Descripción |
   |---|---|
   | Favoritos | Muestra iconos de estrella junto a cada métrica calculada, lo que le permite marcar las métricas calculadas como favoritas. Para obtener más información, consulte [Marcar métricas calculadas como favoritas](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Título y descripción | Estos valores se proporcionan en el Creador de métricas calculadas. Para editar el título y la descripción, seleccione el vínculo del título para abrir el Creador de métricas calculadas. |
   | Grupo de informes | Indica en qué grupo de informes se guardó por última vez la métrica. |
   | Propietario | Indica quién es el propietario de la métrica personalizada. Si no es el administrador, solo podrá ver las métricas que le pertenecen o que compartieron con usted. |
   | Etiquetas | Muestra las etiquetas que se aplicaron a la métrica, tanto por su parte como por parte de las personas que compartieron la métrica calculada con usted. |
   | Compartido con | Enumera las personas o los grupos (solo administrador) o todos (solo administrador) con los que compartió la métrica calculada. <p>Cuando se comparte una métrica calculada, aparece un icono de uso compartido junto al nombre de la métrica calculada.</p> |
   | Fecha de modificación | Indica la fecha en la que se modificó por última vez la métrica personalizada. |
   | Utilizado en | Muestra dónde se están utilizando actualmente las métricas calculadas y cuántas veces se están utilizando en cada área. <p>Por ejemplo, si la métrica calculada se está utilizando en 40 proyectos y 2 alertas, el valor de esta columna se muestra como [!UICONTROL **42 componentes**]. <p>Seleccione el valor de esta columna para ver el desglose de dónde se están utilizando las métricas calculadas (por ejemplo, [!UICONTROL **Proyectos (40)**], [!UICONTROL **Cuadros de resultados móviles (2)**]). Además, puede ver la lista de elementos en los que se utilizan las métricas calculadas. Por ejemplo, para ver la lista de proyectos donde se están usando, seleccione el vínculo [!UICONTROL **Proyectos (40)**].</p><p>Cada una de las siguientes áreas muestra el número de instancias de métricas calculadas que se están utilizando en esa área:</p> <ul><li>[!UICONTROL **Proyectos**]<p>Contiene métricas calculadas que se [crearon en el creador de métricas calculadas](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) y que están disponibles para todos los proyectos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contiene métricas calculadas que fueron [creadas como métricas calculadas rápidas](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) y que están disponibles solamente dentro de un solo proyecto.</p></li><li>[!UICONTROL **Proyectos programados**]</li><li>[!UICONTROL **Cuadros de resultados móviles**]</li><li>[!UICONTROL **Anotaciones**]</li><li>[!UICONTROL **Report Builder**]<p>Al seleccionar esta opción, se descarga un archivo CSV con las siguientes columnas de datos:</p><ul><li>Nombre del Report Builder</li><li>Último acceso</li><li>Identificador de usuario de IMS de último acceso</li><li>Último nombre de usuario accedido</li></ul><p>Cuando se visualiza la información de Report Builder, la información de uso está disponible a partir de septiembre de 2024.</p></li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información solo está disponible para los administradores del sistema.</li><li>La columna [!UICONTROL **Utilizada en**] no se muestra de manera predeterminada. [Configure columnas](#configure-columns) para mostrarlas.</li><li>Si una métrica calculada incluye otra métrica calculada en su definición, cualquier uso de esa métrica calculada no se muestra en la columna [!UICONTROL **Utilizada en**]. Si se incluye una métrica calculada en la definición de otro tipo de componente (como un filtro), entonces el uso se muestra en la columna [!UICONTROL **Utilizado en**].</li><li>Esta información no incluye el uso de la API o la Data Warehouse.</li><li>Si no hay datos en esta columna para un componente determinado pero tiene una fecha de [!UICONTROL **Último uso**], es posible que el componente se haya utilizado en un análisis sin que se haya guardado.</li><li>La información de uso está disponible a partir de septiembre de 2023.</li></ul><p>Puede usar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> |
   | Último uso | Muestra la fecha en la que se utilizó por última vez la métrica calculada en cualquiera de los siguientes tipos de componentes: <ul><li>Métricas calculadas </li><li>Proyectos</li><li>Proyectos programados</li></ul> <p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización o si se debe eliminar.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</li><li>Para algunos componentes, es posible que esta columna no contenga datos si el componente se utilizó por última vez antes de septiembre de 2023.</li><li>Esta información solo está disponible para los administradores del sistema.</li></ul><p>Puede usar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización. |

   {style="table-layout:auto"}
