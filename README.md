<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Junior Hats JR</title>

<style>
:root{
  --negro:#000;
  --negro2:#111;
  --dorado:#d4af37;
  --gris:#cfcfcf;
}

*{box-sizing:border-box}

body{
  margin:0;
  font-family:Arial, sans-serif;
  background:var(--negro);
}

/* ===== SPLASH ===== */
#splash{
  position:fixed;
  inset:0;
  background:linear-gradient(145deg,#000,#111);
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  z-index:9999;
  text-align:center;
}

#splash h1{
  font-size:3rem;
  color:var(--dorado);
  letter-spacing:3px;
  animation:spin 5s linear infinite, glow 3s ease-in-out infinite;
}

@keyframes spin{
  from{transform:rotateY(0deg)}
  to{transform:rotateY(360deg)}
}

@keyframes glow{
  0%,100%{text-shadow:0 0 10px rgba(212,175,55,.4)}
  50%{text-shadow:0 0 30px rgba(212,175,55,.9)}
}

#splash p{
  color:var(--gris);
  margin-top:15px;
}

#splash button{
  margin-top:30px;
  padding:14px 45px;
  border:none;
  border-radius:30px;
  background:var(--dorado);
  color:#000;
  font-weight:bold;
  cursor:pointer;
}

/* ===== HEADER ===== */
header{
  background:#000;
  padding:30px 20px;
  text-align:center;
}

header h1{
  margin:0;
  color:var(--dorado);
}

header h1::before{content:"🧢 "}

header p{
  color:var(--gris);
  margin-top:8px;
}

/* ===== CATÁLOGO ===== */
.catalogo{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
  gap:20px;
  padding:40px 20px;
  max-width:1200px;
  margin:auto;
}

.product{
  background:#1a1a1a;
  border-radius:15px;
  padding:15px;
  box-shadow:0 10px 25px rgba(0,0,0,.8);
  transition:.3s;
}

.product:hover{transform:translateY(-6px)}

.product img{
  width:100%;
  height:220px;
  object-fit:cover;
  border-radius:10px;
}

.p-body{text-align:center;margin-top:12px}
.p-title{color:#fff;font-weight:bold}
.price{color:var(--dorado);font-weight:bold;margin:6px 0}

.btn{
  display:inline-block;
  margin-top:8px;
  padding:8px 22px;
  border:1px solid var(--dorado);
  border-radius:25px;
  color:var(--dorado);
  text-decoration:none;
}

.btn:hover{background:var(--dorado);color:#000}

/* ===== BOTONES ===== */
#exit,#mute{
  position:fixed;
  bottom:20px;
  padding:12px 20px;
  border:none;
  border-radius:50px;
  font-weight:bold;
  cursor:pointer;
}

#exit{right:20px;background:var(--dorado);color:#000}
#mute{left:20px;background:#111;color:var(--dorado);border:1px solid var(--dorado)}
</style>
</head>

<body>

<!-- SPLASH -->
<div id="splash">
  <h1>JUNIOR HATS JR</h1>
  <p>Estilo urbano · Calidad · Presencia</p>
  <button onclick="entrar()">ENTRAR</button>
</div>

<!-- AUDIO -->
<audio id="musica" preload="auto" loop>
  <source src="musica.mp3" type="audio/mpeg">
</audio>

<header>
  <h1>Junior Hats JR</h1>
  <p>La mejor calidad en gorras – Venta al detalle y mayoreo</p>
</header>

<section class="catalogo">
  <!-- PRODUCTOS (tuyos intactos) -->
</section>

<button id="mute" onclick="toggleAudio()">🔊 SONIDO</button>
<button id="exit" onclick="location.reload()">SALIR</button>

<script>
const audio = document.getElementById("musica");
const muteBtn = document.getElementById("mute");
audio.volume = 0.4;
let sonidoActivo = false;

function entrar(){
  document.getElementById("splash").style.display="none";
  audio.play().then(()=>{
    sonidoActivo = true;
    muteBtn.textContent="🔊 SONIDO";
  }).catch(err=>{
    console.log("Audio bloqueado hasta interacción:", err);
  });
}

function toggleAudio(){
  if(sonidoActivo){
    audio.pause();
    muteBtn.textContent="🔇 MUTE";
  }else{
    audio.play();
    muteBtn.textContent="🔊 SONIDO";
  }
  sonidoActivo = !sonidoActivo;
}
</script>

</body>
</html>
