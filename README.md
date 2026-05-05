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

/* =========================
BUTTONS
========================= */
.btn {
  display: inline-block;
  padding: 14px 18px;
  border-radius: 10px;
  text-decoration: none;
  font-weight: bold;
  margin: 8px;
  transition: 0.2s;
}

.btn-green { background: #22c55e; color: white; }
.btn-blue { background: #1e3a8a; color: white; }
.btn:hover { transform: translateY(-2px); }

/* =========================
GRID
========================= */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 15px;
  padding: 20px;
}

/* =========================
CARDS
========================= */
.card {
  background: white;
  padding: 18px;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

/* =========================
SECTIONS TITRES
========================= */
.section-title {
  padding: 20px;
  font-size: 18px;
  font-weight: bold;
}

/* =========================
POPUPS
========================= */
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
  width: 90%;
}

/* =========================
MENU BAS
========================= */
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

</style>
</head>

<body>

<!-- =========================
HERO + DOUBLE ACCÈS
========================= -->
<section class="hero">
  <h1>Bienvenue au bloc opératoire</h1>
  <p>Institut Cœur Poumon – Parcours IADE</p>

  <div>
    <a href="https://acceuil-icp-eiade.github.io/Livret/" class="btn btn-green">🌍 Guide étudiant</a>
    <a href="TON-LIEN-SHAREPOINT" class="btn btn-blue">🔐 Accès complet</a>
  </div>

  <p style="font-size:12px; opacity:0.7;">
    Certains contenus nécessitent un accès réseau interne
  </p>
</section>

<!-- =========================
ACCUEIL MESSAGE
========================= -->
<div class="card" style="margin:15px;">
  <h2>👋 Message de bienvenue</h2>
  <p>
    Toute l’équipe du bloc opératoire de l’Institut Cœur Poumon est ravie de vous accueillir.
  </p>
  <p>
    Ici vous êtes là pour apprendre, progresser et poser toutes vos questions.
  </p>
  <p><strong>👉 Il n’y a pas de mauvaises questions.</strong></p>
</div>

<!-- =========================
ACCES RAPIDES
========================= -->
<div class="section-title">📌 Accès rapides</div>

<div class="grid">
  <div class="card clickable" onclick="openPopup('jour')">📍 Premier jour</div>
  <div class="card clickable" onclick="openPopup('vie')">🏥 Vie pratique</div>
  <div class="card clickable" onclick="openPopup('orga')">🩺 Organigramme</div>
  <div class="card clickable" onclick="openPopup('ref')">♻️ Référents</div>
</div>

<!-- =========================
POPUP JOUR 1
========================= -->
<div id="jour" class="popup">
  <div class="popup-content">
    <h2>📍 Premier jour</h2>
    <ul>
      <li>RDV 8h salle de réveil</li>
      <li>Tenue de bloc obligatoire</li>
      <li>Badge + documents de stage</li>
      <li>Fiche de suivi à compléter</li>
    </ul>
    <button onclick="closePopup('jour')">Fermer</button>
  </div>
</div>

<!-- =========================
POPUP VIE PRATIQUE
========================= -->
<div id="vie" class="popup">
  <div class="popup-content">
    <h2>🏥 Vie pratique</h2>
    <ul>
      <li>Vestiaires avec casiers</li>
      <li>Salle de pause</li>
      <li>Self niveau -2</li>
      <li>Relais H niveau 0</li>
    </ul>
    <button onclick="closePopup('vie')">Fermer</button>
  </div>
</div>

<!-- =========================
PLAN
========================= -->
<div class="card" style="margin:15px;">
  <h2>🗺️ Plan du bloc</h2>
  <p>Consultez le plan pour vous repérer facilement.</p>
  <a class="btn btn-blue" href="pdf/plan2.pdf" target="_blank">📄 Ouvrir le plan</a>
</div>

<!-- =========================
VIDEO
========================= -->
<div class="card" style="margin:15px;">
  <h2>🎥 Visite du service</h2>
  <p>Disponible prochainement</p>
</div>

<!-- =========================
ORGANIGRAMME
========================= -->
<div id="orga" class="popup">
  <div class="popup-content">
    <h2>🩺 Organigramme</h2>
    <p><strong>Anesthésie :</strong> Dr Desbordes</p>
    <p><strong>Réanimation :</strong> Pr Moussa</p>
    <p><strong>SIPO :</strong> Dr Robin</p>
    <p><strong>Cardio :</strong> Pr Vincentelli</p>
    <button onclick="closePopup('orga')">Fermer</button>
  </div>
</div>

<!-- =========================
REFERENTS
========================= -->
<div id="ref" class="popup">
  <div class="popup-content">
    <h2>♻️ Référents</h2>
    <p>Cadre : Mme Reumaux</p>
    <p>IADE référente : Mme Hennache</p>
    <p>Équipe IADE référente disponible au quotidien</p>
    <button onclick="closePopup('ref')">Fermer</button>
  </div>
</div>

<!-- =========================
DOCUMENTS
========================= -->
<div class="card" style="margin:15px;">
  <h2>📄 Documents</h2>
  <a class="btn btn-blue" href="pdf/COEUR.pdf" target="_blank">🫀 Cœur ouvert</a>
  <a class="btn btn-blue" href="pdf/CEC.pdf" target="_blank">⚙️ CEC</a>
  <a class="btn btn-blue" href="pdf/VASCULAIRE.pdf" target="_blank">🩸 Vasculaire</a>
</div>

<!-- =========================
URGENCES
========================= -->
<div class="card" style="margin:15px;">
  <h2>🚨 Protocoles d’urgence</h2>
  <a class="btn btn-blue" href="pdf/arret.pdf">❤️ Arrêt cardiaque</a>
  <a class="btn btn-blue" href="pdf/hemorragie.pdf">🩸 Hémorragie</a>
  <a class="btn btn-blue" href="pdf/anaphylaxie.pdf">⚠️ Anaphylaxie</a>
</div>

<!-- =========================
BILAN + RETOUR
========================= -->
<div class="card" style="margin:15px;">
  <h2>📝 Retour de stage</h2>
  <a class="btn btn-green" href="https://forms.gle/4ATLvfYK83cmkXiN7" target="_blank">
    Donner mon avis
  </a>
</div>

<!-- =========================
MENU BAS
========================= -->
<div class="bottom-menu">
  <a href="#">📑</a>
  <a href="#">🗺</a>
  <a href="#">🎥</a>
  <a href="#">📝</a>
</div>

<script>
function openPopup(id){
  document.getElementById(id).classList.add("show");
}

function closePopup(id){
  document.getElementById(id).classList.remove("show");
}
</script>

</body>
</html>
