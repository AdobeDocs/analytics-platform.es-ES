---
description: Configure la ubicación de exportación de la nube a la que se pueden enviar los datos del Customer Journey Analytics
keywords: Analysis Workspace
title: Configuración de ubicaciones de exportación de nube
feature: Components
hide: true
hidefromtoc: true
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
source-git-commit: b0ddfbb4d018e6d563bef639a31f31e09700fbc2
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---

# Configuración de ubicaciones de exportación de nube

Antes de poder exportar informes de Customer Journey Analytics a un destino de nube, tal como se describe en [Exportar informes de Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md), debe agregar y configurar la ubicación a la que desea enviar los datos.

Este proceso consiste en añadir y configurar la cuenta (como Amazon S3, Google Cloud Platform, etc.) tal como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md)y, a continuación, agregue y configure la ubicación dentro de esa cuenta (por ejemplo, una carpeta dentro de la cuenta) tal como se describe en este artículo.

Para obtener información sobre cómo administrar ubicaciones existentes, incluida la visualización, edición y eliminación de ubicaciones, consulte [Administrar ubicaciones y cuentas de exportación en la nube](/help/components/exports/manage-export-locations.md).

## Comience a crear una ubicación de exportación de nube

1. Debe agregar una cuenta antes de agregar una ubicación. Si aún no lo ha hecho, agregue una cuenta como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md).

1. En Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].

1. Seleccione el [!UICONTROL **Ubicaciones**] pestaña, luego seleccione [!UICONTROL **Añadir ubicación**].

   ![botón añadir ubicación](assets/location-add.png)

   o

   Seleccione el [!UICONTROL **Cuentas de ubicación**] , seleccione el icono de 3 puntos en una cuenta existente donde desee añadir una ubicación y, a continuación, seleccione [!UICONTROL **Añadir ubicación**].

   ![Añadir ubicación a una cuenta existente](assets/add-location-existing-account.png)

   Se muestra el cuadro de diálogo Ubicación.

1. Especifique la siguiente información: |Campo Función | | |---------|----------| | [!UICONTROL **Nombre**] | El nombre de la ubicación.  | | [!UICONTROL **Descripción**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Cuenta de ubicación**] | Seleccione la cuenta en la que desea crear la ubicación. Para obtener información sobre cómo crear una cuenta, consulte [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md). |

1. En el [!UICONTROL **Propiedades de ubicación**] , especifique información específica para el tipo de cuenta de su cuenta de ubicación.

   Continúe con la sección siguiente que corresponde al tipo de cuenta seleccionado en la [!UICONTROL **Cuenta de ubicación**] field.

### Zona de aterrizaje de datos de AEP

>[!IMPORTANT]
>
>Al exportar informes de Customer Journey Analytics a la zona de aterrizaje de datos de Adobe Experience Platform, asegúrese de descargar los datos en un plazo de 7 días y, a continuación, elimínelos de la zona de aterrizaje de datos de AEP. Después de 7 días, los datos se eliminan automáticamente de la zona de aterrizaje de datos de AEP.

1. [Comience a crear una ubicación de exportación de nube](#begin-creating-a-cloud-export-location), tal como se ha descrito anteriormente.

1. En el [!UICONTROL **Propiedades de ubicación**] de la sección [!UICONTROL **Añadir ubicación**] , especifique la siguiente información para configurar una ubicación de zona de aterrizaje de datos de Adobe Experience Platform:

   <!-- still need to update; can't create AEP account -->

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Prefijo**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra diagonal después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).

### Amazon S3 Role ARN

1. [Comience a crear una ubicación de exportación de nube](#begin-creating-a-cloud-export-location), tal como se ha descrito anteriormente.

1. En el [!UICONTROL **Propiedades de ubicación**] de la sección [!UICONTROL **Añadir ubicación**] , especifique la siguiente información para configurar una ubicación ARN de la función de Amazon S3:

   <!-- still need to update; can't create S3 role ARN account -->

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Cubo**] | El bloque de su cuenta de Amazon S3 al que desea enviar los datos de Adobe Analytics. Asegúrese de que el ARN del usuario proporcionado por el Adobe tiene acceso para cargar archivos en este bloque. |
   | [!UICONTROL **Prefijo**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra diagonal después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. [Comience a crear una ubicación de exportación de nube](#begin-creating-a-cloud-export-location), tal como se ha descrito anteriormente.

1. En el [!UICONTROL **Propiedades de ubicación**] de la sección [!UICONTROL **Añadir ubicación**] , especifique la siguiente información para configurar una ubicación de Google Cloud Platform:

   <!-- still need to update; can't create GCP account -->

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Cubo**] | El bloque de su cuenta de GCP al que desea enviar los datos del Customer Journey Analytics. Asegúrese de haber concedido permiso al principal proporcionado por el Adobe para cargar archivos en este bloque. (La entidad de seguridad se proporciona cuando [configuración de la cuenta de Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) Para obtener información sobre la concesión de permisos, consulte [Añadir un principal a una política de nivel de bloque](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) en la documentación de Google Cloud. |
   | [!UICONTROL **Prefijo**] | La carpeta dentro del bloque en el que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra diagonal después del nombre para crear la carpeta. Por ejemplo, folder_name/ |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. [Comience a crear una ubicación de exportación de nube](#begin-creating-a-cloud-export-location), tal como se ha descrito anteriormente.

1. En el [!UICONTROL **Propiedades de ubicación**] de la sección [!UICONTROL **Añadir ubicación**] , especifique la siguiente información para configurar una ubicación SAS de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de contenedor**] | El contenedor de la cuenta que especificó a la que desea enviar los datos del Customer Journey Analytics. |
   | [!UICONTROL **Prefijo**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra diagonal después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. [Comience a crear una ubicación de exportación de nube](#begin-creating-a-cloud-export-location), tal como se ha descrito anteriormente.

1. En el [!UICONTROL **Propiedades de ubicación**] de la sección [!UICONTROL **Añadir ubicación**] , especifique la siguiente información para configurar una ubicación RBAC de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Contenedor**] | El contenedor de la cuenta que especificó a donde desea enviar los datos de Adobe Analytics. Asegúrese de conceder permisos para cargar archivos en la aplicación de Azure que creó anteriormente. |
   | [!UICONTROL **Prefijo**] | Carpeta dentro del contenedor en la que desea colocar los datos. Especifique un nombre de carpeta y, a continuación, añada una barra diagonal después del nombre para crear la carpeta. Por ejemplo, `folder_name/` |
   | [!UICONTROL **Cuenta**] | La cuenta de almacenamiento de Azure. |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. [Comience a crear una ubicación de exportación de nube](#begin-creating-a-cloud-export-location), tal como se ha descrito anteriormente.

1. En el [!UICONTROL **Propiedades de ubicación**] de la sección [!UICONTROL **Añadir ubicación**] , especifique la siguiente información para configurar una ubicación de Snowflake:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **DB**] | La base de datos especificada debe ser una base de datos existente. La función que ha creado debe tener privilegios para acceder a esta base de datos.<p>Es la base de datos asociada al nombre de la etapa.</p><p>Puede otorgar estos privilegios de rol a la base de datos en Snowflake mediante el siguiente comando: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Para obtener más información, consulte la [Página Comandos de base de datos, esquema y uso compartido en la documentación del Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Esquema**] | El esquema especificado debe ser un esquema existente. La función que ha creado debe tener privilegios para acceder a este esquema.<p>Este es el esquema asociado al nombre de la etapa.<p>Puede otorgar al esquema del Snowflake la función que ha creado privilegios mediante el siguiente comando: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Para obtener más información, consulte la [Página Comandos de base de datos, esquema y uso compartido en la documentación del Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Nombre de la fase**] | Nombre de la fase interna en la que se almacenan los archivos de datos en Snowflake.<p>Asegúrese de que la función especificada en la cuenta tiene acceso de lectura y escritura a este nombre de fase. (Como está concediendo acceso de lectura y escritura, se recomienda utilizar una fase que solo se utilice en Adobe).<p>Puede conceder acceso de lectura y escritura al nombre de la fase en Snowflake mediante el siguiente comando: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Para obtener información sobre la concesión de privilegios a un rol, consulte [Conceder privilegios en la documentación de Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Para obtener más información sobre el nombre de la fase, consulte la [Selección de una fase interna para archivos locales en la documentación de Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Ruta de la fase**] | Ruta de acceso a la ubicación donde se almacenan los archivos de datos en el Snowflake. <p>Para obtener más información, consulte la [Selección de una fase interna para archivos locales en la documentación de Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**].

1. Ahora puede exportar datos de Analysis Workspace a la cuenta y la ubicación configuradas. Para obtener información sobre cómo exportar datos a la nube, consulte [Exportación de datos del proyecto a la nube](/help/analysis-workspace/export/export-cloud.md).
