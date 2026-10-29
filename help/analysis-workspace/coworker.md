---
title: Analizar y crear proyectos de Workspace con compañeros de trabajo
description: Utilice la experiencia del producto para que sus compañeros resuman el proyecto abierto, busquen perspectivas y creen paneles, tablas y segmentos a partir de las indicaciones en lenguaje natural.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 88e67c92fc170b340149c9ab73ad5eea2122da2b
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 1%
---
# Uso de la experiencia del producto para compañeros de trabajo

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Además, el colaborador utiliza IA generativa, que puede producir resultados inexactos o inesperados. Revise las respuestas de los compañeros y los cambios que realice en su proyecto antes de actuar en consecuencia o compartir el proyecto.

La experiencia del producto para compañeros de trabajo está disponible en un panel de chat a la derecha de Analysis Workspace. El colaborador utiliza el proyecto abierto como contexto, por lo que puede preguntar sobre su análisis o hacer que el colaborador cree el proyecto sin necesidad de explicar qué contiene.

## Comprender a los compañeros de trabajo en Workspace

### Requisitos previos

* **El colaborador está habilitado para su organización**: la experiencia del producto para el colaborador está deshabilitada de manera predeterminada. Un administrador de Customer Journey Analytics debe habilitarlo para la organización antes de que los usuarios puedan acceder a él.

  Si no puede acceder a Colaborador en Workspace, póngase en contacto con su administrador. Para obtener más información, consulte [Preferencias de organización de IMS](/help/analysis-workspace/user-preferences.md#ims-organization-preferences). <!-- need to update this section with the new toggle -->

* **Acceso a la vista de datos**: El compañero usa su Analysis Workspace existente y los permisos de vista de datos. No puede acceder a datos o componentes a los que aún no tiene acceso.

<!--
FOLLOW-UP: Coworker permissions are still being finalized. The Coworker permission name below is a placeholder. Confirm the name, category, and Admin Console steps with the SME.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Coworker]** permission determines access to Coworker. A [product profile administrator](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) must add this permission to your product profile. For more information, see [Access control](/help/technotes/access-control.md#access-control).

-->

### Elija entre el colaborador en Workspace y la aplicación del colaborador

La experiencia del producto para colaboradores tiene muchas de las mismas capacidades que la [aplicación de CX Enterprise Coworker](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat), incluidas las habilidades a las que tiene acceso. Sin embargo, existen diferencias importantes que determinan cuándo se puede utilizar una sobre la otra:

| | Experiencia del producto para compañeros de trabajo | Aplicación de compañeros |
| --- | --- | --- |
| **Cuándo usar** | Desea generar un proyecto que planea conservar, compartir con otros usuarios o actualizar con el tiempo. | Quieres una respuesta rápida. Puede optar por convertir el análisis en un proyecto de Workspace más adelante, si es necesario. |
| **Contexto** | Centrado en el proyecto<p>Utiliza el proyecto de Workspace abierto como punto de partida. Puede hacer referencia a paneles, tablas y componentes que ya se encuentran en el proyecto y generar versiones a partir de ellos.</p> | Centrado en la vista de datos<p>Utiliza las vistas de datos a las que tiene acceso o las que establece como preferencia en la memoria del Compañero de trabajo. Describe lo que desea analizar en el mensaje.</p> |
| **Usuario típico** | Analistas que generan y validan análisis en Workspace. | Usuarios empresariales que deseen respuestas sin necesidad de acceder ni aprender a usar Workspace. |
| **Salida** | El compañero agrega paneles, tablas y componentes directamente al proyecto de Workspace. <p>Si procede, también responde en el chat.</p> | En la conversación se proporcionan respuestas y análisis, con la opción de abrir en Analysis Workspace. |

### Qué puede hacer con Coworker

#### Hacer preguntas sobre el proyecto abierto

Puede hacer preguntas a sus compañeros como las siguientes:

* Resuma el proyecto.
* Encuentre perspectivas y marque anomalías en los datos.
* Ejecute un análisis de causa raíz en un panel.
* Explique cómo hacer algo en Analysis Workspace, como agregar un gráfico de líneas o cómo colorear las celdas de la tabla en función de sus valores.
* Explicar un componente, como una métrica o dimensión.

Para obtener más información, vea [Hacer preguntas sobre un proyecto](#ask-questions-about-a-project).

#### Crear y editar el proyecto abierto

Puede pedirle a su compañero que haga cosas como:

* Cree un panel improvisado con las dimensiones, métricas y el intervalo de fechas que especifique.
* Agregue paneles al proyecto. Sus compañeros añaden nuevos paneles sin sobrescribir los paneles existentes.
* Desglose una tabla o agregue columnas de comparación.
* Cambiar el intervalo de fechas o el tipo de visualización de un panel, como cambiar una tabla a un gráfico de líneas.
* Cambiar el nombre de un panel.
* Aplique un segmento existente por nombre, cree un segmento a partir de una descripción en un idioma sin formato o copie un segmento y cambie su lógica.
* Cree intervalos de fechas y métricas calculadas simples.
* Agregue descripciones o una visualización de texto que contenga perspectivas del proyecto.
* Cree un proyecto con varios paneles o copie un proyecto y adáptelo a una audiencia o región diferentes.
* Guarde el proyecto.

Para obtener más información, vea [Actualizar un proyecto](#update-a-project).

### Cuando el colaborador actualiza el proyecto o responde en el chat

El compañero decide si responder en el panel de chat o cambiar el proyecto en función de lo que le preguntes. Para obtener más información, vea [Actualizar un proyecto](#update-a-project) y [Hacer preguntas sobre un proyecto](#ask-questions-about-a-project).

También puede ser explícito sobre lo que desea que haga su compañero. Por ejemplo, puedes usar frases como _en el chat_ o _solo dime_ para obtener una respuesta en el panel de chat, o frases como _agregar al proyecto_ o _en esta tabla_ para actualizar el proyecto.

## Uso del colaborador con sus proyectos

Sus compañeros pueden ver todos los paneles y tablas del proyecto abierto. Puede pedir a sus compañeros que respondan a preguntas sobre el proyecto o que le ayuden a actualizarlo.

>[!TIP]
>
>Puede interrumpir a los compañeros de trabajo o actualizar el proyecto en cualquier momento:
>
>* **Dirigir o detener una tarea**: mientras el Compañero de trabajo está trabajando, presione **Mayús+Intro** para darle más dirección o presione **Esc** para detenerla.
>
>* **Realizar actualizaciones en un proyecto de Workspace**: si edita el proyecto mientras el Compañero de trabajo está trabajando, el Compañero de trabajo reconoce los cambios.

### Actualizar un proyecto

Cuando le pide a un compañero que cree o edite algo en el proyecto, el compañero actualiza el proyecto en consecuencia. Esto incluye solicitudes que comienzan con palabras como _add_, _create_, _edit_, _break down_, _change_ y _compare_. Por ejemplo, puede pedir a su compañero que añada paneles y tablas, desglose de datos o cree segmentos.

1. En Customer Journey Analytics, abra un proyecto existente de Workspace o cree un nuevo proyecto.

1. Seleccione el icono **Coworker** ![Pregunte a Coworker](/help/assets/icons/coworker.svg) en la esquina superior derecha del encabezado para abrir el panel de chat de Coworker.

1. En el panel de chat, describa lo que quiere que haga su compañero.

   En la tabla siguiente se muestran ejemplos de peticiones de datos.

   | Preguntar | Qué hace el compañero |
   | --- | --- |
   | _Mostrarme sesiones por página del mes pasado_ | Agrega un nuevo panel improvisado con la dimensión, la métrica y el intervalo de fechas que especifique. Los paneles existentes no se sobrescriben. |
   | _Desglosar esta tabla por dispositivo_ | Agrega el desglose a la tabla a la que hace referencia. |
   | _Agregar una comparación con el mes pasado en esta tabla_ | Agrega una columna de comparación a la tabla a la que hace referencia. |
   | _Cambiar el intervalo de fechas de este panel al mes pasado_ | Actualiza el intervalo de fechas del panel. |
   | _Cambiar esta tabla a un gráfico de líneas_ | Cambia el tipo de visualización del panel. |
   | _Cambiar el nombre de este panel a Rendimiento móvil_ | Cambia el nombre del panel. |
   | _Aplicar el segmento Usuarios móviles a este panel_ | Aplica el segmento existente al panel. Su compañero no conoce la definición del segmento, por lo que debe comprobar que el segmento contiene lo que espera. |
   | _Crear un segmento para visitantes de Canadá_ | Crea el segmento y lo añade al proyecto. El segmento aparece en la lista de componentes después de actualizar la página. |
   | _Copie el segmento de visitantes de Canadá y cámbielo a visitantes de México_ | Crea una copia del segmento con la lógica actualizada y la añade al proyecto. |
   | _Crear un intervalo de fechas para las últimas 6 semanas_ | Crea el intervalo de fechas. El intervalo de fechas aparece en la lista de componentes sin una actualización. |
   | _Crear una métrica calculada para los ingresos por sesión_ | Crea la métrica calculada. El compañero puede crear métricas calculadas simples. |
   | _Agregue una descripción a este panel que explique la caída de visitas_ | Añade la descripción al panel. |
   | _Agregar una visualización de texto con información clave_ | Agrega una visualización de texto que contiene las perspectivas al proyecto. |
   | _Crear un proyecto con paneles para tráfico, conversión e ingresos_ | Crea un proyecto con un panel para cada área que describa. |
   | _Copie este proyecto y adáptelo para la región EMEA_ | Crea una copia del proyecto y la adapta a la región especificada. |
   | _Guardar el proyecto_ | Guarda el proyecto. |
   | _Deshacer el desglose que agregó_ | Deshace el cambio que especifique. |
   | _Eliminar los paneles antiguos_ | Enumera los paneles que planea eliminar y espera la confirmación antes de eliminarlos. |

1. Revise los cambios que Coworker ha realizado en el proyecto. Para obtener más información, consulte [Verificar resultados de los compañeros](#verify-coworker-results).

### Hacer preguntas sobre un proyecto

Cuando hace preguntas sobre un proyecto, el colaborador responde en el panel de chat. Esto incluye solicitudes como _explicar_, _resumir_, _discutir_ y _decirme más_. Los resultados del análisis de causa raíz y habilidades similares también permanecen en el panel de chat hasta que le pida a su compañero que los añada al proyecto.

1. En Customer Journey Analytics, abra un proyecto existente de Workspace o cree un nuevo proyecto.

1. Seleccione el icono **Coworker** ![Pregunte a Coworker](/help/assets/icons/coworker.svg) en la esquina superior derecha del encabezado para abrir el panel de chat de Coworker.

1. En el panel de chat, describa lo que quiere que haga su compañero.

   En la tabla siguiente se muestran ejemplos de peticiones de datos.

   | Preguntar | Qué hace el compañero |
   | --- | --- |
   | _Resumir este proyecto_ | Proporciona un resumen en el panel de chat y ofrece la opción de agregarlo al proyecto como una visualización de texto. |
   | _Buscar información en este proyecto_ | Proporciona perspectivas en el panel de chat y ofertas para añadir los resultados al proyecto. |
   | _Marcar cualquier anomalía en este panel_ | Describe las anomalías del panel de chat. Si le pide a su compañero que muestre anomalías en una visualización, es posible que estas no aparezcan. Ver [limitaciones actuales](#current-limitations). |
   | _Realizar un análisis de causa raíz en la caída de visitas móviles_ | Proporciona el análisis en el panel de chat y ofrece opciones para agregar los resultados al proyecto. |
   | _¿Cómo coloreo las celdas según sus valores?_ | Explica los pasos del panel de chat. |
   | _Explicar la métrica Tasa de salida hacia otro sitio_ | Explica el componente en el panel de chat. La explicación no proviene del [diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md). Se ha planificado la compatibilidad con las definiciones del diccionario de datos para una versión futura. |

1. Revise la respuesta que Coworker proporciona. Para obtener más información, consulte [Verificar resultados de los compañeros](#verify-coworker-results).

## Verificar resultados de compañeros

Coworker le ayuda a comprobar la precisión de sus resultados. Tenga en cuenta lo siguiente al revisarlos:

* **Coworker muestra su trabajo**: los segmentos, las métricas y los filtros que utiliza Coworker para responder a una pregunta se agregan al proyecto para que pueda verificarlos.

* **Preguntas de aclaración**: cuando una solicitud es vaga o coincide con más de un componente, el colaborador hace una pregunta de aclaración o sugiere opciones para elegir. Por ejemplo, si más de una métrica coincide con el nombre que ha utilizado, Coworker sugiere las métricas coincidentes.

* **Notas de calidad de datos**: El colaborador incluye notas de calidad de datos en sus respuestas. Por ejemplo, si compara un mes que solo acaba de empezar con un mes completo, el Compañero de trabajo le indicará que la comparación se basa en datos parciales.

## Limitaciones actuales

La experiencia en el producto para el Compañero de trabajo tiene las siguientes limitaciones:

* **Definiciones de segmentos**: Cuando hace referencia a un segmento por su nombre, el Compañero de trabajo no conoce la definición del segmento. Su compañero podría deducir lo que contiene el segmento basándose en su nombre. Compruebe la definición del segmento antes de confiar en los resultados.

* **Diccionario de datos**: El compañero no está conectado al [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md). No puede usar las definiciones del diccionario de datos para explicar métricas y dimensiones.

* **Componentes aprobados**: el compañero no da preferencia a los componentes aprobados sobre los similares.

* **Copiando paneles**: su compañero no puede copiar ni duplicar un panel.

* **Nuevos segmentos en la lista de componentes**: Los segmentos que Coworker crea no aparecen en la lista de componentes en el carril izquierdo hasta que actualice la página. Los intervalos de fechas que crea el Compañero de trabajo aparecen sin actualizar.

* **Detección de anomalías**: Es posible que no aparezcan las anomalías cuando pida a su compañero que las muestre en una visualización.

* **Historial de conversaciones**: las conversaciones se guardan para cada usuario, no con el proyecto. Otros usuarios que abren el proyecto no pueden ver su conversación con el compañero. Para compartir el contexto con otros usuarios, agréguelo a las descripciones de los paneles del proyecto.

* **Varias fichas del explorador**: Si abre la misma conversación en más de una ficha del explorador, el Compañero de trabajo podría perder el control de en qué está trabajando.

* **Idiomas distintos del inglés**: en las vistas de datos que usan un idioma distinto del inglés, el colaborador puede usar una combinación del inglés y el idioma de la vista de datos en sus respuestas.


