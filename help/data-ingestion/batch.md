---
title: Ingesta y uso de datos por lotes
description: Explicar cómo ingerir y utilizar datos por lotes en el Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: dd46adee-821f-489c-9350-abcfffe7cc3c
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '1954'
ht-degree: 5%

---

# Ingesta y uso de datos por lotes

En esta guía de inicio rápido se explica cómo introducir datos por lotes en Adobe Experience Platform y, a continuación, utilizarlos en Customer Journey Analytics.

Para lograr esto, debe:

- **Configuración de un esquema y un conjunto de datos** en Adobe Experience Platform para definir el modelo (esquema) de los datos que desea recopilar y dónde recopilar realmente los datos (conjunto de datos).

- **Uso de flujos de trabajo** para cargar fácilmente los datos por lotes en el conjunto de datos configurado en Adobe Experience Platform.

- **Configuración de una conexión** en Customer Journey Analytics. Esta conexión debe incluir (al menos) su conjunto de datos de Adobe Experience Platform.

- **Configuración de una vista de datos** en Customer Journey Analytics para definir las métricas y las dimensiones que desea utilizar en Analysis Workspace.

- **Configuración de un proyecto** en Customer Journey Analytics para crear sus informes y visualizaciones.

>[!NOTE]
>
>Esta es una guía simplificada sobre cómo introducir datos por lotes en Adobe Experience Platform y utilizarlos en Customer Journey Analytics. Se recomienda estudiar la información adicional cuando se haga referencia a ella.

## Configuración de un esquema y un conjunto de datos

Para introducir datos en Adobe Experience Platform, primero debe definir qué datos desea recopilar. Todos los datos introducidos en Adobe Experience Platform deben cumplir una estructura estándar y desnormalizada para que las funciones y características descendentes puedan reconocerlos y actuar en consecuencia. Experience Data Model (XDM) es el marco estándar que proporciona esta estructura en forma de esquemas.

Una vez definido un esquema, se utilizan uno o más conjuntos de datos para almacenar y administrar la recopilación de datos. Un conjunto de datos es una construcción de almacenamiento y administración para una colección de datos, normalmente una tabla, que contiene un esquema (columnas) y campos (filas).

Todos los datos introducidos en Adobe Experience Platform deben cumplir un esquema predefinido para que se puedan conservar como conjunto de datos.

### Configuración de un esquema

Para este inicio rápido, debe recopilar algunos datos de fidelidad, por ejemplo, ID de fidelidad, puntos de fidelidad y estado de fidelidad.
Para ello, primero debe definir un esquema que modele estos datos.

Para configurar el esquema:

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Esquemas]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

2. Select **[!UICONTROL Crear esquema]**. Select **[!UICONTROL Perfil individual XDM]** de la lista de opciones.

   ![Creación de un esquema](./assets/create-schema.png)

   >[!INFO]
   >
   >    Se utiliza un esquema de perfil individual para modelar el perfil _attributes_ (como correo electrónico, estado de lealtad, puntos de lealtad). Un esquema de eventos de experiencia se utiliza para modelar la variable _comportamiento_ de un perfil (como la vista de página, agregar al carro de compras).


3. En el [!UICONTROL Esquema sin título] pantalla:

   1. Introduzca un nombre para mostrar para el esquema y (opcional) una descripción.

      ![Asigne un nombre al esquema](./assets/name-loyalty-schema.png)

   2. Select **[!UICONTROL + Agregar]** en [!UICONTROL Grupos de campo].

      ![Agregar grupo de campos](./assets/add-field-group-button.png)

      Los grupos de campos son colecciones reutilizables de objetos y atributos que permiten ampliar fácilmente el esquema.

   3. En el [!UICONTROL Agregar grupos de campos] seleccione **[!UICONTROL Detalles de fidelidad]** grupo de campos de la lista.

      ![Grupo de campos de ExperienceEvent del SDK web de AEP](./assets/loyalty-fieldgroup.png)

      Puede seleccionar el botón de vista previa para ver una vista previa de los campos que forman parte de este grupo de campos.

      ![Campo SDK web de AEP ExperienceEvent vista previa de grupo](./assets/loyalty-fieldgroup-preview.png)

      Select **[!UICONTROL Atrás]** para cerrar la vista previa.

   4. Select **[!UICONTROL Agregar grupos de campos]**.

4. Select **[!UICONTROL +]** junto al nombre del esquema en la [!UICONTROL Estructura] panel.

   ![Ejemplo de botón Agregar campo de esquema](./assets/example-loalty-schema-plus.png)

5. En el [!UICONTROL Propiedades de campo] , introduzca `Identification` como nombre, **[!UICONTROL Identificación]** como el [!UICONTROL Nombre para mostrar], seleccione **[!UICONTROL Objeto]** como el [!UICONTROL Tipo] y seleccione **[!UICONTROL Perfil principal v2]** como el [!UICONTROL Grupo de campos].

   ![Objeto de identificación](./assets/identifcation-loyalty-field.png)

   Esto añade capacidades de identificación al esquema. En su caso, desea identificar la información de fidelidad utilizando la dirección de correo electrónico de los datos del lote.

   Select **[!UICONTROL Aplicar]** para añadir este objeto al esquema.

6. Seleccione el **[!UICONTROL email]** en el objeto de identificación que acaba de añadir y seleccione **[!UICONTROL Identidad]** y **[!UICONTROL Correo electrónico]** de la variable [!UICONTROL Área de nombres de identidad] en el [!UICONTROL Propiedades de campo] panel.

   ![Especificar correo electrónico como identidad](./assets/specify-email-loyalty-id.png)

   Usted especifica la dirección de correo electrónico como la identidad que el servicio de identidad de Adobe Experience Platform puede utilizar para combinar (unir) perfiles.

   Select **[!UICONTROL Aplicar]**. Verá que aparece un icono de huella digital en el atributo de correo electrónico.

   Seleccione **[!UICONTROL Guardar]**.

7. Seleccione el nivel raíz del esquema (con el nombre del esquema) y, a continuación, seleccione el **[!UICONTROL Perfil]** .

   Se le pedirá que habilite el esquema para el perfil. Una vez habilitados, cuando los datos se incorporan en conjuntos de datos basados en este esquema, esos datos se combinan en el perfil del cliente en tiempo real.

   Consulte [Habilitar el esquema para utilizarlo en el perfil de cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) para obtener más información.

   >[!IMPORTANT]
   >
   >    Una vez guardado un esquema habilitado para perfil, ya no se puede deshabilitar para perfil.

   ![Habilitar esquema para perfil](./assets/enable-for-profile.png)

8. Select **[!UICONTROL Guardar]** para guardar el esquema.

Ha creado un esquema mínimo que modela los datos de fidelidad que puede introducir en Adobe Experience Platform. El esquema permite identificar perfiles mediante la dirección de correo electrónico. Al habilitar el esquema para el perfil, se asegura de que los datos del archivo por lotes se agregan al Perfil del cliente en tiempo real.

Consulte [Crear y editar esquemas en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) para obtener más información sobre cómo agregar y quitar grupos de campos y campos individuales a un esquema.

### Configuración de un conjunto de datos

Con el esquema, ha definido el modelo de datos. Ahora tiene que definir la construcción para almacenar y administrar esos datos. Esto se realiza mediante conjuntos de datos.

Para configurar el conjunto de datos:

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Conjuntos de datos]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

2. Select **[!UICONTROL Crear conjunto de datos]**.

   ![Crear conjunto de datos](./assets/create-dataset.png)

3. Select **[!UICONTROL Crear conjunto de datos a partir del esquema]**.

   ![Crear conjunto de datos a partir del esquema](./assets/create-dataset-from-schema.png)

4. Seleccione el esquema creado anteriormente y seleccione **[!UICONTROL Siguiente]**.

5. Asigne un nombre al conjunto de datos y (opcional) proporcione una descripción.

   ![Nombre del conjunto de datos](./assets/name-your-datatest.png)

6. Select **[!UICONTROL Finalizar]**.

7. Seleccione el **[!UICONTROL Perfil]** .

   Se le pedirá que habilite el conjunto de datos para el perfil. Una vez habilitado, el conjunto de datos enriquece los perfiles de clientes en tiempo real con sus datos introducidos.

   >[!IMPORTANT]
   >
   >    Solo se puede habilitar un conjunto de datos para el perfil cuando el esquema, al que se adhiere el conjunto de datos, también esté habilitado para el perfil.

   ![Habilitar esquema para perfil](./assets/loyalty-dataset-profile.png)

Consulte [Guía de la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) para obtener más información sobre cómo ver, previsualizar, crear o eliminar un conjunto de datos. Y cómo habilitar un conjunto de datos para el perfil del cliente en tiempo real.


## Usar flujos de trabajo

La funcionalidad del flujo de trabajo se utiliza para cargar los datos de lote en Adobe Experience Platform. El archivo por lotes de ejemplo que utiliza es un archivo CSV con el siguiente contenido:

```
email,loyaltyID,points,status
abrocking0@blog.com,793406,82.16,Silver
wnichol1@ycombinator.com,988654,40.39,Gold
paisbett2@slideshare.net,444897,91.25,Bronze
bdiamant3@xinhuanet.com,239658,57.87,Gold
ppales4@nsw.gov.au,365384,82.71,Silver
...
```

Para utilizar flujos de trabajo:

1. En la interfaz de usuario de Platform, seleccione **[!UICONTROL Flujos de trabajo]** en el carril izquierdo.

2. Select **[!UICONTROL Asignación de CSV al esquema XDM]**. Select **[!UICONTROL Launch]**.

   ![Asignar CSV a XDN](./assets/workflow-mapcsvtoxdm.png)

3. En el [!UICONTROL Asignación de CSV al esquema XDM] en la [!UICONTROL Detalles de flujo de datos] paso:

   Select **[!UICONTROL Conjunto de datos existente]**, seleccione su conjunto de datos en la lista de conjuntos de datos y asigne un nombre a su [!UICONTROL Nombre de flujo de datos].

   ![Flujo de datos](./assets/workflow-dataflowdetail.png)

   Seleccione **[!UICONTROL Siguiente]**.

4. En el [!UICONTROL Seleccionar datos] paso:

   Arrastrar y soltar o seleccionar **[!UICONTROL Elegir archivos]** para seleccionar el archivo CSV con datos de fidelidad. Verá una vista previa de los datos de fidelidad.

   ![Seleccionar datos](./assets/workflow-selectdata.png)

   Seleccione **[!UICONTROL Siguiente]**.

5. En el [!UICONTROL Asignación] paso:

   Asigne los datos del archivo CSV a los datos del esquema. Con AI, la funcionalidad del flujo de trabajo intenta asignar automáticamente los campos de datos por lotes a los campos de esquema.

   ![Asignar datos](./assets/workflow-dataflow-mapping.png)

   Puede usar **[!UICONTROL Vista previa de datos]** para ver una vista previa de los datos asignados.

   ![Previsualización de la asignación](./assets/workflow-dataflow-mapping-preview.png)

6. Select **[!UICONTROL Finalizar]** para empezar a introducir los datos de lote en Adobe Experience Platform.

Consulte [Asignar un archivo CSV a un esquema XDM existente](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema.html) para obtener más información sobre cómo asignar datos cuando los datos entrantes no son compatibles con el esquema XDM, utilice plantillas de asignación, utilice el campo calculado para asegurarse de que los datos del lote se ajustan a lo que el esquema espera, etc.


## Configuración de una conexión

Para utilizar los datos de Adobe Experience Platform en Customer Journey Analytics, se crea una conexión que incluye los datos resultantes de la configuración del esquema, el conjunto de datos y el flujo de trabajo.

Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform el Espacio de trabajo. Para informar sobre estos conjuntos de datos, primero debe establecer una conexión entre conjuntos de datos en Adobe Experience Platform y Workspace.

Para crear la conexión:

1. En la interfaz de usuario del Customer Journey Analytics, seleccione **[!UICONTROL Conexiones]** en la barra de navegación superior.

2. Select **[!UICONTROL Crear nueva conexión]**.

3. En el [!UICONTROL Conexión sin título] pantalla:

   Asigne un nombre a la conexión y describa su [!UICONTROL Configuración de conexión].

   Seleccione el simulador de pruebas correcto en el [!UICONTROL Sandbox] en [!UICONTROL Configuración de datos] y seleccione el número de eventos diarios en la [!UICONTROL Cantidad promedio de eventos diarios] lista.

   ![Configuración de conexión](./assets/cja-connections-1.png)

   Select **[!UICONTROL Agregar conjuntos de datos]**.

   En el [!UICONTROL Seleccionar conjuntos de datos] paso a paso [!UICONTROL Agregar conjuntos de datos]:

   - Seleccione el conjunto de datos que creó anteriormente (`Example Loyalty Dataset`) y cualquier otro conjunto de datos que desee incluir en la conexión.

      ![Añadir conjuntos de datos](./assets/cja-connections-2.png)

   - Seleccione **[!UICONTROL Siguiente]**.
   En el [!UICONTROL Configuración de conjuntos de datos] paso a paso [!UICONTROL Agregar conjuntos de datos]:

   - Para cada conjunto de datos:

      - Seleccione un [!UICONTROL ID de persona] de las identidades disponibles definidas en los esquemas de conjuntos de datos en Adobe Experience Platform.

      - Seleccione la fuente de datos correcta de la [!UICONTROL Tipo de fuente de datos] lista. Si especifica **[!UICONTROL Otro]** y, a continuación, agregue una descripción para la fuente de datos.

      - Establezca **[!UICONTROL Importar todos los datos nuevos]** y **[!UICONTROL Relleno de conjuntos de datos de datos existentes]** según sus preferencias.

      ![Configurar conjuntos de datos](./assets/cja-connections-3.png)

   - Select **[!UICONTROL Agregar conjuntos de datos]**.
   Seleccione **[!UICONTROL Guardar]**.

Consulte [Información general sobre conexiones](../connections/overview.md) para obtener más información sobre cómo crear y administrar una conexión y cómo seleccionar y combinar conjuntos de datos.

## Configuración de una vista de datos

Una vista de datos es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión. Especifica todas las dimensiones y métricas disponibles en Analysis Workspace y de qué columnas obtienen esos datos las dimensiones y métricas. Las vistas de datos se definen a fin de prepararse para la creación de informes en Analysis Workspace.

Para crear la vista de datos:

1. En la interfaz de usuario del Customer Journey Analytics, seleccione **[!UICONTROL Vistas de datos]** en la barra de navegación superior.

2. Select **[!UICONTROL Crear nueva vista de datos]**.

3. En el [!UICONTROL Configurar] paso:

   Seleccione la conexión en el [!UICONTROL Conexión] lista.

   Nombre y (opcionalmente) describa su conexión.

   ![Configuración de la vista de datos](./assets/cja-dataview-1.png)

   Select **[!UICONTROL Guardar y continuar]**.

4. En el [!UICONTROL Componentes] paso:

   Añada cualquier campo de esquema o componente estándar que desee incluir en el [!UICONTROL MÉTRICAS] o [!UICONTROL Dimension] cuadros de componentes.

   ![Componentes de la vista de datos](./assets/cja-dataview-2.png)

   Select **[!UICONTROL Guardar y continuar]**.

5. En el [!UICONTROL Configuración] paso:

   Configuración de ![vista de datos](./assets/cja-dataview-3.png)

   Deje la configuración tal como está y seleccione **[!UICONTROL Guardar y finalizar]**.

Consulte [Resumen de las vistas de datos](../data-views/data-views.md) para obtener más información sobre cómo crear y editar una vista de datos, qué componentes están disponibles para usar en la vista de datos y cómo usar la configuración de filtro y sesiones.


## Configuración de un proyecto

Analysis Workspace es una herramienta de navegador flexible que le permite crear análisis y compartir perspectivas rápidamente en función de sus datos. Los proyectos de Workspace se utilizan para combinar componentes de datos, tablas y visualizaciones con el fin de crear su análisis y compartirlo con cualquier persona de su organización.

Para crear el proyecto:

1. En la interfaz de usuario del Customer Journey Analytics, seleccione **[!UICONTROL Proyectos]** en la barra de navegación superior.

2. Select **[!UICONTROL Proyectos]** en el panel de navegación izquierdo.

3. Select **[!UICONTROL Crear proyecto]**.

   ![Proyecto de Workspace](./assets/cja-projects-1.png)

   Select **[!UICONTROL Proyecto en blanco]**.

   ![Workspace: proyecto en blanco](./assets/cja-projects-2.png)

4. Seleccione la vista de datos de la lista.

   ![Espacio de trabajo Seleccionar vista de datos](./assets/cja-projects-3.png).

5. Comience a arrastrar y soltar dimensiones y métricas en la [!UICONTROL Tabla improvisada] en el [!UICONTROL Panel] para crear su primer informe. Por ejemplo, arrastre `Program Points Balance` y `Page View` como métricas y `email` como dimensión para obtener una visión general rápida de los perfiles que han visitado su sitio web y forman parte del programa de fidelidad que recopila puntos de fidelidad.

   ![Workspace: primer informe](./assets/cja-projects-5.png)

Consulte [Información general de Analysis Workspace](../analysis-workspace/home.md) para obtener más información sobre cómo crear proyectos y crear su análisis mediante componentes, visualizaciones y paneles.

>[!SUCCESS]
>
>Ha completado todos los pasos. Empezando por definir qué datos de lealtad desea recopilar (esquema) y dónde almacenarlos (conjunto de datos) en Adobe Experience Platform, se configuró un flujo de trabajo para cargar los datos de fidelidad en lote en un conjunto de datos. Ha definido una conexión en Customer Journey Analytics para utilizar los datos de lealtad introducidos y otros datos. La definición de la vista de datos le permite especificar qué dimensión y métricas utilizar y, finalmente, creó su primer proyecto visualizando y analizando los datos.