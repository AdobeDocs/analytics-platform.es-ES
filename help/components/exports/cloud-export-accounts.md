---
description: Configuración de la cuenta de exportación de Cloud donde se pueden enviar los datos del Customer Journey Analytics
keywords: Analysis Workspace
title: Configuración de cuentas de exportación en la nube
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# Configuración de cuentas de exportación en la nube

{{select-package}}

Antes de poder exportar datos de Customer Journey Analytics a un destino de nube, tal como se describe en [Exportación de datos del Customer Journey Analytics a la nube](/help/analysis-workspace/export/export-cloud.md), debe agregar y configurar la ubicación a la que desea enviar los datos.

Este proceso consiste en agregar y configurar la cuenta (como Amazon S3, Google Cloud Platform, etc.) tal como se describe en este artículo y, a continuación, agregar y configurar la ubicación dentro de esa cuenta (como una carpeta dentro de la cuenta) tal como se describe en [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md).

Para obtener información sobre cómo administrar cuentas existentes, como ver, editar y eliminar cuentas, consulte [Administrar ubicaciones y cuentas de exportación en la nube](/help/components/exports/manage-export-locations.md).

Debe configurar Customer Journey Analytics con la información necesaria para acceder a su cuenta de destino en la nube.

Para configurar una cuenta de exportación de en la nube:

1. En Customer Journey Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Exportaciones**].
1. En el [!UICONTROL Exportaciones] , seleccione la [!UICONTROL **Cuentas de ubicación**] pestaña.
1. Seleccionar [!UICONTROL **Añadir cuenta**].

   ![Añadir cuenta](assets/account-add.png)

   Se muestra el cuadro de diálogo Agregar cuenta.
1. Especifique la siguiente información: |Campo Función | | |---------|----------| | [!UICONTROL **Nombre de cuenta de ubicación**] | El nombre de la cuenta de ubicación. Este nombre aparece al crear una ubicación | | [!UICONTROL **Descripción de cuenta de ubicación**] | Proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta. | | [!UICONTROL **Tipo de cuenta**] | Seleccione el tipo de cuenta de nube a la que está exportando. Los tipos de cuenta disponibles son Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake y Adobe Experience Platform. |
1. En el [!UICONTROL **Propiedades de cuenta**] , especifique la información específica del tipo de cuenta que ha seleccionado.

   Para obtener instrucciones de configuración, expanda la sección siguiente que corresponde a la variable [!UICONTROL **Tipo de cuenta**] que ha seleccionado.

   +++Amazon S3 Role ARN

   Especifique la siguiente información para configurar una cuenta ARN de la función Amazon S3:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ARN de función**] | Debe proporcionar un ARN de la función (nombre de recurso de Amazon) que el Adobe pueda utilizar para obtener acceso a la cuenta de Amazon S3. Para ello, se crea una directiva de permisos de IAM para la cuenta de origen, se adjunta la directiva a un usuario y, a continuación, se crea un rol para la cuenta de destino. Para obtener información específica, consulte [esta documentación de AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **ARN de usuario**] | El ARN del usuario (nombre del recurso de Amazon) lo proporciona Adobe. Debe adjuntar este usuario a la directiva que ha creado. |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Especifique la siguiente información para configurar una cuenta de Google Cloud Platform:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID del proyecto**] | El ID del proyecto de Google Cloud que copió de su cuenta de Google Cloud. Consulte la [Documentación de Google Cloud sobre la obtención de un ID de proyecto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **Principal**] | El principal lo proporciona el Adobe. Haga clic en [!UICONTROL **Copiar**] junto al icono [!UICONTROL **Principal**] para copiar el contenido del campo y, a continuación, asegúrese de conceder permiso al principal para cargar archivos en este bloque en Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Especifique la siguiente información para configurar una cuenta SAS de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de la aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI de almacén de claves**] | <p>Ruta al token SAS en Azure Key Vault.  Para configurar Azure SAS, debe almacenar un token SAS como secreto mediante Azure Key Vault. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Una vez creado el URI del almacén de claves, agregue una directiva de acceso en el almacén de claves para conceder permiso a la aplicación de Azure que ha creado. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo asignar una directiva de acceso de Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nombre secreto del almacén de claves**] | El nombre secreto que creó al agregar el secreto a Azure Key Vault. En Microsoft Azure, esta información se encuentra en Key Vault que ha creado, en **Key Vault** páginas de configuración. Para obtener más información, consulte [Documentación de Microsoft Azure sobre cómo establecer y recuperar un secreto de Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Secreto de cuenta de ubicación**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique la siguiente información para configurar una cuenta RBAC de Azure:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de la aplicación**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de inquilino**] | Copie este ID de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Información general** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Secreto de cuenta de ubicación**] | Copie el secreto de la aplicación de Azure que ha creado. En Microsoft Azure, esta información se encuentra en **Certificados y secretos** dentro de la aplicación. Para obtener más información, consulte la [Documentación de Microsoft Azure sobre cómo registrar una aplicación con Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Especifique la siguiente información para configurar una cuenta de Snowflake:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Identificador de cuenta**] | Identifica de forma exclusiva una cuenta de Snowflake dentro de su organización, así como en toda la red global de plataformas en la nube y regiones de la nube compatibles con Snowflake. <p>Para obtener más información, consulte la [Página Identificadores de Cuenta en la documentación del Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Usuario**] | Especifica el nombre de inicio de sesión del usuario para la conexión. Se trata de un usuario que se utilizará específicamente para el Adobe. Puede crear el usuario en Snowflake después de especificar el nombre de usuario aquí. <p>Para obtener más información, consulte la [Página Parámetro de conexión del controlador JDBC: Referencia en la documentación del Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Función**] | Función de control de acceso predeterminada que se utiliza en la sesión del Snowflake iniciada por el controlador. Debe crear una función específica para el Adobe que tenga acceso de lectura y escritura.<p>Para obtener más información, consulte la [Página Parámetro de conexión del controlador JDBC: Referencia en la documentación del Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Clave pública**] | La clave pública la proporciona el Adobe. Seleccione el icono Copiar junto al [!UICONTROL **Clave pública**] para copiar el contenido del campo y, a continuación, utilice la clave pública en su cuenta de Snowflake. Para obtener más información, consulte la [Página Autenticación de Par de Claves y Rotación de Par de Claves en la documentación del Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   Todos los clientes de Adobe Experience Platform pueden exportar datos a la zona de aterrizaje de AEP.

   Especifique la siguiente información para configurar una cuenta de Adobe Experience Platform.

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **ID de organización IMS**] | El Adobe proporciona el ID de organización de IMS. Haga clic en el icono Copiar junto a la etiqueta [!UICONTROL **ID de organización IMS**] para copiar el contenido del campo y, a continuación, utilice el ID en su cuenta de Adobe Experience Platform. |

+++

1. Seleccione [!UICONTROL **Guardar**].

1. Continuar con [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md).

