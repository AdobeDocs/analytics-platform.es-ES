---
title: Información general de uso del producto
description: Vea información e informes sobre cómo su organización utiliza Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: 5c18fd78a71ddffef62dc3ac69f1abc3b42bddda
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 7%

---

# Información general de uso del producto

El uso del producto permite a su organización ver datos de análisis sobre cómo utiliza su organización Customer Journey Analytics. Está disponible para todas las organizaciones que utilizan Customer Journey Analytics. Una vez activados, los siguientes componentes de Adobe Experience Platform se crean y conectan automáticamente:

* Un esquema en Adobe Experience Platform. Este esquema es de solo lectura y no se puede editar.
* Un conjunto de datos en Adobe Experience Platform. La configuración de este conjunto de datos es de solo lectura y no se puede editar.
* Una conexión en Customer Journey Analytics. La configuración de esta conexión es de solo lectura y no se puede editar.
* Una vista de datos en Customer Journey Analytics. Puede editar esta vista de datos o crear más vistas de datos con la misma conexión.

Toda la recopilación y configuración de datos se configura automáticamente una vez que se ha activado. Cada vez que un usuario realiza una acción en Analysis Workspace, esta se rastrea y está disponible para la creación de informes.

>[!IMPORTANT]
>
>Esta función se contabiliza dentro de los límites de datos contractuales en Adobe Experience Platform. Asegúrese de que su organización puede admitir los datos generados por esta función antes de habilitarla.

## Dimensiones disponibles

Al habilitar Uso del producto, están disponibles las siguientes dimensiones:

| Dimensión | Descripción |
| --- | --- |
| Nombre de la acción | El tipo de acción que realizó el usuario. Puede utilizar esta dimensión como cualquier métrica deseada creando una copia en la configuración de la vista de datos. |
| Modelo de atribución utilizado | El tipo de modelo de atribución que utiliza el componente actual. |
| Componente | Campo derivado. |
| Tipo de componente | El tipo de componente añadido, eliminado o modificado. |
| Conexión | La conexión que utiliza el proyecto. |
| Vista de datos | La vista de datos que utiliza el proyecto. |
| Función | Función que utiliza el proyecto. |
| Identificador | El identificador único del evento. |
| Usuario de inicio de sesión | El usuario que realizó la acción. |
| Panel utilizado | Panel en el que se añadió, eliminó o modificó el componente. |
| Proyecto  | Campo derivado. |
| Nombre del proyecto | Nombre descriptivo del proyecto. |
| Tipo de proyecto | El tipo de proyecto. |
| ID de usuario | El ID de usuario que activó el evento. |
| Visualización utilizada | La visualización que se añadió, eliminó o modificó. |

El uso del producto no rastrea componentes de proyecto individuales cuando un proyecto simplemente se abre o se visualiza. Sin embargo, la acción del usuario de abrir un proyecto se rastrea.
