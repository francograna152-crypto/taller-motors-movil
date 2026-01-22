<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Taller Motors Móvil</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body{
margin:0;
font-family:Arial;
background:#0b0b0b;
color:white;
text-align:center;
}
.screen{display:none;padding:40px}
.active{display:block}
button{
background:#e10600;
color:white;
border:none;
padding:15px 30px;
margin:10px;
font-size:18px;
border-radius:10px;
}
input{
width:90%;
max-width:300px;
padding:12px;
margin:10px;
border-radius:8px;
border:none;
}
</style>
</head>

<body>

<div class="screen active" id="s1">
<h1>🏍️ Taller Motors Móvil</h1>
<p>Servicio mecánico a domicilio</p>
<button onclick="go(2)">Empezar</button>
</div>

<div class="screen" id="s2">
<h2>¿Qué deseas hacer?</h2>
<button onclick="go(3)">Agendar cita</button>
<button onclick="alert('Comentarios próximamente ⭐')">Ver comentarios</button>
</div>

<div class="screen" id="s3">
<h2>Tipo de moto</h2>
<button onclick="selectMoto('Naked')">Naked</button>
<button onclick="selectMoto('Trabajo')">Trabajo</button>
<button onclick="selectMoto('Semiautomática')">Semiautomática</button>
<button onclick="selectMoto('Automática')">Automática</button>
<button onclick="selectMoto('Doble propósito')">Doble propósito</button>
</div>

<div class="screen" id="s4">
<h2>Agendar cita</h2>

<form action="mailto:francograna152@gmail.com" method="post" enctype="text/plain">
<input type="text" name="Nombre" placeholder="Nombre" required>
<input type="tel" name="Teléfono" placeholder="Teléfono" required>
<input type="text" name="Ubicación" placeholder="Ubicación" required>
<input type="email" name="Correo" placeholder="Correo" required>

<input type="hidden" id="moto" name="Tipo de moto">

<button type="submit">Enviar cita</button>
</form>
</div>

<script>
function go(n){
document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
document.getElementById('s'+n).classList.add('active');
}
function selectMoto(m){
document.getElementById('moto').value=m;
go(4);
}
</script>

</body>
</html>
