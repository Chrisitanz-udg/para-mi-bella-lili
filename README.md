<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>San Valentín 💘</title>

<style>
    body {
        margin: 0;
        padding: 0;
        background: linear-gradient(to bottom right, #ff9a9e, #fad0c4);
        background-attachment: fixed;
        font-family: Arial, sans-serif;
        text-align: center;
        overflow: hidden;
        transition: background 1s ease;
    }

    h1 {
        margin-top: 100px;
        font-size: 40px;
        color: white;
        text-shadow: 2px 2px 5px #ff4d6d;
    }

    .botones {
        margin-top: 50px;
    }

    button {
        padding: 15px 30px;
        font-size: 20px;
        border: none;
        border-radius: 25px;
        cursor: pointer;
        transition: 0.3s;
        margin: 10px;
    }

    #si {
        background-color: #ff4d6d;
        color: white;
    }

    #si:hover {
        background-color: #ff1e4d;
        transform: scale(1.1);
    }

    #no {
        background-color: white;
        color: #ff4d6d;
        position: absolute;
    }

    .mensaje {
        margin-top: 40px;
        font-size: 28px;
        color: white;
        display: none;
        animation: aparecer 1.5s ease forwards;
    }

    @keyframes aparecer {
        from { opacity: 0; transform: scale(0.5); }
        to { opacity: 1; transform: scale(1); }
    }

    .corazon {
        position: absolute;
        color: red;
        animation: flotar 6s linear infinite;
    }

    @keyframes flotar {
        0% { transform: translateY(100vh); opacity: 1; }
        100% { transform: translateY(-10vh); opacity: 0; }
    }
</style>
</head>

<body>

<!-- 🎵 Música -->
<audio id="musica" loop>
    <source src="cancion.mp3" type="audio/mpeg">
</audio>

<h1>¿Quieres ser mi San Valentín bella? 💖</h1>

<div class="botones">
    <button id="si" onclick="aceptar()">Sí 💕</button>
    <button id="no" onmouseover="mover()">No 😢</button>
</div>

<div class="mensaje" id="mensaje">
    ¡Te amooo bella! 💘  
    Espero alegrarte el día y llenarte de sonrisas.  
    Es increíble estar con alguien como tú ✨  
    Gracias por existir 💖
</div>

<script>

function aceptar() {
    document.getElementById("mensaje").style.display = "block";
    document.getElementById("musica").play();

    // Oscurecer fondo románticamente
    document.body.style.background = "linear-gradient(to bottom right, #ff4d6d, #c9184a)";

    // Explosión de corazones
    for (let i = 0; i < 40; i++) {
        let corazon = document.createElement("div");
        corazon.innerHTML = "💖";
        corazon.style.position = "absolute";
        corazon.style.left = Math.random() * window.innerWidth + "px";
        corazon.style.top = Math.random() * window.innerHeight + "px";
        corazon.style.fontSize = Math.random() * 30 + 20 + "px";
        corazon.style.animation = "flotar 4s linear forwards";
        document.body.appendChild(corazon);

        setTimeout(() => {
            corazon.remove();
        }, 4000);
    }
}

function mover() {
    let botonNo = document.getElementById("no");
    let x = Math.random() * (window.innerWidth - 100);
    let y = Math.random() * (window.innerHeight - 50);
    botonNo.style.left = x + "px";
    botonNo.style.top = y + "px";
}

// Corazones flotando constantemente
setInterval(() => {
    let corazon = document.createElement("div");
    corazon.innerHTML = "💖";
    corazon.classList.add("corazon");
    corazon.style.left = Math.random() * window.innerWidth + "px";
    corazon.style.fontSize = Math.random() * 20 + 20 + "px";
    document.body.appendChild(corazon);

    setTimeout(() => {
        corazon.remove();
    }, 6000);
}, 600);

</script>

</body>
</html>



