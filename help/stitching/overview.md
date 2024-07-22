---
title: Información general de vinculación
description: Información general sobre la vinculación.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: f390789287721a777947093123f672e0a854540a
workflow-type: tm+mt
source-wordcount: '3830'
ht-degree: 12%

---

# Unión

>[!NOTE]
>
>Debe tener el paquete **Select** o superior (para vinculación basada en el campo) o el paquete **Prime** o superior (para vinculación basada en gráficos) para utilizar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.


La vinculación de identidad (o simplemente, la vinculación) es una práctica funcionalidad que aumenta la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. El análisis en canales múltiples es un caso de uso principal que Customer Journey Analytics puede gestionar, lo que le permite combinar y ejecutar informes sin problemas en varios conjuntos de datos de diferentes canales, en función de un identificador común (ID de persona).

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra un problema con su pedido y, a continuación, llama a su equipo de servicio de atención al cliente para que le ayude a resolverlo. Con el análisis en canales múltiples, puede atribuir eventos del centro de llamadas a la publicidad en la que se hizo clic originalmente.

Lamentablemente, no todos los conjuntos de datos basados en eventos que forman parte de la conexión en Customer Journey Analytics están suficientemente rellenados con datos para admitir esta atribución de forma predeterminada. En especial, los conjuntos de datos de experiencias basados en la web o en dispositivos móviles a menudo no tienen una información de ID de persona real disponible en todos los eventos.

La configuración permite volver a incrustar identidades en las filas de un conjunto de datos, asegurándose de que el ID de persona (ID vinculado) esté disponible en cada evento. La vinculación busca los datos de usuario de las sesiones autenticadas y no autenticadas para determinar el valor de ID transitorio común (ID de persona) que se puede utilizar como ID vinculado. Esta regeneración de claves permite resolver registros dispares en un único ID vinculado para su análisis en el nivel de la persona, en lugar de en el nivel de dispositivo o cookie.

El Customer Journey Analytics admite dos tipos de vinculación: vinculación basada en el campo y vinculación basada en gráficos.

## Requisitos previos

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda realizar correctamente el análisis entre canales.

Antes de usar la vinculación, asegúrese de que su organización está preparada con lo siguiente:

- La vinculación incluye la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de activar la vinculación en un conjunto de datos de evento. Consulte [Definición de campos de identidad en la IU](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/fields/identity) para obtener más información.

- Importe los datos deseados en Adobe Experience Platform:

   - Para los datos de Adobe Analytics, consulte [Uso de los datos del grupo de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Para ver otros tipos de datos, consulte [Crear un esquema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) y [Ingesta de datos](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) en la documentación de Adobe Experience Platform.

Se beneficia del análisis en canales múltiples si combina uno o más de los conjuntos de datos enlazados con otros conjuntos de datos, como los datos del centro de llamadas, como parte de la definición de la conexión de Customer Journey Analytics. Esta configuración de conexión supone que esos otros conjuntos de datos ya contienen un ID de persona en cada fila, similar al ID vinculado.


## Limitaciones

>[!IMPORTANT]
>
>- No se admite el uso de `identityMap` como identificador persistente. Debe definir un identificador específico en el conjunto de datos (por ejemplo, `ECID`) como el ID persistente.
>
>- Aplique cualquier cambio que realice en el esquema del conjunto de datos de evento de origen también al nuevo esquema del conjunto de datos vinculado; de lo contrario, este se romperá.
>
>- Si elimina el conjunto de datos de origen, el conjunto de datos enlazado detiene el procesamiento y el sistema lo elimina.
>
>- Las etiquetas de uso de datos no se propagan automáticamente al esquema del conjunto de datos vinculado. Si tiene etiquetas de uso de datos aplicadas al esquema del conjunto de datos de origen, debe aplicar estas etiquetas de uso de datos manualmente al esquema del conjunto de datos vinculado. Consulte [Administración de etiquetas de uso de datos en Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) para obtener más información.

La vinculación es una característica innovadora y sólida, pero tiene limitaciones en cuanto a su uso.

- Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
- La vinculación no transforma el campo que se utiliza para la vinculación de ninguna manera. La vinculación utiliza el valor del campo especificado tal como existe en el conjunto de datos no vinculado dentro del lago de datos.
- El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si aparece unas veces la palabra &quot;Bob&quot; en el campo y otras la palabra &quot;BOB&quot;, estos identificadores se tratan como dos personas independientes.

Asegúrese de no confundir la vinculación con lo siguiente:

- La combinación de dos o más conjuntos de datos. La vinculación solo se aplica a un conjunto de datos. La combinación de conjuntos de datos se produce como resultado de la configuración de una conexión de Customer Journey Analytics y la selección del mismo ID de persona en los conjuntos de datos seleccionados en la conexión.

- La unión de dos conjuntos de datos. En Customer Journey Analytics, una unión se utiliza a menudo para búsquedas o clasificaciones en Analysis Workspace. Aunque la vinculación utiliza la funcionalidad de unión, el proceso en sí mismo implica más que uniones.


## Vinculación basada en el campo

Usted especifica un conjunto de datos de evento, así como el ID persistente (cookie) y el ID transitorio (ID de persona) para ese conjunto de datos. La vinculación basada en el campo crea una nueva columna de ID vinculada en el nuevo conjunto de datos vinculado y actualiza esta columna de ID vinculada en función de las filas que tienen un ID transitorio para ese ID persistente específico. <br/>Puede utilizar la vinculación basada en campos al utilizar Customer Journey Analytics como solución independiente (sin acceso al servicio de identidad de Experience Platform y al gráfico de identidades asociado). O bien, cuando no desee utilizar el gráfico de identidad disponible.

![Vinculación basada en el campo](/help/stitching/assets/fbs.png)

### Cómo funciona la vinculación basada en el campo

La vinculación realiza un mínimo de dos pasadas de datos en un conjunto de datos determinado.

- **Vinculación en tiempo real**: intenta vincular cada visita (evento) conforme se va produciendo. Las visitas de dispositivos que son &quot;nuevos&quot; para el conjunto de datos (nunca se han autenticado) no suelen vincularse en este nivel. Las visitas de dispositivos ya reconocidos se vinculan inmediatamente.

- **Vinculación de repetición**: &quot;reproduce&quot; datos basados en identificadores únicos (ID transitorios) que ha aprendido. En esta fase es en la que las visitas de dispositivos anteriormente desconocidos (ID persistentes) se vinculan (a ID transitorios). Adobe ofrece dos intervalos de reproducción:
   - **Diario**: los datos se reproducen todos los días con una ventana retrospectiva de 24 horas. Esta opción ofrece la ventaja de que las repeticiones son mucho más frecuentes, pero los visitantes no autenticados deben autenticarse el mismo día que visitan el sitio.
   - **Semanal**: los datos se reproducen una vez a la semana con la ventana retrospectiva seleccionada (consulte [opciones](#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de una semana de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.

- **Privacidad**: cuando se reciben solicitudes relacionadas con la privacidad, además de eliminar la identidad solicitada, se debe deshacer cualquier vinculación de esa identidad entre eventos no autenticados.

Los datos que están más allá de la ventana retrospectiva no se reproducen. Un visitante debe autenticarse dentro de una ventana retrospectiva determinada para que una visita no autenticada y una visita autenticada se identifiquen juntas. Una vez que se reconoce un dispositivo, se vincula en vivo a partir de ese momento.

#### Paso 1: Vinculación en tiempo real

La vinculación en tiempo real intenta vincular cada evento tras la recopilación con los dispositivos y canales conocidos.

+++ Detalles

Preste atención al siguiente ejemplo, en el que Bob registra diferentes eventos como parte de un conjunto de datos de eventos.

*Datos tal como aparecieron el día en que se recopilaron:*

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID transitorio (ID de inicio de sesión) | ID con título (después de la unión en directo) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivos** | | **4 personas**:<br/>`246`, `Bob`, `3579`, `81911` |

Tanto los eventos no autenticados como los autenticados en los nuevos dispositivos se cuentan como personas independientes (temporalmente). Los eventos no autenticados en dispositivos reconocidos se vinculan en tiempo real.

La atribución funciona cuando la variable personalizada de identificación está vinculada a un dispositivo. En el ejemplo anterior, todos los eventos, excepto los eventos 1, 8, 9 y 10, se vinculan en tiempo real (todos utilizan el identificador `Bob`). La vinculación en tiempo real &quot;resuelve&quot; el ID vinculado para los eventos 4, 6 y 12.

Los datos con retraso (datos con una marca de tiempo de más de 24 horas) se gestionan con el &quot;mejor esfuerzo&quot;, a la vez que se prioriza la vinculación de los datos actuales para obtener la máxima calidad.

+++

#### Paso 2: Reproducción de la vinculación

A intervalos regulares (una vez a la semana o una vez al día, en función de la ventana retrospectiva seleccionada), la vinculación de reproducción vuelve a calcular los datos históricos en función de los dispositivos que ahora reconoce. Si un dispositivo envía inicialmente datos sin autenticarse y luego inicia sesión, la reproducción de la vinculación vincula esos eventos sin autenticar con la persona correcta.

+++ Detalles

La siguiente tabla representa los mismos datos que arriba, pero muestra números diferentes basados en la reproducción de los datos.

*Los mismos datos después de la reproducción:*

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID transitorio (ID de inicio de sesión) | ID con título (después de la unión en directo) | ID vinculado (después de la reproducción) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![flecha arriba](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![flecha arriba](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivos** | | **4 personas**:<br/>`246`, `Bob`, `3579`, `81911` | **2 personas**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

La atribución funciona cuando la variable personalizada de identificación está vinculada a un dispositivo. En el ejemplo anterior, los eventos 1 y 10 se vinculan como resultado de la reproducción, dejando solo el evento 8 y 9 sin vincular. Y reduciendo la métrica de personas (acumulativa) a 2.

+++

#### Paso 3: Solicitud de privacidad

Cuando recibe una solicitud de privacidad, la ID vinculada se elimina en todos los registros del sujeto del usuario de la solicitud de privacidad.

+++ Detalles

La siguiente tabla representa los mismos datos que los que hemos visto anteriormente, pero muestra el efecto que una solicitud de privacidad para Bob tiene en los datos después de procesarlos. Se eliminan las filas en las que Bob está autenticado (2, 3, 5, 7 y 11), así como Bob como un ID transitorio para otras filas.

*Los mismos datos después de una solicitud de privacidad para Bob:*

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID transitorio (ID de inicio de sesión) | ID con título (después de la unión en directo) | ID vinculado (después de la reproducción) | ID transitorio (ID de inicio de sesión) | ID vinculado (después de la solicitud de privacidad) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![flecha arriba](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flecha derecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![flecha abajo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![flecha arriba](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivos** | | **4 personas**:<br/>246, `Bob`, `3579`, `81911` | **2 personas**:<br/>Bob, `3579` |  | **3 personas**:<br/>`246`, `3579`, `81911` |

+++

### Requisitos previos

Los siguientes requisitos previos se aplican específicamente a la vinculación basada en el campo:

- El conjunto de datos de evento de Adobe Experience Platform al que desee aplicar la vinculación debe tener dos columnas que ayuden a identificar a los visitantes:

   - **ID persistente**, un identificador disponible en cada fila. Por ejemplo, un ID de visitante generado por una biblioteca de AppMeasurement de Adobe Analytics o un ECID generado por el servicio de identidad de Adobe Experience Platform.
   - Un **ID transitorio**, un identificador disponible solo en algunas filas. Por ejemplo, un nombre de usuario o una dirección de correo electrónico con hash una vez que un visitante se autentica. Puede utilizar prácticamente cualquier identificador que desee. La vinculación tiene en cuenta este campo para contener la información de ID de persona real. Para obtener los mejores resultados de vinculación, se debe enviar un ID transitorio dentro de los eventos del conjunto de datos al menos una vez para cada ID persistente. Si planea incluir este conjunto de datos dentro de una conexión de Customer Journey Analytics, es preferible que los demás conjuntos de datos también tengan un identificador común similar.

- Ambas columnas (ID persistente e ID transitorio) deben definirse como un campo de identidad con un área de nombres de identidad en el esquema para el conjunto de datos que desea vincular. Al utilizar la vinculación de identidad en Real-time Customer Data Platform, con el grupo de campos [`identityMap` ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), aún debe agregar campos de identidad con un área de nombres de identidad. Esta identificación de campos de identidad es obligatoria, ya que la vinculación de Customer Journey Analytics no admite el grupo de campos `identityMap`. Al agregar un campo de identidad en el esquema, sin dejar de usar el grupo de campos `identityMap`, no establezca el campo de identidad adicional como identidad principal. La configuración de un campo de identidad adicional como identidad principal interfiere con el grupo de campos `identityMap` que se usa para Real-time Customer Data Platform.

### Limitaciones

Las siguientes limitaciones se aplican específicamente a la vinculación basada en el campo:

- Las capacidades actuales de regeneración de claves están limitadas a un paso (ID persistente a ID transitorio). No se admite la regeneración de claves de varios pasos (por ejemplo, ID persistente a ID transitorio y, a continuación, a otro ID transitorio).
- Si varias personas comparten un dispositivo y el número total de transiciones entre usuarios supera las 50 000, el Customer Journey Analytics deja de vincular datos para ese dispositivo.
- No se admiten los mapas de ID personalizados utilizados en su organización.
- La vinculación distingue entre mayúsculas y minúsculas. Para los conjuntos de datos generados mediante el conector de origen de Analytics, el Adobe recomienda revisar cualquier regla VISTA o de procesamiento que se aplique al campo de ID transitorio. Esta revisión garantiza que ninguna de estas reglas introduzca nuevos formularios del mismo ID. Por ejemplo, debe asegurarse de que ninguna regla VISTA o de procesamiento introduce minúsculas en el campo ID transitorio en solo en una parte de los eventos.
- La configuración no combina ni concatena campos.
- El campo de ID transitorio debe contener un solo tipo de ID (ID de un solo área de nombres). Por ejemplo, el campo de ID transitorio no debe contener una combinación de ID de inicio de sesión e ID de correo electrónico.
- Si se producen varios eventos con la misma marca de tiempo para el mismo ID persistente, pero con valores diferentes en el campo de ID transitorio, la identificación se selecciona en función del orden alfabético. Por lo tanto, si el ID persistente A tiene dos eventos con la misma marca de tiempo y uno de los eventos especifica Bob y el otro Ann, al vincular se selecciona Ann.
- Tenga cuidado con los escenarios donde los ID transitorios contienen valores de marcador de posición, por ejemplo `Undefined`. Consulte las [preguntas frecuentes](faq.md) para obtener más información.


## Identificación basada en gráficos

Puede especificar un conjunto de datos de evento, así como el ID persistente (cookie) y el área de nombres del ID transitorio (ID de persona) para ese conjunto de datos. La vinculación basada en gráficos crea una nueva columna para el ID vinculado en el nuevo conjunto de datos vinculado. Y, a continuación, utiliza el ID persistente para consultar el gráfico de identidades desde el servicio de identidad del Experience Platform, utilizando el área de nombres especificada para actualizar el ID vinculado.

![Vinculación basada en gráficos](/help/stitching/assets/gbs.png)

### Funcionamiento de la vinculación basada en gráficos

La vinculación realiza un mínimo de dos pasadas de datos en un conjunto de datos determinado.

- **Vinculación en tiempo real**: intenta vincular cada visita (evento) conforme se va produciendo, utilizando el ID persistente para buscar el ID transitorio del área de nombres seleccionada consultando el gráfico de identidades. Si el ID transitorio está disponible desde la búsqueda, este ID transitorio se vincula inmediatamente.

- **Reproducir vinculación**: &quot;reproduce&quot; datos basados en identidades actualizadas del gráfico de identidades. En esta fase es en la que las visitas de dispositivos anteriormente desconocidos (ID persistentes) se vinculan a medida que el gráfico de identidad ha resuelto la identidad de un área de nombres. Adobe ofrece dos intervalos de reproducción:
   - **Diario**: los datos se reproducen todos los días con una ventana retrospectiva de 24 horas. Esta opción ofrece la ventaja de que las repeticiones son mucho más frecuentes, pero los visitantes no autenticados deben autenticarse el mismo día que visitan el sitio.
   - **Semanal**: los datos se reproducen una vez a la semana con la ventana retrospectiva (consulte [opciones](#options)). Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos no enlazados con menos de una semana de antigüedad no se vuelven a procesar hasta la siguiente reproducción semanal.

- **Privacidad**: cuando se reciben solicitudes relacionadas con la privacidad, además de quitar la identidad solicitada del conjunto de datos de origen, se debe deshacer cualquier vinculación de esa identidad entre eventos no autenticados. Además, la identidad debe eliminarse del gráfico de identidad para evitar una vinculación futura basada en gráficos para esa identidad específica.

Los datos que están más allá de la ventana retrospectiva no se reproducen. Un visitante debe autenticarse dentro de una ventana retrospectiva determinada para que una visita no autenticada y una visita autenticada se identifiquen juntas. Una vez que se reconoce un dispositivo, se vincula en vivo a partir de ese momento.

Considere los dos gráficos de identidad siguientes para el ID persistente `246` y `3579`, cómo se actualizan estos gráficos de identidad con el paso del tiempo y cómo afectan estas actualizaciones a los pasos de la vinculación basada en gráficos.

![Gráfico de identidad 246](assets/identity-graph-246.svg)
![Gráfico de identidad 3579](assets/identity-graph-3579.svg)

Puede ver un gráfico de identidad a lo largo del tiempo para un perfil específico mediante el [Visor de gráficos de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulte también [Lógica de vinculación del servicio de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) para comprender mejor la lógica utilizada al vincular identidades.

#### Paso 1: Vinculación en tiempo real

La vinculación en tiempo real intenta vincular cada evento, tras la recopilación, con la información conocida en ese momento del gráfico de identidad.

+++ Detalles

| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID con título (después de la unión en directo) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *sin definir* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *sin definir* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Puede ver cómo se resuelve el ID vinculado para cada evento. En función del tiempo, el ID persistente y la búsqueda del gráfico de identidad para el área de nombres especificada (al mismo tiempo).
Cuando la búsqueda responde a más de un ID vinculado (como en el caso del evento 7), se selecciona el primer ID lexicográfico devuelto por el gráfico de identidad (`a.b@yahoo.co.uk` en el ejemplo).

+++

#### Paso 2: Reproducción de la vinculación

A intervalos regulares (en función de la ventana retrospectiva seleccionada), la vinculación de reproducción vuelve a calcular los datos históricos en función de la versión más reciente del gráfico de identidad, en el momento del intervalo.

+++ Detalles

Con una vinculación de reproducción a las 16:30 del 2023-05-13, con una configuración de ventana retrospectiva de 24 horas, algunos eventos de la muestra se vuelven a vincular (indicado por ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Id. con título <br/> (después de la unión activa) | Id. vinculado <br/> (después de la reproducción 24 horas) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Con la vinculación de reproducción a las 16:30 del 2023-05-13, con una configuración de ventana retrospectiva de 7 días, todos los eventos de la muestra se vuelven a vincular.


| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Id. con título <br/> (después de la unión activa) | ID vinculado <br/> (después de la reproducción 7 días) |
|---|---|---|---|---|---|
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *sin definir* | `246` | `a.b@yahoo.co.uk` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproducir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### Paso 3: Solicitud de privacidad

Cuando recibe una solicitud de privacidad, la ID vinculada se elimina en todos los registros del sujeto del usuario de la solicitud de privacidad.

+++ Detalles

La siguiente tabla representa los mismos datos que los que hemos visto anteriormente, pero muestra el efecto que una solicitud de privacidad (por ejemplo, las 18:00 del 13-05-2023) tiene en los eventos de ejemplo.

| | Fecha | Id. persistente<br/>`ECID` | Espacio de nombres <br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID vinculado (después de la solicitud de privacidad) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Vínculo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### Requisitos previos

Los siguientes requisitos previos se aplican específicamente a la vinculación basada en gráficos:

- El conjunto de datos de evento de Adobe Experience Platform al que desea aplicar la vinculación debe tener una columna que identifique a un visitante en cada fila, la **ID persistente**. Por ejemplo, un ID de visitante generado por una biblioteca de AppMeasurement de Adobe Analytics o un ECID generado por el servicio de identidad de Experience Platform.
- El identificador persistente también debe estar [definido como identidad](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/fields/identity) en el esquema.
- El gráfico de identidades del servicio de identidad de Experience Platform debe tener un área de nombres (por ejemplo `Email` o `Phone`) que desee usar durante la vinculación para resolver el **ID transitorio**. Consulte [Servicio de identidad de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/identity/home) para obtener más información.

>[!NOTE]
>
>No necesita **not** una licencia de Real-time Customer Data Platform para la vinculación basada en gráficos. El paquete **Prime** o superior de Customer Journey Analytics incluye los derechos necesarios del servicio de identidad de Experience Platform.


### Limitaciones

Las siguientes limitaciones se aplican específicamente a la vinculación basada en gráficos:

- Las marcas de tiempo no se tienen en cuenta al consultar el ID transitorio mediante el área de nombres especificada. Por lo tanto, es posible que un ID persistente se vincule con un ID transitorio de un registro que tenga una marca de tiempo anterior.
- No es compatible con dispositivos compartidos. Cuando se devuelven varias identidades, al consultar el gráfico de identidades mediante un área de nombres, se utiliza la primera identidad lexicográfica.
- Hay un límite estricto de tres meses para rellenar identidades en el gráfico de identidades. Se utilizan identidades de relleno en caso de que no se utilice una aplicación Experience Platform, como Real-time Customer Data Platform, para rellenar el gráfico de identidades.
- Se aplican las [protecciones del servicio de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails). Vea, por ejemplo, los [límites estáticos](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits) siguientes:
   - Número máximo de identidades en un gráfico: 50.
   - Número máximo de vínculos a una identidad para una sola ingesta por lotes: 50.
   - Número máximo de identidades en un registro XDM para la ingesta de gráficos: 20.
   - Cantidad mínima de identidades en un registro XDM para la ingesta de gráficos: 2.


## Usar vinculación

Una vez que su organización cumpla todos los [requisitos previos](#prerequisites) y comprenda las [limitaciones](#limitations) comunes y las limitaciones ([basadas en campos](#limitations-1) y [basadas en gráficos](#limitations-2)) específicas del método de vinculación, puede seguir estos pasos para empezar a utilizar la vinculación en el Customer Journey Analytics.

### Seleccionar opciones

El paquete de Customer Journey Analytics al que está autorizado determina los métodos de vinculación disponibles, las opciones para la duración del relleno inicial, la ventana retrospectiva, la frecuencia de reproducción y el número máximo de conjuntos de datos permitidos para la vinculación. Consulte la [descripción del producto del Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es) para obtener más información. Decida las opciones disponibles antes de solicitar asistencia.

| | Customer Journey Analytics<br/>Seleccionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Métodos de vinculación disponibles | <li>Vinculación basada en el campo</li> | <li>Vinculación basada en el campo</li><li>Identificación basada en gráficos</li> | <li>Vinculación basada en el campo</li><li>Identificación basada en gráficos</li> |
| Duración de relleno de vinculación única | 13 meses | 13 meses | 25 meses |
| Ventana retrospectiva y frecuencia de reproducción | <li>1 día, todos los días</li><li>hasta 7 días, semanales</li> | <li>1 día, todos los días</li><li>hasta 14 días, semanales</li> | <li>1 día, todos los días</li><li>hasta 30 días por semana</li> |
| Número máximo de conjuntos de datos permitidos para la vinculación | 5 | 10 | 50 |

### Solicitar asistencia

1. Póngase en contacto con Asistencia al cliente de Adobe con la siguiente información:

   - Una solicitud para habilitar la vinculación.
   - ID del conjunto de datos para el que desea volver a escribir.
   - El nombre de columna (ruta de identidad y área de nombres) del ID persistente del conjunto de datos deseado (el identificador que aparece en cada fila).
   - Para la vinculación basada en el campo, el nombre de columna del ID transitorio para el conjunto de datos deseado (el identificador personal, que también actúa como vínculo entre conjuntos de datos en el contexto de una conexión). Para la vinculación basada en gráficos, el área de nombres de identidad que se utilizará para consultar el gráfico de identidad.
   - Su preferencia de ventana retrospectiva y frecuencia de reproducción. Consulta con tu Customer Journey Analytics el paquete de [opciones](#options) disponibles.
   - Nombre de la zona protegida.


2. La Asistencia al cliente de Adobe trabaja con el personal de ingeniería de Adobes para habilitar la vinculación al recibir la solicitud. Una vez habilitado, aparecerá en Adobe Experience Platform un nuevo conjunto de datos con clave con una nueva columna de ID vinculada. La Asistencia al cliente de Adobe puede proporcionar el ID del nuevo conjunto de datos.

3. Cuando se activa por primera vez, el Adobe proporciona un relleno de datos vinculados. Consulte el paquete del Customer Journey Analytics para ver la [opción](#options) disponible.

4. Si desea utilizar el nuevo conjunto de datos vinculado en un análisis en canales múltiples, debe agregar el nuevo conjunto de datos vinculado a una [conexión](../connections/overview.md) en el Customer Journey Analytics. A continuación, añada cualquier otro conjunto de datos necesario para el análisis entre canales y seleccione el ID de persona correcto para cada conjunto de datos.

5. [Cree una vista de datos](/help/data-views/create-dataview.md) en función de la conexión.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una vez configurada la vista de datos, puede ejecutar el análisis de creación de informes de Customer Journey Analytics en varios canales y dispositivos.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

