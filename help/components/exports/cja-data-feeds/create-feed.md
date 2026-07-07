---
title: Crear un feed de datos
description: Aprenda a crear una fuente de datos y conozca la información del archivo que debe proporcionar a Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 66a8a96da6710d20b01b9315fe87ba38c54c2511
workflow-type: tm+mt
source-wordcount: 2675
ht-degree: 29%

---

# Creación de un feed de datos

{{release-limited-testing}}

Al crear un feed de datos, debe proporcionar a Adobe lo siguiente:

* La información sobre el destino al que desea enviar los archivos de datos sin procesar

* Los datos que desea incluir en cada archivo

* La frecuencia con la que se envían los datos (incluido el retraso de procesamiento para capturar las visitas que llegan tarde)

Antes de crear un feed de datos, es importante tener una comprensión básica de las fuentes de datos y asegurarse de que cumple todos los requisitos previos. Para obtener más información, consulte [Información general sobre feeds de datos](data-feed-overview.md).

## Crear o configurar una fuente de datos {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="Manifiesto"
>abstract="Elija si desea incluir un archivo de manifiesto con cada entrega de feed de datos. Los archivos de manifiesto contienen información para cada archivo incluido en el feed de datos. Al enviar datos del feed de datos en un solo paquete, también puede optar por incluir un archivo de finalización, pero se recomiendan los archivos de manifiesto. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="Notificar cuando se complete"
>abstract="Especifique una o varias direcciones de correo electrónico a las que se debe enviar una notificación después de enviar el feed de datos. Las múltiples direcciones de correo electrónico deben separarse con una coma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Intervalo de fecha de retroactividad"
>abstract="Controla hasta qué momento del tiempo se remonta Customer Journey Analytics cuando procesa el envío de fuentes de datos.<br/>Esta configuración no altera el intervalo de frecuencia (hora o día). Sin embargo, el intervalo de fechas de retroactividad puede influir en los datos que se envían. La calificación de segmentos, el cálculo de sesiones, algunas transformaciones de campos derivadas y la persistencia de dimensiones se verán todas afectadas por el intervalo de fechas de retroactividad."

<!-- markdownlint-enable MD034 -->

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.

1. Selecciona [!UICONTROL **Customer Journey Analytics**] del conmutador de aplicaciones ![Aplicación](/help/assets/icons/Apps.svg) en la parte superior derecha de la interfaz.

1. En la barra de navegación superior, vaya a [!UICONTROL **Componentes**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione [!UICONTROL **Crear**] en la esquina superior derecha de la pantalla.

   O bien, si no se han creado fuentes de datos anteriormente, seleccione [!UICONTROL **Crear fuente de datos**] en la tabla vacía.

   Aparece una página con las siguientes fichas: [!UICONTROL **Detalles**], [!UICONTROL **Estructura de datos**] y [!UICONTROL **Envío**].

   ![Nueva página de fuente de datos](assets/data-feed-new.png)

1. En la ficha [!UICONTROL **Detalles**], rellene los campos siguientes:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre**] | El nombre de la fuente de datos. Los nombres deben ser únicos en la vista de datos seleccionada y pueden tener hasta 255 caracteres de longitud. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Etiquetas**] | Aplique cualquier etiqueta a la fuente de datos para facilitar la categorización. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Descripción**] | Especifique una descripción para la fuente de datos. La descripción que agregue será visible al editar la fuente de datos. |
   | [!UICONTROL **Vista de datos**] | Seleccione la vista de datos que contiene los datos que desea exportar.<p>Tenga en cuenta lo siguiente al seleccionar una vista de datos:</p> <ul><li>Si se crean varias fuentes de datos para la misma vista de datos, cada fuente de datos debe tener definiciones de columnas diferentes.</li><li>La lista de columnas disponibles depende de la empresa de inicio de sesión a la que pertenezca la vista de datos seleccionada. Si cambia la vista de datos, puede cambiar la lista de columnas disponibles. </li></ul> |

1. Seleccione [!UICONTROL **Siguiente**].

1. En la ficha [!UICONTROL **Estructura de datos**], asegúrese de que la vista de datos correcta esté seleccionada en el campo **[!UICONTROL Vista de datos]**.

1. En el menú desplegable [!UICONTROL **Segmentos**], busque y seleccione cualquier segmento para filtrar los datos incluidos en la fuente.

   Cuando se aplican varios segmentos, se unen con un operador AND. (Para unir segmentos con un operador OR, primero debe crear un nuevo segmento en el generador de segmentos y, a continuación, aplicar el nuevo segmento a la fuente de datos).

1. Agregue componentes a la configuración de la fuente de datos. En el carril izquierdo, busque los componentes que desee incluir y arrástrelos al lienzo para crear la estructura de datos. Para seleccionar varios componentes, mantén pulsada **[!UICONTROL Mayús]**, o manteniendo pulsado **[!UICONTROL Comando]** (en macOS) o **[!UICONTROL Ctrl]** (en Windows).

   Utilice la siguiente información para comprender las dimensiones que siempre se incluyen, las dimensiones que no se pueden incluir y las métricas que se deben sustituir:

   +++ Dimensiones que siempre se incluyen en las fuentes de datos

   Las siguientes dimensiones se incluyen de forma predeterminada en todas las fuentes de datos y no se pueden eliminar:

   | Nombre de la dimensión | Notas | Fuentes de datos | Otros informes |
   |---|---|---|---|
   | Marca de tiempo | Marca de tiempo del periodo del evento. Granularidad de microsegundos. Representado en UTC. | Obligatorio | No disponible |
   | Identificador de fila | Identificador de fila único | Obligatorio | No disponible |
   | ID de sesión | Identificador único de cada sesión | Obligatorio | No disponible |
   | ID de persona | El identificador personal de la vista de datos y la conexión | Obligatorio | Estándar opcional |
   | ID de cuenta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ID de cuenta al utilizar el contenedor de cuenta | Obligatorio | Estándar opcional |

   +++

   +++ Dimensiones que no se pueden incluir en las fuentes de datos

   Las dimensiones estándar de Customer Journey Analytics no se pueden incluir en las fuentes de datos. En la tabla siguiente se enumeran estas dimensiones:

   | Nombre de la dimensión | Notas | Fuentes de datos |
   |---|---|---|
   | 5 minutos | Intervalos de cinco minutos cuando ocurrieron los eventos (redondeados hacia abajo) | No disponible |
   | 15 minutos | Intervalos de quince minutos cuando ocurrieron los eventos (redondeados hacia abajo) | No disponible |
   | 30 minutos | Intervalos de treinta minutos cuando ocurrieron los eventos (redondeados hacia abajo) | No disponible |
   | Día | Día en que se produjo un evento | No disponible |
   | Día de la semana | Día de la semana en que se produjo un evento | No disponible |
   | Día del mes | Día del mes en el que se produjo un evento | No disponible |
   | Hora | Hora a la que se produjo un evento (redondeado hacia abajo) | No disponible |
   | Hora del día | Hora del día en que se produjo un evento (redondeado hacia abajo) | No disponible |
   | Minuto | Minuto en que se produjo un evento (redondeado hacia abajo) | No disponible |
   | Minuto de la hora | Minuto de la hora en que se produjo un evento (redondeado hacia abajo) | No disponible |
   | Mes | Mes en el que se produjo un evento | No disponible |
   | Mes del año | Mes del año en el que se produjo un evento | No disponible |
   | Trimestre | Trimestre en que se produjo un evento | No disponible |
   | Trimestre del año | Trimestre del año en el que se produjo un evento | No disponible |
   | Second | Segundo evento (redondeado hacia abajo) | No disponible |
   | Semana | Semana en que se produjo un evento | No disponible |
   | Semana del año | Semana del año en que se produjo un evento | No disponible |
   | Año | Año en el que se produjo un evento | No disponible |

   +++

   +++ Métricas que deben sustituirse en las fuentes de datos

   Se deben sustituir las siguientes métricas de Customer Journey Analytics:

   | Nombre de la métrica | Notas | Fuentes de datos |
   |---|---|---|
   | Cuentas [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Según el ID de cuenta especificado en la conexión | No disponible. Utilice un recuento distinto del ID de cuenta. |
   | Comprando grupo [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Comprar grupos en función del ID del grupo de compra en la conexión | No disponible. Utiliza un recuento distinto del ID del grupo de compra. |
   | Eventos | Número de filas de todos los conjuntos de datos de evento de una conexión | No disponible. Utilice un recuento distinto del ID de fila. |
   | Cuentas globales [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Según el ID de cuentas globales de la conexión | No disponible. Utilice un recuento distinto del ID de cuentas globales. |
   | Oportunidades [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Oportunidades basadas en el ID de oportunidad en la conexión | No disponible. Utilice un recuento distinto del ID de oportunidad. |
   | Personas | Según el ID de persona especificado en una conexión | No disponible. Utilice un recuento distinto del ID de persona. |
   | Conversaciones | Número de conversaciones | No disponible. Utilice un recuento distinto del ID de conversación. |
   | Terminaciones de sesión | Número de eventos que fueron el último evento de una sesión | No disponible |
   | La sesión inicia | Número de eventos que fueron el primer evento de una sesión | No disponible |
   | Sesiones | Basado en la configuración de sesión de la vista de datos | No disponible. Utilice un recuento distinto del ID de sesión. |
   | Tiempo empleado (segundos) | Suma el tiempo entre dos valores de dimensión diferentes | No disponible |

   +++

   +++ Componentes estándar opcionales

   | Nombre del componente | Tipo | Notas | Fuentes de datos |
   |---|---|---|---|
   | AM/PM | Dimensión de partición de tiempo | a. m. o p. m. | No disponible |
   | ID de lote | Dimensión | Identificador de un lote de Experience Platform | Disponible |
   | ID de conjunto de datos | Dimensión | Identificador de un conjunto de datos de Experience Platform | Disponible |
   | Día del mes | Dimensión de partición de tiempo | 1-31 | No disponible |
   | Día de la semana | Dimensión de partición de tiempo | De lunes a domingo | No disponible |
   | Día del año | Dimensión de partición de tiempo | 1-366 | No disponible |
   | Profundidad del evento | Dimensión | Valor numérico secuencial (1, 2, 3, etc.) asignado a cada interacción de evento dentro de una sesión<p>Se restablece al principio de cada nueva sesión</p> | Disponible |
   | Hora del día | Dimensión de partición de tiempo | 0-23 | No disponible |
   | Mes del año | Dimensión de partición de tiempo | Enero-diciembre | No disponible |
   | Sesiones por primera vez | Métrica | Primera sesión definida por una persona dentro de la ventana de creación de informes | No disponible |
   | Sesiones de retorno | Métrica | Sesiones que no fueron la primera sesión de una persona | No disponible |
   | Área de nombres de ID de persona | Dimensión | Tipo de ID del que consta el ID de persona (por ejemplo, correo electrónico o ID de cookie) | Disponible |
   | ID de cuenta global [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensión | ID de cuenta global al usar el contenedor de cuenta global | Disponible |
   | ID de oportunidad [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensión | ID de oportunidad al utilizar el contenedor de oportunidad | Disponible |
   | Comprando el identificador de grupo [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensión | ID del grupo de compra al utilizar el contenedor de grupo de compra | Disponible |
   | Trimestre del año | Dimensión de partición de tiempo | T1, T2, T3, T4 | No disponible |
   | Repetir sesión | Métrica | Sesiones que no fueron la primera sesión de una persona | No disponible |
   | Tipo de sesión | Dimensión | Dos valores: Primera vez o Retorno | No disponible |
   | Tiempo empleado por evento | Dimensión | Agrupa el Tiempo empleado de la métrica en bloques de eventos | No disponible |
   | Tiempo empleado por sesión | Dimensión | Agrupa el Tiempo empleado de la métrica en bloques de sesiones | No disponible |
   | Tiempo empleado por persona | Dimensión | Agrupa el Tiempo empleado de la métrica en bloques de personas | No disponible |
   | Fin de semana / Día de la semana | Dimensión de partición de tiempo | Fin de semana o día laborable | No disponible |

   +++


1. En la ficha [!UICONTROL **Envío**], especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Tipo de fuente**] | Seleccione el tipo de fuente que desea crear:<ul><li>[!UICONTROL **Fuente activa**]: exporta datos actuales y futuros.</li><li>[!UICONTROL **Fuente de relleno**]: exporta datos históricos entre dos fechas pasadas.</li></ul> |
   | [!UICONTROL **Fecha de inicio**] | Especifique la fecha en la que desea que comience la fuente de datos. Para empezar a procesar fuentes de datos para datos históricos de inmediato, asegúrese de seleccionar [!UICONTROL **Fuente de relleno**] y luego establezca esta fecha en cualquier fecha del pasado en que se estén recopilando datos. La fecha de inicio se basa en la zona horaria de la vista de datos. |
   | [!UICONTROL **Fecha de finalización**] | Especifique la fecha en la que desea que finalice la fuente de datos. La fecha de finalización se basa en la zona horaria de la vista de datos. |
   | [!UICONTROL **Frecuencia**] | Seleccione la frecuencia con la que se debe enviar la fuente de datos. Los eventos con marcas de tiempo incluidas en la ventana de frecuencia se incluyen en la entrega de fuentes de datos. Los campos [!UICONTROL **Intervalo de fechas de retrospectiva**] y [!UICONTROL **Demora de procesamiento**] también pueden afectar qué eventos se incluyen en los datos para la frecuencia de envío que elija.<p>En el caso de las fuentes en directo, seleccione esta opción para incluir datos de una hora o de un día. Las fuentes de relleno deben ser diarias.</p><ul><li>**Diario**: las fuentes contienen datos de un día completo, de medianoche a medianoche en el huso horario de la vista de datos. Utilice esta opción para fuentes de relleno o para fuentes activas.</li><li>**Por hora**: las fuentes contienen datos de una sola hora. Utilice esta opción para las fuentes activas.</li></ul> |
   | [!UICONTROL **Intervalo de fechas de retrospectiva**] | Controla hasta qué momento del tiempo se remonta Customer Journey Analytics cuando procesa el envío de fuentes de datos. <p>Esta configuración no altera la ventana de frecuencia (hora o día), que define el lapso de tiempo de los eventos que se incluirán en la salida de fuente de datos. Sin embargo, el intervalo de fechas de retrospectiva puede influir en los datos que se envían de las siguientes maneras: </p><ul><li>**Calificación de segmentos**: Cuando se aplica un segmento a su definición de fuente de datos, cualquier evento dentro del intervalo de fechas retrospectivas determina si una persona cumple los requisitos. La configuración del contenedor del segmento determina el ámbito. (Los contenedores posibles son: Persona, Sesión o Evento. B2B tiene los siguientes contenedores adicionales: Cuenta global, Cuenta, Oportunidad, Grupo de compra).  <p>Por ejemplo, si se utiliza un contenedor de persona y la persona se califica durante el intervalo de fechas retrospectivas, también se calificarán todos los eventos de esa persona durante la ventana de frecuencia.</p></li><li>**Cálculo de sesión**: los límites de sesión se calculan usando datos dentro del intervalo de fechas retrospectivo.</li><li>**Transformaciones de campo derivadas**: todas las funciones de campo derivadas que hacen referencia a contenedores utilizan el intervalo de fecha retrospectiva en las exportaciones de fuentes de datos.</li><li>**Persistencia de Dimension**: Si elige establecer la persistencia en una dimensión individual, también elige una caducidad para determinar cuánto tiempo persiste un elemento de dimensión más allá del evento en el que está establecido. <p>El intervalo de fechas de retrospectiva afecta a la persistencia de la dimensión cuando la caducidad se establece en cualquiera de las siguientes opciones de la vista de datos:</p><ul><li>Para cada dimensión de la definición de fuente de datos que usa [!UICONTROL **Ventana de informes**] como caducidad, el intervalo de fecha retrospectiva se convierte en la nueva ventana de informes.</li><li>Para cada dimensión de la definición de fuente de datos que usa [!UICONTROL **Tiempo personalizado**] como caducidad, y si la hora personalizada que se selecciona se extiende más allá del intervalo de fechas de retrospectiva, se ignora la hora personalizada y se usa el intervalo de fechas de retrospectiva para la caducidad de la dimensión.<p>Para obtener más información acerca de cómo establecer la persistencia en dimensiones dentro de la vista de datos, vea [Configuración del componente de persistencia](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Retraso de procesamiento**] | Elija la cantidad de tiempo de espera antes de procesar un archivo de fuente de datos. Las visitas que llegan tarde y que se producen durante el retraso del procesamiento se incluyen en la fuente de datos. <p>Los retrasos en el procesamiento son útiles por varios motivos, como dar a las implementaciones móviles la oportunidad de que los dispositivos sin conexión se conecten y envíen datos, o para dar cabida a los procesos del lado del servidor de su organización en la administración de archivos procesados anteriormente. </p><p>Puede retrasar una fuente 2, 3, 4 u 8 horas.<p>Las sesiones deben comenzar después del límite de retraso de procesamiento para que se incluyan; no se incluyen las sesiones que comienzan antes del límite y finalizan dentro del retraso de procesamiento.</p> |
   | [!UICONTROL **Formato de compresión**] | Seleccione el formato de compresión para los archivos de salida de Parquet enviados a su destino de nube. Elija entre los siguientes formatos:<ul><li>[!UICONTROL **Rápido**]: Compresión y descompresión rápidas con tamaños de archivo moderados. Ampliamente compatible con plataformas de datos modernas como BigQuery, Snowflake y Apache Spark.</li><li>[!UICONTROL **GZip**]: Ampliamente compatible, incluso con herramientas que no admiten Snappy de forma nativa. Se recomienda si la canalización descendente requiere un estándar de compresión ampliamente reconocido.</li><li>[!UICONTROL **Z Standard (Zstd)**]: Alta eficiencia de compresión con descompresión rápida. Adecuado si minimizar el tamaño del archivo es una prioridad y sus herramientas admiten Zstd.</li></ul> |

1. En la ficha [!UICONTROL **Delivery**], en la sección [!UICONTROL **Destination**], configure el destino al que desea enviar los datos.

   >[!NOTE]
   >
   >Al configurar el destino de un informe, tenga en cuenta lo siguiente:
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Todas las cuentas de nube que haya configurado anteriormente están disponibles para su uso en fuentes de datos. Puede configurar cuentas en la nube desde el administrador Ubicaciones, en [Componentes > Exportaciones > Cuentas de ubicación](/help/components/exports/cloud-export-accounts.md).
   >
   >* Las cuentas de nube de están asociadas a su cuenta de usuario de Customer Journey Analytics. Otros usuarios no pueden usar ni ver las cuentas de nube que configure a menos que las ponga a disposición de todos los usuarios de su organización.
   >
   >* Puede editar cualquier ubicación que cree desde el administrador Ubicaciones en [Componentes > Exportaciones > Ubicaciones](/help/components/exports/cloud-export-locations.md).

   Complete los campos siguientes:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Ver destinos para todos los usuarios**] | Si es administrador del sistema, puede activar esta opción para ver los destinos creados por todos los usuarios de su organización. Cuando esta opción está desactivada, solo se muestran los destinos que ha creado. |
   | [!UICONTROL **Cuenta**] | Realice cualquiera de los siguientes pasos:<ul><li>**Usar una cuenta existente:** Seleccione el menú desplegable situado junto al campo **[!UICONTROL Cuenta]**. O bien, empiece a escribir el nombre de la cuenta y, a continuación, selecciónela en el menú desplegable. <p>Las cuentas solo están disponibles si las ha configurado o si se comparten con una organización de la que forma parte.</p></li><li>**Crear una nueva cuenta:** Seleccione **[!UICONTROL Agregar cuenta]** en el menú desplegable **[!UICONTROL Cuenta]**. Para obtener información sobre cómo configurar la cuenta, consulte [Configurar cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Ubicación**] | Realice cualquiera de los siguientes pasos:<ul><li>**Usar una ubicación existente:** Seleccione el menú desplegable situado junto al campo **[!UICONTROL Ubicación]**. O bien, empiece a escribir el nombre de la ubicación y, a continuación, selecciónela en el menú desplegable.</li><li>**Crear una nueva ubicación:** Seleccione **[!UICONTROL Agregar ubicación]** en el menú desplegable **[!UICONTROL Ubicación]**. Para obtener información sobre cómo configurar la ubicación, consulte [Configurar ubicaciones de exportación de la nube](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Notificar cuando se complete**] | Especifique una o varias direcciones de correo electrónico a las que se debe enviar una notificación después de que la fuente de datos se haya enviado correctamente o no se haya enviado. Las múltiples direcciones de correo electrónico deben separarse con una coma. |
   | [!UICONTROL **Habilitar manifiesto**] | Elija si desea incluir un archivo de manifiesto con cada entrega de feed de datos. El archivo de manifiesto contiene información para cada archivo incluido en la fuente de datos. |

1. Seleccione **[!UICONTROL Guardar]**.


