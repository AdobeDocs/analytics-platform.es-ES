---
title: Ingesta y uso de datos de streaming
description: Explicar cómo ingerir y utilizar datos de streaming en Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 9984200a-71e6-4697-b46f-f53e8d4c507f
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: ht
source-wordcount: '2002'
ht-degree: 100%

---

# Ingesta y uso de datos de streaming

En esta guía de inicio rápido se explica cómo ingerir datos de streaming en Adobe Experience Platform y, continuación, utilizarlos en Customer Journey Analytics.

Para lograrlo, debe llevar a cabo lo siguiente:

- **Configurar un esquema y un conjunto de datos** en Adobe Experience Platform para definir el modelo (esquema) de los datos que desea recopilar y dónde recopilar realmente los datos (conjunto de datos).

- **Usar un conector de origen de API HTTP** para transmitir fácilmente los datos al conjunto de datos configurado en Adobe Experience Platform.

- **Configurar una conexión** en Customer Journey Analytics. Esta conexión debe incluir (al menos) su conjunto de datos de Adobe Experience Platform.

- **Configurar una vista de datos** en Customer Journey Analytics para definir las métricas y las dimensiones que desea utilizar en Analysis Workspace.

- **Configurar un proyecto** en Customer Journey Analytics para crear sus informes y visualizaciones.


>[!NOTE]
>
>Esta es una guía simplificada sobre cómo ingerir datos de streaming en Adobe Experience Platform y utilizarlos en Customer Journey Analytics. Se recomienda estudiar la información adicional cuando se haga referencia a ella.

## Configurar un esquema y un conjunto de datos

Para ingerir datos en Adobe Experience Platform, primero debe definir qué datos desea recopilar. Todos los datos ingeridos en Adobe Experience Platform deben cumplir una estructura estándar y desnormalizada para que las funciones y características consecutivas puedan reconocerlos y actuar en consecuencia. Experience Data Model (XDM) es el marco estándar que proporciona esta estructura en forma de esquemas.

Una vez definido un esquema, se utilizan uno o más conjuntos de datos para almacenar y administrar la recopilación de datos. Un conjunto de datos es una construcción de almacenamiento y administración para una colección de datos, normalmente una tabla, que contiene un esquema (columnas) y campos (filas).

Todos los datos ingeridos en Adobe Experience Platform deben cumplir un esquema predefinido para que se puedan conservar como conjunto de datos.

### Configurar un esquema

Para este inicio rápido, debe recopilar algunos datos de fidelidad, como el ID de fidelidad, los puntos de fidelidad y el estado de fidelidad.
Para ello, primero debe definir un esquema que modele estos datos.

Para configurar el esquema:

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Esquemas]** en [!UICONTROL ADMINISTRACIÓN DE DATOS].

2. Seleccione **[!UICONTROL Crear esquema]**. Seleccione **[!UICONTROL Perfil individual XDM]** de la lista de opciones.

   ![Creación de un esquema](./assets/create-schema.png)

   >[!INFO]
   >
   >    Se utiliza un esquema de perfil individual para modelar los _atributos_ del perfil (como nombre, correo electrónico o sexo). Se utiliza un esquema de eventos de experiencia para modelar el _comportamiento_ de un perfil (como la vista de página, o agregar al carro de compras).


3. En la pantalla [!UICONTROL Esquema sin título]:

   1. Introduzca un nombre para mostrar para el esquema y (opcionalmente) una descripción.

      ![Asignar un nombre al esquema](./assets/name-loyalty-schema.png)

   2. Seleccione **[!UICONTROL + Agregar]** en [!UICONTROL Grupos de campos].

      ![Agregar grupo de campos](./assets/add-field-group-button.png)

      Los grupos de campos son una colección reutilizable de objetos y atributos que le permiten ampliar fácilmente sus esquemas.

   3. En el cuadro de diálogo [!UICONTROL Agregar grupos de campos] seleccione el grupo de campos **[!UICONTROL Detalles de fidelidad]** en la lista.

      ![Grupo de campos ExperienceEvent del SDK web de AEP](./assets/loyalty-fieldgroup.png)

      Puede seleccionar el botón de vista previa para ver una vista previa de los campos que forman parte de este grupo de campos.

      ![Vista previa del grupo de campos ExperienceEvent del SDK web de AEP](./assets/loyalty-fieldgroup-preview.png)

      Seleccione **[!UICONTROL Atrás]** para cerrar la vista previa.

   4. Seleccione **[!UICONTROL Agregar grupos de campos]**.

4. Seleccione **[!UICONTROL +]** junto al nombre del esquema en el panel [!UICONTROL Estructura].

   ![Ejemplo de botón para agregar campo de esquema](./assets/example-loalty-schema-plus.png)

5. En el panel [!UICONTROL Propiedades de campo], introduzca `Identification` como nombre, **[!UICONTROL Identificación]** como [!UICONTROL Nombre para mostrar], seleccione **[!UICONTROL Objeto]** como [!UICONTROL Tipo] y seleccione **[!UICONTROL Profile Core v2]** como [!UICONTROL Grupo de campos].

   ![Objeto de identificación](./assets/identifcation-loyalty-field.png)

   Esto añade capacidades de identificación al esquema. En su caso, desea identificar la información de fidelidad utilizando la dirección de correo electrónico en los datos por lotes.

   Seleccione **[!UICONTROL Aplicar]** para agregar este objeto al esquema.

6. Seleccione el campo de **[!UICONTROL correo electrónico]** en el objeto de identificación que acaba de añadir y seleccione **[!UICONTROL Identidad]** y **[!UICONTROL Correo electrónico]** en el [!UICONTROL Área de nombres de identidad] del panel [!UICONTROL Propiedades de campo].

   ![Especificar el correo electrónico como identidad](./assets/specify-email-loyalty-id.png)

   Está especificando la dirección de correo electrónico como la identidad que el servicio de identidad de Adobe Experience Platform puede utilizar para combinar (unir) el comportamiento de los perfiles.

   Seleccione **[!UICONTROL Aplicar]**. Verá que aparece un icono de huella digital en el atributo de correo electrónico.

7. Seleccione el nivel raíz del esquema (con el nombre del esquema) y, a continuación, seleccione el conmutador **[!UICONTROL Perfil]**.

   Se le pedirá que habilite el esquema para el perfil. Tras la habilitación, cuando los datos se incorporan en conjuntos de datos basados en este esquema, los datos se combinan en el perfil del cliente en tiempo real.

   Consulte [Habilitar el esquema para utilizarlo en el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es#profile) para obtener más información.

   >[!IMPORTANT]
   >
   >    Una vez guardado un esquema habilitado para perfil, ya no se puede deshabilitar para perfil.

   ![Habilitar esquema para perfil](./assets/enable-for-profile.png)

8. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

Ha creado un esquema mínimo que modela los datos de fidelidad que puede ingerir en Adobe Experience Platform. El esquema permite identificar perfiles mediante la dirección de correo electrónico. Al habilitar el esquema para el perfil, se asegura de que los datos del origen de streaming se agregan al perfil del cliente en tiempo real.

Consulte [Crear y editar esquemas en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=es) para obtener más información sobre cómo agregar y quitar grupos de campos y campos individuales a un esquema.

### Configurar un conjunto de datos

Con el esquema, ha definido el modelo de datos. Ahora tiene que definir la construcción para almacenar y administrar esos datos. Esto se realiza mediante conjuntos de datos.

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
   >    Solo puede habilitar un conjunto de datos para un perfil cuando el esquema, al que se adhiere el conjunto de datos, también esté habilitado para el perfil.

   ![Habilitar esquema para perfil](./assets/loyalty-dataset-profile.png)

Consulte [Guía de la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) para obtener más información sobre cómo ver, previsualizar, crear o eliminar un conjunto de datos. Y cómo habilitar un conjunto de datos para el perfil del cliente en tiempo real.


## Configurar una conexión de streaming de API HTTP

La aplicación de origen transmite datos que se ajustan, y que tienen un aspecto similar, al esquema creado.

```json
{
    ...
    "_demosystem4": {
        "identification": {
            "core": {
                "email": "abrocking0@blog.com",
                "loyaltyId": "793406",
            }
        }
    },
    "loyalty": {
        "loyaltyID": [
            "793406"
        ],
        "points": 82.16,
        "status": "Silver"
    }
    ...
}
```

Para transmitir estos datos al conjunto de datos que ha creado, debe definir un punto final de streaming al que se enviarán esos datos. Para ello, debe definir un conector de origen de API HTTP.

Para crear un conector de origen de API HTTP, debe hacer lo siguiente:

1. En la interfaz de usuario de Experience Platform, seleccione **[!UICONTROL Orígenes]** en [!UICONTROL CONEXIONES], en el carril izquierdo.

2. Seleccione **[!UICONTROL Streaming]** de la lista de [!UICONTROL CATEGORÍAS].

3. Seleccione **Configuración** en el mosaico de [!UICONTROL API HTTP].

   ![Configurar el mosaico de API HTTP](./assets/httpapi-tile.png)

4. En el paso [!UICONTROL Autenticación] de la pantalla [!UICONTROL Agregar datos], haga lo siguiente:

   Escriba un nombre y una descripción para la conexión de API HTTP.

   Seleccione **[!UICONTROL Compatible con XDM]** para indicar que los datos que transmite son compatibles con un esquema XDM existente.

   Seleccione **[!UICONTROL Conectar a origen]**. Después de una conexión correcta, observará la opción [!UICONTROL Conectado].

   ![Autenticación de API HTTP](./assets/httpapi-authentication.png)

   Haga clic en **[!UICONTROL Siguiente]** para continuar.

5. En el paso [!UICONTROL Detalles de flujo de datos] de la pantalla [!UICONTROL Agregar datos], haga lo siguiente:

   Seleccione **[!UICONTROL Conjunto de datos existente]**, seleccione su conjunto de datos en la lista de conjuntos de datos y asigne un [!UICONTROL Nombre de flujo de datos].

   ![Detalles de flujo de datos](./assets/httpapi-dataflowdetail.png)

   Seleccione **[!UICONTROL Siguiente]**.

6. El paso [!UICONTROL Revisar] de la pantalla [!UICONTROL Agregar datos] proporciona una descripción general de la conexión de API HTTP.

   ![Detalles de flujo de datos](./assets/httpapi-review.png)

   Seleccione **[!UICONTROL Finalizar]**.

7. Verá la definición final del punto final de streaming de API HTTP.

   ![Punto final de streaming de API HTTP](./assets/httpapi-streamingendpoint.png)

Puede copiar la URL del punto final de streaming y utilizarla para configurar la aplicación de fidelidad para que transmita datos al conjunto de datos de fidelidad de Adobe Experience Platform.

Consulte [Creación de una conexión de streaming de API HTTP mediante la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html?lang=es) para ver un tutorial mucho más completo que explica cómo utilizar la autenticación, cómo asignar datos cuando los datos entrantes no son compatibles con el esquema XDM y cómo crear un nuevo conjunto de datos como parte de la configuración del conector de streaming.


## Configurar una conexión

Para utilizar los datos de Adobe Experience Platform en Customer Journey Analytics, se crea una conexión que incluye los datos resultantes de la configuración del esquema, el conjunto de datos y el flujo de trabajo.

Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform en Workspace. Para informar sobre estos conjuntos de datos, primero debe establecer una conexión entre conjuntos de datos en Adobe Experience Platform y Workspace.

Para crear la conexión:

1. En la interfaz de usuario de Customer Journey Analytics, seleccione **[!UICONTROL Conexiones]** en la barra de navegación superior.

2. Seleccione **[!UICONTROL Crear nueva conexión]**.

3. En la pantalla [!UICONTROL Conexión sin título]:

   Asigne un nombre a la conexión y descríbala en [!UICONTROL Configuración de la conexión].

   Seleccione la zona protegida correcta en la lista [!UICONTROL Zona protegida] en [!UICONTROL Configuración de datos] y seleccione el número de eventos diarios en la lista [!UICONTROL Número medio de eventos diarios].

   ![Configuración de la conexión](./assets/cja-connections-1.png)

   Seleccione **[!UICONTROL Agregar conjuntos de datos]**.

   En el paso [!UICONTROL Seleccionar conjuntos de datos] en [!UICONTROL Agregar conjuntos de datos]:

   - Seleccione el conjunto de datos que creó anteriormente (`Example Loyalty Dataset`) y cualquier otro conjunto de datos que quiera incluir en la conexión.

      ![Añadir conjuntos de datos](./assets/cja-connections-2.png)

   - Seleccione **[!UICONTROL Siguiente]**.
   En el paso [!UICONTROL Configuración de conjuntos de datos] en [!UICONTROL Agregar conjuntos de datos]:

   - Para cada conjunto de datos:

      - Seleccione un [!UICONTROL ID de persona] entre las identidades disponibles de los esquemas del conjunto de datos en Adobe Experience Platform.

      - Seleccione la fuente de datos correcta en la lista [!UICONTROL Tipo de fuente de datos]. Si especifica **[!UICONTROL Otro]**, agregue una descripción para la fuente de datos.

      - Establezca **[!UICONTROL Importar todos los datos nuevos]** y **[!UICONTROL Relleno de conjuntos de datos de datos existentes]** según sus preferencias.

      ![Configurar conjuntos de datos](./assets/cja-connections-3.png)

   - Seleccione **[!UICONTROL Agregar conjuntos de datos]**.
   Seleccione **[!UICONTROL Guardar]**.

Consulte [Información general sobre conexiones](../connections/overview.md) para obtener más información sobre cómo crear y administrar una conexión y cómo seleccionar y combinar conjuntos de datos.

## Configurar una vista de datos

Una vista de datos es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión. Especifica todas las dimensiones y métricas disponibles en Analysis Workspace y de qué columnas obtienen esos datos las dimensiones y métricas. Las vistas de datos se definen a fin de prepararse para la creación de informes en Analysis Workspace.

Para crear la vista de datos:

1. En la interfaz de usuario de Customer Journey Analytics, seleccione **[!UICONTROL Vistas de datos]** en la barra de navegación superior.

2. Seleccione **[!UICONTROL Crear nueva vista de datos]**.

3. En el paso [!UICONTROL Configurar]:

   Seleccione la conexión en la lista [!UICONTROL Conexión].

   Asigne un nombre y (opcionalmente) describa su conexión.

   ![Configuración de la vista de datos](./assets/cja-dataview-1.png)

   Seleccione **[!UICONTROL Guardar y continuar]**.

4. En el paso [!UICONTROL Componentes]:

   Agregue cualquier campo de esquema y/o componente estándar que quiera incluir en los cuadros de componentes [!UICONTROL MÉTRICAS] o [!UICONTROL DIMENSIONES].

   ![Componentes de la vista de datos](./assets/cja-dataview-2.png)

   Seleccione **[!UICONTROL Guardar y continuar]**.

5. En el paso [!UICONTROL Configuración]:

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

5. Comience a arrastrar y soltar dimensiones y métricas en la [!UICONTROL Tabla de forma libre] del [!UICONTROL Panel] para crear su primer informe. Por ejemplo, arrastre `Program Points Balance` y `Page View` como métricas y `email` como dimensión para obtener una visión general rápida de los perfiles que han visitado su sitio web y forman parte del programa de fidelidad que recopila puntos de fidelidad.

   ![Workspace - Primer informe](./assets/cja-projects-5.png)

Consulte [Información general de Analysis Workspace](../analysis-workspace/home.md) para obtener más información sobre cómo crear proyectos y compilar su análisis mediante componentes, visualizaciones y paneles.

>[!SUCCESS]
>
>Ha completado todos los pasos. Empezando por definir qué datos de fidelidad quiere recopilar (esquema) y dónde quiere almacenarlos (conjunto de datos) en Adobe Experience Platform, se ha configurado un conector de origen de API HTTP para transmitir los datos de fidelidad directamente al conjunto de datos. La definición de la vista de datos le permite especificar qué dimensión y métricas debe utilizar y, finalmente, crear su primer proyecto visualizando y analizando los datos.
