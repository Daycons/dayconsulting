<!DOCTYPE html>

<html lang="fr" data-lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DAY Consulting — Dane Anselme Youzan</title>
<meta name="description" content="DAY Consulting — Consultant Digital & Audiovisuel, Chef de Projet, Consultant Comptabilité. Côte d'Ivoire.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ═══════════════════════════════════════════════════
   RESET & VARIABLES
═══════════════════════════════════════════════════ */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–ink:     #0c0c14;
–ink2:    #1a1a2e;
–gold:    #c8a84b;
–gold2:   #e8c870;
–cream:   #f8f4ee;
–cream2:  #ede8df;
–smoke:   #6b6b7a;
–white:   #ffffff;
–ff-display: ‘Playfair Display’, serif;
–ff-body:    ‘DM Sans’, sans-serif;
–ff-mono:    ‘DM Mono’, monospace;
–ease:    cubic-bezier(0.16, 1, 0.3, 1);
}

html { scroll-behavior: smooth; font-size: 16px; }

body {
font-family: var(–ff-body);
background: var(–ink);
color: var(–cream);
overflow-x: hidden;
cursor: none;
}

/* Custom cursor */
.cursor {
width: 10px; height: 10px;
background: var(–gold);
border-radius: 50%;
position: fixed; top: 0; left: 0;
pointer-events: none; z-index: 9999;
transition: transform 0.15s var(–ease), opacity 0.3s;
transform: translate(-50%, -50%);
}
.cursor-ring {
width: 36px; height: 36px;
border: 1px solid rgba(200,168,75,0.5);
border-radius: 50%;
position: fixed; top: 0; left: 0;
pointer-events: none; z-index: 9998;
transition: transform 0.4s var(–ease), width 0.3s, height 0.3s, opacity 0.3s;
transform: translate(-50%, -50%);
}
body:not(:hover) .cursor, body:not(:hover) .cursor-ring { opacity: 0; }

a, button { cursor: none; }

/* ═══════════════════════════════════════════════════
NAV
═══════════════════════════════════════════════════ */
nav {
position: fixed; top: 0; left: 0; right: 0;
z-index: 100;
padding: 0 5vw;
height: 72px;
display: flex; align-items: center; justify-content: space-between;
transition: background 0.4s, backdrop-filter 0.4s, border-bottom 0.4s;
}
nav.scrolled {
background: rgba(12,12,20,0.9);
backdrop-filter: blur(20px);
border-bottom: 1px solid rgba(200,168,75,0.1);
}
.nav-logo {
font-family: var(–ff-display);
font-size: 1.4rem;
font-weight: 900;
color: var(–white);
text-decoration: none;
letter-spacing: 1px;
}
.nav-logo span { color: var(–gold); }
.nav-links {
display: flex; align-items: center; gap: 2.5rem;
list-style: none;
}
.nav-links a {
font-size: 0.78rem;
font-weight: 500;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–smoke);
text-decoration: none;
transition: color 0.3s;
position: relative;
}
.nav-links a::after {
content: ‘’; position: absolute; left: 0; bottom: -4px;
width: 0; height: 1px; background: var(–gold);
transition: width 0.3s var(–ease);
}
.nav-links a:hover { color: var(–gold); }
.nav-links a:hover::after { width: 100%; }

.lang-toggle {
display: flex; gap: 0;
border: 1px solid rgba(200,168,75,0.3);
border-radius: 4px; overflow: hidden;
}
.lang-btn {
background: none; border: none;
padding: 5px 12px;
font-family: var(–ff-mono);
font-size: 0.72rem;
letter-spacing: 1px;
color: var(–smoke);
transition: all 0.3s;
}
.lang-btn.active {
background: var(–gold);
color: var(–ink);
font-weight: 500;
}

.menu-toggle { display: none; }

/* ═══════════════════════════════════════════════════
HERO
═══════════════════════════════════════════════════ */
#hero {
min-height: 100vh;
display: flex; align-items: center;
position: relative; overflow: hidden;
padding: 0 5vw;
}

.hero-bg {
position: absolute; inset: 0; z-index: 0;
}
.hero-bg canvas { position: absolute; inset: 0; opacity: 0.4; }

.hero-grid {
position: absolute; inset: 0;
background-image:
linear-gradient(rgba(200,168,75,0.04) 1px, transparent 1px),
linear-gradient(90deg, rgba(200,168,75,0.04) 1px, transparent 1px);
background-size: 60px 60px;
}

.hero-glow {
position: absolute;
width: 600px; height: 600px;
background: radial-gradient(circle, rgba(200,168,75,0.12) 0%, transparent 70%);
right: -100px; top: 50%;
transform: translateY(-50%);
pointer-events: none;
}

.hero-content {
position: relative; z-index: 2;
max-width: 780px;
}

.hero-eyebrow {
display: inline-flex; align-items: center; gap: 12px;
font-family: var(–ff-mono);
font-size: 0.72rem;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 2rem;
opacity: 0; animation: fadeUp 0.8s var(–ease) 0.2s forwards;
}
.hero-eyebrow::before {
content: ‘’; width: 40px; height: 1px; background: var(–gold);
}

.hero-title {
font-family: var(–ff-display);
font-size: clamp(3rem, 8vw, 6.5rem);
font-weight: 900;
line-height: 1.0;
letter-spacing: -1px;
margin-bottom: 1.5rem;
opacity: 0; animation: fadeUp 0.8s var(–ease) 0.4s forwards;
}
.hero-title em {
font-style: italic;
color: transparent;
-webkit-text-stroke: 1px var(–gold);
}

.hero-subtitle {
font-size: 1.05rem;
font-weight: 300;
color: var(–smoke);
line-height: 1.7;
max-width: 500px;
margin-bottom: 2.5rem;
opacity: 0; animation: fadeUp 0.8s var(–ease) 0.6s forwards;
}

.hero-tags {
display: flex; flex-wrap: wrap; gap: 10px;
margin-bottom: 3rem;
opacity: 0; animation: fadeUp 0.8s var(–ease) 0.7s forwards;
}
.tag {
padding: 6px 16px;
border: 1px solid rgba(200,168,75,0.25);
border-radius: 100px;
font-size: 0.75rem;
letter-spacing: 1.5px;
text-transform: uppercase;
color: var(–gold);
background: rgba(200,168,75,0.06);
}

.hero-ctas {
display: flex; gap: 16px; flex-wrap: wrap;
opacity: 0; animation: fadeUp 0.8s var(–ease) 0.8s forwards;
}
.btn-primary {
padding: 14px 36px;
background: var(–gold);
color: var(–ink);
font-weight: 600;
font-size: 0.82rem;
letter-spacing: 2px;
text-transform: uppercase;
text-decoration: none;
border-radius: 3px;
transition: all 0.3s var(–ease);
position: relative; overflow: hidden;
}
.btn-primary::after {
content: ‘’; position: absolute;
inset: 0; background: rgba(255,255,255,0.15);
transform: translateX(-100%);
transition: transform 0.4s var(–ease);
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 12px 40px rgba(200,168,75,0.3); }
.btn-primary:hover::after { transform: translateX(0); }

.btn-secondary {
padding: 14px 36px;
border: 1px solid rgba(200,168,75,0.4);
color: var(–cream);
font-size: 0.82rem;
letter-spacing: 2px;
text-transform: uppercase;
text-decoration: none;
border-radius: 3px;
transition: all 0.3s var(–ease);
}
.btn-secondary:hover {
border-color: var(–gold);
color: var(–gold);
transform: translateY(-2px);
}

.hero-scroll {
position: absolute; bottom: 2.5rem; left: 50%;
transform: translateX(-50%);
display: flex; flex-direction: column; align-items: center; gap: 8px;
font-family: var(–ff-mono); font-size: 0.65rem;
letter-spacing: 3px; text-transform: uppercase;
color: var(–smoke);
animation: bounce 2s ease-in-out infinite;
z-index: 2;
}
.scroll-line {
width: 1px; height: 50px;
background: linear-gradient(to bottom, var(–gold), transparent);
}

/* ═══════════════════════════════════════════════════
SECTIONS COMMUNES
═══════════════════════════════════════════════════ */
section { padding: 120px 5vw; position: relative; }

.section-label {
display: inline-flex; align-items: center; gap: 12px;
font-family: var(–ff-mono);
font-size: 0.7rem;
letter-spacing: 4px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 1.2rem;
}
.section-label::before {
content: ‘’; width: 30px; height: 1px; background: var(–gold);
}

.section-title {
font-family: var(–ff-display);
font-size: clamp(2rem, 5vw, 3.5rem);
font-weight: 700;
line-height: 1.15;
margin-bottom: 1.2rem;
}

.section-desc {
font-size: 1rem;
font-weight: 300;
color: var(–smoke);
line-height: 1.8;
max-width: 540px;
}

/* Reveal on scroll */
.reveal {
opacity: 0;
transform: translateY(30px);
transition: opacity 0.8s var(–ease), transform 0.8s var(–ease);
}
.reveal.visible { opacity: 1; transform: translateY(0); }

/* ═══════════════════════════════════════════════════
SERVICES
═══════════════════════════════════════════════════ */
#services { background: var(–ink); }

.services-header {
display: flex; justify-content: space-between; align-items: flex-end;
margin-bottom: 5rem; flex-wrap: wrap; gap: 2rem;
}

.services-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 1.5px;
background: rgba(200,168,75,0.08);
border: 1px solid rgba(200,168,75,0.08);
}

.service-card {
background: var(–ink);
padding: 3rem 2.5rem;
position: relative; overflow: hidden;
transition: background 0.4s;
}
.service-card::before {
content: ‘’; position: absolute;
top: 0; left: 0; right: 0; height: 2px;
background: linear-gradient(90deg, var(–gold), transparent);
transform: scaleX(0); transform-origin: left;
transition: transform 0.5s var(–ease);
}
.service-card:hover { background: rgba(200,168,75,0.04); }
.service-card:hover::before { transform: scaleX(1); }

.service-number {
font-family: var(–ff-mono);
font-size: 0.65rem;
letter-spacing: 3px;
color: rgba(200,168,75,0.4);
margin-bottom: 2rem;
}

.service-icon {
width: 52px; height: 52px;
border: 1px solid rgba(200,168,75,0.2);
border-radius: 8px;
display: flex; align-items: center; justify-content: center;
font-size: 1.4rem;
margin-bottom: 1.5rem;
transition: border-color 0.3s, background 0.3s;
}
.service-card:hover .service-icon {
border-color: var(–gold);
background: rgba(200,168,75,0.08);
}

.service-name {
font-family: var(–ff-display);
font-size: 1.35rem;
font-weight: 700;
margin-bottom: 1rem;
line-height: 1.2;
}

.service-desc {
font-size: 0.88rem;
color: var(–smoke);
line-height: 1.75;
margin-bottom: 1.5rem;
}

.service-list {
list-style: none;
display: flex; flex-direction: column; gap: 6px;
}
.service-list li {
font-size: 0.78rem;
color: rgba(200,168,75,0.7);
font-family: var(–ff-mono);
letter-spacing: 0.5px;
display: flex; align-items: center; gap: 8px;
}
.service-list li::before {
content: ‘→’; color: var(–gold); font-size: 0.7rem;
}

/* ═══════════════════════════════════════════════════
PORTFOLIO
═══════════════════════════════════════════════════ */
#portfolio { background: rgba(200,168,75,0.02); }

.portfolio-header {
display: flex; justify-content: space-between; align-items: flex-end;
margin-bottom: 4rem; flex-wrap: wrap; gap: 2rem;
}

.portfolio-filters {
display: flex; gap: 8px; flex-wrap: wrap;
}
.filter-btn {
padding: 7px 18px;
background: none;
border: 1px solid rgba(200,168,75,0.2);
border-radius: 100px;
color: var(–smoke);
font-size: 0.75rem;
letter-spacing: 1px;
text-transform: uppercase;
transition: all 0.3s;
}
.filter-btn.active, .filter-btn:hover {
background: var(–gold);
border-color: var(–gold);
color: var(–ink);
}

.portfolio-grid {
display: grid;
grid-template-columns: repeat(12, 1fr);
gap: 16px;
}
.portfolio-item {
position: relative; overflow: hidden;
border-radius: 4px;
background: var(–ink2);
transition: transform 0.4s var(–ease);
}
.portfolio-item:hover { transform: scale(1.01); z-index: 2; }
.portfolio-item:nth-child(1) { grid-column: span 7; grid-row: span 2; }
.portfolio-item:nth-child(2) { grid-column: span 5; }
.portfolio-item:nth-child(3) { grid-column: span 5; }
.portfolio-item:nth-child(4) { grid-column: span 4; }
.portfolio-item:nth-child(5) { grid-column: span 4; }
.portfolio-item:nth-child(6) { grid-column: span 4; }

.portfolio-thumb {
width: 100%; padding-top: 70%;
background: var(–ink2);
position: relative; overflow: hidden;
}
.portfolio-item:first-child .portfolio-thumb { padding-top: 100%; }

.portfolio-thumb-inner {
position: absolute; inset: 0;
display: flex; align-items: center; justify-content: center;
font-size: 3rem;
background: linear-gradient(135deg, var(–ink2), #0d0d20);
transition: transform 0.6s var(–ease);
}
.portfolio-item:hover .portfolio-thumb-inner { transform: scale(1.06); }

.portfolio-overlay {
position: absolute; inset: 0;
background: linear-gradient(to top, rgba(12,12,20,0.95) 0%, rgba(12,12,20,0.3) 50%, transparent 100%);
display: flex; flex-direction: column; justify-content: flex-end;
padding: 2rem;
opacity: 0; transition: opacity 0.4s;
}
.portfolio-item:hover .portfolio-overlay { opacity: 1; }

.portfolio-cat {
font-family: var(–ff-mono);
font-size: 0.65rem;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 6px;
}
.portfolio-title-card {
font-family: var(–ff-display);
font-size: 1.1rem;
font-weight: 700;
line-height: 1.2;
}

.portfolio-info {
padding: 1.2rem 1.5rem;
}
.portfolio-info .portfolio-cat { margin-bottom: 4px; }
.portfolio-info h3 {
font-family: var(–ff-display);
font-size: 1rem;
font-weight: 700;
line-height: 1.3;
color: var(–cream);
}

/* ═══════════════════════════════════════════════════
ABOUT
═══════════════════════════════════════════════════ */
#about { background: var(–ink); }

.about-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 6rem;
align-items: center;
}

.about-visual {
position: relative;
}

.about-frame {
width: 100%;
aspect-ratio: 4/5;
background: var(–ink2);
border-radius: 4px;
position: relative; overflow: hidden;
display: flex; align-items: center; justify-content: center;
font-size: 5rem;
}

.about-frame::before {
content: ‘’;
position: absolute; inset: 0;
background: linear-gradient(135deg,
rgba(200,168,75,0.06) 0%,
transparent 50%,
rgba(200,168,75,0.03) 100%
);
}

.about-badge {
position: absolute; bottom: -20px; right: -20px;
width: 120px; height: 120px;
background: var(–gold);
border-radius: 50%;
display: flex; flex-direction: column;
align-items: center; justify-content: center;
color: var(–ink);
text-align: center;
}
.about-badge .num {
font-family: var(–ff-display);
font-size: 2.2rem;
font-weight: 900;
line-height: 1;
}
.about-badge .txt {
font-size: 0.62rem;
font-weight: 600;
letter-spacing: 1px;
text-transform: uppercase;
line-height: 1.2;
}

.about-decor {
position: absolute; top: -16px; left: -16px;
width: 80px; height: 80px;
border-top: 2px solid var(–gold);
border-left: 2px solid var(–gold);
border-radius: 2px;
}

.about-content .section-label { margin-bottom: 1rem; }
.about-content .section-title { margin-bottom: 1.5rem; }

.about-text {
font-size: 0.95rem;
color: var(–smoke);
line-height: 1.85;
margin-bottom: 1.2rem;
}

.about-stats {
display: grid; grid-template-columns: repeat(3, 1fr);
gap: 1rem; margin: 2.5rem 0;
}
.stat-item {
padding: 1.2rem;
border: 1px solid rgba(200,168,75,0.12);
border-radius: 4px;
text-align: center;
background: rgba(200,168,75,0.03);
}
.stat-num {
font-family: var(–ff-display);
font-size: 2rem;
font-weight: 900;
color: var(–gold);
line-height: 1;
}
.stat-label {
font-size: 0.7rem;
letter-spacing: 1.5px;
text-transform: uppercase;
color: var(–smoke);
margin-top: 4px;
}

.skills-wrap { margin-top: 2rem; }
.skill-row {
margin-bottom: 1rem;
}
.skill-top {
display: flex; justify-content: space-between;
font-size: 0.78rem; margin-bottom: 6px;
letter-spacing: 1px;
}
.skill-top span:last-child { color: var(–gold); font-family: var(–ff-mono); }
.skill-bar {
height: 3px; background: rgba(200,168,75,0.12);
border-radius: 2px; overflow: hidden;
}
.skill-fill {
height: 100%;
background: linear-gradient(90deg, var(–gold), var(–gold2));
border-radius: 2px;
width: 0;
transition: width 1.2s var(–ease) 0.3s;
}

/* ═══════════════════════════════════════════════════
BLOG
═══════════════════════════════════════════════════ */
#blog { background: rgba(200,168,75,0.02); }

.blog-header {
display: flex; justify-content: space-between; align-items: flex-end;
margin-bottom: 4rem; flex-wrap: wrap; gap: 2rem;
}

.blog-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
gap: 2rem;
}

.blog-card {
background: var(–ink2);
border-radius: 4px; overflow: hidden;
border: 1px solid rgba(200,168,75,0.06);
transition: transform 0.4s var(–ease), border-color 0.3s;
}
.blog-card:hover {
transform: translateY(-6px);
border-color: rgba(200,168,75,0.2);
}

.blog-thumb {
height: 200px;
display: flex; align-items: center; justify-content: center;
font-size: 3rem;
background: linear-gradient(135deg, var(–ink), var(–ink2));
position: relative; overflow: hidden;
}

.blog-thumb-tag {
position: absolute; top: 16px; left: 16px;
padding: 4px 12px;
background: var(–gold);
color: var(–ink);
font-size: 0.65rem;
font-weight: 600;
letter-spacing: 2px;
text-transform: uppercase;
border-radius: 2px;
}

.blog-body { padding: 1.8rem; }

.blog-meta {
display: flex; align-items: center; gap: 10px;
font-family: var(–ff-mono);
font-size: 0.68rem;
letter-spacing: 1px;
color: rgba(200,168,75,0.6);
margin-bottom: 1rem;
}
.blog-meta span { color: rgba(200,168,75,0.3); }

.blog-title {
font-family: var(–ff-display);
font-size: 1.2rem;
font-weight: 700;
line-height: 1.3;
margin-bottom: 0.8rem;
color: var(–cream);
transition: color 0.3s;
}
.blog-card:hover .blog-title { color: var(–gold); }

.blog-excerpt {
font-size: 0.85rem;
color: var(–smoke);
line-height: 1.7;
margin-bottom: 1.2rem;
}

.blog-link {
font-family: var(–ff-mono);
font-size: 0.72rem;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–gold);
text-decoration: none;
display: inline-flex; align-items: center; gap: 8px;
transition: gap 0.3s;
}
.blog-link:hover { gap: 14px; }

/* ═══════════════════════════════════════════════════
CONTACT
═══════════════════════════════════════════════════ */
#contact { background: var(–ink); }

.contact-wrap {
display: grid;
grid-template-columns: 1fr 1.4fr;
gap: 6rem;
align-items: start;
}

.contact-info .section-title { margin-bottom: 1.5rem; }

.contact-detail {
display: flex; align-items: flex-start; gap: 1rem;
margin-bottom: 1.8rem;
}
.contact-icon {
width: 44px; height: 44px; flex-shrink: 0;
border: 1px solid rgba(200,168,75,0.2);
border-radius: 8px;
display: flex; align-items: center; justify-content: center;
font-size: 1.1rem;
background: rgba(200,168,75,0.04);
}
.contact-detail-label {
font-family: var(–ff-mono);
font-size: 0.68rem;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 4px;
}
.contact-detail-value {
font-size: 0.95rem;
color: var(–cream);
}

.contact-divider {
height: 1px;
background: linear-gradient(90deg, rgba(200,168,75,0.2), transparent);
margin: 2.5rem 0;
}

.availability {
display: flex; align-items: center; gap: 10px;
font-size: 0.82rem;
color: var(–smoke);
}
.avail-dot {
width: 8px; height: 8px;
border-radius: 50%;
background: #4ade80;
box-shadow: 0 0 8px #4ade80;
animation: pulse-dot 2s ease-in-out infinite;
}
@keyframes pulse-dot {
0%, 100% { transform: scale(1); opacity: 1; }
50% { transform: scale(1.3); opacity: 0.7; }
}

/* Formulaire */
.contact-form { display: flex; flex-direction: column; gap: 1.2rem; }

.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }

.form-group { display: flex; flex-direction: column; gap: 8px; }

.form-label {
font-family: var(–ff-mono);
font-size: 0.68rem;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–gold);
}

.form-input, .form-textarea, .form-select {
background: rgba(200,168,75,0.04);
border: 1px solid rgba(200,168,75,0.12);
border-radius: 4px;
padding: 13px 16px;
font-family: var(–ff-body);
font-size: 0.9rem;
color: var(–cream);
transition: border-color 0.3s, background 0.3s;
outline: none;
width: 100%;
}
.form-input:focus, .form-textarea:focus, .form-select:focus {
border-color: var(–gold);
background: rgba(200,168,75,0.08);
}
.form-input::placeholder, .form-textarea::placeholder {
color: rgba(107,107,122,0.6);
}
.form-textarea { resize: vertical; min-height: 140px; }
.form-select option { background: var(–ink2); color: var(–cream); }

.form-submit {
margin-top: 0.5rem;
padding: 15px 40px;
background: var(–gold);
color: var(–ink);
font-family: var(–ff-body);
font-size: 0.82rem;
font-weight: 600;
letter-spacing: 2px;
text-transform: uppercase;
border: none;
border-radius: 3px;
transition: all 0.3s var(–ease);
align-self: flex-start;
position: relative; overflow: hidden;
}
.form-submit:hover {
transform: translateY(-2px);
box-shadow: 0 12px 40px rgba(200,168,75,0.3);
}

.form-success {
display: none;
padding: 16px;
background: rgba(74,222,128,0.08);
border: 1px solid rgba(74,222,128,0.2);
border-radius: 4px;
color: #4ade80;
font-size: 0.88rem;
text-align: center;
}

/* ═══════════════════════════════════════════════════
FOOTER
═══════════════════════════════════════════════════ */
footer {
background: var(–ink2);
padding: 4rem 5vw 2rem;
border-top: 1px solid rgba(200,168,75,0.08);
}

.footer-top {
display: flex; justify-content: space-between; align-items: flex-start;
margin-bottom: 3rem; flex-wrap: wrap; gap: 3rem;
}

.footer-brand .nav-logo { font-size: 1.6rem; display: block; margin-bottom: 1rem; }

.footer-tagline {
font-size: 0.85rem;
color: var(–smoke);
line-height: 1.7;
max-width: 260px;
}

.footer-links h4 {
font-family: var(–ff-mono);
font-size: 0.68rem;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 1.2rem;
}
.footer-links ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
.footer-links a {
font-size: 0.88rem;
color: var(–smoke);
text-decoration: none;
transition: color 0.3s;
}
.footer-links a:hover { color: var(–cream); }

.footer-bottom {
display: flex; justify-content: space-between; align-items: center;
padding-top: 2rem;
border-top: 1px solid rgba(200,168,75,0.06);
flex-wrap: wrap; gap: 1rem;
}
.footer-copy {
font-family: var(–ff-mono);
font-size: 0.7rem;
letter-spacing: 1px;
color: rgba(107,107,122,0.5);
}
.footer-copy span { color: var(–gold); }

/* ═══════════════════════════════════════════════════
ANIMATIONS
═══════════════════════════════════════════════════ */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}
@keyframes bounce {
0%, 100% { transform: translateX(-50%) translateY(0); }
50% { transform: translateX(-50%) translateY(10px); }
}

/* ═══════════════════════════════════════════════════
MOBILE
═══════════════════════════════════════════════════ */
@media (max-width: 900px) {
.about-grid { grid-template-columns: 1fr; gap: 3rem; }
.contact-wrap { grid-template-columns: 1fr; gap: 3rem; }
.portfolio-item:nth-child(n) { grid-column: span 12; }
.portfolio-grid { display: flex; flex-direction: column; }
.form-row { grid-template-columns: 1fr; }
.nav-links { display: none; }
.menu-toggle {
display: block; background: none; border: none;
color: var(–cream); font-size: 1.4rem;
}
}

@media (max-width: 600px) {
section { padding: 80px 6vw; }
.services-header, .portfolio-header, .blog-header { flex-direction: column; align-items: flex-start; }
.about-stats { grid-template-columns: repeat(3, 1fr); }
.footer-top { flex-direction: column; }
}

/* ═══════════════════════════════════════════════════
MOBILE MENU
═══════════════════════════════════════════════════ */
.mobile-menu {
position: fixed; inset: 0; z-index: 200;
background: rgba(12,12,20,0.98);
backdrop-filter: blur(20px);
display: flex; flex-direction: column;
align-items: center; justify-content: center; gap: 2rem;
transform: translateX(100%);
transition: transform 0.4s var(–ease);
}
.mobile-menu.open { transform: translateX(0); }
.mobile-menu a {
font-family: var(–ff-display);
font-size: 2rem; font-weight: 700;
color: var(–cream); text-decoration: none;
transition: color 0.3s;
}
.mobile-menu a:hover { color: var(–gold); }
.mobile-close {
position: absolute; top: 24px; right: 24px;
background: none; border: none;
color: var(–smoke); font-size: 1.5rem;
}
</style>

</head>
<body>

<!-- Cursors -->

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Mobile menu -->

<div class="mobile-menu" id="mobileMenu">
  <button class="mobile-close" onclick="toggleMenu()">✕</button>
  <a href="#services" onclick="toggleMenu()" data-fr="Services" data-en="Services">Services</a>
  <a href="#portfolio" onclick="toggleMenu()" data-fr="Portfolio" data-en="Portfolio">Portfolio</a>
  <a href="#about" onclick="toggleMenu()" data-fr="À propos" data-en="About">À propos</a>
  <a href="#blog" onclick="toggleMenu()" data-fr="Blog" data-en="Blog">Blog</a>
  <a href="#contact" onclick="toggleMenu()" data-fr="Contact" data-en="Contact">Contact</a>
</div>

<!-- NAV -->

<nav id="navbar">
  <a href="#hero" class="nav-logo">DAY<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#services" data-fr="Services" data-en="Services">Services</a></li>
    <li><a href="#portfolio" data-fr="Portfolio" data-en="Portfolio">Portfolio</a></li>
    <li><a href="#about" data-fr="À propos" data-en="About">À propos</a></li>
    <li><a href="#blog" data-fr="Blog" data-en="Blog">Blog</a></li>
    <li><a href="#contact" data-fr="Contact" data-en="Contact">Contact</a></li>
  </ul>
  <div style="display:flex;align-items:center;gap:16px;">
    <div class="lang-toggle">
      <button class="lang-btn active" onclick="setLang('fr')">FR</button>
      <button class="lang-btn" onclick="setLang('en')">EN</button>
    </div>
    <button class="menu-toggle" onclick="toggleMenu()">☰</button>
  </div>
</nav>

<!-- ══ HERO ═══════════════════════════════════════════ -->

<section id="hero">
  <div class="hero-bg">
    <div class="hero-grid"></div>
    <div class="hero-glow"></div>
  </div>
  <div class="hero-content">
    <div class="hero-eyebrow" data-fr="Consultant Digital & Audiovisuel" data-en="Digital & Audiovisual Consultant">
      Consultant Digital & Audiovisuel
    </div>
    <h1 class="hero-title">
      <span data-fr="Créer." data-en="Create.">Créer.</span><br>
      <em data-fr="Piloter." data-en="Lead.">Piloter.</em><br>
      <span data-fr="Développer." data-en="Grow.">Développer.</span>
    </h1>
    <p class="hero-subtitle" data-fr="DAY Consulting accompagne vos projets audiovisuels, digitaux et de gestion — de la conception à l'exécution, avec créativité et rigueur." data-en="DAY Consulting supports your audiovisual, digital and management projects — from conception to execution, with creativity and precision.">
      DAY Consulting accompagne vos projets audiovisuels, digitaux et de gestion — de la conception à l'exécution, avec créativité et rigueur.
    </p>
    <div class="hero-tags">
      <span class="tag" data-fr="Audiovisuel" data-en="Audiovisual">Audiovisuel</span>
      <span class="tag" data-fr="Web Design" data-en="Web Design">Web Design</span>
      <span class="tag" data-fr="Chef de Projet" data-en="Project Manager">Chef de Projet</span>
      <span class="tag" data-fr="Comptabilité" data-en="Accounting">Comptabilité</span>
    </div>
    <div class="hero-ctas">
      <a href="#services" class="btn-primary" data-fr="Voir mes services" data-en="My Services">Voir mes services</a>
      <a href="#contact" class="btn-secondary" data-fr="Me contacter" data-en="Get in touch">Me contacter</a>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span data-fr="Défiler" data-en="Scroll">Défiler</span>
  </div>
</section>

<!-- ══ SERVICES ═══════════════════════════════════════ -->

<section id="services">
  <div class="services-header reveal">
    <div>
      <div class="section-label" data-fr="Ce que je fais" data-en="What I do">Ce que je fais</div>
      <h2 class="section-title" data-fr="Mes Services" data-en="My Services">Mes Services</h2>
    </div>
    <p class="section-desc" data-fr="Une offre complète pour vos besoins créatifs, digitaux et de gestion d'entreprise." data-en="A complete offer for your creative, digital and business management needs.">
      Une offre complète pour vos besoins créatifs, digitaux et de gestion d'entreprise.
    </p>
  </div>

  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-number">01</div>
      <div class="service-icon">🎬</div>
      <div class="service-name" data-fr="Production Audiovisuelle" data-en="Audiovisual Production">Production Audiovisuelle</div>
      <p class="service-desc" data-fr="De la conception à la réalisation : clips musicaux, contenus digitaux, télé-réalité. Un regard artistique au service de votre vision." data-en="From concept to completion: music videos, digital content, reality TV. An artistic eye at the service of your vision.">
        De la conception à la réalisation : clips musicaux, contenus digitaux, télé-réalité. Un regard artistique au service de votre vision.
      </p>
      <ul class="service-list">
        <li data-fr="Direction & Assistance à la réalisation" data-en="Direction & AD">Direction & Assistance à la réalisation</li>
        <li data-fr="Gestion de plateau" data-en="Set management">Gestion de plateau</li>
        <li data-fr="Coordination technique" data-en="Technical coordination">Coordination technique</li>
        <li data-fr="Post-production" data-en="Post-production">Post-production</li>
      </ul>
    </div>

```
<div class="service-card reveal">
  <div class="service-number">02</div>
  <div class="service-icon">🌐</div>
  <div class="service-name" data-fr="Web Design & Identité Visuelle" data-en="Web Design & Visual Identity">Web Design & Identité Visuelle</div>
  <p class="service-desc" data-fr="Création de sites vitrines professionnels, identités visuelles mémorables et supports de communication digitaux qui convertissent." data-en="Professional showcase websites, memorable visual identities and digital communication materials that convert.">
    Création de sites vitrines professionnels, identités visuelles mémorables et supports de communication digitaux qui convertissent.
  </p>
  <ul class="service-list">
    <li data-fr="Site vitrine professionnel" data-en="Professional website">Site vitrine professionnel</li>
    <li data-fr="Identité visuelle & branding" data-en="Visual identity & branding">Identité visuelle & branding</li>
    <li data-fr="Carte de visite & supports print" data-en="Business card & print">Carte de visite & supports print</li>
    <li data-fr="Marketing digital" data-en="Digital marketing">Marketing digital</li>
  </ul>
</div>

<div class="service-card reveal">
  <div class="service-number">03</div>
  <div class="service-icon">📊</div>
  <div class="service-name" data-fr="Gestion & Comptabilité" data-en="Management & Accounting">Gestion & Comptabilité</div>
  <p class="service-desc" data-fr="Accompagnement administratif et gestion comptable pour TPE/PME. Des outils simples pour piloter votre activité en toute sérénité." data-en="Administrative support and accounting management for SMEs. Simple tools to manage your business with peace of mind.">
    Accompagnement administratif et gestion comptable pour TPE/PME. Des outils simples pour piloter votre activité en toute sérénité.
  </p>
  <ul class="service-list">
    <li data-fr="Suivi comptable & facturation" data-en="Accounting & invoicing">Suivi comptable & facturation</li>
    <li data-fr="Gestion administrative" data-en="Administrative management">Gestion administrative</li>
    <li data-fr="Tableaux de bord & reporting" data-en="Dashboards & reporting">Tableaux de bord & reporting</li>
    <li data-fr="Conseil en organisation" data-en="Organizational consulting">Conseil en organisation</li>
  </ul>
</div>

<div class="service-card reveal">
  <div class="service-number">04</div>
  <div class="service-icon">🎯</div>
  <div class="service-name" data-fr="Chef de Projet Digital" data-en="Digital Project Manager">Chef de Projet Digital</div>
  <p class="service-desc" data-fr="Pilotage de projets créatifs et digitaux de A à Z : coordination d'équipes, gestion des délais, suivi budgétaire et livraison." data-en="End-to-end management of creative and digital projects: team coordination, deadline management, budget tracking and delivery.">
    Pilotage de projets créatifs et digitaux de A à Z : coordination d'équipes, gestion des délais, suivi budgétaire et livraison.
  </p>
  <ul class="service-list">
    <li data-fr="Coordination d'équipes" data-en="Team coordination">Coordination d'équipes</li>
    <li data-fr="Planification & suivi" data-en="Planning & tracking">Planification & suivi</li>
    <li data-fr="Gestion budgétaire" data-en="Budget management">Gestion budgétaire</li>
    <li data-fr="Reporting client" data-en="Client reporting">Reporting client</li>
  </ul>
</div>
```

  </div>
</section>

<!-- ══ PORTFOLIO ══════════════════════════════════════ -->

<section id="portfolio">
  <div class="portfolio-header reveal">
    <div>
      <div class="section-label" data-fr="Réalisations" data-en="Work">Réalisations</div>
      <h2 class="section-title" data-fr="Portfolio" data-en="Portfolio">Portfolio</h2>
    </div>
    <div class="portfolio-filters">
      <button class="filter-btn active" data-filter="all" data-fr="Tout" data-en="All">Tout</button>
      <button class="filter-btn" data-filter="av" data-fr="Audiovisuel" data-en="Audiovisual">Audiovisuel</button>
      <button class="filter-btn" data-filter="web" data-fr="Web" data-en="Web">Web</button>
      <button class="filter-btn" data-filter="gestion" data-fr="Gestion" data-en="Management">Gestion</button>
    </div>
  </div>

  <div class="portfolio-grid reveal">

```
<div class="portfolio-item" data-category="av">
  <div class="portfolio-thumb">
    <div class="portfolio-thumb-inner">🎬</div>
    <div class="portfolio-overlay">
      <div class="portfolio-cat" data-fr="Clip Musical" data-en="Music Video">Clip Musical</div>
      <div class="portfolio-title-card" data-fr="Wantché — Djamo, No Cap, Bahi" data-en="Wantché — Djamo, No Cap, Bahi">Wantché — Djamo, No Cap, Bahi</div>
    </div>
  </div>
  <div class="portfolio-info">
    <div class="portfolio-cat" data-fr="Assistant Réalisateur · 2024--2025" data-en="Assistant Director · 2024--2025">Assistant Réalisateur · 2024--2025</div>
    <h3 data-fr="Wantché — Clips officiels" data-en="Wantché — Official Music Videos">Wantché — Clips officiels</h3>
  </div>
</div>

<div class="portfolio-item" data-category="av">
  <div class="portfolio-thumb">
    <div class="portfolio-thumb-inner">🎵</div>
    <div class="portfolio-overlay">
      <div class="portfolio-cat" data-fr="Clip Musical" data-en="Music Video">Clip Musical</div>
      <div class="portfolio-title-card" data-fr="Korey Lo — Come Back, Petit Mouvement, Gbozon" data-en="Korey Lo — Come Back, Petit Mouvement, Gbozon">Korey Lo — Come Back, Petit Mouvement, Gbozon</div>
    </div>
  </div>
  <div class="portfolio-info">
    <div class="portfolio-cat" data-fr="Assistant Réalisateur · 2024--2025" data-en="Assistant Director · 2024--2025">Assistant Réalisateur · 2024--2025</div>
    <h3 data-fr="Korey Lo — Clips officiels" data-en="Korey Lo — Official Music Videos">Korey Lo — Clips officiels</h3>
  </div>
</div>

<div class="portfolio-item" data-category="av">
  <div class="portfolio-thumb">
    <div class="portfolio-thumb-inner">📺</div>
    <div class="portfolio-overlay">
      <div class="portfolio-cat" data-fr="Télé-réalité" data-en="Reality TV">Télé-réalité</div>
      <div class="portfolio-title-card" data-fr="Amour sous tension — Sowa Prod" data-en="Amour sous tension — Sowa Prod">Amour sous tension — Sowa Prod</div>
    </div>
  </div>
  <div class="portfolio-info">
    <div class="portfolio-cat" data-fr="Asst. Régie & Caméra · Fév--Mars 2026" data-en="Asst. Production & Camera · Feb--Mar 2026">Asst. Régie & Caméra · Fév--Mars 2026</div>
    <h3 data-fr="Amour sous tension — Sowa Prod" data-en="Amour sous tension — Sowa Prod">Amour sous tension — Sowa Prod</h3>
  </div>
</div>

<div class="portfolio-item" data-category="web">
  <div class="portfolio-thumb">
    <div class="portfolio-thumb-inner">🌐</div>
    <div class="portfolio-overlay">
      <div class="portfolio-cat" data-fr="Web Design" data-en="Web Design">Web Design</div>
      <div class="portfolio-title-card" data-fr="DAY Consulting — Site vitrine" data-en="DAY Consulting — Showcase Website">DAY Consulting — Site vitrine</div>
    </div>
  </div>
  <div class="portfolio-info">
    <div class="portfolio-cat" data-fr="Web Design · 2025" data-en="Web Design · 2025">Web Design · 2025</div>
    <h3 data-fr="DAY Consulting — Site vitrine" data-en="DAY Consulting — Showcase Website">DAY Consulting — Site vitrine</h3>
  </div>
</div>

<div class="portfolio-item" data-category="gestion">
  <div class="portfolio-thumb">
    <div class="portfolio-thumb-inner">📊</div>
    <div class="portfolio-overlay">
      <div class="portfolio-cat" data-fr="Gestion de projet" data-en="Project Management">Gestion de projet</div>
      <div class="portfolio-title-card" data-fr="Coordination BELT GROUP" data-en="BELT GROUP Coordination">Coordination BELT GROUP</div>
    </div>
  </div>
  <div class="portfolio-info">
    <div class="portfolio-cat" data-fr="Assistance Direction · 2018" data-en="Executive Assistant · 2018">Assistance Direction · 2018</div>
    <h3 data-fr="BELT GROUP — Assistance Direction" data-en="BELT GROUP — Executive Assistant">BELT GROUP — Assistance Direction</h3>
  </div>
</div>

<div class="portfolio-item" data-category="av">
  <div class="portfolio-thumb">
    <div class="portfolio-thumb-inner">📸</div>
    <div class="portfolio-overlay">
      <div class="portfolio-cat" data-fr="Photographie" data-en="Photography">Photographie</div>
      <div class="portfolio-title-card" data-fr="Captation & Direction artistique" data-en="Capture & Art Direction">Captation & Direction artistique</div>
    </div>
  </div>
  <div class="portfolio-info">
    <div class="portfolio-cat" data-fr="Photographie · En cours" data-en="Photography · Ongoing">Photographie · En cours</div>
    <h3 data-fr="Captation & Direction artistique" data-en="Capture & Art Direction">Captation & Direction artistique</h3>
  </div>
</div>
```

  </div>
</section>

<!-- ══ ABOUT ══════════════════════════════════════════ -->

<section id="about">
  <div class="about-grid">
    <div class="about-visual reveal">
      <div class="about-decor"></div>
      <div class="about-frame">
        🎬
        <div class="about-badge">
          <div class="num">8+</div>
          <div class="txt">ans d'expérience</div>
        </div>
      </div>
    </div>
    <div class="about-content reveal">
      <div class="section-label" data-fr="Qui suis-je ?" data-en="Who am I?">Qui suis-je ?</div>
      <h2 class="section-title" data-fr="Dane Anselme Youzan" data-en="Dane Anselme Youzan">Dane Anselme Youzan</h2>
      <p class="about-text" data-fr="Professionnel ivoirien polyvalent, je combine créativité, rigueur et sens du leadership pour piloter des projets à fort impact. De la gestion de clips musicaux pour des artistes reconnus à la coordination de productions télévisées, j'apporte une vision globale à chaque projet." data-en="A versatile Ivorian professional, I combine creativity, rigor and leadership skills to drive high-impact projects. From managing music videos for recognized artists to coordinating television productions, I bring a holistic vision to every project.">
        Professionnel ivoirien polyvalent, je combine créativité, rigueur et sens du leadership pour piloter des projets à fort impact. De la gestion de clips musicaux pour des artistes reconnus à la coordination de productions télévisées, j'apporte une vision globale à chaque projet.
      </p>
      <p class="about-text" data-fr="Issu d'une formation en Sciences Économiques et de Gestion, j'ai forgé mon parcours à travers des expériences variées : assistant de direction, secrétaire général, commercial, conseiller client — autant d'atouts qui nourrissent aujourd'hui mon approche de consultant." data-en="With a background in Economics and Management, I have built my career through diverse experiences: executive assistant, secretary general, sales rep, customer advisor — all assets that fuel my consulting approach today.">
        Issu d'une formation en Sciences Économiques et de Gestion, j'ai forgé mon parcours à travers des expériences variées : assistant de direction, secrétaire général, commercial, conseiller client — autant d'atouts qui nourrissent aujourd'hui mon approche de consultant.
      </p>

```
  <div class="about-stats">
    <div class="stat-item">
      <div class="stat-num">6+</div>
      <div class="stat-label" data-fr="Clips produits" data-en="Videos produced">Clips produits</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">3</div>
      <div class="stat-label" data-fr="Secteurs d'expertise" data-en="Expert fields">Secteurs</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">2</div>
      <div class="stat-label" data-fr="Langues maîtrisées" data-en="Languages">Langues</div>
    </div>
  </div>

  <div class="skills-wrap">
    <div class="skill-row">
      <div class="skill-top">
        <span data-fr="Production Audiovisuelle" data-en="Audiovisual Production">Production Audiovisuelle</span>
        <span>85%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" data-width="85"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-top">
        <span data-fr="Gestion de Projet" data-en="Project Management">Gestion de Projet</span>
        <span>80%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" data-width="80"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-top">
        <span data-fr="Web Design & Digital" data-en="Web Design & Digital">Web Design & Digital</span>
        <span>70%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" data-width="70"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-top">
        <span data-fr="Gestion & Comptabilité" data-en="Management & Accounting">Gestion & Comptabilité</span>
        <span>65%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" data-width="65"></div></div>
    </div>
  </div>

  <div style="margin-top:2.5rem;">
    <a href="#contact" class="btn-primary" data-fr="Travaillons ensemble" data-en="Let's work together">Travaillons ensemble</a>
  </div>
</div>
```

  </div>
</section>

<!-- ══ BLOG ═══════════════════════════════════════════ -->

<section id="blog">
  <div class="blog-header reveal">
    <div>
      <div class="section-label" data-fr="Actualités & Réflexions" data-en="News & Insights">Actualités & Réflexions</div>
      <h2 class="section-title" data-fr="Blog" data-en="Blog">Blog</h2>
    </div>
    <a href="#" class="btn-secondary" style="padding:10px 24px;font-size:0.75rem;" data-fr="Tous les articles" data-en="All articles">Tous les articles</a>
  </div>

  <div class="blog-grid">
    <div class="blog-card reveal">
      <div class="blog-thumb">
        🎬
        <div class="blog-thumb-tag" data-fr="Audiovisuel" data-en="Audiovisual">Audiovisuel</div>
      </div>
      <div class="blog-body">
        <div class="blog-meta">
          <span data-fr="Mars 2026" data-en="March 2026">Mars 2026</span>
          <span>·</span>
          <span data-fr="5 min de lecture" data-en="5 min read">5 min de lecture</span>
        </div>
        <h3 class="blog-title" data-fr="Les coulisses d'une télé-réalité : mon expérience sur Amour sous tension" data-en="Behind the scenes of reality TV: my experience on Amour sous tension">Les coulisses d'une télé-réalité : mon expérience sur Amour sous tension</h3>
        <p class="blog-excerpt" data-fr="Un mois passé aux côtés de Sowa Prod sur le tournage de la télé-réalité Amour sous tension. Ce que j'ai appris sur la production TV." data-en="A month alongside Sowa Prod on the Amour sous tension reality show shoot. What I learned about TV production.">
          Un mois passé aux côtés de Sowa Prod sur le tournage de la télé-réalité Amour sous tension. Ce que j'ai appris sur la production TV.
        </p>
        <a href="#" class="blog-link">
          <span data-fr="Lire l'article" data-en="Read article">Lire l'article</span> →
        </a>
      </div>
    </div>

```
<div class="blog-card reveal">
  <div class="blog-thumb">
    🌐
    <div class="blog-thumb-tag" data-fr="Digital" data-en="Digital">Digital</div>
  </div>
  <div class="blog-body">
    <div class="blog-meta">
      <span data-fr="Fév. 2026" data-en="Feb. 2026">Fév. 2026</span>
      <span>·</span>
      <span data-fr="4 min de lecture" data-en="4 min read">4 min de lecture</span>
    </div>
    <h3 class="blog-title" data-fr="Créer une identité visuelle forte pour les PME ivoiriennes" data-en="Building a strong visual identity for Ivorian SMEs">Créer une identité visuelle forte pour les PME ivoiriennes</h3>
    <p class="blog-excerpt" data-fr="Pourquoi l'identité visuelle est le premier investissement à faire pour une PME qui veut se démarquer dans un marché concurrentiel." data-en="Why visual identity is the first investment an SME should make to stand out in a competitive market.">
      Pourquoi l'identité visuelle est le premier investissement à faire pour une PME qui veut se démarquer dans un marché concurrentiel.
    </p>
    <a href="#" class="blog-link">
      <span data-fr="Lire l'article" data-en="Read article">Lire l'article</span> →
    </a>
  </div>
</div>

<div class="blog-card reveal">
  <div class="blog-thumb">
    📊
    <div class="blog-thumb-tag" data-fr="Gestion" data-en="Management">Gestion</div>
  </div>
  <div class="blog-body">
    <div class="blog-meta">
      <span data-fr="Janv. 2026" data-en="Jan. 2026">Janv. 2026</span>
      <span>·</span>
      <span data-fr="6 min de lecture" data-en="6 min read">6 min de lecture</span>
    </div>
    <h3 class="blog-title" data-fr="5 outils gratuits pour gérer la comptabilité de votre TPE" data-en="5 free tools to manage your small business accounting">5 outils gratuits pour gérer la comptabilité de votre TPE</h3>
    <p class="blog-excerpt" data-fr="Indy, Abby, Tiime, Google Sheets... Tour d'horizon des meilleurs outils pour gérer vos finances sans débourser un centime." data-en="Indy, Abby, Tiime, Google Sheets... Overview of the best tools to manage your finances without spending a cent.">
      Indy, Abby, Tiime, Google Sheets... Tour d'horizon des meilleurs outils pour gérer vos finances sans débourser un centime.
    </p>
    <a href="#" class="blog-link">
      <span data-fr="Lire l'article" data-en="Read article">Lire l'article</span> →
    </a>
  </div>
</div>
```

  </div>
</section>

<!-- ══ CONTACT ════════════════════════════════════════ -->

<section id="contact">
  <div class="contact-wrap">
    <div class="contact-info reveal">
      <div class="section-label" data-fr="Travaillons ensemble" data-en="Let's work together">Travaillons ensemble</div>
      <h2 class="section-title" data-fr="Prêt à démarrer votre projet ?" data-en="Ready to start your project?">Prêt à démarrer votre projet ?</h2>
      <p class="section-desc" style="margin-bottom:2.5rem;" data-fr="Que ce soit pour un clip, un site, une gestion comptable ou un projet digital, je suis là pour vous accompagner." data-en="Whether it's a music video, a website, accounting management or a digital project, I'm here to support you.">
        Que ce soit pour un clip, un site, une gestion comptable ou un projet digital, je suis là pour vous accompagner.
      </p>

```
  <div class="contact-detail">
    <div class="contact-icon">📞</div>
    <div>
      <div class="contact-detail-label" data-fr="Téléphone" data-en="Phone">Téléphone</div>
      <div class="contact-detail-value">(+225) 07 77 87 02 19</div>
    </div>
  </div>
  <div class="contact-detail">
    <div class="contact-icon">✉️</div>
    <div>
      <div class="contact-detail-label" data-fr="Email" data-en="Email">Email</div>
      <div class="contact-detail-value">dannyouzan@gmail.com</div>
    </div>
  </div>
  <div class="contact-detail">
    <div class="contact-icon">📍</div>
    <div>
      <div class="contact-detail-label" data-fr="Localisation" data-en="Location">Localisation</div>
      <div class="contact-detail-value" data-fr="Rosiers 5e programme, Abidjan, Côte d'Ivoire" data-en="Rosiers 5th programme, Abidjan, Ivory Coast">Rosiers 5e programme, Abidjan, Côte d'Ivoire</div>
    </div>
  </div>

  <div class="contact-divider"></div>

  <div class="availability">
    <div class="avail-dot"></div>
    <span data-fr="Disponible pour de nouvelles missions" data-en="Available for new projects">Disponible pour de nouvelles missions</span>
  </div>
</div>

<div class="reveal">
  <form class="contact-form" id="contactForm" onsubmit="handleSubmit(event)">
    <div class="form-row">
      <div class="form-group">
        <label class="form-label" data-fr="Nom complet" data-en="Full name">Nom complet</label>
        <input class="form-input" type="text" required placeholder="Jean Kouassi" data-placeholder-fr="Jean Kouassi" data-placeholder-en="John Smith">
      </div>
      <div class="form-group">
        <label class="form-label" data-fr="Email" data-en="Email">Email</label>
        <input class="form-input" type="email" required placeholder="jean@exemple.com" data-placeholder-fr="jean@exemple.com" data-placeholder-en="john@example.com">
      </div>
    </div>
    <div class="form-group">
      <label class="form-label" data-fr="Sujet" data-en="Subject">Sujet</label>
      <select class="form-select" required>
        <option value="" data-fr="Choisissez un service..." data-en="Select a service...">Choisissez un service...</option>
        <option value="av" data-fr="Production Audiovisuelle" data-en="Audiovisual Production">Production Audiovisuelle</option>
        <option value="web" data-fr="Web Design & Identité visuelle" data-en="Web Design & Visual Identity">Web Design & Identité visuelle</option>
        <option value="compta" data-fr="Gestion & Comptabilité" data-en="Management & Accounting">Gestion & Comptabilité</option>
        <option value="project" data-fr="Chef de Projet" data-en="Project Management">Chef de Projet</option>
        <option value="other" data-fr="Autre demande" data-en="Other inquiry">Autre demande</option>
      </select>
    </div>
    <div class="form-group">
      <label class="form-label" data-fr="Votre message" data-en="Your message">Votre message</label>
      <textarea class="form-textarea" required placeholder="Décrivez votre projet..." data-placeholder-fr="Décrivez votre projet..." data-placeholder-en="Describe your project..."></textarea>
    </div>
    <button type="submit" class="form-submit" data-fr="Envoyer le message →" data-en="Send message →">Envoyer le message →</button>
    <div class="form-success" id="formSuccess" data-fr="✓ Message envoyé ! Je vous réponds dans les 24h." data-en="✓ Message sent! I'll reply within 24 hours.">
      ✓ Message envoyé ! Je vous réponds dans les 24h.
    </div>
  </form>
</div>
```

  </div>
</section>

<!-- ══ FOOTER ═════════════════════════════════════════ -->

<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <a href="#hero" class="nav-logo">DAY<span>.</span></a>
      <p class="footer-tagline" data-fr="Consultant Digital & Audiovisuel. Créer, piloter et développer vos projets avec passion et expertise." data-en="Digital & Audiovisual Consultant. Creating, leading and growing your projects with passion and expertise.">
        Consultant Digital & Audiovisuel. Créer, piloter et développer vos projets avec passion et expertise.
      </p>
    </div>
    <div class="footer-links">
      <h4 data-fr="Navigation" data-en="Navigation">Navigation</h4>
      <ul>
        <li><a href="#services" data-fr="Services" data-en="Services">Services</a></li>
        <li><a href="#portfolio" data-fr="Portfolio" data-en="Portfolio">Portfolio</a></li>
        <li><a href="#about" data-fr="À propos" data-en="About">À propos</a></li>
        <li><a href="#blog" data-fr="Blog" data-en="Blog">Blog</a></li>
        <li><a href="#contact" data-fr="Contact" data-en="Contact">Contact</a></li>
      </ul>
    </div>
    <div class="footer-links">
      <h4 data-fr="Services" data-en="Services">Services</h4>
      <ul>
        <li><a href="#services" data-fr="Production Audiovisuelle" data-en="Audiovisual Production">Production Audiovisuelle</a></li>
        <li><a href="#services" data-fr="Web Design" data-en="Web Design">Web Design</a></li>
        <li><a href="#services" data-fr="Gestion & Comptabilité" data-en="Management & Accounting">Gestion & Comptabilité</a></li>
        <li><a href="#services" data-fr="Chef de Projet" data-en="Project Manager">Chef de Projet</a></li>
      </ul>
    </div>
    <div class="footer-links">
      <h4 data-fr="Contact" data-en="Contact">Contact</h4>
      <ul>
        <li><a href="mailto:dannyouzan@gmail.com">dannyouzan@gmail.com</a></li>
        <li><a href="tel:+22507778702 19">(+225) 07 77 87 02 19</a></li>
        <li><a href="#" data-fr="Abidjan, Côte d'Ivoire" data-en="Abidjan, Ivory Coast">Abidjan, Côte d'Ivoire</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2026 <span>DAY Consulting</span> — Dane Anselme Youzan. <span data-fr="Tous droits réservés." data-en="All rights reserved.">Tous droits réservés.</span></div>
    <div class="footer-copy" data-fr="Abidjan · Côte d'Ivoire" data-en="Abidjan · Ivory Coast">Abidjan · Côte d'Ivoire</div>
  </div>
</footer>

<script>
// ── Cursor ───────────────────────────────────────────
const cursor = document.getElementById('cursor');
const cursorRing = document.getElementById('cursorRing');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; });
function animateCursor() {
  cursor.style.transform = `translate(${mx - 5}px, ${my - 5}px)`;
  rx += (mx - rx) * 0.12;
  ry += (my - ry) *.12;
  cursorRing.style.transform = `translate(${rx - 18}px, ${ry - 18}px)`;
  requestAnimationFrame(animateCursor);
}
animateCursor();
document.querySelectorAll('a, button, .service-card, .portfolio-item, .blog-card').forEach(el => {
  el.addEventListener('mouseenter', () => {
    cursorRing.style.width = '60px';
    cursorRing.style.height = '60px';
    cursorRing.style.borderColor = 'rgba(200,168,75,0.8)';
  });
  el.addEventListener('mouseleave', () => {
    cursorRing.style.width = '36px';
    cursorRing.style.height = '36px';
    cursorRing.style.borderColor = 'rgba(200,168,75,0.5)';
  });
});

// ── Navbar scroll ────────────────────────────────────
window.addEventListener('scroll', () => {
  document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 50);
});

// ── Mobile menu ──────────────────────────────────────
function toggleMenu() {
  document.getElementById('mobileMenu').classList.toggle('open');
}

// ── Scroll reveal ────────────────────────────────────
const revealObs = new IntersectionObserver((entries) => {
  entries.forEach((e, i) => {
    if (e.isIntersecting) {
      e.target.style.transitionDelay = (i * 0.08) + 's';
      e.target.classList.add('visible');
      // Skill bars
      e.target.querySelectorAll('.skill-fill').forEach(bar => {
        bar.style.width = bar.dataset.width + '%';
      });
    }
  });
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => revealObs.observe(el));

// ── Portfolio filters ────────────────────────────────
document.querySelectorAll('.filter-btn').forEach(btn => {
  btn.addEventListener('click', () => {
    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    const filter = btn.dataset.filter;
    document.querySelectorAll('.portfolio-item').forEach(item => {
      const show = filter === 'all' || item.dataset.category === filter;
      item.style.display = show ? '' : 'none';
    });
  });
});

// ── Langue ───────────────────────────────────────────
function setLang(lang) {
  document.documentElement.setAttribute('data-lang', lang);
  document.querySelectorAll('.lang-btn').forEach(b => {
    b.classList.toggle('active', b.textContent.toLowerCase() === lang);
  });
  document.querySelectorAll('[data-fr]').forEach(el => {
    const txt = lang === 'fr' ? el.dataset.fr : el.dataset.en;
    if (!txt) return;
    if (el.tagName === 'INPUT' || el.tagName === 'TEXTAREA') {
      el.placeholder = txt;
    } else if (el.tagName === 'OPTION') {
      el.textContent = txt;
    } else {
      el.textContent = txt;
    }
  });
}

// ── Contact form ─────────────────────────────────────
function handleSubmit(e) {
  e.preventDefault();
  const btn = e.target.querySelector('.form-submit');
  const success = document.getElementById('formSuccess');
  const lang = document.documentElement.getAttribute('data-lang');
  btn.textContent = lang === 'fr' ? 'Envoi en cours...' : 'Sending...';
  btn.disabled = true;
  setTimeout(() => {
    e.target.reset();
    btn.style.display = 'none';
    success.style.display = 'block';
    success.textContent = success.dataset[lang] || success.dataset.fr;
  }, 1200);
}

// ── Smooth scroll offset nav ─────────────────────────
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    const target = document.querySelector(a.getAttribute('href'));
    if (target) {
      e.preventDefault();
      const top = target.getBoundingClientRect().top + window.scrollY - 72;
      window.scrollTo({ top, behavior: 'smooth' });
    }
  });
});
</script>

</body>
</html>