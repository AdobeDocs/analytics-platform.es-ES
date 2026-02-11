---
title: Validación De La Configuración De Identidad En Customer Journey Analytics
description: Obtenga información sobre cómo validar la vinculación de identidad en Customer Journey Analytics. Mida las tasas de autenticación y la identificación antes y después de la vinculación.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
source-git-commit: 0eb3fec2e52fe0850c5f42777edbdb5d981988fb
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 0%

---

# Validar vinculación

El objetivo de [vincular la identidad](/help/stitching/overview.md) (o simplemente, vincular) es elevar la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. Esta elevación se logra cuando todas las filas de datos del conjunto de datos contienen la identidad de orden superior deseada que está disponible. Esta elevación le permite:

* Crear informes centrados en la persona, sin excluir a las personas anónimas.
* Conecte varios dispositivos a una sola persona.
* Conectar a una persona a través de canales.

Este artículo describe métodos de análisis para medir la elevación de uno o más conjuntos de datos enlazados recién creados y proporcionar confianza en que la vinculación ofrece estos beneficios.

Los métodos de análisis implican [configuraciones del componente de vista de datos](/help/data-views/component-settings/overview.md) a las que suelen tener acceso los administradores. Los métodos también requieren analistas, que trabajan en un proyecto de Analysis Workspace, para crear métricas calculadas y visualizaciones.

Aunque estos métodos de análisis se pueden utilizar tanto para la vinculación basada en el campo como en la basada en gráficos, es posible que algunos elementos no estén presentes en el conjunto de datos, especialmente en un escenario de vinculación basada en gráficos. Estos elementos que faltan pueden dificultar el cálculo del alza directamente en Analysis Workspace.

>[!NOTE]
>
>La vinculación (validación) de uno o más conjuntos de datos contribuye en última instancia a un mejor análisis y perspectivas. Sin embargo, este artículo no analiza el valor general de una configuración de Customer Journey Analytics que tiene todos los conjuntos de datos de Experience Platform alineados con el mismo área de nombres de identidad. Y que todos estos conjuntos de datos están muy bien unidos para realizar análisis en todo un recorrido de clientes.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Habilitación y validación de vinculación](https://video.tv.adobe.com/v/3478123?captions=spa&quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]



## Vinculación en la validación de Conexiones

Esta sección detalla cómo validar la vinculación habilitada en la interfaz Conexiones.

### Recomendaciones de conexión

Para validar la vinculación que habilitó en la interfaz Conexiones, seleccione un período corto y representativo para **[!UICONTROL Relleno de conjunto de datos]**. Por ejemplo, una semana.

En el ejemplo siguiente, desea vincular el conjunto de datos de evento. Ha configurado una conexión de prueba en la que agrega el conjunto de datos de evento. Para ese conjunto de datos, usted define el **[!UICONTROL ECID]** **[!UICONTROL Espacio de nombres]** como el **[!UICONTROL ID persistente]** y la **[!UICONTROL Dirección de correo electrónico con hash de visitante (directMarketing.hashedEmail)]** como el **[!UICONTROL ID de persona]**. Para validar esta vinculación, debe definir un **[!UICONTROL relleno de conjunto de datos]** para un período de tiempo reducido (del 24 de enero de 2026 al 10 de febrero de 2026). Utilice esa pequeña ventana para validar si la vinculación funciona según lo previsto.

![Configuración de vinculación](/help/stitching/assets/stitching-config.png)

### Requisitos previos de vista de datos

Para la validación de la vinculación, debe asegurarse de que tiene todas las dimensiones y métricas necesarias del conjunto de datos vinculado definidas en una vista de datos. Cree una vista de datos basada en la conexión definida anteriormente. En el paso **[!UICONTROL Componentes]** de la configuración de la vista de datos, debe:

* Agregue **[!UICONTROL Área de nombres de identidad]** de **[!UICONTROL Métricas y dimensiones]** como dimensión a la lista **[!UICONTROL Dimensiones]**.

  ![Espacio de nombres de identidad](/help/stitching/assets/identity-namespace.png)


* Seleccione el **[!UICONTROL Identificador de dirección de correo electrónico con hash para el visitante]** que ha definido como ID de persona para sus eventos en **[!UICONTROL Campos de esquema]**. Agregue el campo como dimensión a la lista **[!UICONTROL Dimensiones]** y como métrica a la lista **[!UICONTROL Métricas]**. Modifique **[!UICONTROL Nombre de componente]** para la métrica a `Email set`.

  ![Identificador de correo electrónico](/help/stitching/assets/email-identifier.png)

Asegúrese de guardar la vista de datos.

### Crear un proyecto de Workspace

En Workspace, cree un nuevo proyecto y use una tabla de forma libre para mostrar la métrica **[!UICONTROL Correo electrónico establecido]** para el intervalo de fechas que ha definido para probar la configuración de vinculación. Esta tabla de forma libre muestra los eventos que tienen una dirección de correo electrónico antes de la vinculación.

![Tabla de forma libre con información general de vinculación - Conjunto de correo electrónico](/help/stitching/assets/workspace-emailset.png)

Para ver los eventos que tienen una dirección de correo electrónico establecida después del proceso de vinculación, defina una métrica calculada `Email stitched namespace`. Esa métrica calculada busca **[!UICONTROL Eventos]** que tienen un **[!UICONTROL Área de nombres de identidad]** igual al área de nombres de correo electrónico con hash `email_lc_sha256`.

![Información general sobre la vinculación: métrica calculada del área de nombres vinculada por correo electrónico](/help/stitching/assets/cm-email-stitched-namespace.png)

Si agrega la nueva métrica calculada **[!UICONTROL Área de nombres vinculada por correo electrónico]** a la tabla de forma libre, verá el aumento en el número de eventos que ahora tienen una dirección de correo electrónico después del proceso de vinculación.

![Información general sobre la vinculación de tabla de forma libre: correo electrónico establecido y vinculado](/help/stitching/assets/workspace-emailset-stitched.png)

Puede obtener más información al definir dos métricas calculadas adicionales.

* **[!UICONTROL Tasa de autenticación de correo electrónico]**. Esta métrica calculada determina la tasa de autenticación antes del proceso de vinculación.

  ![Definición de métrica calculada de tasa de autenticación de correo electrónico](/help/stitching/assets/cm-email-authentication-rate.png)

* **[!UICONTROL Tasa de autenticación vinculada]**. Esta métrica calculada determina la tasa de autenticación después del proceso de vinculación.

  ![Definición de métrica calculada de tasa de autenticación vinculada](/help/stitching/assets/cm-stitched-authentication-rate.png)

Agregue estas dos métricas calculadas adicionales a la tabla de forma libre y podrá ver el aumento de eventos vinculados.

![Tabla de forma libre con información general de vinculación - Autenticado](/help/stitching/assets/workspace-authenticated.png)

Para obtener más información, puede agregar dos métricas calculadas más (**[!UICONTROL Aumento porcentual]** y **[!UICONTROL Alza]**) a la tabla de forma libre para ver el impacto de la configuración de la vinculación.

![Tabla de forma libre con información general de vinculación - Alza autenticada](/help/stitching/assets/workspace-authenticated-lift.png)



## Solicitar validación de vinculación

Esta sección detalla cómo validar la vinculación que ha solicitado a Adobe. Este método está obsoleto, pero es posible que aún tenga conjuntos de datos enlazados mediante este método.

### Requisitos previos de vista de datos

Para el plan de medición de validación de vinculación, debe asegurarse de que tiene todas las dimensiones y métricas necesarias del conjunto de datos vinculado definidas en una vista de datos. Compruebe que los campos `stitchedID.id` y `stitchedID.namespace.code` se hayan agregado como dimensiones. Aunque el conjunto de datos vinculado es una copia exacta del conjunto de datos original, el proceso de vinculación agrega estas dos nuevas columnas al conjunto de datos:

* Use `stitchedID.namespace.code` para definir una dimensión de **[!UICONTROL espacio de nombres vinculado]**. Esta dimensión contiene el área de nombres de la identidad a la que se elevó la fila, por ejemplo `Email` o `Phone`. O el área de nombres al que se recupera el proceso de vinculación, como `ECID`.
  ![Dimensión del área de nombres vinculada](/help/stitching/assets/stitchednamespace-dimension.png)

* Use `stitchedID.id` para definir una dimensión de **[!UICONTROL ID vinculado]**. Esta dimensión contiene el valor sin procesar de la identidad. Por ejemplo: correo electrónico con hash, teléfono con hash, ECID. Este valor se usa con **[!UICONTROL espacio de nombres vinculado]**.
  ![Dimensión de ID vinculado](/help/stitching/assets/stitchedid-dimension.png)


Además, debe agregar dos métricas de vinculación basadas en la presencia de valores en una dimensión.

1. Utilice el campo que contiene el ID de persona del conjunto de datos vinculado para configurar una métrica que defina si se establece un ID de persona. Añada este ID de persona aunque utilice la vinculación basada en gráficos, ya que el ID de persona ayuda a establecer una línea de base. Si el ID de persona no está contenido en el conjunto de datos, la línea de base es del 0 %.

   En el ejemplo siguiente, `personalEmail.address` sirve como identidad y se usa para crear la métrica **[!UICONTROL _Email set]**.
   ![Métrica del conjunto de correo electrónico](/help/stitching/assets/emailset-metric.png)

1. Utilice el campo `stitchedID.namespace.code` para crear una métrica de **[!UICONTROL espacio de nombres vinculado por correo electrónico]**. Asegúrese de especificar [Incluir valores de exclusión en la configuración de componentes](/help/data-views/component-settings/include-exclude-values.md), de modo que sólo tenga en cuenta los valores del área de nombres a la que intenta elevar filas de datos.
   1. Seleccione **[!UICONTROL Establecer valores de inclusión/exclusión]**.
   1. Seleccione **[!UICONTROL Si se cumplen todos los criterios]** como **[!UICONTROL Coincidencia]**.
   1. Especifique **[!UICONTROL Es igual que]** `email` como **[!UICONTROL criterio]** para seleccionar eventos que se han elevado al espacio de nombres de correo electrónico.

   ![Métrica del área de nombres vinculada por correo electrónico](/help/stitching/assets/emailstitchednamespace-metric.png)

### Dimensiones vinculadas

Con ambas dimensiones agregadas a la vista de datos, use [tablas de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) en Analysis Workspace para comprobar los datos que tiene cada dimensión.

En la tabla de dimensiones **[!UICONTROL Stitched Namespace]**, normalmente verá dos filas para cada conjunto de datos. Una fila representa cuándo tuvo que utilizar el proceso de vinculación el método de reserva (ECID). La otra fila muestra los eventos asociados con el área de nombres de identidad deseada (correo electrónico).

Para la tabla de dimensiones **[!UICONTROL Stitched ID value]**, verá los valores sin procesar que provienen de los eventos. En esta tabla, verá que los valores oscilan entre el ID persistente y el ID de persona deseado.

![Comprobar dimensiones vinculadas](/help/stitching/assets/check-data-on-stitching.png)


### Informes centrados en el dispositivo o en la persona

Al crear una conexión, debe definir qué campo o identidad se utiliza para el ID de persona. Por ejemplo, en un conjunto de datos web, si elige un ID de dispositivo como ID de persona, crea informes centrados en el dispositivo y pierde la capacidad de unir estos datos con otros canales sin conexión. Si selecciona un campo o una identidad en canales múltiples, por ejemplo, un correo electrónico, perderá los eventos no autenticados. Para comprender este impacto, debe averiguar qué parte del tráfico no está autenticado y qué parte del tráfico está autenticado.

1. Crear una métrica calculada **[!UICONTROL Eventos no autenticados en total]**. Defina la regla en el generador de reglas como se muestra a continuación:
   ![Eventos no autenticados en total](/help/stitching/assets/calcmetric-unauthenticatedeventsovertotal.png)

1. Cree una métrica calculada **[!UICONTROL tasa de autenticación de correo electrónico]**, basada en la métrica **[!UICONTROL _Correo electrónico establecido]** que definió anteriormente. Defina la regla en el generador de reglas como se muestra a continuación:
   ![Tasa de autenticación de correo electrónico](/help/stitching/assets/calcmetric-emailauthenticationrate.png)

1. Utilice la métrica calculada **[!UICONTROL Eventos no autenticados sobre el total]**, junto con la métrica calculada **[!UICONTROL Tasa de autenticación de correo electrónico]**, para crear una visualización [Anillo](/help/analysis-workspace/visualizations/donut.md). La visualización muestra el número de eventos en el conjunto de datos que no están autenticados y autenticados.

   ![Detalles de identificación](/help/stitching/assets/identification-details.png)



### Vinculación de tasas de identificación

Desea medir el rendimiento de identificación antes y después de la vinculación. Para ello, cree tres métricas calculadas adicionales:

1. Una métrica calculada de **[!UICONTROL tasa de autenticación vinculada]** que calcula el número de eventos donde el área de nombres vinculada está configurada con la identidad deseada sobre el número total de eventos. Al configurar la vista de datos, creó una métrica de **[!UICONTROL área de nombres vinculada por correo electrónico]** que incluía un filtro para contar solo cuando un evento tiene un área de nombres configurada como correo electrónico. La métrica calculada utiliza esta métrica **[!UICONTROL Área de nombres vinculada por correo electrónico]** para proporcionar una indicación del porcentaje de datos que tiene la identidad deseada.
   ![Métrica calculada de tasa de autenticación vinculada](/help/stitching/assets/calcmetric-stitchedauthenticationrate.png)

1. Una métrica calculada de **[!UICONTROL aumento porcentual]** que calcula el cambio de porcentaje sin procesar entre la tasa de identificación actual y la unida.
   ![Métrica calculada de aumento porcentual](/help/stitching/assets/calcmetric-percentincrease.png)

1. Una métrica calculada de **[!UICONTROL Lift]** que calcula el alza entre la tasa de identificación actual y la tasa de identificación vinculada.
   ![Métrica calculada de alza](/help/stitching/assets/calcmetric-lift.png)


### Conclusión

Si combina todos los datos en una tabla de forma libre de Analysis Workspace, puede empezar a ver el impacto y el valor que proporciona la vinculación, incluidos los siguientes:

* Tasa de autenticación actual: la línea de base del número de eventos que ya tenían el ID de persona correcto sobre el número total de eventos.
* Tasa de autenticación vinculada: el nuevo número de eventos que tienen el ID de persona correcto sobre el número total de eventos.
* Aumento porcentual: el aumento porcentual sin procesar desde la tasa de autenticación vinculada menos la tasa de autenticación actual de línea de base.
* Alza: el cambio porcentual con respecto a la tasa de autenticación actual de línea base.

![Rendimiento de identificación](/help/stitching/assets/identification-performance.png)


## Principales conclusiones

La conclusión clave de este artículo es que vincular validación y análisis le ayuda a lo siguiente:

* Proporcione una vista personalizada completa de la eficacia de la autenticación comparando las tasas actuales frente a las vinculadas.
* Habilite la medición clara de la mejora mediante incrementos porcentuales y métricas de alza.
* Ayude a identificar el verdadero impacto de la implementación de la vinculación en la autenticación de usuarios.
* Cree una forma estandarizada de comunicar el rendimiento de autenticación entre equipos.
* Permite tomar decisiones basadas en datos acerca de la estrategia de autenticación y la optimización.

Estas métricas, en conjunto, proporcionan a las partes interesadas una imagen completa de cómo la vinculación de Customer Journey Analytics afecta a las tasas de éxito de autenticación y al rendimiento general de identificación de personas.
