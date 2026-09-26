 Sistema de Componentes y Galería Flexbox

Este documento detalla las decisiones técnicas y de diseño implementadas en el desarrollo de la interfaz de usuario, los componentes base y la galería de productos responsiva.

 Decisiones de Diseño y Arquitectura CSS

 Variables Globales (CSS Custom Properties)
Se implementó un sistema de variables en la raíz (`:root`) para manejar la paleta de colores (primario, acento, fondos, textos) y la tipografía. Esto centraliza el diseño, asegura la consistencia visual en todos los componentes y facilita enormemente la mantenibilidad o futuras implementaciones (como un "Modo Oscuro").

Tipografía y Jerarquía
Se seleccionó la fuente **Inter** por su excelente legibilidad en interfaces digitales y su aspecto limpio. La jerarquía de tamaños se diseñó para guiar la vista del usuario:
- Títulos (26px, Bold): Dan peso estructural a la vista principal.
- Subtítulos (18px) y Cuerpo (14px): Optimizados para la lectura ágil dentro de las tarjetas.
- Textos Auxiliares (12px, gris): Agregan contexto (como información de envíos o labels) sin competir visualmente con la información principal.

 Layout Responsivo Fluido (El poder de Flexbox)
Para la cuadrícula de productos (`.galeria-grid`), se evitó el uso rígido de Media Queries. En su lugar, se optó por un diseño intrínsecamente responsivo mediante Flexbox:
- El uso combinado de `flex-wrap: wrap` con un `gap` de 24px asegura la distribución limpia.
- La regla `flex: 1 1 300px` (`flex-grow`, `flex-shrink`, `flex-basis`) en cada tarjeta permite que los productos tengan un ancho ideal de 300px, pero crezcan para rellenar los espacios vacíos de la fila. Si la pantalla se achica, fluyen naturalmente hacia abajo.

 Componentización Modular
Los elementos de la interfaz se maquetaron como bloques reutilizables independientes:
Cards (Tarjetas): Utilizan internamente `display: flex; flex-direction: column`. Se aplicó `margin-top: auto;` al contenedor de los botones para asegurar que, sin importar cuánto texto tenga el producto, las acciones de compra siempre queden perfectamente alineadas en la base de la tarjeta.
Botones y Chips: Diseñados con bordes redondeados (8px y formato píldora) para mantener un estilo moderno. Comparten propiedades base, delegando los colores a clases modificadoras (`.btn-primario`, `.btn-secundario`).

 Microinteracciones y Accesibilidad
Se añadieron sutiles transiciones (`transition: 0.2s ease`) a todos los elementos interactivos:
- Las tarjetas se elevan levemente y aumentan su sombra al pasar el cursor (`:hover`), indicando que son clicables.
- Los inputs cambian el color de su borde al recibir foco (`:focus`), mejorando la accesibilidad y la experiencia de usuario al navegar por teclado.