# PolyominosPuzzle02

### Fuentes
Desarrollado a partir de Polyomino Puzzle & Solver, codigo creado por Simon Hung
Utiliza (por ahora) [KineticJS](http://kineticjs.com).

### Descripcion
Pentominos Puzzle is a one player game. An opportunity for mental exercise and fun at the same time.
What does it consist of?
Hay un tablero cuadrado de 64 celdillas, 8 filas y ocho columnas. Cuatro celdillas se presentan ocupadas. El jugador debe colocar los doce pentominos de forma tal que cubran el resto del tablero.
Cada disposici�n diferentes de las celdillas ocupadas previamente da lugar a un problema. Los problemas son identificados num�ricamente. El jugador puede seguir esa secuencia num�rica o elegir los problemas arbitrariamente. Cada problema resuelto le suma puntos a su haber.
En caso de tener dificultades para encontrar la soluci�n el jugador puede solicitar ayuda. Esta consiste en la colocacion de una pieza por parte de la aplicaci�n y le restar� un punto al finalizar el problema.

### Generalidades
Espa�olizaci�n del original. La utlizar� como master para volver en caso de no funcionar las variantes que se vayan planteando.
El objetivo es crear un puzzle con pentominos en una tablero de 8 x 8 utilizando los doce pentominos y ocupando previamente 4 cuadraditos con cuadr�minos o cuatro cuadraditos independientes.

## Funcionamiento de la aplicaci�n
La ocupaci�n de celdas fijas, cudr�minos o cuadraditos separados, define diferentes problemas. Estos ser�n identificados / codificados para tener una secuencia fija para el jugador.
Los problemas se iran desarrollando secuencialmente (o siguiendo el orden que elija el jugador).
Se deber� llevar una tabla de registro donde se guarden los problemas resueltos por el jugador, los puntos obtenidos en cada caso y el total de puntos acumulados.
Tambi�n deber�a presentarse una tabla de clasificaci�n general de acuerdo a los puntos obtenidos.

En cada problema el jugador tendr� la posibilidad de solicitar ayuda. Por cada ayuda solicitada se descontar� un punto del total posible. Se podr�n solicitar hasta una m�ximo de x ayudas (por ejemplo: 8)
De forma tal que el jugador est� obligado a resolver, al menos, un problema m�s simple y justifique los puntos que obtenga.

Tabla de clasificaci�n general y tabla de logros personal.

El cuadr�mino o los cuadraditos estar�n programados previamente. Cada disposici�n da lugar a un problema diferente; tendr� asignado un n�mero o codigo. Creo que para los jugadores es mejor presentarlos ordenados numericamente.
El jugador podr� seguir la secuencia num�rica o elegir los numeros arbitrariamente.


### ----------------------------------
## Internals

Las celdas del tablero estan inicializadas con un cero.
gBoardState es la variable que guarda el estado de las celdas del tablero:
	0: libres
	99: ocupadas por la pieza 99


Las soluciones vienen en una clase ()generalmente identificada como result) que tiene
	totalAnswer
	elapsedTime
	solvedBoard: un arreglo de tres dimensiones: solvedBoard[totalAnswer][x][y]
	op


### Etapa preparacion del puzzle

Las funciones que siguen se ejecutan en la etapa preparatoria

####	function createBoard(boardX, boardY)		
	genera / crea un tablero nuevo con sus celdas inicializadas a cero

####	gBoardState = createBoard(SCREEN_BOARD_X, SCREEN_BOARD_Y); //external function
####	clearPolyInsertOrder(); //for hints
####	randomBlock(gBlockGroup); //external function
####	randomBlockStyle(gBlockGroup); //external function
####	randomPolyInitPos(gBlockGroup.length - numOfFixedBlocks);

####	clearFixedBlock();



En averiguacion:
Como se inserta cada poliomino. Donde queda registrado el poliomino utilizado y las celdas ocupadas???


### Referencias

*[Polyomino wiki](https://en.wikipedia.org/wiki/Polyomino)

*[Pentomino wiki](https://en.wikipedia.org/wiki/Pentomino)

*[Tetromino wiki](https://en.wikipedia.org/wiki/Tetromino)

## <a target="_blank" href="http://simonsays-tw.com/web/Polyomino/game/polyomino.html">Polyomino solver</a>

## <a target="_blank" href="http://simonsays-tw.com/web/Polyomino/game/pentomino.puzzle.html">Play Polyomino Puzzle game online</a>

### Referencias citadas en la aplicacion de Simon Hung

Window size and scrolling:
	http://www.howtocreate.co.uk/tutorials/javascript/browserwindow

Manejo de colores
	https://www.w3schools.com/colors/colors_picker.asp
	http://www.colorhexa.com/

block colors:
	http://en.wikipedia.org/wiki/File:Pentomino_Puzzle_Solutions.svg	  

just for fixed: chrome sets cursor to text while dragging, why?
	http://stackoverflow.com/questions/2745028/chrome-sets-cursor-to-text-while-dragging-why

Solucion problema poliominos:
	http://godel.hws.edu/xJava/PentominosSolver/index.html

Fuentes del pentomino solver en java:
	http://godel.hws.edu/xJava/PentominosSolver/source/

clear select options reference:
	http://www.somacon.com/p542.php


### Versiones
#### Version 0.0.1	-	19/6/2018
#### Version 0.0.2	-	21/6/2018
	Iniciamos la conversi�n a un puzzle de pentominos en tablero de 8 x 8.

#### Version 0.1.0	-	09/7/2018
	Primer version funcional para resolver el problema een tablero 8 x 8.

#### Version 0.2.0	-	12/7/2018
	El objetivo ahora es desarrollar una aplicacion que corra en windows y en Android

#### Version 0.2.1	-	19/9/2018
	Para verificar funcionamiento en un dispositivo touch.
	Las piezas se arrastran pero no se pueden girar ni voltear.

#### Version 0.2.2	-	25/9/2018
	Se incorporan botones para girar y voltear piezas.

### Corecciones a realizar
Agrandar tamaño tablero. Experimentar metodos de SUMADO
Forzar posicion apaisada
---	Reemplazar el 'operator object' con un boton que produzca resultados similares.

Corregir:
	no toma indicaciones de giro y volteo en la pantalla del celular.
	Detalles menores de iconos, texto descripcion
	Incorporar secuencia de problemas a resolver
	ayudas mediante colocacion de pieza en su lugar, limite de ayudas, etc.
	Tablas de logros y clasificaciones.
	Pantalla de inicio con opciones de jugar, ayudas, acerca de, y otros.


	Corregido: Detectar resultado exitoso y avisar. Actualmente, al colocar la ultima pieza correcta, dice no haber solucion.

	9/7/2018
		Consegui hacer funcionar la colocacion de piezas con ayuditas.

	8/7/2018
		No puedo hacer detectar el cuadromino fijo.
		auto-Sugerencia: insertarlo de forma similar a
			function addFixedBlock2Layer(op, numOfFixedBlocks)
		en lugar de la forma actual

	6/7/2018
		Debo intentar manejar la posicion del cuadromino de forma tal que
		detecte el lugar como ocupado y no permita que lo ocupe un pentomino.

	5/7/2018
		Hay que crear estilos de bloque para el cuadromino fijo (!?)
		Esto es para que funcione el buscador de soluciones y ayuditas.

	2/7/2018
	Pensar en resolver la insercion de cuadróminos fijos de la siguiente forma:
		el cuadromino fijo a insertar se agrega al grupo de poliomonios
		se establece en 1 la cantidad de poliominos fijos
		adaptar la <<< function addFixedBlock2Layer(op, numOfFixedBlocks) >>> para  asegurarse que tome el cuadromino.
		verificar

	linea 433, he logrado insertar el cuadromino. Ahora falta pintar las celditas ocupadas.


	Elimino todas las acciones vinculadas a demo; no es lo que quiero hacer

	23/6/2018
		Habria que agregar un style a wCuadromGroup... Por ahora no.

	18/6/2018
		Adecuacion de Willie Verger para un rompecabezas con pentominos
		wpentomino.puzzle.js
		descripcion de variables y funciones del script

	include files: polyomino5.js, polySolution.js, animate.js, polyDemo.js

	v1.3
	12/16/2014 - (1) Bug fixed for Chrome 38.x
				  (1.1) remark "context.stroke(context);"
				  (1.2) change lib version to kinetic-v4.4.3

	v1.2
	07/10/2013 - (1) Bug fixed for Chrome 28.0.1500.71 m
				  change context.fill(context) to context.fill()

	v1.1
	04/04/2013 - (1) For work with Chrome 26.0.1410.43m move to kineticJS 4.4.0
			  (2) Support tranditional chinese

	v1.0
	11/05/2012 - recover play mode info after demo back and change board color

	11/03/2012 - add demo function
	10/26/2012 - create by Simon Hung

	
