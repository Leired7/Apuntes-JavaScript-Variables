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
console.log(totalPictures)  // 30
```

Paso a paso, lo que hemos hecho en este ejemplo es lo siguiente:

1. Declarar una variable ```let``` con nombre ```numberOfDogPictures``` y con un valor de ```5```.

2. Declarar una variable ```let``` con nombre ```totalPictures```. Esta variable será igual al valor de ```numberOfDogPictures``` (que en este caso, es ```5```) + ```25```. 

_Nótese cómo no hemos vuelto a poner ```let``` antes de ```numberOfDogPictures``` porque ya declaramos la variable en la línea anterior; con declarar la variable una vez es suficiente._

3. Imprimir en la consola el contenido de la variable ```totalPictures```, que será ```30```.
