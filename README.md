<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RM. Sriwedari – Masakan Indonesia & Chinese Halal Surabaya</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #E8C96A;
    --gold-dim: #8B6E30;
    --cream: #FDF6E8;
    --deep: #1A0F00;
    --brown: #3D2200;
    --brown-mid: #6B3D0A;
    --white: #FFFFFF;
    --text-muted: #8C7355;
    --green-halal: #2D7A3A;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--deep);
    color: var(--cream);
    overflow-x: hidden;
  }

  /* ── WATERMARK ── */
  .watermark-bar {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 9999;
    background: linear-gradient(90deg, #111 0%, #1e1200 50%, #111 100%);
    border-bottom: 1px solid var(--gold-dim);
    padding: 7px 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    font-size: 12px;
    letter-spacing: 0.12em;
    color: var(--gold-light);
    font-family: 'DM Sans', sans-serif;
    font-weight: 500;
  }
  .watermark-bar span.dot { color: var(--gold); font-size: 16px; line-height: 1; }
  .watermark-bar strong { color: var(--white); letter-spacing: 0.18em; }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 32px; left: 0; right: 0;
    z-index: 999;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 48px;
    background: rgba(26, 15, 0, 0.88);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(201,168,76,0.15);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--gold);
    letter-spacing: 0.04em;
  }
  .nav-logo span { color: var(--cream); }
  .nav-links { display: flex; gap: 32px; }
  .nav-links a {
    color: var(--cream);
    text-decoration: none;
    font-size: 13px;
    letter-spacing: 0.1em;
    opacity: 0.75;
    transition: opacity 0.2s, color 0.2s;
    text-transform: uppercase;
  }
  .nav-links a:hover { opacity: 1; color: var(--gold-light); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    padding-top: 100px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    overflow: hidden;
    background:
      radial-gradient(ellipse 80% 60% at 50% 30%, rgba(201,168,76,0.10) 0%, transparent 70%),
      linear-gradient(180deg, #1A0F00 0%, #0D0700 100%);
  }

  /* decorative batik-inspired rings */
  .hero::before {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 700px; height: 700px;
    border-radius: 50%;
    border: 1px solid rgba(201,168,76,0.08);
    animation: pulse-ring 4s ease-in-out infinite;
  }
  .hero::after {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 500px; height: 500px;
    border-radius: 50%;
    border: 1px solid rgba(201,168,76,0.12);
    animation: pulse-ring 4s ease-in-out infinite 1s;
  }
  @keyframes pulse-ring {
    0%, 100% { opacity: 0.4; transform: translate(-50%, -50%) scale(1); }
    50% { opacity: 0.9; transform: translate(-50%, -50%) scale(1.03); }
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(201,168,76,0.12);
    border: 1px solid rgba(201,168,76,0.3);
    border-radius: 100px;
    padding: 7px 18px;
    font-size: 11.5px;
    letter-spacing: 0.18em;
    color: var(--gold-light);
    text-transform: uppercase;
    margin-bottom: 28px;
    position: relative; z-index: 2;
    animation: fadeUp 0.8s ease both;
  }
  .halal-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--green-halal);
    box-shadow: 0 0 6px rgba(45,122,58,0.8);
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(52px, 8vw, 96px);
    font-weight: 900;
    line-height: 0.95;
    color: var(--cream);
    position: relative; z-index: 2;
    animation: fadeUp 0.8s ease 0.1s both;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--gold);
    display: block;
  }

  .hero-tagline {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: clamp(16px, 2vw, 22px);
    color: var(--gold-light);
    margin: 22px 0 12px;
    position: relative; z-index: 2;
    animation: fadeUp 0.8s ease 0.2s both;
  }
  .hero-sub {
    font-size: 15px;
    color: var(--text-muted);
    max-width: 460px;
    line-height: 1.7;
    position: relative; z-index: 2;
    animation: fadeUp 0.8s ease 0.3s both;
  }

  .hero-cta {
    display: flex;
    gap: 14px;
    margin-top: 36px;
    flex-wrap: wrap;
    justify-content: center;
    position: relative; z-index: 2;
    animation: fadeUp 0.8s ease 0.4s both;
  }

  .btn-primary {
    padding: 15px 34px;
    background: linear-gradient(135deg, var(--gold) 0%, var(--gold-dim) 100%);
    color: var(--deep);
    border: none;
    border-radius: 4px;
    font-size: 14px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 24px rgba(201,168,76,0.3);
  }
  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(201,168,76,0.45);
  }

  .btn-outline {
    padding: 15px 34px;
    background: transparent;
    color: var(--gold);
    border: 1px solid rgba(201,168,76,0.4);
    border-radius: 4px;
    font-size: 14px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    transition: background 0.2s, border-color 0.2s;
    position: relative;
  }
  .btn-outline .dummy-tag {
    position: absolute;
    top: -10px; right: -10px;
    background: var(--brown-mid);
    color: var(--gold-light);
    font-size: 9px;
    padding: 2px 6px;
    border-radius: 4px;
    letter-spacing: 0.1em;
    border: 1px solid var(--gold-dim);
  }
  .btn-outline:hover {
    background: rgba(201,168,76,0.06);
    border-color: var(--gold);
  }

  .hero-info-strip {
    display: flex;
    gap: 32px;
    margin-top: 52px;
    position: relative; z-index: 2;
    flex-wrap: wrap;
    justify-content: center;
    animation: fadeUp 0.8s ease 0.5s both;
  }
  .info-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 13px;
    color: var(--text-muted);
  }
  .info-item .icon { font-size: 16px; }
  .info-item strong { color: var(--cream); font-weight: 500; }

  /* ornament divider */
  .ornament {
    display: flex;
    align-items: center;
    gap: 16px;
    justify-content: center;
    padding: 60px 0 20px;
    opacity: 0.5;
  }
  .ornament::before, .ornament::after {
    content: '';
    width: 80px; height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold));
  }
  .ornament::after { background: linear-gradient(90deg, var(--gold), transparent); }
  .ornament span { color: var(--gold); font-size: 18px; }

  /* ── SECTION BASE ── */
  section { padding: 80px 48px; max-width: 1200px; margin: 0 auto; }

  .section-label {
    font-size: 11px;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 12px;
    display: block;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(32px, 4vw, 52px);
    font-weight: 700;
    line-height: 1.1;
    color: var(--cream);
    margin-bottom: 16px;
  }
  .section-title em { font-style: italic; color: var(--gold); }
  .section-desc {
    font-size: 15px;
    color: var(--text-muted);
    max-width: 520px;
    line-height: 1.75;
  }

  /* ── MENU SECTION ── */
  #menu {
    background: linear-gradient(180deg, #0D0700 0%, #130B00 100%);
    padding: 80px 0;
  }
  #menu > .section-inner { max-width: 1200px; margin: 0 auto; padding: 0 48px; }

  .menu-tabs {
    display: flex;
    gap: 4px;
    margin: 40px 0 48px;
    background: rgba(255,255,255,0.04);
    border-radius: 8px;
    padding: 5px;
    width: fit-content;
  }
  .tab-btn {
    padding: 10px 24px;
    background: transparent;
    border: none;
    border-radius: 6px;
    color: var(--text-muted);
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.06em;
    cursor: pointer;
    transition: all 0.2s;
    font-family: 'DM Sans', sans-serif;
  }
  .tab-btn.active {
    background: linear-gradient(135deg, var(--gold) 0%, var(--gold-dim) 100%);
    color: var(--deep);
    font-weight: 600;
  }

  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 20px;
  }

  .menu-card {
    background: linear-gradient(145deg, rgba(255,255,255,0.04) 0%, rgba(201,168,76,0.03) 100%);
    border: 1px solid rgba(201,168,76,0.12);
    border-radius: 12px;
    padding: 24px;
    transition: transform 0.25s, border-color 0.25s, box-shadow 0.25s;
    position: relative;
    overflow: hidden;
  }
  .menu-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    opacity: 0;
    transition: opacity 0.25s;
  }
  .menu-card:hover {
    transform: translateY(-4px);
    border-color: rgba(201,168,76,0.3);
    box-shadow: 0 12px 32px rgba(0,0,0,0.4);
  }
  .menu-card:hover::before { opacity: 1; }

  .menu-emoji { font-size: 36px; margin-bottom: 14px; display: block; }
  .menu-name {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    font-weight: 700;
    color: var(--cream);
    margin-bottom: 6px;
  }
  .menu-desc {
    font-size: 13px;
    color: var(--text-muted);
    line-height: 1.6;
    margin-bottom: 16px;
  }
  .menu-price {
    font-size: 18px;
    font-weight: 600;
    color: var(--gold);
  }
  .menu-price span { font-size: 12px; color: var(--text-muted); font-weight: 400; }

  .menu-badge {
    display: inline-block;
    background: rgba(45,122,58,0.2);
    border: 1px solid rgba(45,122,58,0.4);
    color: #5CBF6A;
    font-size: 10px;
    letter-spacing: 0.14em;
    padding: 3px 9px;
    border-radius: 100px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .menu-locked {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 40px;
    padding: 16px 22px;
    background: rgba(201,168,76,0.06);
    border: 1px dashed rgba(201,168,76,0.25);
    border-radius: 10px;
    color: var(--text-muted);
    font-size: 13px;
  }
  .menu-locked .lock-icon { font-size: 20px; }
  .menu-locked strong { color: var(--gold-light); display: block; font-size: 14px; margin-bottom: 2px; }

  .signature-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
  .signature-card {
    background: linear-gradient(145deg, rgba(201,168,76,0.06), rgba(201,168,76,0.02));
    border: 1px solid rgba(201,168,76,0.2);
    border-radius: 14px;
    padding: 30px 24px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .signature-card .crown { font-size: 40px; margin-bottom: 14px; display: block; }
  .signature-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    color: var(--gold-light);
    margin-bottom: 8px;
  }
  .signature-card p { font-size: 13px; color: var(--text-muted); line-height: 1.6; }
  .custom-tag {
    display: inline-block;
    background: rgba(201,168,76,0.15);
    border: 1px solid rgba(201,168,76,0.3);
    color: var(--gold);
    font-size: 10px;
    padding: 4px 10px;
    border-radius: 100px;
    letter-spacing: 0.12em;
    margin-top: 12px;
    text-transform: uppercase;
  }

  /* ── ABOUT ── */
  #about { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
  .about-visual {
    position: relative;
    aspect-ratio: 4/5;
    background: linear-gradient(145deg, rgba(201,168,76,0.08), rgba(201,168,76,0.02));
    border-radius: 16px;
    border: 1px solid rgba(201,168,76,0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
  .about-visual-inner {
    font-size: 100px;
    animation: float 3s ease-in-out infinite;
  }
  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-12px); }
  }
  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 36px;
  }
  .stat-box {
    background: rgba(201,168,76,0.06);
    border: 1px solid rgba(201,168,76,0.14);
    border-radius: 10px;
    padding: 18px 20px;
  }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    font-weight: 700;
    color: var(--gold);
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-label { font-size: 12px; color: var(--text-muted); letter-spacing: 0.06em; }

  /* ── TESTIMONI ── */
  #testimoni {
    background: #0D0700;
    padding: 80px 0;
  }
  #testimoni > .section-inner { max-width: 1200px; margin: 0 auto; padding: 0 48px; }

  .testi-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 48px; }
  .testi-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(201,168,76,0.1);
    border-radius: 14px;
    padding: 28px;
    position: relative;
  }
  .testi-card .quote-mark {
    font-family: 'Playfair Display', serif;
    font-size: 60px;
    color: var(--gold);
    opacity: 0.2;
    line-height: 0.5;
    display: block;
    margin-bottom: 16px;
  }
  .testi-text { font-size: 15px; color: var(--cream); line-height: 1.75; margin-bottom: 20px; font-style: italic; }
  .testi-author { display: flex; align-items: center; gap: 12px; }
  .testi-avatar {
    width: 40px; height: 40px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--gold-dim), var(--brown-mid));
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
  }
  .testi-name { font-weight: 600; font-size: 14px; color: var(--cream); }
  .testi-stars { color: var(--gold); font-size: 13px; margin-top: 2px; }

  .testi-gmaps {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 36px;
    padding: 14px 22px;
    background: rgba(201,168,76,0.06);
    border: 1px dashed rgba(201,168,76,0.25);
    border-radius: 10px;
    color: var(--text-muted);
    font-size: 13px;
    width: fit-content;
  }
  .testi-gmaps strong { color: var(--gold-light); }
  .testi-gmaps .lock-icon { font-size: 18px; }

  /* ── LOKASI ── */
  #lokasi {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: start;
  }
  .lokasi-info h3 {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    color: var(--cream);
    margin-bottom: 20px;
  }
  .lokasi-detail { display: flex; flex-direction: column; gap: 14px; }
  .lokasi-row {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    font-size: 14px;
    color: var(--text-muted);
    line-height: 1.6;
  }
  .lokasi-row .icon { font-size: 18px; flex-shrink: 0; margin-top: 2px; }
  .lokasi-row strong { color: var(--cream); display: block; margin-bottom: 2px; }
  .map-container {
    border-radius: 16px;
    overflow: hidden;
    border: 1px solid rgba(201,168,76,0.18);
    aspect-ratio: 4/3;
  }
  .map-container iframe { width: 100%; height: 100%; border: none; display: block; }

  /* ── CTA ── */
  .cta-section {
    background: linear-gradient(135deg, rgba(201,168,76,0.08) 0%, rgba(61,34,0,0.4) 50%, rgba(201,168,76,0.04) 100%);
    border: 1px solid rgba(201,168,76,0.15);
    border-radius: 24px;
    padding: 72px 48px;
    text-align: center;
    margin: 0 48px 80px;
    position: relative;
    overflow: hidden;
  }
  .cta-section::before {
    content: '✦';
    position: absolute;
    font-size: 200px;
    color: var(--gold);
    opacity: 0.03;
    top: -30px; right: -20px;
  }
  .cta-section h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(28px, 4vw, 48px);
    color: var(--cream);
    line-height: 1.2;
    margin-bottom: 14px;
  }
  .cta-section h2 em { font-style: italic; color: var(--gold); }
  .cta-section p { font-size: 15px; color: var(--text-muted); margin-bottom: 36px; }
  .cta-btns { display: flex; gap: 14px; justify-content: center; flex-wrap: wrap; }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid rgba(201,168,76,0.1);
    padding: 40px 48px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 16px;
  }
  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    color: var(--gold);
  }
  .footer-logo span { color: var(--text-muted); font-size: 12px; display: block; font-family: 'DM Sans', sans-serif; margin-top: 2px; letter-spacing: 0.1em; }
  .footer-copy { font-size: 12px; color: var(--text-muted); text-align: center; }
  .footer-wm {
    font-size: 12px;
    color: var(--gold-dim);
    letter-spacing: 0.1em;
    text-align: right;
  }
  .footer-wm strong { color: var(--gold); }

  /* ── SECTION DIVIDER ── */
  .section-divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent 0%, rgba(201,168,76,0.15) 30%, rgba(201,168,76,0.15) 70%, transparent 100%);
    margin: 0;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    nav { padding: 12px 20px; }
    .nav-links { display: none; }
    section { padding: 60px 20px; }
    #about { grid-template-columns: 1fr; gap: 40px; }
    .about-visual { aspect-ratio: 16/7; }
    #lokasi { grid-template-columns: 1fr; }
    .testi-grid { grid-template-columns: 1fr; }
    .signature-grid { grid-template-columns: 1fr; }
    .cta-section { padding: 48px 24px; margin: 0 20px 60px; }
    footer { padding: 32px 20px; flex-direction: column; text-align: center; }
    .footer-wm { text-align: center; }
    #about .section-inner { padding: 0 20px; }
    #menu > .section-inner { padding: 0 20px; }
    #testimoni > .section-inner { padding: 0 20px; }
    #lokasi { padding: 60px 20px; }
  }
</style>
</head>
<body>

<!-- WATERMARK -->
<div class="watermark-bar">
  <span class="dot">✦</span>
  PREVIEW BY <strong>AUTOCUAN DIGITAL</strong>
  <span class="dot">✦</span>
  Demo Only – Belum Aktif
  <span class="dot">✦</span>
</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">RM. <span>Sriwedari</span></div>
  <div class="nav-links">
    <a href="#menu">Menu</a>
    <a href="#about">Tentang</a>
    <a href="#testimoni">Testimoni</a>
    <a href="#lokasi">Lokasi</a>
    <a href="#cta">Pesan</a>
  </div>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-badge">
    <span class="halal-dot"></span>
    Indonesia &amp; Chinese · Halal · Surabaya
  </div>
  <h1>RM.<em>Sriwedari</em></h1>
  <p class="hero-tagline">"Masakan Indonesia &amp; Chinese Halal Legendaris di Surabaya"</p>
  <p class="hero-sub">Nikmati hidangan berkualitas dengan cita rasa khas sejak lama</p>
  <div class="hero-cta">
    <a href="#menu" class="btn-primary">🍽 Lihat Menu</a>
    <a href="#" class="btn-outline" onclick="return false;">
      📲 Order via WhatsApp
      <span class="dummy-tag">DEMO</span>
    </a>
  </div>
  <div class="hero-info-strip">
    <div class="info-item">
      <span class="icon">🕙</span>
      <div>Buka <strong>10.00 – 22.00</strong></div>
    </div>
    <div class="info-item">
      <span class="icon">📍</span>
      <div>Raya Kendangsari 99, <strong>Surabaya</strong></div>
    </div>
    <div class="info-item">
      <span class="icon">📞</span>
      <div>Telp <strong>031-8415599</strong></div>
    </div>
  </div>
</div>

<!-- MENU SECTION -->
<div class="section-divider"></div>
<div id="menu">
  <div class="section-inner">
    <span class="section-label">✦ Pilihan Terbaik</span>
    <h2 class="section-title">Menu <em>Unggulan</em></h2>
    <p class="section-desc">Dibuat dengan bahan segar pilihan dan rempah berkualitas setiap harinya.</p>

    <div class="menu-tabs">
      <button class="tab-btn active" onclick="showTab('minuman', this)">🥤 Minuman</button>
      <button class="tab-btn" onclick="showTab('signature', this)">👑 Signature</button>
    </div>

    <!-- Minuman -->
    <div id="tab-minuman" class="menu-grid">
      <div class="menu-card">
        <span class="menu-emoji">🥤</span>
        <span class="menu-badge">Segar</span>
        <div class="menu-name">Es Teler</div>
        <div class="menu-desc">Campuran alpukat, kelapa, kolang-kaling, dan nangka dalam santan segar yang menyegarkan.</div>
        <div class="menu-price">Rp 31.000 <span>/ porsi</span></div>
      </div>
      <div class="menu-card">
        <span class="menu-emoji">🍧</span>
        <span class="menu-badge">Favorit</span>
        <div class="menu-name">Es Campur</div>
        <div class="menu-desc">Perpaduan isian es serut dengan topping lengkap khas Surabaya yang menggugah selera.</div>
        <div class="menu-price">Rp 31.000 <span>/ porsi</span></div>
      </div>
      <div class="menu-card">
        <span class="menu-emoji">🥑</span>
        <span class="menu-badge">Premium</span>
        <div class="menu-name">Juice Alpukat</div>
        <div class="menu-desc">Alpukat segar diblender dengan susu coklat, creamy dan kaya nutrisi.</div>
        <div class="menu-price">Rp 31.000 <span>/ porsi</span></div>
      </div>
      <div class="menu-card">
        <span class="menu-emoji">🥥</span>
        <span class="menu-badge">Segar</span>
        <div class="menu-name">Es Jeruk Degan</div>
        <div class="menu-desc">Perpaduan jeruk segar dan kelapa muda yang ringan dan menyegarkan.</div>
        <div class="menu-price">Rp 26.000 <span>/ porsi</span></div>
      </div>
    </div>

    <!-- Signature -->
    <div id="tab-signature" class="signature-grid" style="display:none;">
      <div class="signature-card">
        <span class="crown">🏆</span>
        <h3>Sego Tumpeng</h3>
        <p>Tumpeng nasi kuning atau nasi putih dengan lauk lengkap khas Jawa. Ideal untuk acara syukuran, ulang tahun, dan selamatan.</p>
        <span class="custom-tag">Custom Order</span>
      </div>
      <div class="signature-card">
        <span class="crown">✨</span>
        <h3>Tumpeng Nasi Kuning</h3>
        <p>Simbol kemakmuran dalam budaya Jawa. Disajikan dengan berbagai lauk pauk pilihan yang lezat dan halal.</p>
        <span class="custom-tag">Custom Order</span>
      </div>
      <div class="signature-card">
        <span class="crown">🌾</span>
        <h3>Tumpeng Nasi Putih</h3>
        <p>Tampilan elegan dengan nasi putih pulen. Cocok untuk berbagai hajatan dan acara keluarga besar.</p>
        <span class="custom-tag">Custom Order</span>
      </div>
      <div class="signature-card" style="background: rgba(201,168,76,0.03); border-style: dashed; display:flex; align-items:center; justify-content:center; flex-direction:column; gap:10px;">
        <span style="font-size:36px">🔒</span>
        <p style="color: var(--text-muted); font-size: 13px; text-align: center;">Dan banyak menu lainnya<br>tersedia di website lengkap</p>
      </div>
    </div>

    <div class="menu-locked">
      <span class="lock-icon">🔒</span>
      <div>
        <strong>Menu Lengkap Tersedia di Website Full</strong>
        Hubungi AutoCuan Digital untuk mengaktifkan seluruh fitur menu, sistem order, dan tampilan premium.
      </div>
    </div>
  </div>
</div>

<!-- ABOUT -->
<div class="section-divider"></div>
<section id="about">
  <div class="about-visual">
    <div class="about-visual-inner">🍲</div>
  </div>
  <div>
    <span class="section-label">✦ Tentang Kami</span>
    <h2 class="section-title">Cita Rasa <em>Autentik</em> Sejak Lama</h2>
    <p class="section-desc" style="max-width: 100%; margin-bottom: 20px;">
      RM. Sriwedari merupakan restoran yang menyajikan masakan Indonesia dan Chinese halal dengan cita rasa autentik. Berlokasi di Surabaya, kami menjadi pilihan keluarga untuk berbagai acara dan santapan sehari-hari.
    </p>
    <p class="section-desc" style="max-width: 100%;">
      Setiap hidangan dimasak dengan bahan-bahan segar pilihan dan bumbu rempah berkualitas, menghadirkan pengalaman makan yang tak terlupakan untuk seluruh keluarga.
    </p>
    <div class="about-stats">
      <div class="stat-box">
        <div class="stat-num">100%</div>
        <div class="stat-label">Halal Terjamin</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">2 Masak</div>
        <div class="stat-label">Indonesia & Chinese</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">Surabaya</div>
        <div class="stat-label">Kendangsari, Sby</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">10–22</div>
        <div class="stat-label">Jam Buka Setiap Hari</div>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONI -->
<div class="section-divider"></div>
<div id="testimoni">
  <div class="section-inner">
    <span class="section-label">✦ Apa Kata Pelanggan</span>
    <h2 class="section-title">Testimoni <em>Pelanggan</em></h2>
    <div class="testi-grid">
      <div class="testi-card">
        <span class="quote-mark">"</span>
        <p class="testi-text">Makanannya enak banget dan tempatnya nyaman. Cocok buat makan siang keluarga. Nasi tumpengnya juara, pasti balik lagi!</p>
        <div class="testi-author">
          <div class="testi-avatar">👩</div>
          <div>
            <div class="testi-name">Dewi S.</div>
            <div class="testi-stars">★★★★★</div>
          </div>
        </div>
      </div>
      <div class="testi-card">
        <span class="quote-mark">"</span>
        <p class="testi-text">Cocok banget buat keluarga dan acara. Tumpengnya rapi, lauk lengkap, dan halal. Pelayanannya ramah dan cepat!</p>
        <div class="testi-author">
          <div class="testi-avatar">👨</div>
          <div>
            <div class="testi-name">Budi H.</div>
            <div class="testi-stars">★★★★★</div>
          </div>
        </div>
      </div>
    </div>
    <div class="testi-gmaps">
      <span class="lock-icon">🔒</span>
      <div>
        <strong>Lihat Review Lengkap di Google Maps</strong>
        &nbsp;— Tersedia di website full version
      </div>
    </div>
  </div>
</div>

<!-- LOKASI -->
<div class="section-divider"></div>
<section id="lokasi">
  <div>
    <span class="section-label">✦ Temukan Kami</span>
    <h2 class="section-title">Lokasi <em>Kami</em></h2>
    <div class="lokasi-detail">
      <div class="lokasi-row">
        <span class="icon">📍</span>
        <div>
          <strong>Alamat</strong>
          Jl. Raya Kendangsari No. 99, Surabaya, Jawa Timur
        </div>
      </div>
      <div class="lokasi-row">
        <span class="icon">🕙</span>
        <div>
          <strong>Jam Operasional</strong>
          Setiap hari: 10.00 – 22.00 WIB
        </div>
      </div>
      <div class="lokasi-row">
        <span class="icon">📞</span>
        <div>
          <strong>Telepon</strong>
          031 - 8415599
        </div>
      </div>
      <div class="lokasi-row">
        <span class="icon">📲</span>
        <div>
          <strong>WhatsApp</strong>
          081383337185
        </div>
      </div>
    </div>
  </div>
  <div class="map-container">
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3957.1!2d112.749!3d-7.325!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2dd7fbc0b2e3f1a7%3A0x0!2sJl.+Raya+Kendangsari+99%2C+Surabaya!5e0!3m2!1sid!2sid!4v1"
      allowfullscreen=""
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade">
    </iframe>
  </div>
</section>

<!-- CTA -->
<div class="section-divider"></div>
<div id="cta" style="padding: 80px 0 20px;">
  <div class="cta-section">
    <h2>Pesan Sekarang &amp; Nikmati<br>Hidangan Terbaik dari <em>RM Sriwedari</em></h2>
    <p>Hubungi kami via WhatsApp untuk reservasi, custom order tumpeng, dan info promo terbaru</p>
    <div class="cta-btns">
      <a href="#" class="btn-primary" onclick="return false;" style="position:relative;">
        📲 Pesan via WhatsApp
        <span style="position:absolute;top:-10px;right:-10px;background:#3D2200;color:#E8C96A;font-size:9px;padding:2px 6px;border-radius:4px;letter-spacing:0.1em;border:1px solid #8B6E30;">DEMO</span>
      </a>
      <a href="tel:03184155990" class="btn-outline">📞 Hubungi Telepon</a>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">
    RM. Sriwedari
    <span>Masakan Indonesia & Chinese · Halal · Surabaya</span>
  </div>
  <div class="footer-copy">
    © 2025 RM. Sriwedari · Jl. Raya Kendangsari 99, Surabaya<br>
    <span style="font-size:11px; color: var(--gold-dim);">⚠️ Demo preview — Tombol WA dan fitur order belum aktif</span>
  </div>
  <div class="footer-wm">
    Demo by<br>
    <strong>AutoCuan Digital</strong>
  </div>
</footer>

<script>
  function showTab(tab, btn) {
    document.getElementById('tab-minuman').style.display = 'none';
    document.getElementById('tab-signature').style.display = 'none';
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('tab-' + tab).style.display = tab === 'signature' ? 'grid' : 'grid';
    btn.classList.add('active');
    if (tab === 'minuman') {
      document.getElementById('tab-minuman').style.display = 'grid';
    } else {
      document.getElementById('tab-signature').style.display = 'grid';
    }
  }

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.menu-card, .signature-card, .testi-card, .stat-box').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
