---
title: Crecimiento neto
description: Balance de pérdidas y ganancias del usuario.
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Crecimiento neto

{{release-limited-testing}}

El **Crecimiento neto** tipo de vista proporciona perspectivas sobre la velocidad a la que adquiere o pierde usuarios durante un período específico. El eje horizontal siempre es una granularidad de tiempo, mientras que el eje vertical siempre es la medida del crecimiento.

Cada punto de datos representa el crecimiento neto de ese punto de datos, que se calcula con la siguiente fórmula:

`([New users] + [Return users]) / [Dormant users]`

Similar a la [Activo](active.md) Tipo de vista, los usuarios se definen de la siguiente manera:

* **Nuevo**: el usuario estaba activo durante el punto de datos actual y no ha aparecido en ningún punto de datos anterior.
* **Volver**: el usuario no apareció en el punto de datos inmediatamente anterior, pero no es un usuario nuevo.
* **Inactivo**: el usuario no apareció en el punto de datos actual, sino en el punto de datos inmediatamente anterior. Los usuarios inactivos no se contabilizan en el número total de usuarios activos.

**Repetir** Los usuarios de no se tienen en cuenta en este cálculo, ya que no representan ningún crecimiento o pérdida.

El resultado de esta fórmula es una proporción en la que la base de usuarios creció o se redujo durante ese punto de datos. Un crecimiento neto de `1` representa un equivalente; el producto obtuvo el mismo número de usuarios que perdió. Un crecimiento neto bueno que `1` representa un crecimiento positivo; hubo más usuarios nuevos/de retorno que usuarios inactivos. Del mismo modo, un crecimiento neto menor que `1` representa una pérdida de usuarios activos; había más usuarios inactivos que usuarios nuevos/de retorno.

Los casos de uso para este tipo de vista incluyen:

* **Análisis de adquisición de usuarios**: le permite evaluar la eficacia de sus estrategias de adquisición de usuarios. El análisis de las fuentes de crecimiento de los usuarios, como motores de búsqueda, campañas u otros canales de marketing, permite identificar las fuentes de crecimiento más significativas para poder asignar los recursos en consecuencia.
* **Evaluación del rendimiento**: le permite evaluar el rendimiento general del producto en términos de adquisición de nuevos usuarios. Al rastrear las tendencias de crecimiento, puede comprender mejor si su producto atrae y retiene a los usuarios a un ritmo deseado.
* **Análisis de pérdida**: El crecimiento neto incluye la desgaste en su fórmula (usuarios inactivos). Puede evaluar el estado general de su base de usuarios a lo largo del tiempo. Si el crecimiento neto es sistemáticamente inferior a `1`Sin embargo, indica una gran cantidad de desgaste, lo que le obliga a investigar las razones detrás e implementar estrategias de retención.

[Captura de pantalla del crecimiento de usuarios]

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **Eventos**: el evento que desea medir. Dado que este tipo de vista está basada en el usuario, un usuario puede tocar el evento una vez dentro de la granularidad de fecha establecida para estar en el crecimiento neto. Solo se puede incluir un evento en una consulta.
* **People**: El segmento que desea medir. Solo puede incluir un segmento en una consulta.

## Intervalo de fechas

El intervalo de fechas deseado. Hay dos componentes importantes en esta configuración:

* **Intervalo**: La granularidad de fecha en la que desea ver los datos. Las opciones válidas incluyen Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos que afectan al número de puntos de datos del gráfico y al número de columnas de la tabla. Por ejemplo, si se ve un análisis que abarca tres días con granularidad diaria, solo se mostrarían tres puntos de datos, mientras que un análisis que abarca tres días con granularidad horaria, mostraría 72 puntos de datos.
* **Fecha**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas están disponibles para su comodidad o puede utilizar el selector de calendario para establecer la fecha exacta deseada.
