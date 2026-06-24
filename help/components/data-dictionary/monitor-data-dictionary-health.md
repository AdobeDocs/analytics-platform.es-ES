---
description: Los administradores son responsables de supervisar el estado del diccionario de datos. Esto incluye si los componentes están recopilando datos, están aprobados, contienen descripciones y no tienen duplicados.
title: Monitorización del estado del diccionario de datos
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: b7493ad9283b5830c36b8e3ac942bf9295b693f8
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 88%

---

# Monitorización del estado del diccionario de datos {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Diccionario de datos"
>abstract="Cuando se selecciona esta opción, el componente principal se comparte con todas las personas que tienen acceso a los componentes duplicados (tanto los propietarios como cualquier persona con los que se comparten los componentes). A continuación, estos usuarios pueden seleccionar el componente principal de la lista de componentes para proyectos futuros. Sin embargo, no pueden editar el componente, aunque sean los propietarios de un componente duplicado que se haya consolidado. <br/>Esta opción solo está disponible cuando el componente principal es un segmento, una métrica calculada o un intervalo de fechas. Las métricas y dimensiones siempre están disponibles para todos los usuarios.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="Compartir componente principal"
>abstract="Cuando se selecciona esta opción, el componente principal se comparte con todas las personas que tienen acceso a los componentes duplicados (tanto los propietarios como cualquier persona con los que se comparten los componentes). A continuación, estos usuarios pueden seleccionar el componente principal de la lista de componentes para proyectos futuros. Sin embargo, no pueden editar el componente, aunque sean los propietarios de un componente duplicado que se haya consolidado. <br/>Esta opción solo está disponible cuando el componente principal es un segmento, una métrica calculada o un intervalo de fechas. Las métricas y dimensiones siempre están disponibles para todos los usuarios.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="Eliminar duplicados reemplazados"
>abstract="Cuando se selecciona esta opción, los duplicados consolidados ya no están disponibles para su uso. Anule la selección de esta opción si desea que los duplicados sigan estando disponibles."

<!-- markdownlint-enable MD034 -->

Los administradores de Customer Journey Analytics son responsables de mantener un diccionario de datos en buen estado.

## Características de un diccionario de datos correcto

Un diccionario de datos correcto es aquel en el que todos los componentes:

* Se están utilizando y recopilando datos

* Incluyen descripciones útiles para que los usuarios sepan cómo utilizarlas mejor

* Están libres de duplicados innecesarios

* Están aprobados por el administrador

## Comprobar el estado del diccionario de datos

Para identificar problemas de estado en el diccionario de datos:

1. Creación de un proyecto de Analysis Workspace.

1. Seleccione el icono del diccionario de datos en la parte izquierda de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Vista del administrador del diccionario de datos que muestra el estado del diccionario](assets/data-dictionary-admin.png)

1. Asegúrese de que está seleccionada la vista de datos correcta en el menú desplegable.

1. En la pestaña [!UICONTROL **Salud del diccionario**], seleccione [!UICONTROL **Ver**] junto a cualquiera de las siguientes opciones:

   * [!UICONTROL **faltan descripciones en los componentes**]

   * [!UICONTROL **los componentes tienen duplicados**]

   * [!UICONTROL **los componentes no tienen datos conectados**]

   Según lo que seleccione, el segmento adecuado se aplicará al diccionario de datos y solo se mostrarán los componentes relevantes.

1. Edite cualquiera de los componentes para mejorar el estado del diccionario de datos. Para obtener información acerca de cómo editar un componente en el diccionario de datos, consulte [Editar entradas de componentes en el diccionario de datos](/help/components/data-dictionary/edit-entries-data-dictionary.md).
