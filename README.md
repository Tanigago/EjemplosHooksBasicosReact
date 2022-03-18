# Ejemplos principales HOOKs

1. Clonar
Dentro de la carpeta del proyecto:
2. `npm install`
3. `npm start`

## useRef
Nos permite conservar valores entre renderizaciones del componente.

En el ejemplo podemos comprobar que la variable `contador` no conserva su valor cuando el componente cambia la información que muestra en pantalla, mietras que la referencia `contadorRef` sí lo hace.

Creación:
```js
const nombreRef = useRef(valorInicial);
```
Acceso:
```js
const c = nombreRef.current;
```
Modificación:
```js
nombreRef.current = nuevoValor;
```
## useState
Permite conservar un valor entre renderizaciones del componente y además redibuja el componente cada vez que el valor cambie.

Creación:
```js
const [ nombreState, nombreSetterState ] = useState(valorInicial);
```
Acceso:
```js
const c = nombreState;
```
Modificación:
```js
nombreSetterState(nuevoValor);
```
### useEffect
Permite controlar la ejecución de un bloque de código en relación al redibujo del compomente. En todos los casos, el bloque de codigo a controlar se ejecuta cuando el componente se crea en la pantalla.
```js
useEffect (
    ()=>{
        // Aquí va el código que pretendemos controlar
        // Simpre se ejecuta una vez en la creación
        // del compomente en pantalla
        // Adicionalmente se puede ejecutar al cambiar props o
        // states indicados en el array siguiente
        return ()=>{
            // POdemos añadir un return con una función.
            // El contenido de la función sólo se
            // ejecutará al destruirse el compomente.
        }
    },
    [prop1, prop2, state1, state2, ...]
    // El cambio del valor de los props
    // y states del array harán que se ejecute 
    // Nuevamente el código de la primera
    // funcion del useEffect.
    // Si el array está vacío no se
    // ejecutará nuevamente el código
    // tras la creación del componente.

)
```
### useContext
