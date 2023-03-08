---
description: Los administradores son responsables de supervisar el estado del diccionario de datos. Esto incluye si los componentes están recopilando datos, están aprobados, contienen descripciones y no tienen duplicados.
title: Monitorización del estado del diccionario de datos
feature: Components
role: Admin
source-git-commit: 5929d56bef8f756967926482f80014db0d43d3e3
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 94%

---

# Monitorización del estado del diccionario de datos

{{release-limited-testing}}

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

1. Seleccione el icono del diccionario de datos en la parte izquierda de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md).)

   Se muestra la ventana Diccionario de datos.

   ![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que el grupo de informes correcto está seleccionado en el menú desplegable.

1. En la pestaña [!UICONTROL **Salud del diccionario**], seleccione [!UICONTROL **Ver**] junto a cualquiera de las siguientes opciones:

   * [!UICONTROL **faltan descripciones en los componentes**]

   * [!UICONTROL **los componentes tienen duplicados**]

   * [!UICONTROL **los componentes no tienen datos conectados**]

   Según lo que seleccione, el filtro adecuado se aplica al diccionario de datos y solo se muestran los componentes relevantes.

1. Edite cualquiera de los componentes para mejorar el estado del diccionario de datos. Para obtener información acerca de cómo editar un componente en el diccionario de datos, consulte [Editar entradas de componentes en el diccionario de datos](/help/components/data-dictionary/edit-entries-data-dictionary.md).