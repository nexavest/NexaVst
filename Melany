<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Cuenta Regresiva - Melany Bajana</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-family: Arial, sans-serif;
  color: white;
  background: url("fon.jpg") center/cover no-repeat;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.5);
}

.contenido {
  position: relative;
  z-index: 2;
  width: 90%;
  max-width: 650px;
}

.titulo {
  font-size: 45px;
  font-weight: bold;
  text-transform: uppercase;
  margin-bottom: 30px;
}

.owner {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
}

.nombre {
  font-size: 35px;
  font-weight: bold;
  margin-bottom: 35px;
}

.contador {
  display: flex;
  justify-content: center;
  gap: 12px;
}

.caja {
  min-width: 105px;
  padding: 20px 12px;
  border-radius: 15px;
  background: rgba(255,255,255,0.15);
  border: 1px solid rgba(255,255,255,0.35);
  backdrop-filter: blur(8px);
}

.numero {
  display: block;
  font-size: 42px;
  font-weight: bold;
}

.etiqueta {
  display: block;
  margin-top: 6px;
  font-size: 13px;
  text-transform: uppercase;
}

.terminado {
  display: none;
  font-size: 28px;
  font-weight: bold;
  margin-top: 25px;
}

@media (max-width: 500px) {

  .titulo {
    font-size: 31px;
  }

  .nombre {
    font-size: 28px;
  }

  .caja {
    min-width: 85px;
    padding: 15px 8px;
  }

  .numero {
    font-size: 32px;
  }
}
</style>
</head>

<body>

<div class="contenido">

  <div class="titulo">
    Cuenta Regresiva
  </div>

  <div class="owner">
    BONUS OWNER
  </div>

  <div class="nombre">
    Melany Bajana
  </div>

  <div class="contador" id="contador">

    <div class="caja">
      <span class="numero" id="horas">03</span>
      <span class="etiqueta">Horas</span>
    </div>

    <div class="caja">
      <span class="numero" id="minutos">00</span>
      <span class="etiqueta">Minutos</span>
    </div>

    <div class="caja">
      <span class="numero" id="segundos">00</span>
      <span class="etiqueta">Segundos</span>
    </div>

  </div>

  <div class="terminado" id="terminado">
    ¡La cuenta regresiva ha terminado!
  </div>

</div>

<script>

let tiempo = 3 * 60 * 60;

function actualizar() {

  let horas = Math.floor(tiempo / 3600);
  let minutos = Math.floor((tiempo % 3600) / 60);
  let segundos = tiempo % 60;

  document.getElementById("horas").textContent =
    String(horas).padStart(2, "0");

  document.getElementById("minutos").textContent =
    String(minutos).padStart(2, "0");

  document.getElementById("segundos").textContent =
    String(segundos).padStart(2, "0");

  if (tiempo <= 0) {

    clearInterval(cuentaRegresiva);

    document.getElementById("contador").style.display = "none";
    document.getElementById("terminado").style.display = "block";

    return;
  }

  tiempo--;
}

actualizar();

const cuentaRegresiva = setInterval(actualizar, 1000);

</script>

</body>
</html>
