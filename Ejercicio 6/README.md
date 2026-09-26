Organización del CSS: El archivo está comentado y dividido lógicamente de menor a mayor especificidad (Etiquetas -> Clases -> IDs), lo que facilita su lectura y mantenimiento.

Selector de Clase (.card): Se utiliza para dar una base de estilo idéntica a los tres <div>, evitando repetir código.

Selector de ID (#plan-destacado): Al tener mayor especificidad (peso) que una clase, CSS le da prioridad. Por eso, aunque el "Plan Premium" tiene la clase .card (fondo blanco, borde gris), el ID #plan-destacado logra sobreescribir esos valores (fondo celeste, borde azul).

Selectores Descendientes (.card p, .card p span): En lugar de ponerle una clase a cada párrafo o span, usamos la cascada de CSS para decir: "Aplica este estilo solamente a los <span> que estén dentro de un <p>, que a su vez esté dentro de un elemento con la clase .card".