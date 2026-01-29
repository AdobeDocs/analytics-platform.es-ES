---
title: Advertencias
description: Advertencias sobre la extensión de BI en varias herramientas de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Advertencias


Cada una de las herramientas de BI admitidas tiene algunas advertencias a la hora de trabajar con la extensión de BI de Customer Journey Analytics.

+++ Herramientas de BI

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

* El filtrado avanzado de intervalos de fechas de Power BI Desktop es exclusivo.  Para la fecha de finalización, debe seleccionar una fecha posterior al día en el que desee crear el informe. Por ejemplo, **[!UICONTROL es el]** `1/1/2023` **[!UICONTROL y antes del]** `1/2/2023` o después de este.
* Power BI Desktop usa el valor predeterminado **[!UICONTROL Importar]** al crear una conexión. Asegúrese de usar **[!UICONTROL Direct Query]**.
* Power BI Desktop expone las transformaciones de datos a través de Power Query.  Power Query funciona principalmente con conexiones de tipo Import, por lo que muchas transformaciones que se aplican, como funciones de fecha o cadena, generan un error que indica que debe cambiar a una conexión de tipo Import.  Si necesita transformar los datos en el momento de la consulta, debe utilizar dimensiones y métricas derivadas para que Power BI no necesite realizar las transformaciones en sí.
* Power BI Desktop no entiende cómo gestionar columnas de tipo fecha-hora, por lo que las dimensiones **[!UICONTROL daterange *X *]**&#x200B;como&#x200B;**[!UICONTROL daterangehour &#x200B;]**&#x200B;y&#x200B;**[!UICONTROL daterangeminute &#x200B;]**&#x200B;no son compatibles.
* Power BI Desktop de forma predeterminada intenta realizar varias conexiones con un máximo de sesiones de Query Service.  Vaya a la configuración de Power BI para el proyecto y deshabilite las consultas paralelas.
* Power BI Desktop realiza toda la ordenación y limitación del lado del cliente. Power BI Desktop también tiene una semántica diferente para el filtrado superior *X* que incluye valores vinculados. Por lo tanto, no se puede crear la misma ordenación y limitación que en Analysis Workspace.
* Las versiones anteriores del lanzamiento de Power BI Desktop de octubre de 2024 rompen las fuentes de datos PostgreSQL. Asegúrese de utilizar la versión mencionada en este artículo.

>[!TAB Escritorio Tableau]

* El filtrado Tableau Desktop Range of Dates es exclusivo. Para la fecha de finalización, debe seleccionar una fecha posterior al día en el que desee crear el informe.
* De manera predeterminada, cuando se agrega una dimensión de fecha y hora como **[!UICONTROL Daterangemonth]** a las filas de una hoja, Tableau Desktop ajusta el campo en una función **[!UICONTROL YEAR()]**.  Para obtener lo que desea, debe seleccionar esa dimensión y en el menú desplegable, seleccionar la función de fecha que desee utilizar.  Por ejemplo, cambie **[!UICONTROL Year]** a **[!UICONTROL Month]** cuando intente usar **[!UICONTROL Daterangemonth]**.
* Limitar los resultados a los *X* principales no es obvio en Tableau Desktop. Puede limitar los resultados explícitamente o mediante un campo calculado y la función **[!UICONTROL INDEX()]**.  Agregar un filtro *X* superior a una dimensión genera SQL complejo mediante una combinación interna no compatible.

>[!TAB Buscador]

* El buscador tiene un número máximo de conexiones por configuración de nodo que debe estar entre 5 y 100.  No puede establecer este valor en 1.  Esta configuración implica que una conexión de Buscador siempre utiliza al menos 5 de las sesiones de servicio de consultas disponibles.
* Looker permite crear un proyecto con una vista basada en una vista de datos de Customer Journey Analytics. A continuación, Looker crea un modelo basado en las dimensiones y métricas disponibles en la vista Datos mediante LookerML.  Esta vista de proyecto no se actualiza automáticamente para que coincida con el origen.  Si realiza cambios o adiciones a las dimensiones, métricas, métricas calculadas o segmentos de la vista de datos de CJA, estos cambios no se muestran automáticamente en Looker.  Debe actualizar manualmente la vista de proyecto o crear un nuevo proyecto.
* La experiencia del usuario del buscador en campos de fecha y hora como **[!UICONTROL Daterange Date]** o **[!UICONTROL Daterangeday Date]** es confusa.
* El intervalo de fechas del buscador es exclusivo en lugar de inclusivo.  **[!UICONTROL hasta (antes)]** está en gris, por lo que puede pasar por alto ese aspecto.  Para el día de finalización, debe seleccionar uno después del día en el que desee crear el informe.
* Looker no trata automáticamente sus métricas como métricas.  Al seleccionar una métrica, Looker intenta de forma predeterminada tratar la métrica como una dimensión en la consulta.  Para tratar una métrica como una métrica, debe crear un campo personalizado como se ilustra arriba. Como método abreviado, puede seleccionar **[!UICONTROL ⋮]**, seleccionar **[!UICONTROL Agregar]** y, a continuación, seleccionar **[!UICONTROL Suma]**.

>[!TAB Jupyter Notebook]

* La principal advertencia para Jupyter Notebook es que la herramienta no tiene una interfaz de usuario de arrastrar y soltar como otras herramientas de BI. Puede crear buenos elementos visuales, pero debe escribir código para lograrlo.

>[!TAB EstudioRS]

* R dplyr funciona con un esquema plano, por lo que se requiere la opción **[!UICONTROL FLATTEN]**.
* La advertencia principal para RStudio es que la herramienta no utiliza una interfaz de usuario de arrastrar y soltar como otras herramientas de BI. Puede crear buenos elementos visuales, pero debe escribir código para lograrlo.

>[!ENDTABS]

+++
