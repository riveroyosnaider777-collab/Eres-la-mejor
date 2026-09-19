<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flores Amarillas Para Ti</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600&family=Montserrat:ital,wght@0,300;0,400;0,600;1,300&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --letter-bg: #f9f5ea;
      --text-main: #5a4a42;
      --accent-color: #d4a373;
      --flower-yellow: #fcd34d;
      --flower-center: #b45309;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      background: radial-gradient(circle at center, #d90429 0%, #6b021d 60%, #2b000c 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Montserrat', sans-serif;
      padding: 20px;
      overflow-x: hidden;
    }

    /* Fondo animado de corazones suaves */
    .bg-hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
      background-image: 
        radial-gradient(circle at 20% 20%, rgba(255,182,193,0.15) 0%, transparent 20%),
        radial-gradient(circle at 80% 80%, rgba(255,182,193,0.15) 0%, transparent 20%);
    }

    /* Tarjeta Principal */
    .card-container {
      position: relative;
      z-index: 1;
      background-color: var(--letter-bg);
      width: 100%;
      max-width: 820px;
      border-radius: 35px;
      padding: 40px 35px;
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.4);
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
      gap: 30px;
    }

    /* Sección de Texto */
    .text-content {
      flex: 1.2;
      color: var(--text-main);
      display: flex;
      flex-direction: column;
      gap: 22px;
    }

    .title {
      font-size: 1.35rem;
      font-weight: 600;
      color: #4a3b32;
      line-height: 1.4;
    }

    .poem {
      font-size: 1.05rem;
      font-weight: 300;
      line-height: 1.7;
      color: #5c4b41;
    }

    .love-signature {
      font-size: 1.3rem;
      font-style: italic;
      color: #635045;
      margin-top: 5px;
    }

    .cursor {
      display: inline-block;
      animation: blink 1s infinite;
      font-weight: bold;
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }

    /* Contador */
    .counter-section {
      margin-top: 15px;
      border-bottom: 2px solid #8d7568;
      padding-bottom: 8px;
    }

    .counter-title {
      font-size: 0.95rem;
      color: #725e52;
      margin-bottom: 6px;
    }

    .counter-digits {
      font-size: 1.25rem;
      font-weight: 600;
      color: #3b2d25;
      letter-spacing: 0.5px;
    }

    .counter-digits span {
      font-weight: 400;
      font-size: 0.95rem;
      color: #635045;
      margin-right: 6px;
    }

    /* Ilustración del Árbol de Corazón */
    .illustration-container {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    .tree-svg {
      width: 100%;
      max-width: 320px;
      height: auto;
      filter: drop-shadow(0 10px 15px rgba(0,0,0,0.08));
    }

    /* Pétalos cayendo */
    .falling-petal {
      position: absolute;
      background: #facc15;
      border-radius: 50% 0 50% 50%;
      opacity: 0.8;
      animation: fall 4s infinite linear;
    }

    @keyframes fall {
      0% {
        transform: translateY(-20px) rotate(0deg);
        opacity: 0.9;
      }
      100% {
        transform: translateY(220px) rotate(360deg);
        opacity: 0;
      }
    }

    /* Adaptación para pantallas de teléfonos */
    @media (max-width: 720px) {
      .card-container {
        flex-direction: column-reverse;
        padding: 30px 22px;
        border-radius: 28px;
        gap: 20px;
      }

      .title {
        font-size: 1.2rem;
      }

      .poem {
        font-size: 0.98rem;
      }

      .counter-digits {
        font-size: 1.05rem;
      }

      .tree-svg {
        max-width: 240px;
      }
    }
  </style>
</head>
<body>

  <div class="bg-hearts"></div>

  <div class="card-container">
    
    <!-- LADO IZQUIERDO: TEXTOS Y CONTADOR -->
    <div class="text-content">
      <div class="title">
        Flores Amarillas para el amor de mi vida:
      </div>

      <div class="poem">
        <p>Si pudiera elegir un lugar seguro, sería a tu lado.</p>
        <br>
        <p>Cuanto más tiempo estoy contigo más te amo.</p>
      </div>

      <div class="love-signature">
        — I Love You! <span class="cursor">_</span>
      </div>

      <div class="counter-section">
        <div class="counter-title">Mi amor por ti comenzó hace...</div>
        <div class="counter-digits" id="timer">
          000 <span>días</span> 00 <span>horas</span> 00 <span>minutos</span> 00 <span>segundos</span>
        </div>
      </div>
    </div>

    <!-- LADO DERECHO: ÁRBOL DE FLORES AMARILLAS EN FORMA DE CORAZÓN -->
    <div class="illustration-container">
      <svg class="tree-svg" viewBox="0 0 300 320" fill="none" xmlns="http://www.w3.org/2000/svg">
        <!-- Tronco -->
        <path d="M140 300 C140 250, 120 220, 135 180 C140 165, 148 150, 150 135 C152 150, 160 165, 165 180 C180 220, 160 250, 160 300 Z" fill="#7c4a03" />
        <path d="M135 220 C110 200, 95 180, 85 170 C95 180, 115 195, 138 200 Z" fill="#5c3601" />
        <path d="M165 220 C190 200, 205 180, 215 170 C205 180, 185 195, 162 200 Z" fill="#5c3601" />

        <!-- Copa en Forma de Corazón (Flores) -->
        <g id="heart-foliage">
          <!-- Silueta base suave -->
          <path d="M150 135 C110 70, 40 80, 50 130 C60 180, 150 230, 150 230 C150 230, 240 180, 250 130 C260 80, 190 70, 150 135 Z" fill="#facc15" opacity="0.3" />

          <!-- Múltiples flores formando el corazón -->
          <!-- Centro e Izquierda -->
          <circle cx="150" cy="130" r="16" fill="#fbbf24"/><circle cx="150" cy="130" r="6" fill="#b45309"/>
          <circle cx="130" cy="110" r="15" fill="#facc15"/><circle cx="130" cy="110" r="5" fill="#92400e"/>
          <circle cx="170" cy="110" r="15" fill="#fde047"/><circle cx="170" cy="110" r="5" fill="#92400e"/>
          <circle cx="110" cy="130" r="16" fill="#facc15"/><circle cx="110" cy="130" r="6" fill="#b45309"/>
          <circle cx="190" cy="130" r="16" fill="#fbbf24"/><circle cx="190" cy="130" r="6" fill="#b45309"/>

          <!-- Lóbulo Izquierdo -->
          <circle cx="110" cy="95" r="15" fill="#fde047"/><circle cx="110" cy="95" r="5" fill="#b45309"/>
          <circle cx="85" cy="90" r="16" fill="#facc15"/><circle cx="85" cy="90" r="6" fill="#78350f"/>
          <circle cx="65" cy="110" r="15" fill="#fbbf24"/><circle cx="65" cy="110" r="5" fill="#92400e"/>
          <circle cx="70" cy="135" r="14" fill="#fde047"/><circle cx="70" cy="135" r="5" fill="#78350f"/>
          <circle cx="85" cy="155" r="15" fill="#facc15"/><circle cx="85" cy="155" r="5" fill="#b45309"/>

          <!-- Lóbulo Derecho -->
          <circle cx="190" cy="95" r="15" fill="#fde047"/><circle cx="190" cy="95" r="5" fill="#b45309"/>
          <circle cx="215" cy="90" r="16" fill="#facc15"/><circle cx="215" cy="90" r="6" fill="#78350f"/>
          <circle cx="235" cy="110" r="15" fill="#fbbf24"/><circle cx="235" cy="110" r="5" fill="#92400e"/>
          <circle cx="230" cy="135" r="14" fill="#fde047"/><circle cx="230" cy="135" r="5" fill="#78350f"/>
          <circle cx="215" cy="155" r="15" fill="#facc15"/><circle cx="215" cy="155" r="5" fill="#b45309"/>

          <!-- Punta Inferior del Corazón -->
          <circle cx="130" cy="160" r="15" fill="#fbbf24"/><circle cx="130" cy="160" r="5" fill="#78350f"/>
          <circle cx="170" cy="160" r="15" fill="#facc15"/><circle cx="170" cy="160" r="5" fill="#78350f"/>
          <circle cx="150" cy="180" r="16" fill="#fde047"/><circle cx="150" cy="180" r="6" fill="#b45309"/>
          <circle cx="150" cy="200" r="12" fill="#facc15"/><circle cx="150" cy="200" r="4" fill="#78350f"/>

          <!-- Detalle de florecitas pequeñas alrededor -->
          <circle cx="100" cy="75" r="10" fill="#fef08a"/><circle cx="200" cy="75" r="10" fill="#fef08a"/>
          <circle cx="150" cy="75" r="12" fill="#fbbf24"/>
          <circle cx="50" cy="120" r="11" fill="#fde047"/>
          <circle cx="250" cy="120" r="11" fill="#fde047"/>
          <circle cx="105" cy="175" r="12" fill="#facc15"/>
          <circle cx="195" cy="175" r="12" fill="#facc15"/>
        </g>
      </svg>

      <!-- Pétalos sueltos cayendo -->
      <div class="falling-petal" style="left: 25%; width: 10px; height: 10px; animation-delay: 0s;"></div>
      <div class="falling-petal" style="left: 45%; width: 12px; height: 12px; animation-delay: 1.5s;"></div>
      <div class="falling-petal" style="left: 70%; width: 9px; height: 9px; animation-delay: 0.8s;"></div>
      <div class="falling-petal" style="left: 85%; width: 11px; height: 11px; animation-delay: 2.2s;"></div>
    </div>

  </div>

  <script>
    // ========================================================
    // CONFIGURA AQUÍ TU FECHA DE INICIO DE RELACIÓN O CONOCIDOS:
    // Año, Mes (0 = Enero, 1 = Febrero... 8 = Septiembre), Día, Hora, Minuto
    // Ejemplo: 21 de Septiembre de 2025 -> new Date(2025, 8, 21, 0, 0, 0)
    // ========================================================
    const startDate = new Date(2025, 8, 21, 0, 0, 0);

    function updateTimer() {
      const now = new Date();
      const difference = now - startDate;

      if (difference < 0) {
        document.getElementById("timer").innerHTML = "¡El contador comenzará muy pronto!";
        return;
      }

      const days = Math.floor(difference / (1000 * 60 * 60 * 24));
      const hours = Math.floor((difference / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((difference / 1000 / 60) % 60);
      const seconds = Math.floor((difference / 1000) % 60);

      const formattedHours = hours < 10 ? '0' + hours : hours;
      const formattedMinutes = minutes < 10 ? '0' + minutes : minutes;
      const formattedSeconds = seconds < 10 ? '0' + seconds : seconds;

      document.getElementById("timer").innerHTML = 
        `${days} <span>días</span> ${formattedHours} <span>horas</span> ${formattedMinutes} <span>minutos</span> ${formattedSeconds} <span>segundos</span>`;
    }

    // Actualiza el contador cada 1 segundo
    setInterval(updateTimer, 1000);
    updateTimer();
  </script>
</body>
</html>
