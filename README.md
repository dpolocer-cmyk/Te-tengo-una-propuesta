<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Propuesta</title>

<style>
    body{
        font-family: Arial, sans-serif;
        text-align: center;
        background: #ffe6f2;
        margin: 0;
        padding: 0;
        overflow-x: hidden;
    }

    #propuesta, #pregunta{
        margin-top: 80px;
    }

    .btn{
        padding: 15px 35px;
        font-size: 24px;
        border: none;
        border-radius: 20px;
        cursor: pointer;
        transition: 0.3s;
    }

    #si{
        background: #ff4d94;
        color: white;
        position: relative;
        z-index: 10;
    }

    #no{
        background: white;
        border: 2px solid #ff4d94;
        color: #ff4d94;
        position: absolute;
        transition: 0.3s;
        z-index: 1;
    }

    #msg{
        font-size: 24px;
        color: #d9006b;
        margin-top: 20px;
        min-height: 40px;
    }

    .sticker{
        width: 180px;
        display: block;
        margin: 20px auto;
    }

    .imagen-creativa{
        width: 280px;
        border-radius: 20px;
        box-shadow: 0 5px 20px rgba(0,0,0,0.2);
    }
</style>

</head>
<body>

<!-- PRIMERA PANTALLA -->
<div id="propuesta">
    <img class="imagen-creativa" 
         src="https://i.pinimg.com/474x/41/fa/6a/41fa6a760822ff93bfe43fa2b1d3cf07.jpg">
    
    <h1>Tengo una propuesta 😳💗</h1>
    
    <button class="btn" onclick="mostrarPregunta()">Ver propuesta 💌</button>
</div>

<!-- SEGUNDA PANTALLA -->
<div id="pregunta" style="display:none;">
    <h1>¿Quieres regresar conmigo? 🥺💗</h1>

    <img class="sticker" 
         src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQSlkgrnvrWRCNvkajsY58XJLd08EkrpaM_M0joRoaehiPvTYRBP2S4dwLHbw_g5FALyq8&usqp=CAU">

    <div style="margin-top:40px; position:relative; height:200px;">
        <button class="btn" id="si" onclick="aceptar()">Sí 💞</button>
        <button class="btn" id="no" onclick="rechazar()">No 💔</button>
    </div>

    <div id="msg"></div>
</div>

<script>
    const mensajes = [
        "¿Seguro? 😣",
        "No seas malo conmigo 🥺",
        "Dame una oportunidad pues 😞",
        "Piénsalo bien, corazón ❤️",
        "No me digas que no 😭",
        "Oye, no seas así conmigo 😫",
        "Sabes que te quiero mucho 💗",
        "No me rompas otra vez 😢",
        "Solo dame una chance más 😖",
        "Te juro que puedo mejorar ✨"
    ];

    let index = 0;
    let sizeSi = 24;

    function mostrarPregunta(){
        document.getElementById("propuesta").style.display = "none";
        document.getElementById("pregunta").style.display = "block";
    }

    function rechazar(){
        document.getElementById("msg").innerText = mensajes[index];
        index = (index + 1) % mensajes.length;

        sizeSi += 8;
        const si = document.getElementById("si");
        si.style.fontSize = sizeSi + "px";
        si.style.padding = (sizeSi/2) + "px " + (sizeSi) + "px";

        const no = document.getElementById("no");

        const x = (Math.random() * 300) - 150;
        const y = (Math.random() * 120) - 60;

        no.style.transform = `translate(${x}px, ${y}px)`;
    }

    function aceptar(){
        document.body.innerHTML = `
            <div style="
                position: fixed;
                top: 0;
                left: 0;
                width: 100vw;
                height: 100vh;
                background: #ffe6f2;
                display: flex;
                justify-content: center;
                align-items: center;
                flex-direction: column;
                text-align: center;
                padding: 0;
                margin: 0;
            ">
                <h1 style="
                    font-size: 40px;
                    color: #ff4d94;
                    margin-bottom: 20px;
                ">
                    Sabía que ibas a decir que sí 💘✨
                </h1>

                <img style="width: 200px;" 
                    src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRrb89SF64azOT04C18HsIMcCRVyE5yiQB0Xplg_9RhRlb6PK6_nyyEAHqVIYLOvD-xU2Y&usqp=CAU">
            </div>
        `;
    }
</script>

</body>
</html>
