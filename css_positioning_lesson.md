##Codehike Lesson

#CSS Positioning

* The "normal flow" of web page determines how elements are displayed by default
* For example, `block` elements go below the previous element, where as `inline` elements go straight after, if there is room.
* There are CSS properties that can alter that behaviour and are therefore useful in designing layouts, for example`float` and `position`.

1. Float and Clear (10 mins)

	* `float` property removes an element from the normal flow and places it to it's left or right side. Other non-floating elements will fit around it.
	* Note that the dimensions of a container div will be defined by it's children. However, floating children are excluded.
	* The `clear` property stops an element from fitting around floated elements and will move the element below any floated elements.

	index.html

		<!DOCTYPE html>
		<html>
		<head>
			<meta charset="utf-8"/>
			<link rel="stylesheet" type="text/css" href="style.css">
		</head>
		<body>
			<div id="container">

				<!--Part 2-->
				<div id="square"></div>

				<div id="text">Lorem ipsum dolor sit amet, audiam efficiendi pri eu, ei nam saepe civibus vulputate, labitur ocurreret an sit. Qui et iusto nusquam, at mundi choro consul pro. Ne est tale integre disputationi. Vix nisl nibh novum ea, vidit modus euripidis ei has, odio labitur assueverit cu eum. Fuisset necessitatibus cum eu, te usu ipsum maiorum.</div>

				<!--Part 4-->
				<div class="clearfix"></div>

			</div>
			<script src="script.js"></script>
		</body>
		</html>

	style.css

		#container {
			width: 300px;
			background-color: white;
			border: 1px solid black;
		}

		/*Part 2*/
		#square {
			width: 100px;
			height: 100px;
			background-color: blue;
			float: left;
		}

		/*Part 3*/
		#text {
			width: 100px;
			float: left;
			border: 1px solid black;
		}

		/*Part 4*/
		.clearfix {
			clear: both;
		}


	Exercise (5 mins): Make a page layout with: header, three columns, footer

	Starting code:

	index.html

		<!DOCTYPE html>
		<html>
		<head>
			<meta charset="utf-8"/>
			<link rel="stylesheet" type="text/css" href="style.css">
		</head>
		<body>
			<div id="container">
				<div id="header">
				Lorem ipsum dolor sit amet, audiam efficiendi pri eu, ei nam saepe civibus vulputate, labitur ocurreret an sit.
				</div>
				<div id="col-left">
				Lorem ipsum dolor sit amet, audiam efficiendi pri eu, ei nam saepe civibus vulputate, labitur ocurreret an sit. pri eu, ei nam saepe civibus vulputate, labitur ocurreret an sit. Qui et iusto nusquam, at mundi choro consul pro. Ne est tale integre disputationi.
				</div>
				<div id="col-right">Lorem ipsum dolor sit amet, audiam efficiendi.</div>
				<div id="footer">Lorem ipsum dolor sit amet, audiam efficiendi pri eu, ei nam saepe civibus vulputate.</div>
			</div>
			<script src="script.js"></script>
		</body>
		</html>

	style.css

		#container {
			background-color: white;
			border: 1px solid black;
		}

		#header {
			background-color: lightblue
		}

		#col-left {
			background-color: pink;
		}

		#col-right{
			background-color: lightgreen;
		}

		#footer {
			background-color: lightyellow;
		}

	Solution:

	* Set column width to 50%
	* Float columns
	* Add a clearfix div with clear: both

2. Position: static, fixed, relative, absolute (10 mins)

	* `relative` positioning moves an element relative to where it would have been if it had the default `static` positioning. You can now use properties like `top`, `bottom`, `left`, `right` to nudge the element.
	* Absolute positioning removes an element from the flow and positions it relative to the first parent container with a `relative` position (otherwise falls back to the `html` tag)
	* `z-index` specifies the stack order of an element, but on works on non-static positioned elements.

	index.html

		<!DOCTYPE html>
		<html>
		<head>
			<meta charset="utf-8"/>
			<link rel="stylesheet" type="text/css" href="style.css">
		</head>
		<body>
			<div id="container">
				
				<div id="text">Lorem ipsum dolor sit amet, audiam efficiendi pri eu, ei nam saepe civibus vulputate, labitur ocurreret an sit. Qui et iusto nusquam, at mundi choro consul pro. Ne est tale integre disputationi. Vix nisl nibh novum ea, vidit modus euripidis ei has, odio labitur assueverit cu eum. Fuisset necessitatibus cum eu, te usu ipsum maiorum.
				</div>

				<!--Part 2-->
				<div id="square"></div>

			</div>
			<script src="script.js"></script>
		</body>
		</html>


	style.css

		#container {
			width: 300px;
			height: 300px;
			background-color: white;
			border: 1px solid black;
			position: relative;
			left: 20px;
		}

		<!--Part 2-->
		#square {
			width: 100px;
			height: 100px;
			background-color: blue;
			position: absolute;
			top: 20px;
		}

		<!--Part 3-->
		#text {
			position:relative;
			z-index: 1;
		}


	Exercise: (5 mins):

	* Add two more squares to the container
	* Give them different colors, dimensions, positions, z-index
	* Get them to go above and below each other and the text
