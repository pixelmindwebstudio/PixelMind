<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pixelmind — Modernizing Websites, Elevating Brands</title>
<meta name="description" content="Pixelmind is a web design studio modernizing outdated websites into fast, elegant, AI-enhanced digital experiences.">

<!-- EMBEDDED VECTOR FAVICON (PixelMind Node-Network Icon) -->
<link rel="icon" type="image/svg+xml" href="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><defs><linearGradient id='g' x1='0' y1='0' x2='100' y2='100'><stop offset='0%' stop-color='%2338BDF8'/><stop offset='40%' stop-color='%232563EB'/><stop offset='70%' stop-color='%237C3AED'/><stop offset='100%' stop-color='%23EF4444'/></linearGradient></defs><path d='M25 35 L50 20 L75 35 L75 65 L50 80 L25 65 Z' fill='none' stroke='url(%23g)' stroke-width='6'/><circle cx='25' cy='35' r='8' fill='%2338BDF8'/><circle cx='50' cy='20' r='8' fill='%232563EB'/><circle cx='75' cy='35' r='8' fill='%237C3AED'/><circle cx='75' cy='65' r='8' fill='%23EF4444'/><circle cx='50' cy='80' r='8' fill='%23F97316'/><circle cx='25' cy='65' r='8' fill='%237C3AED'/></svg>">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@500;600;700;800&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
/* ============================================================
   PIXELMIND — DESIGN TOKENS
   ============================================================ */
:root{
  --white:#FFFFFF;
  --surface:#F9FAFB;
  --surface-alt:#F3F4F8;
  --ink:#14162B;
  --ink-soft:#585C78;
  --ink-faint:#8A8DAA;
  --line:#E7E8F0;

  --blue-light:#38BDF8;
  --blue:#2563EB;
  --purple:#7C3AED;
  --red:#EF4444;
  --orange:#F97316;

  --gradient-flow: linear-gradient(115deg, var(--blue-light) 0%, var(--blue) 32%, var(--purple) 68%, var(--red) 100%);
  --gradient-soft: linear-gradient(135deg, rgba(37,99,235,.10), rgba(124,58,237,.10) 55%, rgba(239,68,68,.08));

  --shadow-sm: 0 1px 2px rgba(20,22,43,.06);
  --shadow-md: 0 8px 24px rgba(20,22,43,.08);
  --shadow-lg: 0 24px 64px rgba(20,22,43,.14);
  --shadow-glow: 0 0 0 1px rgba(37,99,235,.08), 0 20px 48px rgba(124,58,237,.16);

  --radius-sm: 10px;
  --radius-md: 16px;
  --radius-lg: 26px;

  --container: 1200px;
  --nav-h: 76px;
}

*,*::before,*::after{ box-sizing:border-box; margin:0; padding:0; }
html{ scroll-behavior:smooth; }
body{
  font-family:'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  color:var(--ink);
  background:var(--white);
  line-height:1.6;
  -webkit-font-smoothing:antialiased;
  overflow-x:hidden;
}
img{ max-width:100%; display:block; }
a{ color:inherit; text-decoration:none; }
ul{ list-style:none; }
button{ font-family:inherit; cursor:pointer; border:none; background:none; }
h1,h2,h3,h4{
  font-family:'Outfit', sans-serif;
  color:var(--ink);
  line-height:1.08;
  letter-spacing:-0.01em;
}
.container{ max-width:var(--container); margin:0 auto; padding:0 32px; }

@media (max-width:640px){ .container{ padding:0 22px; } }

/* Focus visibility */
a:focus-visible, button:focus-visible{
  outline:2px solid var(--blue);
  outline-offset:3px;
  border-radius:4px;
}

@media (prefers-reduced-motion: reduce){
  *{ animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important; scroll-behavior:auto !important; }
}

/* ============================================================
   REVEAL (single restrained utility, brief-requested)
   ============================================================ */
.reveal{ opacity:0; transform:translateY(14px); transition:opacity .7s ease, transform .7s ease; }
.reveal.is-visible{ opacity:1; transform:translateY(0); }

/* ============================================================
   NAVIGATION
   ============================================================ */
.navbar{
  position:fixed; top:0; left:0; right:0; z-index:1000;
  height:var(--nav-h);
  display:flex; align-items:center;
  background:rgba(255,255,255,.72);
  backdrop-filter:blur(16px) saturate(160%);
  -webkit-backdrop-filter:blur(16px) saturate(160%);
  border-bottom:1px solid rgba(20,22,43,.06);
  transition:box-shadow .3s ease, background .3s ease;
}
.navbar.scrolled{ box-shadow:0 4px 24px rgba(20,22,43,.06); }
.nav-inner{
  width:100%; max-width:var(--container); margin:0 auto; padding:0 32px;
  display:flex; align-items:center; justify-content:space-between;
}
.brand{ display:flex; align-items:center; gap:10px; }
.brand svg{ height:34px; width:34px; }
.brand-word{ font-family:'Outfit', sans-serif; font-weight:700; font-size:1.28rem; letter-spacing:-0.01em; }
.brand-word .pixel{ color:var(--ink); }
.brand-word .mind{
  background:linear-gradient(90deg, var(--blue), var(--purple));
  -webkit-background-clip:text; background-clip:text; color:transparent;
}
.nav-links{ display:flex; align-items:center; gap:40px; }
.nav-links a{
  font-size:.95rem; font-weight:500; color:var(--ink-soft);
  position:relative; padding:6px 0; transition:color .2s ease;
}
.nav-links a::after{
  content:''; position:absolute; left:0; right:100%; bottom:0; height:2px;
  background:var(--gradient-flow); transition:right .28s ease;
}
.nav-links a:hover{ color:var(--ink); }
.nav-links a:hover::after{ right:0; }
.nav-actions{ display:flex; align-items:center; gap:20px; }
.btn{
  display:inline-flex; align-items:center; justify-content:center; gap:8px;
  padding:12px 26px; border-radius:999px;
  font-size:.94rem; font-weight:600; font-family:'Inter',sans-serif;
  transition:transform .25s ease, box-shadow .25s ease, background .25s ease;
  white-space:nowrap;
}
.btn-primary{
  color:#fff; background:linear-gradient(100deg, var(--blue), var(--purple));
  box-shadow:0 10px 24px rgba(124,58,237,.28);
}
.btn-primary:hover{ transform:translateY(-2px); box-shadow:0 16px 32px rgba(124,58,237,.36); }
.btn-ghost{
  color:var(--ink); background:var(--white); border:1px solid var(--line);
}
.btn-ghost:hover{ border-color:var(--blue); color:var(--blue); }
.btn-block{ width:100%; }

.nav-toggle{
  display:none; flex-direction:column; gap:5px; width:26px; padding:8px 0;
}
.nav-toggle span{ height:2px; width:100%; background:var(--ink); border-radius:2px; transition:transform .3s ease, opacity .3s ease; }
.nav-toggle.open span:nth-child(1){ transform:translateY(7px) rotate(45deg); }
.nav-toggle.open span:nth-child(2){ opacity:0; }
.nav-toggle.open span:nth-child(3){ transform:translateY(-7px) rotate(-45deg); }

.mobile-panel{
  position:fixed; top:var(--nav-h); left:0; right:0; z-index:999;
  background:var(--white); border-bottom:1px solid var(--line);
  padding:8px 22px 26px; display:flex; flex-direction:column; gap:4px;
  transform:translateY(-12px); opacity:0; pointer-events:none;
  transition:transform .28s ease, opacity .28s ease;
  box-shadow:0 20px 40px rgba(20,22,43,.10);
}
.mobile-panel.open{ transform:translateY(0); opacity:1; pointer-events:auto; }
.mobile-panel a{ padding:14px 4px; font-weight:500; border-bottom:1px solid var(--line); }
.mobile-panel .btn{ margin-top:14px; }

@media (max-width:900px){
  .nav-links{ display:none; }
  .nav-actions .btn-ghost{ display:none; }
  .nav-toggle{ display:flex; }
}

/* ============================================================
   HERO
   ============================================================ */
.hero{
  position:relative;
  padding:calc(var(--nav-h) + 64px) 0 88px;
  overflow:hidden;
  background:var(--white);
}
.hero-blob{
  position:absolute; z-index:0; filter:blur(60px); opacity:.55; pointer-events:none;
}
.hero-blob.b1{ width:520px; height:520px; top:-160px; right:-140px;
  background:radial-gradient(circle at 30% 30%, rgba(56,189,248,.35), rgba(124,58,237,.18) 60%, transparent 75%); }
.hero-blob.b2{ width:420px; height:420px; bottom:-180px; left:-120px;
  background:radial-gradient(circle at 60% 40%, rgba(239,68,68,.16), rgba(37,99,235,.14) 55%, transparent 75%); }

.hero-grid{
  position:relative; z-index:1;
  display:grid; grid-template-columns:1.05fr .95fr; gap:56px; align-items:center;
}
.hero-eyebrow-line{
  display:flex; align-items:center; gap:10px; margin-bottom:22px;
  font-size:.9rem; color:var(--ink-soft); font-weight:500;
}
.hero-eyebrow-line .dot{
  width:8px; height:8px; border-radius:50%; background:var(--gradient-flow);
}
.hero h1{
  font-size:clamp(2.4rem, 4.6vw, 3.6rem);
  font-weight:800;
  margin-bottom:22px;
  max-width:640px;
}
.hero h1 .accent{
  background:var(--gradient-flow);
  -webkit-background-clip:text; background-clip:text; color:transparent;
}
.hero p.lead{
  font-size:1.13rem; color:var(--ink-soft); max-width:520px; margin-bottom:34px;
}
.hero-ctas{ display:flex; gap:16px; flex-wrap:wrap; margin-bottom:40px; }
.hero-trust{
  display:flex; gap:28px; flex-wrap:wrap; padding-top:28px; border-top:1px solid var(--line);
  max-width:560px;
}
.hero-trust div{ font-size:.88rem; color:var(--ink-faint); }
.hero-trust strong{ display:block; font-family:'Outfit',sans-serif; font-size:1.02rem; color:var(--ink); font-weight:700; margin-bottom:2px; }

/* Hero visual panel */
.hero-visual{
  position:relative; height:520px;
  display:flex; align-items:center; justify-content:center;
}
.hero-visual svg{ width:100%; height:100%; max-width:520px; overflow:visible; }
.node{ transform-origin:center; }
.node circle{ filter:drop-shadow(0 6px 14px rgba(37,99,235,.28)); }
.edge{
  stroke-dasharray:400; stroke-dashoffset:400;
  animation:draw 1.6s ease forwards;
}
@keyframes draw{ to{ stroke-dashoffset:0; } }
.node{ opacity:0; animation:pop .5s ease forwards; }
@keyframes pop{
  0%{ opacity:0; transform:scale(.3); }
  70%{ opacity:1; transform:scale(1.12); }
  100%{ opacity:1; transform:scale(1); }
}
.node.pulse{ animation:pop .5s ease forwards, pulse 4.5s ease-in-out 1.6s infinite; }
@keyframes pulse{
  0%,100%{ transform:scale(1); }
  50%{ transform:scale(1.06); }
}

.glass-card{
  position:absolute; padding:14px 16px; border-radius:14px;
  background:rgba(255,255,255,.65); backdrop-filter:blur(14px);
  border:1px solid rgba(255,255,255,.6);
  box-shadow:var(--shadow-lg);
  display:flex; align-items:center; gap:10px;
  font-size:.82rem; font-weight:600; color:var(--ink);
  opacity:0; animation:floatIn .7s ease forwards;
}
.glass-card i{ font-size:1rem; }
.glass-card.gc1{ top:6%; left:-4%; animation-delay:1.9s; }
.glass-card.gc2{ bottom:10%; right:-6%; animation-delay:2.15s; }
.glass-card.gc3{ bottom:-2%; left:12%; animation-delay:2.4s; }
@keyframes floatIn{
  0%{ opacity:0; transform:translateY(16px); }
  100%{ opacity:1; transform:translateY(0); }
}
.glass-card{ animation-name:floatIn, drift; animation-duration:.7s, 6s; animation-timing-function:ease, ease-in-out; animation-iteration-count:1, infinite; animation-delay: inherit, inherit; }
.gc1{ animation-delay:1.9s, 1.9s; }
.gc2{ animation-delay:2.15s, 2.15s; }
.gc3{ animation-delay:2.4s, 2.4s; }
@keyframes drift{ 0%,100%{ transform:translateY(0); } 50%{ transform:translateY(-8px); } }

@media (max-width:980px){
  .hero-grid{ grid-template-columns:1fr; }
  .hero-visual{ height:380px; order:-1; }
  .hero h1{ max-width:none; }
}
@media (max-width:640px){
  .hero{ padding-top:calc(var(--nav-h) + 40px); }
  .glass-card{ display:none; }
}

/* ============================================================
   SECTION SHELLS
   ============================================================ */
section{ position:relative; padding:104px 0; }
.section-alt{ background:var(--surface); }
.section-head{ max-width:620px; margin-bottom:56px; }
.section-head h2{ font-size:clamp(1.9rem,3vw,2.5rem); font-weight:700; margin-bottom:14px; }
.section-head p{ color:var(--ink-soft); font-size:1.04rem; }
@media (max-width:640px){ section{ padding:72px 0; } }

/* ============================================================
   SERVICES — asymmetric grid
   ============================================================ */
.services-grid{
  display:grid;
  grid-template-columns:repeat(6,1fr);
  gap:22px;
}
.service-card{
  grid-column:span 3;
  background:var(--white);
  border:1px solid var(--line);
  border-radius:var(--radius-lg);
  padding:38px 34px;
  transition:transform .3s ease, box-shadow .3s ease, border-color .3s ease;
  position:relative; overflow:hidden;
}
.service-card:hover{ transform:translateY(-4px); box-shadow:var(--shadow-md); border-color:transparent; }
.service-card.wide{ grid-column:span 4; }
.service-card.narrow{ grid-column:span 2; }
.service-card .icon-badge{
  width:52px; height:52px; border-radius:14px; margin-bottom:22px;
  display:flex; align-items:center; justify-content:center;
  font-size:1.25rem; color:#fff;
}
.service-card:nth-child(1) .icon-badge{ background:linear-gradient(135deg, var(--blue-light), var(--blue)); }
.service-card:nth-child(2) .icon-badge{ background:linear-gradient(135deg, var(--blue), var(--purple)); }
.service-card:nth-child(3) .icon-badge{ background:linear-gradient(135deg, var(--purple), var(--red)); }
.service-card:nth-child(4) .icon-badge{ background:linear-gradient(135deg, var(--red), var(--orange)); }
.service-card h3{ font-size:1.22rem; font-weight:700; margin-bottom:10px; }
.service-card p{ color:var(--ink-soft); font-size:.97rem; }

@media (max-width:900px){
  .service-card, .service-card.wide, .service-card.narrow{ grid-column:span 6; }
}

/* ============================================================
   PORTFOLIO
   ============================================================ */
.portfolio-grid{
  display:grid; grid-template-columns:repeat(3,1fr); gap:26px;
}
.project-card{
  border-radius:var(--radius-lg); overflow:hidden; background:var(--ink);
  position:relative; box-shadow:var(--shadow-md);
  transition:transform .35s ease, box-shadow .35s ease;
}
.project-card:hover{ transform:translateY(-6px); box-shadow:var(--shadow-lg); }
.project-thumb{ height:210px; position:relative; overflow:hidden; }
.project-thumb svg{ width:100%; height:100%; display:block; }
.project-tag{
  position:absolute; top:14px; left:14px; z-index:2;
  font-size:.72rem; font-weight:700; letter-spacing:.02em;
  padding:6px 12px; border-radius:999px; color:#fff;
  background:rgba(20,22,43,.55); backdrop-filter:blur(6px);
}
.project-body{ padding:26px 26px 28px; background:var(--white); }
.project-body h3{ font-size:1.14rem; font-weight:700; margin-bottom:8px; }
.project-body p{ color:var(--ink-soft); font-size:.93rem; margin-bottom:16px; }
.project-meta{ display:flex; gap:10px; flex-wrap:wrap; }
.project-meta span{
  font-size:.76rem; font-weight:600; color:var(--purple);
  background:rgba(124,58,237,.08); padding:5px 11px; border-radius:999px;
}
@media (max-width:900px){ .portfolio-grid{ grid-template-columns:1fr; } }

/* ============================================================
   SKILLS / TECH STACK MATRIX
   ============================================================ */
.skills-columns{
  display:grid; grid-template-columns:repeat(3,1fr); gap:40px;
}
.skills-col h4{
  font-size:.86rem; font-weight:700; text-transform:none;
  color:var(--ink-faint); margin-bottom:20px; letter-spacing:.01em;
  padding-bottom:14px; border-bottom:1px solid var(--line);
}
.skill-row{ display:flex; align-items:center; gap:14px; padding:12px 0; }
.skill-row i{
  width:38px; height:38px; border-radius:10px; flex-shrink:0;
  display:flex; align-items:center; justify-content:center;
  font-size:1.05rem; color:#fff;
  background:linear-gradient(135deg, var(--blue), var(--purple));
}
.skill-row span{ font-weight:500; font-size:.96rem; }
@media (max-width:900px){ .skills-columns{ grid-template-columns:1fr; gap:8px; } }

/* ============================================================
   CONTACT / FOOTER
   ============================================================ */
.contact-section{
  background:var(--ink); color:#EDEEF7; overflow:hidden; position:relative;
}
.contact-section .organic{
  position:absolute; inset:0; opacity:.14; pointer-events:none;
}
.contact-grid{
  position:relative; z-index:1;
  display:grid; grid-template-columns:1.1fr .9fr; gap:64px; align-items:start;
}
.contact-grid h2{ color:#fff; font-size:clamp(1.9rem,3vw,2.5rem); margin-bottom:16px; }
.contact-grid > div > p{ color:#B6B9D4; font-size:1.03rem; max-width:460px; margin-bottom:34px; }
.contact-list{ display:flex; flex-direction:column; gap:18px; margin-bottom:34px; }
.contact-list a, .contact-list div{
  display:flex; align-items:center; gap:14px; font-size:.98rem; color:#EDEEF7; font-weight:500;
}
.contact-list i{
  width:42px; height:42px; border-radius:12px; flex-shrink:0;
  display:flex; align-items:center; justify-content:center;
  background:rgba(255,255,255,.08); color:#9FC8FF;
}
.contact-list a:hover{ color:var(--blue-light); }
.social-row{ display:flex; gap:12px; }
.social-row a{
  width:44px; height:44px; border-radius:12px; background:rgba(255,255,255,.08);
  display:flex; align-items:center; justify-content:center; font-size:1.05rem;
  transition:background .25s ease, transform .25s ease;
}
.social-row a:hover{ background:var(--gradient-flow); transform:translateY(-3px); }

.contact-card{
  background:rgba(255,255,255,.05); border:1px solid rgba(255,255,255,.1);
  border-radius:var(--radius-lg); padding:34px;
  backdrop-filter:blur(10px);
}
.contact-card h3{ color:#fff; font-size:1.2rem; margin-bottom:6px; }
.contact-card p{ color:#9DA0C0; font-size:.9rem; margin-bottom:22px; }
.form-row{ margin-bottom:16px; }
.form-row input, .form-row textarea{
  width:100%; padding:13px 16px; border-radius:10px;
  background:rgba(255,255,255,.06); border:1px solid rgba(255,255,255,.14);
  color:#fff; font-family:'Inter',sans-serif; font-size:.92rem;
}
.form-row input::placeholder, .form-row textarea::placeholder{ color:#787CA0; }
.form-row input:focus, .form-row textarea:focus{ outline:none; border-color:var(--blue-light); }
.form-row textarea{ resize:vertical; min-height:96px; }

@media (max-width:900px){ .contact-grid{ grid-template-columns:1fr; gap:40px; } }

.footer-bottom{
  position:relative; z-index:1;
  border-top:1px solid rgba(255,255,255,.1);
  margin-top:80px; padding-top:40px;
  display:flex; align-items:center; justify-content:space-between; flex-wrap:wrap; gap:24px;
}
.footer-brand{ display:flex; align-items:center; gap:14px; }
.footer-brand svg{ height:40px; width:40px; }
.footer-brand-text{ display:flex; flex-direction:column; }
.footer-brand-title{ font-family:'Outfit', sans-serif; font-weight:700; font-size:1.2rem; color:#fff; }
.footer-brand-title span{ background:linear-gradient(90deg, var(--blue-light), var(--purple)); -webkit-background-clip:text; background-clip:text; color:transparent; }
.footer-brand span.slogan{ color:#9DA0C0; font-size:.86rem; }
.footer-links{ display:flex; gap:28px; flex-wrap:wrap; }
.footer-links a{ color:#B6B9D4; font-size:.88rem; }
.footer-links a:hover{ color:#fff; }
.footer-copy{ color:#787CA0; font-size:.82rem; width:100%; margin-top:8px; }

/* ============================================================
   MISC
   ============================================================ */
.gradient-divider{ height:2px; background:var(--gradient-flow); border:0; opacity:.5; }
::selection{ background:rgba(124,58,237,.22); }
</style>
</head>
<body>

<!-- ============================================================
     NAVIGATION
     ============================================================ -->
<nav class="navbar" id="navbar">
  <div class="nav-inner">
    <a href="#top" class="brand">
      <!-- INLINE VECTOR BRAND ICON -->
      <svg viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="navGrad" x1="0" y1="0" x2="100" y2="100" gradientUnits="userSpaceOnUse">
            <stop offset="0%" stop-color="#38BDF8"/>
            <stop offset="40%" stop-color="#2563EB"/>
            <stop offset="70%" stop-color="#7C3AED"/>
            <stop offset="100%" stop-color="#EF4444"/>
          </linearGradient>
        </defs>
        <path d="M25 35 L50 20 L75 35 L75 65 L50 80 L25 65 Z" stroke="url(#navGrad)" stroke-width="6" stroke-linejoin="round"/>
        <line x1="25" y1="35" x2="75" y2="65" stroke="url(#navGrad)" stroke-width="3" stroke-dasharray="4 4"/>
        <line x1="75" y1="35" x2="25" y2="65" stroke="url(#navGrad)" stroke-width="3" stroke-dasharray="4 4"/>
        <circle cx="25" cy="35" r="8" fill="#38BDF8"/>
        <circle cx="50" cy="20" r="8" fill="#2563EB"/>
        <circle cx="75" cy="35" r="8" fill="#7C3AED"/>
        <circle cx="75" cy="65" r="8" fill="#EF4444"/>
        <circle cx="50" cy="80" r="8" fill="#F97316"/>
        <circle cx="25" cy="65" r="8" fill="#7C3AED"/>
      </svg>
      <span class="brand-word"><span class="pixel">Pixel</span><span class="mind">Mind</span></span>
    </a>
    <div class="nav-links">
      <a href="#services">Services</a>
      <a href="#portfolio">Portfolio</a>
      <a href="#skills">Skills</a>
      <a href="#contact">Contact</a>
    </div>
    <div class="nav-actions">
      <a href="#contact" class="btn btn-ghost">Contact Us</a>
      <a href="#contact" class="btn btn-primary">Get Started</a>
      <button class="nav-toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>
  <div class="mobile-panel" id="mobilePanel">
    <a href="#services">Services</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#skills">Skills</a>
    <a href="#contact">Contact</a>
    <a href="#contact" class="btn btn-primary btn-block">Get Started</a>
  </div>
</nav>

<!-- ============================================================
     HERO
     ============================================================ -->
<header class="hero" id="top">
  <div class="hero-blob b1"></div>
  <div class="hero-blob b2"></div>
  <div class="container hero-grid">
    <div class="hero-copy">
      <div class="hero-eyebrow-line"><span class="dot"></span> Web Design Studio · South Africa</div>
      <h1>Websites built for where your business is <span class="accent">going next</span></h1>
      <p class="lead">Pixelmind rebuilds outdated sites into fast, modern experiences — engineered with clean code, thoughtful motion, and AI-enhanced visuals that actually fit your brand.</p>
      <div class="hero-ctas">
        <a href="#portfolio" class="btn btn-primary"><i class="fa-solid fa-arrow-up-right-from-square"></i> View Work</a>
        <a href="#contact" class="btn btn-ghost">Contact Us</a>
      </div>
      <div class="hero-trust">
        <div><strong>Renovation-first</strong>Old site, new foundation — no starting from zero</div>
        <div><strong>AI-enhanced</strong>Custom visuals generated for your brand, not stock photos</div>
        <div><strong>Built to launch</strong>Modern stack, responsive by default</div>
      </div>
    </div>

    <div class="hero-visual">
      <!-- HERO BANNER VISUAL: Dynamic Animated Node Network -->
      <svg viewBox="0 0 500 500" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="edgeGrad" x1="0" y1="0" x2="500" y2="500" gradientUnits="userSpaceOnUse">
            <stop offset="0%" stop-color="#38BDF8"/>
            <stop offset="40%" stop-color="#2563EB"/>
            <stop offset="70%" stop-color="#7C3AED"/>
            <stop offset="100%" stop-color="#EF4444"/>
          </linearGradient>
          <radialGradient id="n1" cx="35%" cy="35%" r="70%"><stop offset="0%" stop-color="#7DD3FC"/><stop offset="100%" stop-color="#2563EB"/></radialGradient>
          <radialGradient id="n2" cx="35%" cy="35%" r="70%"><stop offset="0%" stop-color="#A78BFA"/><stop offset="100%" stop-color="#6D28D9"/></radialGradient>
          <radialGradient id="n3" cx="35%" cy="35%" r="70%"><stop offset="0%" stop-color="#FCA5A5"/><stop offset="100%" stop-color="#DC2626"/></radialGradient>
          <radialGradient id="n4" cx="35%" cy="35%" r="70%"><stop offset="0%" stop-color="#FDBA74"/><stop offset="100%" stop-color="#EA580C"/></radialGradient>
        </defs>

        <g class="edges" stroke="url(#edgeGrad)" stroke-width="2" opacity="0.85">
          <line class="edge" x1="110" y1="180" x2="220" y2="120" style="animation-delay:.1s"/>
          <line class="edge" x1="220" y1="120" x2="330" y2="150" style="animation-delay:.2s"/>
          <line class="edge" x1="110" y1="180" x2="180" y2="260" style="animation-delay:.3s"/>
          <line class="edge" x1="180" y1="260" x2="220" y2="120" style="animation-delay:.4s"/>
          <line class="edge" x1="180" y1="260" x2="300" y2="270" style="animation-delay:.5s"/>
          <line class="edge" x1="300" y1="270" x2="330" y2="150" style="animation-delay:.6s"/>
          <line class="edge" x1="300" y1="270" x2="390" y2="210" style="animation-delay:.7s"/>
          <line class="edge" x1="330" y1="150" x2="390" y2="210" style="animation-delay:.8s"/>
          <line class="edge" x1="390" y1="210" x2="410" y2="130" style="animation-delay:.9s"/>
          <line class="edge" x1="180" y1="260" x2="150" y2="330" style="animation-delay:1s"/>
          <line class="edge" x1="150" y1="330" x2="270" y2="350" style="animation-delay:1.1s"/>
          <line class="edge" x1="270" y1="350" x2="300" y2="270" style="animation-delay:1.2s"/>
        </g>

        <g class="node pulse" style="animation-delay:1.3s"><circle cx="110" cy="180" r="30" fill="url(#n1)"/></g>
        <g class="node" style="animation-delay:.9s"><circle cx="220" cy="120" r="16" fill="url(#n1)"/></g>
        <g class="node pulse" style="animation-delay:1.1s"><circle cx="330" cy="150" r="22" fill="url(#n2)"/></g>
        <g class="node" style="animation-delay:1.4s"><circle cx="180" cy="260" r="13" fill="url(#n1)"/></g>
        <g class="node pulse" style="animation-delay:1.2s"><circle cx="300" cy="270" r="26" fill="url(#n2)"/></g>
        <g class="node" style="animation-delay:1.5s"><circle cx="390" cy="210" r="19" fill="url(#n3)"/></g>
        <g class="node" style="animation-delay:1.6s"><circle cx="410" cy="130" r="12" fill="url(#n4)"/></g>
        <g class="node" style="animation-delay:1.7s"><circle cx="150" cy="330" r="11" fill="url(#n2)"/></g>
        <g class="node" style="animation-delay:1.8s"><circle cx="270" cy="350" r="15" fill="url(#n2)"/></g>
      </svg>

      <div class="glass-card gc1"><i class="fa-solid fa-wand-magic-sparkles" style="color:#7C3AED"></i> AI visuals, generated</div>
      <div class="glass-card gc2"><i class="fa-solid fa-bolt" style="color:#2563EB"></i> Fast, modern build</div>
      <div class="glass-card gc3"><i class="fa-solid fa-mobile-screen" style="color:#EF4444"></i> Responsive everywhere</div>
    </div>
  </div>
</header>

<!-- ============================================================
     SERVICES
     ============================================================ -->
<section id="services">
  <div class="container">
    <div class="section-head reveal">
      <h2>What we do</h2>
      <p>Four capabilities, one goal: a site that looks and feels like where your brand is headed.</p>
    </div>
    <div class="services-grid reveal">
      <div class="service-card wide">
        <div class="icon-badge"><i class="fa-solid fa-rotate"></i></div>
        <h3>Advanced Web Design &amp; Renovation</h3>
        <p>We take outdated sites — slow, cluttered, hard to update — and rebuild them from the ground up: modern layout, faster load times, and a structure that's easy to maintain.</p>
      </div>
      <div class="service-card narrow">
        <div class="icon-badge"><i class="fa-solid fa-wand-magic-sparkles"></i></div>
        <h3>AI-Generated Visuals</h3>
        <p>Custom imagery and tech media generated for your brand, not stock photography.</p>
      </div>
      <div class="service-card narrow">
        <div class="icon-badge"><i class="fa-solid fa-film"></i></div>
        <h3>Motion &amp; Animation</h3>
        <p>Smooth, purposeful interactions inspired by modern motion design — never decoration for its own sake.</p>
      </div>
      <div class="service-card wide">
        <div class="icon-badge"><i class="fa-brands fa-github"></i></div>
        <h3>GitHub &amp; Modern Stack Integration</h3>
        <p>Version-controlled, deployable builds using a current front-end toolchain — so your site is easy to hand off, extend, or scale later.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============================================================
     PORTFOLIO
     ============================================================ -->
<section id="portfolio" class="section-alt">
  <div class="container">
    <div class="section-head reveal">
      <h2>Selected work</h2>
      <p>A live client build alongside a couple of concept explorations that show the range we design across.</p>
    </div>

    <div class="portfolio-grid reveal">

      <!-- Project 1: Bridge Street (Warm, ambient bistro & smokehouse AI composition) -->
      <div class="project-card">
        <div class="project-thumb">
          <span class="project-tag">In Progress</span>
          <svg viewBox="0 0 400 210" width="100%" height="100%" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <linearGradient id="bgBistro" x1="0" y1="0" x2="400" y2="210" gradientUnits="userSpaceOnUse">
                <stop offset="0%" stop-color="#1A0C06"/>
                <stop offset="50%" stop-color="#421C0E"/>
                <stop offset="100%" stop-color="#7A3418"/>
              </linearGradient>
              <radialGradient id="glowGqeberha" cx="50%" cy="50%" r="50%">
                <stop offset="0%" stop-color="#F97316" stop-opacity="0.4"/>
                <stop offset="100%" stop-color="#1A0C06" stop-opacity="0"/>
              </radialGradient>
            </defs>
            <rect width="400" height="210" fill="url(#bgBistro)"/>
            <circle cx="200" cy="105" r="140" fill="url(#glowGqeberha)"/>
            
            <!-- AI Stylized Culinary & Musical Lines -->
            <path d="M 0 160 Q 100 120, 200 150 T 400 110" fill="none" stroke="#FDBA74" stroke-width="1.5" opacity="0.4"/>
            <path d="M 0 180 Q 120 140, 240 170 T 400 130" fill="none" stroke="#EF4444" stroke-width="1" opacity="0.3"/>
            
            <!-- Bistro Bar / Stage Glass Frame -->
            <rect x="40" y="30" width="320" height="150" rx="12" fill="rgba(255,255,255,0.04)" stroke="rgba(251,146,60,0.3)" stroke-width="1"/>
            
            <!-- Ambient Light Nodes -->
            <circle cx="100" cy="70" r="4" fill="#FDBA74"/>
            <line x1="100" y1="30" x2="100" y2="66" stroke="#FDBA74" stroke-width="1" opacity="0.5"/>
            <circle cx="200" cy="60" r="6" fill="#F97316"/>
            <line x1="200" y1="30" x2="200" y2="54" stroke="#F97316" stroke-width="1" opacity="0.5"/>
            <circle cx="300" cy="75" r="4" fill="#FCA5A5"/>
            <line x1="300" y1="30" x2="300" y2="71" stroke="#FCA5A5" stroke-width="1" opacity="0.5"/>
            
            <!-- Audio Wave Visualizer Art -->
            <g fill="#FDBA74" opacity="0.7">
              <rect x="140" y="110" width="4" height="20" rx="2"/>
              <rect x="150" y="100" width="4" height="40" rx="2"/>
              <rect x="160" y="90" width="4" height="60" rx="2"/>
              <rect x="170" y="105" width="4" height="30" rx="2"/>
              <rect x="180" y="85" width="4" height="70" rx="2"/>
              <rect x="190" y="95" width="4" height="50" rx="2"/>
              <rect x="200" y="80" width="4" height="80" rx="2"/>
              <rect x="210" y="100" width="4" height="40" rx="2"/>
              <rect x="220" y="90" width="4" height="60" rx="2"/>
              <rect x="230" y="110" width="4" height="20" rx="2"/>
              <rect x="240" y="105" width="4" height="30" rx="2"/>
              <rect x="250" y="115" width="4" height="10" rx="2"/>
            </g>
            <text x="200" y="180" font-family="'Outfit', sans-serif" font-size="11" fill="#FDBA74" text-anchor="middle" letter-spacing="2" opacity="0.8">BRIDGE STREET BISTRO</text>
          </svg>
        </div>
        <div class="project-body">
          <h3>Bridge Street Bistro &amp; Smokehouse</h3>
          <p>A restaurant, bar &amp; live-music venue site for Gqeberha — warm, moody visuals with a menu and events flow built for mobile.</p>
          <div class="project-meta"><span>Restaurant</span><span>Live Music</span><span>Gqeberha, SA</span></div>
        </div>
      </div>

      <!-- Project 2: SaaS concept (Aperture Analytics AI Dark Glass Interface) -->
      <div class="project-card">
        <div class="project-thumb">
          <span class="project-tag">Concept</span>
          <svg viewBox="0 0 400 210" width="100%" height="100%" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <linearGradient id="bgSaaS" x1="0" y1="0" x2="400" y2="210" gradientUnits="userSpaceOnUse">
                <stop offset="0%" stop-color="#0B1021"/>
                <stop offset="60%" stop-color="#111836"/>
                <stop offset="100%" stop-color="#1E295B"/>
              </linearGradient>
            </defs>
            <rect width="400" height="210" fill="url(#bgSaaS)"/>
            
            <!-- Tech Grid Lines -->
            <g stroke="rgba(56, 189, 248, 0.08)" stroke-width="1">
              <line x1="0" y1="40" x2="400" y2="40"/>
              <line x1="0" y1="80" x2="400" y2="80"/>
              <line x1="0" y1="120" x2="400" y2="120"/>
              <line x1="0" y1="160" x2="400" y2="160"/>
              <line x1="80" y1="0" x2="80" y2="210"/>
              <line x1="160" y1="0" x2="160" y2="210"/>
              <line x1="240" y1="0" x2="240" y2="210"/>
              <line x1="320" y1="0" x2="320" y2="210"/>
            </g>
            
            <!-- Dashboard Glass Panel -->
            <rect x="30" y="25" width="340" height="160" rx="10" fill="rgba(255,255,255,0.03)" stroke="rgba(255,255,255,0.12)" stroke-width="1"/>
            
            <!-- Analytics Chart Area -->
            <path d="M 50 140 L 110 110 L 170 125 L 230 75 L 290 90 L 350 45" fill="none" stroke="#38BDF8" stroke-width="3"/>
            <path d="M 50 140 L 110 110 L 170 125 L 230 75 L 290 90 L 350 45 L 350 160 L 50 160 Z" fill="url(#bgSaaS)" opacity="0.5"/>
            
            <!-- Floating Glowing Nodes -->
            <circle cx="230" cy="75" r="5" fill="#7C3AED"/>
            <circle cx="230" cy="75" r="9" fill="none" stroke="#7C3AED" stroke-width="1.5" opacity="0.6"/>
            <circle cx="350" cy="45" r="5" fill="#38BDF8"/>
            
            <!-- UI Widgets -->
            <rect x="50" y="40" width="80" height="24" rx="5" fill="rgba(56, 189, 248, 0.15)"/>
            <rect x="60" y="48" width="40" height="8" rx="2" fill="#38BDF8"/>
          </svg>
        </div>
        <div class="project-body">
          <h3>Aperture Analytics</h3>
          <p>A dashboard-first landing page concept for a data analytics product — dark UI, glassmorphic cards, animated metrics.</p>
          <div class="project-meta"><span>SaaS</span><span>Dashboard</span></div>
        </div>
      </div>

      <!-- Project 3: Tech portal concept (Meridian Neural Matrix AI Visual) -->
      <div class="project-card">
        <div class="project-thumb">
          <span class="project-tag">Concept</span>
          <svg viewBox="0 0 400 210" width="100%" height="100%" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <linearGradient id="bgPortal" x1="0" y1="0" x2="400" y2="210" gradientUnits="userSpaceOnUse">
                <stop offset="0%" stop-color="#0A0E1F"/>
                <stop offset="50%" stop-color="#1A1440"/>
                <stop offset="100%" stop-color="#3B1578"/>
              </linearGradient>
            </defs>
            <rect width="400" height="210" fill="url(#bgPortal)"/>
            
            <!-- Neural Network Web -->
            <g stroke="#8B5CF6" stroke-width="1.2" opacity="0.45">
              <line x1="50" y1="50" x2="150" y2="110"/>
              <line x1="150" y1="110" x2="270" y2="60"/>
              <line x1="150" y1="110" x2="190" y2="160"/>
              <line x1="270" y1="60" x2="350" y2="130"/>
              <line x1="190" y1="160" x2="330" y2="175"/>
              <line x1="50" y1="50" x2="90" y2="170"/>
              <line x1="90" y1="170" x2="190" y2="160"/>
            </g>
            
            <!-- AI Nodes -->
            <circle cx="50" cy="50" r="6" fill="#38BDF8"/>
            <circle cx="150" cy="110" r="10" fill="#7C3AED"/>
            <circle cx="270" cy="60" r="7" fill="#38BDF8"/>
            <circle cx="190" cy="160" r="8" fill="#EF4444"/>
            <circle cx="350" cy="130" r="5" fill="#F97316"/>
            <circle cx="330" cy="175" r="6" fill="#7C3AED"/>
            <circle cx="90" cy="170" r="5" fill="#38BDF8"/>
            
            <!-- Code Bracket Graphic Overlay -->
            <text x="320" y="55" font-family="monospace" font-size="22" fill="rgba(255,255,255,0.2)">&lt;/&gt;</text>
            <text x="40" y="130" font-family="monospace" font-size="18" fill="rgba(255,255,255,0.15)">{ AI }</text>
          </svg>
        </div>
        <div class="project-body">
          <h3>Meridian Tech Portal</h3>
          <p>An internal-tools portal concept blending a dark interface with node-based visuals — built to explain complex systems simply.</p>
          <div class="project-meta"><span>Tech Portal</span><span>Dark UI</span></div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ============================================================
     SKILLS / TECH STACK MATRIX
     ============================================================ -->
<section id="skills">
  <div class="container">
    <div class="section-head reveal">
      <h2>Tech stack &amp; skills</h2>
      <p>The core toolkit behind every Pixelmind build.</p>
    </div>
    <div class="skills-columns reveal">
      <div class="skills-col">
        <h4>Frontend Core</h4>
        <div class="skill-row"><i class="fa-brands fa-html5"></i><span>HTML5</span></div>
        <div class="skill-row"><i class="fa-brands fa-css3-alt"></i><span>CSS3</span></div>
        <div class="skill-row"><i class="fa-brands fa-js"></i><span>JavaScript (ES6+)</span></div>
        <div class="skill-row"><i class="fa-solid fa-mobile-screen-button"></i><span>Mobile-First Responsive Design</span></div>
      </div>
      <div class="skills-col">
        <h4>Styling &amp; Frameworks</h4>
        <div class="skill-row"><i class="fa-solid fa-sliders"></i><span>Custom CSS Variables</span></div>
        <div class="skill-row"><i class="fa-solid fa-table-cells"></i><span>Flexbox &amp; Grid</span></div>
        <div class="skill-row"><i class="fa-solid fa-wand-magic-sparkles"></i><span>CSS Animation</span></div>
        <div class="skill-row"><i class="fa-solid fa-layer-group"></i><span>Glassmorphism</span></div>
      </div>
      <div class="skills-col">
        <h4>Design &amp; Aesthetics</h4>
        <div class="skill-row"><i class="fa-solid fa-object-group"></i><span>Modern UI/UX</span></div>
        <div class="skill-row"><i class="fa-solid fa-font"></i><span>Typography Systems</span></div>
        <div class="skill-row"><i class="fa-solid fa-arrows-turn-to-dots"></i><span>Interactive Motion Design</span></div>
        <div class="skill-row"><i class="fa-solid fa-photo-film"></i><span>High-Impact Media Integration</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================================================
     CONTACT / FOOTER
     ============================================================ -->
<section id="contact" class="contact-section">
  <!-- Subtle SVG Background Wave & Organic Art -->
  <svg class="organic" viewBox="0 0 1200 700" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
    <path d="M-40 620 C 140 520, 180 420, 120 320 S 240 140, 420 180 S 560 340, 700 300 S 860 120, 1040 160 S 1220 340, 1260 260"
          fill="none" stroke="#38BDF8" stroke-width="1.4"/>
    <path d="M-20 660 C 160 600, 220 500, 180 420 S 320 260, 480 300 S 620 460, 780 400 S 940 220, 1100 260"
          fill="none" stroke="#7C3AED" stroke-width="1.2"/>
    <g fill="none" stroke="#EF4444" stroke-width="1">
      <path d="M300 200 q 20 -30 40 0 q 20 30 40 0"/>
      <path d="M780 480 q 20 -30 40 0 q 20 30 40 0"/>
    </g>
  </svg>

  <div class="container">
    <div class="contact-grid">
      <div>
        <h2 class="reveal">Let's build something that actually works</h2>
        <p class="reveal">Tell us about your project — a tired site that needs a rebuild, or something new from scratch. We usually reply within a day.</p>

        <div class="contact-list reveal">
          <a href="tel:+27761501439"><i class="fa-solid fa-phone"></i> +27 76 150 1439 (Phone / WhatsApp)</a>
          <a href="mailto:pixelmind.webstudio@gmail.com"><i class="fa-solid fa-envelope"></i> pixelmind.webstudio@gmail.com</a>
          <a href="mailto:Lathithamajavu123@gmail.com"><i class="fa-solid fa-paper-plane"></i> Lathithamajavu123@gmail.com (Direct)</a>
          <div><i class="fa-solid fa-location-dot"></i> South Africa (+27)</div>
        </div>

        <div class="social-row reveal">
          <a href="https://facebook.com" target="_blank" rel="noopener" aria-label="Pixelmind on Facebook"><i class="fa-brands fa-facebook-f"></i></a>
          <a href="https://linkedin.com" target="_blank" rel="noopener" aria-label="Pixelmind Web Design Studio on LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
          <a href="https://instagram.com" target="_blank" rel="noopener" aria-label="@pixelmindstudio7 on Instagram"><i class="fa-brands fa-instagram"></i></a>
        </div>
      </div>

      <div class="contact-card reveal">
        <h3>Start a project</h3>
        <p>Fill this in and we'll get back to you shortly.</p>
        <form id="contactForm" onsubmit="return false;">
          <div class="form-row"><input type="text" placeholder="Your name" required></div>
          <div class="form-row"><input type="email" placeholder="Email address" required></div>
          <div class="form-row"><textarea placeholder="Tell us about your project"></textarea></div>
          <button type="submit" class="btn btn-primary btn-block">Send Message</button>
        </form>
      </div>
    </div>

    <div class="footer-bottom">
      <div class="footer-brand">
        <!-- FOOTER BRAND LOCKUP -->
        <svg viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M25 35 L50 20 L75 35 L75 65 L50 80 L25 65 Z" stroke="url(#navGrad)" stroke-width="6" stroke-linejoin="round"/>
          <circle cx="25" cy="35" r="8" fill="#38BDF8"/>
          <circle cx="50" cy="20" r="8" fill="#2563EB"/>
          <circle cx="75" cy="35" r="8" fill="#7C3AED"/>
          <circle cx="75" cy="65" r="8" fill="#EF4444"/>
          <circle cx="50" cy="80" r="8" fill="#F97316"/>
          <circle cx="25" cy="65" r="8" fill="#7C3AED"/>
        </svg>
        <div class="footer-brand-text">
          <div class="footer-brand-title">Pixel<span>Mind</span></div>
          <span class="slogan">Modernizing Websites, Elevating Brands, and Harnessing AI Innovation.</span>
        </div>
      </div>
      <div class="footer-links">
        <a href="#services">Services</a>
        <a href="#portfolio">Portfolio</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
      </div>
      <div class="footer-copy">© <span id="year"></span> Pixelmind Web Design Studio. All rights reserved.</div>
    </div>
  </div>
</section>

<script>
// Mobile nav toggle
const navToggle = document.getElementById('navToggle');
const mobilePanel = document.getElementById('mobilePanel');
navToggle.addEventListener('click', () => {
  const open = navToggle.classList.toggle('open');
  mobilePanel.classList.toggle('open');
  navToggle.setAttribute('aria-expanded', open);
});
mobilePanel.querySelectorAll('a').forEach(a => a.addEventListener('click', () => {
  navToggle.classList.remove('open');
  mobilePanel.classList.remove('open');
  navToggle.setAttribute('aria-expanded', false);
}));

// Navbar scroll shadow
const navbar = document.getElementById('navbar');
window.addEventListener('scroll', () => {
  navbar.classList.toggle('scrolled', window.scrollY > 12);
}, { passive: true });

// Smooth scroll for in-page anchors
document.querySelectorAll('a[href^="#"]').forEach(link => {
  link.addEventListener('click', function(e){
    const id = this.getAttribute('href');
    if(id.length > 1){
      const target = document.querySelector(id);
      if(target){
        e.preventDefault();
        target.scrollIntoView({ behavior:'smooth', block:'start' });
      }
    }
  });
});

// Restrained scroll-reveal
const revealEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if(entry.isIntersecting){
      entry.target.classList.add('is-visible');
      io.unobserve(entry.target);
    }
  });
}, { threshold: 0.15, rootMargin: '0px 0px -60px 0px' });
revealEls.forEach(el => io.observe(el));

// Simple contact form handoff to mailto
const form = document.getElementById('contactForm');
form.addEventListener('submit', function(){
  const name = form.querySelector('input[type="text"]').value;
  const email = form.querySelector('input[type="email"]').value;
  const message = form.querySelector('textarea').value;
  const subject = encodeURIComponent('New project inquiry — ' + name);
  const body = encodeURIComponent(message + '\n\nFrom: ' + name + ' (' + email + ')');
  window.location.href = 'mailto:pixelmind.webstudio@gmail.com?subject=' + subject + '&body=' + body;
});

document.getElementById('year').textContent = new Date().getFullYear();
</script>
</body>
</html>
