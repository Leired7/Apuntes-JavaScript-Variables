# Variables

En programación, las variables son como cajas que guardan algún tipo de información.

Tú eliges el nombre que quieres darle a cada variable, a cada caja con información. Siempre tienes que procurar ponerle un nombre que dé información sobre el contenido que tiene o su función en nuestro código. Por ejemplo, si nos vamos a mudar de casa y estamos metiendo todos los utensilios de cocina en una misma caja, a esta caja le escribiríamos por fuera algo como "cocina" o "utensilios de cocina" para poder localizarla más fácil entre todas nuestras cajas. No se nos ocurriría ponerle "cosas del baño" o "comida del perro" porque no sería coherente con lo que hay dentro de ella. En la programación ocurre igual con las variables.

Para escribir una variable, primero tenemos que indicar qué tipo de variable va a ser. En JavaScript, hay tres tipos de variable: var, let y const.

## Tipos de variables
```var``` -- Es la forma antigua de declarar una variable. Ya no se utiliza y no deberíais utilizarla.

```let``` -- Es la forma correcta de declarar una variable.

```const``` -- Declara una variable que es inmutable, es decir, que no puede cambiar de valor una vez declarada.

## Declarar una variable

Para declarar una variable, tenemos que indicar el tipo de variable, luego el nombre de la variable y luego el valor que le queremos dar. 

Por ejemplo:
```javascript
var isOn = false;
let numberOfDogs = 2;
const name = "Arturo";
```

Ahora, tenemos una variable declarada que se llama ```isOn``` y es igual a ```false```, otra que se llama ```numberOfDogs``` y es igual al número ```2```, y otra variable declarada ```const``` que es inmutable y que contiene el string ```"Arturo"```.

Solo hace falta declarar la variable una vez en nuestro programa. Una vez declarada, cada vez que queramos tener acceso a esa misma variable sólo haría falta llamarla.

Por ejemplo:

```javascript
let numberOfDogPictures = 5;
let totalPictures = numberOfDogPictures + 25;
console.log(totalPictures); // 30
```

Paso a paso, lo que hemos hecho en este ejemplo es lo siguiente:

1. Declarar una variable ```let``` con nombre ```numberOfDogPictures``` y con un valor de ```5```.

2. Declarar una variable ```let``` con nombre ```totalPictures```. Esta variable será igual al valor de ```numberOfDogPictures``` (que en este caso, es ```5```) + ```25```. 

_Nótese cómo no hemos vuelto a poner ```let``` antes de ```numberOfDogPictures``` porque ya declaramos la variable en la línea anterior; con declarar la variable una vez es suficiente._

3. Imprimir en la consola el contenido de la variable ```totalPictures```, que será ```30```.

## Diferencias entre los tipos de variables

### Diferencias entre const y var/let

```const``` se diferencia con ```var``` y ```let``` en que no puede mutar, es decir, no puede cambiar de valor una vez le asignas un valor.

Veamos el siguiente ejemplo:

```javascript
let mainBackground = 'red';
mainBackground = 'blue';

console.log(mainBackground); // blue


const virtualReality = 'activated';
virtualReality = 'deactivated' // ERROR: Assignment to constant variable.
```

En el primer ejemplo no hubo ningún problema y pudimos re-asignar un valor nuevo a la variable ```mainBackground```. Sin embargo, si ejecutamos las últimas dos líneas de código y abrimos la consola, veremos que aparece el fallo ```Assignment to constant variable.```. Esto es debido a que, efectivamente, no podemos re-asignar un valor a una variable que declaramos con la palabra ```const```. Es constante; is inmutable.

### Diferencias entre let/const y var

La diferencia entre ```var``` y ```const``` / ```let``` reside en el alcance de las variables a nivel de scope (alcance).

```let``` y ```const``` nos permiten declarar variables limitando su alcance al bloque, expresión o declaración en que está siendo declarado. ```var```, en cambio, tiene un alcance global independientemente de si es declarada dentro de un bloque o no.

Veámoslo con tres ejemplos:

```javascript
  if (true) {
    var x = 55;
    console.log(x);  // 55
  }
  console.log(x);  // 55
```
Como podemos ver en este ejemplo, al imprimir ```x``` con ```console.log``` dentro del scope del ```if statement```, se muestra el contenido de ```x``` en la consola. Y también, si hacemos la llamada de ```console.log``` fuera del scope del ```if statement``` nos mostrará efectivamente el mismo valor en la consola. Esto es debido a que ```var``` tiene un alcance global y, a pesar de haber sido declarada dentro de un ```if statement```, sigue teniendo el mismo valor fuera de este scope.

En cambio, en este otro ejemplo:

```javascript
  if (true) {
    let y = 10;
    console.log(y);  // 10
  }
  console.log(y);  // Uncaught ReferenceError: y is not defined
```
En este caso, el primer ```console.log``` sí nos lo mostraría en la consola correctamente, mostrando el valor de ```y```. Pero en el segundo caso, nos da un error. Nos dice que ```y is not defined```. Esto es debido a que la variable ```y```, que hemos declarado con ```let```, solo existe dentro del scope en el que ha sido declarada. En otras palabras: ```y``` solo existe dentro del ```if statement```. Por eso cuando intentamos imprimirla en la consola fuera del ```if statement``` nos marca como que la variable no existe.

Con ```const``` ocurriría lo mismo:

```javascript
  if (true) {
    const z = 'Wild Code School';
    console.log(z);  // Wild Code School
  }
  console.log(z);  // Uncaught ReferenceError: z is not defined
```
Si imprimimos ```z``` fuera del scope del ```if statement``` te saldrá un error indicando que la variable no existe. Porque, al igual que en ```let```, estas variables solo existen dentro del scope donde han sido declaradas. 
