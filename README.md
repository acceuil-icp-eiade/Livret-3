<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Accueil IADE - ICP</title>

<style>
/* =========================
RESET PROPRE
========================= */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html, body {
  overflow-x: hidden;
}

/* =========================
BASE
========================= */
body {
  font-family: 'Segoe UI', Arial, sans-serif;
  background-color: #f7f9fb;
  color: #2c3e50;
}

/* =========================
HEADER
========================= */
header {
  background: linear-gradient(135deg, #5dade2, #48c9b0);
  color: white;
  padding: 20px;
  text-align: center;
  border-radius: 0 0 16px 16px;
}

header h1 {
  font-size: 20px;
}

header p {
  font-size: 13px;
  opacity: 0.9;
}

/* =========================
CONTAINER
========================= */
.container {
  padding: 15px;
}

/* =========================
CARDS
========================= */
.card {
  background: white;
  padding: 18px;
  margin-bottom: 15px;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

/* =========================
BUTTONS
========================= */
.btn {
  display: block;
  background: #3498db;
  color: white;
  text-decoration: none;
  padding: 14px;
  margin-top: 10px;
  border-radius: 12px;
  text-align: center;
  font-weight: bold;
}

.btn:hover {
  filter: brightness(1.1);
}

/* variants */
.btn.urgence { background: #e74c3c; }
.btn.bilan { background: #27ae60; }

/* =========================
GRID
========================= */
.cards-row {
  display: flex;
  gap: 10px;
}

.cards-row .card {
  flex: 1;
}

/* =========================
POPUP
========================= */
.popup {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.5);
  display: none;
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.popup.show {
  display: flex;
}

.popup-content {
  background: white;
  padding: 20px;
  border-radius: 16px;
  width: 90%;
  max-width: 500px;
}

/* =========================
CLOSE BTN
========================= */
.close-btn {
  float: right;
  border: none;
  background: transparent;
  font-size: 18px;
}

/* =========================
MENU BAS
========================= */
.bottom-menu {
  position: fixed;
  bottom: 0;
  width: 100%;
  max-width: 500px;
  left: 50%;
  transform: translateX(-50%);
  background: white;
  display: flex;
  justify-content: space-around;
  padding: 10px;
  box-shadow: 0 -2px 10px rgba(0,0,0,0.1);
}

/* =========================
UTILITIES
========================= */
.hidden {
  display: none;
}

.rouge { color: red; font-weight: bold; }

.hint {
  font-size: 12px;
  color: gray;
}

</style>
</head>

<body>

<!-- HEADER -->
<header>
  <h1>Bienvenue à l'ICP</h1>
  <p>Bloc opératoire – Accueil des étudiants IADE</p>
</header>

<!-- LOGIN -->
<div id="loginPage" class="container">
  <div class="card">
    <h2>Accès réservé</h2>
    <input type="password" id="password" placeholder="Mot de passe">
    <button class="btn" onclick="checkPassword()">Entrer</button>
    <p id="error" style="color:red;"></p>
  </div>
</div>

<!-- DISCLAIMER -->
<div id="disclaimer" class="popup">
  <div class="popup-content">
    <h3>⚠️ Avertissement</h3>
    <p>Site pédagogique non officiel.</p>
    <button class="btn" onclick="acceptDisclaimer()">Continuer</button>
  </div>
</div>

<!-- CONTENU -->
<div id="content" class="hidden container">

<!-- WELCOME -->
<div class="card">
  <h2>👋 Message de bienvenue</h2>
  <p>Bienvenue au bloc opératoire de l’ICP.</p>
</div>

<!-- ACCES RAPIDES -->
<div class="cards-row">

  <div class="card clickable" onclick="openPopup('jour')">
    📍 Premier jour
  </div>

  <div class="card clickable" onclick="openPopup('vie')">
    🏥 Vie pratique
  </div>

</div>

<!-- PLAN -->
<div class="card">
  <h2>🗺️ Plan du bloc</h2>
  <a class="btn" href="pdf/plan2.pdf" target="_blank">Voir le plan</a>
</div>

<!-- URGENCES -->
<div class="card">
  <h2>🚨 Protocoles</h2>
  <a class="btn urgence" href="pdf/arret.pdf">Arrêt cardiaque</a>
  <a class="btn urgence" href="pdf/hemorragie.pdf">Hémorragie</a>
</div>

<!-- RETOUR -->
<div class="card">
  <h2>📝 Retour de stage</h2>
  <a class="btn bilan" href="https://forms.gle/4ATLvfYK83cmkXiN7" target="_blank">
    Donner mon avis
  </a>
</div>

</div>

<!-- POPUPS -->
<div id="jour" class="popup">
  <div class="popup-content">
    <button class="close-btn" onclick="closePopup('jour')">✖️</button>
    <h3>Premier jour</h3>
    <p>RDV 8h salle de réveil</p>
  </div>
</div>

<div id="vie" class="popup">
  <div class="popup-content">
    <button class="close-btn" onclick="closePopup('vie')">✖️</button>
    <h3>Vie pratique</h3>
    <p>Vestiaires, pause, restauration</p>
  </div>
</div>

<!-- MENU -->
<div class="bottom-menu">
  <a href="#">📑</a>
  <a href="#">🗺</a>
  <a href="#">🚨</a>
  <a href="#">📝</a>
</div>

<script>

function openPopup(id){
  document.getElementById(id).classList.add("show");
}

function closePopup(id){
  document.getElementById(id).classList.remove("show");
}

function checkPassword(){
  const pass = document.getElementById("password").value;

  if(pass === "iadeicp543"){
    document.getElementById("loginPage").style.display = "none";
    document.getElementById("disclaimer").classList.add("show");
  } else {
    document.getElementById("error").innerText = "Mot de passe incorrect";
  }
}

function acceptDisclaimer(){
  document.getElementById("disclaimer").classList.remove("show");
  document.getElementById("content").classList.remove("hidden");
}

</script>

</body>
</html>
