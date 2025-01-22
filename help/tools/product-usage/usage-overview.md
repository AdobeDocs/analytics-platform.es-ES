---
title: Información general de uso del producto
description: Vea información e informes sobre cómo su organización utiliza Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: ae22dc84406427567d45b670aa9737ea3a8b2f7b
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 12%

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

## Habilitar el uso del producto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL Uso del producto]**

Si navega a esta sección de la interfaz en Customer Journey Analytics, accederá a [Configuración de datos](data-settings.md), donde podrá habilitar esta característica.

## Dimensiones disponibles

Al habilitar Uso del producto, están disponibles las siguientes dimensiones. Si desea cambiar cualquier configuración de dimensión, cree una copia de la vista de datos propiedad del sistema y utilice la vista de datos copiada en Analysis Workspace.

* **[!UICONTROL Nombre de acción]**: Tipo de acción que realizó el usuario. Puede utilizar esta dimensión como cualquier métrica deseada creando una copia en la configuración de la vista de datos. Los elementos de Dimension incluyen:
   * [!UICONTROL Agregar atribución]
   * [!UICONTROL Agregar componente]
   * [!UICONTROL Agregar panel]
   * [!UICONTROL Agregar visualización]
   * [!UICONTROL Crear nuevo análisis guiado]
   * [!UICONTROL Crear nuevo proyecto]
   * [!UICONTROL Depurar componentes]
   * [!UICONTROL Descargar CSV]
   * [!UICONTROL Descargar PDF]
   * [!UICONTROL Análisis guiado de carga]
   * [!UICONTROL Cargar proyecto]
   * [!UICONTROL Se ha cargado el nuevo cuadro de resultados]
   * [!UICONTROL Abrir diccionario de datos]
   * [!UICONTROL Abrir subtítulos inteligentes]
   * [!UICONTROL Recurso compartido de proyecto]
   * [!UICONTROL Ejecutar panel de experimentación]
   * [!UICONTROL Guardar proyecto]
   * [!UICONTROL Informe de valoración guardado]
   * [!UICONTROL Enviar archivo]
   * [!UICONTROL Enviar archivo según lo programado]
   * [!UICONTROL Compartir proyecto con alguien]
   * [!UICONTROL Compartir proyecto con usuarios de Workspace]
* **[!UICONTROL Modelo de atribución utilizado]**: Tipo de modelo de atribución que utiliza el componente. Los elementos de Dimension incluyen:
   * [!UICONTROL Último contacto]
   * [!UICONTROL Primer contacto]
   * [!UICONTROL Lineal]
   * [!UICONTROL Participación]
   * [!UICONTROL Mismo contacto]
   * [!UICONTROL Forma de U]
   * [!UICONTROL Curva J]
   * [!UICONTROL J inversa]
   * [!UICONTROL Deterioro de tiempo]
   * [!UICONTROL Personalizado]
   * [!UICONTROL Algorítmico]
* **[!UICONTROL Nombre de componente]**: El nombre del componente que se agregó, eliminó o modificó.
* **[!UICONTROL Tipo de componente]**: El tipo de componente que se agregó, eliminó o modificó. Los elementos de Dimension incluyen:
   * [!UICONTROL Dimensión]
   * [!UICONTROL Métrica]
   * [!UICONTROL Filtro]
   * [!UICONTROL Métrica calculada]
   * [!UICONTROL Intervalo de fecha]
   * [!UICONTROL Anotación]
   * [!UICONTROL Alerta]
* **[!UICONTROL Usuario de inicio de sesión]**: El usuario que realizó la acción.
* **[!UICONTROL Panel utilizado]**: Panel donde se agregó, eliminó o modificó el componente. Los elementos de Dimension incluyen:
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
* **[!UICONTROL Nombre de proyecto]**: El nombre descriptivo del proyecto.
* **[!UICONTROL Tipo de proyecto]**: El tipo de proyecto. Los elementos de Dimension incluyen:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL ID de usuario]**: El ID de usuario que activó el evento.
* **[!UICONTROL Visualización utilizada]**: La visualización que se agregó, eliminó o modificó. Los elementos de Dimension incluyen:
   * [!UICONTROL Tabla de forma libre]
   * [!UICONTROL Tabla de cohorte]
   * [!UICONTROL Visita en orden previsto]
   * [!UICONTROL Flujo]
   * [!UICONTROL Informe breve de lienzo de Recorrido]
   * [!UICONTROL Área]
   * [!UICONTROL Area stacked]
   * [!UICONTROL Barra]
   * [!UICONTROL Barra apilada]
   * [!UICONTROL Bullet]
   * [!UICONTROL Combo]
   * [!UICONTROL Anillo]
   * [!UICONTROL Histograma]
   * [!UICONTROL Barra horizontal]
   * [!UICONTROL Barra horizontal apilada]
   * [!UICONTROL Resumen de métricas clave]
   * [!UICONTROL Líneas]
   * [!UICONTROL Mapa]
   * [!UICONTROL Dispersión]
   * [!UICONTROL Encabezado de sección]
   * [!UICONTROL Cambio de resumen]
   * [!UICONTROL Número de resumen]
   * [!UICONTROL Texto]
   * [!UICONTROL Gráfico de rectángulos]
   * [!UICONTROL Venn]

El uso del producto no rastrea componentes de proyecto individuales cuando un proyecto simplemente se abre o se visualiza. Sin embargo, la acción del usuario de abrir un proyecto se rastrea.
