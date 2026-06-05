---
title: Búsquedas compartidas
description: Descubra cómo las búsquedas compartidas en Customer Journey Analytics le permiten definir varias rutas de unión entre un conjunto de datos de búsqueda y los datos de evento, lo que permite crear informes flexibles en los escenarios B2C y B2B.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: 774ac76b0a49d8172b31dc97563c13debb0858a7
workflow-type: tm+mt
source-wordcount: '2431'
ht-degree: 13%

---


# Búsquedas compartidas

En Customer Journey Analytics, un conjunto de datos de búsqueda enriquece los datos de evento con contexto adicional. Por ejemplo, un conjunto de datos del catálogo de productos que agrega nombres de productos, categorías y precios a los eventos de compra. O un conjunto de datos de metadatos de campaña que agregue detalles de campaña a los eventos de marketing.

Las búsquedas permiten informar sobre datos de evento mediante atributos que no están almacenados en los propios eventos.
Tradicionalmente, un conjunto de datos de búsqueda se une a los eventos a través de una sola ruta fija. Un campo clave del conjunto de datos de evento coincide con un campo clave del conjunto de datos de búsqueda. Esta búsqueda funciona cuando solo hay una manera de relacionar los dos conjuntos de datos, pero este vínculo simple se desglosa en escenarios reales comunes:

* Catálogo de productos unido a eventos en el SKU o el ID de producto, según el origen de evento.
* Una búsqueda de atributos de usuario unida a eventos en diferentes áreas de nombres de identidad, según el canal (correo electrónico para eventos web, ID de fidelidad para eventos en tienda).
* Un conjunto de datos de perfil unido a eventos directamente (por persona) e indirectamente (por cuenta, para fines de informes B2B)

Las búsquedas compartidas resuelven las uniones de rutas fijas limitadas al permitirle definir varias rutas de unión entre un conjunto de datos de búsqueda y los eventos que enriquecen los datos de búsqueda. Cada ruta describe una forma de hacer coincidir las filas de búsqueda con las filas de eventos. Las dimensiones o métricas, creadas a partir de la búsqueda, pueden elegir la ruta que se va a utilizar. El mismo conjunto de datos de búsqueda ahora puede alimentar varios escenarios de creación de informes desde una sola configuración.

Las búsquedas compartidas también son la base de [creación de informes de población total](./tpr.md), que usa búsquedas compartidas para conectar conjuntos de datos de perfil a eventos.

## Conceptos

Las secciones siguientes describen conceptos clave de las búsquedas compartidas.

### Unir rutas

Una ruta de unión es una ruta única para hacer coincidir filas entre un conjunto de datos de búsqueda y los eventos. Cada ruta de unión tiene:

* Un **nombre de ruta**. Una etiqueta legible en lenguaje natural que usted elija, utilizada para identificar la ruta en la interfaz de usuario al crear dimensiones y métricas.
* Un campo de clave **key** en el lado de eventos. Este campo se utiliza para hacer coincidir el evento con los datos de búsqueda.
* Un **campo de clave coincidente** en el lado de búsqueda.  Este campo es con el que coincide la clave.
* Un **espacio de nombres** opcional. El área de nombres es necesaria cuando el campo de clave es un mapa de identidad.

Un único conjunto de datos de búsqueda puede tener una o más rutas de unión. Las dimensiones y métricas creadas en un campo de esa búsqueda pueden especificar qué ruta utilizar. Si no se especifica una ruta, se utiliza la ruta predeterminada para un conjunto de datos.

### Coincidencia por contenedor

Para los conjuntos de datos de perfil (utilizados con los informes de población total), las búsquedas compartidas admiten una configuración de coincidencia por contenedor que configura automáticamente la unión en función del tipo de contenedor:

* **Contenedor de coincidencia por persona**. La búsqueda se une a los eventos a través de la identidad de la persona, utilizando el mapa de identidad del conjunto de datos de evento como clave.
* **Coincidencia por contenedor de cuenta** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. La búsqueda se une a través de la identidad de la cuenta.
* **Coincidencia por contenedor de cuenta global** ([!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} con cuentas globales habilitadas). La búsqueda se une a través de la identidad de cuenta global.

Coincidencia por contenedor administra los casos comunes sin que sea necesario configurar los campos clave manualmente. La principal ventaja de la coincidencia por contenedor es que las deduplicaciones se gestionan automáticamente. El contenedor almacena identidades únicas (para persona, cuenta o cuenta global).

Más allá de los informes de población total, también puede utilizar la coincidencia por contenedor para definir rutas de unión a otros conjuntos de datos de búsqueda.

### Coincidencia por campo

También puede hacer coincidir conjuntos de datos de perfil por campo. Esa coincidencia genera búsquedas directas para cada evento en los datos de evento, en función de una identidad específica. Cuando se utiliza la coincidencia por campo, los resultados pueden contener datos duplicados, lo que puede llevar a resultados confusos, especialmente cuando se utiliza con métricas. Consulte [Ejemplo](#example) para obtener una explicación más detallada.

### Mapas de identidad como campos clave

Cuando el campo clave a ambos lados de la unión es un mapa de identidad (un campo que contiene varias identidades con área de nombres), se necesita una configuración adicional:

* **Clave principal** o **área de nombres**. Puede hacer coincidir utilizando la clave principal del mapa de identidad o seleccionando un área de nombres específica. La selección de un área de nombres es la opción más común; la clave principal no se rellena en todos los orígenes de datos de perfil.
* **Área de nombres secundaria**. En los casos en los que el área de nombres principal no se rellena en una fila determinada (lo que es común con los conjuntos de datos enlazados), puede especificar un área de nombres de reserva. La unión utiliza el área de nombres principal cuando se rellena y, en caso contrario, vuelve a la secundaria.
* **Coherencia entre rutas**. Cuando se utiliza el mismo mapa de identidad como campo de clave en varias búsquedas compartidas en una conexión, las selecciones del área de nombres deben ser coherentes en todas esas búsquedas.

### Búsqueda en rutas de búsqueda

Un conjunto de datos de búsqueda se puede unir a otro conjunto de datos de búsqueda. Esta búsqueda en la búsqueda crea una cadena de búsqueda de dos niveles: evento → búsqueda A → búsqueda B.

Cada nivel de la cadena de búsqueda puede tener sus propias rutas de unión. Las dimensiones o métricas creadas en los campos de la búsqueda de segundo nivel atraviesan la cadena utilizando la ruta configurada en cada paso. No se admiten cadenas de búsqueda de más de dos niveles.


## Uso

Utilice búsquedas compartidas cuando se cumpla alguna de las siguientes condiciones:

* Debe unir el mismo conjunto de datos de búsqueda a los eventos de más de una manera.
* Puede trabajar con datos de identidad B2C (de empresa a consumidor) donde los distintos eventos utilizan diferentes áreas de nombres de identidad.
* Puede configurar una conexión B2B (empresa a empresa) que necesite relacionar eventos con personas y cuentas.
* Se agrega un conjunto de datos de perfil a una conexión para la creación de informes de población total.

Si el conjunto de datos de búsqueda tiene una sola clave de combinación obvia y solo necesita una forma de relacionar los datos del conjunto de datos de búsqueda con los eventos, puede configurar una sola ruta. Las búsquedas compartidas también admiten ese caso simple.

## Ejemplo

El ejemplo completo siguiente describe las búsquedas compartidas en general.

Imagine que tiene, junto a un conjunto de datos de evento, el siguiente perfil, perfil de oportunidad, cuenta y conjuntos de datos de búsqueda de oportunidad configurados como parte de la conexión de Customer Journey Analytics.

Los datos de ejemplo para cada conjunto de datos:

>[!BEGINTABS]

>[!TAB Eventos]

| Marca de tiempo | ID de la persona | ID de cuenta | ID de cuenta global | ID de oportunidad | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | A-123 | A-123 | O-432 | Página principal |
| 2025-02-28 05:32:13 | P-ABC | A-123 | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | P-ABC | A-123 | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | A-123 | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | O-876 | Página principal |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | O-876 | Gadget |

>[!TAB Perfil]

| ID de la persona | Nombre | ID de cuenta | ID de cuenta global |
|---|---|---|---|
| P-ABC | John | A-123 | A-123 |
| P-EFG | Kate | A-123 | A-123 |
| P-HIJ | Dave | A-789 | A-789 |
| P-LMN | Vijay | A-456 | A-789 |

>[!TAB Cuenta]

| ID de cuenta | Nombre | ID de cuenta global | País | Valor de duración |
|---|---|---|---|---:|
| A-123 | Acme | A-123 | EE. UU. | 122 MILLONES DE USD |
| A-456 | BigCo | A-789 | JP | 23 MILLONES DE DÓLARES |
| A-789 | Gigante | A-789 | RU | $48 MILLONES |

>[!TAB Perfil de oportunidad]

| ID de la persona | ID de oportunidad | ID de cuenta global |
|---|---|---|
| P-ABC | O-432 | A-123 |
| P-ABC | O-543 | A-123 |
| P-EFG | O-543 | A-123 |
| P-LMN | O-876 | A-789 |

>[!TAB Oportunidad]

| ID de oportunidad | Nombre | ID de cuenta | ID de cuenta global | Estado | Valor |
|---|---|---|---|---|---:|
| O-432 | Acme Express | A-123 | A-123 | Abrir | $2 MILLONES |
| O-543 | Acme CC | A-123 | A-123 | Cerrado | $1 MILLÓN |
| O-765 | Acme DX | A-123 | A-123 | Abrir | $8 MILLONES |
| O-876 | BigCo CC | A-456 | A-789 | Abrir | $7 MILLONES |
| O-987 | BigCo DX | A-456 | A-789 | Abrir | $16 MILLONES |
| O-888 | DX gigante | A-789 | A-789 | Abrir | $13 MILLONES |

>[!ENDTABS]

Cuando se crea esta conexión, [los contenedores](/help/getting-started/cja-b2b-concepts-features.md#containers) se crean automáticamente como parte de la funcionalidad principal de Customer Journey Analytics.

El diagrama siguiente muestra las relaciones de entidad para esta conexión.

![Diagrama de relación de entidad que muestra conexiones de búsqueda compartidas](./assets/erd.png){zoomable="yes"}

Puede utilizar estos contenedores como parte del control de rutas para informar sobre el valor de oportunidad de cada cuenta. En función del contenedor seleccionado, puede obtener diferentes resultados.

| Nombre de la cuenta | Valor de oportunidad <br/>(contenedor de oportunidad) | Valor de oportunidad <br/>(contenedor de cuenta de subproductos lácteos) | Valor de oportunidad <br/>(contenedor de persona) |
|---|---:|---:|---:|
| Acme | $3 MILLONES | $11 MILLONES | $4 MILLONES |
| BigCo | $7 MILLONES | 23 MILLONES DE DÓLARES | $7 MILLONES |


### Coincidencia por contenedor de oportunidad

Para hacer coincidir las oportunidades con las cuentas, utilice el contenedor de oportunidades como ruta desde el evento a los datos de búsqueda de oportunidades, lo que resulta en 3 millones de dólares para Acme y 7 millones de dólares para BigCo.

![ERD muestra coincidencia por ruta de contenedor de oportunidad](./assets/erd-oo.png){zoomable="yes"}

>[!BEGINTABS]

>[!TAB Datos de evento]

| Marca de tiempo | ID de la persona | ID de cuenta | ID de cuenta global | ID de oportunidad ![Link](/help/assets/icons/Link.svg) | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | A-123 | A-123 | **O-432** | Página principal |
| 2025-02-28 05:32:13 | P-ABC | A-123 | A-123 | **O-432** | Widget |
| 2025-03-13 08:21:47 | P-ABC | A-123 | A-123 | **O-432** | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | A-123 | A-123 | **O-543** | Gadget |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | **O-876** | Página principal |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | **O-876** | Gadget |

>[!TAB Oportunidad]

| ID de oportunidad ![Link](/help/assets/icons/Link.svg) | Nombre | ID de cuenta | ID de cuenta global | Estado | Valor |
|---|---|---|---|---|---:|
| **O-432** | Acme Express | A-123 | A-123 | Abrir | **$2M** |
| **O-543** | Acme CC | A-123 | A-123 | Cerrado | **$1M** |
| O-765 | Acme DX | A-123 | A-123 | Abrir | $8 MILLONES |
| **O-876** | BigCo CC | A-456 | A-789 | Abrir | **$7M** |
| O-987 | BigCo DX | A-456 | A-789 | Abrir | $16 MILLONES |
| O-888 | DX gigante | A-789 | A-789 | Abrir | $13 MILLONES |

>[!ENDTABS]


### Coincidencia por contenedor de cuenta subsidiaria

Para hacer coincidir las oportunidades con las cuentas, utilice el contenedor de cuenta subsidiaria como la ruta desde los datos de búsqueda de evento a oportunidad, lo que resulta en 11 millones de dólares para Acme y 23 millones de dólares para BigCo.

![ERD que muestra coincidencia por ruta de contenedor de cuenta subsidiaria](./assets/erd-sao.png){zoomable="yes"}

>[!BEGINTABS]

>[!TAB Eventos]

| Marca de tiempo | ID de la persona | ID de cuenta ![Link](/help/assets/icons/Link.svg) | ID de cuenta global | ID de oportunidad | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | **A-123** | A-123 | O-432 | Página principal |
| 2025-02-28 05:32:13 | P-ABC | **A-123** | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | P-ABC | **A-123** | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | **A-123** | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | O-876 | Página principal |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | O-876 | Gadget |

>[!TAB Oportunidad]

| ID de oportunidad | Nombre | ID de cuenta ![Link](/help/assets/icons/Link.svg) | ID de cuenta global | Estado | Valor |
|---|---|---|---|---|---:|
| O-432 | Acme Express | **A-123** | A-123 | Abrir | **$2M** |
| O-543 | Acme CC | **A-123** | A-123 | Cerrado | **$1M** |
| O-765 | Acme DX | **A-123** | A-123 | Abrir | **$8M** |
| O-876 | BigCo CC | **A-456** | A-789 | Abrir | **$7M** |
| O-987 | BigCo DX | **A-456** | A-789 | Abrir | **$16M** |
| O-888 | DX gigante | A-789 | A-789 | Abrir | $13 MILLONES |


>[!ENDTABS]


### Contenedor Coincidir por persona

![ERD que muestra coincidencia por ruta de contenedor de persona](./assets/erd-popo.png){zoomable="yes"}

Para hacer coincidir oportunidades con cuentas, utilice el contenedor de persona como ruta al perfil de oportunidad y a los datos de búsqueda, lo que da como resultado 4 millones de dólares para Acme y 7 millones de dólares para BigCo.


>[!BEGINTABS]

>[!TAB Eventos]

| Marca de tiempo | ID de persona ![Link](/help/assets/icons/Link.svg) | ID de cuenta | ID de cuenta global | ID de oportunidad | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | **P-ABC** | A-123 | A-123 | O-432 | Página principal |
| 2025-02-28 05:32:13 | **P-ABC** | A-123 | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | **P-ABC** | A-123 | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | **P-EFG** | A-123 | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | **P-LMN** | A-456 | A-789 | O-876 | Página principal |
| 2025-04-01 05:32:13 | **P-LMN** | A-456 | A-789 | O-876 | Gadget |

>[!TAB Persona/Oportunidad]

| ID de persona ![Link](/help/assets/icons/Link.svg) | ID de oportunidad ![Link](/help/assets/icons/Link.svg) | ID de cuenta global |
|---|---|---|
| **P-ABC** | **O-432** | A-123 |
| **P-ABC** | **O-543** | A-123 |
| **P-EFG** | **O-543** | A-123 |
| **P-LMN** | **O-876** | A-789 |

>[!TAB Búsqueda de oportunidades]

| ID de oportunidad ![Link](/help/assets/icons/Link.svg) | Nombre | ID de cuenta | ID de cuenta global | Estado | Valor |
|---|---|---|---|---|---:|
| **O-432** | Acme Express | A-123 | A-123 | Abrir | **$2M** |
| **O-543** (2x) | Acme CC | A-123 | A-123 | Cerrado | $1M x 2 = **$2M** |
| O-765 | Acme DX | A-123 | A-123 | Abrir | $8 MILLONES |
| **O-876** | BigCo CC | A-456 | A-789 | Abrir | **$7M** |
| O-987 | BigCo DX | A-456 | A-789 | Abrir | $16 MILLONES |
| O-888 | DX gigante | A-789 | A-789 | Abrir | $13 MILLONES |

>[!ENDTABS]


### Otras coincidencias por contenedores

En el ejemplo hay más rutas de unión posibles. Por ejemplo, a través del contenedor de cuenta global o del contenedor de grupo de compra. Cada una de las rutas de unión realiza una búsqueda a través de un contenedor de coincidencia por.

### Coincidencia por campo

En lugar de buscar coincidencias por contenedor, también puede optar por buscar coincidencias por campo. A continuación, debe hacer coincidir directamente los ID de oportunidad.

![ERD muestra coincidencia por campo](./assets/erd-field.png)

>[!BEGINTABS]

>[!TAB Eventos]

| Marca de tiempo | ID de la persona | ID de cuenta | ID de cuenta global | ID de oportunidad ![Link](/help/assets/icons/Link.svg) | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | **A-123** | A-123 | **O-432** | Página principal |
| 2025-02-28 05:32:13 | P-ABC | **A-123** | A-123 | **O-432** | Widget |
| 2025-03-13 08:21:47 | P-ABC | **A-123** | A-123 | **O-432** | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | **A-123** | A-123 | **O-543** | Gadget |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | **O-876** | Página principal |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | **O-876** | Gadget |

>[!TAB Oportunidad]

| ID de oportunidad ![Link](/help/assets/icons/Link.svg) | Nombre | ID de cuenta | ID de cuenta global | Estado | Valor |
|---|---|---|---|---|---:|
| **O-432** (3x) | Acme Express | A-123 | A-123 | Abrir | 2 millones de dólares x 3 = **6 millones de dólares** |
| **O-543** | Acme CC | A-123 | A-123 | Cerrado | **$1M** |
| O-765 | Acme DX | A-123 | A-123 | Abrir | $8 MILLONES |
| **O-876** (2x) | BigCo CC | A-456 | A-789 | Abrir | 7 millones de dólares x 2 = **14 millones de dólares** |
| O-987 | BigCo DX | A-456 | A-789 | Abrir | $16 MILLONES |
| O-888 | DX gigante | A-789 | A-789 | Abrir | $13 MILLONES |

>[!ENDTABS]

### Total de informes de población

![ERD que muestra el total de uniones de informes de población](./assets/erd-tpr.png){zoomable="yes"}

[Informes de población total](tpr.md) usan búsquedas compartidas pero no informa sobre eventos. En el ejemplo, solo puede generar informes sobre las métricas del valor de oportunidad de la cuenta mediante la cuenta o el contenedor de cuenta global, ya que estos contenedores son las únicas combinaciones posibles de los datos de búsqueda de oportunidad.

>[!BEGINTABS]

>[!TAB Perfil]

| ID de la persona | Nombre | ID de cuenta ![Link](/help/assets/icons/Link.svg) | ID de cuenta global |
|---|---|---|---|
| P-ABC | John | **A-123** | A-123 |
| P-EFG | Kate | **A-123** | A-123 |
| P-HIJ | Dave | **A-789** | A-789 |
| P-LMN | Vijay | **A-456** | A-789 |


>[!TAB Oportunidad]

| ID de oportunidad | Nombre | ID de cuenta ![Link](/help/assets/icons/Link.svg) | ID de cuenta global | Estado | Valor |
|---|---|---|---|---|---:|
| O-432 | Acme Express | **A-123** | A-123 | Abrir | **$2M** |
| O-543 | Acme CC | **A-123** | A-123 | Cerrado | **$1M** |
| O-765 | Acme DX | **A-123** | A-123 | Abrir | **$8M** |
| O-876 | BigCo CC | **A-456** | A-789 | Abrir | **$7M** |
| O-987 | BigCo DX | **A-456** | A-789 | Abrir | **$16M** |
| O-888 | DX gigante | **A-789** | A-789 | Abrir | **$13M** |

* 3 oportunidades para la cuenta A-123 (Acme) con un total de **$13M**.
* 2 oportunidades para la cuenta A-456 (BigCo) con un total de **$23M**.
* 1 oportunidad para la cuenta A-789 (Gigante) con un total de **$13M**.

>[!ENDTABS]
