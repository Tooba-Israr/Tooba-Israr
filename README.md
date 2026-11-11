<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Tooba Israr | CSIT Student at NED University</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,500;0,700;1,500&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --butter: #FFF1A8;
    --butter-soft: #FFFAE0;
    --pink: #FFD1DC;
    --pink-soft: #FFEAF0;
    --rose: #E58BA6;
    --ink: #4A3340;
    --muted: #8A6F7B;
    --serif: "Fraunces", Georgia, "Times New Roman", serif;
    --sans: "Inter", "Segoe UI", Arial, sans-serif;
    --mono: "JetBrains Mono", "Courier New", monospace;
  }
  * { box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    margin: 0;
    padding: 48px 16px;
    font-family: var(--sans);
    color: var(--ink);
    line-height: 1.7;
    background:
      radial-gradient(circle at 15% 10%, var(--pink) 0, transparent 40%),
      radial-gradient(circle at 85% 90%, var(--butter) 0, transparent 45%),
      var(--butter-soft);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* soft drifting orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(40px);
    opacity: .55;
    z-index: 0;
    pointer-events: none;
    animation: drift 14s ease-in-out infinite alternate;
  }
  .orb.one { width: 260px; height: 260px; background: var(--pink); top: 8%; left: -60px; }
  .orb.two { width: 320px; height: 320px; background: var(--butter); bottom: 5%; right: -80px; animation-delay: -6s; }
  @keyframes drift { to { transform: translate(40px, -30px) scale(1.1); } }

  .page {
    position: relative;
    z-index: 1;
    max-width: 780px;
    margin: 0 auto;
    background: rgba(255, 255, 255, .72);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(229, 139, 166, .35);
    border-radius: 28px;
    box-shadow: 0 20px 50px rgba(229, 139, 166, .22);
    overflow: hidden;
    animation: rise .9s cubic-bezier(.2,.8,.2,1) both;
  }
  @keyframes rise { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: none; } }

  /* ---------- Hero ---------- */
  .hero {
    padding: 64px 40px 48px;
    text-align: center;
    background: linear-gradient(160deg, var(--butter) 0%, var(--pink-soft) 55%, var(--pink) 100%);
    position: relative;
  }
  .eyebrow {
    font-family: var(--mono);
    font-size: .78rem;
    letter-spacing: .22em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 14px;
    animation: fade 1s .3s both;
  }
  .hero h1 {
    font-family: var(--serif);
    font-size: clamp(2.4rem, 7vw, 3.6rem);
    font-weight: 700;
    line-height: 1.1;
    margin: 0;
    animation: fade 1s .5s both;
  }
  .hero h1 em {
    font-style: italic;
    font-weight: 500;
    color: var(--rose);
  }
  .tagline {
    margin: 16px auto 0;
    max-width: 460px;
    color: var(--muted);
    font-size: 1.05rem;
    animation: fade 1s .7s both;
  }
  .sparkle {
    position: absolute;
    color: var(--rose);
    font-size: 1.2rem;
    animation: twinkle 3s ease-in-out infinite;
  }
  .sparkle.s1 { top: 24px; left: 12%; }
  .sparkle.s2 { top: 60px; right: 14%; animation-delay: 1s; font-size: .9rem; }
  .sparkle.s3 { bottom: 28px; left: 20%; animation-delay: 2s; font-size: .8rem; }
  @keyframes twinkle { 0%,100% { opacity: .2; transform: scale(.7) rotate(0); } 50% { opacity: 1; transform: scale(1.2) rotate(20deg); } }
  @keyframes fade { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: none; } }

  /* ---------- Sections ---------- */
  section { padding: 36px 40px 8px; animation: fade .9s both; }
  section:nth-of-type(1) { animation-delay: .8s; }
  section:nth-of-type(2) { animation-delay: 1s; }
  section:nth-of-type(3) { animation-delay: 1.2s; }
  section:nth-of-type(4) { animation-delay: 1.4s; }

  h2 {
    font-family: var(--serif);
    font-size: 1.5rem;
    margin: 0 0 14px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  h2::after {
    content: "";
    flex: 1;
    height: 2px;
    background: linear-gradient(90deg, var(--pink), transparent);
    transform-origin: left;
    animation: grow 1.2s 1s both;
  }
  @keyframes grow { from { transform: scaleX(0); } to { transform: scaleX(1); } }

  p { margin: 0 0 12px; }

  .facts { list-style: none; padding: 0; margin: 0; display: grid; gap: 10px; }
  .facts li {
    padding: 12px 16px;
    background: var(--butter-soft);
    border-left: 4px solid var(--rose);
    border-radius: 0 12px 12px 0;
    transition: transform .25s, background .25s;
  }
  .facts li:hover { transform: translateX(6px); background: var(--pink-soft); }
  .facts b { font-weight: 600; }
  .facts span { display: block; font-size: .82rem; color: var(--muted); text-transform: uppercase; letter-spacing: .08em; }

  /* ---------- Code card ---------- */
  .code {
    background: #4A3340;
    color: #FFF1A8;
    border-radius: 16px;
    padding: 18px 22px;
    font-family: var(--mono);
    font-size: .9rem;
    line-height: 1.8;
    overflow-x: auto;
    box-shadow: 0 8px 20px rgba(74, 51, 64, .25);
  }
  .code .c { color: #C9A9B6; }
  .code .k { color: #FFD1DC; }
  .code .s { color: #FFF1A8; }
  .code .cursor {
    display: inline-block;
    width: 8px; height: 1em;
    background: var(--pink);
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* ---------- Focus chips ---------- */
  .chips { display: flex; flex-wrap: wrap; gap: 10px; }
  .chips span {
    padding: 7px 16px;
    border-radius: 999px;
    background: var(--pink-soft);
    border: 1px solid var(--pink);
    font-size: .9rem;
    font-weight: 500;
    transition: transform .25s, background .25s;
    animation: bob 5s ease-in-out infinite;
  }
  .chips span:nth-child(2) { animation-delay: .6s; }
  .chips span:nth-child(3) { animation-delay: 1.2s; }
  .chips span:nth-child(4) { animation-delay: 1.8s; }
  .chips span:hover { background: var(--butter); transform: translateY(-3px) scale(1.05); }
  @keyframes bob { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-3px); } }

  /* ---------- CTA ---------- */
  .cta { text-align: center; padding-bottom: 36px; }
  .btn {
    display: inline-block;
    margin-top: 6px;
    padding: 13px 30px;
    border-radius: 999px;
    background: var(--ink);
    color: var(--butter) !important;
    font-weight: 600;
    text-decoration: none;
    letter-spacing: .02em;
    transition: transform .25s, background .25s, box-shadow .25s;
    animation: glow 2.8s ease-in-out infinite;
  }
  .btn:hover { background: var(--rose); color: #fff !important; transform: translateY(-3px); }
  @keyframes glow { 0%,100% { box-shadow: 0 0 0 0 rgba(229,139,166,.55); } 50% { box-shadow: 0 0 0 12px rgba(229,139,166,0); } }

  footer {
    padding: 18px;
    text-align: center;
    font-size: .85rem;
    color: var(--muted);
    background: linear-gradient(90deg, var(--butter), var(--pink));
  }

  @media (max-width: 560px) {
    .hero { padding: 48px 22px 36px; }
    section { padding: 28px 22px 4px; }
  }
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; transition: none !important; }
  }

  /* ---------- Extra animation ---------- */
  .hero h1 em {
    background: linear-gradient(90deg, var(--rose), #F2B8C9, var(--rose));
    background-size: 200% auto;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
    animation: shimmer 4s linear infinite;
  }
  @keyframes shimmer { to { background-position: 200% center; } }

  .rotator {
    position: relative;
    display: inline-block;
    height: 1.7em;
    min-width: 12ch;
    vertical-align: bottom;
    overflow: hidden;
    font-family: var(--mono);
    font-size: .95rem;
    color: var(--rose);
    font-weight: 500;
  }
  .rotator span {
    position: absolute;
    left: 0; right: 0;
    opacity: 0;
    transform: translateY(100%);
    animation: swap 9s infinite;
  }
  .rotator span:nth-child(2) { animation-delay: 3s; }
  .rotator span:nth-child(3) { animation-delay: 6s; }
  @keyframes swap {
    0% { opacity: 0; transform: translateY(100%); }
    5%, 30% { opacity: 1; transform: translateY(0); }
    36%, 100% { opacity: 0; transform: translateY(-100%); }
  }
  .now { margin-top: 10px; font-size: .95rem; color: var(--muted); animation: fade 1s .9s both; }

  .code .line { display: block; opacity: 0; animation: lineIn .5s forwards; }
  .code .line:nth-child(1) { animation-delay: 1.6s; }
  .code .line:nth-child(2) { animation-delay: 2.1s; }
  .code .line:nth-child(3) { animation-delay: 2.6s; }
  .code .line:nth-child(4) { animation-delay: 3.1s; }
  .code .line:nth-child(5) { animation-delay: 3.6s; }
  .code .line:nth-child(6) { animation-delay: 4.1s; }
  .code .line:nth-child(7) { animation-delay: 4.6s; }
  @keyframes lineIn { from { opacity: 0; transform: translateX(-10px); } to { opacity: 1; transform: none; } }

  .btn { position: relative; overflow: hidden; }
  .btn::after {
    content: "";
    position: absolute;
    top: 0; left: -80%;
    width: 50%; height: 100%;
    background: linear-gradient(100deg, transparent, rgba(255,241,168,.55), transparent);
    transform: skewX(-20deg);
    animation: sweep 3.5s ease-in-out infinite;
  }
  @keyframes sweep { 0%, 55% { left: -80%; } 100% { left: 140%; } }

  .bubble {
    position: fixed;
    bottom: -30px;
    z-index: 0;
    pointer-events: none;
    color: var(--rose);
    opacity: 0;
    animation: rise-up linear infinite;
  }
  @keyframes rise-up {
    0% { transform: translateY(0) rotate(0); opacity: 0; }
    10% { opacity: .7; }
    90% { opacity: .5; }
    100% { transform: translateY(-110vh) rotate(180deg); opacity: 0; }
  }
  .facts li, .chips span { cursor: default; }
</style>
</head>
<body>
  <span class="bubble" style="left:6%;font-size:1rem;animation-duration:14s;animation-delay:0s">✦</span>
  <span class="bubble" style="left:18%;font-size:0.7rem;animation-duration:17s;animation-delay:3s">✦</span>
  <span class="bubble" style="left:30%;font-size:1.1rem;animation-duration:15s;animation-delay:6s">✦</span>
  <span class="bubble" style="left:44%;font-size:0.8rem;animation-duration:19s;animation-delay:2s">✦</span>
  <span class="bubble" style="left:58%;font-size:1rem;animation-duration:16s;animation-delay:8s">✦</span>
  <span class="bubble" style="left:70%;font-size:0.7rem;animation-duration:18s;animation-delay:4s">✦</span>
  <span class="bubble" style="left:82%;font-size:1.2rem;animation-duration:14s;animation-delay:7s">✦</span>
  <span class="bubble" style="left:93%;font-size:0.8rem;animation-duration:20s;animation-delay:1s">✦</span>
  <div class="orb one"></div>
  <div class="orb two"></div>

  <main class="page">
    <header class="hero">
      <span class="sparkle s1">✦</span>
      <span class="sparkle s2">✦</span>
      <span class="sparkle s3">✦</span>
      <p class="eyebrow">Computer Science &amp; IT · NED University</p>
      <h1>Tooba <em>Israr</em></h1>
      <p class="tagline">A curious student learning to write C, one small, tidy program at a time.</p>
      <p class="now">Right now I'm exploring
        <span class="rotator"><span>pointers &amp; memory</span><span>loops &amp; logic</span><span>clean, tidy code</span></span>
      </p>
    </header>

    <section>
      <h2>About</h2>
      <p>
        I'm a student at NED University of Engineering &amp; Technology, studying in the
        Department of Computer Science &amp; Information Technology (CSIT). This repository is
        my little corner for notes, exercises, and experiments as I learn how computers
        really think.
      </p>
      <ul class="facts">
        <li><span>University</span><b>NED University of Engineering &amp; Technology</b></li>
        <li><span>Department</span><b>CSIT</b></li>
        <li><span>Currently learning</span><b>The C programming language</b></li>
      </ul>
    </section>

    <section>
      <h2>Where it all begins</h2>
      <div class="code">
        <span class="line"><span class="c">/* every great program starts somewhere */</span></span>
        <span class="line"><span class="k">#include</span> <span class="s">&lt;stdio.h&gt;</span></span>
        <span class="line">&nbsp;</span>
        <span class="line"><span class="k">int</span> main(<span class="k">void</span>) {</span>
        <span class="line">&nbsp;&nbsp;printf(<span class="s">"Hello, world!\n"</span>);</span>
        <span class="line">&nbsp;&nbsp;<span class="k">return</span> 0;<span class="cursor"></span></span>
        <span class="line">}</span>
      </div>
    </section>

    <section>
      <h2>Currently exploring</h2>
      <div class="chips">
        <span>C Fundamentals</span>
        <span>Problem Solving</span>
        <span>Data Structures</span>
        <span>Git &amp; GitHub</span>
      </div>
    </section>

    <section class="cta">
      <h2>Say hello</h2>
      <p>Always happy to connect with fellow learners and curious minds.</p>
      <a class="btn" href="https://www.linkedin.com/in/tooba-israr-769079428?utm_source=share_via&amp;utm_content=profile&amp;utm_medium=member_ios" target="_blank" rel="noopener">Connect on LinkedIn</a>
    </section>

    <footer>Crafted with care by Tooba Israr</footer>
  </main>
</body>
</html>
