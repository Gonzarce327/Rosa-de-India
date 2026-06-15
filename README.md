<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rosa de India · Herbolario Natural · Villanueva de la Cañada</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400;1,600&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --night: #0A1A0C;
    --forest: #1B3D24;
    --sage: #3D6E52;
    --leaf: #7AAE8A;
    --gold: #C49830;
    --gold-pale: #DDB86A;
    --rose: #B8697A;
    --rose-pale: #D49AA7;
    --cream: #F5F0E6;
    --white: #FCFAF6;
    --ink: #1A1A17;
    --muted: #5A5A55;
    --light-text: #F8F5EE;
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior: smooth; }
  body { font-family:'Jost',sans-serif; background:var(--white); color:var(--ink); overflow-x:hidden; }

  /* ─── NAV ─── */
  nav {
    position:fixed; top:0; width:100%; z-index:200;
    display:flex; justify-content:space-between; align-items:center;
    padding:0 56px; height:64px;
    background:rgba(10,26,12,0.88); backdrop-filter:blur(12px);
    border-bottom:1px solid rgba(196,152,48,0.18); transition:background 0.4s;
  }
  nav.solid { background:rgba(10,26,12,0.98); }
  .nav-brand { font-family:'Cormorant Garamond',serif; font-size:1.25rem; font-weight:400; color:var(--light-text); letter-spacing:0.08em; }
  .nav-brand em { font-style:italic; color:var(--gold-pale); }
  .nav-links { display:flex; gap:40px; list-style:none; }
  .nav-links a { color:rgba(248,245,238,0.6); text-decoration:none; font-size:0.7rem; letter-spacing:0.18em; text-transform:uppercase; font-weight:500; transition:color 0.25s; }
  .nav-links a:hover { color:var(--gold-pale); }

  /* ─── HERO ─── */
  .hero {
    min-height:100vh; background:var(--night);
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    text-align:center; padding:120px 24px 100px; position:relative; overflow:hidden;
  }
  .hero-glow { position:absolute; inset:0; pointer-events:none; background:radial-gradient(ellipse 55% 55% at 50% 42%, rgba(61,110,82,0.14) 0%, transparent 72%); }
  .hero-rose { width:200px; height:200px; margin-bottom:44px; animation:sway 7s ease-in-out infinite; position:relative; z-index:1; }
  @keyframes sway { 0%,100%{transform:translateY(0) rotate(-0.5deg);} 50%{transform:translateY(-10px) rotate(0.5deg);} }
  .hero-eyebrow { font-size:0.68rem; letter-spacing:0.32em; text-transform:uppercase; color:var(--gold); margin-bottom:18px; font-weight:600; position:relative; z-index:1; }
  .hero h1 { font-family:'Cormorant Garamond',serif; font-size:clamp(4rem,10vw,7.5rem); font-weight:300; line-height:0.92; color:var(--light-text); letter-spacing:-0.01em; margin-bottom:6px; position:relative; z-index:1; }
  .hero h1 em { font-style:italic; color:var(--rose-pale); }
  .hero-tagline { font-family:'Cormorant Garamond',serif; font-size:clamp(1.1rem,2.5vw,1.55rem); font-style:italic; font-weight:300; color:rgba(248,245,238,0.45); margin-bottom:52px; letter-spacing:0.02em; position:relative; z-index:1; }
  .btn-outline { display:inline-block; padding:13px 38px; border:1px solid rgba(196,152,48,0.55); color:var(--gold-pale); text-decoration:none; font-size:0.72rem; letter-spacing:0.22em; text-transform:uppercase; font-weight:600; transition:all 0.3s; position:relative; z-index:1; }
  .btn-outline:hover { background:var(--gold); color:var(--night); border-color:var(--gold); }
  .hero-arrow { position:absolute; bottom:36px; left:50%; transform:translateX(-50%); z-index:1; display:flex; flex-direction:column; align-items:center; gap:8px; }
  .arrow-stem { width:1px; height:44px; background:linear-gradient(to bottom,rgba(196,152,48,0.6),transparent); animation:pulse 2.2s ease-in-out infinite; }
  @keyframes pulse { 0%,100%{opacity:0.3;} 50%{opacity:1;} }

  /* ─── VIDEO SECTION ─── */
  .video-section { position:relative; width:100%; height:70vh; overflow:hidden; background:var(--night); }
  .video-section video { width:100%; height:100%; object-fit:cover; display:block; }
  .video-overlay {
    position:absolute; inset:0; pointer-events:none;
    background:linear-gradient(to bottom,rgba(10,26,12,0.35) 0%,rgba(10,26,12,0.1) 40%,rgba(10,26,12,0.45) 100%);
  }
  .video-label {
    position:absolute; bottom:28px; left:50%; transform:translateX(-50%);
    font-size:0.65rem; letter-spacing:0.28em; text-transform:uppercase;
    color:rgba(248,245,238,0.5); font-weight:600;
    display:flex; align-items:center; gap:10px;
  }
  .video-label::before, .video-label::after { content:''; width:32px; height:1px; background:rgba(196,152,48,0.4); }
  /* Fallback animated placeholder while video loads or generates */
  .video-placeholder {
    position:absolute; inset:0;
    background:linear-gradient(135deg,#0A1A0C 0%,#1B3D24 35%,#2D5A3A 55%,#1B3D24 75%,#0A1A0C 100%);
    background-size:400% 400%;
    animation:gradientShift 8s ease infinite;
    display:flex; align-items:center; justify-content:center;
  }
  @keyframes gradientShift { 0%{background-position:0% 50%;} 50%{background-position:100% 50%;} 100%{background-position:0% 50%;} }
  .video-placeholder svg { opacity:0.12; width:220px; height:220px; }

  /* ─── PULL QUOTE ─── */
  .pull-quote { background:var(--forest); padding:52px 24px; text-align:center; }
  .pull-quote blockquote { font-family:'Cormorant Garamond',serif; font-size:clamp(1.25rem,3vw,1.9rem); font-weight:300; font-style:italic; color:var(--light-text); max-width:640px; margin:0 auto; line-height:1.75; }
  .pull-quote cite { display:block; margin-top:18px; font-size:0.68rem; letter-spacing:0.22em; text-transform:uppercase; color:var(--gold); font-style:normal; font-weight:600; font-family:'Jost',sans-serif; }

  /* ─── SECTIONS ─── */
  section { padding:100px 24px; }
  .wrap { max-width:1080px; margin:0 auto; }
  .eyebrow { font-size:0.68rem; letter-spacing:0.28em; text-transform:uppercase; color:var(--sage); font-weight:600; margin-bottom:14px; }
  .section-h { font-family:'Cormorant Garamond',serif; font-size:clamp(2rem,5vw,3.2rem); font-weight:300; line-height:1.1; color:var(--forest); margin-bottom:28px; }
  .section-h em { font-style:italic; }

  /* ─── ABOUT ─── */
  .about { background:var(--white); }
  .about-grid { display:grid; grid-template-columns:1fr 1fr; gap:80px; align-items:start; }
  .about-body p { color:var(--muted); line-height:1.85; font-size:0.92rem; font-weight:300; margin-bottom:18px; }
  .about-body strong { color:var(--forest); font-weight:600; }
  .stats { display:flex; flex-direction:column; gap:18px; margin-top:8px; }
  .stat { padding:22px 26px; border-left:2px solid var(--gold); background:var(--cream); }
  .stat-n { font-family:'Cormorant Garamond',serif; font-size:2.6rem; font-weight:300; color:var(--forest); line-height:1; }
  .stat-l { font-size:0.76rem; color:var(--muted); letter-spacing:0.04em; margin-top:6px; font-weight:300; }

  /* ─── NEWS SECTION ─── */
  .news { background:linear-gradient(135deg,var(--sage) 0%,var(--forest) 100%); }
  .news .eyebrow { color:rgba(248,245,238,0.65); }
  .news .section-h { color:var(--light-text); }
  .news-grid { display:grid; grid-template-columns:repeat(4,1fr); gap:16px; margin-top:44px; }
  .news-card {
    background:rgba(255,255,255,0.07); border:1px solid rgba(255,255,255,0.12);
    padding:28px 24px; transition:background 0.3s, transform 0.3s;
    cursor:default; position:relative; overflow:hidden;
  }
  .news-card::before { content:''; position:absolute; top:0; left:0; width:100%; height:2px; background:var(--gold); transform:scaleX(0); transition:transform 0.3s; transform-origin:left; }
  .news-card:hover { background:rgba(255,255,255,0.12); transform:translateY(-3px); }
  .news-card:hover::before { transform:scaleX(1); }
  .news-date { font-size:0.62rem; letter-spacing:0.2em; text-transform:uppercase; color:var(--gold-pale); font-weight:600; margin-bottom:12px; opacity:0.85; }
  .news-title { font-family:'Cormorant Garamond',serif; font-size:1.08rem; font-weight:400; color:var(--light-text); line-height:1.45; margin-bottom:10px; }
  .news-body { font-size:0.78rem; color:rgba(248,245,238,0.55); line-height:1.65; font-weight:300; }
  .news-source { font-size:0.65rem; color:rgba(248,245,238,0.35); letter-spacing:0.1em; margin-top:14px; font-weight:500; }
  .news-source a { color:var(--gold-pale); text-decoration:none; opacity:0.7; transition:opacity 0.2s; }
  .news-source a:hover { opacity:1; }

  /* ─── PRODUCT CATEGORIES ─── */
  .products { background:var(--cream); }
  .products-head { text-align:center; max-width:540px; margin:0 auto 52px; }
  .cat-tabs {
    display:flex; gap:0; overflow-x:auto; margin-bottom:3px;
    scrollbar-width:none; -webkit-overflow-scrolling:touch;
  }
  .cat-tabs::-webkit-scrollbar { display:none; }
  .cat-tab {
    flex-shrink:0; padding:14px 26px;
    background:var(--white); border:none; cursor:pointer;
    font-family:'Jost',sans-serif; font-size:0.78rem;
    font-weight:500; letter-spacing:0.08em; text-transform:uppercase;
    color:var(--muted); transition:all 0.25s;
    border-bottom:2px solid transparent; position:relative;
  }
  .cat-tab:hover { color:var(--forest); background:rgba(245,240,230,0.6); }
  .cat-tab.active { color:var(--forest); background:var(--cream); border-bottom-color:var(--gold); font-weight:600; }
  .cat-tab .tab-icon { display:block; font-size:1.3rem; margin-bottom:5px; }
  .products-grid {
    display:grid; grid-template-columns:repeat(3,1fr);
    gap:3px; min-height:360px;
  }
  .pcard {
    background:var(--white); padding:36px 28px;
    transition:background 0.3s; position:relative; overflow:hidden;
    display:none;
  }
  .pcard.visible { display:block; animation:fadeIn 0.35s ease; }
  @keyframes fadeIn { from{opacity:0;transform:translateY(8px);} to{opacity:1;transform:translateY(0);} }
  .pcard::before { content:''; position:absolute; bottom:0; left:0; width:100%; height:2px; background:var(--gold); transform:scaleX(0); transition:transform 0.35s cubic-bezier(0.22,1,0.36,1); transform-origin:left; }
  .pcard:hover { background:var(--forest); }
  .pcard:hover::before { transform:scaleX(1); }
  .pcard:hover .pcard-title { color:var(--light-text); }
  .pcard:hover .pcard-body { color:rgba(248,245,238,0.5); }
  .pcard:hover .pcard-tag { background:rgba(196,152,48,0.25); color:var(--gold-pale); }
  .pcard-icon { font-size:1.7rem; margin-bottom:16px; display:block; }
  .pcard-title { font-family:'Cormorant Garamond',serif; font-size:1.3rem; font-weight:400; color:var(--forest); margin-bottom:8px; transition:color 0.3s; }
  .pcard-body { font-size:0.8rem; color:var(--muted); line-height:1.65; font-weight:300; transition:color 0.3s; margin-bottom:12px; }
  .pcard-tag { display:inline-block; padding:3px 10px; background:var(--cream); font-size:0.62rem; letter-spacing:0.1em; text-transform:uppercase; color:var(--sage); font-weight:600; transition:all 0.25s; }
  .products-empty { display:none; grid-column:1/-1; text-align:center; padding:80px 24px; color:var(--muted); font-family:'Cormorant Garamond',serif; font-size:1.3rem; font-style:italic; }

  /* ─── REVIEWS ─── */
  .reviews { background:var(--night); }
  .reviews .eyebrow { color:var(--gold); }
  .reviews .section-h { color:var(--light-text); }
  .reviews-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:2px; margin-top:52px; }
  .rcard { padding:34px 28px; background:rgba(255,255,255,0.04); border-top:1px solid rgba(196,152,48,0.18); transition:background 0.3s; }
  .rcard:hover { background:rgba(255,255,255,0.07); }
  .stars { color:var(--gold); font-size:0.78rem; letter-spacing:3px; margin-bottom:16px; }
  .rtext { font-family:'Cormorant Garamond',serif; font-size:1.02rem; font-weight:300; font-style:italic; line-height:1.65; color:rgba(248,245,238,0.82); margin-bottom:20px; }
  .rauthor { font-size:0.68rem; letter-spacing:0.2em; text-transform:uppercase; color:var(--gold); font-weight:600; }

  /* ─── HORARIO + CONTACTO ─── */
  .info { background:var(--cream); }
  .info-grid { display:grid; grid-template-columns:1fr 1fr; gap:80px; align-items:start; }
  .hours-table { width:100%; border-collapse:collapse; margin-top:28px; }
  .hours-table tr { border-bottom:1px solid rgba(0,0,0,0.06); }
  .hours-table td { padding:13px 0; font-size:0.86rem; font-weight:300; color:var(--muted); }
  .hours-table td:first-child { color:var(--forest); font-weight:600; }
  .hours-table td:last-child { text-align:right; }
  .closed-txt { color:var(--rose)!important; font-style:italic; }
  .today-row td { color:var(--forest)!important; }
  .today-row td:first-child::after { content:' ·'; color:var(--gold); }
  .contact-list { margin-top:28px; display:flex; flex-direction:column; gap:0; }
  .citem { display:flex; align-items:flex-start; gap:16px; padding:18px 0; border-bottom:1px solid rgba(0,0,0,0.06); }
  .citem:last-child { border-bottom:none; }
  .cicon { width:38px; height:38px; border-radius:50%; background:var(--forest); display:flex; align-items:center; justify-content:center; font-size:0.95rem; flex-shrink:0; margin-top:2px; }
  .clabel { font-size:0.65rem; letter-spacing:0.2em; text-transform:uppercase; color:var(--sage); font-weight:600; margin-bottom:4px; }
  .cval { font-size:0.9rem; color:var(--ink); font-weight:300; line-height:1.55; }
  .cval a { color:var(--forest); text-decoration:none; font-weight:500; }
  .cval a:hover { color:var(--gold); }

  /* ─── MAP ─── */
  .map-section { padding:0; }
  .map-section iframe { display:block; width:100%; height:380px; border:none; }

  /* ─── FOOTER ─── */
  footer { background:var(--night); padding:52px 24px; text-align:center; border-top:1px solid rgba(196,152,48,0.12); }
  .footer-brand { font-family:'Cormorant Garamond',serif; font-size:1.7rem; font-weight:300; color:var(--light-text); letter-spacing:0.08em; margin-bottom:6px; }
  .footer-sub { font-size:0.68rem; color:rgba(248,245,238,0.3); letter-spacing:0.2em; text-transform:uppercase; margin-bottom:36px; }
  .footer-nav { display:flex; justify-content:center; gap:36px; list-style:none; margin-bottom:36px; }
  .footer-nav a { color:rgba(248,245,238,0.35); text-decoration:none; font-size:0.68rem; letter-spacing:0.16em; text-transform:uppercase; transition:color 0.25s; }
  .footer-nav a:hover { color:var(--gold-pale); }
  .footer-sep { width:1px; height:32px; background:rgba(196,152,48,0.25); margin:0 auto 20px; }
  .footer-copy { font-size:0.68rem; color:rgba(248,245,238,0.2); }

  /* ─── REVEAL ─── */
  .reveal { opacity:0; transform:translateY(22px); transition:opacity 0.55s ease,transform 0.55s ease; }
  .reveal.in { opacity:1; transform:translateY(0); }

  /* ─── RESPONSIVE ─── */
  @media(max-width:900px) {
    .news-grid { grid-template-columns:repeat(2,1fr); }
    .about-grid,.info-grid,.reviews-grid { grid-template-columns:1fr; gap:44px; }
    .products-grid { grid-template-columns:1fr 1fr; }
  }
  @media(max-width:600px) {
    nav { padding:0 20px; }
    .nav-links { display:none; }
    .news-grid,.products-grid { grid-template-columns:1fr; }
    .video-section { height:50vh; }
    section { padding:72px 20px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <div class="nav-brand">Rosa <em>de India</em></div>
  <ul class="nav-links">
    <li><a href="#nosotros">Nosotros</a></li>
    <li><a href="#noticias">Noticias</a></li>
    <li><a href="#productos">Productos</a></li>
    <li><a href="#opiniones">Opiniones</a></li>
    <li><a href="#contacto">Horario</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-glow"></div>
  <svg class="hero-rose" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
    <circle cx="100" cy="96" r="72" stroke="rgba(196,152,48,0.12)" stroke-width="0.8" stroke-dasharray="2 8"/>
    <circle cx="100" cy="96" r="55" stroke="rgba(122,174,138,0.14)" stroke-width="0.8" stroke-dasharray="3 6"/>
    <path d="M100 192 C100 192 100 145 100 110" stroke="#5A9470" stroke-width="1.4" stroke-linecap="round"/>
    <path d="M100 170 Q88 162 84 154" stroke="#5A9470" stroke-width="0.9" fill="none" stroke-linecap="round"/>
    <path d="M100 155 Q112 147 116 139" stroke="#5A9470" stroke-width="0.9" fill="none" stroke-linecap="round"/>
    <path d="M100 148 Q72 136 64 118 Q79 124 95 142Z" fill="rgba(90,148,112,0.2)" stroke="#5A9470" stroke-width="1" stroke-linejoin="round"/>
    <path d="M100 148 Q72 136 64 118" stroke="#5A9470" stroke-width="0.7" stroke-dasharray="2 3" fill="none"/>
    <path d="M100 132 Q130 120 138 102 Q123 108 104 128Z" fill="rgba(90,148,112,0.2)" stroke="#5A9470" stroke-width="1" stroke-linejoin="round"/>
    <path d="M100 132 Q130 120 138 102" stroke="#5A9470" stroke-width="0.7" stroke-dasharray="2 3" fill="none"/>
    <path d="M100 110 Q92 104 88 96" stroke="#6DAB87" stroke-width="1.1" fill="none" stroke-linecap="round"/>
    <path d="M100 110 Q108 104 112 96" stroke="#6DAB87" stroke-width="1.1" fill="none" stroke-linecap="round"/>
    <path d="M100 102 Q82 88 78 68 Q94 80 100 102Z" fill="rgba(184,105,122,0.18)" stroke="#B8697A" stroke-width="1.1" stroke-linejoin="round"/>
    <path d="M100 102 Q118 88 122 68 Q106 80 100 102Z" fill="rgba(184,105,122,0.18)" stroke="#B8697A" stroke-width="1.1" stroke-linejoin="round"/>
    <path d="M100 102 Q78 96 64 80 Q80 85 100 102Z" fill="rgba(184,105,122,0.15)" stroke="#B8697A" stroke-width="1.1" stroke-linejoin="round"/>
    <path d="M100 102 Q122 96 136 80 Q120 85 100 102Z" fill="rgba(184,105,122,0.15)" stroke="#B8697A" stroke-width="1.1" stroke-linejoin="round"/>
    <path d="M100 102 Q86 118 84 132 Q96 112 100 102Z" fill="rgba(184,105,122,0.12)" stroke="#B8697A" stroke-width="1" stroke-linejoin="round"/>
    <path d="M100 102 Q114 118 116 132 Q104 112 100 102Z" fill="rgba(184,105,122,0.12)" stroke="#B8697A" stroke-width="1" stroke-linejoin="round"/>
    <path d="M100 96 Q88 82 86 66 Q97 78 100 96Z" fill="rgba(196,152,48,0.15)" stroke="#C49830" stroke-width="0.9" stroke-linejoin="round"/>
    <path d="M100 96 Q112 82 114 66 Q103 78 100 96Z" fill="rgba(196,152,48,0.15)" stroke="#C49830" stroke-width="0.9" stroke-linejoin="round"/>
    <path d="M100 96 Q84 94 76 106 Q90 96 100 96Z" fill="rgba(196,152,48,0.13)" stroke="#C49830" stroke-width="0.9" stroke-linejoin="round"/>
    <path d="M100 96 Q116 94 124 106 Q110 96 100 96Z" fill="rgba(196,152,48,0.13)" stroke="#C49830" stroke-width="0.9" stroke-linejoin="round"/>
    <circle cx="100" cy="88" r="11" fill="rgba(196,152,48,0.12)" stroke="#C49830" stroke-width="0.9"/>
    <circle cx="100" cy="88" r="6.5" fill="rgba(184,105,122,0.2)" stroke="#B8697A" stroke-width="0.8"/>
    <circle cx="100" cy="88" r="3" fill="rgba(196,152,48,0.4)"/>
    <circle cx="96" cy="84" r="1.2" fill="#C49830" opacity="0.7"/>
    <circle cx="104" cy="84" r="1.2" fill="#C49830" opacity="0.7"/>
    <circle cx="100" cy="82" r="1.2" fill="#C49830" opacity="0.7"/>
    <circle cx="68" cy="70" r="1.8" fill="#5A9470" opacity="0.4"/>
    <circle cx="132" cy="70" r="1.8" fill="#5A9470" opacity="0.4"/>
  </svg>
  <p class="hero-eyebrow">Herbolario Natural · Villanueva de la Cañada, Madrid</p>
  <h1>Rosa <em>de India</em></h1>
  <p class="hero-tagline">Donde la naturaleza cuida de ti</p>
  <a href="#productos" class="btn-outline">Descubre lo que ofrecemos</a>
  <div class="hero-arrow"><div class="arrow-stem"></div></div>
</section>

<!-- VIDEO SECTION -->
<div class="video-section" id="video-section">
  <!-- Placeholder animado mientras se genera/carga el vídeo -->
  <div class="video-placeholder" id="video-placeholder">
    <svg viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <circle cx="100" cy="88" r="72" stroke="rgba(122,174,138,0.35)" stroke-width="0.8" stroke-dasharray="2 8"/>
      <path d="M100 192 C100 192 100 145 100 110" stroke="#5A9470" stroke-width="2" stroke-linecap="round"/>
      <path d="M100 148 Q72 136 64 118 Q79 124 95 142Z" fill="rgba(90,148,112,0.3)" stroke="#5A9470" stroke-width="1.5"/>
      <path d="M100 132 Q130 120 138 102 Q123 108 104 128Z" fill="rgba(90,148,112,0.3)" stroke="#5A9470" stroke-width="1.5"/>
      <path d="M100 102 Q82 88 78 68 Q94 80 100 102Z" fill="rgba(184,105,122,0.3)" stroke="#B8697A" stroke-width="1.5"/>
      <path d="M100 102 Q118 88 122 68 Q106 80 100 102Z" fill="rgba(184,105,122,0.3)" stroke="#B8697A" stroke-width="1.5"/>
      <path d="M100 102 Q78 96 64 80 Q80 85 100 102Z" fill="rgba(184,105,122,0.25)" stroke="#B8697A" stroke-width="1.5"/>
      <path d="M100 102 Q122 96 136 80 Q120 85 100 102Z" fill="rgba(184,105,122,0.25)" stroke="#B8697A" stroke-width="1.5"/>
      <circle cx="100" cy="88" r="11" fill="rgba(196,152,48,0.2)" stroke="#C49830" stroke-width="1.2"/>
      <circle cx="100" cy="88" r="5" fill="rgba(196,152,48,0.5)"/>
    </svg>
  </div>
  <!-- El vídeo se activa en cuanto su src esté disponible -->
  <video id="nature-video" autoplay loop muted playsinline style="display:none">
    <source id="video-src" src="" type="video/mp4">
  </video>
  <div class="video-overlay"></div>
  <div class="video-label">Naturaleza · Bienestar · Salud</div>
</div>

<!-- PULL QUOTE -->
<div class="pull-quote">
  <blockquote>"El mejor herbolario de la zona. Su conocimiento hace de cada visita una experiencia muy enriquecedora."</blockquote>
  <cite>— Clienta habitual, Villanueva de la Cañada</cite>
</div>

</body>
</html>
