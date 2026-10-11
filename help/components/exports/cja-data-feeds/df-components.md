---
title: Componentes disponibles en las fuentes de datos de Customer Journey Analytics
description: Descubra qué dimensiones y métricas son necesarias, no son compatibles, están restringidas o deben sustituirse al crear fuentes de datos de Customer Journey Analytics.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: adc7e85339e89c181375c0d3ea5c228d473239a7
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 43%
---
# Disponibilidad de componentes en fuentes de datos

{{release-limited-testing}}

No todos los componentes de Customer Journey Analytics se pueden usar en fuentes de datos. Algunas dimensiones se incluyen en cada fuente de datos, algunos componentes no se pueden incluir y algunas métricas deben reemplazarse con un sustituto.

Use la siguiente información para comprender qué componentes puede incluir al [crear una fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md).

## Dimensiones necesarias {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="Dimensiones necesarias"
>abstract="Cada fuente de datos debe incluir determinadas dimensiones, identificadas por una etiqueta **Necesario** junto al nombre de la dimensión. Estas dimensiones proporcionan la estructura mínima necesaria para el análisis a nivel de evento."

<!-- markdownlint-enable MD034 -->

Las siguientes dimensiones se incluyen de forma predeterminada en todas las fuentes de datos y no se pueden eliminar:

| Nombre de la dimensión | Notas | Fuentes de datos | Otros informes |
|---|---|---|---|
| Marca de tiempo UTC | La fecha y la hora en que se produjo el evento, representadas en la zona horaria UTC. Admite granularidad de subsegundos (microsegundos). | Requerido | No disponible |
| ID de fila | El identificador único de cada fila se incluye en el feed de datos. | Requerido | No disponible |
| ID de sesión | El identificador único de cada sesión se incluye el feed de datos. | Requerido | No disponible |
| ID de persona | El identificador personal de la vista de datos y la conexión | Requerido | Estándar opcional |
| ID de cuenta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ID de cuenta al utilizar el contenedor de cuenta | Requerido | Estándar opcional |

## Dimensiones no admitidas {#unsupported-dimensions}

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

## Métricas no admitidas {#unsupported-metrics}

Las siguientes métricas estándar de Customer Journey Analytics no se pueden incluir en las fuentes de datos:

| Nombre de la métrica | Notas | Fuentes de datos |
|---|---|---|
| Perfil de visitantes de Adobe | | No disponible |
| Unión de oportunidades de Adobe | | No disponible |
| Perfil de oportunidades de Adobe | | No disponible |
| Unión de cuentas de Adobe | | No disponible |
| Perfil de cuentas de Adobe | | No disponible |
| Adobe Buying Groups Union | | No disponible |
| Perfil de grupos de compra de Adobe | | No disponible |
| Unión de cuentas globales de Adobe | | No disponible |
| Perfil de cuentas globales de Adobe | | No disponible |
| Adobe Persons Union | | No disponible |
| Perfil de personas de Adobe | | No disponible |

## Dimensiones que no se pueden usar juntas {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

<!-- pretty sure this isn't being used -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="Los datos del agente de usuario y los datos de búsqueda del dispositivo no pueden existir en la misma configuración de la fuente de datos."

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>Ciertas dimensiones no se pueden usar juntas en conjuntos de datos de Experience Platform y, por lo tanto, no se pueden incluir en la misma fuente de datos.
>
>Si decide incluir las dimensiones **User agent** o **Mobile ID** en su fuente de datos, las dimensiones que se indican a continuación no se podrán agregar a la fuente de datos.
>
>Si utiliza Web SDK, esta restricción se aplica en las secuencias de datos antes de que los datos lleguen a un conjunto de datos de Experience Platform. Para obtener más información, consulte [Configurar la búsqueda de dispositivos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure#geolocation-device-lookup) en [Crear y configurar flujos de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure) en la guía de recopilación de datos.

Las siguientes dimensiones no se pueden usar junto con las dimensiones **Agente de usuario** o **ID móvil**:

>[!NOTE]
>
>La siguiente lista utiliza nombres de dimensión predeterminados. Las dimensiones con nuevos nombres en la vista de datos aparecen en las fuentes de datos con sus nombres personalizados.


* Tipo de explorador
* Explorador
* ID de explorador
* Fabricante de dispositivos móviles
* Tipo de dispositivo móvil
* Compatibilidad con el audio del dispositivo móvil
* DRM móvil
* Máquina virtual Java móvil
* Servicios de información móvil
* Compatibilidad con la imagen del dispositivo móvil
* Profundidad de color del dispositivo móvil
* Protocolos de red móvil
* Número de dispositivo móvil
* Longitud máxima del correo electrónico móvil
* Decoración de correo móvil
* Pulsar y hablar móvil
* Ancho de la pantalla del dispositivo móvil
* Longitud máxima de la dirección URL del explorador móvil
* Sistema operativo móvil (obsoleto)
* Altura de la pantalla del dispositivo móvil
* Compatibilidad con el video del dispositivo móvil
* Compatibilidad con cookies del dispositivo móvil
* Longitud máxima del marcador móvil
* Tamaño de la pantalla del dispositivo móvil
* Nombre de dispositivo móvil
* Tipos de sistemas operativos
* Sistemas operativos
* ID del sistema operativo

## Métricas que requieren un sustituto {#substitute-metrics}

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

## Componentes estándar opcionales {#optional-standard-components}

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
