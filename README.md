<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vi Ordner Det — Havehjælp og praktiske opgaver i Silkeborg</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --skov: #17331F;
    --skov-2: #234631;
    --gran: #2F5B41;
    --loev: #8AC17A;
    --loev-lys: #CBE7B5;
    --sand: #F4EEDE;
    --sand-2: #ECE3CC;
    --hvid: #FFFFFF;
    --ink: #17331F;
    --ink-soft: #4D5F52;
    --radius-lg: 28px;
    --radius-md: 18px;
  }

  *{ box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{
    margin:0;
    background:var(--hvid);
    color:var(--ink);
    font-family:'Inter',sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.display{
    font-family:'Space Grotesk',sans-serif;
    font-weight:600;
    letter-spacing:-0.01em;
    margin:0;
    color:var(--skov);
  }
  p{ margin:0; line-height:1.65; color:var(--ink-soft); }
  a{ color:inherit; text-decoration:none; }
  img,svg{ display:block; max-width:100%; }
  button{ font-family:inherit; }
  ul{ margin:0; padding:0; list-style:none; }

  a:focus-visible, button:focus-visible, input:focus-visible, textarea:focus-visible{
    outline:3px solid var(--gran);
    outline-offset:2px;
    border-radius:6px;
  }

  .wrap{ max-width:1180px; margin:0 auto; padding:0 32px; }

  /* ---------- BUTTONS ---------- */
  .btn{
    display:inline-flex; align-items:center; justify-content:center; gap:8px;
    padding:15px 28px;
    border-radius:999px;
    font-weight:700;
    font-size:0.98rem;
    border:1.5px solid transparent;
    cursor:pointer;
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease, color .18s ease;
  }
  .btn-primary{
    background:var(--loev);
    color:var(--skov);
    box-shadow:0 12px 24px -12px rgba(23,51,31,0.45);
  }
  .btn-primary:hover{ transform:translateY(-2px); background:var(--loev-lys); }
  .btn-outline{
    background:transparent;
    border-color:rgba(255,255,255,0.55);
    color:var(--hvid);
  }
  .btn-outline:hover{ background:rgba(255,255,255,0.12); transform:translateY(-2px); }
  .btn-dark{
    background:var(--skov);
    color:var(--hvid);
  }
  .btn-dark:hover{ background:var(--skov-2); transform:translateY(-2px); }
  .btn-block{ width:100%; }

  /* ---------- NAV ---------- */
  header.nav{
    position:fixed; top:0; left:0; right:0; z-index:200;
    padding:22px 0;
    transition:background .3s ease, padding .3s ease, box-shadow .3s ease;
  }
  header.nav.solid{
    background:rgba(255,255,255,0.94);
    backdrop-filter:blur(10px);
    padding:14px 0;
    box-shadow:0 1px 0 rgba(23,51,31,0.08);
  }
  .nav-inner{ display:flex; align-items:center; justify-content:space-between; }
  .brand{ display:flex; align-items:center; gap:10px; }
  .brand .mark{
    width:38px; height:38px; border-radius:11px;
    background:var(--skov);
    display:flex; align-items:center; justify-content:center;
  }
  .brand .mark svg{ width:20px; height:20px; }
  .brand .name{
    font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:1.12rem;
    color:var(--skov);
  }
  header.nav:not(.solid) .brand .name{ color:var(--hvid); }
  header.nav:not(.solid) .brand .mark{ background:rgba(255,255,255,0.18); }

  nav.links{ display:flex; gap:32px; align-items:center; font-size:0.96rem; font-weight:500; }
  nav.links a{ color:var(--skov); position:relative; padding-bottom:3px; }
  header.nav:not(.solid) nav.links a{ color:var(--hvid); }
  nav.links a::after{
    content:""; position:absolute; left:0; right:0; bottom:-2px; height:2px;
    background:var(--loev); transform:scaleX(0); transform-origin:left;
    transition:transform .22s ease;
  }
  nav.links a:hover::after{ transform:scaleX(1); }

  .nav-cta{ display:flex; align-items:center; gap:14px; }
  .call-pill{
    display:inline-flex; align-items:center; gap:8px;
    font-weight:600; font-size:0.92rem;
    color:var(--hvid);
  }
  header.nav.solid .call-pill{ color:var(--skov); }
  .call-pill svg{ width:17px; height:17px; }

  .burger{
    display:none;
    width:44px; height:44px;
    border-radius:12px;
    border:1.5px solid rgba(23,51,31,0.2);
    background:var(--hvid);
    align-items:center; justify-content:center;
    cursor:pointer;
  }
  .burger span, .burger span::before, .burger span::after{
    content:""; display:block; width:20px; height:2px; background:var(--skov);
    position:relative; transition:transform .22s ease, opacity .22s ease;
  }
  .burger span::before{ position:absolute; top:-6px; }
  .burger span::after{ position:absolute; top:6px; }
  .burger.open span{ background:transparent; }
  .burger.open span::before{ transform:rotate(45deg); top:0; }
  .burger.open span::after{ transform:rotate(-45deg); top:0; }

  .mobile-menu{
    position:fixed; inset:0; z-index:190;
    background:var(--skov);
    display:flex; flex-direction:column;
    justify-content:center; align-items:flex-start;
    gap:6px; padding:0 40px;
    transform:translateY(-100%);
    transition:transform .35s ease;
  }
  .mobile-menu.open{ transform:translateY(0); }
  .mobile-menu a{
    font-family:'Space Grotesk',sans-serif; font-size:2rem; font-weight:600;
    color:var(--sand); padding:14px 0;
  }
  .mobile-menu .btn{ margin-top:20px; }

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    background:var(--skov);
    overflow:hidden;
    padding:0;
  }
  .hero-inner{
    display:grid; grid-template-columns:1fr 0.95fr;
    align-items:center;
    min-height:96vh;
    gap:20px;
  }
  .hero-copy{ padding:170px 0 90px; position:relative; z-index:2; }
  .hero-copy .kicker{
    display:inline-flex; align-items:center; gap:9px;
    color:var(--loev-lys); font-weight:600; font-size:0.95rem;
    margin-bottom:22px;
  }
  .hero-copy .kicker .dot{ width:8px; height:8px; border-radius:50%; background:var(--loev); }
  .hero h1{
    font-size:clamp(2.9rem, 5.2vw, 4.6rem);
    line-height:0.98;
    color:var(--hvid);
  }
  .hero .tagline{
    font-family:'Space Grotesk',sans-serif;
    font-weight:500; font-style:normal;
    color:var(--loev-lys);
    font-size:clamp(1.2rem, 1.8vw, 1.5rem);
    margin-top:20px;
  }
  .hero .lede{
    margin-top:20px;
    font-size:1.12rem;
    max-width:38ch;
    color:rgba(244,238,222,0.82);
  }
  .hero-ctas{ display:flex; gap:16px; margin-top:40px; flex-wrap:wrap; }

  .hero-visual{
    position:relative;
    height:100%;
    min-height:520px;
    display:flex; align-items:flex-end; justify-content:center;
  }
  .hero-visual svg{ width:100%; height:auto; }

  .leaf-float{
    position:absolute;
    animation:leafDrift 9s ease-in-out infinite;
    opacity:0.8;
  }
  @keyframes leafDrift{
    0%{ transform:translate(0,0) rotate(0deg); }
    50%{ transform:translate(-14px,18px) rotate(18deg); }
    100%{ transform:translate(0,0) rotate(0deg); }
  }

  /* ---------- SECTION SHELLS ---------- */
  section{ padding:112px 0; }
  .kicker-text{
    display:inline-block;
    color:var(--gran);
    font-weight:700;
    font-size:0.98rem;
    margin-bottom:12px;
  }
  .section-head{
    display:flex; justify-content:space-between; align-items:flex-end;
    gap:40px; margin-bottom:60px; flex-wrap:wrap;
  }
  .section-head h2{ font-size:clamp(2rem, 3.4vw, 2.7rem); max-width:16ch; }
  .section-head p{ max-width:36ch; font-size:1.02rem; }

  /* ---------- SERVICES ---------- */
  .services{ background:var(--sand); }
  .service-grid{
    display:grid; grid-template-columns:repeat(3,1fr); gap:22px;
  }
  .service-card{
    background:var(--hvid);
    border-radius:var(--radius-md);
    padding:32px 28px;
    transition:transform .22s ease, box-shadow .22s ease;
    box-shadow:0 14px 30px -22px rgba(23,51,31,0.35);
  }
  .service-card:hover{
    transform:translateY(-6px);
    box-shadow:0 22px 40px -20px rgba(23,51,31,0.4);
  }
  .service-card .icon{
    width:56px; height:56px; border-radius:16px;
    display:flex; align-items:center; justify-content:center;
    margin-bottom:22px;
  }
  .service-card .icon svg{ width:26px; height:26px; }
  .service-card h3{ font-size:1.2rem; margin-bottom:10px; }
  .service-card p{ font-size:0.94rem; }
  .service-card.wide{ grid-column:span 3; display:flex; align-items:center; justify-content:space-between; gap:24px; flex-wrap:wrap; padding:30px 34px; }
  .service-card.wide .icon{ margin-bottom:0; flex-shrink:0; }
  .service-card.wide .txt{ flex:1; min-width:220px; }
  .service-card.wide h3{ margin-bottom:6px; }

  /* icon bg tints */
  .tint-a{ background:var(--loev-lys); color:var(--skov); }
  .tint-b{ background:var(--sand-2); color:var(--gran); }
  .tint-c{ background:var(--skov); color:var(--loev-lys); }

  /* ---------- PRISER ---------- */
  .priser{ background:var(--hvid); }
  .price-grid{
    display:grid; grid-template-columns:0.85fr 1.15fr; gap:26px; align-items:stretch;
  }
  .price-hero{
    background:var(--skov);
    border-radius:var(--radius-lg);
    padding:44px 38px;
    color:var(--hvid);
    display:flex; flex-direction:column; justify-content:space-between;
    position:relative;
    overflow:hidden;
  }
  .price-hero::after{
    content:"";
    position:absolute; right:-40px; bottom:-40px;
    width:180px; height:180px; border-radius:50%;
    background:rgba(138,193,122,0.18);
  }
  .price-hero .label{ font-weight:600; color:var(--loev-lys); font-size:1.02rem; }
  .price-hero .amount{
    font-family:'Space Grotesk',sans-serif; font-weight:700;
    font-size:4rem; line-height:1; margin:18px 0 8px; position:relative; z-index:1;
  }
  .price-hero .unit{ color:rgba(244,238,222,0.75); font-size:0.98rem; }
  .price-hero .note{ margin-top:26px; font-size:0.92rem; color:rgba(244,238,222,0.7); position:relative; z-index:1; }

  .price-list{
    display:flex; flex-direction:column; gap:1px;
    background:var(--sand-2);
    border-radius:var(--radius-lg);
    overflow:hidden;
  }
  .price-row{
    background:var(--hvid);
    padding:26px 32px;
    display:flex; justify-content:space-between; align-items:center; gap:20px;
  }
  .price-row h4{ font-size:1.08rem; font-weight:600; color:var(--skov); margin-bottom:4px; font-family:'Space Grotesk',sans-serif; }
  .price-row p{ font-size:0.9rem; }
  .price-row .tag{
    font-size:0.86rem; font-weight:700; color:var(--gran);
    background:var(--loev-lys);
    padding:9px 16px; border-radius:999px;
    white-space:nowrap;
  }

  /* ---------- OM OS ---------- */
  .om{ background:var(--sand); }
  .om-grid{ display:grid; grid-template-columns:1fr 1fr; gap:70px; align-items:center; }
  .om h2{ font-size:clamp(2rem, 3.2vw, 2.6rem); max-width:14ch; margin-bottom:26px; }
  .om p{ font-size:1.05rem; margin-bottom:18px; max-width:52ch; }
  .om-stats{ display:flex; gap:40px; margin-top:34px; flex-wrap:wrap; }
  .om-stats div{ display:flex; flex-direction:column; gap:2px; }
  .om-stats .num{ font-family:'Space Grotesk',sans-serif; font-size:2rem; color:var(--skov); font-weight:700; }
  .om-stats .lab{ font-size:0.86rem; color:var(--ink-soft); }

  .om-visual{
    background:var(--hvid);
    border-radius:var(--radius-lg);
    padding:38px;
    position:relative;
  }
  .om-visual ul{ display:flex; flex-direction:column; gap:22px; }
  .om-visual li{ display:flex; gap:16px; align-items:flex-start; }
  .om-visual .check{
    width:32px; height:32px; border-radius:10px; flex-shrink:0;
    background:var(--loev-lys); display:flex; align-items:center; justify-content:center;
  }
  .om-visual .check svg{ width:16px; height:16px; color:var(--skov); }
  .om-visual strong{ display:block; color:var(--skov); font-family:'Space Grotesk',sans-serif; font-size:1.02rem; margin-bottom:3px; }
  .om-visual span{ font-size:0.92rem; color:var(--ink-soft); }

  /* ---------- FØR/EFTER ---------- */
  .foer-efter{ background:var(--hvid); }
  .fe-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:22px; }
  .fe-card{
    border-radius:var(--radius-md);
    overflow:hidden;
    border:1px solid var(--sand-2);
  }
  .fe-split{ display:grid; grid-template-columns:1fr 1fr; height:190px; }
  .fe-before, .fe-after{ position:relative; display:flex; align-items:center; justify-content:center; }
  .fe-before{ background:linear-gradient(160deg,#DCD6BF,#C9C2A4); }
  .fe-after{ background:linear-gradient(160deg,var(--loev),var(--gran)); }
  .fe-before svg, .fe-after svg{ width:56%; }
  .fe-label{
    position:absolute; top:12px; left:12px;
    font-size:0.75rem; font-weight:700; letter-spacing:0.02em;
    padding:5px 12px; border-radius:999px;
    background:rgba(255,255,255,0.85); color:var(--ink);
  }
  .fe-after .fe-label{ background:rgba(23,51,31,0.35); color:var(--hvid); }
  .fe-info{ padding:20px 22px; }
  .fe-info h4{ font-family:'Space Grotesk',sans-serif; color:var(--skov); font-size:1.05rem; margin-bottom:4px; }
  .fe-info p{ font-size:0.9rem; }

  /* ---------- OMRÅDE ---------- */
  .omraade{
    background:var(--skov);
    color:var(--sand);
    position:relative;
    overflow:hidden;
  }
  .omraade .section-head h2, .omraade .section-head p{ color:var(--hvid); }
  .omraade .section-head p{ color:rgba(244,238,222,0.72); }
  .omraade .kicker-text{ color:var(--loev-lys); }
  .map-wrap{ display:flex; justify-content:center; }
  .radar{
    position:relative;
    width:100%; max-width:620px;
    aspect-ratio:1/1;
  }
  .radar svg{ width:100%; height:100%; }
  .radar .town{
    font-family:'Space Grotesk',sans-serif; font-size:13px; font-weight:600; fill:var(--sand);
  }
  .radar .center-label{
    font-family:'Space Grotesk',sans-serif; font-size:16px; font-weight:700; fill:var(--skov);
  }

  /* ---------- KONTAKT ---------- */
  .kontakt{ background:var(--sand); }
  .kontakt-grid{ display:grid; grid-template-columns:1.15fr 0.85fr; gap:26px; align-items:stretch; }
  .form-card{
    background:var(--hvid);
    border-radius:var(--radius-lg);
    padding:44px;
  }
  .form-card h2{ font-size:clamp(1.9rem, 3vw, 2.4rem); margin-bottom:10px; }
  .form-card > p{ margin-bottom:32px; font-size:1.02rem; }
  .field{ margin-bottom:20px; }
  .field label{
    display:block; font-size:0.88rem; font-weight:600; color:var(--skov); margin-bottom:8px;
  }
  .field input, .field textarea{
    width:100%;
    border:1.5px solid var(--sand-2);
    background:var(--sand);
    border-radius:12px;
    padding:14px 16px;
    font-family:'Inter',sans-serif;
    font-size:0.98rem;
    color:var(--ink);
    transition:border-color .2s ease, background .2s ease;
  }
  .field input:focus, .field textarea:focus{
    border-color:var(--gran); background:var(--hvid); outline:none;
  }
  .field textarea{ resize:vertical; min-height:110px; }
  .field-row{ display:grid; grid-template-columns:1fr 1fr; gap:18px; }

  .contact-side{ display:flex; flex-direction:column; gap:20px; }
  .contact-panel{
    background:var(--skov);
    color:var(--hvid);
    border-radius:var(--radius-lg);
    padding:34px;
    flex:1;
    display:flex; flex-direction:column; justify-content:center;
    gap:20px;
  }
  .contact-line{
    display:flex; align-items:center; gap:16px;
    padding:16px 18px;
    background:rgba(255,255,255,0.06);
    border-radius:14px;
    transition:background .2s ease, transform .2s ease;
  }
  .contact-line:hover{ background:rgba(255,255,255,0.12); transform:translateX(3px); }
  .contact-line .ic{
    width:40px; height:40px; border-radius:11px;
    background:var(--loev); display:flex; align-items:center; justify-content:center; flex-shrink:0;
  }
  .contact-line .ic svg{ width:19px; height:19px; color:var(--skov); }
  .contact-line .txt strong{ display:block; font-family:'Space Grotesk',sans-serif; font-size:1.02rem; }
  .contact-line .txt span{ font-size:0.86rem; color:rgba(244,238,222,0.72); }

  .area-note{
    background:var(--hvid);
    border-radius:var(--radius-md);
    padding:26px 28px;
    display:flex; gap:16px; align-items:flex-start;
  }
  .area-note .ic{
    width:40px; height:40px; border-radius:11px; flex-shrink:0;
    background:var(--loev-lys); display:flex; align-items:center; justify-content:center;
  }
  .area-note .ic svg{ width:19px; height:19px; color:var(--skov); }
  .area-note strong{ display:block; color:var(--skov); font-family:'Space Grotesk',sans-serif; margin-bottom:3px; }
  .area-note span{ font-size:0.9rem; color:var(--ink-soft); }

  /* ---------- FOOTER ---------- */
  footer{ background:var(--skov); color:rgba(244,238,222,0.6); padding:56px 0 34px; }
  .footer-grid{
    display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:24px;
    padding-bottom:30px; border-bottom:1px solid rgba(244,238,222,0.14);
  }
  footer .brand .name{ color:var(--hvid); }
  .footer-links{ display:flex; gap:26px; font-size:0.9rem; }
  .footer-links a:hover{ color:var(--hvid); }
  .footer-bottom{ padding-top:22px; font-size:0.82rem; display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px; }

  /* ---------- STICKY MOBILE CALL ---------- */
  .mobile-call{
    display:none;
    position:fixed; bottom:18px; left:18px; right:18px; z-index:150;
    background:var(--skov);
    color:var(--hvid);
    border-radius:16px;
    padding:16px 20px;
    align-items:center; justify-content:center; gap:10px;
    font-weight:700;
    box-shadow:0 16px 32px -12px rgba(23,51,31,0.55);
  }
  .mobile-call svg{ width:19px; height:19px; }

  /* ---------- RESPONSIVE ---------- */
  @media (max-width: 1020px){
    .hero-inner{ grid-template-columns:1fr; min-height:auto; }
    .hero-copy{ padding:150px 0 40px; }
    .hero-visual{ min-height:340px; }
    .service-grid{ grid-template-columns:repeat(2,1fr); }
    .service-card.wide{ grid-column:span 2; }
    .price-grid, .om-grid, .kontakt-grid{ grid-template-columns:1fr; }
    .fe-grid{ grid-template-columns:1fr; }
    nav.links{ display:none; }
    .call-pill{ display:none; }
    .burger{ display:flex; }
  }
  @media (max-width: 640px){
    .wrap{ padding:0 20px; }
    section{ padding:80px 0; }
    .service-grid{ grid-template-columns:1fr; }
    .service-card.wide{ grid-column:span 1; flex-direction:column; align-items:flex-start; text-align:left; }
    .field-row{ grid-template-columns:1fr; }
    .form-card, .contact-panel, .price-hero{ padding:28px; }
    .mobile-call{ display:flex; }
    body{ padding-bottom:82px; }
    .om-visual{ padding:28px; }
  }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    .leaf-float{ animation:none !important; }
    *{ transition-duration:0.01ms !important; animation-duration:0.01ms !important; }
  }
</style>
</head>
<body>

<header class="nav" id="siteNav">
  <div class="wrap nav-inner">
    <a href="#top" class="brand">
      <span class="mark">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 21c-4-2-7-6-7-10a7 7 0 0 1 14 0c0 4-3 8-7 10Z"/><path d="M12 11v6"/></svg>
      </span>
      <span class="name">Vi Ordner Det</span>
    </a>
    <nav class="links">
      <a href="#services">Services</a>
      <a href="#priser">Priser</a>
      <a href="#om">Om os</a>
      <a href="#omraade">Område</a>
      <a href="#kontakt">Kontakt</a>
    </nav>
    <div class="nav-cta">
      <a class="call-pill" href="tel:+4561729513">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.13.96.36 1.9.68 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.91.32 1.85.55 2.81.68A2 2 0 0 1 22 16.92Z"/></svg>
        61 72 95 13
      </a>
      <a class="btn btn-primary" href="#kontakt">Få et tilbud</a>
      <button class="burger" id="burgerBtn" aria-label="Åbn menu"><span></span></button>
    </div>
  </div>
</header>

<div class="mobile-menu" id="mobileMenu">
  <a href="#services">Services</a>
  <a href="#priser">Priser</a>
  <a href="#om">Om os</a>
  <a href="#omraade">Område</a>
  <a href="#kontakt">Kontakt</a>
  <a class="btn btn-primary" href="#kontakt">Få et tilbud</a>
</div>

<section class="hero" id="top">
  <div class="wrap hero-inner">
    <div class="hero-copy">
      <div class="kicker"><span class="dot"></span>Silkeborg og omegn</div>
      <h1>VI ORDNER DET</h1>
      <div class="tagline">Du har opgaven. Vi ordner den.</div>
      <p class="lede">Lokal hjælp til haven og huset i Silkeborg og omegn — hurtigt, ordentligt og uden besvær.</p>
      <div class="hero-ctas">
        <a class="btn btn-primary" href="#kontakt">Få et tilbud</a>
        <a class="btn btn-outline" href="#services">Se vores services</a>
      </div>
    </div>

    <div class="hero-visual">
      <svg viewBox="0 0 520 560" fill="none" xmlns="http://www.w3.org/2000/svg">
        <ellipse cx="260" cy="520" rx="220" ry="24" fill="#0F2617"/>
        <circle cx="410" cy="90" r="46" fill="#8AC17A" opacity="0.5"/>
        <path d="M120 340 L120 200 L200 140 L280 200 L280 340 Z" fill="#2F5B41"/>
        <rect x="150" y="250" width="46" height="90" rx="4" fill="#17331F"/>
        <rect x="225" y="220" width="34" height="34" rx="3" fill="#CBE7B5"/>
        <path d="M112 200 L200 132 L288 200" stroke="#CBE7B5" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
        <ellipse cx="345" cy="470" rx="60" ry="16" fill="#0F2617" opacity="0.4"/>
        <path d="M300 470 Q300 430 345 430 Q390 430 390 470 Z" fill="#8AC17A"/>
        <circle cx="315" cy="440" r="10" fill="#CBE7B5"/>
        <circle cx="345" cy="425" r="13" fill="#CBE7B5"/>
        <circle cx="372" cy="442" r="9" fill="#CBE7B5"/>
        <g>
          <ellipse cx="150" cy="480" rx="34" ry="9" fill="#0F2617" opacity="0.35"/>
          <circle cx="150" cy="450" r="10" fill="#CBE7B5"/>
          <path d="M150 460 Q150 500 130 500" stroke="#CBE7B5" stroke-width="4" fill="none"/>
          <path d="M150 460 Q150 500 170 500" stroke="#CBE7B5" stroke-width="4" fill="none"/>
        </g>
        <g transform="translate(240,340)">
          <circle cx="0" cy="0" r="20" fill="#F4EEDE"/>
          <path d="M-16 22 L16 22 L20 90 L-20 90 Z" fill="#8AC17A"/>
          <path d="M-20 92 L20 92 L28 130 L-28 130 Z" fill="#2F5B41"/>
          <path d="M20 60 L52 40" stroke="#F4EEDE" stroke-width="7" stroke-linecap="round"/>
          <path d="M-18 65 L-46 82" stroke="#F4EEDE" stroke-width="7" stroke-linecap="round"/>
          <path d="M52 40 L54 6" stroke="#17331F" stroke-width="5" stroke-linecap="round"/>
          <path d="M40 8 L68 8" stroke="#17331F" stroke-width="6" stroke-linecap="round"/>
        </g>
        <g transform="translate(90,410)">
          <rect x="0" y="10" width="70" height="42" rx="6" fill="#F4EEDE"/>
          <circle cx="14" cy="58" r="9" fill="#17331F"/>
          <circle cx="56" cy="58" r="9" fill="#17331F"/>
          <path d="M0 20 L-18 8" stroke="#17331F" stroke-width="5" stroke-linecap="round"/>
        </g>
        <g class="leaf-float" style="transform-origin:80px 120px;">
          <path d="M60 100 Q80 80 100 100 Q80 120 60 100Z" fill="#CBE7B5" transform="translate(0,0)"/>
        </g>
        <g class="leaf-float" style="transform-origin:420px 220px; animation-delay:2s;">
          <path d="M400 220 Q420 200 440 220 Q420 240 400 220Z" fill="#8AC17A"/>
        </g>
        <g class="leaf-float" style="transform-origin:440px 340px; animation-delay:4s;">
          <path d="M420 340 Q440 320 460 340 Q440 360 420 340Z" fill="#CBE7B5"/>
        </g>
      </svg>
    </div>
  </div>
</section>

<section class="services" id="services">
  <div class="wrap">
    <div class="section-head">
      <div>
        <span class="kicker-text">Services</span>
        <h2>Praktisk hjælp til haven og huset</h2>
      </div>
      <p>Vælg en enkelt opgave, eller lad os tage flere ting i én omgang — vi tilpasser os det, du har brug for.</p>
    </div>

    <div class="service-grid">
      <div class="service-card">
        <div class="icon tint-a">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22c5-4 8-8 8-13a8 8 0 0 0-16 0c0 5 3 9 8 13Z"/><path d="M12 22V9"/></svg>
        </div>
        <h3>Lugning af ukrudt</h3>
        <p>Vi fjerner ukrudt fra bede, fliser og indkørsel, så haven fremstår ryddelig igen.</p>
      </div>

      <div class="service-card">
        <div class="icon tint-b">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2v6"/><path d="M6 22c0-6 3-10 6-14 3 4 6 8 6 14"/><path d="M6 22h12"/></svg>
        </div>
        <h3>Havearbejde</h3>
        <p>Klipning, beskæring og generel pleje af planter, hæk og bede gennem hele sæsonen.</p>
      </div>

      <div class="service-card">
        <div class="icon tint-c">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 7h16"/><path d="M6 7l1 13a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2l1-13"/><path d="M9 7V4a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v3"/></svg>
        </div>
        <h3>Rengøring af skraldespande</h3>
        <p>Vi vasker og lugtfrier skraldespandene, så de er rene til næste tømning.</p>
      </div>

      <div class="service-card">
        <div class="icon tint-b">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 20 20 4"/><path d="M14 4h6v6"/><path d="M4 14v6h6"/></svg>
        </div>
        <h3>Oprydning</h3>
        <p>Havaffald, grenaffald og andet skrammel bliver samlet sammen og kørt væk.</p>
      </div>

      <div class="service-card">
        <div class="icon tint-a">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M14.7 6.3a4 4 0 0 0-5.4 5.4L3 18l3 3 6.3-6.3a4 4 0 0 0 5.4-5.4l-2.3 2.3-3-3Z"/></svg>
        </div>
        <h3>Småopgaver om huset</h3>
        <p>Mindre praktiske opgaver, som er svære at nå — indenfor og udenfor.</p>
      </div>

      <div class="service-card">
        <div class="icon tint-c">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"/><path d="M12 8v4l3 2"/></svg>
        </div>
        <h3>Efter aftale</h3>
        <p>Har du en opgave, der ikke står på listen? Fortæl os om den, så finder vi en løsning.</p>
      </div>
    </div>
  </div>
</section>

<section class="priser" id="priser">
  <div class="wrap">
    <div class="section-head">
      <div>
        <span class="kicker-text">Priser</span>
        <h2>Tydelige priser, ingen overraskelser</h2>
      </div>
      <p>Én fast pris på skraldespande. Alt andet aftaler vi ud fra opgavens omfang.</p>
    </div>

    <div class="price-grid">
      <div class="price-hero">
        <div>
          <div class="label">Rengøring af skraldespand</div>
          <div class="amount">50 kr</div>
          <div class="unit">pr. skraldespand</div>
        </div>
        <div class="note">Book flere spande på samme adresse, og vi kommer forbi i én omgang.</div>
      </div>

      <div class="price-list">
        <div class="price-row">
          <div><h4>Havearbejde</h4><p>Klipning, beskæring, ukrudt og pleje.</p></div>
          <span class="tag">Pris efter aftale</span>
        </div>
        <div class="price-row">
          <div><h4>Vinduespudsning</h4><p>Indvendig og/eller udvendig, efter behov.</p></div>
          <span class="tag">Pris efter aftale</span>
        </div>
        <div class="price-row">
          <div><h4>Oprydning</h4><p>Havaffald, grenaffald og oprydning på grunden.</p></div>
          <span class="tag">Pris efter aftale</span>
        </div>
        <div class="price-row">
          <div><h4>Andre opgaver</h4><p>Fortæl os om opgaven, så sender vi et tilbud.</p></div>
          <span class="tag">Kontakt os</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="om" id="om">
  <div class="wrap om-grid">
    <div>
      <span class="kicker-text">Om os</span>
      <h2>Vi tager os af det, du ikke selv gider.</h2>
      <p>Vi Ordner Det er startet af lokale kræfter i Silkeborg, der kunne se, at mange praktiske opgaver i haven og om huset ofte bliver skubbet foran sig. Det ordner vi for dig.</p>
      <p>Vi lægger vægt på god service, fair priser og ordentligt udført arbejde hver gang — uanset om det er en enkelt skraldespand eller en hel havesæson.</p>
      <div class="om-stats">
        <div><span class="num">100%</span><span class="lab">lokalt drevet</span></div>
        <div><span class="num">Fast</span><span class="lab">pris på skrald</span></div>
        <div><span class="num">Hurtig</span><span class="lab">respons på henvendelser</span></div>
      </div>
    </div>

    <div class="om-visual">
      <ul>
        <li>
          <span class="check"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg></span>
          <div><strong>Ung og energisk</strong><span>Vi går til opgaverne med samme gejst hver gang.</span></div>
        </li>
        <li>
          <span class="check"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg></span>
          <div><strong>Seriøs i det små og det store</strong><span>Samme kvalitet, uanset opgavens størrelse.</span></div>
        </li>
        <li>
          <span class="check"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg></span>
          <div><strong>Nem at få fat på</strong><span>Ring, skriv eller send en forespørgsel — vi svarer hurtigt.</span></div>
        </li>
      </ul>
    </div>
  </div>
</section>

<section class="foer-efter" id="foer-efter">
  <div class="wrap">
    <div class="section-head">
      <div>
        <span class="kicker-text">Resultatet</span>
        <h2>Det gør vi ved opgaven</h2>
      </div>
      <p>Fra fyldt og rodet til rent og ryddeligt — det er den forskel, vi leverer.</p>
    </div>

    <div class="fe-grid">
      <div class="fe-card">
        <div class="fe-split">
          <div class="fe-before">
            <span class="fe-label">Før</span>
            <svg viewBox="0 0 100 100"><rect x="30" y="30" width="40" height="55" rx="4" fill="#8A836B"/><circle cx="20" cy="40" r="4" fill="#5A5540"/><circle cx="78" cy="55" r="5" fill="#5A5540"/><circle cx="15" cy="70" r="3" fill="#5A5540"/><path d="M30 40 L20 25" stroke="#5A5540" stroke-width="3"/><path d="M70 45 L82 30" stroke="#5A5540" stroke-width="3"/></svg>
          </div>
          <div class="fe-after">
            <span class="fe-label">Efter</span>
            <svg viewBox="0 0 100 100"><rect x="30" y="30" width="40" height="55" rx="4" fill="#F4EEDE"/><rect x="36" y="38" width="28" height="4" rx="2" fill="#17331F" opacity="0.3"/></svg>
          </div>
        </div>
        <div class="fe-info"><h4>Skraldespande</h4><p>Vasket rene og lugtfri, klar til næste tømning.</p></div>
      </div>

      <div class="fe-card">
        <div class="fe-split">
          <div class="fe-before">
            <span class="fe-label">Før</span>
            <svg viewBox="0 0 100 100"><path d="M20 80 Q30 60 20 50 Q30 45 25 30" stroke="#5A5540" stroke-width="3" fill="none"/><path d="M45 85 Q55 65 45 45 Q55 40 50 25" stroke="#5A5540" stroke-width="3" fill="none"/><path d="M70 80 Q80 60 70 50 Q80 45 75 30" stroke="#5A5540" stroke-width="3" fill="none"/></svg>
          </div>
          <div class="fe-after">
            <span class="fe-label">Efter</span>
            <svg viewBox="0 0 100 100"><rect x="15" y="70" width="70" height="10" rx="5" fill="#F4EEDE" opacity="0.8"/><circle cx="35" cy="55" r="10" fill="#F4EEDE"/><circle cx="60" cy="50" r="13" fill="#F4EEDE"/></svg>
          </div>
        </div>
        <div class="fe-info"><h4>Ukrudt og bede</h4><p>Ryddet for ukrudt, så beplantningen kommer til sin ret.</p></div>
      </div>

      <div class="fe-card">
        <div class="fe-split">
          <div class="fe-before">
            <span class="fe-label">Før</span>
            <svg viewBox="0 0 100 100"><rect x="20" y="20" width="60" height="60" rx="3" fill="none" stroke="#5A5540" stroke-width="3"/><line x1="20" y1="40" x2="80" y2="40" stroke="#5A5540" stroke-width="2"/><line x1="20" y1="60" x2="80" y2="60" stroke="#5A5540" stroke-width="2"/><line x1="40" y1="20" x2="40" y2="80" stroke="#5A5540" stroke-width="2"/><line x1="60" y1="20" x2="60" y2="80" stroke="#5A5540" stroke-width="2"/></svg>
          </div>
          <div class="fe-after">
            <span class="fe-label">Efter</span>
            <svg viewBox="0 0 100 100"><rect x="20" y="20" width="60" height="60" rx="3" fill="#F4EEDE" opacity="0.15" stroke="#F4EEDE" stroke-width="3"/><path d="M30 30 L45 45" stroke="#F4EEDE" stroke-width="4" stroke-linecap="round"/></svg>
          </div>
        </div>
        <div class="fe-info"><h4>Vinduer</h4><p>Klare og pletfrie ruder, indefra og ude.</p></div>
      </div>
    </div>
  </div>
</section>

<section class="omraade" id="omraade">
  <div class="wrap">
    <div class="section-head">
      <div>
        <span class="kicker-text">Vores område</span>
        <h2>Vi arbejder i Silkeborg og omegn</h2>
      </div>
      <p>Er du i tvivl om, hvorvidt vi dækker dit område? Skriv til os — vi kommer som regel gerne lidt uden for kortet også.</p>
    </div>

    <div class="map-wrap">
      <div class="radar">
        <svg viewBox="0 0 400 400">
          <circle cx="200" cy="200" r="170" fill="none" stroke="rgba(244,238,222,0.14)" stroke-dasharray="4 6"/>
          <circle cx="200" cy="200" r="115" fill="none" stroke="rgba(244,238,222,0.16)" stroke-dasharray="4 6"/>
          <circle cx="200" cy="200" r="60" fill="none" stroke="rgba(244,238,222,0.2)"/>
          <circle cx="200" cy="200" r="34" fill="#8AC17A"/>
          <text x="200" y="205" text-anchor="middle" class="center-label">Silkeborg</text>

          <circle cx="120" cy="110" r="7" fill="#F4EEDE"/>
          <text x="120" y="95" text-anchor="middle" class="town">Kjellerup</text>

          <circle cx="300" cy="120" r="7" fill="#F4EEDE"/>
          <text x="300" y="105" text-anchor="middle" class="town">Gjern</text>

          <circle cx="90" cy="270" r="7" fill="#F4EEDE"/>
          <text x="90" y="292" text-anchor="middle" class="town">Them</text>

          <circle cx="310" cy="280" r="7" fill="#F4EEDE"/>
          <text x="310" y="302" text-anchor="middle" class="town">Bryrup</text>

          <circle cx="255" cy="330" r="7" fill="#F4EEDE"/>
          <text x="255" y="352" text-anchor="middle" class="town">Sejs-Svejbæk</text>
        </svg>
      </div>
    </div>
  </div>
</section>

<section class="kontakt" id="kontakt">
  <div class="wrap kontakt-grid">
    <div class="form-card">
      <h2>Skal vi ordne det?</h2>
      <p>Udfyld formularen, så vender vi tilbage med et svar eller et tilbud hurtigst muligt.</p>

      <form id="contactForm">
        <div class="field-row">
          <div class="field">
            <label for="navn">Navn</label>
            <input type="text" id="navn" name="navn" placeholder="Dit navn" required>
          </div>
          <div class="field">
            <label for="telefon">Telefonnummer</label>
            <input type="tel" id="telefon" name="telefon" placeholder="Dit telefonnummer" required>
          </div>
        </div>
        <div class="field">
          <label for="email">E-mail</label>
          <input type="email" id="email" name="email" placeholder="din@email.dk" required>
        </div>
        <div class="field">
          <label for="opgave">Hvad skal vi hjælpe med?</label>
          <textarea id="opgave" name="opgave" placeholder="Beskriv opgaven kort" required></textarea>
        </div>
        <div class="field">
          <label for="adresse">Adresse eller område (valgfrit)</label>
          <input type="text" id="adresse" name="adresse" placeholder="F.eks. Silkeborg, Them, Kjellerup...">
        </div>
        <button type="submit" class="btn btn-dark btn-block">Send forespørgsel</button>
      </form>
    </div>

    <div class="contact-side">
      <div class="contact-panel">
        <a class="contact-line" href="tel:+4561729513">
          <span class="ic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.13.96.36 1.9.68 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.91.32 1.85.55 2.81.68A2 2 0 0 1 22 16.92Z"/></svg></span>
          <span class="txt"><strong>Ring til os</strong><span>61 72 95 13</span></span>
        </a>
        <a class="contact-line" href="mailto:Jakobfonnesbech@gmail.com">
          <span class="ic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16v16H4Z"/><path d="m4 6 8 7 8-7"/></svg></span>
          <span class="txt"><strong>Skriv til os</strong><span>Jakobfonnesbech@gmail.com</span></span>
        </a>
        <a class="contact-line" href="#omraade">
          <span class="ic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22c5-4 8-8 8-13a8 8 0 0 0-16 0c0 5 3 9 8 13Z"/><circle cx="12" cy="9" r="2.5"/></svg></span>
          <span class="txt"><strong>Kontaktperson</strong><span>Jakob Fonnesbæk</span></span>
        </a>
      </div>

      <div class="area-note">
        <span class="ic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"/><path d="M12 8v4l3 2"/></svg></span>
        <div><strong>Hurtig respons</strong><span>Vi vender som regel tilbage samme dag eller dagen efter.</span></div>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="footer-grid">
      <a href="#top" class="brand">
        <span class="mark">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 21c-4-2-7-6-7-10a7 7 0 0 1 14 0c0 4-3 8-7 10Z"/><path d="M12 11v6"/></svg>
        </span>
        <span class="name">Vi Ordner Det</span>
      </a>
      <div class="footer-links">
        <a href="#services">Services</a>
        <a href="#priser">Priser</a>
        <a href="#om">Om os</a>
        <a href="#kontakt">Kontakt</a>
      </div>
    </div>
    <div class="footer-bottom">
      <span>Silkeborg og omegn</span>
      <span>61 72 95 13 · Jakobfonnesbech@gmail.com</span>
    </div>
  </div>
</footer>

<a href="tel:+4561729513" class="mobile-call">
  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.13.96.36 1.9.68 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.91.32 1.85.55 2.81.68A2 2 0 0 1 22 16.92Z"/></svg>
  Ring nu — 61 72 95 13
</a>

<script>
  const nav = document.getElementById('siteNav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('solid', window.scrollY > 30);
  });

  const burger = document.getElementById('burgerBtn');
  const mobileMenu = document.getElementById('mobileMenu');
  burger.addEventListener('click', () => {
    burger.classList.toggle('open');
    mobileMenu.classList.toggle('open');
  });
  mobileMenu.querySelectorAll('a').forEach(a => {
    a.addEventListener('click', () => {
      burger.classList.remove('open');
      mobileMenu.classList.remove('open');
    });
  });

  const form = document.getElementById('contactForm');
  form.addEventListener('submit', (e) => {
    e.preventDefault();
    const navn = document.getElementById('navn').value;
    const telefon = document.getElementById('telefon').value;
    const email = document.getElementById('email').value;
    const opgave = document.getElementById('opgave').value;
    const adresse = document.getElementById('adresse').value;

    const subject = encodeURIComponent('Forespørgsel fra ' + navn);
    const body = encodeURIComponent(
      'Navn: ' + navn + '\n' +
      'Telefon: ' + telefon + '\n' +
      'E-mail: ' + email + '\n' +
      'Adresse/område: ' + (adresse || 'Ikke angivet') + '\n\n' +
      'Opgave:\n' + opgave
    );
    window.location.href = 'mailto:Jakobfonnesbech@gmail.com?subject=' + subject + '&body=' + body;
  });
</script>

</body>
</html>
