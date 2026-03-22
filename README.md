<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Accueil IADE - ICP</title>

  <style>
    * { box-sizing: border-box; }

    body {
      font-family: 'Segoe UI', Arial, sans-serif;
      margin: 0;
      padding: 10px;
      background-color: #f7f9fb;
      color: #2c3e50;
    }

    header {
      background: linear-gradient(135deg, #5dade2, #48c9b0);
      color: white;
      padding: 20px;
      text-align: center;
      border-radius: 10px;
    }

    h1 {
      margin: 0;
      font-size: 22px;
    }

    /* 🔐 LOGIN */
    .login {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 80vh;
    }

    input {
      padding: 12px;
      margin: 10px;
      border-radius: 8px;
      border: 1px solid #ccc;
      width: 220px;
      text-align: center;
    }

    button {
      padding: 12px 20px;
      border: none;
      border-radius: 8px;
      background: #3498db;
      color: white;
      font-weight: bold;
    }

    .hidden {
      display: none;
    }

    .container {
      padding: 10px;
      width: 100%;
      max-width: 100%;
    }

    .card {
      background: white;
      padding: 15px;
      margin-bottom: 15px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    }

    h2 {
      color: #3498db;
      font-size: 18px;
    }

    /* 🔥 BOUTONS PDF */
    .btn {
      display: block;
      background: #3498db;
      color: white;
      text-decoration: none;
      padding: 16px;
      margin-bottom: 10px;
      border-radius: 12px;
      text-align: center;
      font-size: 16px;
      font-weight: bold;
    }

    .btn:active {
      background: #2c80b4;
    }

    footer {
      text-align: center;
      padding: 15px;
      color: #7f8c8d;
      font-size: 12px;
    }
  </style>
</head>

<body>

<header>
  <h1>Bienvenue à l’ICP ❤️</h1>
  <p>Bloc opératoire – Accueil des étudiants IADE</p>
</header>

<!-- 🔐 PAGE DE CONNEXION -->
<div id="loginPage" class="login">
  <h2>Accès réservé</h2>
  <input type="password" id="password" placeholder="Mot de passe">
  <button onclick="checkPassword()">Entrer</button>
  <p id="error" style="color:red;"></p>
</div>

<!-- 🔓 CONTENU -->
<div id="content" class="hidden">

<div class="container">

  <div class="card">
    <h2>👋 Message de bienvenue</h2>
    <p>
      Toute l’équipe du bloc opératoire de l’Institut Cœur Poumon est ravie de vous accueillir.  
      Nous savons que les débuts peuvent être impressionnants — ici, vous êtes là pour apprendre, progresser et poser toutes vos questions.
    </p>
    <p><strong>👉 Il n’y a pas de “mauvaises questions”.</strong></p>
  </div>

  <div class="card">
    <h2>📍 Votre premier jour</h2>
    <ul>
      <li><strong>Heure :</strong> 7h30</li>
      <li><strong>Lieu :</strong> Salle de repos du bloc</li>
      <li><strong>Tenue :</strong> Pyjama de bloc</li>
      <li><strong>À prévoir :</strong> Badge, carnet de stage</li>
    </ul>
  </div>

  <div class="card">
    <h2>🏥 Organisation du service</h2>
    <ul>
      <li>Bloc opératoire</li>
      <li>SSPI</li>
      <li>Consultation d’anesthésie</li>
    </ul>
    <p>
      Vous serez encadré(e) par une équipe d’IADE, de médecins anesthésistes et d’IDE expérimentés.
    </p>
  </div>

  <div class="card">
    <h2>📄 Accès rapide aux documents</h2>

    <a class="btn" href="docs/protocoles.pdf" target="_blank">
      📘 Protocoles anesthésie
    </a>

    <a class="btn" href="docs/checklist.pdf" target="_blank">
      ✅ Check-list sécurité
    </a>

    <a class="btn" href="docs/urgence.pdf" target="_blank">
      🚨 Urgences anesthésie
    </a>

  </div>

  <div class="card">
    <h2>📞 Contacts</h2>
    <p><strong>Cadre :</strong> (à compléter)</p>
    <p><strong>Référent IADE :</strong> (à compléter)</p>
  </div>

  <div class="card">
    <h2>💬 Petit mot pour vous</h2>
    <p>
      Le bloc est un environnement exigeant, mais aussi passionnant.  
      Prenez le temps d’observer, de comprendre… et surtout de vous faire confiance.
    </p>
    <p><strong>On est là pour vous accompagner 🤝</strong></p>
  </div>

</div>

<footer>
  Institut Cœur Poumon – Bloc opératoire
</footer>

</div>

<script>
function checkPassword() {
  const password = document.getElementById("password").value;

  // 🔑 CHANGE TON MOT DE PASSE ICI
  const correctPassword = "iadeicp543";

  if (password === correctPassword) {
    document.getElementById("loginPage").classList.add("hidden");
    document.getElementById("content").classList.remove("hidden");
  } else {
    document.getElementById("error").innerText = "Mot de passe incorrect";
  }
}
</script>

</body>
</html>
