<!DOCTYPE html>
<html>
	<head>
		<script>
	
			function v(val)//display clicked buttons
			{
				document.getElementById("d").value+=val;
			}
			function e() //evaluate
			{ 
				try 
				{ 
					c(eval(document.getElementById("d").value)) 
				} 
				catch(e) 
				{
					c('Error') 
				} 
			}  
		</script>
		<style>
			* {
				margin: 0;
				padding: 0;
				box-sizing: border-box;
				
				
				font: bold 14px Arial, sans-serif;
			}

			

			/* A nice BG gradient */
			html {
				height: 100%;
				background: white;
				background: radial-gradient(circle, #fff 20%, #ccc);
				background-size: cover;
			}

			/* Using box shadows to create 3D effects */
			#calculator {
				width: 325px;
				height: auto;
				
				margin: 100px auto;
				padding: 20px 20px 9px;
				
				background: #9dd2ea;
				background: linear-gradient(#9dd2ea, #8bceec);
				border-radius: 3px;
				box-shadow: 0px 4px #009de4, 0px 10px 15px rgba(0, 0, 0, 0.2);
			}

			/* Top portion */
			.top .clear {
				float: left;
			}

			/* Inset shadow on the screen to create indent */
			.top .screen {
				height: 40px;
				width: 212px;
				
				float: right;
				
				padding: 0 10px;
				
				background: rgba(0, 0, 0, 0.2);
				border-radius: 3px;
				box-shadow: inset 0px 4px rgba(0, 0, 0, 0.2);
				
				/* Typography */
				font-size: 17px;
				line-height: 40px;
				color: white;
				text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
				text-align: right;
				letter-spacing: 1px;
			}

			/* Clear floats */
			.keys, .top {overflow: hidden;}

			/* Applying same to the keys */
			.keys input, .top .clear {
				float: left;
				position: relative;
				top: 0;
				
				cursor: pointer;
				
				width: 66px;
				height: 36px;
				
				background: white;
				border-radius: 3px;
				box-shadow: 0px 4px rgba(0, 0, 0, 0.2);
				
				margin: 0 7px 11px 0;
				
				color: #888;
				line-height: 36px;
				text-align: center;
				
				/* prevent selection of text inside keys */
				user-select: none;
				
				/* Smoothing out hover and active states using css3 transitions */
				transition: all 0.2s ease;
			}

			/* Remove right margins from operator keys */
			/* style different type of keys (operators/evaluate/clear) differently */
			.keys .operator {
				background: #FFF0F5;
				margin-right: 0;
			}
			

			.keys .eval {
				background: #f1ff92;
				box-shadow: 0px 4px #9da853;
				color: #888e5f;
			}

			.top .clear {
				background: #ff9fa8;
				box-shadow: 0px 4px #ff7c87;
				color: white;
			}

			/* Some hover effects */
			.keys input:hover {
				background: #9c89f6;
				box-shadow: 0px 4px #6b54d3;
				color: white;
			}

			.keys .eval:hover {
				background: #abb850;
				box-shadow: 0px 4px #717a33;
				color: #ffffff;
			}

			.top .clear:hover {
				background: #f68991;
				box-shadow: 0px 4px #d3545d;
				color: white;
			}

			/* Simulating "pressed" effect on active state of the keys by removing the box-shadow and moving the keys down a bit */
			.keys input:active {
				box-shadow: 0px 0px #6b54d3;
				top: 4px;
			}

			.keys .eval:active {
				box-shadow: 0px 0px #717a33;
				top: 4px;
			}

			.top .clear:active {
				top: 4px;
				box-shadow: 0px 0px #d3545d;
			}
			input:focus{
				outline: 0;
			}


		</style>
	</head>

	<body>
		<div id="calculator">
			<!-- Screen and clear key -->
			<div class="top">
				<input type="button" style="border-style:none;" class="clear" value="C" onclick='c("")'>
				<div><input class="screen" style="border-style:none;" type="text" size="18" id="d"></div>
			</div>
			<div class="keys">
				
				
				<input type="button" style="border-style:none;"  value="7" onclick='v("7")'>
				<input type="button" style="border-style:none;"  value="8" onclick='v("8")'>
				<input type="button" style="border-style:none;"  value="9" onclick='v("9")'>
				<input type="button" style="border-style:none;" class="operator" value="/" onclick='v("/")'>
				
				<input type="button" style="border-style:none;"  value="4" onclick='v("4")'>
				<input type="button" style="border-style:none;" value="5" onclick='v("5")'>
				<input type="button" style="border-style:none;"  value="6" onclick='v("6")'>
				<input type="button" style="border-style:none;" class="operator" value="*" onclick='v("*")'>
				
				
				<input type="button" style="border-style:none;"  value="1" onclick='v("1")'>
				<input type="button" style="border-style:none;" value="2" onclick='v("2")'>
				<input type="button" style="border-style:none;"  value="3" onclick='v("3")'>
				<input type="button" style="border-style:none;"  class="operator" value="-" onclick='v("-")'>
				
				<input type="button" style="border-style:none;" value="." onclick='v(".")'>
				<input type="button" style="border-style:none;"  value="0" onclick='v("0")'>
				<input type="button" style="border-style:none;"  class="eval" value="=" onclick='e()'>
				<input type="button" style="border-style:none;" class="operator" value="+" onclick='v("+")'>
			</div>
		</div>
	</body>
</html>
