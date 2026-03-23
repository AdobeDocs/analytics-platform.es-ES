---
description: Aprenda a utilizar las fuentes de datos para obtener datos sin procesar de Customer Journey Analytics. Descubra los requisitos previos para utilizar fuentes de datos y qué hacer a continuación.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Información general sobre las fuentes de datos de Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: b0b86424399ea79deca8f1d522d52354dfaaa8c7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# Resumen de fuentes de datos

Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Customer Journey Analytics. Estos datos sin procesar se pueden utilizar en otras plataformas fuera de Adobe para su uso según convenga a su organización. Los datos se entregan en lotes por hora al final de cada hora o en lotes diarios al final de cada día.

## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar fuentes de datos.

* Una implementación en funcionamiento con los datos que se están ingiriendo en Adobe Customer Journey Analytics. <!-- For more information, see Data ingestion overview - add link -->
* Su cuenta es un administrador de productos de Analytics o pertenece a un perfil de producto con acceso a fuentes de datos. <!--???-->
* Un contenedor configurado en Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS.<!--Which cloud providers do we support??-->
* (Heredado: requerido solo para los tipos de destino FTP y SFTP heredados) Tenga a mano un sitio FTP y credenciales (credenciales de FTP proporcionadas por su organización).<!--Delete???-->

## Comparación de fuentes de datos en Customer Journey Analytics y Adobe Analytics

La funcionalidad de las fuentes de datos en Customer Journey Analytics difiere de la de Adobe Analytics. Para obtener más información, consulte [Comparar fuentes de datos en Customer Journey Analytics y Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).


## Pasos siguientes

Los siguientes recursos le ayudan a comprender el flujo de trabajo básico de la obtención de fuentes de datos. Después de comprender el flujo de trabajo básico, puede trabajar con equipos de su organización para almacenar o introducir datos sin procesar en una base de datos.

* Prácticas recomendadas de fuentes de datos<!--add link-->: Prácticas recomendadas para crear y administrar fuentes de datos.
* Crear una fuente de datos <!--add link-->: detalles técnicos para crear una fuente de datos; explicación más detallada de los campos individuales
* Administrar fuentes de datos <!--add link-->: Más información sobre cómo navegar por la interfaz de la fuente de datos
* Contenido de fuente de datos <!--add link-->: comprenda qué hay dentro del archivo comprimido <!-- Is this still the output users can download from the destination? I aske Jun. -->
* Definiciones de columnas de datos <!--add link-->: Una lista completa de todas las columnas disponibles.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navegar por la interfaz de la fuente de datos](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Buscar su ID de fuente de datos](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]
