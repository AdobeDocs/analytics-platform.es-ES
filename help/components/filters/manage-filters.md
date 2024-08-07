---
title: Administrador de filtros
description: descubra cómo administrar filtros en Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e84010b9ea9e6385574e8b1a04f7eccbba3ebc90
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 22%

---

# Administrador de filtros

El administrador de filtros ofrece numerosas maneras de conservar los filtros, como compartir, etiquetar, aprobar, copiar, eliminar y marcar como favoritos.

El administrador de filtros le muestra todos los filtros que posee y que han compartido con usted. Los usuarios con nivel de administrador pueden ver todos los filtros de la organización. Esta introducción presenta la interfaz de usuario y las capacidades del administrador de filtros.

![](assets/filter-manager-ui.png)

## Acceso al administrador de filtros

1. En el Customer Journey Analytics, seleccione la ficha **[!UICONTROL Componentes]** y, a continuación, seleccione **[!UICONTROL Filtros]**.

## Acciones disponibles en el administrador de filtros

En el Administrador de filtros, puede:

* [Filtrar la lista de filtros](/help/components/filters/filters-filter.md)

* [Marcar filtros como favoritos](/help/components/filters/filters-favorite.md)

* [Aprobar filtros](/help/components/filters/filters-approve.md)

* [Filtros de etiquetas](/help/components/filters/filters-tag.md)

* [Compartir filtros](/help/components/filters/filters-share.md)

* Exporte un filtro a un archivo CSV.

* [Copiar filtros](/help/components/filters/filters-copy.md)

* Eliminar filtros

## Configuración de columnas

Puede configurar la información mostrada para cada filtro en el administrador de filtros configurando las columnas que se muestran.

Para configurar las columnas visibles en el administrador de filtros:

1. En Customer Journey Analytics, seleccione la ficha **[!UICONTROL Componentes]** y, a continuación, seleccione **[!UICONTROL Filtros]**.

1. En el Administrador de filtros, seleccione el icono **Personalizar columnas** ![Personalizar icono de columnas](assets/customize-columns-icon.png) y, a continuación, seleccione las columnas que desea que se muestren en el Administrador de filtros.

   Las columnas disponibles son las siguientes:

   | Título de columna | Descripción |
   |---|---|
   | Título y descripción | Estos valores se proporcionan en el Generador de filtros. Para editar el título y la descripción, seleccione el vínculo del título para abrir el Generador de filtros. |
   | Favoritos | Muestra iconos de estrella junto a cada filtro, lo que permite marcar los filtros como favoritos. Para obtener más información, consulte [Marcar filtros como favoritos](/help/components/filters/filters-favorite.md). |
   | Vista de datos | Esta columna indica en qué vista de datos se guardó por última vez el filtro. |
   | Propietario | Indica a quién pertenece el filtro. Si no es el administrador, solo podrá ver los filtros que le pertenecen o que compartieron con usted. |
   | Etiquetas (la columna no aparece porque no está marcada en el selector de columnas) | Etiquetas que se aplicaron al filtro, tanto por su parte como por parte de las personas que compartieron el filtro con usted. |
   | Compartido con | Enumera las personas o los grupos (solo administrador) o todos (solo administrador) con los que compartió el filtro. <p>Cuando usted o con usted comparten un filtro, aparece un icono de uso compartido junto al nombre del filtro.</p> |
   | Fecha de modificación | Muestra la última fecha de modificación del filtro. |
   | Utilizado en | Muestra en cuántos componentes se está utilizando el filtro actualmente. <p>Por ejemplo, si el filtro se está utilizando en 40 proyectos y 2 alertas, el valor de esta columna se muestra como [!UICONTROL **42 componentes**].</p> <p>Seleccione el valor de esta columna para ver el desglose de dónde se está usando el filtro (por ejemplo, [!UICONTROL **Proyectos (40)**], [!UICONTROL **Alertas (2)**]).</p><p>Los filtros se pueden utilizar en cualquiera de los siguientes tipos de componentes:</p> <ul><li>Métricas calculadas </li><li>Proyectos</li><li>Proyectos programados</li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</li><li>La columna [!UICONTROL **Utilizada en**] no se muestra de manera predeterminada. [Configure columnas](#configure-columns) para mostrarlas.</li><li>Si no hay datos en esta columna para un componente determinado pero tiene una fecha de [!UICONTROL **Último uso**], es posible que el componente se haya utilizado en un análisis sin que se haya guardado.</li><li>Esta información solo está disponible para los administradores del sistema.</li></ul><p>Puede usar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> |
   | Último uso | Muestra la fecha en la que se utilizó por última vez el filtro en cualquiera de los siguientes tipos de componentes: <ul><li>Métricas calculadas </li><li>Proyectos</li><li>Proyectos programados</li><li>Filtros</li></ul> <p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización o si se debe eliminar.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</li><li>Para algunos componentes, es posible que esta columna no contenga datos si el componente se utilizó por última vez antes de septiembre de 2023.</li><li>Esta información solo está disponible para los administradores del sistema.</li></ul><p>Puede usar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización. |

   {style="table-layout:auto"}
