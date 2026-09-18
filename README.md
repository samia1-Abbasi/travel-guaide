[index.html](https://github.com/user-attachments/files/32366911/index.html)
#
tgt
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Wander Notes — A Travel Journal</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600&family=Work+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#1B2A3A;
    --parchment:#EFE6D8;
    --parchment-2:#E4D8C4;
    --ochre:#C98A3B;
    --teal:#2F5D62;
    --paper-text:#F7F3EC;
    --charcoal:#262220;
    --line:rgba(27,42,58,0.14);
    --radius:2px;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--parchment);
    color:var(--charcoal);
    font-family:'Work Sans', sans-serif;
    line-height:1.6;
    overflow-x:hidden;
  }
  h1,h2,h3,.logo{
    font-family:'Fraunces', serif;
    font-weight:500;
    letter-spacing:-0.01em;
  }
  a{color:inherit;text-decoration:none;}
  img{max-width:100%;display:block;}
  .wrap{max-width:1100px;margin:0 auto;padding:0 28px;}

  /* ---- Nav ---- */
  header{
    position:sticky;top:0;z-index:50;
    background:rgba(239,230,216,0.92);
    backdrop-filter:blur(6px);
    border-bottom:1px solid var(--line);
  }
  nav{
    display:flex;align-items:center;justify-content:space-between;
    padding:18px 28px;max-width:1100px;margin:0 auto;
  }
  .logo{font-size:1.3rem;color:var(--ink);}
  .logo em{font-style:italic;color:var(--ochre);}
  .nav-links{display:flex;gap:32px;list-style:none;font-size:0.95rem;}
  .nav-links a{position:relative;padding:4px 0;}
  .nav-links a:after{
    content:"";position:absolute;left:0;bottom:0;width:0;height:1px;
    background:var(--ink);transition:width .25s ease;
  }
  .nav-links a:hover:after{width:100%;}
  .nav-toggle{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;}
  .nav-toggle span{width:24px;height:2px;background:var(--ink);}

  /* ---- Hero ---- */
  .hero{
    position:relative;padding:120px 0 100px;overflow:hidden;
  }
  .route-svg{
    position:absolute;right:-60px;top:20px;width:520px;max-width:60vw;opacity:0.9;pointer-events:none;
  }
  .hero-inner{max-width:620px;position:relative;z-index:2;}
  .eyebrow{
    font-size:0.85rem;color:var(--teal);margin-bottom:18px;
  }
  .hero h1{
    font-size:clamp(2.6rem, 6vw, 4.2rem);
    color:var(--ink);
    line-height:1.05;
    margin-bottom:24px;
  }
  .hero p{
    font-size:1.15rem;max-width:480px;color:#4a433d;margin-bottom:34px;
  }
  .btn{
    display:inline-block;background:var(--ink);color:var(--paper-text);
    padding:14px 30px;border-radius:var(--radius);font-size:0.95rem;
    transition:background .2s ease, transform .2s ease;
  }
  .btn:hover{background:var(--teal);}
  .btn.outline{
    background:transparent;border:1px solid var(--ink);color:var(--ink);
  }
  .btn.outline:hover{background:var(--ink);color:var(--paper-text);}

  section{padding:100px 0;}
  .section-head{max-width:560px;margin-bottom:56px;}
  .section-head .eyebrow{margin-bottom:14px;}
  .section-head h2{font-size:clamp(1.9rem,3.4vw,2.6rem);color:var(--ink);}

  /* ---- About ---- */
  .about{background:var(--parchment-2);}
  .about-grid{
    display:grid;grid-template-columns:1fr 1.3fr;gap:64px;align-items:center;
  }
  .about-photo{
    aspect-ratio:4/5;border-radius:var(--radius);
    background:linear-gradient(160deg, var(--ink), var(--teal));
    position:relative;overflow:hidden;
  }
  .about-photo:before{
    content:"";position:absolute;inset:0;
    background-image: radial-gradient(circle at 30% 30%, rgba(247,243,236,0.14) 0, transparent 40%);
  }
  .about-photo .caption{
    position:absolute;bottom:18px;left:18px;color:var(--paper-text);
    font-size:0.8rem;letter-spacing:0.03em;opacity:0.85;
  }
  .about-text p{margin-bottom:18px;color:#3c352e;}
  .stat-row{display:flex;gap:40px;margin-top:34px;flex-wrap:wrap;}
  .stat b{font-family:'Fraunces',serif;font-size:1.8rem;color:var(--ink);display:block;}
  .stat span{font-size:0.85rem;color:#6b6258;}

  /* ---- Destinations ---- */
  .dest-grid{
    display:grid;grid-template-columns:repeat(3,1fr);gap:2px;background:var(--line);
  }
  .dest-card{
    background:var(--parchment);padding:36px 30px;position:relative;
    transition:background .25s ease;
  }
  .dest-card:hover{background:var(--parchment-2);}
  .dest-num{font-size:0.8rem;color:var(--ochre);margin-bottom:14px;display:block;}
  .dest-card h3{font-size:1.3rem;color:var(--ink);margin-bottom:10px;}
  .dest-card p{font-size:0.92rem;color:#5c554c;margin-bottom:14px;}
  .dest-meta{font-size:0.8rem;color:var(--teal);}

  /* ---- Blog ---- */
  .blog{background:var(--ink);color:var(--paper-text);}
  .blog .section-head h2{color:var(--paper-text);}
  .blog .eyebrow{color:#e0b97e;}
  .post-list{display:flex;flex-direction:column;}
  .post-row{
    display:grid;grid-template-columns:120px 1fr auto;gap:28px;align-items:baseline;
    padding:26px 0;border-bottom:1px solid rgba(247,243,236,0.15);
  }
  .post-row:first-child{border-top:1px solid rgba(247,243,236,0.15);}
  .post-date{font-size:0.85rem;color:#b9c2c4;}
  .post-title{font-family:'Fraunces',serif;font-size:1.25rem;}
  .post-title a{border-bottom:1px solid transparent;transition:border-color .2s ease;}
  .post-row:hover .post-title a{border-color:#e0b97e;}
  .post-tag{font-size:0.8rem;color:#e0b97e;justify-self:end;}

  /* ---- Gallery ---- */
  .gallery-grid{
    display:grid;grid-template-columns:repeat(4,1fr);gap:14px;
  }
  .gallery-grid div{
    aspect-ratio:1;border-radius:var(--radius);
  }
  .g1{background:linear-gradient(135deg,#C98A3B,#8a5a25);}
  .g2{background:linear-gradient(135deg,#2F5D62,#173033);}
  .g3{background:linear-gradient(135deg,#8a5a25,#1B2A3A);}
  .g4{background:linear-gradient(135deg,#1B2A3A,#2F5D62);}
  .g5{background:linear-gradient(135deg,#2F5D62,#C98A3B);grid-column:span 2;}
  .g6{background:linear-gradient(135deg,#173033,#8a5a25);}
  .g7{background:linear-gradient(135deg,#C98A3B,#2F5D62);}
  .gallery-note{margin-top:24px;font-size:0.85rem;color:#6b6258;}

  /* ---- Contact ---- */
  .contact{background:var(--parchment-2);}
  .contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:64px;}
  form{display:flex;flex-direction:column;gap:18px;}
  label{font-size:0.85rem;color:#5c554c;margin-bottom:6px;display:block;}
  input,textarea{
    width:100%;padding:13px 14px;border:1px solid var(--line);
    background:var(--parchment);font-family:'Work Sans',sans-serif;font-size:0.95rem;
    border-radius:var(--radius);
  }
  input:focus,textarea:focus{outline:2px solid var(--teal);outline-offset:1px;}
  textarea{resize:vertical;min-height:120px;}
  .contact-info p{margin-bottom:14px;color:#3c352e;}
  .contact-info a{color:var(--teal);border-bottom:1px solid var(--teal);}

  footer{
    padding:36px 0;text-align:center;font-size:0.85rem;color:#6b6258;
    border-top:1px solid var(--line);
  }

  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{transition:none !important;}
  }

  @media (max-width:820px){
    .about-grid,.contact-grid{grid-template-columns:1fr;gap:36px;}
    .dest-grid{grid-template-columns:1fr;}
    .gallery-grid{grid-template-columns:repeat(2,1fr);}
    .g5{grid-column:span 2;}
    .post-row{grid-template-columns:1fr;gap:6px;}
    .post-tag{justify-self:start;}
  }
  @media (max-width:640px){
    .nav-links{
      position:absolute;top:100%;left:0;right:0;background:var(--parchment);
      flex-direction:column;gap:0;border-bottom:1px solid var(--line);
      max-height:0;overflow:hidden;transition:max-height .3s ease;
    }
    .nav-links.open{max-height:300px;}
    .nav-links li{padding:14px 28px;border-top:1px solid var(--line);}
    .nav-toggle{display:flex;}
    .route-svg{display:none;}
    .hero{padding:80px 0 70px;}
  }
</style>
</head>
<body>

<header>
  <nav>
    <a href="#home" class="logo">Wander<em>Notes</em></a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#destinations">Destinations</a></li>
      <li><a href="#blog">Blog</a></li>
      <li><a href="#gallery">Gallery</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle menu">
      <span></span><span></span><span></span>
    </button>
  </nav>
</header>

<section class="hero" id="home">
  <svg class="route-svg" viewBox="0 0 500 400" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M20 350 C 120 320, 140 200, 240 210 S 340 100, 460 60" stroke="#1B2A3A" stroke-width="1.5" stroke-dasharray="2 8" stroke-linecap="round"/>
    <circle cx="20" cy="350" r="5" fill="#C98A3B"/>
    <circle cx="240" cy="210" r="5" fill="#2F5D62"/>
    <circle cx="460" cy="60" r="5" fill="#C98A3B"/>
  </svg>
  <div class="wrap hero-inner">
    <p class="eyebrow">A personal travel journal</p>
    <h1>Notes from every road I've followed.</h1>
    <p>Stories, places, and the small details worth remembering — written after the dust settles, not while the trip is still happening.</p>
    <a href="#blog" class="btn">Read the latest post</a>
  </div>
</section>

<section class="about" id="about">
  <div class="wrap about-grid">
    <div class="about-photo">
      <span class="caption">Somewhere along the way</span>
    </div>
    <div class="about-text">
      <p class="eyebrow">About</p>
      <h2 style="margin-bottom:20px;">Saamia — the person behind the notebook.</h2>
      <p>I write this journal to hold onto what usually gets lost after a trip ends: the name of the street where the food was best, the stranger who gave good directions, the light at a particular hour.</p>
      <p>No polished highlight reels here — just honest notes, practical details, and the occasional detour that turned out better than the plan.</p>
      <div class="stat-row">
        <div class="stat"><b>14</b><span>Countries visited</span></div>
        <div class="stat"><b>60+</b><span>Journal entries</span></div>
        <div class="stat"><b>3</b><span>Continents crossed</span></div>
      </div>
    </div>
  </div>
</section>

<section class="destinations" id="destinations">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">Destinations</p>
      <h2>Places worth the detour.</h2>
    </div>
  </div>
  <div class="dest-grid">
    <div class="dest-card">
      <span class="dest-num">01</span>
      <h3>Hunza Valley</h3>
      <p>Terraced orchards, glacier views, and the quietest mornings I've had anywhere.</p>
      <span class="dest-meta">Pakistan · 6 days</span>
    </div>
    <div class="dest-card">
      <span class="dest-num">02</span>
      <h3>Istanbul</h3>
      <p>A city that changes character block by block — ferries, tea houses, and old bookshops.</p>
      <span class="dest-meta">Turkey · 5 days</span>
    </div>
    <div class="dest-card">
      <span class="dest-num">03</span>
      <h3>Chiang Mai</h3>
      <p>Slow mornings at the temples, night markets, and the best khao soi of the trip.</p>
      <span class="dest-meta">Thailand · 8 days</span>
    </div>
    <div class="dest-card">
      <span class="dest-num">04</span>
      <h3>Skardu</h3>
      <p>Turquoise lakes and roads that make you renegotiate your idea of scenic.</p>
      <span class="dest-meta">Pakistan · 4 days</span>
    </div>
    <div class="dest-card">
      <span class="dest-num">05</span>
      <h3>Tbilisi</h3>
      <p>Sulphur baths, wine cellars, and a skyline that mixes centuries without apology.</p>
      <span class="dest-meta">Georgia · 5 days</span>
    </div>
    <div class="dest-card">
      <span class="dest-num">06</span>
      <h3>Zanzibar</h3>
      <p>Spice farms, stone-town alleys, and water the color you assume is edited.</p>
      <span class="dest-meta">Tanzania · 7 days</span>
    </div>
  </div>
</section>

<section class="blog" id="blog">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">From the journal</p>
      <h2>Recent entries.</h2>
    </div>
    <div class="post-list">
      <div class="post-row">
        <span class="post-date">Sep 2026</span>
        <span class="post-title"><a href="#">What nobody tells you about traveling alone in Hunza</a></span>
        <span class="post-tag">Pakistan</span>
      </div>
      <div class="post-row">
        <span class="post-date">Jul 2026</span>
        <span class="post-title"><a href="#">A slow week in Chiang Mai, mostly spent eating</a></span>
        <span class="post-tag">Thailand</span>
      </div>
      <div class="post-row">
        <span class="post-date">Apr 2026</span>
        <span class="post-title"><a href="#">Getting lost in Istanbul on purpose</a></span>
        <span class="post-tag">Turkey</span>
      </div>
      <div class="post-row">
        <span class="post-date">Jan 2026</span>
        <span class="post-title"><a href="#">Packing lighter: what I stopped bringing</a></span>
        <span class="post-tag">Guide</span>
      </div>
    </div>
  </div>
</section>

<section class="gallery" id="gallery">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">Gallery</p>
      <h2>A few frames from the road.</h2>
    </div>
    <div class="gallery-grid">
      <div class="g1"></div>
      <div class="g2"></div>
      <div class="g5"></div>
      <div class="g3"></div>
      <div class="g4"></div>
      <div class="g6"></div>
      <div class="g7"></div>
    </div>
    <p class="gallery-note">Placeholder tiles — replace these with your own photos before publishing.</p>
  </div>
</section>

<section class="contact" id="contact">
  <div class="wrap contact-grid">
    <div>
      <p class="eyebrow">Contact</p>
      <h2 style="margin-bottom:20px;color:var(--ink);">Say hello.</h2>
      <div class="contact-info">
        <p>Have a question about a place I've written about, or a recommendation to share? I read every message.</p>
        <p>Email: <a href="mailto:hello@wandernotes.com">hello@wandernotes.com</a></p>
        <p>Instagram: <a href="#">@wander.notes</a></p>
      </div>
    </div>
    <form id="contactForm">
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" name="name" required>
      </div>
      <div>
        <label for="email">Email</label>
        <input type="email" id="email" name="email" required>
      </div>
      <div>
        <label for="message">Message</label>
        <textarea id="message" name="message" required></textarea>
      </div>
      <button type="submit" class="btn" style="align-self:flex-start;">Send message</button>
    </form>
  </div>
</section>

<footer>
  <div class="wrap">
    <p>&copy; 2026 Wander Notes. Written on the road, edited at home.</p>
  </div>
</footer>

<script>
  const toggle = document.getElementById('navToggle');
  const links = document.getElementById('navLinks');
  toggle.addEventListener('click', () => links.classList.toggle('open'));
  links.querySelectorAll('a').forEach(a => a.addEventListener('click', () => links.classList.remove('open')));

  const form = document.getElementById('contactForm');
  form.addEventListener('submit', function(e){
    e.preventDefault();
    alert("Thanks for reaching out! This form is a static demo — connect it to a service like Formspree or Netlify Forms to receive real messages.");
    form.reset();
  });
</script>

</body>
</html>
