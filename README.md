# Notas Sección 3: Clean Code - Clases y Comentarios
___

#### Principio de Responsabilidad Única

Debe trabajar sobre una misma clase, no debe tener herencia y siempre debe priorizar la composición frente a la herencia. 

Malo ❌

![clase-b](/src/images/classes-b.png)

Bueno ✅

![clase-c](/src/images/classes-c.png)

Para obtener un resultado

![resultado](/src/images/ResultadoPrincipioRespUnica.PNG)


#### Estructura recomendada en una Clase

Se recomienda en una `clase`: 

a. Tener propiedades estáticas.
b. Propiedades públicas al último.

    public static domReady: boolean = false

Para un `método`: 

a. Empezando por los constructores estáticos.
b. Luego el constructor.
c. Seguidamente métodos estáticos.
d. Métodos privados después.
e. Resto de métodos de instancia ordenados de mayor a menor importancia. 
f. Getters y Setters al final. 

    static createInput( id: string ){
        return new HtmlElement(id, 'input');
    }

    constructor( id: string, type: string ) {
        this._id = id;
        this.type = type;
        this.updatedAt = Date.now();
    }

    setType( type: string ) {
        this.type = type;
        this.updatedAt = Date.now();
    }

    get id(): string {
        return this.id;
    }

#### Comentarios en el Código

Cuando usamos librerías de terceros, APIs, Frameworks, etc. nos encontraremos ante situaciones en las que escribir un comentario será mejor que dejar una solución compleja o un hack sin explicación. 

Los comentarios deberían de ser la excepción, no la regla. 

