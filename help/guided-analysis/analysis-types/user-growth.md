---
title: Crecimiento de usuarios
description: Realice un seguimiento del crecimiento de la base de usuarios de su producto.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 2%

---

# Crecimiento de usuarios

{{release-limited-testing}}

El **Crecimiento de usuarios** [Tipo de análisis](overview.md) proporciona perspectivas sobre el crecimiento y la adquisición de usuarios durante un periodo específico. El eje horizontal siempre es una granularidad de tiempo, mientras que el eje vertical siempre es una medida de usuarios. Los usuarios se analizan desde el inicio del intervalo de fechas, dividido en cuatro categorías:

* **Nuevo**: es la primera vez que aparece el usuario en el intervalo de fechas especificado. El primer punto de datos siempre es un 100 % de usuarios nuevos, ya que el análisis no se ve fuera del intervalo de fechas.
* **Repetir**: el usuario apareció en el punto de datos inmediatamente anterior y en el punto de datos actual.
* **Volver**: el usuario no apareció en el punto de datos inmediatamente anterior, pero no es un usuario nuevo. Los usuarios que vuelven no pueden aparecer en el primer o segundo punto de datos, ya que primero deben aparecer como un usuario nuevo y después como un usuario inactivo.
* **Inactivo**: el usuario no apareció en el punto de datos actual, sino en el punto de datos inmediatamente anterior. Los usuarios inactivos no se contabilizan en el número total de usuarios activos.

Todos los usuarios activos (nuevos + repetidos + devueltos) aparecen como un tono de verde azulado encima del eje horizontal, mientras que todos los usuarios inactivos aparecen en naranja debajo del eje horizontal.

Los casos de uso de este tipo de análisis incluyen:

* **Evaluación del rendimiento**: el crecimiento de usuarios le permite evaluar el rendimiento general del producto en términos de adquisición de nuevos usuarios. Al rastrear las tendencias de crecimiento, puede comprender mejor si su producto atrae y retiene a los usuarios a un ritmo deseado.
* **Retención y pérdida de usuarios:** El crecimiento del usuario proporciona una visualización clara de los períodos de retención de usuarios alta o baja. Reconocer estos períodos de retención alta o baja puede ayudarle a tomar decisiones sobre productos para fomentar una retención alta o ayudar a minimizar la pérdida.
* **Evaluación de campaña**: Ver el crecimiento de usuarios específico de una campaña específica puede ayudarle a comprender no solo cuánto tráfico generó, sino también en qué medida la campaña ayudó a los usuarios a seguir participando.

[Captura de pantalla del crecimiento de usuarios]

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **Eventos**: el evento que desea medir. Dado que este tipo de análisis se basa en el usuario, un usuario puede tocar el evento una vez dentro de la granularidad de fecha establecida para contarlo como un usuario activo. Solo puede incluir un evento.
* **People**: El segmento que desea medir. Solo puede incluir un segmento.

## Tipos de vista

El crecimiento de usuarios ofrece los siguientes tipos de vistas. Puede cambiar el tipo de vista mediante el menú desplegable situado en la parte superior izquierda del gráfico.

* **Activo:** Mida el crecimiento de su base de usuarios.

## Ajustes del gráfico

El crecimiento de usuarios ofrece la siguiente configuración de gráfico. Puede ajustar la configuración del gráfico mediante el menú entre el tipo de vista y el selector de calendario.

* **Métrica**: La métrica que desea medir. Las opciones incluyen Número de usuarios y Porcentaje de usuarios.
* **Tipo de gráfico**: el tipo de visualización que desea utilizar. Las opciones incluyen Barra apilada y Área apilada.

## Intervalo de fechas

El intervalo de fechas deseado. Hay dos componentes importantes en esta configuración:

* **Intervalo**: La granularidad de fecha en la que desea ver los datos. Las opciones válidas incluyen Por hora, Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **Fecha**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas están disponibles para su comodidad o puede utilizar el selector de calendario para establecer la fecha exacta deseada.
