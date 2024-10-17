---
title: Información general de uso del producto
description: Vea información e informes sobre cómo su organización utiliza Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: b3d33561cc29aa1d37efa9f943bc145c16be814c
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# Información general de uso del producto

{{release-limited-testing}}

El uso del producto permite a su organización ver datos de análisis sobre cómo utiliza su organización Customer Journey Analytics. Está disponible para todas las organizaciones que utilizan Customer Journey Analytics. Una vez activados, los siguientes componentes de Adobe Experience Platform se crean y conectan automáticamente. Todos estos componentes son de propiedad del sistema, de solo lectura y no se pueden editar.

* Un esquema en Adobe Experience Platform
* Un conjunto de datos en Adobe Experience Platform
* Una conexión en el Customer Journey Analytics
* Una vista de datos en Customer Journey Analytics

Toda la recopilación y configuración de datos se configura automáticamente una vez que se ha activado. Cada vez que un usuario realiza una acción en Analysis Workspace, esta se rastrea y está disponible para la creación de informes.

>[!IMPORTANT]
>
>Esta función cuenta para los límites de filas contractuales en Adobe Experience Platform. Asegúrese de que su organización puede admitir los datos generados por esta función antes de habilitarla.

## Dimensiones disponibles

Al habilitar Uso del producto, están disponibles las siguientes dimensiones. Si desea cambiar cualquier configuración de dimensión, cree una copia de la vista de datos propiedad del sistema y utilice la vista de datos copiada en Analysis Workspace.

| Dimensión | Descripción |
| --- | --- |
| Nombre de la acción | El tipo de acción que realizó el usuario. Puede utilizar esta dimensión como cualquier métrica deseada creando una copia en la configuración de la vista de datos. |
| Modelo de atribución utilizado | El tipo de modelo de atribución que utiliza el componente. |
| Componente | Campo derivado que incluye el tipo y el nombre del componente. |
| Tipo de componente | El tipo de componente añadido, eliminado o modificado. |
| Usuario de inicio de sesión | El usuario que realizó la acción. |
| Panel utilizado | Panel en el que se añadió, eliminó o modificó el componente. |
| Nombre del proyecto | Nombre descriptivo del proyecto. |
| Tipo de proyecto | El tipo de proyecto. |
| ID de usuario | El ID de usuario que activó el evento. |
| Visualización utilizada | La visualización que se añadió, eliminó o modificó. |

El uso del producto no rastrea componentes de proyecto individuales cuando un proyecto simplemente se abre o se visualiza. Sin embargo, la acción del usuario de abrir un proyecto se rastrea.
