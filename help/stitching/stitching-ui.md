---
title: Unión
description: Obtenga información sobre cómo crear y administrar conjuntos de datos enlazados
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# Crear y administrar conjuntos de datos enlazados

La vinculación permite a los administradores vincular identidades en conjuntos de datos disponibles en el Customer Journey Analytics. La vinculación de conjuntos de datos aumenta la precisión de la representación de un perfil, lo que en última instancia resulta en un mejor análisis e informes.

El proceso de vinculación permite definir un **ID persistente** en un conjunto de datos. A continuación, vincule ese identificador persistente para una ventana de reproducción especificada (diaria, semanal) con la más precisa **ID transitorio** (persona o identificador autenticado) disponible para ese conjunto de datos. Algunos ejemplos de identificadores transitorios son correo electrónico, número de teléfono, ID de CRM u otras identidades almacenadas en el gráfico. Consulte [Información general](overview.md) para obtener más información sobre la vinculación.

## Crear

Para iniciar la vinculación, debe crear uno o varios conjuntos de datos vinculados. Para crear un conjunto de datos vinculado:

1. Seleccionar **[!UICONTROL ** Vinculación **]** de **[!UICONTROL ** Administración de datos **]** en la barra superior.

2. En el [!UICONTROL Conjuntos de datos enlazados] pantalla, seleccione **[!UICONTROL ** Crear conjunto de datos vinculado **]**.

   Se le mostrará un cuadro de diálogo en el que se explican sus responsabilidades.

3. Seleccionar **[!UICONTROL ** Continuar **]** si acepta estas responsabilidades.

   >[!NOTE]
   >
   >    Si selecciona **[!UICONTROL ** Cancelar **]** Sin embargo, no puede crear un conjunto de datos vinculado.

4. En el [!UICONTROL Conjuntos de datos enlazados > Conjunto de datos enlazados sin título] pantalla:

   1. Defina un **[!UICONTROL ** Nombre del conjunto de datos **]** y (opcional) **[!UICONTROL ** Descripción **]**,

   2. Seleccione la zona protegida de la **[!UICONTROL ** Sandbox **]** lista donde se almacena el conjunto de datos de evento.

      ![Pantalla de creación inicial](./assets/create-initial.png)

   3. Seleccione el **[!UICONTROL ** Seleccionar conjunto de datos de origen **]** botón.

      En el [!UICONTROL Seleccionar un conjunto de datos para vincular] ventana emergente:

      ![Seleccionar un conjunto de datos](./assets/select-one-dataset.png)

      - Seleccione un conjunto de datos y seleccione **[!UICONTROL ** Seleccionar **]** para continuar.

   4. Seleccione un identificador persistente de la **[!UICONTROL ** ID persistente **]** lista.

   5. Seleccione un identificador transitorio de la **[!UICONTROL ** ID transitorio **]** lista.

      Verá que aparece un panel de vista previa para calcular las tasas de saturación (cantidad de veces que hay un valor para cada uno de los identificadores especificados a lo largo del número de eventos) durante los últimos siete días. Cuando termina de calcular, el panel visualiza con colores si se cumplen las condiciones mínimas de vinculación (verde) o no (rojo).

      ![Crear conjunto de datos vinculado con tasas de saturación](./assets/create-before-experimenting.png)

      Las condiciones mínimas son:

      - saturación de identificador persistente: tasa >= 95 %

      - saturación de identificador transitorio: tasa >= 5 %

        Si se cumplen las condiciones mínimas, puede experimentar con valores de muestra.

      - Seleccionar **[!UICONTROL ** Crear ID vinculados de demostración **]**.

        En el [!UICONTROL Experimentar con valores de muestra] , se muestra una tabla con un valor de muestra para [!UICONTROL timestamp], [!UICONTROL ID persistente], [!UICONTROL ID transitorio], [!UICONTROL ID con título (activo)], [!UICONTROL ID con título (reproducción de 1 día)], y [!UICONTROL ID vinculado (reproducción de 7 días)].

            ![Experimento con valores de muestra](./assets/experiment-sample-values.png)
            
            1.  Introduzca un valor para la **[!UICONTROL **ID persistente**]**.
            
            2.  Seleccionar **[!UICONTROL **Actualizar ID vinculados**]** para ver el efecto del proceso de vinculación en los datos del conjunto de datos.
            
            3.  Seleccionar **[!UICONTROL **Cerrar**]** cuando haya terminado de experimentar con valores de muestra.
        

        De nuevo en [!UICONTROL Conjuntos de datos enlazados > _Nombre del conjunto de datos_] pantalla:

   6. Seleccione una opción para la frecuencia y el período de reafirmación de datos históricos en la **[!UICONTROL ** Ventana de repetición **]** lista.

      Puede seleccionar entre el valor predeterminado **[!UICONTROL ** Día anterior, diario **]** o **[!UICONTROL ** 7 días anteriores, semanales **]**.

   7. Seleccione un valor del **[!UICONTROL ** Promedio del número de eventos diarios **]** lista.

   8. Introduzca un valor (entre `0` y `12`) en **[!UICONTROL ** Número de meses para rellenar **]**.

   9. Seleccionar **[!UICONTROL ** Guardar **]** para guardar el conjunto de datos vinculado e iniciar la vinculación.

## Ver estado

Puede ver el estado de la vinculación en la [!UICONTROL Conjuntos de datos enlazados] lista.

- Seleccionar **[!UICONTROL ** Vinculación **]** de **[!UICONTROL ** Administración de datos **]** en la barra superior.

  Verá una lista de conjuntos de datos enlazados, cada uno identificado con [!UICONTROL Sandbox], [!UICONTROL Conjunto de datos de origen], [!UICONTROL Estado], [!UICONTROL Estado de relleno], [!UICONTROL Propietario], y [!UICONTROL Fecha de creación].

  ![Información general sobre conjuntos de datos enlazados](./assets/overview-stitched-datasetts.png)

  Valores posibles para [!UICONTROL Estado] son:

  | Valor | Explicación |
  |-----|-----|
  | **[!UICONTROL ** En cola **]** | La solicitud se recibe y se procesa pronto. |
  | **[!UICONTROL ** Creación en curso **]** | Los recursos y el conjunto de datos recién enlazado están en creación. |
  | **[!UICONTROL ** Vinculación en curso **]** | Existen los recursos y el conjunto de datos vinculado y la vinculación está en curso |
  | **[!UICONTROL ** Error **]** | Hay un problema con la vinculación. Tal vez haya cambiado un esquema entre el conjunto de datos de origen y el conjunto de datos vinculado, el volumen diario es demasiado grande o... (_**necesita más información aquí...**_) |

  >[!INFO]
  >
  >    Cada vez que cambia un estado, se envía una notificación con el mensaje **[!UICONTROL ** Conjunto de datos vinculado _nombre del conjunto de datos_ ha cambiado a estado _nombre del estado _**]**.


  El [!UICONTROL Estado de relleno] puede tener los siguientes valores: 0 %, 25 %, 50 %, 75 % o 100 %.

  Puede seleccionar el icono de información para mostrar una ventana emergente con más detalles sobre el conjunto de datos vinculado seleccionado.


## Eliminar

>[!NOTE]
>
>Solo puede eliminar conjuntos de datos que tengan el estado [!UICONTROL Vinculación en curso], [!UICONTROL Error], o [!UICONTROL En cola].


Para eliminar un solo conjunto de datos vinculado:

- Seleccionar **[!UICONTROL **...**]** para el conjunto de datos vinculado y seleccione **[!UICONTROL ** Eliminar **]** en el menú.

  ![Eliminar un conjunto de datos vinculado](./assets/delete-stitched-dataset.png)

Para eliminar varios datos vinculados:

- Seleccione varios conjuntos de datos enlazados mediante la casilla de verificación al principio de cada conjunto de datos enumerado.

- Seleccionar **[!UICONTROL **...**]** de uno de los conjuntos de datos enlazados seleccionados y seleccione **[!UICONTROL ** Eliminar **]** en el menú.
