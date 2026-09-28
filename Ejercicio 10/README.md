Sistema de Diseño y Layout Base (CSS Grid)

Maquetación avanzada utilizando CSS Grid Layout, Flexbox para micro-componentes, y una arquitectura basada en componentes UI reutilizables.
Estructuración de una vista tipo *Dashboard* (Header, Sidebar, Main, Footer) utilizando `grid-template-areas`. Se garantizó la ausencia de huecos mediante una correcta definición de la matriz.

Decisiones de Diseño y Arquitectura
Se utilizó la fuente *Inter por su alta legibilidad en interfaces de gestión y paneles de control. Se implementaron variables CSS en `:root` que mapean estrictamente los requisitos solicitados en la rúbrica:

Se utilizó `grid-template-areas` para garantizar un layout semántico y visualmente predictible
Desktop: layout utiliza dos columnas (`260px 1fr`), permitiendo que el `sidebar` ocupe todo el alto disponible debajo del `header`, compartiendo la fila inferior con el `footer`.*Mobile (Responsive): Mediante una *Media Query* (`max-width: 768px`), el layout se transforma en una sola columna fluida (`1fr`), apilando lógicamente las áreas (Header > Sidebar > Main > Footer) para facilitar la navegación táctil.

Componentización y UI
Todos los elementos (Botones, Inputs, Chips, Cards) se diseñaron como clases modulares (`.btn-primario`, `.card`, `.chip`).
Bordes y Sombras se respetaron los requerimientos de `8px` para elementos interactivos (botones/inputs) y `12px` con padding de `16px` para las tarjetas (`.card`).
Forma Píldora:  La clase `.chip` utiliza `border-radius: 9999px` para garantizar la forma circular perfecta en los extremos, sin importar la cantidad de texto que contenga.

Uso de etiquetas semánticas de HTML5 (`<header>`, `<aside>`, `<main>`, `<nav>`, `<footer>`). El campo de búsqueda implementa el patrón de accesibilidad correcto asociando explícitamente `<label for="buscar-producto">` con `<input id="buscar-producto">`.
 
La refactorización se realizó utilizando la metodología Mobile First (estableciendo las reglas base para pantallas pequeñas e introduciendo @media (min-width: ...) para pantallas más grandes).

Rendimiento y Simplicidad: Los dispositivos móviles cargan el código base sin necesidad de procesar complejas reglas de sobreescritura CSS para "desarmar" el grid de escritorio.

Mantenibilidad: Es estructuralmente más lógico diseñar la jerarquía en una sola columna limpia (estado base) y progresivamente ir expandiendo geométricamente el layout (sumando columnas y desplegando el .sidebar)