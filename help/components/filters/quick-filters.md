---
description: Uso de filtros rápidos en Analysis Workspace para Customer Journey Analytics
title: Filtros rápidos
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 3d55105a7d4f4687ed0fc6d857c906eec707f6a6
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 38%

---

# Filtros rápidos

Los filtros rápidos le permiten explorar fácilmente los datos de un proyecto determinado, sin necesidad de crear un filtro de lista de componentes más complejo en el [Generador de filtros](/help/components/filters/create-filters.md).

Tenga en cuenta lo siguiente al crear filtros rápidos:

* Los filtros rápidos solo se aplican al proyecto en el que se crearon. No están disponibles en otros proyectos y no se pueden compartir con otros usuarios.
* Se permite un máximo de 3 reglas.
* No se admiten contenedores anidados ni reglas secuenciales.

El siguiente vídeo muestra cómo utilizar filtros rápidos. (Nota: En este vídeo se utiliza el término &quot;segmentos rápidos&quot; en lugar de &quot;filtros rápidos&quot;.) Sin embargo, la funcionalidad es la misma.)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Crear de un filtro rápido {#create}

Cualquier usuario de Analysis Workspace puede crear un filtro rápido.

Para crear un filtro rápido:

1. Elija uno de los siguientes métodos para empezar a crear el filtro rápido:

   * **Ad hoc (arrastrar y soltar):** Desde el carril izquierdo, arrastre un componente a la zona de colocación situada junto a la etiqueta **Filtrar** en el encabezado del panel y, a continuación, seleccione **Editar** para ajustar el filtro.

     ![Editar filtro ad hoc](assets/filter-adhoc-edit.png)

     >[!NOTE]
     >
     > Tenga en cuenta lo siguiente al crear un filtro rápido ad hoc (arrastrar y soltar):
     > * No se admiten los siguientes tipos de componentes: métricas calculadas y dimensiones, así como métricas a partir de las cuales no se pueden crear filtros.
     > * Para las dimensiones y eventos completos, Analysis Workspace crea filtros de evento &quot;existe&quot;. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
     > * Si se suelta sin especificar o como “ninguno” en la zona de colocación de filtros, se convierten automáticamente en un filtro “no existe”, de modo que se los trate adecuadamente en la segmentación.


   * **Uso del icono de filtro:** En una tabla de forma libre, seleccione **Filtrar** en el encabezado del panel.

     ![Filtro de segmento](assets/quick-seg1.png)

1. Ajuste cualquiera de las siguientes opciones:

   | Configuración | Descripción |
   | --- | --- |
   | [!UICONTROL Nombre] | El nombre predeterminado de un filtro es una combinación de los nombres de reglas del filtro. Puede cambiar el nombre del filtro por otro más descriptivo. |
   | [!UICONTROL Incluir/excluir] | Puede incluir o excluir componentes en la definición del filtro, pero no ambos. |
   | [!UICONTROL Contenedor de visita/visita individual/visitante] | Los filtros rápidos incluyen un [contenedor de filtros](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=es#filter-containers) que solo permite incluir una dimensión, métrica o intervalo de fechas en el filtro (o excluirlo de) él. [!UICONTROL Visitante] contiene datos globales específicos de la persona en las visitas y vistas de página. A [!UICONTROL Visita] Un contenedor de permite establecer reglas para desglosar los datos de la persona en función de las visitas y un [!UICONTROL Visita] El contenedor de permite desglosar la información de la persona en función de las vistas de página individuales. El contenedor predeterminado es [!UICONTROL Visita individual]. |
   | [!UICONTROL Componentes] (dimensión/métrica/intervalo de fechas) | Defina hasta 3 reglas añadiendo componentes (dimensiones, métricas, intervalos de fechas o valores de dimensión). Existen tres formas de encontrar el componente correcto:<ul><li>Empiece a escribir y el generador de filtros rápidos encuentra automáticamente el componente adecuado.</li><li>Utilice la lista desplegable para buscar el componente.</li><li>Arrástrelos y suéltelos desde el carril izquierdo.</li></ul> |
   | [!UICONTROL Operador] | Utilice el menú desplegable para buscar operadores estándar y operadores de [!UICONTROL recuento distintos]. Consulte [Operadores de filtro](operators.md). |
   | Signo más (+) | Añadir otra regla |
   | Calificadores AND/OR | Puede agregar calificadores AND u OR a las reglas, pero no puede combinar AND y OR en una sola definición de filtro. |
   | [!UICONTROL Aplicar] | Aplique este filtro al panel. Si el filtro no contiene datos, se le preguntará si desea continuar. |
   | [!UICONTROL Abrir creador] | Se abre el Generador de filtros. Después de guardar o aplicar el filtro en el Generador de filtros, ya no se considera un filtro rápido. Forma parte de la biblioteca de filtros de lista de componentes. <p>Para que el componente esté disponible en todos los proyectos y en el carril izquierdo, seleccione la opción [!UICONTROL **Haga que este filtro esté disponible para todos los proyectos y añádalo a la lista de componentes**].</p><p>Para obtener más información, consulte la sección [Guardar un filtro rápido como filtro de lista de componentes](#save-a-quick-filter-as-a-component-list-filter) en este artículo.</p><p>**Nota:** Solo los usuarios con el permiso de Creación de segmentos en [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=es) Puede abrir el Generador de filtros.</p> |
   | [!UICONTROL Cancelar] | Cancele este filtro rápido (no lo aplique). |
   | [!UICONTROL Intervalo de fechas] | El validador utiliza el intervalo de fechas del panel para la búsqueda de datos. Sin embargo, cualquier intervalo de fechas aplicado en un filtro rápido anula el intervalo de fechas del panel en la parte superior del panel. |
   | Vista previa (parte superior derecha) | Le permite ver si tiene un filtro válido y su amplitud. Representa el desglose del conjunto de datos que verá si aplica este filtro. Podría recibir un aviso que indique que este filtro no tiene datos. En este caso, puede continuar o cambiar la definición del filtro. |

1. Seleccionar [!UICONTROL **Aplicar**] para guardar los cambios.

## Edición de un filtro rápido {#edit}

1. Pase el ratón sobre el filtro rápido que quiere editar y, a continuación, seleccione la opción **Editar** icono.

   ![Editar filtro ad hoc](assets/filter-adhoc-edit.png)

1. Edite la definición del filtro o el nombre del filtro.
1. Seleccionar [!UICONTROL **Aplicar**] para guardar los cambios.

## Guardar un filtro rápido como filtro de lista de componentes {#save}

>[!IMPORTANT]
>
> Tenga en cuenta lo siguiente al guardar un filtro rápido:
> 
> * Para guardar un filtro rápido, necesita el permiso de Creación de segmentos en la [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=es).
> 
> * Después de guardar o aplicar el filtro, ya no se puede editar en el generador de filtros rápidos. En su lugar, debe utilizar el Generador de filtros normal.

Puede elegir guardar filtros rápidos como filtros de lista de componentes. Las ventajas de los filtros de lista de componentes incluyen:

* Disponibilidad en todos los proyectos de Workspace
* Admitir filtros más complejos, así como filtros secuenciales

Puede guardar filtros desde el generador de filtros rápidos o desde el [!UICONTROL Generador de filtros].

### Guardar en el generador de filtros rápidos {#save2}

1. Después de aplicar el filtro rápido, pase el ratón sobre él y seleccione el icono de información (i).
1. Seleccionar **[!UICONTROL Poner a disposición de todos los proyectos y añadirlos a la lista de componentes]**.
1. (Opcional) Cambie el nombre del filtro.
1. Seleccione **[!UICONTROL Guardar]**.

   El filtro ahora aparece en la lista de componentes en el carril izquierdo. Tenga en cuenta también que la barra lateral del filtro cambia de azul claro a azul más oscuro, lo que indica que ya no se puede editar ni abrir en el generador de filtros rápidos.

### Guardar en el Generador de filtros {#save3}

1. Después de aplicar el filtro rápido, pase el ratón sobre él y seleccione el icono de información (i).
1. Seleccione **[!UICONTROL Guardar filtro]**
1. (Opcional) Cambie el nombre del filtro y seleccione [!UICONTROL **Aplicar**].

   Vuelva al espacio de trabajo y observe que la barra lateral del filtro cambia de azul claro a azul más oscuro, lo que indica que ya no se puede editar ni abrir en el generador de filtros rápidos. Al guardarlo, pasa a formar parte de la lista de componentes.

   ![Filtrado de la lista de componentes](assets/quick-seg4.png)

Después de aplicar el filtro, puede elegir agregarlo a la lista de componentes del filtro y ponerlo a disposición de todos los proyectos.

1. Pase el ratón sobre el filtro guardado y seleccione el icono de lápiz.

1. Seleccionar [!UICONTROL **Abrir creador**].

1. En la parte superior del Generador de filtros, observe este cuadro de diálogo:

   ![Cuadro de diálogo Filtro](assets/project-only-filter-dialog.png)

1. Seleccione la casilla que hay junto a **[!UICONTROL Ponga esta filtr a disposición de todos los proyectos y agréguela a la lista de componentes.]**

1. Seleccione **[!UICONTROL Guardar]**.

   El filtro ahora aparece en la lista de componentes del filtro para todos los proyectos.
También puede [compartir el filtro](/help/components/filters/filters-share.md) con otras personas de su organización.

## Ejemplo de filtro rápido

El siguiente ejemplo de filtro combina dimensiones y métricas:

![Ejemplo de definición de filtro](assets/quick-seg2.png)

