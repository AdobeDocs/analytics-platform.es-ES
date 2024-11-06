---
title: Uso de etiquetas para implementar el SDK web para Customer Journey Analytics
description: Obtenga información sobre cómo utilizar las etiquetas para implementar el SDK web para Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# Uso de etiquetas para implementar el SDK web para Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

Puede utilizar la función Etiquetas en Adobe Experience Platform para implementar código en el sitio para recopilar datos. Esta solución de administración de etiquetas le permite implementar código de junto con otros requisitos de etiquetado. Las etiquetas ofrecen una integración perfecta con Adobe Experience Platform mediante la extensión del SDK web de Adobe Experience Platform.

## Crear una etiqueta

1. En la interfaz de usuario de Adobe Experience Platform, en el carril izquierdo, seleccione **[!UICONTROL Etiquetas]** en [!UICONTROL RECOPILACIÓN DE DATOS].

2. Seleccione **[!UICONTROL Nueva propiedad]**.

   Asigne un nombre a la etiqueta, seleccione **[!UICONTROL Web]** e introduzca un nombre de dominio. Seleccione **[!UICONTROL Guardar]** para continuar.

   ![Crear una propiedad](assets/create-property.png)

## Configurar una etiqueta

Después de crear la etiqueta, debe configurarla con las extensiones correctas y configurar los elementos de datos y las reglas según cómo desee rastrear el sitio y enviar datos a Adobe Experience Platform.

Seleccione la etiqueta recién creada de la lista de [!UICONTROL Propiedades de la etiqueta] para abrirla.


### **Extensiones**

Para asegurarse de que puede enviar datos a Adobe Experience Platform (a través de su secuencia de datos), agregue la extensión SDK para web de Adobe Platform a la etiqueta.

Para crear y configurar la extensión del SDK web de Adobe Experience Platform, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Extensiones]** en el carril izquierdo.

1. Seleccione **[!UICONTROL Catálogo]** en la barra superior.

1. Busque o desplácese hasta la extensión del SDK web de Adobe Experience Platform y seleccione **[!UICONTROL Instalar]** para instalarla.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Seleccione la zona protegida y la secuencia de datos que ha creado anteriormente para su [!UICONTROL Entorno de producción], (opcionalmente) su [!UICONTROL Entorno de ensayo] y su [!UICONTROL Entorno de desarrollo].

   ![Configuración de la extensión del SDK web de AEP](assets/aepwebsk-extension-datastreams.png)

   Seleccione **[!UICONTROL Guardar]**.

Consulte [Configurar la extensión del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html) para obtener más información.

El SDK web incluye el [!UICONTROL servicio Adobe Experience Cloud ID] de forma nativa, por lo que no es necesario que agregue la extensión del servicio de ID a la etiqueta.

### **Elementos de datos**

Los Data Elements son los componentes básicos del diccionario de datos (o mapa de datos). Utilice Data Elements para recopilar, organizar y entregar datos a través de la tecnología de marketing y publicidad. Los elementos de datos de la etiqueta se configuran para que se lean en la capa de datos y se puedan utilizar para enviar datos a Adobe Experience Platform.

Existen diferentes tipos de elementos de datos. Primero se configura un elemento de datos para capturar el nombre de página que las personas están viendo en el sitio.

Para definir un elemento de datos de nombre de página, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Elementos de datos]** en el carril izquierdo.

2. Seleccione **[!UICONTROL Agregar elemento de datos]**.

3. En el cuadro de diálogo [!UICONTROL Crear elemento de datos], haga lo siguiente:

   - Asigne un nombre al elemento de datos como, por ejemplo, `Page Name`.

   - Seleccione **[!UICONTROL Principal]** en la lista [!UICONTROL Extensión].

   - Seleccione **[!UICONTROL Información de página]** en la lista [!UICONTROL Tipo de elemento de datos].

   - Seleccione **[!UICONTROL Título]** en la lista [!UICONTROL Atributo].

     ![Crear un elemento de fecha mediante información de página](assets/create-dataelement-1.png)

     Como alternativa, podría haber utilizado el valor de una variable de la capa de datos, por ejemplo `pageName`, y el tipo de elemento de datos [!UICONTROL Variable JavaScript] para definir el elemento de datos.

     ![Crear elementos de datos mediante la variable Javascript](assets/create-dataelement-2.png)

   - Seleccione **[!UICONTROL Guardar]**.

Ahora desea configurar un elemento de datos que haga referencia al Experience Cloud ID que proporciona automáticamente el SDK web de Adobe Experience Platform y que está disponible a través de la extensión del servicio de ID de Experience Cloud.

Para definir un elemento de datos ECID, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Elementos de datos]** en el carril izquierdo.

2. Seleccione **[!UICONTROL Agregar elemento de datos]**.

3. En el cuadro de diálogo [!UICONTROL Crear elemento de datos], haga lo siguiente:

   - Asigne un nombre al elemento de datos, por ejemplo `ECID`.

   - Seleccione **[!UICONTROL Servicio de Experience Cloud ID]** en la lista [!UICONTROL Extensión].

   - Seleccione **[!UICONTROL ECID]** en la lista [!UICONTROL Tipo de elemento de datos].

     ![Elemento de datos ECID](assets/ecid-dataelement.png)

   - Seleccione **[!UICONTROL Guardar]**.

Por último, ahora desea asignar cualquiera de los elementos de datos específicos al esquema definido anteriormente. Puede definir otro elemento de datos que proporcione una representación del esquema XDM.

Para definir un elemento de datos de objeto XDM, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Elementos de datos]** en el carril izquierdo.

2. Seleccione **[!UICONTROL Agregar elemento de datos]**.

3. En el cuadro de diálogo [!UICONTROL Crear elemento de datos], haga lo siguiente:

   - Asigne un nombre al elemento de datos, por ejemplo `XDM - Page View`.

   - Seleccione **[!UICONTROL SDK web de Adobe Experience Platform]** en la lista [!UICONTROL Extensión].

   - Seleccione **[!UICONTROL Objeto XDM]** en la lista [!UICONTROL Tipo de elemento de datos].

   - Seleccione la zona protegida en la lista [!UICONTROL Zona protegida].

   - Seleccione el esquema en la lista [!UICONTROL Esquema].

   - Asigne el atributo `identification > core > ecid`, definido en el esquema, al elemento de datos ECID. Seleccione el icono del cilindro para elegir fácilmente el elemento de datos ECID de su lista de elementos de datos.

     ![Seleccionar un elemento de datos ECID](assets/pick-ecid-dataelement.png)

     ![Asignar un elemento de datos ECID](assets/map-ecid.png)


   - Asigne el atributo `web > webPageDetails > name`, definido en el esquema, al elemento de datos Nombre de página.

     ![Asignar un elemento de datos de nombre de página](assets/map-pagename.png)

   - Seleccione **[!UICONTROL Guardar]**.


### **Reglas**

Las etiquetas de Adobe Experience Platform siguen un sistema basado en reglas. Buscan la interacción de usuarios y datos asociados. Cuando se cumplen los criterios descritos en las reglas, la regla activa la extensión, script o el código del lado del cliente identificados. Puede utilizar reglas para enviar datos (como un objeto XDM) a Adobe Experience Platform mediante la extensión del SDK web de Adobe Experience Platform.

Para definir una regla, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Reglas]** en el carril izquierdo.

1. Seleccione **[!UICONTROL Crear nueva regla]**.

1. En el cuadro de diálogo [!UICONTROL Crear regla], haga lo siguiente:

   - Asigne un nombre a la regla como, por ejemplo, `Page View`.

   - Seleccione **[!UICONTROL + Agregar]**, bajo [!UICONTROL Eventos].

   - En el cuadro de diálogo [!UICONTROL Configuración de evento], haga lo siguiente:

      - Seleccione **[!UICONTROL Principal]** en la lista [!UICONTROL Extensión].

      - Seleccione **[!UICONTROL Ventana cargada]** en la lista [!UICONTROL Tipo de evento].

        ![Regla - Configuración de evento](assets/event-windowloaded-pageview.png)

      - Seleccione **[!UICONTROL Conservar cambios]**.



   - Seleccione **[!UICONTROL + Agregar]**, bajo [!UICONTROL Acciones].

   - En el cuadro de diálogo [!UICONTROL Configuración de acción], haga lo siguiente:

      - Seleccione **[!UICONTROL SDK web de Adobe Experience Platform]** en la lista [!UICONTROL Extensión].

      - Seleccione **[!UICONTROL Enviar evento]** en la lista [!UICONTROL Tipo de acción].

      - Seleccione **[!UICONTROL web.webpagedetails.pageViews]** en la lista [!UICONTROL Tipo].

      - Seleccione el icono de cilindro situado junto a [!UICONTROL Datos XDM] y seleccione **[!UICONTROL XDM - Vista de página]** en la lista de elementos de datos.

     ![Regla - Configuración de la acción](assets/action-pageview-xdm.png)

      - Seleccione **[!UICONTROL Conservar cambios]**.

   - La regla debe tener el siguiente aspecto:

     ![Crear regla](assets/rule-pageview.png)

1. Seleccione **[!UICONTROL Guardar]**.

Lo anterior es solo un ejemplo de definición de una regla que envía datos XDM, que contienen valores de otros elementos de datos, a Adobe Experience Platform.

Puede utilizar las reglas de varias formas en la etiqueta para manipular las variables (mediante los elementos de datos).

Consulte [Reglas](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=es) para obtener más información.

## Compilar y publicar una etiqueta

Después de haber definido los elementos de datos y las reglas, debe generar y publicar la etiqueta. Al crear una compilación de biblioteca, debe asignarla a un entorno. Las extensiones, reglas y elementos de datos de la compilación se compilan y colocan en el entorno asignado. Cada entorno proporciona un código incrustado único que le permite integrar su compilación asignada en el sitio.

Para compilar y publicar una etiqueta, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Flujo de publicación]** en el carril izquierdo.

2. Seleccione **[!UICONTROL Seleccionar una biblioteca de trabajo]**, seguido de **[!UICONTROL Agregar biblioteca…]**.

3. En el cuadro de diálogo [!UICONTROL Crear biblioteca], haga lo siguiente:

   - Asigne un nombre a la biblioteca.

   - Seleccione **[!UICONTROL Desarrollo (desarrollo)]** en la lista [!UICONTROL Entorno].

   - Seleccione **[!UICONTROL + Agregar todos los recursos modificados]**.

     ![Publicar - Crear biblioteca](assets/create-library-aep.png)

   - Seleccione **[!UICONTROL Guardar y compilar para desarrollo]**.

   La etiqueta se guardará y se compilará para su entorno de desarrollo. Un punto verde indica que la compilación de la etiqueta se ha realizado correctamente en el entorno de desarrollo.

4. Puede seleccionar **[!UICONTROL ...]** para recompilar la biblioteca o moverla a un entorno de ensayo o producción.

   ![Publicar - Compilar biblioteca](assets/build-library.png)

Las etiquetas de Adobe Experience Platform admiten flujos de trabajo de publicación simples o complejos que deben admitir la implementación del SDK web de Adobe Experience Platform.

Consulte la [Información general de la publicación](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=es) para obtener más información.


## Recuperar el código de una etiqueta

Finalmente, debe instalar la etiqueta en el sitio web que desee rastrear, lo que implica colocar un código en la etiqueta de encabezado de la plantilla del sitio web.

Para obtener el código que hace referencia a la etiqueta, debe hacer lo siguiente:

1. Seleccione **[!UICONTROL Entornos]** en el carril izquierdo.

1. En la lista de entornos, seleccione el botón (cuadro) de instalación correcto.

   En el cuadro de diálogo [!UICONTROL Instrucciones de instalación en la web] seleccione el botón para copiar junto al código de script que debería ser parecido a:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Entorno](assets/environment.png)

1. Seleccione **[!UICONTROL Cerrar]**.

   En lugar del código para el entorno de desarrollo, puede seleccionar otro entorno (ensayo o producción) en función de dónde se encuentre en el proceso de implementación del SDK web de Adobe Experience Platform.

   Consulte [Entornos](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=es) para obtener más información.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).
