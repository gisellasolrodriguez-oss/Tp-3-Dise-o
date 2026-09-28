Detalles de la Implementación Semántica y Técnica:
Accesibilidad (a11y): Cada elemento <label> tiene el atributo for que coincide exactamente con el atributo id de su respectivo <input> o <textarea>. Esto permite que si el usuario hace clic en el texto de la etiqueta, el foco se mueva automáticamente al campo correspondiente, lo cual es vital para lectores de pantalla y facilidad de uso.

Validación Nativa HTML5:
Se utilizó el atributo required en todos los campos, lo que impide que el formulario se envíe si están vacíos, mostrando las alertas nativas del navegador.

Se utilizó type="email" en el correo, lo que obliga al navegador a validar que el texto ingresado tenga el formato correcto (usuario@dominio.com) antes de enviarlo.

CSS Moderno: Se utilizó Flexbox en .formulario-contacto y .grupo-form para apilar los elementos verticalmente de forma limpia, usando la propiedad gap para manejar los márgenes internos sin necesidad de usar margin-bottom en cada elemento. Además, se agregaron estilos de :focus claros para mejorar la navegación por teclado.

Ejercicio 13:
Se integró dentro de un contenedor tipo tarjeta con sombras suaves para darle mayor jerarquía visual sobre el fondo. Los campos de texto y el botón principal ahora presentan bordes redondeados uniformes que modernizan considerablemente la estética del diseño. Se añadió un estado :focus muy claro en los inputs, el cual resalta el borde de color índigo y proyecta un resplandor luminoso exterior para indicarle al usuario dónde está escribiendo. El botón incorporó interactividad avanzada, oscureciéndose levemente al pasar el cursor (:hover) y reduciendo su tamaño para simular un efecto de hundimiento físico al hacer clic (:active). Finalmente, todas estas interacciones visuales se suavizaron utilizando la propiedad transition, lo que garantiza un feedback fluido y profesional en cada cambio de estado.