# cumple-Daniela
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Invitación de Daniela</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background-color: #f3e8ff;
      color: #4b0082;
      text-align: center;
    }
    .container {
      padding: 20px;
    }
    h1 {
      font-size: 3em;
      margin-top: 30px;
    }
    .countdown {
      font-size: 2em;
      margin: 20px 0;
    }
    .rsvp input, .rsvp button {
      padding: 10px;
      font-size: 1em;
      margin: 5px;
      border-radius: 10px;
      border: none;
    }
    .rsvp button {
      background-color: #d8b4f8;
      cursor: pointer;
    }
    footer {
      margin-top: 40px;
      font-size: 0.9em;
      color: #6b21a8;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>¡Daniela cumple 7 años!</h1>
    <p>Estás invitado a una celebración muy especial 🎉</p>

    <div class="countdown" id="countdown">
      Cargando cuenta regresiva...
    </div>

    <h2>📍 Detalles del evento</h2>
    <p><strong>Fecha:</strong> Próximamente</p>
    <p><strong>Hora:</strong> Próximamente</p>
    <p><strong>Lugar:</strong> Próximamente</p>

    <h2>💌 Confirma tu asistencia</h2>
    <div class="rsvp">
      <input type="text" placeholder="Tu nombre" id="nombre">
      <button onclick="confirmarAsistencia()">Confirmar</button>
      <p id="respuesta"></p>
    </div>

    <footer>
      Con cariño, Daniela 💜
    </footer>
  </div>

  <script>
    // Fecha del evento (ajusta cuando tengas la fecha real)
    const evento = new Date("2025-04-20T15:00:00").getTime();

    const cuentaRegresiva = setInterval(function() {
      const ahora = new Date().getTime();
      const distancia = evento - ahora;

      const dias = Math.floor(distancia / (1000 * 60 * 60 * 24));
      const horas = Math.floor((distancia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutos = Math.floor((distancia % (1000 * 60 * 60)) / (1000 * 60));
      const segundos = Math.floor((distancia % (1000 * 60)) / 1000);

      document.getElementById("countdown").innerHTML = `${dias}d ${horas}h ${minutos}m ${segundos}s`;

      if (distancia < 0) {
        clearInterval(cuentaRegresiva);
        document.getElementById("countdown").innerHTML = "¡Ya comenzó la fiesta! 🎉";
      }
    }, 1000);

    function confirmarAsistencia() {
      const nombre = document.getElementById("nombre").value;
      if (nombre.trim() === "") {
        document.getElementById("respuesta").textContent = "Por favor, escribe tu nombre.";
      } else {
        document.getElementById("respuesta").textContent = `¡Gracias por confirmar, ${nombre}! 🥳`;
      }
    }
  </script>
</body>
</html>
