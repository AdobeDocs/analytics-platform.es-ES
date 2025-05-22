---
title: Transición del conector de origen de Analytics al SDK web para Customer Journey Analytics
description: Obtenga información sobre cómo realizar la transición al SDK web desde el conector de origen de Analytics al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# Transición del conector de origen de Analytics al SDK web para Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Disponibilidad del conector de origen de Analytics"
>abstract="El conector de origen de Analytics permite obtener fácilmente valor con Customer Journey Analytics, pero requiere que se pague tanto por Adobe Analytics como por Customer Journey Analytics. Esta guía puede ayudarle a avanzar hacia una implementación independiente del SDK web."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Eliminar el conector de origen de Analytics existente"
>abstract="El conector de origen de Analytics que tiene actualmente no es compatible con el esquema personalizado de su organización. Sin embargo, los datos siguen estando en el grupo de informes de Analytics. Este paso elimina el conector de origen actual de Analytics para que pueda volverlo a crear con el esquema correcto en un paso posterior.<br><br>Antes de eliminar el conector de origen, es posible que desee coordinarse con otros usuarios de su organización para asegurarse de que la eliminación del conector de origen no afecte a la creación de informes dentro de su organización. Esta coordinación puede tardar varias semanas en completarse."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Existen desventajas inherentes al uso del conector de origen de Analytics como única implementación para Customer Journey Analytics.

Si su organización ya ha actualizado a Customer Journey Analytics utilizando únicamente la implementación del conector de origen de Analytics, Adobe recomienda realizar la transición a una nueva implementación de Web SDK para la recopilación de datos continua y utilizar el conector de origen de Analytics solo para los datos históricos.

## Ventajas y desventajas de utilizar el conector de origen de Analytics exclusivamente

Para obtener información sobre las ventajas y desventajas de utilizar el conector de origen de Analytics, consulte [Uso del conector de origen de Analytics exclusivamente para actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Transición de conector de origen de Analytics al SDK web

A continuación se muestra un proceso de alto nivel para realizar la transición de utilizar exclusivamente el conector de origen de Analytics a una implementación compuesta tanto por el conector de origen de Analytics como por una implementación del SDK web:

1. Cree una implementación del SDK web, tal como se describe en [Pasos de actualización recomendados detallados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) en el artículo [Actualización de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Una vez configurada la implementación del SDK web, continúe con los siguientes pasos.

1. [Cree un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Asigne cada dimensión de Adobe Analytics desde el conector de origen de Analytics a la dimensión del esquema del SDK web.

   1. 
      <!-- how do you get here -->

   1. En la sección **[!UICONTROL Asignar campos estándar]**, seleccione la pestaña **[!UICONTROL Personalizado]**.

   1. Seleccione **[!UICONTROL Añadir nueva asignación]**.

      ![asignar campos del esquema](assets/schema-mapping.png)

   1. En el **[!UICONTROL campo de origen]**, seleccione un campo de Adobe Analytics del grupo de campos Plantilla de Adobe Analytics ExperienceEvent. A continuación, en el **[!UICONTROL campo de destino]**, seleccione el campo XDM al que desea asignarlo.

   1. Repita este proceso para cada campo del grupo de campos Plantilla de Adobe Analytics ExperienceEvent que esté utilizando para recopilar datos en Adobe Analytics.

1. Añada el conjunto de datos creado automáticamente con el conector de origen original de Analytics a la conexión de Customer Journey Analytics.

   Para obtener más información, consulte [Añadir el conjunto de datos desde el conector de origen actual de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condicional) Si utiliza conjuntos de datos de consulta, deberá crear el conjunto de datos de consulta y añadirlo a la conexión. Para obtener más información, consulte [Creación de conjuntos de datos de consulta para clasificar datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Elimine el conector de origen de Analytics existente.<!-- need to add steps somewhere about how to do this -->

1. [Cree el conector de origen de Analytics y asigne campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

{{upgrade-final-step}}
