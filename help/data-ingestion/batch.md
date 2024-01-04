---
title: Ingesta y uso de datos por lotes
description: Explicar cómo ingerir y utilizar datos por lotes en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: dd46adee-821f-489c-9350-abcfffe7cc3c
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 87%

---

# Ingesta y uso de datos por lotes

En esta guía de inicio rápido se explica cómo ingerir datos por lotes en Adobe Experience Platform y, continuación, utilizarlos en Customer Journey Analytics.

Para lograrlo, debe llevar a cabo lo siguiente:

- **Configurar un esquema y un conjunto de datos** en Adobe Experience Platform para definir el modelo (esquema) de los datos que desea recopilar y dónde recopilar realmente los datos (conjunto de datos).

- **Usar flujos de trabajo** para cargar fácilmente los datos por lotes en el conjunto de datos configurado en Adobe Experience Platform.

- **Configurar una conexión** en Customer Journey Analytics. Esta conexión debe incluir (al menos) su conjunto de datos de Adobe Experience Platform.

- **Configurar una vista de datos** en Customer Journey Analytics para definir las métricas y las dimensiones que desea utilizar en Analysis Workspace.

- **Configurar un proyecto** en Customer Journey Analytics para crear sus informes y visualizaciones.

>[!NOTE]
>
>Esta guía de inicio rápido es una guía simplificada sobre cómo introducir datos por lotes en Adobe Experience Platform y utilizarlos en Customer Journey Analytics. Se recomienda estudiar la información adicional cuando se haga referencia a ella.

## Configurar un esquema y un conjunto de datos

Para ingerir datos en Adobe Experience Platform, primero debe definir qué datos desea recopilar. Todos los datos ingeridos en Adobe Experience Platform deben cumplir una estructura estándar y desnormalizada para que las funciones y características consecutivas puedan reconocerlos y actuar en consecuencia. Experience Data Model (XDM) es el marco estándar que proporciona esta estructura en forma de esquemas.

Una vez definido un esquema, se utilizan uno o más conjuntos de datos para almacenar y administrar la recopilación de datos. Un conjunto de datos es una construcción de almacenamiento y administración para una colección de datos (normalmente una tabla) que contiene un esquema (columnas) y campos (filas).

Todos los datos ingeridos en Adobe Experience Platform deben cumplir un esquema predefinido para que se puedan conservar como conjunto de datos.

### Configurar un esquema

Para este inicio rápido, debe recopilar algunos datos de fidelidad, como el ID de fidelidad, los puntos de fidelidad y el estado de fidelidad.
Primero debe definir un esquema que modele estos datos.

Para configurar el esquema:

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Esquemas]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

1. Seleccionar **[!UICONTROL Crear esquema]**. .
1. En el paso Seleccionar una clase del asistente Crear esquema:

   1. Seleccionar **[!UICONTROL Perfil individual]**.

      ![Creación de un esquema](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Se utiliza un esquema de Evento de experiencia para modelar el _comportamiento_ de un perfil (como nombre de la escena, botón para añadir al carro de compras). Se utiliza un esquema de perfil individual para modelar los _atributos_ del perfil (como nombre, correo electrónico o sexo).

   1. Seleccione **[!UICONTROL Siguiente]**.


1. En el [!UICONTROL Nombre y paso de revisión] de la [!UICONTROL Crear esquema] asistente:

   1. Introduzca una **[!UICONTROL Nombre para mostrar del esquema]** para su esquema y (opcional) un **[!UICONTROL Descripción]**.

      ![Asignar un nombre al esquema](./assets/create-pr-schema-wizard-step-2.png)

   1. Seleccione **[!UICONTROL Finalizar]**.

1. En la pestaña Estructura del esquema de ejemplo:

   1. Seleccione **[!UICONTROL + Agregar]** en [!UICONTROL Grupos de campos].

      ![Agregar grupo de campos](./assets/add-field-group-button.png)

      Los grupos de campos son colecciones reutilizables de objetos y atributos que le permiten ampliar fácilmente su esquema.

   1. En el cuadro de diálogo [!UICONTROL Agregar grupos de campos] seleccione el grupo de campos **[!UICONTROL Detalles de fidelidad]** en la lista.

      ![Grupo de campos ExperienceEvent del SDK web de AEP](./assets/loyalty-fieldgroup.png)

      Puede seleccionar el botón de vista previa para ver una vista previa de los campos que forman parte de este grupo de campos.

      ![Vista previa del grupo de campos ExperienceEvent del SDK web de AEP](./assets/loyalty-fieldgroup-preview.png)

      Seleccione **[!UICONTROL Atrás]** para cerrar la vista previa.

   1. Seleccione **[!UICONTROL Agregar grupos de campos]**.

1. Seleccione **[!UICONTROL +]** junto al nombre del esquema en el panel [!UICONTROL Estructura].

   ![Ejemplo de botón para agregar campo de esquema](./assets/example-loalty-schema-plus.png)

1. En el panel [!UICONTROL Propiedades de campo], introduzca `Identification` como nombre, **[!UICONTROL Identificación]** como [!UICONTROL Nombre para mostrar], seleccione **[!UICONTROL Objeto]** como [!UICONTROL Tipo] y seleccione **[!UICONTROL Profile Core v2]** como [!UICONTROL Grupo de campos].

   ![Objeto de identificación](./assets/identifcation-loyalty-field.png)

   El objeto de identificación agrega capacidades de identificación al esquema. En su caso, desea identificar la información de fidelidad utilizando la dirección de correo electrónico de los datos por lotes.

   Seleccione **[!UICONTROL Aplicar]** para agregar este objeto al esquema.

1. Seleccione el campo de **[!UICONTROL correo electrónico]** en el objeto de identificación que acaba de añadir y seleccione **[!UICONTROL Identidad]** y **[!UICONTROL Correo electrónico]** en el [!UICONTROL Área de nombres de identidad] del panel [!UICONTROL Propiedades de campo].

   ![Especificar el correo electrónico como identidad](./assets/specify-email-loyalty-id.png)

   Está especificando la dirección de correo electrónico como la identidad que el servicio de identidad de Adobe Experience Platform puede utilizar para combinar (unir) perfiles.

   Seleccione **[!UICONTROL Aplicar]**. Verá que aparece un icono de huella digital en el atributo de correo electrónico.

   Seleccione **[!UICONTROL Guardar]**.

1. Seleccione el nivel raíz del esquema (con el nombre del esquema) y, a continuación, seleccione el conmutador **[!UICONTROL Perfil]**.

   Se le pedirá que habilite el esquema para el perfil. Tras la habilitación, cuando los datos se incorporan en conjuntos de datos basados en este esquema, los datos se combinan en el perfil del cliente en tiempo real.

   Consulte [Habilitar el esquema para utilizarlo en el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es#profile) para obtener más información.

   >[!IMPORTANT]
   >
   >    Una vez guardado un esquema habilitado para perfil, ya no se puede deshabilitar para perfil.

   ![Habilitar esquema para perfil](./assets/enable-for-profile.png)

1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

Ha creado un esquema mínimo que modela los datos de fidelidad que puede ingerir en Adobe Experience Platform. El esquema permite identificar perfiles mediante la dirección de correo electrónico. Al habilitar el esquema para el perfil, se asegura de que los datos del origen del archivo por lotes se agregan al perfil del cliente en tiempo real.

Consulte [Crear y editar esquemas en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=es) para obtener más información sobre cómo agregar y quitar grupos de campos y campos individuales a un esquema.

### Configurar un conjunto de datos

Con el esquema, ha definido el modelo de datos. Ahora tiene que definir la construcción para almacenar y administrar esos datos, lo que se hace a través de conjuntos de datos.

Para configurar un conjunto de datos:

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Conjuntos de datos]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

2. Seleccione **[!UICONTROL Crear conjunto de datos]**.

   ![Crear conjunto de datos](./assets/create-dataset.png)

3. Seleccione **[!UICONTROL Crear conjunto de datos a partir de esquema]**.

   ![Crear conjunto de datos a partir de esquema](./assets/create-dataset-from-schema.png)

4. Seleccione el esquema creado anteriormente y, después, **[!UICONTROL Siguiente]**.

5. Asigne un nombre al conjunto de datos y (opcionalmente) proporcione una descripción.

   ![Nombre del conjunto de datos](./assets/name-your-datatest.png)

6. Seleccione **[!UICONTROL Finalizar]**.

7. Seleccione el conmutador **[!UICONTROL Perfil]**.

   Se le pedirá que habilite el conjunto de datos para el perfil. Una vez habilitado, el conjunto de datos enriquece los perfiles de clientes en tiempo real con sus datos ingeridos.

   >[!IMPORTANT]
   >
   >Solo puede habilitar un conjunto de datos para un perfil cuando el esquema, al que se adhiere el conjunto de datos, también esté habilitado para el perfil.

   ![Habilitar esquema para perfil](./assets/loyalty-dataset-profile.png)

Consulte [Guía de la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) para obtener más información sobre cómo ver, previsualizar, crear o eliminar un conjunto de datos. Y cómo habilitar un conjunto de datos para el perfil del cliente en tiempo real.


## Usar flujos de trabajo

La funcionalidad de flujos de trabajo se utiliza para cargar los datos por lotes en Adobe Experience Platform. El archivo por lotes de ejemplo que utiliza es un archivo CSV con el siguiente contenido:

```
email,loyaltyID,points,status
abrocking0@blog.com,793406,82.16,Silver
wnichol1@ycombinator.com,988654,40.39,Gold
paisbett2@slideshare.net,444897,91.25,Bronze
bdiamant3@xinhuanet.com,239658,57.87,Gold
ppales4@nsw.gov.au,365384,82.71,Silver
...
```

Para utilizar flujos de trabajo, debe hacer lo siguiente:

1. En la interfaz de usuario de Platform, seleccione **[!UICONTROL Flujos de trabajo]** en el carril izquierdo.

2. Seleccione **[!UICONTROL Asignar CSV al esquema XDM]**. Seleccione **[!UICONTROL Lanzamiento]**.

   ![Asignar CSV a XDN](./assets/workflow-mapcsvtoxdm.png)

3. En la pantalla [!UICONTROL Asignar CSV al esquema XDM], en el paso [!UICONTROL Detalles de flujo de datos], haga lo siguiente:

   Seleccione **[!UICONTROL Conjunto de datos existente]**, seleccione su conjunto de datos en la lista de conjuntos de datos y asigne un [!UICONTROL Nombre de flujo de datos].

   ![Flujo de datos](./assets/workflow-dataflowdetail.png)

   Seleccione **[!UICONTROL Siguiente]**.

4. En el paso [!UICONTROL Seleccionar datos], haga lo siguiente:

   Arrastre y suelte o seleccione **[!UICONTROL Elegir archivos]** para seleccionar el archivo CSV con datos de fidelidad. Verá una vista previa de los datos de fidelidad.

   ![Seleccionar datos](./assets/workflow-selectdata.png)

   Seleccione **[!UICONTROL Siguiente]**.

5. En el paso [!UICONTROL Asignación], haga lo siguiente:

   Asigne los datos del archivo CSV a los datos del esquema. Con el uso de inteligencia artificial, la funcionalidad del flujo de trabajo intenta asignar automáticamente los campos de datos por lotes a los campos de esquema.

   ![Asignar datos](./assets/workflow-dataflow-mapping.png)

   Puede usar **[!UICONTROL Vista previa de datos]** para ver una vista previa de los datos asignados.

   ![Vista previa de la asignación](./assets/workflow-dataflow-mapping-preview.png)

6. Seleccione **[!UICONTROL Finalizar]** para empezar a ingerir los datos por lotes en Adobe Experience Platform.

Consulte [Asignar un archivo CSV a un esquema XDM existente](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema.html?lang=es) para obtener más información sobre:

- Obtenga información sobre cómo asignar datos cuando los datos entrantes no sean compatibles con el esquema XDM.
- utilizar plantillas de asignación,
- utilice campos calculados para asegurarse de que los datos por lotes se ajustan a lo que espera el esquema.
- y más.


## Configurar una conexión

Para utilizar los datos de Adobe Experience Platform en Customer Journey Analytics, se crea una conexión que incluye los datos resultantes de la configuración del esquema, el conjunto de datos y el flujo de trabajo.

Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform en Workspace. Para informar sobre estos conjuntos de datos, primero debe establecer una conexión entre conjuntos de datos en Adobe Experience Platform y Workspace.

Para crear la conexión:

1. En la interfaz de usuario de Customer Journey Analytics, seleccione **[!UICONTROL Conexiones]** en la barra de navegación superior.

2. Seleccione **[!UICONTROL Crear nueva conexión]**.

3. En la pantalla [!UICONTROL Conexión sin título], haga lo siguiente:

   Asigne un nombre a la conexión y descríbala en [!UICONTROL Configuración de la conexión].

   Seleccione la zona protegida correcta en la lista [!UICONTROL Zona protegida] de [!UICONTROL Configuración de datos] y seleccione el número de eventos diarios en la lista [!UICONTROL Número medio de eventos diarios].

   ![Configuración de la conexión](./assets/cja-connections-1.png)

   Seleccione **[!UICONTROL Agregar conjuntos de datos]**.

   En el paso [!UICONTROL Seleccionar conjuntos de datos] en [!UICONTROL Agregar conjuntos de datos]:

   - Seleccione el conjunto de datos que creó anteriormente (`Example Loyalty Dataset`) y cualquier otro conjunto de datos que quiera incluir en la conexión.

     ![Añadir conjuntos de datos](./assets/cja-connections-2.png)

   - Seleccione **[!UICONTROL Siguiente]**.

   En el paso [!UICONTROL Configuración de conjuntos de datos], en [!UICONTROL Agregar conjuntos de datos], haga lo siguiente:

   - Para cada conjunto de datos:

      - Seleccione un [!UICONTROL ID de persona] entre las identidades disponibles de los esquemas del conjunto de datos en Adobe Experience Platform.

      - Seleccione la fuente de datos correcta en la lista [!UICONTROL Tipo de fuente de datos]. Si especifica **[!UICONTROL Otro]**, agregue una descripción para la fuente de datos.

      - Establezca **[!UICONTROL Importar todos los datos nuevos]** y **[!UICONTROL Datos existentes del relleno del conjunto de datos]** según sus preferencias.

     ![Configurar conjuntos de datos](./assets/cja-connections-3.png)

   - Seleccione **[!UICONTROL Agregar conjuntos de datos]**.

   Seleccione **[!UICONTROL Guardar]**.

Consulte [Información general sobre conexiones](../connections/overview.md) para obtener más información sobre cómo crear y administrar una conexión y cómo seleccionar y combinar conjuntos de datos.

## Configurar una vista de datos

Una vista de datos es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión. Especifica todas las dimensiones y métricas disponibles en Analysis Workspace y de qué columnas obtienen esos datos las dimensiones y métricas. Las vistas de datos se definen a fin de prepararse para la creación de informes en Analysis Workspace.

Para crear la vista de datos:

1. En la interfaz de usuario de Customer Journey Analytics, seleccione **[!UICONTROL Vistas de datos]** en la barra de navegación superior.

2. Seleccione **[!UICONTROL Crear nueva vista de datos]**.

3. En el paso [!UICONTROL Configurar], haga lo siguiente:

   Seleccione la conexión en la lista [!UICONTROL Conexión].

   Asigne un nombre y (opcionalmente) describa su conexión.

   ![Configuración de la vista de datos](./assets/cja-dataview-1.png)

   Seleccione **[!UICONTROL Guardar y continuar]**.

4. En el paso [!UICONTROL Componentes], haga lo siguiente:

   Agregue cualquier campo de esquema o componente estándar que quiera incluir en los cuadros de componentes [!UICONTROL MÉTRICAS] o [!UICONTROL DIMENSIONES].

   ![Componentes de la vista de datos](./assets/cja-dataview-2.png)

   Seleccione **[!UICONTROL Guardar y continuar]**.

5. En el paso [!UICONTROL Configuración], haga lo siguiente:

   Configuración de ![vista de datos](./assets/cja-dataview-3.png)

   Deje la configuración tal como está y seleccione **[!UICONTROL Guardar y finalizar]**.

Consulte [Información general de las vistas de datos](../data-views/data-views.md) para obtener más información sobre cómo crear y editar una vista de datos, qué componentes están disponibles para usar en la vista de datos y cómo usar la configuración de filtro y sesiones.


## Configurar un proyecto

Analysis Workspace es una herramienta de navegador flexible que le permite compilar análisis y compartir perspectivas rápidamente, en función de los datos. Los proyectos de Workspace se usan para combinar componentes, tablas y visualizaciones de datos para crear un análisis y compartirlo con cualquier persona de su organización.

Para crear un proyecto:

1. En la interfaz de usuario de Customer Journey Analytics, seleccione **[!UICONTROL Proyectos]** en la barra de navegación superior.

2. Seleccione **[!UICONTROL Proyectos]** en el panel de navegación izquierdo.

3. Seleccione **[!UICONTROL Crear proyecto]**.

   ![Proyecto de Workspace](./assets/cja-projects-1.png)

   Seleccione **[!UICONTROL Proyecto en blanco]**.

   ![Workspace - Proyecto en blanco](./assets/cja-projects-2.png)

4. Seleccione la vista de datos en la lista.

   ![Workspace - Seleccionar vista de datos](./assets/cja-projects-3.png).

5. Para crear el primer informe, comience a arrastrar y soltar dimensiones y métricas en la [!UICONTROL Tabla de forma libre] en el [!UICONTROL Panel]. Por ejemplo, arrastre `Program Points Balance` y `Page View` como métricas y `email` como dimensión para obtener una visión general rápida de los perfiles que han visitado su sitio web y forman parte del programa de fidelidad que recopila puntos de fidelidad.

   ![Workspace - Primer informe](./assets/cja-projects-5.png)

Consulte [Información general de Analysis Workspace](../analysis-workspace/home.md) para obtener más información sobre cómo crear proyectos y compilar su análisis mediante componentes, visualizaciones y paneles.

>[!SUCCESS]
>
>Ha completado todos los pasos. Empezando por definir qué datos de fidelidad quiere recopilar (esquema) y dónde quiere almacenarlos (conjunto de datos) en Adobe Experience Platform, se ha configurado un flujo de trabajo para cargar los datos de fidelidad por lotes en un conjunto de datos. Ha definido una conexión en Customer Journey Analytics para utilizar los datos de fidelidad ingeridos y otros datos. La definición de la vista de datos le permite especificar qué dimensión y métricas debe utilizar y, finalmente, crear su primer proyecto visualizando y analizando los datos.
