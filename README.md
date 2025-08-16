<!DOCTYPE html><html lang="fr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>InfoNews — L'actualité du monde</title>
  <meta name="description" content="InfoNews — Suivez l'actualité du monde en temps réel : politique, économie, sport, culture, tech et plus." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --brand:#d32f2f;     /* Rouge principal */
      --brand-dark:#b71c1c;/* Rouge foncé */
      --ink:#111827;       /* Texte principal */
      --muted:#6b7280;     /* Texte secondaire */
      --bg:#ffffff;        /* Fond */
      --card:#f9fafb;      /* Cartes */
      --border:#e5e7eb;    /* Bordures */
      --focus:#ef9a9a;     /* Focus */
    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:var(--bg);color:var(--ink);font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif}
    a{color:var(--brand);text-decoration:none}
    a:hover{text-decoration:underline}/* Header */
.topbar{background:var(--brand);color:white}
.container{max-width:1200px;margin:0 auto;padding:0 16px}
.row{display:flex;align-items:center;gap:16px}
header{position:sticky;top:0;z-index:50;box-shadow:0 2px 8px rgba(0,0,0,.06)}
.topbar .row{justify-content:space-between;padding:10px 0}
.brand{display:flex;align-items:center;gap:10px;font-weight:800;letter-spacing:.3px}
.brand-logo{display:inline-grid;place-items:center;width:36px;height:36px;border-radius:10px;background:white;color:var(--brand);font-weight:900}
.brand-title{font-size:1.25rem}

nav{background:white;border-bottom:1px solid var(--border)}
.nav-inner{display:flex;align-items:center;justify-content:space-between;padding:8px 0;gap:12px}
.menu{display:flex;flex-wrap:wrap;gap:8px}
.menu a{padding:8px 12px;border-radius:999px;color:var(--ink);border:1px solid transparent}
.menu a:hover{background:var(--card)}
.menu a.active{background:var(--brand);color:white}

.search{position:relative;flex:1;max-width:380px}
.search input{width:100%;padding:10px 12px 10px 40px;border:1px solid var(--border);border-radius:12px;background:white}
.search svg{position:absolute;left:12px;top:50%;transform:translateY(-50%)}

.hamburger{display:none;background:transparent;border:0;font-size:1.1rem;padding:8px;color:var(--brand)}

/* Hero */
.hero{background:linear-gradient(180deg, rgba(211,47,47,.12), transparent 60%)}
.hero-inner{padding:28px 0 18px}
.badge{display:inline-block;background:var(--brand);color:#fff;padding:6px 10px;border-radius:999px;font-size:.8rem;font-weight:700;letter-spacing:.3px}
.headline{margin:10px 0 6px;font-size:1.8rem;line-height:1.2}
.sub{color:var(--muted)}

/* Layout */
.grid{display:grid;grid-template-columns:2fr 1fr;gap:22px}

/* Cards */
.card{background:var(--card);border:1px solid var(--border);border-radius:16px;overflow:hidden}
.card h3{margin:0 0 8px}
.card .content{padding:16px}
.tag{display:inline-flex;align-items:center;gap:6px;padding:4px 10px;border-radius:999px;background:white;border:1px solid var(--border);font-size:.8rem;color:var(--muted)}

.list{display:grid;gap:12px;padding:12px}
.item{display:grid;grid-template-columns:120px 1fr;gap:14px;background:white;border:1px solid var(--border);border-radius:14px;overflow:hidden}
.thumb{background:linear-gradient(135deg, var(--brand) 0%, var(--brand-dark) 100%);height:100%}
.item .meta{display:flex;gap:8px;flex-wrap:wrap;margin-top:6px}
.item h4{margin:2px 0 4px}
.item p{margin:0;color:var(--muted)}

/* Sidebar */
.side-card{background:white;border:1px solid var(--border);border-radius:16px;overflow:hidden}
.side-card h3{margin:0;padding:14px 16px;border-bottom:1px solid var(--border)}
.side-card .body{padding:12px 16px}

/* Footer */
footer{margin-top:32px;border-top:1px solid var(--border);background:white}
.foot-inner{padding:18px 0;display:flex;flex-wrap:wrap;align-items:center;justify-content:space-between;gap:12px}

/* Responsive */
@media (max-width: 900px){
  .grid{grid-template-columns:1fr}
}
@media (max-width: 720px){
  .menu{display:none}
  .menu.open{display:flex}
  .hamburger{display:inline-flex}
  .item{grid-template-columns:1fr}
  .thumb{height:140px}
}

/* Focus states */
:focus-visible{outline:3px solid var(--focus);outline-offset:2px;border-radius:8px}

  </style>
</head>
<body>
  <!-- Topbar -->
  <header>
    <div class="topbar">
      <div class="container row">
        <div class="brand" aria-label="InfoNews">
          <span class="brand-logo" aria-hidden="true">IN</span>
          <span class="brand-title">InfoNews</span>
        </div>
        <div class="row" style="gap:10px">
          <span id="datetime" aria-live="polite"></span>
          <a class="badge" href="mailto:bilmutinga@gmail.com">Nous contacter</a>
        </div>
      </div>
    </div><nav>
  <div class="container nav-inner">
    <button class="hamburger" id="menuBtn" aria-label="Ouvrir le menu">☰ Menu</button>
    <div class="menu" id="menu">
      <a href="#a-la-une" class="active">À la Une</a>
      <a href="#afrique">Afrique</a>
      <a href="#europe">Europe</a>
      <a href="#ameriques">Amériques</a>
      <a href="#asie">Asie</a>
      <a href="#economie">Économie</a>
      <a href="#tech">Tech</a>
      <a href="#sport">Sport</a>
      <a href="#culture">Culture</a>
    </div>
    <div class="search" role="search">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
      <label for="q" class="sr-only">Rechercher</label>
      <input id="q" type="search" placeholder="Rechercher une actualité... (ex: élection, RDC, foot)" />
    </div>
  </div>
</nav>

  </header>  <!-- Hero -->  <section class="hero">
    <div class="container hero-inner">
      <span class="badge">DERNIÈRE MINUTE</span>
      <h1 class="headline">L'actualité du monde, en un clin d'œil.</h1>
      <p class="sub">InfoNews vous apporte des dépêches et des analyses sur la politique, l'économie, la tech, le sport et la culture, partout dans le monde.</p>
    </div>
  </section>  <!-- Main -->  <main class="container" id="a-la-une">
    <div class="grid">
      <section class="card" aria-labelledby="une-title">
        <div class="content">
          <div style="display:flex;align-items:center;justify-content:space-between;gap:12px">
            <h2 id="une-title" style="margin:0">À la Une</h2>
            <span class="tag"><span aria-hidden="true">⏱</span><span>Mis à jour <time id="lastUpdate">—</time></span></span>
          </div>
        </div>
        <div class="list" id="list-une">
          <!-- Éléments d'actualité (exemples statiques, remplacez par votre contenu) -->
          <article class="item" data-tags="politique europe union">
            <div class="thumb" aria-hidden="true"></div>
            <div class="content">
              <div class="meta"><span class="tag">Europe</span><span class="tag">Politique</span><time class="tag" datetime="2025-08-10">10 août 2025</time></div>
              <h4>Sommet européen : feuille de route commune sur l'énergie et la sécurité</h4>
              <p>Les dirigeants adoptent un plan coordonné visant à stabiliser les prix et renforcer les stocks stratégiques.</p>
            </div>
          </article><article class="item" data-tags="rdc afrique economie minerais">
        <div class="thumb" aria-hidden="true"></div>
        <div class="content">
          <div class="meta"><span class="tag">Afrique</span><span class="tag">Économie</span><time class="tag" datetime="2025-08-09">9 août 2025</time></div>
          <h4>RDC : nouveaux investissements dans la transformation locale des minerais</h4>
          <p>Un consortium annonce des usines orientées vers la valeur ajoutée et la création d'emplois.</p>
        </div>
      </article>

      <article class="item" data-tags="tech innovation ia monde">
        <div class="thumb" aria-hidden="true"></div>
        <div class="content">
          <div class="meta"><span class="tag">Tech</span><span class="tag">Innovation</span><time class="tag" datetime="2025-08-08">8 août 2025</time></div>
          <h4>Intelligence artificielle : percée majeure dans l'efficience énergétique des modèles</h4>
          <p>Des chercheurs dévoilent une technique réduisant la consommation tout en améliorant la précision.</p>
        </div>
      </article>

      <article class="item" data-tags="sport football coupe monde qualifs">
        <div class="thumb" aria-hidden="true"></div>
        <div class="content">
          <div class="meta"><span class="tag">Sport</span><span class="tag">Football</span><time class="tag" datetime="2025-08-07">7 août 2025</time></div>
          <h4>Qualifs Coupe du monde : rebond spectaculaire lors de la dernière journée</h4>
          <p>Un scénario renversant relance la course à la qualification dans plusieurs confédérations.</p>
        </div>
      </article>
    </div>
  </section>

  <aside>
    <section class="side-card" id="newsletter">
      <h3>Newsletter</h3>
      <div class="body">
        <p>Recevez l'essentiel de l'actualité chaque matin.</p>
        <form onsubmit="subscribe(event)">
          <label for="email" style="display:block;margin-bottom:6px">Votre email</label>
          <input id="email" type="email" required placeholder="votre@email.com" style="width:100%;padding:10px;border:1px solid var(--border);border-radius:12px" />
          <button type="submit" style="margin-top:8px;width:100%;padding:10px 14px;background:var(--brand);color:white;border:0;border-radius:12px;font-weight:700">S'abonner</button>
        </form>
      </div>
    </section>

    <section class="side-card" id="tendances" style="margin-top:16px">
      <h3>Tendances</h3>
      <div class="body">
        <ul style="list-style:none;padding:0;margin:0;display:grid;gap:10px">
          <li><a href="#">Élections & gouvernance</a></li>
          <li><a href="#">Transition énergétique</a></li>
          <li><a href="#">Startups africaines</a></li>
          <li><a href="#">IA & productivité</a></li>
          <li><a href="#">Foot : mercato</a></li>
        </ul>
      </div>
    </section>

    <section class="side-card" id="contact" style="margin-top:16px">
      <h3>Contact</h3>
      <div class="body">
        <p>Rédaction InfoNews</p>
        <p><a href="mailto:bilmutinga@gmail.com">bilmutinga@gmail.com</a></p>
      </div>
    </section>
  </aside>
</div>

<!-- Sections thématiques (exemples) -->
<section class="card" id="afrique" style="margin-top:22px">
  <div class="content"><h2>Afrique</h2></div>
  <div class="list" id="list-afrique">
    <article class="item" data-tags="afrique sante campagne">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Santé</span><time class="tag" datetime="2025-08-05">5 août 2025</time></div>
        <h4>Campagnes de prévention renforcées dans plusieurs capitales</h4>
        <p>Les autorités intensifient la sensibilisation et l'accès aux soins essentiels.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="europe" style="margin-top:22px">
  <div class="content"><h2>Europe</h2></div>
  <div class="list" id="list-europe">
    <article class="item" data-tags="europe climat canicule">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Climat</span><time class="tag" datetime="2025-08-06">6 août 2025</time></div>
        <h4>Vague de chaleur : plans d'urgence activés</h4>
        <p>Plusieurs pays déclenchent des mesures face aux records de températures.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="ameriques" style="margin-top:22px">
  <div class="content"><h2>Amériques</h2></div>
  <div class="list" id="list-ameriques">
    <article class="item" data-tags="ameriques finance marche">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Finance</span><time class="tag" datetime="2025-08-04">4 août 2025</time></div>
        <h4>Les marchés réagissent aux nouvelles orientations monétaires</h4>
        <p>Volatilité accrue après la publication des dernières données macroéconomiques.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="asie" style="margin-top:22px">
  <div class="content"><h2>Asie</h2></div>
  <div class="list" id="list-asie">
    <article class="item" data-tags="asie tech semi-conducteurs">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Tech</span><time class="tag" datetime="2025-08-03">3 août 2025</time></div>
        <h4>Chips : nouvelles alliances pour sécuriser la chaîne d'approvisionnement</h4>
        <p>Les fabricants signent des partenariats stratégiques régionaux.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="economie" style="margin-top:22px">
  <div class="content"><h2>Économie</h2></div>
  <div class="list" id="list-economie">
    <article class="item" data-tags="economie emploi inflation">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Macro</span><time class="tag" datetime="2025-08-02">2 août 2025</time></div>
        <h4>Inflation en recul : quels impacts sur l'emploi ?</h4>
        <p>Les analystes anticipent un atterrissage en douceur dans plusieurs régions.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="tech" style="margin-top:22px">
  <div class="content"><h2>Tech</h2></div>
  <div class="list" id="list-tech">
    <article class="item" data-tags="tech cybersécurité reseaux">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Cybersécurité</span><time class="tag" datetime="2025-08-01">1 août 2025</time></div>
        <h4>Réseaux : nouvelles normes pour renforcer la résilience</h4>
        <p>Les opérateurs accélèrent les mises à niveau d'infrastructure.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="sport" style="margin-top:22px">
  <div class="content"><h2>Sport</h2></div>
  <div class="list" id="list-sport">
    <article class="item" data-tags="sport basket tournoi">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Basket</span><time class="tag" datetime="2025-07-31">31 juil. 2025</time></div>
        <h4>Tournée internationale : les favoris confirment</h4>
        <p>Une préparation réussie avant les compétitions majeures.</p>
      </div>
    </article>
  </div>
</section>

<section class="card" id="culture" style="margin-top:22px">
  <div class="content"><h2>Culture</h2></div>
  <div class="list" id="list-culture">
    <article class="item" data-tags="culture cinema festival">
      <div class="thumb" aria-hidden="true"></div>
      <div class="content">
        <div class="meta"><span class="tag">Cinéma</span><time class="tag" datetime="2025-07-30">30 juil. 2025</time></div>
        <h4>Festivals : palmarès et nouvelles sorties à l'affiche</h4>
        <p>Les réalisateurs émergents bousculent les codes avec des œuvres audacieuses.</p>
      </div>
    </article>
  </div>
</section>

  </main>  <footer>
    <div class="container foot-inner">
      <p>© <span id="year"></span> InfoNews — Tous droits réservés.</p>
      <nav style="display:flex;gap:12px;flex-wrap:wrap">
        <a href="#">À propos</a>
        <a href="#">Publicité</a>
        <a href="#">Mentions légales</a>
        <a href="mailto:bilmutinga@gmail.com">Contact</a>
      </nav>
    </div>
  </footer>  <script>
    // Date/heure dynamiques
    function formatDateTime(d){
      return d.toLocaleString('fr-FR', { dateStyle:'full', timeStyle:'short' });
    }
    const now = new Date();
    document.getElementById('datetime').textContent = formatDateTime(now);
    document.getElementById('lastUpdate').textContent = formatDateTime(now);
    document.getElementById('year').textContent = now.getFullYear();

    // Recherche simple (filtrage côté client)
    const q = document.getElementById('q');
    q.addEventListener('input', () => {
      const term = q.value.trim().toLowerCase();
      document.querySelectorAll('.item').forEach(card => {
        const text = card.innerText.toLowerCase();
        const tags = (card.getAttribute('data-tags')||'').toLowerCase();
        const match = text.includes(term) || tags.includes(term);
        card.style.display = match ? '' : 'none';
      });
    });

    // Menu mobile
    const menuBtn = document.getElementById('menuBtn');
    const menu = document.getElementById('menu');
    menuBtn.addEventListener('click', ()=>{
      menu.classList.toggle('open');
    });

    // Abonnement newsletter (demo)
    function subscribe(e){
      e.preventDefault();
      const input = document.getElementById('email');
      const mail = input.value.trim();
      if(!mail){return}
      alert(`Merci ! Vous recevrez bientôt InfoNews à l'adresse : ${mail}`);
      input.value = '';
    }
    window.subscribe = subscribe;
  </script></body>
</html>