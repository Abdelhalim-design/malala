<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Portfolio - Abdelhalim Zouggagh</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css"> <!-- Ton fichier CSS externe -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    .skills-container {
        padding: 20px;
    }
    .skill {
        margin-bottom: 15px;
    }
    label {
        display: block;
        margin-bottom: 5px;
    }
    progress {
        width: 100%;
        height: 20px;
    }
    #map {
        width: 100%;
        height: 200px;
        margin-top: 20px;
        border-radius: 8px;
    }
  </style>
</head>
<body>

  <h1>🎓 Portfolio - Abdelhalim Zouggagh</h1>
  <p>Bienvenue sur mon portfolio !<br>
  Vous y découvrirez mon parcours, mes compétences et mes projets réalisés en <strong>Génie Électrique et Informatique Industrielle (GEII)</strong>.</p>

  <h2>🏅 À Propos de Moi</h2>

  <p>
    🎓 <strong>Abdelhalim Zouggagh</strong><br>
    📍 <em>Étudiant en Génie Électrique et Informatique Industrielle (GEII) - IUT de Nîmes</em>
  </p>

  <h2>📍 Localisation de mon IUT</h2>
  <div id="map"></div>

  <h3>🔹 Parcours scolaire</h3>
  <ul>
    <li>🎓 <strong>Baccalauréat Général</strong> (Mathématiques & SES)</li>
    <li>🏗️ <strong>GEII - IUT de Nîmes</strong> (Projets en électronique, programmation, systèmes embarqués...)</li>
  </ul>

  <h3>🔹 Compétences principales</h3>
  <ul>
    <li>✅ Programmation (Python, C, HTML/CSS, Arduino)</li>
    <li>✅ Systèmes embarqués & électronique</li>
    <li>✅ Automatisme & réseaux industriels</li>
  </ul>

  <h3>🔹 Objectifs professionnels</h3>
  <ul>
    <li>📡 Travailler dans le domaine des <strong>systèmes embarqués et de l'électronique industrielle</strong></li>
    <li>🤖 Développer des solutions <strong>d'automatisation et d’intelligence artificielle embarquée</strong></li>
    <li>🚀 Continuer mes études en <strong>ingénierie ou recherche appliquée</strong></li>
  </ul>

  <button id="dark-mode-toggle">🌙 Mode Sombre</button>

  <div class="skills-container">
    <h2>Mes Compétences</h2>
    <div class="skill">
        <label for="html">HTML</label>
        <progress id="html" value="90" max="100"></progress>
    </div>
    <div class="skill">
        <label for="css">CSS</label>
        <progress id="css" value="85" max="100"></progress>
    </div>
    <div class="skill">
        <label for="js">JavaScript</label>
        <progress id="js" value="75" max="100"></progress>
    </div>
    <div class="skill">
        <label for="python">Python</label>
        <progress id="python" value="80" max="100"></progress>
    </div>
  </div>

  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
  <script>
    var map = L.map('map').setView([43.8362, 4.3517], 15);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '© OpenStreetMap contributors'
    }).addTo(map);
    L.marker([43.8362, 4.3517]).addTo(map)
      .bindPopup('📍 IUT de Nîmes')
      .openPopup();

    // Mode sombre
    document.getElementById("dark-mode-toggle").addEventListener("click", function () {
      document.body.classList.toggle("dark-mode");
    });
  </script>

</body>
</html>
