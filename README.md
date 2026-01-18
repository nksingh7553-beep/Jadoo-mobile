# Jadoo-mobile
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JADOO Mobile</title>

<style>
  body {
    margin: 0;
    background: black;
    color: #00ffcc;
    font-family: monospace;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
    user-select: none;
  }

  .screen {
    border: 2px solid #00ffcc;
    padding: 20px;
    width: 90%;
    max-width: 350px;
  }

  .blink {
    animation: blink 1s infinite;
  }

  @keyframes blink {
    50% { opacity: 0; }
  }
</style>
</head>

<body>
  <div class="screen" id="screen">
    <p>JADOO v1</p>
    <p class="blink">TAP TO ACTIVATE</p>
  </div>

<script>
  const screen = document.getElementById("screen");
  const sound = new Audio("https://actions.google.com/sounds/v1/alarms/beep_short.ogg");

  screen.addEventListener("click", () => {
    sound.play();
    if (navigator.vibrate) navigator.vibrate(100);

    screen.innerHTML = `
      <p>RECEIVING SIGNAL...</p>
      <p>SENDING DATA...</p>
      <p class="blink">CONNECTED</p>
    `;
  });
</script>
</body>
</html>
