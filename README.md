<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cuenta Regresiva - Melany Bajana</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      background: url("fon.jpg") center center / cover no-repeat;
      color: white;
      text-align: center;
    }

    .overlay {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.45);
    }

    .container {
      position: relative;
      z-index: 1;
      width: 90%;
      max-width: 600px;
      padding: 35px 20px;
    }

    .titulo {
      font-size: 42px;
      font-weight: 800;
      letter-spacing: 2px;
      margin-bottom: 35px;
      text-transform: uppercase;
    }

    .propietario {
      font-size: 21px;
      margin-bottom: 12px;
      font-weight: 600;
    }

    .nombre {
      font-size: 34px;
      font-weight: 800;
      margin-bottom: 35px;
    }

    .contador {
      display: flex;
      justify-content: center;
      gap: 12px;
      flex-wrap: wrap;
    }

    .tiempo {
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(8px);
      border: 1px solid rgba(255,255,255,0.3);
      border-radius: 15px;
      padding: 18px 15px;
      min-width: 105px;
    }

    .numero {
      display: block;
      font-size: 42px;
      font-weight: 800;
    }

    .etiqueta {
      display: block;
      font-size: 14px;
      margin-top: 5px;
      text-transform: uppercase;
    }

    .finalizado {
      font-size: 28px;
      font-weight: bold;
      display: none;
      margin-top: 25px;
    }

    @media (max-width: 500px) {
      .titulo {
        font-size: 30px;
      }

      .nombre {
        font-size: 27px;
      }

      .tiempo {
        min-width: 85px;
        padding: 14px 10px;
      }

      .numero {
        font-size: 32px;
      }
    }
  </style>
</head>

<body>

  <div class="overlay"></div>

  <div class="container">

    <div class="titulo">Cuenta Regresiva</div>

    <div class="propietario">BONUS OWNER</div>
    <div class="nombre">Melany Bajana</div>

    <div class="contador" id="contador">

      <div class="tiempo">
        <span class="numero" id="horas">03</span>
        <span class="etiqueta">Horas</span>
      </div>

      <div class="tiempo">
        <span class="numero" id="minutos">00</span>
        <span class="etiqueta">Minutos</span>
      </div>

      <div class="tiempo">
        <span class="numero" id="segundos">00</span>
        <span class="etiqueta">Segundos</span>
      </div>

    </div>

    <div class="finalizado" id="finalizado">
      ¡La cuenta regresiva ha terminado!
    </div>

  </div>

  <script>
    // 3 horas en milisegundos
    let tiempoRestante = 3 * 60 * 60 * 1000;

    const horas = document.getElementById("horas");
    const minutos = document.getElementById("minutos");
    const segundos = document.getElementById("segundos");
    const contador = document.getElementById("contador");
    const finalizado = document.getElementById("finalizado");

    function actualizarContador() {

      if (tiempoRestante <= 0) {
        tiempoRestante = 0;

        horas.textContent = "00";
        minutos.textContent = "00";
        segundos.textContent = "00";

        contador.style.display = "none";
        finalizado.style.display = "block";

        clearInterval(intervalo);
        return;
      }

      const totalSegundos = Math.floor(tiempoRestante / 1000);

      const h = Math.floor(totalSegundos / 3600);
      const m = Math.floor((totalSegundos % 3600) / 60);
      const s = totalSegundos % 60;

      horas.textContent = String(h).padStart(2, "0");
      minutos.textContent = String(m).padStart(2, "0");
      segundos.textContent = String(s).padStart(2, "0");

      tiempoRestante -= 1000;
    }

    actualizarContador();

    const intervalo = setInterval(actualizarContador, 1000);
  </script>

</body>
</html>
