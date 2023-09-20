---
description: Configure la ubicación de exportación de la nube a la que se pueden enviar los datos del Customer Journey Analytics
keywords: Analysis Workspace
title: Configuración de ubicaciones de exportación de nube
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 6%

---

# Configuración de ubicaciones de exportación de nube

{{select-package}}

Antes de poder exportar datos de Customer Journey Analytics a un destino de nube, tal como se describe en [Exportación de datos del Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md), debe agregar y configurar la ubicación a la que desea enviar los datos.

Este proceso consiste en añadir y configurar la cuenta (como Amazon S3, Google Cloud Platform, etc.) tal como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md)y, a continuación, agregue y configure la ubicación dentro de esa cuenta (por ejemplo, una carpeta dentro de la cuenta) tal como se describe en este artículo.

Para obtener información sobre cómo administrar ubicaciones existentes, incluida la visualización, edición y eliminación de ubicaciones, consulte [Administrar ubicaciones y cuentas de exportación en la nube](/help/components/exports/manage-export-locations.md).

Para configurar una ubicación de exportación en la nube:

1. Debe agregar una cuenta antes de agregar una ubicación. Si aún no lo ha hecho, agregue una cuenta como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md).
1. En Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].
1. En el [!UICONTROL Exportaciones] , seleccione la [!UICONTROL **Ubicaciones**] pestaña.
1. Seleccionar [!UICONTROL **Añadir ubicación**].

   ![botón añadir ubicación](assets/location-add.png)

   Se muestra el cuadro de diálogo Ubicación.

1. Especifique la siguiente información: |Campo Función | | |---------|----------| | [!UICONTROL **Nombre**] | El nombre de la ubicación.  | | [!UICONTROL **Descripción**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Cuenta de ubicación**] | Seleccione la cuenta de ubicación que creó en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md). |

1. En el [!UICONTROL **Propiedades de ubicación**] , especifique información específica para el tipo de cuenta de su cuenta de ubicación.

   Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde al tipo de cuenta seleccionado en la [!UICONTROL **Cuentas de ubicación**] field.

   +++Amazon S3 Role ARN

   Especifique la siguiente información para configurar una ubicación ARN de la función Amazon S3:

   <!-- still need to update; can't create S3 role ARN account -->

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Cubo**] | El bloque de su cuenta de Amazon S3 al que desea enviar los datos de Adobe Analytics. Asegúrese de que el ARN del usuario proporcionado por el Adobe tiene acceso para cargar archivos en este bloque. |
   | [!UICONTROL **Prefijo**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Especifique la siguiente información para configurar una ubicación de Google Cloud Platform:

   <!-- still need to update; can't create GCP account -->

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Cubo**] | El bloque de su cuenta de GCP al que desea enviar los datos del Customer Journey Analytics. Asegúrese de haber concedido permiso al principal proporcionado por el Adobe para cargar archivos en este bloque. (La entidad de seguridad se proporciona cuando [configuración de la cuenta de Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) Para obtener información sobre la concesión de permisos, consulte [Añadir un principal a una política de nivel de bloque](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) en la documentación de Google Cloud. |
   | [!UICONTROL **Prefijo**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Especifique la siguiente información para configurar una ubicación SAS de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó a la que desea enviar los datos del Customer Journey Analytics. |
   | [!UICONTROL **Prefijo**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique la siguiente información para configurar una ubicación RBAC de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Contenedor**] | El contenedor de la cuenta que especificó a donde desea enviar los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
   | [!UICONTROL **Prefijo**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |
   | [!UICONTROL **Cuenta**] | La cuenta de almacenamiento de Azure. |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Especifique la siguiente información para configurar una ubicación de Snowflake:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **DB**] | La base de datos predeterminada que se utiliza una vez conectada o especifica una cadena vacía. La base de datos especificada debe ser una base de datos existente para la que el rol predeterminado especificado tenga privilegios. <p>Para obtener más información, consulte la [Página Parámetro de conexión del controlador JDBC: Referencia en la documentación del Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Esquema**] | El esquema predeterminado que se va a utilizar para la base de datos especificada una vez conectada, o especifica una cadena vacía. El esquema especificado debe ser un esquema existente para el cual la función predeterminada especificada tenga privilegios. <p>Para obtener más información, consulte la [Página Parámetro de conexión del controlador JDBC: Referencia en la documentación del Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Nombre de la fase**] | Nombre de la ubicación donde se almacenan los archivos de datos en el Snowflake. <p>Para obtener más información, consulte la [Selección de una fase interna para archivos locales en la documentación de Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Ruta de la fase**] | Ruta de acceso a la ubicación donde se almacenan los archivos de datos en el Snowflake. <p>Para obtener más información, consulte la [Selección de una fase interna para archivos locales en la documentación de Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   Especifique la siguiente información para configurar una ubicación de Adobe Experience Platform:

   <!-- still need to update; can't create AEP account -->

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de organización IMS**] | El Adobe proporciona el ID de organización de IMS. Haga clic en el icono Copiar junto a la etiqueta [!UICONTROL **ID de organización IMS**] para copiar el contenido del campo y, a continuación, utilice el ID en su cuenta de Adobe Experience Platform. |
   | [!UICONTROL **Prefijo**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, agregue una barra invertida después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

+++

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).