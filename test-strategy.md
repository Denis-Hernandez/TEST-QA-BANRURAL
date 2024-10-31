# Lista de Errores
## TypeError
Uncaught TypeError: guessSubmit.addeventListener is not a function

Linea 87: guessSubmit.addeventListener('click', checkGuess);
Correccion: guessSubmit.addEventListener('click', checkGuess);

## TypeError
Uncaught TypeError: lowOrHi is null

Linea 49: const lowOrHi = document.querySelector('lowOrHi');
Correccion: const lowOrHi = document.querySelector('.lowOrHi');

## TypeError
Uncaught TypeError: resetButton.addeventListener is not a function

Linea 95: resetButton.addeventListener('click', resetGame);
Correccion: resetButton.addEventListener('click', resetGame);

## Cantidad de intentos
La aplicacion finaliza despues de 5 intentos, se requiere que sean 10 intentos

Linea 46: const ATTEMPS = 5;
Correccion: const ATTEMPS = 10;

## Mensaje de Victoria o Derrota intercambiados
Al finalizar la aplicacion, aparece el mensaje incorrecto

Linea 65: lastResult.textContent = '!!!Pérdistes!!!';
Correccion: lastResult.textContent = 'Felicitaciones! adivinaste el número!';

Linea 70: lastResult.textContent = 'Felicitaciones! adivinaste el número!';
Correccion: lastResult.textContent = '!!!Pérdistes!!!';

## guessField permite cadenas de texto
guessField permite ingresar valores no numericos

Linea 31: <label for="guessField">Ingresa el número a adivinar: </label><input type="text" id="guessField" class="guessField">
Correccion: <label for="guessField">Ingresa el número a adivinar: </label><input type="text" id="guessField" class="guessField">

## Color de Mensajer es incorrecto
El mensaje de numero incorrecto aparece de color verde cuando debe de ser negro, mientras que el mensaje de numero correcto aparece negro mientras que debe de ser verde

Linea 66: lastResult.style.backgroundColor = 'black';
Correccion: lastResult.style.backgroundColor = 'green';

Linea 75: lastResult.style.backgroundColor = 'green';
Linea 75: lastResult.style.backgroundColor = 'black';