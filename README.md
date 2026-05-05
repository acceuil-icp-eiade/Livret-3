<!DOCTYPE html><html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Accueil IADE - ICP</title><style>

/* RESET */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

/* BASE */
body {
  font-family: Arial, sans-serif;
  background: #f9fafb;
  color: #1f2937;
}

/* HERO */
.hero {
  background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)),
              url('https://images.unsplash.com/photo-1586773860418-d37222d8fce3');
  background-size: cover;
  background-position: center;
  color: white;
  text-align: center;
  padding: 60px 20px;
}

.hero h1 {
  font-size: 2em;
}

.hero p {
  margin-top: 10px;
  opacity: 0.9;
}

/* BUTTONS */
.btn {
  display: inline-block;
  padding: 14px 20px;
  border-radius: 10px;
  text-decoration: none;
  font-weight: bold;
  margin: 10px;
  transition: 0.2s;
}

.btn-green {
  background: #22c55e;
  color: white;
}

.btn-blue {
  background: #1e3a8a;
  color: white;
}

.btn:hover {
  transform: translateY(-2px);
}

/* GRID */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 15px;
  padding: 20px;
}

/* CARDS */
.card {
  background: white;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

/* POPUP */
.popup {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.5);
  display: none;
  justify-content: center;
  align-items: center;
}

.popup.show {
  display: flex;
}

.popup-content {
  background: white;
  padding: 20px;
  border-radius: 15px;
  max-width: 500px;
}

/* MENU BAS */
.bottom-menu {
  position: fixed;
  bottom: 0;
  width: 100%;
  background: white;
  display: flex;
  justify-content: space-around;
  padding: 10px;
  box-shadow: 0 -2px 10px rgba(0,0,0,0.05);
}

</style></head><body><!-- HERO --><section class="hero">
  <h1>Bienvenue au bloc opératoire</h1>
  <p>Parcours IADE – Institut Cœur Poumon</p>  <div>
    <a href="TON-LIEN-SITE" class="btn btn-green">🌍 Accès guide étudiant</a>
    <a href="TON-LIEN-SHAREPOINT" class="btn btn-blue">🔐 Accès contenu complet</a>
  </div>  <p style="font-size:12px; opacity:0.7;">
    Certains contenus nécessitent un accès réseau interne
  </p>
</section><!-- CONTENU --><div class="grid">  <div class="card" onclick="openPopup('jour')">📍 Premier jour</div>
  <div class="card" onclick="openPopup('vie')">🏥 Vie pratique</div>
  <div class="card" onclick="openPopup('orga')">🩺 Organigramme</div>
  <div class="card" onclick="openPopup('ref')">♻️ Référents</div></div><!-- POPUPS --><div id="jour" class="popup">
  <div class="popup-content">
    <h2>📍 Premier jour</h2>
    <p>RDV à 8h en salle de réveil</p>
    <button onclick="closePopup('jour')">Fermer</button>
  </div>
</div><div id="vie" class="popup">
  <div class="popup-content">
    <h2>🏥 Vie pratique</h2>
    <p>Vestiaires, salle de pause, restauration disponibles</p>
    <button onclick="closePopup('vie')">Fermer</button>
  </div>
</div><!-- MENU BAS --><div class="bottom-menu">
  <a href="#">📑</a>
  <a href="#">🗺</a>
  <a href="#">🎥</a>
  <a href="#">📝</a>
</div><script>
function openPopup(id){
  document.getElementById(id).classList.add("show");
}

function closePopup(id){
  document.getElementById(id).classList.remove("show");
}
</script></body>
</html>
