---
title: Diseñe su esquema para utilizarlo con Customer Journey Analytics
description: Aprenda a diseñar un esquema XDM que desbloquee la flexibilidad de Customer Journey Analytics, a la vez que admita una ruta de migración práctica desde Adobe Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 5808de9b39d3c8fa5632755958ddb887c081b203
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 9%

---

# Diseñe su esquema para utilizarlo con Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Diseñar un esquema"
>abstract="Comente en su organización los requisitos de la recopilación de datos y determine cómo desea crear un esquema para utilizarlo en Adobe Experience Platform. Este paso surge porque desea utilizar el proceso recomendado de usar un esquema adaptado a su organización. Realizar este paso correctamente es fundamental, ya que un esquema con el que todos los equipos de la organización estén de acuerdo facilita considerablemente la ingesta de datos.<br><br>El tiempo estimado para reunir a todas las partes relevantes de su organización para alinearse en un esquema unificado es de 1 a 2 meses. Este lapso de tiempo depende en gran medida del número de equipos que haya que coordinar y del número de dimensiones + métricas que haya que alinear."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe recomienda crear un esquema personalizado [Experience Data Model](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home) (XDM) para Customer Journey Analytics al implementar [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/es/docs/experience-platform/collection/home). La creación de este esquema se suele realizar antes de que se toquen los cambios de implementación o el código. Un esquema personalizado permite diseñar un contrato de datos conciso y específico de la organización sin heredar las restricciones de Adobe Analytics. Consulte [Elija su esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) para obtener más información sobre los tipos de esquemas disponibles para su organización.

Los esquemas están pensados para ser versiones refinadas de cómo desea que se estructuren los datos a largo plazo. Los cambios en los esquemas son costosos porque afectan a la recopilación de datos, la validación y los servicios descendentes. Puede añadir a los esquemas con el tiempo, según lo permitan los requisitos empresariales; sin embargo, los campos de esquema no se pueden eliminar una vez que los datos empiecen a fluir a ellos.

## Comparar esquemas con vistas de datos

La canalización de datos para Customer Journey Analytics contiene áreas independientes para la recopilación y la interpretación de datos. Al actualizar desde Adobe Analytics, un error común es intentar recrear props y eVars con sus comportamientos en XDM. En su lugar, utilice Web SDK para recopilar los datos y utilice [Vistas de datos](/help/data-views/data-views.md) para determinar cómo se interpretan esos datos en los informes.

| Capa | Objetivo principal | Flexibilidad | Qué pertenece | Lo que no pertenece |
|---|---|---|---|---|
| **esquema XDM** | Definir la estructura duradera y el significado de los datos recopilados | Puntos de datos rígidos, considerados inmutables | Forma de evento y entidad, significado de campo, relaciones, valores permitidos, reutilización en varios canales | &quot;ranuras&quot; numeradas (eVar1/prop1), lógica de atribución/persistencia, soluciones específicas para la creación de informes |
| **Vistas de datos** | Definición del comportamiento de los datos recopilados en el análisis | Flexible; se pueden modificar libremente y pueden reinterpretar los datos de forma retroactiva | Configuración de componentes, comportamiento de atribución y persistencia, campos derivados, métricas filtradas, métricas calculadas | Significado fundamental de los campos; ese significado debe ser estable en el esquema |

## Comparar esquemas con la recopilación de datos de Adobe Analytics

El modelo de datos de Experience que utiliza Customer Journey Analytics ofrece una flexibilidad considerablemente mayor que la mayoría de las demás soluciones de Analytics (incluido Adobe Analytics). El establecimiento de un esquema sólido es la oportunidad que tiene su organización para evitar avanzar restricciones que existen en otros productos de Analytics.

| Hábito Adobe Analytics común | Mejor enfoque en XDM + Customer Journey Analytics |
|---|---|
| Diseño en torno a ranuras numeradas (`eVar1`–,`eVar250` `prop1` –`prop75`) | Crear campos con significado estable (por ejemplo, `search.term`, `content.category`, `user.membershipTier`) y reutilizarlos de forma coherente |
| Codificación de persistencia/Asignación/caducidad en el modelo de datos | Capturar hechos duraderos en el esquema; aplicar el comportamiento de atribución y persistencia en el nivel de vista de datos |
| Duplicación del mismo valor en varias variables para lograr comportamientos de informes | Almacene el valor una vez y cree varios componentes (dimensiones/métricas) a partir de él en vistas de datos |
| Creación de un &quot;campo de métrica&quot; único para cada recuento que desee | Capture los hechos correctos una vez (a menudo como enumeraciones, booleanos, cadenas) y luego defina las métricas como recuentos filtrados en las vistas de datos |
| Diseño de variables para la creación de informes &quot;previa a la resolución&quot; | Diseñe sus esquema para capturar hechos y usar vistas de datos para resolver sistema de informes semántica |

## Establezca un esquema con atributos comunes

Un esquema unificado en todos los canales es posible cuando se estandariza un conjunto de atributos reutilizables que aparecen en muchos eventos. Algunos ejemplos son:

* **Contexto de la experiencia:** nombre del sitio/aplicación, entorno, configuración regional, canal, marca
* **Contexto de Recorrido:** identificadores de campaña, contexto de referencia, identificadores de experimento
* **Estado del usuario:** estado de inicio de sesión, nivel de abono cuenta
* **Detalles de interacción:** nombre/tipo de interacción, área geográfica de IU, etiqueta de elemento, categoría de error

La clave es estandarizar lo que representa el campo, independientemente de canal. Evite modelar el mismo concepto de manera diferente en todos los canales a menos que realmente representen conceptos diferentes. Por ejemplo, sería prudente evitar tener campos de esquema separados para los ID de campaña web y los ID de campaña móvil. La separación de campos de esquema hace más difícil establecer datos de retorno de la inversión en publicidad canal cruzada. Si se requiere una diferenciación en sistema de informes, puede segmento canal o concatenando varios campos para proporcionar esa distinción. El mismo campo esquema se puede utilizar en cualquier número de dimensiones o métricas.

Una manera práctica de admitir varios canales mientras se mantiene una única estrategia de esquema es usar un patrón de **core + extensions**:

* **Principal:** campos que se aplican en términos generales en todos los canales y equipos
* **Extensiones:** grupos de campos específicos de canal o dominio que se aplican solo donde es necesario (interacción web, comercio, ciclo de vida móvil, detalles específicos del lado del servidor)

Este patrón admite una sola estrategia de esquema organizativo sin forzar a los equipos a rellenar campos innecesarios.

## Preferir grupos de campos estándar donde quepan

Adobe recomienda utilizar grupos de campos estandarizados donde coincidan con sus necesidades y ampliar con campos personalizados los conceptos específicos de la organización.

Los grupos de campos estándar suelen ayudarle a lo siguiente:

* Reduzca la ambigüedad utilizando una semántica de campo conocida
* Alinear entre equipos más fácilmente
* Compatibilidad con interoperabilidad entre aplicaciones de Adobe Experience Platform

Los campos personalizados son adecuados cuando:

* Su organización tiene conceptos que no se asignan correctamente a los campos estándar
* Necesita atributos adicionales para cumplir con los requisitos de creación de informes, gobernanza o activación
* Desea representar una taxonomía específica de la empresa (por ejemplo, categorías de contenido interno)

## Determinar cómo se cuentan las métricas

En Adobe Analytics, muchos equipos tratan la variable `events` como el único medio para rastrear métricas. En Customer Journey Analytics, las métricas se pueden rastrear de varias formas en función de lo que necesite contar y de cómo desee interpretarlas.

Al diseñar un esquema, manténgase al tanto de los hechos. Por ejemplo, `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Defina las métricas en la vista de datos como recuentos y recuentos filtrados sobre esos hechos. Por ejemplo:

* `checkout.step` (enumeración/cadena) puede activar:
   * &quot;Cierre de compra: Paso de envío alcanzado&quot; (recuento donde `checkout.step == "shipping"`)
   * &quot;Cierre de compra: paso de pago alcanzado&quot;
* `error.type` (enumeración/cadena) puede activar:
   * &quot;Errores de validación&quot;
   * &quot;Errores de autorización&quot;
* `user.isLoggedIn` (booleano) puede potenciar:
   * &quot;Sesiones autenticadas&quot;
   * &quot;Conversiones autenticadas&quot;

>[!TIP]
>
>Al decidir si algo debe ser un campo dedicado en el esquema o un campo derivado más adelante, prefiera capturar el hecho duradero en el esquema si es ampliamente útil y estable. Puede utilizar campos derivados para corregir o modificar la forma de los datos después de la recopilación.

## Mantener la paridad con Adobe Analytics durante la transición sin equipaje de esquema

Algunas organizaciones deben continuar con los informes de Adobe Analytics mientras actualizan a Customer Journey Analytics. Puede mantener la paridad sin introducir artefactos específicos de Analytics en el diseño de esquema a largo plazo mediante el siguiente método:

1. **Utilice rutas de campo XDM que Adobe Analytics reconozca y asigne automáticamente:** Cuando envíe campos XDM reconocidos a Adobe Analytics a través de Edge Network, se [asignarán automáticamente](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/xdm-var-mapping) sin necesidad de configuración adicional.
1. **Use campos XDM personalizados para conceptos específicos de la organización:** Todos los campos XDM que no se asignen automáticamente a una variable de Analytics se reenvían como [Variables de datos de contexto](https://experienceleague.adobe.com/es/docs/analytics/implementation/vars/page-vars/contextdata) en Adobe Analytics.
1. **Use reglas de procesamiento de Adobe Analytics para asignar esas variables de datos de contexto a props/eVars:** [Las reglas de procesamiento](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) en última instancia le permiten asignar cualquier campo XDM personalizado a cualquier eVar o prop. Este concepto admite la creación de informes de paridad en Adobe Analytics, a la vez que mantiene el esquema limpio y centrado en Customer Journey Analytics.

## Identificación de partes interesadas y definición de propiedad

El diseño del esquema se realiza correctamente cuando se acuerda y mantiene el significado del campo. Aunque las estructuras organizativas varían, las siguientes funciones suelen participar:

* **Analytics administrador/analista**: define sistema de informes preguntas, valida que los campos representan conceptos significativos y revisa análisis semántica en vistas de datos.
* **Desarrollador/propietario de la implementación**: Garantiza que los campos se puedan recopilar de forma fiable mediante Web SDK y se ajusta a la capa de datos/instrumentación de la aplicación.
* **Arquitecto/ingeniero de datos**: garantiza la coherencia del esquema, su reutilización en todos los dominios y la compatibilidad con los servicios descendentes.
* **responsable de departamento** de privacidad/gobernanza: revisa la minimización de datos, las expectativas de consentimiento y las restricciones de uso de datos.

Defina un propietario claro para esquema cambios. Un esquema estable con control de cambios disciplinado evita la rotura aguas abajo y reduce el retrabajo. Considere la posibilidad de utilizar una flujo de trabajo o herramientas de gobernanza seguimiento para democratizar las solicitudes y administrar el control de los cambios a lo largo del tiempo.

## Consideraciones de privacidad y gobernanza

El diseño del esquema debe reflejar las expectativas de privacidad y gobernanza, según las políticas de privacidad de su organización. Tenga en cuenta los siguientes puntos al crear el esquema:

* Recopile solo lo que necesite para admitir casos de uso definidos.
* Asegúrese de que los requisitos de uso de datos y consentimiento se reflejen en la estrategia de recopilación. Consulte [Usar Web SDK para procesar los datos de consentimiento del cliente](https://experienceleague.adobe.com/es/docs/experience-platform/landing/governance-privacy-security/consent/sdk) para obtener más información.
* Considere cómo se etiquetan y controlan los campos confidenciales dentro de las herramientas de gobernanza de Adobe Experience Platform. Consulte [Adobe Customer Journey Analytics y control de datos](/help/privacy/privacy-overview.md) para obtener más información.

## Pasos siguientes

Una vez que haya establecido y acordado una arquitectura de esquema, puede empezar a crearla en Adobe Experience Platform. Vea [Crear un esquema personalizado para usar con Customer Journey Analytics](cja-upgrade-schema-create.md) para obtener más información.
