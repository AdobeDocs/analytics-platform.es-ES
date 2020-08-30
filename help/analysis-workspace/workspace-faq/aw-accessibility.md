---
description: Funciones de soporte de accesibilidad en Analysis Workspace
title: Accesibilidad en Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 100%

---


# Accesibilidad en Analysis Workspace

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Obtenga información sobre la compatibilidad con la accesibilidad en [!UICONTROL Analysis Workspace], la herramienta de análisis más importante para Adobe Analytics.

La accesibilidad se refiere a hacer que personas con discapacidades visuales, auditivas, cognitivas, motoras y de otro tipo puedan utilizar un producto. Algunos ejemplos de funciones de accesibilidad para productos de software son la compatibilidad con lectores de pantalla, equivalentes de texto para gráficos, métodos abreviados de teclado, cambio de colores de visualización a alto contraste, etc.

[!UICONTROL Analysis Workspace] proporciona algunas herramientas de accesibilidad, entre ellas:

## Navegar por [!UICONTROL Workspace] mediante el teclado

La navegación en el [!UICONTROL Analysis Workspace] funciona desde arriba a abajo e izquierda a derecha. Los siguientes elementos de navegación facilitan la accesibilidad:

* La tecla `F6` habilita los métodos abreviados de referencia
* La tecla `Tab` permite moverse entre elementos individuales.
* Aplicamos indicadores de enfoque para que los usuarios de este tipo de teclados tengan una clara indicación de qué elemento de la interfaz de usuario está seleccionado actualmente. El indicador es un borde azul alrededor del elemento seleccionado.

   ![Indicador de enfoque](assets/focus-indicator.png)

### Navegación por teclado para interacciones de arrastrar y soltar

[!UICONTROL Analysis Workspace] es una interfaz de usuario de arrastrar y soltar. Sin embargo, los usuarios pueden agregar componentes mediante el teclado:

1. Tabule hasta un componente en el carril izquierdo.
1. Pulse `Enter` para seleccionarlo.
1. Utilice las teclas de flecha para desplazarse hasta el área en la que desea soltar el componente.
1. Pulse `Enter` para colocar el componente.

### Métodos abreviados de teclado (teclas de acceso directo)

[!UICONTROL Analysis Workspace] ofrece un completo conjunto de [métodos abreviados de teclado](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) para lograr un flujo de trabajo más fluido. A continuación se enumeran algunos métodos abreviados comunes para la navegación, la creación de análisis y la democratización de los datos.

#### Navegación

| Acceso directo | Acción |
|---|---|
| Alt + Mayús + 1 / 2 / 3 | Saltar a diferentes carriles: [!UICONTROL Paneles], [!UICONTROL Visualizaciones] o [!UICONTROL Componentes] |
| Alt + flecha izquierda/derecha | Desplazamiento entre paneles |
| Alt + M | Contraer/Expandir todos los paneles |
| Alt + Ctrl + M | Contraer/Expandir panel activo |
| Ctrl + / | Buscar carril izquierdo |

#### Creación de análisis

| Acceso directo | Acción |
|---|---|
| Alt + 1 | Nueva tabla improvisada |
| Ctrl + Mayús + C | Nueva métrica calculada |
| Ctrl + Mayús + D | Nuevo intervalo de fechas |
| Ctrl + Mayús + E | Nuevo segmento |
| Ctrl + Z | Deshacer |
| Mantenga pulsada la tecla Mayús (en la zona desplegable de segmentos del panel) | Cree un [filtro desplegable](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### Democratización

| Acceso directo | Acción |
|---|---|
| Ctrl + S | Guardar |
| Ctrl + Mayús + G | Depurar |
| Ctrl + G | Compartir |
| Alt + Mayús + S | Programación |
| Alt + L | Obtener vínculo al proyecto |
| Ctrl + Mayús + B | Descargar PDF |

## Compatibilidad con lectores de pantalla y ampliadores de pantalla

Un lector de pantalla lee el texto que aparece en la pantalla del equipo. También lee información no textual, como etiquetas de botones o descripciones de imágenes en la aplicación, proporcionada en etiquetas o atributos de accesibilidad.

## Paletas de color y contraste

[!UICONTROL Analysis Workspace] se esfuerza por lograr la conformidad con WCAG 2.1 AA, incluyendo sus requisitos para el contraste de color.

Además, los usuarios pueden establecer su propia paleta de colores preferida para un proyecto en **[!UICONTROL Proyecto]** > **[!UICONTROL Ajustes del proyecto]** > [Paleta de color del proyecto](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Validación de campo requerida en los generadores de componentes

Al crear un componente, los campos obligatorios se validan al guardarlos. Si un campo requerido no supera la validación, se delineará en rojo con un icono de error. Aparece una descripción por escrito del problema que debe solucionarse.

Una vez validado el componente, al pulsar `Save` se cierra el generador.

![Validación de errores](assets/error-validation.png)

## Compatibilidad con las funciones de accesibilidad del sistema operativo

Analysis Workspace admite funciones de accesibilidad integradas de MS Windows y macOS, como modo de alto contraste, teclas adhesivas y teclas de filtro/teclas lentas. También proporciona información sobre la interfaz de usuario del sistema operativo para habilitar la interacción con tecnologías de asistencia, incluidos lectores de pantalla como VoiceOver para macOS y NVDA en Windows.