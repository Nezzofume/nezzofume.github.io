<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Nezzofume — Luxury Perfume Landing Page</title>
  <meta name="description" content="Nezzofume menghadirkan parfum premium dengan karakter elegan, berkelas, dan berkesan. Temukan signature scent yang mencerminkan identitasmu." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #070707;
      --bg-soft: #101010;
      --panel: rgba(255,255,255,0.04);
      --panel-2: rgba(255,255,255,0.06);
      --text: #f7f1e8;
      --muted: #c4bba8;
      --gold: #d9b36a;
      --gold-soft: #f0d8a6;
      --line: rgba(217,179,106,0.22);
      --shadow: 0 20px 80px rgba(0,0,0,.45);
      --radius-xl: 28px;
      --radius-lg: 22px;
      --radius-md: 16px;
      --max: 1200px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: 'Inter', sans-serif;
      background:
        radial-gradient(circle at top right, rgba(217,179,106,.12), transparent 28%),
        radial-gradient(circle at left center, rgba(217,179,106,.08), transparent 24%),
        linear-gradient(180deg, #050505 0%, #090909 45%, #060606 100%);
      color: var(--text);
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background: linear-gradient(rgba(255,255,255,.02), rgba(255,255,255,0));
      mix-blend-mode: soft-light;
      opacity: .4;
    }

    img { max-width: 100%; display: block; }
    a { color: inherit; text-decoration: none; }
    .container { width: min(calc(100% - 32px), var(--max)); margin: 0 auto; }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(18px);
      background: rgba(5,5,5,.65);
      border-bottom: 1px solid rgba(255,255,255,.05);
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      min-height: 78px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 14px;
      letter-spacing: .18em;
      text-transform: uppercase;
      font-size: 13px;
      font-weight: 700;
    }

    .brand-mark {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      border: 1px solid var(--line);
      display: grid;
      place-items: center;
      color: var(--gold-soft);
      background: radial-gradient(circle at 30% 30%, rgba(255,255,255,.14), rgba(255,255,255,.02));
      box-shadow: inset 0 0 24px rgba(217,179,106,.08);
      font-family: 'Cormorant Garamond', serif;
      font-size: 20px;
    }

    .menu {
      display: flex;
      align-items: center;
      gap: 22px;
      color: var(--muted);
      font-size: 14px;
    }

    .menu a:hover { color: var(--gold-soft); }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 14px 22px;
      border-radius: 999px;
      border: 1px solid transparent;
      font-weight: 600;
      transition: .25s ease;
    }

    .btn-primary {
      color: #111;
      background: linear-gradient(135deg, var(--gold-soft), var(--gold));
      box-shadow: 0 10px 30px rgba(217,179,106,.2);
    }

    .btn-primary:hover { transform: translateY(-2px); }

    .btn-outline {
      border-color: var(--line);
      color: var(--text);
      background: rgba(255,255,255,.02);
    }

    .btn-outline:hover {
      border-color: rgba(217,179,106,.55);
      background: rgba(255,255,255,.04);
    }

    .hero {
      position: relative;
      padding: 82px 0 60px;
      overflow: hidden;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 40px;
      align-items: center;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 10px 14px;
      border: 1px solid rgba(217,179,106,.18);
      border-radius: 999px;
      color: var(--gold-soft);
      background: rgba(255,255,255,.02);
      font-size: 12px;
      letter-spacing: .16em;
      text-transform: uppercase;
      margin-bottom: 22px;
    }

    h1, h2, h3, h4 {
      margin: 0;
      font-family: 'Cormorant Garamond', serif;
      line-height: 1;
      letter-spacing: -.02em;
    }

    h1 {
      font-size: clamp(52px, 8vw, 98px);
      line-height: .95;
      max-width: 740px;
    }

    .hero h1 span { color: var(--gold); }

    .hero-copy p {
      margin: 24px 0 0;
      max-width: 620px;
      color: var(--muted);
      font-size: 17px;
      line-height: 1.9;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-top: 34px;
    }

    .hero-stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
      margin-top: 44px;
    }

    .stat {
      padding: 18px 18px;
      border-radius: var(--radius-md);
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.025));
      border: 1px solid rgba(255,255,255,.05);
      box-shadow: var(--shadow);
    }

    .stat strong {
      display: block;
      font-size: 24px;
      color: var(--gold-soft);
      margin-bottom: 8px;
      font-family: 'Cormorant Garamond', serif;
    }

    .stat span { color: var(--muted); font-size: 13px; line-height: 1.6; }

    .hero-visual {
      position: relative;
      min-height: 640px;
      display: grid;
      place-items: center;
    }

    .glow {
      position: absolute;
      inset: 12% 12% auto auto;
      width: 320px;
      height: 320px;
      background: radial-gradient(circle, rgba(217,179,106,.35), transparent 65%);
      filter: blur(24px);
    }

    .bottle-card {
      position: relative;
      width: min(100%, 470px);
      aspect-ratio: 4/5;
      border-radius: 34px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.07), rgba(255,255,255,.02)),
        radial-gradient(circle at top, rgba(217,179,106,.12), transparent 35%),
        #0f0f0f;
      border: 1px solid rgba(255,255,255,.07);
      box-shadow: var(--shadow);
      overflow: hidden;
      display: grid;
      place-items: center;
    }

    .bottle-card::before,
    .bottle-card::after {
      content: "";
      position: absolute;
      border-radius: 50%;
      border: 1px solid rgba(217,179,106,.2);
    }

    .bottle-card::before {
      width: 120%;
      height: 120%;
      top: -70%;
      right: -40%;
    }

    .bottle-card::after {
      width: 78%;
      height: 78%;
      bottom: -35%;
      left: -10%;
    }

    .bottle {
      position: relative;
      width: 220px;
      height: 400px;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      filter: drop-shadow(0 30px 50px rgba(0,0,0,.5));
    }

    .cap {
      position: absolute;
      top: 34px;
      width: 88px;
      height: 74px;
      border-radius: 18px 18px 10px 10px;
      background: linear-gradient(180deg, #bb934c, #7f5a20);
      border: 1px solid rgba(255,255,255,.12);
      z-index: 2;
    }

    .neck {
      position: absolute;
      top: 90px;
      width: 42px;
      height: 34px;
      border-radius: 10px;
      background: linear-gradient(180deg, #87642b, #5e4014);
      z-index: 1;
    }

    .glass {
      width: 210px;
      height: 285px;
      border-radius: 34px 34px 28px 28px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.15), rgba(255,255,255,.03)),
        linear-gradient(180deg, rgba(30,30,30,.4), rgba(12,12,12,.9));
      border: 1px solid rgba(255,255,255,.1);
      position: relative;
      overflow: hidden;
      backdrop-filter: blur(8px);
      display: grid;
      place-items: center;
      padding: 28px;
    }

    .glass::before {
      content: "";
      position: absolute;
      inset: auto 0 0 0;
      height: 58%;
      background: linear-gradient(180deg, rgba(217,179,106,.07), rgba(217,179,106,.28));
    }

    .glass::after {
      content: "";
      position: absolute;
      left: 16px;
      top: 18px;
      width: 28px;
      height: 72%;
      background: linear-gradient(180deg, rgba(255,255,255,.22), transparent);
      filter: blur(1px);
      opacity: .5;
      transform: skewX(-8deg);
    }

    .label {
      position: relative;
      z-index: 2;
      width: 100%;
      padding: 20px 16px;
      border: 1px solid rgba(217,179,106,.35);
      border-radius: 18px;
      background: rgba(0,0,0,.32);
      text-align: center;
    }

    .label small {
      display: block;
      color: var(--gold-soft);
      letter-spacing: .28em;
      text-transform: uppercase;
      font-size: 10px;
      margin-bottom: 10px;
    }

    .label strong {
      display: block;
      font-family: 'Cormorant Garamond', serif;
      font-size: 28px;
      color: #fff;
      margin-bottom: 6px;
    }

    .label span {
      color: var(--muted);
      font-size: 12px;
      letter-spacing: .08em;
      text-transform: uppercase;
    }

    .floating-note,
    .floating-award {
      position: absolute;
      padding: 16px 18px;
      border-radius: 18px;
      background: rgba(12,12,12,.82);
      border: 1px solid rgba(255,255,255,.08);
      box-shadow: var(--shadow);
      backdrop-filter: blur(14px);
      max-width: 220px;
    }

    .floating-note {
      left: 0;
      bottom: 110px;
    }

    .floating-award {
      right: 0;
      top: 90px;
    }

    .floating-note strong,
    .floating-award strong {
      display: block;
      color: var(--gold-soft);
      margin-bottom: 8px;
      font-size: 15px;
    }

    .floating-note p,
    .floating-award p {
      margin: 0;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.7;
    }

    section.section { padding: 88px 0; }

    .section-head {
      display: flex;
      justify-content: space-between;
      gap: 24px;
      align-items: end;
      margin-bottom: 34px;
    }

    .section-head p {
      margin: 0;
      max-width: 560px;
      color: var(--muted);
      line-height: 1.8;
    }

    h2 {
      font-size: clamp(38px, 5vw, 62px);
      line-height: .95;
      margin-bottom: 12px;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
    }

    .card {
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.03));
      border: 1px solid rgba(255,255,255,.07);
      border-radius: var(--radius-xl);
      padding: 32px;
      box-shadow: var(--shadow);
    }

    .about-copy p,
    .long-copy {
      color: var(--muted);
      line-height: 1.95;
      font-size: 15px;
    }

    .pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 22px;
    }

    .pill {
      padding: 10px 14px;
      border-radius: 999px;
      background: rgba(255,255,255,.03);
      border: 1px solid rgba(217,179,106,.15);
      font-size: 13px;
      color: var(--gold-soft);
    }

    .composition {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
      margin-top: 24px;
    }

    .note-box {
      padding: 20px;
      border-radius: 18px;
      background: rgba(255,255,255,.03);
      border: 1px solid rgba(255,255,255,.06);
    }

    .note-box small {
      display: block;
      color: var(--gold-soft);
      text-transform: uppercase;
      letter-spacing: .15em;
      font-size: 11px;
      margin-bottom: 12px;
    }

    .note-box strong {
      display: block;
      margin-bottom: 8px;
      font-size: 19px;
      font-family: 'Cormorant Garamond', serif;
    }

    .note-box p {
      margin: 0;
      color: var(--muted);
      line-height: 1.8;
      font-size: 14px;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 18px;
      margin-top: 30px;
    }

    .feature {
      padding: 24px;
      border-radius: 22px;
      border: 1px solid rgba(255,255,255,.06);
      background: rgba(255,255,255,.03);
    }

    .feature .icon {
      width: 46px;
      height: 46px;
      border-radius: 14px;
      display: grid;
      place-items: center;
      background: rgba(217,179,106,.12);
      color: var(--gold-soft);
      font-size: 19px;
      margin-bottom: 16px;
    }

    .feature h3 { font-size: 26px; margin-bottom: 12px; }
    .feature p { margin: 0; color: var(--muted); line-height: 1.8; font-size: 14px; }

    .product-showcase {
      display: grid;
      grid-template-columns: .95fr 1.05fr;
      gap: 24px;
      align-items: stretch;
    }

    .product-visual {
      min-height: 560px;
      position: relative;
      overflow: hidden;
    }

    .gold-orb {
      position: absolute;
      width: 260px;
      height: 260px;
      right: -30px;
      top: -30px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(217,179,106,.34), transparent 65%);
      filter: blur(10px);
    }

    .product-panel {
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 24px;
    }

    .meta {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 14px;
    }

    .meta-item {
      padding: 16px;
      border-radius: 18px;
      background: rgba(255,255,255,.03);
      border: 1px solid rgba(255,255,255,.06);
    }

    .meta-item span {
      display: block;
      color: var(--muted);
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: .14em;
      margin-bottom: 8px;
    }

    .meta-item strong {
      font-size: 18px;
      font-family: 'Cormorant Garamond', serif;
    }

    .info-list {
      display: grid;
      gap: 14px;
      margin-top: 10px;
    }

    .info-item {
      padding: 18px 18px;
      border-left: 2px solid rgba(217,179,106,.55);
      background: rgba(255,255,255,.03);
      border-radius: 0 16px 16px 0;
    }

    .info-item strong {
      display: block;
      color: var(--gold-soft);
      margin-bottom: 6px;
      font-size: 14px;
      letter-spacing: .12em;
      text-transform: uppercase;
    }

    .info-item p {
      margin: 0;
      color: var(--muted);
      line-height: 1.8;
      font-size: 14px;
    }

    .highlight {
      color: var(--gold-soft);
      font-weight: 600;
    }

    .testimonial {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .quote {
      position: relative;
      padding: 28px;
      border-radius: 24px;
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.025));
      border: 1px solid rgba(255,255,255,.06);
    }

    .quote::before {
      content: '“';
      position: absolute;
      top: 18px;
      right: 24px;
      font-size: 62px;
      font-family: 'Cormorant Garamond', serif;
      color: rgba(217,179,106,.18);
      line-height: 1;
    }

    .quote p {
      margin: 0 0 24px;
      color: var(--muted);
      line-height: 1.95;
      font-size: 14px;
    }

    .quote strong { display: block; color: #fff; }
    .quote span { color: var(--gold-soft); font-size: 13px; }

    .cta {
      position: relative;
      overflow: hidden;
      padding: 38px;
      border-radius: 32px;
      border: 1px solid rgba(217,179,106,.16);
      background:
        radial-gradient(circle at right top, rgba(217,179,106,.18), transparent 34%),
        linear-gradient(135deg, rgba(255,255,255,.05), rgba(255,255,255,.03));
      box-shadow: var(--shadow);
    }

    .cta-grid {
      display: grid;
      grid-template-columns: 1.2fr .8fr;
      gap: 26px;
      align-items: center;
    }

    .cta p {
      color: var(--muted);
      line-height: 1.9;
      margin: 14px 0 0;
      max-width: 650px;
    }

    .cta-actions {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-end;
      gap: 12px;
    }

    footer {
      padding: 34px 0 50px;
      color: var(--muted);
      font-size: 14px;
    }

    .footer-row {
      display: flex;
      justify-content: space-between;
      gap: 18px;
      align-items: center;
      border-top: 1px solid rgba(255,255,255,.05);
      padding-top: 22px;
    }

    @media (max-width: 1080px) {
      .hero-grid,
      .grid-2,
      .product-showcase,
      .cta-grid,
      .testimonial,
      .features {
        grid-template-columns: 1fr;
      }

      .hero-visual { min-height: 540px; }
      .hero-stats,
      .composition,
      .meta { grid-template-columns: 1fr 1fr; }
      .cta-actions { justify-content: flex-start; }
    }

    @media (max-width: 720px) {
      .menu { display: none; }
      .hero { padding-top: 42px; }
      h1 { font-size: 54px; }
      .hero-stats,
      .composition,
      .meta { grid-template-columns: 1fr; }
      .features { grid-template-columns: 1fr; }
      .section-head,
      .footer-row {
        flex-direction: column;
        align-items: flex-start;
      }
      .floating-note,
      .floating-award {
        position: static;
        max-width: none;
        margin-top: 14px;
      }
      .hero-visual {
        min-height: unset;
        display: block;
      }
      .bottle-card { margin: 0 auto; }
      .cta { padding: 28px; }
      .card { padding: 24px; }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <div class="container nav">
      <a href="#home" class="brand">
        <span class="brand-mark">N</span>
        <span>Nezzofume</span>
      </a>

      <nav class="menu">
        <a href="#tentang">Brand</a>
        <a href="#komposisi">Isi Badan</a>
        <a href="#parfum">Parfum</a>
        <a href="#detail">Detail</a>
      </nav>

      <a href="#cta" class="btn btn-primary">Hubungi Kami</a>
    </div>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="container hero-grid">
        <div class="hero-copy">
          <div class="eyebrow">Luxury Perfume House</div>
          <h1>Parfum premium untuk <span>identitas</span> yang tidak mudah dilupakan.</h1>
          <p>
            Nezzofume menghadirkan pengalaman aroma yang elegan, berkarakter, dan berkelas. Dirancang untuk mereka yang ingin tampil berbeda sejak semprotan pertama, dengan kesan mewah yang bertahan dan meninggalkan memori.
          </p>

          <div class="hero-actions">
            <a href="#parfum" class="btn btn-primary">Lihat Koleksi</a>
            <a href="#detail" class="btn btn-outline">Pelajari Detail</a>
          </div>

          <div class="hero-stats">
            <div class="stat">
              <strong>Premium DNA</strong>
              <span>Karakter aroma dirancang agar terasa eksklusif, modern, dan mudah dikenali.</span>
            </div>
            <div class="stat">
              <strong>Long Lasting</strong>
              <span>Komposisi dibuat untuk memberi impresi kuat sejak opening hingga dry down.</span>
            </div>
            <div class="stat">
              <strong>Luxury Presence</strong>
              <span>Tampilan visual dan pengalaman produk disusun untuk kelas premium.</span>
            </div>
          </div>
        </div>

        <div class="hero-visual">
          <div class="glow"></div>
          <div class="bottle-card">
            <div class="bottle">
              <div class="cap"></div>
              <div class="neck"></div>
              <div class="glass">
                <div class="label">
                  <small>Signature Edition</small>
                  <strong>De Luna Scandalum</strong>
                  <span>Extrait de Parfum</span>
                </div>
              </div>
            </div>
          </div>

          <div class="floating-note">
            <strong>Opening Impression</strong>
            <p>Fresh, luxurious, dan langsung memberi kesan bahwa aroma ini punya kelas tersendiri.</p>
          </div>

          <div class="floating-award">
            <strong>Brand Character</strong>
            <p>Black & gold aesthetic untuk menonjolkan identitas Nezzofume yang elegan dan profesional.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="tentang">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow">Brand</div>
            <h2>Nezzofume, bukan sekadar parfum.</h2>
          </div>
          <p>
            Sebuah brand yang dibangun untuk menghadirkan aroma sebagai simbol karakter. Fokusnya bukan hanya wangi, tetapi impresi, kepercayaan diri, dan kesan premium yang melekat pada setiap pemakaian.
          </p>
        </div>

        <div class="grid-2">
          <div class="card about-copy">
            <h3 style="font-size:40px; margin-bottom:18px;">Filosofi Brand</h3>
            <p>
              Nezzofume dirancang untuk orang yang ingin tampil berkelas tanpa harus berlebihan. Konsep brand ini menekankan keseimbangan antara kemewahan, ketegasan, dan kenyamanan aroma, sehingga parfum terasa istimewa baik untuk penggunaan harian maupun momen spesial.
            </p>
            <p>
              Identitas visual hitam dan gold dipilih untuk memperkuat citra eksklusif, sophisticated, dan mudah dikenali. Setiap detail diarahkan agar brand tampil profesional, premium, dan siap bersaing di pasar parfum modern.
            </p>
            <div class="pill-row">
              <span class="pill">Luxury Identity</span>
              <span class="pill">Modern Elegance</span>
              <span class="pill">Premium Presentation</span>
              <span class="pill">Signature Scent</span>
            </div>
          </div>

          <div class="card">
            <h3 style="font-size:40px; margin-bottom:18px;">Nilai Utama</h3>
            <div class="info-list">
              <div class="info-item">
                <strong>Eksklusivitas</strong>
                <p>Karakter wangi dibuat agar terasa berbeda dari racikan pasaran dan memiliki identitas yang kuat.</p>
              </div>
              <div class="info-item">
                <strong>Keseimbangan</strong>
                <p>Perpaduan aroma dipikirkan untuk menghadirkan opening, transisi, dan dry down yang harmonis.</p>
              </div>
              <div class="info-item">
                <strong>Pengalaman Premium</strong>
                <p>Bukan hanya dari aromanya, tetapi juga dari tampilan, storytelling, dan kesan saat pertama kali melihat produk.</p>
              </div>
              <div class="info-item">
                <strong>Kepercayaan Diri</strong>
                <p>Parfum yang dirancang untuk membuat pemakainya tampil lebih yakin, rapi, dan meninggalkan jejak yang berkesan.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="komposisi">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow">Isi Badan</div>
            <h2>Komposisi aroma yang berlapis dan berkarakter.</h2>
          </div>
          <p>
            Struktur parfum dibangun untuk memberikan pengalaman bertahap, mulai dari kesan pertama yang memikat, jantung aroma yang menonjolkan identitas, hingga dasar aroma yang hangat dan tahan lama.
          </p>
        </div>

        <div class="card">
          <div class="composition">
            <div class="note-box">
              <small>Top Notes</small>
              <strong>Fresh Opening</strong>
              <p>Bagian pembuka yang menghadirkan first impression. Umumnya terasa segar, bersih, terang, dan langsung menarik perhatian pada semprotan awal.</p>
            </div>
            <div class="note-box">
              <small>Middle Notes</small>
              <strong>Heart of the Scent</strong>
              <p>Inti karakter parfum. Di sinilah identitas aroma mulai berbicara lebih jelas dan menjadi pusat pengalaman pemakaian.</p>
            </div>
            <div class="note-box">
              <small>Base Notes</small>
              <strong>Lasting Impression</strong>
              <p>Fondasi parfum yang memberi kedalaman, kehangatan, dan daya tahan. Bagian inilah yang tertinggal paling lama di kulit maupun pakaian.</p>
            </div>
          </div>

          <div class="features">
            <div class="feature">
              <div class="icon">✦</div>
              <h3>Blend Halus</h3>
              <p>Transisi tiap lapisan aroma dirancang agar tidak terasa patah, tetapi menyatu secara elegan.</p>
            </div>
            <div class="feature">
              <div class="icon">◈</div>
              <h3>Projection</h3>
              <p>Menciptakan aura wangi yang terasa hadir tanpa terkesan berlebihan atau menusuk.</p>
            </div>
            <div class="feature">
              <div class="icon">◆</div>
              <h3>Depth</h3>
              <p>Memberi nuansa kaya, mewah, dan kompleks agar parfum tidak terasa datar.</p>
            </div>
            <div class="feature">
              <div class="icon">✺</div>
              <h3>Memorable</h3>
              <p>Dibuat untuk meninggalkan kesan khas yang mudah diingat oleh orang di sekitar.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="parfum">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow">Parfum</div>
            <h2>Signature scent yang memancarkan kemewahan modern.</h2>
          </div>
          <p>
            Halaman ini bisa difokuskan untuk satu produk utama atau diperluas menjadi beberapa varian. Saat ini disusun dengan satu parfum unggulan agar presentasinya lebih eksklusif dan terarah.
          </p>
        </div>

        <div class="product-showcase">
          <div class="card product-visual">
            <div class="gold-orb"></div>
            <div class="bottle" style="margin: 40px auto 0; transform: scale(1.05);">
              <div class="cap"></div>
              <div class="neck"></div>
              <div class="glass">
                <div class="label">
                  <small>Nezzofume</small>
                  <strong>De Luna Scandalum</strong>
                  <span>Luxury Extrait</span>
                </div>
              </div>
            </div>
          </div>

          <div class="card product-panel">
            <div>
              <div class="eyebrow" style="margin-bottom:16px;">Nama Parfum</div>
              <h3 style="font-size:56px; margin-bottom:14px;">De Luna Scandalum</h3>
              <p class="long-copy">
                Sebuah parfum dengan pendekatan elegan, sensual, dan misterius. Dirancang untuk menghadirkan aura mewah yang langsung terasa sejak semprotan pertama, lalu berkembang menjadi karakter yang lebih dalam, hangat, dan sophisticated.
              </p>
            </div>

            <div class="meta">
              <div class="meta-item">
                <span>Kategori</span>
                <strong>Unisex Premium</strong>
              </div>
              <div class="meta-item">
                <span>Kesan</span>
                <strong>Elegant • Bold • Addictive</strong>
              </div>
              <div class="meta-item">
                <span>Cocok Untuk</span>
                <strong>Daily & Special Moment</strong>
              </div>
              <div class="meta-item">
                <span>Persona</span>
                <strong>Modern Luxury</strong>
              </div>
            </div>

            <div class="info-list">
              <div class="info-item">
                <strong>Karakter Aroma</strong>
                <p>Fresh opening yang memikat, jantung aroma yang anggun, lalu ditutup basis hangat dan creamy yang memberikan kesan <span class="highlight">mahal serta berkelas</span>.</p>
              </div>
              <div class="info-item">
                <strong>Target Kesan</strong>
                <p>Dibuat untuk memunculkan reaksi seperti: <span class="highlight">“ini aroma yang beda, rapi, dan punya identitas.”</span></p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="detail">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow">Detail Parfum</div>
            <h2>Deskripsi lengkap yang menjual pengalaman, bukan hanya wangi.</h2>
          </div>
          <p>
            Bagian ini sangat penting untuk meningkatkan rasa percaya pelanggan. Detail yang kuat akan membantu calon pembeli membayangkan aroma, situasi pemakaian, dan karakter produk sebelum mereka mencoba secara langsung.
          </p>
        </div>

        <div class="grid-2">
          <div class="card">
            <h3 style="font-size:42px; margin-bottom:20px;">Pyramid Notes</h3>
            <div class="info-list">
              <div class="info-item">
                <strong>Top Notes</strong>
                <p>Lavender, Pineapple, Bergamot, Lemon Verbena, Raspberry Liqueur — menghadirkan pembukaan yang segar, fruity, clean, namun tetap terasa dewasa dan mewah.</p>
              </div>
              <div class="info-item">
                <strong>Middle Notes</strong>
                <p>Red Apple, Dried Fruits, Oak Moss, Geranium, Coumarin, Rose, Peony — inti aroma yang mempertemukan nuansa floral, green, sweet, dan elegant dalam satu alur yang kaya.</p>
              </div>
              <div class="info-item">
                <strong>Base Notes</strong>
                <p>Tonka Bean, Sandalwood, Praline — penutup hangat, creamy, soft gourmand, dan meninggalkan jejak yang halus namun berkesan.</p>
              </div>
            </div>
          </div>

          <div class="card">
            <h3 style="font-size:42px; margin-bottom:20px;">Deskripsi Produk</h3>
            <p class="long-copy">
              De Luna Scandalum adalah representasi dari kemewahan yang modern: tidak terlalu berat, tidak terlalu ramai, tetapi tetap punya daya tarik yang kuat. Pembukaannya terasa cerah dan hidup, lalu berkembang menjadi inti aroma yang lebih sophisticated, sebelum akhirnya menetap dalam nuansa hangat dan sensual yang nyaman.
            </p>
            <p class="long-copy">
              Cocok digunakan untuk kamu yang ingin tampil rapi, elegan, dan berbeda tanpa harus terkesan berlebihan. Parfum ini ideal untuk menemani aktivitas harian, pertemuan penting, acara malam, hingga momen spesial yang membutuhkan kesan lebih eksklusif.
            </p>
            <div class="pill-row">
              <span class="pill">Elegant</span>
              <span class="pill">Mysterious</span>
              <span class="pill">Warm Finish</span>
              <span class="pill">Premium Presence</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow">Why Choose This</div>
            <h2>Alasan landing page ini cocok untuk brand premium.</h2>
          </div>
          <p>
            Struktur dibuat untuk membantu pengunjung memahami brand, merasakan nilai produknya, lalu terdorong untuk melakukan kontak atau pembelian.
          </p>
        </div>

        <div class="testimonial">
          <div class="quote">
            <p>Desain hitam dan gold memperkuat positioning premium, sangat cocok untuk brand parfum yang ingin terlihat mahal dan profesional.</p>
            <strong>Visual Premium</strong>
            <span>Luxury Branding</span>
          </div>
          <div class="quote">
            <p>Urutan konten dimulai dari identitas brand lalu turun ke produk dan detail, sehingga alur membaca terasa natural dan meyakinkan.</p>
            <strong>Struktur Jelas</strong>
            <span>High Conversion Flow</span>
          </div>
          <div class="quote">
            <p>Isi kontennya sudah mengarah ke copywriting penjualan, bukan sekadar teks biasa, jadi lebih kuat untuk kebutuhan promosi.</p>
            <strong>Copy Lebih Menjual</strong>
            <span>Professional Messaging</span>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="cta">
      <div class="container">
        <div class="cta">
          <div class="cta-grid">
            <div>
              <div class="eyebrow">Call To Action</div>
              <h2>Siap jadikan Nezzofume tampil lebih premium?</h2>
              <p>
                Landing page ini sudah siap dijadikan dasar untuk website parfum brand kamu. Tinggal tambahkan foto botol asli, harga, testimoni, link WhatsApp, marketplace, atau form pemesanan agar langsung siap dipakai untuk promosi dan penjualan.
              </p>
            </div>
            <div class="cta-actions">
              <a href="#home" class="btn btn-outline">Kembali ke Atas</a>
              <a href="https://wa.me/" class="btn btn-primary">Chat WhatsApp</a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-row">
      <div>© 2026 Nezzofume Perfumery. All rights reserved.</div>
      <div>Crafted for a premium fragrance experience.</div>
    </div>
  </footer>
</body>
</html>
