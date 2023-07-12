---
title: Activo
description: Medir el crecimiento de la base de usuarios.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 2%

---

# Activo

{{release-limited-testing}}

El **Activo** tipo de vista proporciona perspectivas sobre el crecimiento y la adquisición de usuarios durante un periodo específico. El eje horizontal siempre es una granularidad de tiempo, mientras que el eje vertical siempre es una medida de usuarios. Los usuarios se analizan desde el inicio del intervalo de fechas, dividido en cuatro categorías:

* **Nuevo**: el usuario estaba activo durante el punto de datos actual y no ha aparecido en ningún punto de datos anterior. Pase el ratón sobre &#39;[!UICONTROL Nuevos usuarios]&#39; en la leyenda del gráfico para ver hasta dónde alcanza el informe para determinar un nuevo usuario. Esta fecha se selecciona dinámicamente en función de la longitud y granularidad del intervalo de fechas.
* **Repetir**: el usuario apareció en el punto de datos inmediatamente anterior y en el punto de datos actual.
* **Volver**: el usuario no apareció en el punto de datos inmediatamente anterior, pero no es un usuario nuevo.
* **Inactivo**: el usuario no apareció en el punto de datos actual, sino en el punto de datos inmediatamente anterior. Los usuarios inactivos no se contabilizan en el número total de usuarios activos.

Todos los usuarios activos (nuevos + repetidos + devueltos) aparecen como un tono de verde azulado encima del eje horizontal, mientras que todos los usuarios inactivos aparecen en naranja debajo del eje horizontal.

Los casos de uso para este tipo de vista incluyen:

* **Retención y pérdida de usuarios:** Proporciona una visualización clara de los períodos de retención de usuarios alta o baja. Reconocer estos períodos de retención alta o baja puede ayudarle a tomar decisiones sobre productos para fomentar una retención alta o ayudar a minimizar la pérdida.
* **Evaluación de campaña**: Ver una campaña específica puede ayudarle a comprender no solo cuánto tráfico generó, sino también en qué medida la campaña ayudó a los usuarios a seguir participando.
* **Análisis del ciclo vital de usuario**: El análisis del crecimiento activo del usuario a lo largo del ciclo vital de este puede ayudar a identificar fases específicas en las que disminuye la participación del usuario. Por ejemplo, si hay una alta proporción de usuarios inactivos para aquellos que se encuentran en una fase de incorporación, puede indicar problemas de uso o una necesidad de una mejor orientación del producto.

![Activo](../assets/active.png)

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **Eventos**: el evento que desea medir. Dado que este tipo de vista se basa en el usuario, un usuario puede tocar el evento una vez dentro de la granularidad de fecha establecida para contarse como un usuario activo. Solo se puede incluir un evento en una consulta.
* **People**: El segmento que desea medir. Solo puede incluir un segmento en una consulta.

## Ajustes del gráfico

Este tipo de vista ofrece la siguiente configuración de gráfico. Puede ajustar la configuración del gráfico mediante el menú entre el tipo de vista y el selector de calendario.

* **Métrica**: La métrica que desea medir. Las opciones incluyen Número de usuarios y Porcentaje de usuarios.
* **Tipo de gráfico**: el tipo de visualización que desea utilizar. Las opciones incluyen Barra apilada y Área apilada.

## Aplicar comparación de tiempo

{{apply-time-comparison}}

![Comparación del tiempo activo](../assets/active-compare.png)

## Intervalo de fechas

El intervalo de fechas deseado. Hay dos componentes importantes en esta configuración:

* **Intervalo**: La granularidad de fecha en la que desea ver los datos. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **Fecha**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas están disponibles para su comodidad o puede utilizar el selector de calendario para establecer la fecha exacta deseada.
