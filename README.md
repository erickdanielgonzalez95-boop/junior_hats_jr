<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Junior Caps JR</title>

<style>
body {
  font-family: Arial, sans-serif;
  margin:0;
  padding:0;
  background:#f4f4f4;
}
header {
  background:#111;
  color:#fff;
  padding:20px;
  text-align:center;
}
.catalogo {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(180px,1fr));
  gap:15px;
  padding:20px;
  max-width:1200px;
  margin:auto;
}
.product {
  background:#fff;
  border-radius:10px;
  overflow:hidden;
  box-shadow:0 2px 5px rgba(0,0,0,0.2);
}
.product img {
  width:100%;
  height:200px;
  object-fit:cover;
}
.p-body {
  padding:10px;
  text-align:center;
}
.p-title { font-weight:bold; }
.price { margin-bottom:8px; font-weight:bold; }
.btn {
  display:inline-block;
  padding:8px 12px;
  background:#25D366;
  color:#fff;
  text-decoration:none;
  border-radius:5px;
  cursor:pointer;
}
footer {
  text-align:center;
  padding:20px;
  background:#111;
  color:#fff;
}
footer a { color:#ffcc00; text-decoration:none; }
</style>

<script>
function comprar(producto) {
  const phone = "524428655081";
  const mensaje = encodeURIComponent(
    "Hola quiero comprar la gorra " + producto
  );

  if (/iPhone|iPad|iPod/i.test(navigator.userAgent)) {
    window.location.href =
      "whatsapp://send?phone=" + phone + "&text=" + mensaje;
  } else {
    window.open(
      "https://api.whatsapp.com/send?p
