---
description: Funciones de soporte de accesibilidad en Analysis Workspace
title: Accesibilidad en Analysis Workspace
feature: FAQ
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
source-git-commit: 32c507cb9de4fcd146de0e9c828c54c5f4f1a062
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 99%

---

# Accesibilidad en Analysis Workspace

Obtenga información acerca de la compatibilidad con la accesibilidad en [!UICONTROL Analysis Workspace], la herramienta de análisis más importante para Customer Journey Analytics.

La accesibilidad se refiere a hacer que personas con discapacidades visuales, auditivas, cognitivas, motoras y de otro tipo puedan utilizar un producto. Algunos ejemplos de funciones de accesibilidad para productos de software son la compatibilidad con lectores de pantalla, equivalentes de texto para gráficos, métodos abreviados de teclado, cambio de colores de visualización a alto contraste, etc.

[!UICONTROL Analysis Workspace] proporciona algunas herramientas de accesibilidad, entre ellas:

## Navegar por [!UICONTROL Workspace] mediante el teclado

La navegación en el [!UICONTROL Analysis Workspace] funciona desde arriba a abajo e izquierda a derecha. Los siguientes elementos de navegación facilitan la accesibilidad:

* La tecla `Tab` habilita los métodos abreviados de referencia, moviéndose entre secciones más grandes en Workspace. En el carril izquierdo, `Tab` también le permite pasar de una opción arrastrable a la siguiente.
* El movimiento `left/right arrows` entre elementos individuales después de que `Tab` lo haya resaltado.
* El `F6` se desplaza al primer panel del proyecto y se mueve entre las visualizaciones de ese panel. A continuación, se desplaza al siguiente panel del proyecto y se repite.
* Aplicamos indicadores de enfoque para que los usuarios de este tipo de teclados tengan una clara indicación de qué elemento de la interfaz de usuario está seleccionado actualmente. El indicador es un borde azul alrededor del elemento seleccionado.

   ![Indicador de enfoque](assets/focus-indicator.png)

### Navegación por teclado para la barra de menús

1. Use el tabulador hasta que haya llegado a la barra de menús.
1. Utilice las teclas de flecha izquierda/derecha para desplazarse hasta el menú que desee.
1. Pulse `Enter` para seleccionar el menú y mostrar sus opciones.
1. Utilice las teclas de flecha arriba/abajo para ir a la opción de menú que desee.
1. Pulse `Enter` para seleccionar la opción.

### Navegación por teclado para interacciones de arrastrar y soltar

[!UICONTROL Analysis Workspace] es una interfaz de usuario de arrastrar y soltar. Sin embargo, los usuarios pueden agregar componentes mediante el teclado:

1. Tabule hasta un componente en el carril izquierdo.
1. Pulse `Enter` para seleccionarlo.
1. Utilice las teclas de flecha para desplazarse hasta el área en la que desea soltar el componente.
1. Pulse `Enter` para colocar el componente.

### Métodos abreviados de teclado (teclas de acceso directo)

[!UICONTROL Analysis Workspace] ofrece un completo conjunto de [métodos abreviados de teclado](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=es) para lograr un flujo de trabajo más fluido. A continuación se enumeran algunos métodos abreviados comunes para la navegación, la creación de análisis y la democratización de los datos.

#### Navegación

| Acceso directo | Acción |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Saltar a diferentes carriles: [!UICONTROL Paneles], [!UICONTROL Visualizaciones] o [!UICONTROL Componentes] |
| `[Alt + Left / Right]` | Desplazamiento entre paneles |
| `[Alt + M]` | Contraer/Expandir todos los paneles |
| `[Alt + Ctrl + M]` | Contraer/Expandir el panel activo |
| `[Ctrl + /]` | Buscar carril izquierdo |

#### Creación de análisis

| Acceso directo | Acción |
| --- | --- |
| `[Alt + 1]` | Nueva tabla de forma libre |
| `[Ctrl + Shift + C]` | Nueva métrica calculada |
| `[Ctrl + Shift + D]` | Nuevo intervalo de fechas |
| `[Ctrl + Shift + E]` | Nuevo segmento |
| `[Ctrl + Z]` | Deshacer |
| `[Component drag + Shift]` | Creación de un filtro desplegable |

#### Democratización

| Acceso directo | Acción |
| --- | --- |
| `[Ctrl + S]` | Guardar |
| `[Ctrl + Shift + G]` | Depurar |
| `[Ctrl + G]` | Compartir |
| `[Alt + Shift + S]` | Programación |
| `[Alt + L]` | Obtener vínculo al proyecto |
| `[Ctrl + Shift + B]` | Descargar PDF |

## Compatibilidad con lectores de pantalla y ampliadores de pantalla

Un lector de pantalla lee el texto que aparece en la pantalla del equipo. También lee información no textual, como etiquetas de botones o descripciones de imágenes en la aplicación, proporcionada en etiquetas o atributos de accesibilidad.

## Paletas de color y contraste

[!UICONTROL Analysis Workspace] se esfuerza por lograr la conformidad con WCAG 2.1 AA, incluyendo sus requisitos para el contraste de color.

Además, los usuarios pueden establecer su propia paleta de colores preferida para un proyecto en **[!UICONTROL Proyecto]** > **[!UICONTROL Ajustes del proyecto]** > [Paleta de color del proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=es).

## Validación de campo requerida en los generadores de componentes

Al crear un componente, los campos obligatorios se validan al guardarlos. Si un campo requerido no supera la validación, se delineará en rojo con un icono de error. Aparece una descripción por escrito del problema que debe solucionarse.

Una vez validado el componente, al pulsar `Save` se cierra el generador.

![Validación de errores](assets/error-validation.png)

## Compatibilidad con las funciones de accesibilidad del sistema operativo

Analysis Workspace admite funciones de accesibilidad integradas de MS Windows y macOS, como modo de alto contraste, teclas adhesivas y teclas de filtro/teclas lentas. También proporciona información sobre la interfaz de usuario del sistema operativo para habilitar la interacción con tecnologías de asistencia, incluidos lectores de pantalla como VoiceOver para macOS y NVDA en Windows.
