---
title: Unión
description: Obtenga información sobre cómo crear y administrar conjuntos de datos enlazados
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Creación y administración de conjuntos de datos identificados

{{select-package}}

La vinculación permite a los administradores vincular identidades en conjuntos de datos disponibles en Customer Journey Analytics. La vinculación de conjuntos de datos aumenta la precisión de la representación de un perfil, lo que en última instancia resulta en un mejor análisis e informes.

El proceso de vinculación le permite definir un **ID persistente** existente en un conjunto de datos. Luego vincule ese identificador persistente para una ventana de reproducción especificada (diaria, semanal) con la **ID de persona** (persona o identificador autenticado) más precisa disponible para ese conjunto de datos. Algunos ejemplos de identificadores de persona son correo electrónico, número de teléfono, ID de CRM u otras identidades almacenadas en el gráfico. Consulte [Información general](overview.md) para obtener más información sobre la vinculación.

## Crear

Para iniciar la vinculación, debe crear uno o varios conjuntos de datos vinculados. Para crear un conjunto de datos vinculado:

1. Seleccione **[!UICONTROL ** Vinculación **]** de **[!UICONTROL ** Administración de datos **]** en la barra superior.

2. En la pantalla [!UICONTROL Conjuntos de datos vinculados], seleccione **[!UICONTROL ** Crear conjunto de datos vinculado **]**.

   Se le mostrará un cuadro de diálogo en el que se explican sus responsabilidades.

3. Seleccione **[!UICONTROL ** Continuar **]** si acepta estas responsabilidades.

   >[!NOTE]
   >
   >    Si selecciona **[!UICONTROL ** Cancelar **]**, no podrá crear un conjunto de datos enlazado.

4. En la pantalla [!UICONTROL Conjuntos de datos enlazados > Conjunto de datos enlazados sin título]:

   1. Definir un **[!UICONTROL ** nombre de conjunto de datos **]** y (opcional) **[!UICONTROL ** Descripción **]**,

   2. Seleccione la zona protegida de la lista **[!UICONTROL ** Zona protegida **]** donde se almacena el conjunto de datos de evento.

      ![Pantalla de creación inicial](./assets/create-initial.png)

   3. Seleccione el botón **[!UICONTROL ** Seleccionar conjunto de datos de origen **]**.

      En la ventana emergente [!UICONTROL Seleccionar un conjunto de datos para unir]:

      ![Seleccionar un conjunto de datos](./assets/select-one-dataset.png)

      - Seleccione un conjunto de datos y seleccione **[!UICONTROL ** Seleccionar **]** para continuar.

   4. Seleccione un identificador persistente de la lista **[!UICONTROL ** ID persistente **]**.

   5. Seleccione un identificador de persona de la lista **[!UICONTROL ** ID transitorio **]**.

      Verá que aparece un panel de vista previa para calcular las tasas de saturación (cantidad de veces que hay un valor para cada uno de los identificadores especificados a lo largo del número de eventos) durante los últimos siete días. Cuando termina de calcular, el panel visualiza con colores si se cumplen las condiciones mínimas de vinculación (verde) o no (rojo).

      ![Crear conjunto de datos enlazado con tasas de saturación](./assets/create-before-experimenting.png)

      Las condiciones mínimas son:

      - saturación de identificador persistente: tasa >= 95 %

      - saturación del identificador de persona: tasa >= 5 %

        Si se cumplen las condiciones mínimas, puede experimentar con valores de muestra.

      - Seleccione **[!UICONTROL ** Crear ID vinculado de demostración **]**.

        En el cuadro de diálogo [!UICONTROL Experimento con valores de muestra], se muestra una tabla con un valor de muestra para [!UICONTROL timestamp], [!UICONTROL ID persistente], [!UICONTROL ID transitorio], [!UICONTROL ID con título (activo)], [!UICONTROL ID con título (reproducción de 1 día)] y [!UICONTROL ID con título (reproducción de 7 días)].

        ¡    ![Experimente con valores de muestra](./assets/experiment-sample-values.png)
            
            1.  Escriba un valor para el **[!UICONTROL **ID persistente**]**.
            
            2.  Seleccione **[!UICONTROL **Actualizar los ID vinculados**]** para ver el efecto del proceso de vinculación en los datos del conjunto de datos.
            
            3.  Seleccione **[!UICONTROL **Close**]** cuando haya terminado de experimentar con valores de muestra.
        

        Vuelva a la pantalla [!UICONTROL Conjuntos de datos enlazados > _Nombre del conjunto de datos_]:

   6. Seleccione una opción para la frecuencia y el período de restauración de datos históricos en la lista **[!UICONTROL ** Ventana de reproducción **]**.

      Puede seleccionar entre el valor predeterminado **[!UICONTROL ** Día anterior, diario **]** o **[!UICONTROL ** Días anteriores, semanales **]**.

   7. Seleccione un valor de la lista **[!UICONTROL ** Cantidad promedio de eventos diarios **]**.

   8. Escriba un valor (entre `0` y `12`) en **[!UICONTROL ** Número de meses para rellenar **]**.

   9. Seleccione **[!UICONTROL ** Guardar **]** para guardar el conjunto de datos vinculado e iniciar la vinculación.

## Ver estado

Puede ver el estado de la vinculación en la lista [!UICONTROL Conjuntos de datos vinculados].

- Seleccione **[!UICONTROL ** Vinculación **]** de **[!UICONTROL ** Administración de datos **]** en la barra superior.

  Verá una lista de conjuntos de datos enlazados, cada uno identificado con [!UICONTROL espacio aislado], [!UICONTROL conjunto de datos de Source], [!UICONTROL Estado], [!UICONTROL Estado de relleno], [!UICONTROL Propietario] y [!UICONTROL Fecha de creación].

  ![Información general sobre conjuntos de datos enlazados](./assets/overview-stitched-datasetts.png)

  Los valores posibles de [!UICONTROL Status] son:

  | Valor | Explicación |
  |-----|-----|
  | **[!UICONTROL ** En cola **]** | La solicitud se recibe y se procesa pronto. |
  | **[!UICONTROL ** Creación **]** en curso | Los recursos y el conjunto de datos recién enlazado están en creación. |
  | **[!UICONTROL ** Configuración en curso **]** | Existen los recursos y el conjunto de datos vinculado y la vinculación está en curso |
  | **[!UICONTROL ** Error **]** | Hay un problema con la vinculación. Tal vez se cambió un esquema entre el conjunto de datos de origen y el conjunto de datos vinculado, el volumen diario es demasiado grande o... (_**necesita más información aquí...**_) |

  >[!INFO]
  >
  >    Cada vez que cambia el estado, se envía una notificación con el mensaje **[!UICONTROL ** El conjunto de datos vinculado _nombre del conjunto de datos_ ha cambiado al estado _nombre del estado _**]**.


  El [!UICONTROL estado de relleno] puede tener los siguientes valores: 0%, 25%, 50%, 75% o 100%.

  Puede seleccionar el icono de información para mostrar una ventana emergente con más detalles sobre el conjunto de datos vinculado seleccionado.


## Eliminar

>[!NOTE]
>
>Solo puede eliminar conjuntos de datos que tengan el estado [!UICONTROL Configuración en curso], [!UICONTROL Error] o [!UICONTROL En cola].


Para eliminar un solo conjunto de datos vinculado:

- Seleccione **[!UICONTROL **...**]** para el conjunto de datos enlazado y seleccione **[!UICONTROL ** Eliminar **]** del menú.

  ![Eliminar un conjunto de datos vinculado](./assets/delete-stitched-dataset.png)

Para eliminar varios datos vinculados:

- Seleccione varios conjuntos de datos enlazados mediante la casilla de verificación al principio de cada conjunto de datos enumerado.

- Seleccione **[!UICONTROL **...**]** de uno de los conjuntos de datos enlazados seleccionados y seleccione **[!UICONTROL ** Eliminar **]** del menú.
