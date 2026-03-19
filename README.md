


<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DAY Consulting — Dane Anselme Youzan</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;font-size:16px}
body{font-family:'DM Sans',sans-serif;background:#0c0c14;color:#f8f4ee;overflow-x:hidden}
/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:100;padding:0 5vw;height:72px;display:flex;align-items:center;justify-content:space-between;transition:background .4s}
nav.scrolled{background:rgba(12,12,20,.92);backdrop-filter:blur(20px);border-bottom:1px solid rgba(200,168,75,.1)}
.nav-logo{font-family:'Playfair Display',serif;font-size:1.5rem;font-weight:900;color:#fff;text-decoration:none;letter-spacing:1px}
.nav-logo span{color:#c8a84b}
.nav-links{display:flex;align-items:center;gap:2.5rem;list-style:none}
.nav-links a{font-size:.78rem;font-weight:500;letter-spacing:2px;text-transform:uppercase;color:#6b6b7a;text-decoration:none;transition:color .3s;position:relative}
.nav-links a:hover{color:#c8a84b}
.lang-toggle{display:flex;border:1px solid rgba(200,168,75,.3);border-radius:4px;overflow:hidden}
.lang-btn{background:none;border:none;padding:5px 12px;font-family:'DM Mono',monospace;font-size:.72rem;color:#6b6b7a;transition:all .3s;cursor:pointer}
.lang-btn.active{background:#c8a84b;color:#0c0c14;font-weight:600}
.menu-toggle{display:none;background:none;border:none;color:#f8f4ee;font-size:1.5rem;cursor:pointer}
/* HERO */
#hero{min-height:100vh;display:flex;align-items:center;position:relative;overflow:hidden;padding:90px 5vw 0}
.hero-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(200,168,75,.04) 1px,transparent 1px),linear-gradient(90deg,rgba(200,168,75,.04) 1px,transparent 1px);background-size:60px 60px;pointer-events:none}
.hero-glow{position:absolute;width:600px;height:600px;background:radial-gradient(circle,rgba(200,168,75,.12) 0%,transparent 70%);right:-100px;top:50%;transform:translateY(-50%);pointer-events:none}
.hero-content{position:relative;z-index:2;max-width:780px}
.hero-eyebrow{display:inline-flex;align-items:center;gap:12px;font-family:'DM Mono',monospace;font-size:.72rem;letter-spacing:3px;text-transform:uppercase;color:#c8a84b;margin-bottom:2rem;animation:fadeUp .8s ease .2s both}
.hero-eyebrow::before{content:'';width:40px;height:1px;background:#c8a84b}
.hero-title{font-family:'Playfair Display',serif;font-size:clamp(3rem,8vw,6.5rem);font-weight:900;line-height:1;letter-spacing:-1px;margin-bottom:1.5rem;animation:fadeUp .8s ease .4s both}
.hero-title em{font-style:italic;color:transparent;-webkit-text-stroke:1px #c8a84b}
.hero-subtitle{font-size:1.05rem;font-weight:300;color:#6b6b7a;line-height:1.7;max-width:500px;margin-bottom:2.5rem;animation:fadeUp .8s ease .6s both}
.hero-tags{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:3rem;animation:fadeUp .8s ease .7s both}
.tag{padding:6px 16px;border:1px solid rgba(200,168,75,.3);border-radius:100px;font-size:.75rem;letter-spacing:1.5px;text-transform:uppercase;color:#c8a84b;background:rgba(200,168,75,.06)}
.hero-ctas{display:flex;gap:16px;flex-wrap:wrap;animation:fadeUp .8s ease .8s both}
.btn-primary{padding:14px 36px;background:#c8a84b;color:#0c0c14;font-weight:600;font-size:.82rem;letter-spacing:2px;text-transform:uppercase;text-decoration:none;border-radius:3px;transition:all .3s;border:none;cursor:pointer;display:inline-block}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(200,168,75,.35)}
.btn-secondary{padding:14px 36px;border:1px solid rgba(200,168,75,.4);color:#f8f4ee;font-size:.82rem;letter-spacing:2px;text-transform:uppercase;text-decoration:none;border-radius:3px;transition:all .3s;display:inline-block}
.btn-secondary:hover{border-color:#c8a84b;color:#c8a84b;transform:translateY(-2px)}
.hero-scroll{position:absolute;bottom:2.5rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;font-family:'DM Mono',monospace;font-size:.65rem;letter-spacing:3px;text-transform:uppercase;color:#6b6b7a;animation:bounce 2s ease-in-out infinite;z-index:2}
.scroll-line{width:1px;height:50px;background:linear-gradient(to bottom,#c8a84b,transparent)}
/* SECTIONS */
section{padding:120px 5vw;position:relative}
.section-label{display:inline-flex;align-items:center;gap:12px;font-family:'DM Mono',monospace;font-size:.7rem;letter-spacing:4px;text-transform:uppercase;color:#c8a84b;margin-bottom:1.2rem}
.section-label::before{content:'';width:30px;height:1px;background:#c8a84b}
.section-title{font-family:'Playfair Display',serif;font-size:clamp(2rem,5vw,3.5rem);font-weight:700;line-height:1.15;margin-bottom:1.2rem}
.section-desc{font-size:1rem;font-weight:300;color:#6b6b7a;line-height:1.8;max-width:540px}
.reveal{opacity:0;transform:translateY(30px);transition:opacity .8s ease,transform .8s ease}
.reveal.visible{opacity:1;transform:translateY(0)}
/* SERVICES */
#services{background:#0c0c14}
.services-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:5rem;flex-wrap:wrap;gap:2rem}
.services-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.5px;background:rgba(200,168,75,.08);border:1px solid rgba(200,168,75,.08)}
.service-card{background:#0c0c14;padding:3rem 2.5rem;position:relative;overflow:hidden;transition:background .4s}
.service-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,#c8a84b,transparent);transform:scaleX(0);transform-origin:left;transition:transform .5s ease}
.service-card:hover{background:rgba(200,168,75,.04)}
.service-card:hover::before{transform:scaleX(1)}
.service-number{font-family:'DM Mono',monospace;font-size:.65rem;letter-spacing:3px;color:rgba(200,168,75,.4);margin-bottom:2rem}
.service-icon{width:52px;height:52px;border:1px solid rgba(200,168,75,.2);border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:1.4rem;margin-bottom:1.5rem;transition:border-color .3s,background .3s}
.service-card:hover .service-icon{border-color:#c8a84b;background:rgba(200,168,75,.08)}
.service-name{font-family:'Playfair Display',serif;font-size:1.35rem;font-weight:700;margin-bottom:1rem;line-height:1.2;color:#f8f4ee}
.service-desc{font-size:.88rem;color:#6b6b7a;line-height:1.75;margin-bottom:1.5rem}
.service-list{list-style:none;display:flex;flex-direction:column;gap:6px}
.service-list li{font-size:.78rem;color:rgba(200,168,75,.8);font-family:'DM Mono',monospace;display:flex;align-items:center;gap:8px}
.service-list li::before{content:'→';color:#c8a84b}
/* PORTFOLIO */
#portfolio{background:rgba(200,168,75,.02)}
.portfolio-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:4rem;flex-wrap:wrap;gap:2rem}
.portfolio-filters{display:flex;gap:8px;flex-wrap:wrap}
.filter-btn{padding:7px 18px;background:none;border:1px solid rgba(200,168,75,.2);border-radius:100px;color:#6b6b7a;font-size:.75rem;letter-spacing:1px;text-transform:uppercase;transition:all .3s;cursor:pointer}
.filter-btn.active,.filter-btn:hover{background:#c8a84b;border-color:#c8a84b;color:#0c0c14}
.portfolio-grid{display:grid;grid-template-columns:repeat(12,1fr);gap:16px}
.portfolio-item{position:relative;overflow:hidden;border-radius:4px;background:#1a1a2e;transition:transform .4s ease}
.portfolio-item:hover{transform:scale(1.01);z-index:2}
.portfolio-item:nth-child(1){grid-column:span 7;grid-row:span 2}
.portfolio-item:nth-child(2){grid-column:span 5}
.portfolio-item:nth-child(3){grid-column:span 5}
.portfolio-item:nth-child(4){grid-column:span 4}
.portfolio-item:nth-child(5){grid-column:span 4}
.portfolio-item:nth-child(6){grid-column:span 4}
.portfolio-thumb{width:100%;padding-top:70%;position:relative;overflow:hidden}
.portfolio-item:first-child .portfolio-thumb{padding-top:100%}
.portfolio-thumb-inner{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:3rem;background:linear-gradient(135deg,#1a1a2e,#0d0d20);transition:transform .6s ease}
.portfolio-item:hover .portfolio-thumb-inner{transform:scale(1.06)}
.portfolio-overlay{position:absolute;inset:0;background:linear-gradient(to top,rgba(12,12,20,.95),rgba(12,12,20,.3) 50%,transparent);display:flex;flex-direction:column;justify-content:flex-end;padding:2rem;opacity:0;transition:opacity .4s}
.portfolio-item:hover .portfolio-overlay{opacity:1}
.portfolio-cat{font-family:'DM Mono',monospace;font-size:.65rem;letter-spacing:3px;text-transform:uppercase;color:#c8a84b;margin-bottom:6px}
.portfolio-title-card{font-family:'Playfair Display',serif;font-size:1.1rem;font-weight:700;line-height:1.2;color:#f8f4ee}
.portfolio-info{padding:1.2rem 1.5rem}
.portfolio-info h3{font-family:'Playfair Display',serif;font-size:1rem;font-weight:700;color:#f8f4ee}
/* ABOUT */
#about{background:#0c0c14}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:center}
.about-visual{position:relative}
.about-frame{width:100%;aspect-ratio:4/5;background:#1a1a2e;border-radius:4px;position:relative;overflow:hidden;display:flex;align-items:center;justify-content:center;font-size:5rem}
.about-frame::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(200,168,75,.06),transparent 50%,rgba(200,168,75,.03))}
.about-badge{position:absolute;bottom:-20px;right:-20px;width:120px;height:120px;background:#c8a84b;border-radius:50%;display:flex;flex-direction:column;align-items:center;justify-content:center;color:#0c0c14;text-align:center}
.about-badge .num{font-family:'Playfair Display',serif;font-size:2.2rem;font-weight:900;line-height:1}
.about-badge .txt{font-size:.62rem;font-weight:600;letter-spacing:1px;text-transform:uppercase;line-height:1.2}
.about-decor{position:absolute;top:-16px;left:-16px;width:80px;height:80px;border-top:2px solid #c8a84b;border-left:2px solid #c8a84b}
.about-text{font-size:.95rem;color:#6b6b7a;line-height:1.85;margin-bottom:1.2rem}
.about-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;margin:2.5rem 0}
.stat-item{padding:1.2rem;border:1px solid rgba(200,168,75,.12);border-radius:4px;text-align:center;background:rgba(200,168,75,.03)}
.stat-num{font-family:'Playfair Display',serif;font-size:2rem;font-weight:900;color:#c8a84b;line-height:1}
.stat-label{font-size:.7rem;letter-spacing:1.5px;text-transform:uppercase;color:#6b6b7a;margin-top:4px}
.skill-row{margin-bottom:1rem}
.skill-top{display:flex;justify-content:space-between;font-size:.78rem;margin-bottom:6px}
.skill-top span:last-child{color:#c8a84b;font-family:'DM Mono',monospace}
.skill-bar{height:3px;background:rgba(200,168,75,.12);border-radius:2px;overflow:hidden}
.skill-fill{height:100%;background:linear-gradient(90deg,#c8a84b,#e8c870);width:0;transition:width 1.2s ease .3s}
/* BLOG */
#blog{background:rgba(200,168,75,.02)}
.blog-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:4rem;flex-wrap:wrap;gap:2rem}
.blog-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:2rem}
.blog-card{background:#1a1a2e;border-radius:4px;overflow:hidden;border:1px solid rgba(200,168,75,.06);transition:transform .4s ease,border-color .3s}
.blog-card:hover{transform:translateY(-6px);border-color:rgba(200,168,75,.2)}
.blog-thumb{height:200px;display:flex;align-items:center;justify-content:center;font-size:3rem;background:linear-gradient(135deg,#0c0c14,#1a1a2e);position:relative}
.blog-thumb-tag{position:absolute;top:16px;left:16px;padding:4px 12px;background:#c8a84b;color:#0c0c14;font-size:.65rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;border-radius:2px}
.blog-body{padding:1.8rem}
.blog-meta{font-family:'DM Mono',monospace;font-size:.68rem;color:rgba(200,168,75,.6);margin-bottom:1rem}
.blog-title{font-family:'Playfair Display',serif;font-size:1.2rem;font-weight:700;line-height:1.3;margin-bottom:.8rem;color:#f8f4ee;transition:color .3s}
.blog-card:hover .blog-title{color:#c8a84b}
.blog-excerpt{font-size:.85rem;color:#6b6b7a;line-height:1.7;margin-bottom:1.2rem}
.blog-link{font-family:'DM Mono',monospace;font-size:.72rem;letter-spacing:2px;text-transform:uppercase;color:#c8a84b;text-decoration:none}
/* CONTACT */
#contact{background:#0c0c14}
.contact-wrap{display:grid;grid-template-columns:1fr 1.4fr;gap:6rem;align-items:start}
.contact-detail{display:flex;align-items:flex-start;gap:1rem;margin-bottom:1.8rem}
.contact-icon{width:44px;height:44px;flex-shrink:0;border:1px solid rgba(200,168,75,.2);border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:1.1rem;background:rgba(200,168,75,.04)}
.contact-detail-label{font-family:'DM Mono',monospace;font-size:.68rem;letter-spacing:2px;text-transform:uppercase;color:#c8a84b;margin-bottom:4px}
.contact-detail-value{font-size:.95rem;color:#f8f4ee}
.contact-divider{height:1px;background:linear-gradient(90deg,rgba(200,168,75,.2),transparent);margin:2.5rem 0}
.availability{display:flex;align-items:center;gap:10px;font-size:.82rem;color:#6b6b7a}
.avail-dot{width:8px;height:8px;border-radius:50%;background:#4ade80;box-shadow:0 0 8px #4ade80;animation:pulse-dot 2s ease-in-out infinite}
.contact-form{display:flex;flex-direction:column;gap:1.2rem}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem}
.form-group{display:flex;flex-direction:column;gap:8px}
.form-label{font-family:'DM Mono',monospace;font-size:.68rem;letter-spacing:2px;text-transform:uppercase;color:#c8a84b}
.form-input,.form-textarea,.form-select{background:rgba(200,168,75,.04);border:1px solid rgba(200,168,75,.12);border-radius:4px;padding:13px 16px;font-family:'DM Sans',sans-serif;font-size:.9rem;color:#f8f4ee;outline:none;width:100%;transition:border-color .3s}
.form-input:focus,.form-textarea:focus,.form-select:focus{border-color:#c8a84b}
.form-input::placeholder,.form-textarea::placeholder{color:rgba(107,107,122,.6)}
.form-textarea{resize:vertical;min-height:140px}
.form-select option{background:#1a1a2e;color:#f8f4ee}
.form-submit{padding:15px 40px;background:#c8a84b;color:#0c0c14;font-size:.82rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;border:none;border-radius:3px;transition:all .3s;cursor:pointer;align-self:flex-start}
.form-submit:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(200,168,75,.3)}
.form-success{display:none;padding:16px;background:rgba(74,222,128,.08);border:1px solid rgba(74,222,128,.2);border-radius:4px;color:#4ade80;font-size:.88rem;text-align:center}
/* FOOTER */
footer{background:#1a1a2e;padding:4rem 5vw 2rem;border-top:1px solid rgba(200,168,75,.08)}
.footer-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:3rem;flex-wrap:wrap;gap:3rem}
.footer-tagline{font-size:.85rem;color:#6b6b7a;line-height:1.7;max-width:260px}
.footer-links h4{font-family:'DM Mono',monospace;font-size:.68rem;letter-spacing:3px;text-transform:uppercase;color:#c8a84b;margin-bottom:1.2rem}
.footer-links ul{list-style:none;display:flex;flex-direction:column;gap:10px}
.footer-links a{font-size:.88rem;color:#6b6b7a;text-decoration:none;transition:color .3s}
.footer-links a:hover{color:#f8f4ee}
.footer-bottom{display:flex;justify-content:space-between;align-items:center;padding-top:2rem;border-top:1px solid rgba(200,168,75,.06);flex-wrap:wrap;gap:1rem}
.footer-copy{font-family:'DM Mono',monospace;font-size:.7rem;color:rgba(107,107,122,.5)}
.footer-copy span{color:#c8a84b}
/* MOBILE MENU */
.mobile-menu{position:fixed;inset:0;z-index:200;background:rgba(12,12,20,.98);backdrop-filter:blur(20px);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:2rem;transform:translateX(100%);transition:transform .4s ease}
.mobile-menu.open{transform:translateX(0)}
.mobile-menu a{font-family:'Playfair Display',serif;font-size:2rem;font-weight:700;color:#f8f4ee;text-decoration:none;transition:color .3s}
.mobile-menu a:hover{color:#c8a84b}
.mobile-close{position:absolute;top:24px;right:24px;background:none;border:none;color:#6b6b7a;font-size:1.5rem;cursor:pointer}
/* ANIMATIONS */
@keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
@keyframes bounce{0%,100%{transform:translateX(-50%) translateY(0)}50%{transform:translateX(-50%) translateY(10px)}}
@keyframes pulse-dot{0%,100%{transform:scale(1);opacity:1}50%{transform:scale(1.3);opacity:.7}}
/* RESPONSIVE */
@media(max-width:900px){.about-grid{grid-template-columns:1fr;gap:3rem}.contact-wrap{grid-template-columns:1fr;gap:3rem}.portfolio-grid{display:flex;flex-direction:column}.form-row{grid-template-columns:1fr}.nav-links{display:none}.menu-toggle{display:block}}
@media(max-width:600px){section{padding:80px 6vw}.footer-top{flex-direction:column}}
</style>
</head>
<body>

<div class="mobile-menu" id="mobileMenu">
  <button class="mobile-close" onclick="toggleMenu()">&#10005;</button>
  <a href="#services" onclick="toggleMenu()">Services</a>
  <a href="#portfolio" onclick="toggleMenu()">Portfolio</a>
  <a href="#about" onclick="toggleMenu()">&#192; propos</a>
  <a href="#blog" onclick="toggleMenu()">Blog</a>
  <a href="#contact" onclick="toggleMenu()">Contact</a>
</div>

<nav id="navbar">
  <a href="#hero" class="nav-logo">DAY<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#about">&#192; propos</a></li>
    <li><a href="#blog">Blog</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <div style="display:flex;align-items:center;gap:16px">
    <div class="lang-toggle">
      <button class="lang-btn active" onclick="setLang('fr')">FR</button>
      <button class="lang-btn" onclick="setLang('en')">EN</button>
    </div>
    <button class="menu-toggle" onclick="toggleMenu()">&#9776;</button>
  </div>
</nav>

<section id="hero">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-content">
    <div class="hero-eyebrow" data-fr="Consultant Digital &amp; Audiovisuel" data-en="Digital &amp; Audiovisual Consultant">Consultant Digital &amp; Audiovisuel</div>
    <h1 class="hero-title">
      <span data-fr="Cr&#233;er." data-en="Create.">Cr&#233;er.</span><br>
      <em data-fr="Piloter." data-en="Lead.">Piloter.</em><br>
      <span data-fr="D&#233;velopper." data-en="Grow.">D&#233;velopper.</span>
    </h1>
    <p class="hero-subtitle" data-fr="DAY Consulting accompagne vos projets audiovisuels, digitaux et de gestion &#8212; de la conception &#224; l&#8217;ex&#233;cution, avec cr&#233;ativit&#233; et rigueur." data-en="DAY Consulting supports your audiovisual, digital and management projects &#8212; from conception to execution, with creativity and precision.">DAY Consulting accompagne vos projets audiovisuels, digitaux et de gestion &#8212; de la conception &#224; l&#8217;ex&#233;cution, avec cr&#233;ativit&#233; et rigueur.</p>
    <div class="hero-tags">
      <span class="tag">Audiovisuel</span>
      <span class="tag">Web Design</span>
      <span class="tag">Chef de Projet</span>
      <span class="tag">Comptabilit&#233;</span>
    </div>
    <div class="hero-ctas">
      <a href="#services" class="btn-primary" data-fr="Voir mes services" data-en="My Services">Voir mes services</a>
      <a href="#contact" class="btn-secondary" data-fr="Me contacter" data-en="Get in touch">Me contacter</a>
    </div>
  </div>
  <div class="hero-scroll"><div class="scroll-line"></div><span>D&#233;filer</span></div>
</section>

<section id="services">
  <div class="services-header reveal">
    <div>
      <div class="section-label">Ce que je fais</div>
      <h2 class="section-title" data-fr="Mes Services" data-en="My Services">Mes Services</h2>
    </div>
    <p class="section-desc" data-fr="Une offre compl&#232;te pour vos besoins cr&#233;atifs, digitaux et de gestion." data-en="A complete offer for your creative, digital and business needs.">Une offre compl&#232;te pour vos besoins cr&#233;atifs, digitaux et de gestion.</p>
  </div>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-number">01</div>
      <div class="service-icon">&#127916;</div>
      <div class="service-name" data-fr="Production Audiovisuelle" data-en="Audiovisual Production">Production Audiovisuelle</div>
      <p class="service-desc" data-fr="Clips musicaux, contenus digitaux, t&#233;l&#233;-r&#233;alit&#233;. Un regard artistique au service de votre vision." data-en="Music videos, digital content, reality TV. An artistic eye at the service of your vision.">Clips musicaux, contenus digitaux, t&#233;l&#233;-r&#233;alit&#233;. Un regard artistique au service de votre vision.</p>
      <ul class="service-list">
        <li data-fr="Direction &amp; Assistance r&#233;alisation" data-en="Direction &amp; AD">Direction &amp; Assistance r&#233;alisation</li>
        <li data-fr="Gestion de plateau" data-en="Set management">Gestion de plateau</li>
        <li data-fr="Coordination technique" data-en="Technical coordination">Coordination technique</li>
        <li data-fr="Post-production" data-en="Post-production">Post-production</li>
      </ul>
    </div>
    <div class="service-card reveal">
      <div class="service-number">02</div>
      <div class="service-icon">&#127760;</div>
      <div class="service-name" data-fr="Web Design &amp; Identit&#233; Visuelle" data-en="Web Design &amp; Visual Identity">Web Design &amp; Identit&#233; Visuelle</div>
      <p class="service-desc" data-fr="Sites vitrines professionnels et identit&#233;s visuelles m&#233;morables qui convertissent." data-en="Professional websites and memorable visual identities that convert.">Sites vitrines professionnels et identit&#233;s visuelles m&#233;morables qui convertissent.</p>
      <ul class="service-list">
        <li data-fr="Site vitrine professionnel" data-en="Professional website">Site vitrine professionnel</li>
        <li data-fr="Identit&#233; visuelle &amp; branding" data-en="Visual identity &amp; branding">Identit&#233; visuelle &amp; branding</li>
        <li data-fr="Carte de visite &amp; print" data-en="Business card &amp; print">Carte de visite &amp; print</li>
        <li data-fr="Marketing digital" data-en="Digital marketing">Marketing digital</li>
      </ul>
    </div>
    <div class="service-card reveal">
      <div class="service-number">03</div>
      <div class="service-icon">&#128202;</div>
      <div class="service-name" data-fr="Gestion &amp; Comptabilit&#233;" data-en="Management &amp; Accounting">Gestion &amp; Comptabilit&#233;</div>
      <p class="service-desc" data-fr="Accompagnement administratif et gestion comptable pour TPE/PME." data-en="Administrative support and accounting management for SMEs.">Accompagnement administratif et gestion comptable pour TPE/PME.</p>
      <ul class="service-list">
        <li data-fr="Suivi comptable &amp; facturation" data-en="Accounting &amp; invoicing">Suivi comptable &amp; facturation</li>
        <li data-fr="Gestion administrative" data-en="Administrative management">Gestion administrative</li>
        <li data-fr="Tableaux de bord &amp; reporting" data-en="Dashboards &amp; reporting">Tableaux de bord &amp; reporting</li>
        <li data-fr="Conseil en organisation" data-en="Organizational consulting">Conseil en organisation</li>
      </ul>
    </div>
    <div class="service-card reveal">
      <div class="service-number">04</div>
      <div class="service-icon">&#127919;</div>
      <div class="service-name" data-fr="Chef de Projet Digital" data-en="Digital Project Manager">Chef de Projet Digital</div>
      <p class="service-desc" data-fr="Pilotage de projets cr&#233;atifs et digitaux de A &#224; Z." data-en="End-to-end management of creative and digital projects.">Pilotage de projets cr&#233;atifs et digitaux de A &#224; Z.</p>
      <ul class="service-list">
        <li data-fr="Coordination d&#8217;&#233;quipes" data-en="Team coordination">Coordination d&#8217;&#233;quipes</li>
        <li data-fr="Planification &amp; suivi" data-en="Planning &amp; tracking">Planification &amp; suivi</li>
        <li data-fr="Gestion budg&#233;taire" data-en="Budget management">Gestion budg&#233;taire</li>
        <li data-fr="Reporting client" data-en="Client reporting">Reporting client</li>
      </ul>
    </div>
  </div>
</section>

<section id="portfolio">
  <div class="portfolio-header reveal">
    <div>
      <div class="section-label">R&#233;alisations</div>
      <h2 class="section-title" data-fr="Portfolio" data-en="Portfolio">Portfolio</h2>
    </div>
    <div class="portfolio-filters">
      <button class="filter-btn active" data-filter="all">Tout</button>
      <button class="filter-btn" data-filter="av">Audiovisuel</button>
      <button class="filter-btn" data-filter="web">Web</button>
      <button class="filter-btn" data-filter="gestion">Gestion</button>
    </div>
  </div>
  <div class="portfolio-grid reveal">
    <div class="portfolio-item" data-category="av">
      <div class="portfolio-thumb"><div class="portfolio-thumb-inner">&#127916;</div><div class="portfolio-overlay"><div class="portfolio-cat">Clip Musical</div><div class="portfolio-title-card">Wantch&#233; &#8212; Djamo, No Cap, Bahi</div></div></div>
      <div class="portfolio-info"><div class="portfolio-cat">Assistant R&#233;alisateur &middot; 2024&#8211;2025</div><h3>Wantch&#233; &#8212; Clips officiels</h3></div>
    </div>
    <div class="portfolio-item" data-category="av">
      <div class="portfolio-thumb"><div class="portfolio-thumb-inner">&#127925;</div><div class="portfolio-overlay"><div class="portfolio-cat">Clip Musical</div><div class="portfolio-title-card">Korey Lo &#8212; Come Back, Petit Mouvement, Gbozon</div></div></div>
      <div class="portfolio-info"><div class="portfolio-cat">Assistant R&#233;alisateur &middot; 2024&#8211;2025</div><h3>Korey Lo &#8212; Clips officiels</h3></div>
    </div>
    <div class="portfolio-item" data-category="av">
      <div class="portfolio-thumb"><div class="portfolio-thumb-inner">&#128250;</div><div class="portfolio-overlay"><div class="portfolio-cat">T&#233;l&#233;-r&#233;alit&#233;</div><div class="portfolio-title-card">Amour sous tension &#8212; Sowa Prod</div></div></div>
      <div class="portfolio-info"><div class="portfolio-cat">Asst. R&#233;gie &amp; Cam&#233;ra &middot; F&#233;v&#8211;Mars 2026</div><h3>Amour sous tension &#8212; Sowa Prod</h3></div>
    </div>
    <div class="portfolio-item" data-category="web">
      <div class="portfolio-thumb"><div class="portfolio-thumb-inner">&#127760;</div><div class="portfolio-overlay"><div class="portfolio-cat">Web Design</div><div class="portfolio-title-card">DAY Consulting &#8212; Site vitrine</div></div></div>
      <div class="portfolio-info"><div class="portfolio-cat">Web Design &middot; 2026</div><h3>DAY Consulting &#8212; Site vitrine</h3></div>
    </div>
    <div class="portfolio-item" data-category="gestion">
      <div class="portfolio-thumb"><div class="portfolio-thumb-inner">&#128202;</div><div class="portfolio-overlay"><div class="portfolio-cat">Gestion de projet</div><div class="portfolio-title-card">BELT GROUP &#8212; Coordination</div></div></div>
      <div class="portfolio-info"><div class="portfolio-cat">Assistance Direction &middot; 2018</div><h3>BELT GROUP &#8212; Assistance Direction</h3></div>
    </div>
    <div class="portfolio-item" data-category="av">
      <div class="portfolio-thumb"><div class="portfolio-thumb-inner">&#128247;</div><div class="portfolio-overlay"><div class="portfolio-cat">Photographie</div><div class="portfolio-title-card">Captation &amp; Direction artistique</div></div></div>
      <div class="portfolio-info"><div class="portfolio-cat">En cours</div><h3>Captation &amp; Direction artistique</h3></div>
    </div>
  </div>
</section>

<section id="about">
  <div class="about-grid">
    <div class="about-visual reveal">
      <div class="about-decor"></div>
      <div class="about-frame">&#127916;
        <div class="about-badge"><div class="num">8+</div><div class="txt">ans exp.</div></div>
      </div>
    </div>
    <div class="reveal">
      <div class="section-label">Qui suis-je ?</div>
      <h2 class="section-title">Dane Anselme Youzan</h2>
      <p class="about-text" data-fr="Professionnel ivoirien polyvalent, je combine cr&#233;ativit&#233;, rigueur et sens du leadership pour piloter des projets &#224; fort impact. De la gestion de clips musicaux pour des artistes reconnus &#224; la coordination de productions t&#233;l&#233;vis&#233;es, j&#8217;apporte une vision globale &#224; chaque projet." data-en="A versatile Ivorian professional, I combine creativity, rigor and leadership to drive high-impact projects. From music videos to TV productions, I bring a holistic vision to every project.">Professionnel ivoirien polyvalent, je combine cr&#233;ativit&#233;, rigueur et sens du leadership pour piloter des projets &#224; fort impact.</p>
      <p class="about-text" data-fr="Issu d&#8217;une formation en Sciences &#201;conomiques et de Gestion, j&#8217;ai forg&#233; mon parcours &#224; travers des exp&#233;riences vari&#233;es&#160;: assistant de direction, secr&#233;taire g&#233;n&#233;ral, commercial, conseiller client." data-en="With a background in Economics and Management, I have built my career through diverse experiences: executive assistant, secretary general, sales rep, customer advisor.">Issu d&#8217;une formation en Sciences &#201;conomiques et de Gestion, j&#8217;ai forg&#233; mon parcours &#224; travers des exp&#233;riences vari&#233;es.</p>
      <div class="about-stats">
        <div class="stat-item"><div class="stat-num">6+</div><div class="stat-label">Clips</div></div>
        <div class="stat-item"><div class="stat-num">3</div><div class="stat-label">Secteurs</div></div>
        <div class="stat-item"><div class="stat-num">2</div><div class="stat-label">Langues</div></div>
      </div>
      <div class="skill-row"><div class="skill-top"><span>Production Audiovisuelle</span><span>85%</span></div><div class="skill-bar"><div class="skill-fill" data-width="85"></div></div></div>
      <div class="skill-row"><div class="skill-top"><span>Gestion de Projet</span><span>80%</span></div><div class="skill-bar"><div class="skill-fill" data-width="80"></div></div></div>
      <div class="skill-row"><div class="skill-top"><span>Web Design &amp; Digital</span><span>70%</span></div><div class="skill-bar"><div class="skill-fill" data-width="70"></div></div></div>
      <div class="skill-row"><div class="skill-top"><span>Gestion &amp; Comptabilit&#233;</span><span>65%</span></div><div class="skill-bar"><div class="skill-fill" data-width="65"></div></div></div>
      <div style="margin-top:2.5rem"><a href="#contact" class="btn-primary">Travaillons ensemble</a></div>
    </div>
  </div>
</section>

<section id="blog">
  <div class="blog-header reveal">
    <div>
      <div class="section-label">Actualit&#233;s &amp; R&#233;flexions</div>
      <h2 class="section-title" data-fr="Blog" data-en="Blog">Blog</h2>
    </div>
    <a href="#" class="btn-secondary" style="padding:10px 24px;font-size:.75rem" data-fr="Tous les articles" data-en="All articles">Tous les articles</a>
  </div>
  <div class="blog-grid">
    <div class="blog-card reveal">
      <div class="blog-thumb">&#127916;<div class="blog-thumb-tag">Audiovisuel</div></div>
      <div class="blog-body">
        <div class="blog-meta">Mars 2026 &middot; 5 min</div>
        <h3 class="blog-title" data-fr="Les coulisses d&#8217;une t&#233;l&#233;-r&#233;alit&#233;" data-en="Behind the scenes of reality TV">Les coulisses d&#8217;une t&#233;l&#233;-r&#233;alit&#233;</h3>
        <p class="blog-excerpt" data-fr="Mon exp&#233;rience sur Amour sous tension avec Sowa Prod." data-en="My experience on Amour sous tension with Sowa Prod.">Mon exp&#233;rience sur Amour sous tension avec Sowa Prod.</p>
        <a href="#" class="blog-link">Lire &#8594;</a>
      </div>
    </div>
    <div class="blog-card reveal">
      <div class="blog-thumb">&#127760;<div class="blog-thumb-tag">Digital</div></div>
      <div class="blog-body">
        <div class="blog-meta">F&#233;v. 2026 &middot; 4 min</div>
        <h3 class="blog-title" data-fr="Cr&#233;er une identit&#233; visuelle forte" data-en="Building a strong visual identity">Cr&#233;er une identit&#233; visuelle forte</h3>
        <p class="blog-excerpt" data-fr="Pourquoi l&#8217;identit&#233; visuelle est le premier investissement d&#8217;une PME." data-en="Why visual identity is the first investment for an SME.">Pourquoi l&#8217;identit&#233; visuelle est le premier investissement d&#8217;une PME.</p>
        <a href="#" class="blog-link">Lire &#8594;</a>
      </div>
    </div>
    <div class="blog-card reveal">
      <div class="blog-thumb">&#128202;<div class="blog-thumb-tag">Gestion</div></div>
      <div class="blog-body">
        <div class="blog-meta">Janv. 2026 &middot; 6 min</div>
        <h3 class="blog-title" data-fr="5 outils gratuits pour votre comptabilit&#233;" data-en="5 free tools for your accounting">5 outils gratuits pour votre comptabilit&#233;</h3>
        <p class="blog-excerpt" data-fr="Indy, Abby, Tiime... g&#233;rez vos finances sans d&#233;bourser un centime." data-en="Indy, Abby, Tiime... manage your finances for free.">Indy, Abby, Tiime... g&#233;rez vos finances sans d&#233;bourser un centime.</p>
        <a href="#" class="blog-link">Lire &#8594;</a>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="contact-wrap">
    <div class="contact-info reveal">
      <div class="section-label">Travaillons ensemble</div>
      <h2 class="section-title" data-fr="Pr&#234;t &#224; d&#233;marrer ?" data-en="Ready to start?">Pr&#234;t &#224; d&#233;marrer ?</h2>
      <p class="section-desc" style="margin-bottom:2.5rem" data-fr="Clips, sites, comptabilit&#233; ou gestion de projet &#8212; je suis l&#224; pour vous." data-en="Videos, websites, accounting or project management &#8212; I am here for you.">Clips, sites, comptabilit&#233; ou gestion de projet &#8212; je suis l&#224; pour vous.</p>
      <div class="contact-detail"><div class="contact-icon">&#128222;</div><div><div class="contact-detail-label">T&#233;l&#233;phone</div><div class="contact-detail-value">(+225) 07 77 87 02 19</div></div></div>
      <div class="contact-detail"><div class="contact-icon">&#9993;</div><div><div class="contact-detail-label">Email</div><div class="contact-detail-value">dannyouzan@gmail.com</div></div></div>
      <div class="contact-detail"><div class="contact-icon">&#128205;</div><div><div class="contact-detail-label">Localisation</div><div class="contact-detail-value">Rosiers 5e programme, Abidjan, C&#244;te d&#8217;Ivoire</div></div></div>
      <div class="contact-divider"></div>
      <div class="availability"><div class="avail-dot"></div><span data-fr="Disponible pour de nouvelles missions" data-en="Available for new projects">Disponible pour de nouvelles missions</span></div>
    </div>
    <div class="reveal">
      <form class="contact-form" id="contactForm" onsubmit="handleSubmit(event)">
        <div class="form-row">
          <div class="form-group"><label class="form-label">Nom complet</label><input class="form-input" type="text" required placeholder="Jean Kouassi"></div>
          <div class="form-group"><label class="form-label">Email</label><input class="form-input" type="email" required placeholder="jean@exemple.com"></div>
        </div>
        <div class="form-group">
          <label class="form-label">Sujet</label>
          <select class="form-select" required>
            <option value="">Choisissez un service...</option>
            <option>Production Audiovisuelle</option>
            <option>Web Design &amp; Identit&#233; visuelle</option>
            <option>Gestion &amp; Comptabilit&#233;</option>
            <option>Chef de Projet</option>
            <option>Autre demande</option>
          </select>
        </div>
        <div class="form-group"><label class="form-label">Message</label><textarea class="form-textarea" required placeholder="D&#233;crivez votre projet..."></textarea></div>
        <button type="submit" class="form-submit">Envoyer &#8594;</button>
        <div class="form-success" id="formSuccess">&#10003; Message envoy&#233; ! R&#233;ponse sous 24h.</div>
      </form>
    </div>
  </div>
</section>

<footer>
  <div class="footer-top">
    <div>
      <a href="#hero" class="nav-logo" style="display:block;margin-bottom:1rem">DAY<span>.</span></a>
      <p class="footer-tagline" data-fr="Consultant Digital &amp; Audiovisuel. Cr&#233;er, piloter et d&#233;velopper vos projets avec passion." data-en="Digital &amp; Audiovisual Consultant. Creating, leading and growing your projects with passion.">Consultant Digital &amp; Audiovisuel. Cr&#233;er, piloter et d&#233;velopper vos projets avec passion.</p>
    </div>
    <div class="footer-links">
      <h4>Navigation</h4>
      <ul>
        <li><a href="#services">Services</a></li>
        <li><a href="#portfolio">Portfolio</a></li>
        <li><a href="#about">&#192; propos</a></li>
        <li><a href="#blog">Blog</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
    <div class="footer-links">
      <h4>Services</h4>
      <ul>
        <li><a href="#services">Production Audiovisuelle</a></li>
        <li><a href="#services">Web Design</a></li>
        <li><a href="#services">Gestion &amp; Comptabilit&#233;</a></li>
        <li><a href="#services">Chef de Projet</a></li>
      </ul>
    </div>
    <div class="footer-links">
      <h4>Contact</h4>
      <ul>
        <li><a href="mailto:dannyouzan@gmail.com">dannyouzan@gmail.com</a></li>
        <li>(+225) 07 77 87 02 19</li>
        <li>Abidjan, C&#244;te d&#8217;Ivoire</li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">&#169; 2026 <span>DAY Consulting</span> &#8212; Dane Anselme Youzan. Tous droits r&#233;serv&#233;s.</div>
    <div class="footer-copy">Abidjan &middot; C&#244;te d&#8217;Ivoire</div>
  </div>
</footer>

<script>
window.addEventListener('scroll',function(){document.getElementById('navbar').classList.toggle('scrolled',window.scrollY>50)});
function toggleMenu(){document.getElementById('mobileMenu').classList.toggle('open')}
var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting){e.target.classList.add('visible');e.target.querySelectorAll('.skill-fill').forEach(function(b){b.style.width=b.dataset.width+'%'})}})},{threshold:.1});
document.querySelectorAll('.reveal').forEach(function(el){obs.observe(el)});
document.querySelectorAll('.filter-btn').forEach(function(btn){btn.addEventListener('click',function(){document.querySelectorAll('.filter-btn').forEach(function(b){b.classList.remove('active')});btn.classList.add('active');var f=btn.dataset.filter;document.querySelectorAll('.portfolio-item').forEach(function(item){item.style.display=(f==='all'||item.dataset.category===f)?'':'none'})})});
function setLang(lang){document.querySelectorAll('.lang-btn').forEach(function(b){b.classList.toggle('active',b.textContent.toLowerCase()===lang)});document.querySelectorAll('[data-fr]').forEach(function(el){var txt=lang==='fr'?el.dataset.fr:el.dataset.en;if(txt){if(el.tagName==='INPUT'||el.tagName==='TEXTAREA'){el.placeholder=txt}else{el.textContent=txt}}})}
function handleSubmit(e){e.preventDefault();var btn=e.target.querySelector('.form-submit');btn.textContent='Envoi...';btn.disabled=true;setTimeout(function(){e.target.reset();btn.style.display='none';document.getElementById('formSuccess').style.display='block'},1200)}
document.querySelectorAll('a[href^="#"]').forEach(function(a){a.addEventListener('click',function(e){var t=document.querySelector(a.getAttribute('href'));if(t){e.preventDefault();window.scrollTo({top:t.getBoundingClientRect().top+window.scrollY-72,behavior:'smooth'})}})});
</script>

</body>
</html>