---
title: Preguntas más frecuentes sobre Attribution
description: Obtenga respuestas a preguntas más frecuentes sobre Attribution.
feature: Attribution
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Preguntas más frecuentes sobre Attribution

**¿Cuál es el elemento de línea Ninguno al utilizar la atribución?**

El elemento de línea “Ninguno” es un captador global que representa todas las conversiones que se produjeron sin ningún punto de contacto dentro de la ventana retrospectiva. Intente incluir un intervalo de tiempo más largo en la ventana de informes.

**¿Por qué a veces veo fechas fuera de la ventana de informes al utilizar modelos de atribución?**

Estas fechas adicionales se deben a la ventana retrospectiva de informes de visitantes. Consulte [Datos que aparecen fuera de la ventana de informes](https://helpx.adobe.com/es/analytics/kb/data-appearing-outside-reporting-window.html) en la BC de Analytics para obtener más información. Adobe filtrará estas filas extra en una próxima versión.

**¿Cuándo debo usar una retrospectiva de atribución de visita o de visitante?**

La elección de la retrospectiva de atribución depende de su caso de uso. Si las conversiones suelen tardar más de una sola visita, se recomienda una retrospectiva del visitante. La creación de una vista de datos con una definición de visita más larga también es una posible solución.

**¿Cómo se comparan las props y las eVars al utilizar la atribución?**

La atribución se vuelve a calcular durante el tiempo de ejecución del informe, por lo que no hay diferencia entre una prop o eVar (o cualquier otra dimensión) en cuanto al modelado de atribución. Las props pueden persistir con cualquier ventana retrospectiva o modelo de atribución y se omiten las opciones de asignación/caducidad de eVar.

**¿Qué dimensiones y métricas no son compatibles?**

El panel de atribución admite todas las dimensiones. Las métricas no admitidas incluyen:

* Visitantes únicos
* Visitas
* Ocurrencias
* Vistas de páginas
* Métricas de A4T
* Métricas de tiempo empleado
* Devoluciones
* Porcentaje de rebote
* Entradas
* Salidas
* Páginas no encontradas
* Búsquedas
* Visitas a una sola página
* Acceso único

**¿Cómo funciona la atribución con los filtros?**

La atribución siempre se ejecuta antes que los filtros y los filtros globales se ejecutan antes de que se aplique cualquier otro filtro de informe.
