<html>
<head>
	<title>Mensaje para Ximena</title>
	<style>
		body {
			background-color: #f0f0f0;
			font-family: Arial, sans-serif;
			color: #333;
			text-align: center;
		}
		.contenido {
			display: none;
		}
		.mostrar {
			display: block;
		}
	</style>
</head>
<body>
	<h2 id="mensaje-inicial"><b>Xime podrias volver a abrir este enlace en:</b></h2>
	<div id="cuenta-regresiva"></div>
	<div class="contenido" id="mensaje">
		<p>Ximena… de verdad que ese nombre estará presente para siempre en mi vida quisiera darte las gracias por estar ahi en todos los momentos buenos y malos y de verdad que el solo recordar todo lo que hiciste por mi me dan ganas de llorar te volviste alguien super especial en mi vida y no tengo el como agradecerte que fueras así conmigo de verdad, pero aun así quisiera despedirme porque tengo muchos asuntos que resolver pero no me querido ir sin antes darte las gracias por tantas cosas como cuando paso lo de mía cuando entre al volibol por ti gracias agradezco eso cada dia de mi vida y lo agradeceré siempre,ojala y en futuro donde ya logré cumplir mi sueño pueda tener la opción de volver a verte quisiera pedirte perdon por dejarte asi tan derrepente solo q ya no podia estar mas tiempo siendo yo si me vuelves a ver sere otra persona completamente diferente nuevamente losiento y t quisiera decir que esto no es un adios es un hasta pronto Eres mi hermana de otra madre gracias por todo</p>
	</div>
	<div id="gracias" style="display: none;">
		<h1>GRACIAS</h1>
	</div>
	<script>
		var fechaActual = new Date();
		var fechaMostrar = new Date('2024-08-03T10:00:00');
		var fechaOcultar = new Date('2024-08-05T17:00:00');
		var diferencia = fechaMostrar - fechaActual;
		var dias = Math.floor(diferencia / (1000 * 60 * 60 * 24));
		var horas = Math.floor((diferencia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
		var minutos = Math.floor((diferencia % (1000 * 60 * 60)) / (1000 * 60));
		var segundos = Math.floor((diferencia % (1000 * 60)) / 1000);
		document.getElementById('cuenta-regresiva').innerHTML = 'La página se abrirá en ' + dias + ' días, ' + horas + ' horas, ' + minutos + ' minutos y ' + segundos + ' segundos';
		var intervalo = setInterval(function() {
			diferencia -= 1000;
			dias = Math.floor(diferencia / (1000 * 60 * 60 * 24));
			horas = Math.floor((diferencia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
			minutos = Math.floor((diferencia % (1000 * 60 * 60)) / (1000 * 60));
			segundos = Math.floor((diferencia % (1000 * 60)) / 1000);
			document.getElementById('cuenta-regresiva').innerHTML = 'La página se abrirá en ' + dias + ' días, ' + horas + ' horas, ' + minutos + ' minutos y ' + segundos + ' segundos';
			if (diferencia <= 0) {
				clearInterval(intervalo);
				document.getElementById('mensaje-inicial').style.display = 'none';
				document.getElementById('mensaje').classList.add('mostrar');
				document.getElementById('cuenta-regresiva').style.display = 'none';
				var intervaloOcultar = setInterval(function() {
					var diferenciaOcultar = fechaOcultar - new Date();
					if (diferenciaOcultar <= 0) {
						clearInterval(intervaloOcultar);
						document.getElementById('mensaje').style.display = 'none';
						document.getElementById('gracias').style.display = 'block';
					}
				}, 1000);
			}
		}, 1000);
	</script>
</body>
</html>
