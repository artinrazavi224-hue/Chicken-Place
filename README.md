<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chicken Place — North York</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,600;9..144,700;9..144,900&family=Karla:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --charcoal: #1E1912;
    --charcoal-2: #2A2319;
    --charcoal-3: #362D20;
    --cream: #F7F0E2;
    --cream-2: #EFE5D0;
    --gold: #D8A03D;
    --gold-dim: #B9862F;
    --olive: #5C6B3D;
    --brick: #A13C24;
    --ink: #2B2116;
    --line: rgba(43,33,22,0.14);
    --line-dark: rgba(247,240,226,0.16);
  }

  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--cream);
    color:var(--ink);
    font-family:'Karla', sans-serif;
    font-size:17px;
    line-height:1.6;
  }
  h1,h2,h3,.display{
    font-family:'Fraunces', serif;
    font-weight:700;
    color:var(--ink);
    margin:0;
  }
  a{color:inherit;}
  img{max-width:100%;display:block;}
  .wrap{max-width:1160px;margin:0 auto;padding:0 32px;}

  @media (prefers-reduced-motion: reduce){
    *{animation:none !important; transition:none !important;}
  }

  /* ---------- NAV ---------- */
  .nav{
    position:sticky; top:0; z-index:50;
    background:var(--charcoal);
    border-bottom:1px solid var(--line-dark);
  }
  .nav .wrap{
    display:flex; align-items:center; justify-content:space-between;
    height:76px;
  }
  .nav-mark{
    font-family:'Fraunces', serif;
    font-weight:700; font-size:22px;
    color:var(--cream);
    letter-spacing:0.2px;
    display:flex; align-items:center; gap:10px;
  }
  .nav-mark svg{width:26px;height:26px;flex:none;}
  .nav-links{display:flex; gap:34px; list-style:none; margin:0; padding:0;}
  .nav-links a{
    color:var(--cream-2); text-decoration:none; font-size:15px; font-weight:500;
    position:relative; padding:4px 0;
  }
  .nav-links a::after{
    content:""; position:absolute; left:0; right:100%; bottom:-2px; height:1px;
    background:var(--gold); transition:right .25s ease;
  }
  .nav-links a:hover::after{ right:0; }
  .nav-call{
    background:var(--gold); color:var(--charcoal); text-decoration:none;
    font-weight:700; font-size:14.5px; padding:10px 18px; border-radius:2px;
    white-space:nowrap;
  }
  .nav-toggle{display:none;}

  /* ---------- HERO ---------- */
  .hero{
    background:var(--charcoal);
    color:var(--cream);
    position:relative;
    overflow:hidden;
    border-bottom:1px solid var(--line-dark);
  }
  .hero .wrap{
    display:grid; grid-template-columns:1.1fr 0.9fr; gap:40px;
    align-items:center;
    padding-top:76px; padding-bottom:76px;
  }
  .hero-eyebrow{
    color:var(--gold); font-weight:600; font-size:14.5px;
    display:flex; align-items:center; gap:10px; margin-bottom:22px;
    opacity:0; animation:rise .7s ease .1s forwards;
  }
  .hero-eyebrow .dot{width:6px;height:6px;background:var(--olive);border-radius:50%;}
  .hero h1{
    font-size:clamp(38px, 5vw, 60px);
    line-height:1.05;
    letter-spacing:-0.5px;
    opacity:0; animation:rise .7s ease .25s forwards;
  }
  .hero h1 em{
    font-style:italic; color:var(--gold); font-weight:600;
  }
  .hero p.lede{
    margin-top:22px; font-size:18px; color:var(--cream-2); max-width:46ch;
    opacity:0; animation:rise .7s ease .4s forwards;
  }
  .hero-actions{
    margin-top:34px; display:flex; gap:14px; flex-wrap:wrap;
    opacity:0; animation:rise .7s ease .55s forwards;
  }
  .btn{
    display:inline-flex; align-items:center; gap:9px;
    padding:14px 24px; border-radius:2px; text-decoration:none;
    font-weight:700; font-size:15px; border:1px solid transparent;
  }
  .btn-gold{background:var(--gold); color:var(--charcoal);}
  .btn-gold:hover{background:var(--cream);}
  .btn-outline{border-color:var(--line-dark); color:var(--cream);}
  .btn-outline:hover{border-color:var(--gold); color:var(--gold);}

  .hero-facts{
    margin-top:40px; display:flex; gap:28px; flex-wrap:wrap;
    opacity:0; animation:rise .7s ease .7s forwards;
  }
  .hero-fact{font-size:14px; color:var(--cream-2);}
  .hero-fact b{display:block; color:var(--cream); font-family:'Fraunces',serif; font-size:22px; font-weight:600;}

  @keyframes rise{ from{opacity:0; transform:translateY(14px);} to{opacity:1; transform:translateY(0);} }

  .hero-art{position:relative; width:100%; aspect-ratio:1/1;}

  /* ---------- ABOUT ---------- */
  .about{padding:96px 0; background:var(--cream);}
  .about .wrap{display:grid; grid-template-columns:0.85fr 1.15fr; gap:64px; align-items:start;}
  .section-tag{
    display:inline-flex; align-items:center; gap:8px;
    color:var(--olive); font-weight:700; font-size:14px; margin-bottom:18px;
  }
  .section-tag svg{width:16px;height:16px;}
  .about h2{font-size:clamp(28px,3.4vw,38px); line-height:1.15; max-width:14ch;}
  .about-copy p{max-width:56ch; color:var(--ink); opacity:0.9;}
  .about-stats{
    margin-top:36px; display:grid; grid-template-columns:repeat(3,1fr); gap:0;
    border-top:1px solid var(--line);
  }
  .about-stat{padding:20px 0; border-bottom:1px solid var(--line);}
  .about-stat:not(:last-child){border-right:1px solid var(--line); padding-right:16px;}
  .about-stat b{display:block; font-family:'Fraunces',serif; font-size:30px; font-weight:600; color:var(--brick);}
  .about-stat span{font-size:13.5px; color:var(--ink); opacity:0.7;}

  /* ---------- MENU ---------- */
  .menu{background:var(--charcoal); color:var(--cream); padding:100px 0;}
  .menu-head{display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:20px; margin-bottom:56px;}
  .menu-head h2{color:var(--cream); font-size:clamp(28px,3.4vw,40px); max-width:16ch;}
  .menu-head p{color:var(--cream-2); max-width:38ch; margin:10px 0 0; font-size:15.5px;}
  .menu-cols{display:grid; grid-template-columns:repeat(3,1fr); gap:48px;}
  .menu-cat h3{
    font-size:13px; letter-spacing:0.4px; text-transform:none;
    color:var(--gold); font-family:'Karla',sans-serif; font-weight:700;
    display:flex; align-items:center; gap:9px; margin-bottom:18px;
    padding-bottom:12px; border-bottom:1px solid var(--line-dark);
  }
  .menu-cat h3 svg{width:17px;height:17px;flex:none;}
  .menu-item{
    display:flex; justify-content:space-between; align-items:baseline; gap:12px;
    padding:11px 0; border-bottom:1px dashed var(--line-dark);
  }
  .menu-item:last-child{border-bottom:none;}
  .menu-item .name{font-size:15.5px; color:var(--cream);}
  .menu-item .tag{font-size:11.5px; color:var(--gold-dim); border:1px solid var(--gold-dim); padding:2px 7px; border-radius:20px; white-space:nowrap;}
  .menu-note{margin-top:44px; font-size:14.5px; color:var(--cream-2); border-top:1px solid var(--line-dark); padding-top:24px;}
  .menu-note b{color:var(--gold);}

  /* ---------- REVIEWS ---------- */
  .reviews{padding:100px 0; background:var(--cream-2);}
  .reviews-head{display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:24px; margin-bottom:52px;}
  .rating-badge{
    display:flex; align-items:center; gap:16px;
    background:var(--charcoal); color:var(--cream); padding:16px 22px; border-radius:3px;
  }
  .rating-badge .score{font-family:'Fraunces',serif; font-size:34px; font-weight:700; color:var(--gold); line-height:1;}
  .rating-badge .meta{font-size:13px; color:var(--cream-2); line-height:1.4;}
  .rating-badge .stars{color:var(--gold); font-size:13px; letter-spacing:2px;}
  .review-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:26px;}
  .review-card{
    background:var(--cream); border:1px solid var(--line); border-radius:3px; padding:28px;
    display:flex; flex-direction:column; gap:18px; height:100%;
  }
  .review-card .quote{font-family:'Fraunces',serif; font-size:18px; line-height:1.4; color:var(--ink);}
  .review-card .who{font-size:13.5px; color:var(--ink); opacity:0.65; margin-top:auto;}

  /* ---------- VISIT ---------- */
  .visit{padding:100px 0 110px; background:var(--cream);}
  .visit .wrap{display:grid; grid-template-columns:1fr 1fr; gap:64px;}
  .visit h2{font-size:clamp(28px,3.4vw,38px); max-width:16ch; margin-bottom:30px;}
  .hours-table{width:100%; border-collapse:collapse;}
  .hours-table tr{border-bottom:1px solid var(--line);}
  .hours-table tr:last-child{border-bottom:none;}
  .hours-table td{padding:12px 0; font-size:15px;}
  .hours-table td:first-child{color:var(--ink); font-weight:600;}
  .hours-table td:last-child{text-align:right; color:var(--ink); opacity:0.75;}
  .hours-table tr.closed td:last-child{color:var(--brick); opacity:1;}
  .hours-today{
    display:inline-flex; align-items:center; gap:8px; margin-top:24px;
    font-size:14px; color:var(--olive); font-weight:600;
  }
  .hours-today .dot{width:7px;height:7px;border-radius:50%;background:var(--olive);}

  .visit-card{background:var(--charcoal); color:var(--cream); border-radius:3px; padding:38px;}
  .visit-card .line{display:flex; gap:14px; padding:16px 0; border-bottom:1px solid var(--line-dark);}
  .visit-card .line:last-of-type{border-bottom:none;}
  .visit-card .line svg{width:20px;height:20px;flex:none; color:var(--gold); margin-top:2px;}
  .visit-card .line .lbl{font-size:12.5px; color:var(--cream-2); margin-bottom:3px;}
  .visit-card .line .val{font-size:15.5px; color:var(--cream);}
  .visit-card .line a{text-decoration:none; color:var(--cream);}
  .visit-card .line a:hover{color:var(--gold);}
  .visit-card .btn{margin-top:26px; width:100%; justify-content:center;}

  /* ---------- FOOTER ---------- */
  footer{background:var(--charcoal); border-top:1px solid var(--line-dark); padding:32px 0;}
  footer .wrap{display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:14px;}
  footer .nav-mark{color:var(--cream-2); font-size:16px;}
  footer .fine{font-size:13px; color:var(--cream-2); opacity:0.6;}

  /* ---------- RESPONSIVE ---------- */
  @media (max-width: 880px){
    .nav-links{display:none;}
    .hero .wrap{grid-template-columns:1fr; padding-top:52px; padding-bottom:52px;}
    .hero-art{max-width:280px; margin:0 auto;}
    .about .wrap{grid-template-columns:1fr; gap:36px;}
    .menu-cols{grid-template-columns:1fr; gap:36px;}
    .review-grid{grid-template-columns:1fr;}
    .visit .wrap{grid-template-columns:1fr; gap:44px;}
    .reviews-head{flex-direction:column; align-items:flex-start;}
    .wrap{padding:0 22px;}
  }
</style>
</head>
<body>

<nav class="nav">
  <div class="wrap">
    <div class="nav-mark">
      <svg viewBox="0 0 24 24" fill="none"><path d="M12 3c2.8 0 4.6 2 4.9 4.3.2 1.5-.2 2.4-.9 3.5-.6 1-1 1.7-1 3 0 2.6 1.8 3.2 1.8 5.2 0 1.7-2.2 3-4.8 3s-4.8-1.3-4.8-3c0-2 1.8-2.6 1.8-5.2 0-1.3-.4-2-1-3-.7-1.1-1.1-2-1-3.5C7.4 5 9.2 3 12 3Z" stroke="#D8A03D" stroke-width="1.4"/></svg>
      Chicken Place
    </div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#menu">Menu</a></li>
      <li><a href="#reviews">Reviews</a></li>
      <li><a href="#visit">Visit</a></li>
    </ul>
    <a class="nav-call" href="tel:+14166305000">Call (416) 630-5000</a>
  </div>
</nav>

<header class="hero">
  <div class="wrap">
    <div>
      <div class="hero-eyebrow"><span class="dot"></span>North York, Ontario · Family-run</div>
      <h1>Rotisserie chicken, <em>done properly.</em></h1>
      <p class="lede">A small, family-owned kitchen on Champagne Drive serving slow-roasted chicken, chargrilled souvlaki, and salads made from scratch — every single day it's open.</p>
      <div class="hero-actions">
        <a class="btn btn-gold" href="#menu">See the menu</a>
        <a class="btn btn-outline" href="https://www.google.com/maps/search/?api=query&query=586+Champagne+Dr+North+York+ON+M3J+2C6" target="_blank" rel="noopener">Get directions</a>
      </div>
      <div class="hero-facts">
        <div class="hero-fact"><b>4.9 / 5</b>from 1,052 reviews</div>
        <div class="hero-fact"><b>$10–20</b>per person</div>
        <div class="hero-fact"><b>Dine-in & takeout</b>no delivery markup</div>
      </div>
    </div>
    <div class="hero-art" aria-hidden="true">
      <svg viewBox="0 0 340 340" width="100%" height="100%">
        <circle cx="170" cy="170" r="160" fill="#2A2319"/>
        <circle cx="170" cy="170" r="132" fill="none" stroke="#4A3F2C" stroke-width="1.5" stroke-dasharray="3 6"/>
        <!-- plate -->
        <ellipse cx="170" cy="195" rx="118" ry="88" fill="#F7F0E2"/>
        <ellipse cx="170" cy="195" rx="96" ry="70" fill="none" stroke="#D8CBAE" stroke-width="2"/>
        <!-- chicken pieces -->
        <path d="M120 185c-14-8-18-24-8-34 8-8 22-8 28 2 4-14 22-18 32-8 10 10 4 26-10 34-14 8-30 12-42 6Z" fill="#D8A03D"/>
        <path d="M120 185c-6 8-4 18 4 22 10 4 22-2 24-12" fill="none" stroke="#B9862F" stroke-width="2"/>
        <path d="M210 180c14-6 26 2 26 14 0 10-10 18-24 16-10-14-8-24-2-30Z" fill="#C98F31"/>
        <!-- lemon -->
        <circle cx="222" cy="222" r="16" fill="#D8A03D" opacity="0.9"/>
        <path d="M222 208v28M209 222h26" stroke="#F7F0E2" stroke-width="1.2" opacity="0.7"/>
        <!-- herbs -->
        <path d="M108 215c6-10 18-14 26-10-4 10-16 16-26 10Z" fill="#5C6B3D"/>
        <path d="M118 222c4-10 14-16 24-14-2 10-14 18-24 14Z" fill="#6E7F49"/>
        <!-- skewer accent -->
        <line x1="60" y1="80" x2="130" y2="120" stroke="#A13C24" stroke-width="3" stroke-linecap="round"/>
        <circle cx="66" cy="84" r="6" fill="#A13C24"/>
        <circle cx="84" cy="95" r="6" fill="#5C6B3D"/>
        <circle cx="102" cy="106" r="6" fill="#D8A03D"/>
      </svg>
    </div>
  </div>
</header>

<section class="about" id="about">
  <div class="wrap">
    <div>
      <div class="section-tag">
        <svg viewBox="0 0 24 24" fill="none"><path d="M4 12h16M4 6h16M4 18h10" stroke="#5C6B3D" stroke-width="1.6" stroke-linecap="round"/></svg>
        About us
      </div>
      <h2>Made with love, since we opened the doors.</h2>
    </div>
    <div class="about-copy">
      <p>Chicken Place is a small, cozy, family-owned spot tucked into North York — the kind of place where the same hands that season the chicken are the ones who bring it to your table. Regulars know it for warm, welcoming service and food that tastes like someone actually cared while making it.</p>
      <p>The menu leans into honest, Mediterranean-style comfort food: whole roasted chickens, chargrilled souvlaki and kebab, hand-formed falafel, and salads and sides made fresh in-house. Everything's built for dine-in or takeout, at a price that still feels fair.</p>
      <div class="about-stats">
        <div class="about-stat"><b>4.9</b><span>average rating</span></div>
        <div class="about-stat"><b>1,052</b><span>Google reviews</span></div>
        <div class="about-stat"><b>$10–20</b><span>per person</span></div>
      </div>
    </div>
  </div>
</section>

<section class="menu" id="menu">
  <div class="wrap">
    <div class="menu-head">
      <h2>What's on the board</h2>
      <p>A working sample of the menu — everything's roasted, grilled, or made fresh to order. $10–20 per person on average.</p>
    </div>
    <div class="menu-cols">
      <div class="menu-cat">
        <h3><svg viewBox="0 0 24 24" fill="none"><path d="M4 12h16M9 7l-5 5 5 5M15 7l5 5-5 5" stroke="#D8A03D" stroke-width="1.6"/></svg>Sandwiches & wraps</h3>
        <div class="menu-item"><span class="name">Chicken Place Sandwich</span><span class="tag">Popular</span></div>
        <div class="menu-item"><span class="name">Chicken Souvlaki Sandwich</span></div>
        <div class="menu-item"><span class="name">Chicken Sandwich with Lettuce & Tomato</span></div>
        <div class="menu-item"><span class="name">Chicken Garlic Mayo</span></div>
      </div>
      <div class="menu-cat">
        <h3><svg viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="8" stroke="#D8A03D" stroke-width="1.6"/><path d="M12 4v16" stroke="#D8A03D" stroke-width="1.6"/></svg>Platters & grill</h3>
        <div class="menu-item"><span class="name">BBQ Chicken</span><span class="tag">Popular</span></div>
        <div class="menu-item"><span class="name">Grilled Chicken</span></div>
        <div class="menu-item"><span class="name">Chicken Kebab</span></div>
        <div class="menu-item"><span class="name">Chicken Souvlaki Platter</span></div>
        <div class="menu-item"><span class="name">Chicken Fingers and Fries</span></div>
      </div>
      <div class="menu-cat">
        <h3><svg viewBox="0 0 24 24" fill="none"><path d="M4 10c2-4 14-4 16 0-1 6-4 10-8 10s-7-4-8-10Z" stroke="#D8A03D" stroke-width="1.6"/></svg>Sides & salads</h3>
        <div class="menu-item"><span class="name">Chicken Greek Salad</span><span class="tag">Popular</span></div>
        <div class="menu-item"><span class="name">Falafel Plate</span><span class="tag">Popular</span></div>
        <div class="menu-item"><span class="name">Lentil Soup</span><span class="tag">Popular</span></div>
        <div class="menu-item"><span class="name">Babaganoush</span></div>
        <div class="menu-item"><span class="name">Fries (Small)</span></div>
      </div>
    </div>
    <p class="menu-note"><b>Note —</b> menu items and availability change from time to time. Call (416) 630-5000 to confirm before you head over.</p>
  </div>
</section>

<section class="reviews" id="reviews">
  <div class="wrap">
    <div class="reviews-head">
      <div>
        <div class="section-tag"><svg viewBox="0 0 24 24" fill="none"><path d="M12 3l2.6 5.6 6.1.7-4.5 4.2 1.2 6-5.4-3-5.4 3 1.2-6-4.5-4.2 6.1-.7L12 3Z" stroke="#5C6B3D" stroke-width="1.4"/></svg>Reviews</div>
        <h2 style="font-size:clamp(28px,3.4vw,38px); max-width:14ch;">What regulars keep saying</h2>
      </div>
      <div class="rating-badge">
        <div class="score">4.9</div>
        <div class="meta"><div class="stars">★★★★★</div>1,052 Google reviews</div>
      </div>
    </div>
    <div class="review-grid">
      <div class="review-card">
        <div class="quote">"Food is always delicious and tasty, friendly staff and excellent service."</div>
        <div class="who">Google review</div>
      </div>
      <div class="review-card">
        <div class="quote">"Great sandwiches at a price cheaper than Subway — hard to beat that."</div>
        <div class="who">Google review</div>
      </div>
      <div class="review-card">
        <div class="quote">"Small and cozy, family-owned — the food is made with love and full of flavor. Service is warm and welcoming."</div>
        <div class="who">Oleg Vasilkov, Local Guide</div>
      </div>
    </div>
  </div>
</section>

<section class="visit" id="visit">
  <div class="wrap">
    <div>
      <h2>Hours</h2>
      <table class="hours-table">
        <tr class="closed"><td>Sunday</td><td>Closed</td></tr>
        <tr><td>Monday</td><td>11 a.m. – 4 p.m.</td></tr>
        <tr><td>Tuesday</td><td>11 a.m. – 4 p.m.</td></tr>
        <tr><td>Wednesday</td><td>11 a.m. – 4 p.m.</td></tr>
        <tr><td>Thursday</td><td>11 a.m. – 4 p.m.</td></tr>
        <tr><td>Friday</td><td>11 a.m. – 4 p.m.</td></tr>
        <tr class="closed"><td>Saturday</td><td>Closed</td></tr>
      </table>
      <div class="hours-today"><span class="dot"></span>Open Monday–Friday, 11 a.m. to 4 p.m.</div>
    </div>
    <div class="visit-card">
      <div class="line">
        <svg viewBox="0 0 24 24" fill="none"><path d="M12 22s7-7.4 7-13a7 7 0 1 0-14 0c0 5.6 7 13 7 13Z" stroke="currentColor" stroke-width="1.5"/><circle cx="12" cy="9" r="2.5" stroke="currentColor" stroke-width="1.5"/></svg>
        <div><div class="lbl">Address</div><div class="val"><a href="https://www.google.com/maps/search/?api=query&query=586+Champagne+Dr+North+York+ON+M3J+2C6" target="_blank" rel="noopener">586 Champagne Dr, North York, ON M3J 2C6</a></div></div>
      </div>
      <div class="line">
        <svg viewBox="0 0 24 24" fill="none"><path d="M4 5c0-1 1-2 2-2h2l2 5-2 1c1 3 3 5 6 6l1-2 5 2v2c0 1-1 2-2 2C10 19 4 13 4 5Z" stroke="currentColor" stroke-width="1.5"/></svg>
        <div><div class="lbl">Phone</div><div class="val"><a href="tel:+14166305000">(416) 630-5000</a></div></div>
      </div>
      <div class="line">
        <svg viewBox="0 0 24 24" fill="none"><rect x="3" y="4" width="18" height="17" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3 9h18M8 2v4M16 2v4" stroke="currentColor" stroke-width="1.5"/></svg>
        <div><div class="lbl">Service</div><div class="val">Dine-in & takeout</div></div>
      </div>
      <a class="btn btn-gold" href="https://www.google.com/maps/search/?api=query&query=586+Champagne+Dr+North+York+ON+M3J+2C6" target="_blank" rel="noopener">Get directions</a>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="nav-mark">Chicken Place · North York</div>
    <div class="fine">586 Champagne Dr, North York, ON M3J 2C6 · (416) 630-5000</div>
  </div>
</footer>

</body>
</html>
