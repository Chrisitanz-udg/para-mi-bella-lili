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
        font-family: 'Arial', sans-serif;
        text-align: center;
        overflow: hidden;
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
        font-size: 25px;
        color: white;
        display: none;
    }

    /* Corazones flotando */
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

<h1>¿Quieres ser mi San Valentín bella? 💖</h1>

<div class="botones">
    <button id="si" onclick="aceptar()">Sí 💕</button>
    <button id="no" onmouseover="mover()">No 😢</button>
</div>

<div class="mensaje" id="mensaje">
    ¡Te amooo bella espero alegrearte el día y llenarte de sonrísas, es increíble estar con alguien como tú mua mua :*! 💘✨  
    
</div>

<script>
    function aceptar() {
        document.getElementById("mensaje").style.display = "block";
    }

    function mover() {
        let botonNo = document.getElementById("no");
        let x = Math.random() * window.innerWidth;
        let y = Math.random() * window.innerHeight;
        botonNo.style.left = x + "px";
        botonNo.style.top = y + "px";
    }

 
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
    }, 500);
</script>

</body>
</html>
