# 📞 Contact

## 📧 Email
✉️ Tu peux me contacter par email : [monemail@example.com](mailto:monemail@example.com)

## 🔗 LinkedIn
🔗 Retrouve-moi sur [LinkedIn](https://www.linkedin.com/in/monprofil)

## 🏫 Adresse
📍 Mon adresse :  
123 Rue de l'IUT, 30000 Nîmes, France

## 📱 Téléphone
📞 +33 7 81 23 30 35

---

## 📝 Formulaire de Contact (si activé)
Si ton site est hébergé avec GitHub Pages, **MkDocs n'accepte pas les formulaires de base**.  
Tu peux utiliser [Formspree](https://formspree.io/) pour ajouter un **formulaire de contact**.


<canvas id="circuitCanvas"></canvas>
<script>
const canvas = document.getElementById("circuitCanvas");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

const nodes = [];
for (let i = 0; i < 50; i++) {
    nodes.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        dx: (Math.random() - 0.5) * 2,
        dy: (Math.random() - 0.5) * 2
    });
}

function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = "rgba(0, 255, 100, 0.8)";
    
    nodes.forEach(node => {
        node.x += node.dx;
        node.y += node.dy;
        
        if (node.x < 0 || node.x > canvas.width) node.dx *= -1;
        if (node.y < 0 || node.y > canvas.height) node.dy *= -1;

        ctx.beginPath();
        ctx.arc(node.x, node.y, 3, 0, Math.PI * 2);
        ctx.fill();
        
        nodes.forEach(other => {
            const dist = Math.hypot(node.x - other.x, node.y - other.y);
            if (dist < 100) {
                ctx.strokeStyle = `rgba(0, 255, 100, ${1 - dist / 100})`;
                ctx.lineWidth = 1;
                ctx.beginPath();
                ctx.moveTo(node.x, node.y);
                ctx.lineTo(other.x, other.y);
                ctx.stroke();
            }
        });
    });
    requestAnimationFrame(draw);
}
draw();
</script>
<style>
#circuitCanvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    background: white;
}
</style>

<div class="cv-container">
    <h2>Mon CV</h2>
    <ul>
        <li>
            <a href="#experience1">Expérience 1</a>
        </li>
        <li>
            <a href="#experience2">Expérience 2</a>
        </li>
        <li>
            <a href="#formation">Formation</a>
        </li>
    </ul>

    <div id="experience1" class="cv-section">
        <h3>Poste 1</h3>
        <p>Description de l'expérience professionnelle 1...</p>
    </div>
    <div id="experience2" class="cv-section">
        <h3>Poste 2</h3>
        <p>Description de l'expérience professionnelle 2...</p>
    </div>
    <div id="formation" class="cv-section">
        <h3>Formation</h3>
        <p>Détails de ta formation académique...</p>
    </div>

    <button><a href="cv.pdf" download>Télécharger mon CV</a></button>
</div>

<style>
    .cv-container {
        padding: 20px;
    }
    .cv-section {
        margin-top: 20px;
    }
    a {
        text-decoration: none;
    }
</style>
