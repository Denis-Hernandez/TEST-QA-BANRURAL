# Lista de Errores
## TypeError
Uncaught TypeError: guessSubmit.addeventListener is not a function

* Linea 87: guessSubmit.addeventListener('click', checkGuess);
* Correccion: guessSubmit.addEventListener('click', checkGuess);

## TypeError
Uncaught TypeError: lowOrHi is null

* Linea 49: const lowOrHi = document.querySelector('lowOrHi');
* Correccion: const lowOrHi = document.querySelector('.lowOrHi');

## TypeError
Uncaught TypeError: resetButton.addeventListener is not a function

* Linea 95: resetButton.addeventListener('click', resetGame);
* Correccion: resetButton.addEventListener('click', resetGame);

## Cantidad de intentos
La aplicacion finaliza despues de 5 intentos, se requiere que sean 10 intentos

* Linea 46: const ATTEMPS = 5;
* Correccion: const ATTEMPS = 10;

## Mensaje de Victoria o Derrota intercambiados
Al finalizar la aplicacion, aparece el mensaje incorrecto

* Linea 65: lastResult.textContent = '!!!Pérdistes!!!';
* Correccion: lastResult.textContent = 'Felicitaciones! adivinaste el número!';

* Linea 70: lastResult.textContent = 'Felicitaciones! adivinaste el número!';
* Correccion: lastResult.textContent = '!!!Pérdistes!!!';

## guessField permite cadenas de texto
guessField permite ingresar valores no numericos

* Linea 31: <label for="guessField">Ingresa el número a adivinar: </label><input type="text" id="guessField" class="guessField">
* Correccion: <label for="guessField">Ingresa el número a adivinar: </label><input type="text" id="guessField" class="guessField">

## Color de Mensajer es incorrecto
El mensaje de numero incorrecto aparece de color verde cuando debe de ser negro, mientras que el mensaje de numero correcto aparece negro mientras que debe de ser verde

* Linea 66: lastResult.style.backgroundColor = 'black';
* Correccion: lastResult.style.backgroundColor = 'green';

* Linea 75: lastResult.style.backgroundColor = 'green';
* Correccion: lastResult.style.backgroundColor = 'black';

## Numero aleatorio no cumple con las instrucciones
Al imprimir en consola la variable randomNumber se visualiza que el numero no es entero y varia de numeros del 1 al 10 cuando debe de ser del 1 al 100

* Linea 44: let randomNumber = Math.random() * 10;
* Correccion: let randomNumber = Math.floor( Math.random() * 100 );

## guessField permite ingresar valores no Enteros
El campo guessField permite ingresar cadenas de texto y valores decimales, se recomenda cambiar el tipo de input a Number y agregar un script que no permita el ingreso de este tipo de valores

* Linea 31:  ``` javascript<input type="text" id="guessField" class="guessField"> ```
* correccion: <input type="number" min="1" max="100" id="guessField" class="guessField" oninput="this.value = this.value.replace(/[^0-9]/g, ''); this.value = Math.min(Math.max(this.value, 1), 100);">

## guessField permite ingresar valores vacios
Se recomienda agregar una validacion en la funcion checkGuess que verifique si el valor evaluado es vacio, Ejemplo

```javascript
function checkGuess() {
    if(guessField.value.length > 0 ){
        //ejecucion del codigo de checkGuess
    }
}
```

## El valor de guessField no es Convertido a entero
La comparacion userGuess === randomNumber hace una comparacion adicional de tipo de dato, al extraer el valor ingresado por el usuario, este se extrae como un valor del tipo String, se recomienta hacer un parseInt a userGuess o reducir la calidacion a == para que javascript no compare el tipo de dato.

* Linea 64:
    -```javascript if(userGuess === randomNumber) ```
* Correccion:
    -```javascript if(userGuess == randomNumber) ``` o ```if(parseInt(userGuess) == randomNumber) ```