---
title: Información general sobre el uso del producto
description: Vea información e informes sobre cómo su organización utiliza Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 5b5d4cb17ee73415dbd77bbf0964fc3d4e513cf0
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 89%

---

# Información general sobre el uso del producto

El uso del producto le permite a su organización ver datos de análisis sobre cómo su organización utiliza Customer Journey Analytics. Está disponible para todas las organizaciones que utilizan Customer Journey Analytics. Una vez habilitados, los siguientes componentes de Adobe Experience Platform se crean y conectan automáticamente. Todos estos componentes son propiedad del sistema, son de solo lectura y no se pueden editar.

* Un esquema de Adobe Experience Platform
* Un conjunto de datos de Adobe Experience Platform
* Una conexión de Customer Journey Analytics
* Una vista de datos de Customer Journey Analytics

Toda la recopilación y configuración de datos se configura automáticamente una vez que se haya habilitado. Cada vez que un usuario realiza una acción en Analysis Workspace, se rastrea y está disponible para la creación de informes.

>[!IMPORTANT]
>
>Esta función cuenta para los límites de filas contractuales en Adobe Experience Platform. Asegúrese de que su organización puede alojar los datos generados por esta función antes de habilitarla.

## Habilitar el uso del producto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL Uso del producto]**

Si navega hasta esta sección de la interfaz en Customer Journey Analytics, accederá a [Configuración de datos](data-settings.md), donde podrá habilitar esta función.

## Dimensiones disponibles

Al habilitar el uso del producto, están disponibles las siguientes dimensiones. Si desea cambiar alguna configuración de dimensión, cree una copia de la vista de datos propiedad del sistema y utilice la vista de datos copiada en Analysis Workspace.

* **[!UICONTROL Nombre de acción]**: tipo de acción que realizó el usuario. Puede utilizar esta dimensión como cualquier métrica deseada creando una copia en la configuración de la vista de datos. Los elementos de dimensión incluyen:
   * [!UICONTROL Añadir atribución]
   * [!UICONTROL Añadir componente]
   * [!UICONTROL Añadir panel]
   * [!UICONTROL Añadir visualización]
   * [!UICONTROL Crear un análisis guiado]
   * [!UICONTROL Crear nuevo proyecto]
   * [!UICONTROL Depurar componentes]
   * [!UICONTROL Descargar CSV]
   * [!UICONTROL Descargar PDF]
   * [!UICONTROL Cargar análisis guiado]
   * [!UICONTROL Cargar proyecto]
   * [!UICONTROL Nuevo cuadro de resultados cargado]
   * [!UICONTROL Abrir diccionario de datos]
   * [!UICONTROL Crear subtítulos inteligentes]
   * [!UICONTROL Uso compartido del proyecto]
   * [!UICONTROL Ejecutar panel de experimentación]
   * [!UICONTROL Guardar proyecto]
   * [!UICONTROL Cuadro de resultados guardado]
   * [!UICONTROL Enviar archivo]
   * [!UICONTROL Enviar archivo según lo programado]
   * [!UICONTROL Compartir proyecto con cualquiera]
   * [!UICONTROL Compartir proyecto con usuarios de Workspace]
   * [!UICONTROL Cambiar vista de datos]
* **[!UICONTROL Modelo de atribución utilizado]**: tipo de modelo de atribución que utiliza el componente. Los elementos de dimensión incluyen:
   * [!UICONTROL Último contacto]
   * [!UICONTROL Primer contacto]
   * [!UICONTROL Lineal]
   * [!UICONTROL Participación]
   * [!UICONTROL Mismo contacto]
   * [!UICONTROL En forma de U]
   * [!UICONTROL Curva J]
   * [!UICONTROL J inversa]
   * [!UICONTROL Deterioro de tiempo]
   * [!UICONTROL Personalizado]
   * [!UICONTROL Algorítmico]
* **[!UICONTROL Id. de componente]**: Id. del componente que se agregó, eliminó o modificó.
* **[!UICONTROL Nombre de componente]**: El nombre descriptivo del componente que se agregó, eliminó o modificó.
* **[!UICONTROL Tipo de componente]**: el tipo de componente que se ha añadido, eliminado o modificado. Los elementos de dimensión incluyen:
   * [!UICONTROL Dimensión]
   * [!UICONTROL Métrica]
   * [!UICONTROL Segmento]
   * [!UICONTROL Métrica calculada]
   * [!UICONTROL Intervalo de fecha]
   * [!UICONTROL Anotación]
   * [!UICONTROL Alerta]
* **[!UICONTROL ID de vista de datos]**: El ID de la vista de datos.
* **[!UICONTROL Nombre de vista de datos]**: El nombre descriptivo de la vista de datos.
* **[!UICONTROL Usuario de inicio de sesión]**: el usuario que ha realizado la acción.
* **[!UICONTROL Panel utilizado]**: El panel que se agregó, eliminó o modificó. Los elementos de dimensión incluyen:
   * [!UICONTROL Atribución]
   * [!UICONTROL Panel en blanco]
   * [!UICONTROL Experimentación]
   * [!UICONTROL Freeform]
   * [!UICONTROL Elemento siguiente o anterior]
   * [!UICONTROL Información rápida]
   * [!UICONTROL Tendencias]
   * [!UICONTROL Canal]
   * [!UICONTROL Crecimiento de usuarios]
   * [!UICONTROL Impacto]
   * [!UICONTROL Flujo de usuarios]
   * [!UICONTROL Retención]
   * [!UICONTROL Matriz de características]
* **[!UICONTROL Id. de proyecto]**: Id. del proyecto.
* **[!UICONTROL Nombre de proyecto]**: el nombre descriptivo del proyecto.
* **[!UICONTROL Tipo de proyecto]**: el tipo de proyecto. Los elementos de dimensión incluyen:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualización utilizada]**: la visualización que se ha añadido, eliminado o modificado. Los elementos de dimensión incluyen:
   * [!UICONTROL Tabla de forma libre]
   * [!UICONTROL Tabla de cohorte]
   * [!UICONTROL Visita en orden previsto]
   * [!UICONTROL Flujo]
   * [!UICONTROL Informe breve del lienzo de recorridos]
   * [!UICONTROL Área]
   * [!UICONTROL Area stacked]
   * [!UICONTROL Barra]
   * [!UICONTROL Barra apilada]
   * [!UICONTROL Bullet]
   * [!UICONTROL Combo]
   * [!UICONTROL Anillo]
   * [!UICONTROL Histograma]
   * [!UICONTROL Barra horizontal]
   * [!UICONTROL Barra apilada horizontal]
   * [!UICONTROL Resumen de las métricas clave]
   * [!UICONTROL Líneas]
   * [!UICONTROL Mapa]
   * [!UICONTROL Dispersión]
   * [!UICONTROL Encabezado de sección]
   * [!UICONTROL Cambio de resumen]
   * [!UICONTROL Número de resumen]
   * [!UICONTROL Texto]
   * [!UICONTROL Gráfico de rectángulos]
   * [!UICONTROL Venn]

El uso del producto no rastrea componentes individuales del proyecto cuando un proyecto simplemente se abre o se visualiza. Sin embargo, la acción del usuario de abrir un proyecto se rastrea.

## Plantilla disponible

Hay disponible una [plantilla de Adobe](/help/analysis-workspace/templates/use-templates.md) que utiliza los componentes generados automáticamente a partir de esta característica.

**[!UICONTROL Plantillas de Adobe]** > **[!UICONTROL Otras]** > **[!UICONTROL Información general del uso del producto]**

Seleccione la vista de datos que Uso del producto creó automáticamente en el selector de vista de datos y, a continuación, seleccione la plantilla **[!UICONTROL Información general del uso del producto]**. Seleccione **[!UICONTROL Vista previa]** para ver qué paneles utiliza la plantilla y conocer los casos de uso ideales, o bien seleccione **[!UICONTROL Usar plantilla]** para abrirla en Analysis Workspace.
