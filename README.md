# E-Commerce-BD
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mobaail Hub</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    :root {
      --bg1: #0b0618;
      --bg2: #180d2f;
      --card: rgba(255, 255, 255, 0.08);
      --card2: rgba(255, 255, 255, 0.05);
      --purple: #8b5cf6;
      --purple2: #a855f7;
      --pink: #ec4899;
      --text: #f5f3ff;
      --muted: #d8d1ff;
      --green: #22c55e;
      --yellow: #fbbf24;
      --danger: #f43f5e;
      --line: rgba(255,255,255,0.1);
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background:
        radial-gradient(circle at top left, rgba(168,85,247,0.35), transparent 30%),
        radial-gradient(circle at bottom right, rgba(236,72,153,0.20), transparent 25%),
        linear-gradient(135deg, var(--bg1), var(--bg2));
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      width: min(1200px, calc(100% - 32px));
      margin: 0 auto;
    }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: rgba(11, 6, 24, 0.5);
      border-bottom: 1px solid var(--line);
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      min-height: 76px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 700;
      letter-spacing: 1px;
    }

    .logo-badge {
      width: 42px;
      height: 42px;
      border-radius: 14px;
      background: linear-gradient(135deg, var(--purple), var(--pink));
      display: grid;
      place-items: center;
      box-shadow: 0 10px 20px rgba(168,85,247,0.45);
      font-size: 20px;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
      color: var(--muted);
      font-size: 0.96rem;
    }

    .nav-links a:hover {
      color: white;
    }

    .nav-btn {
      padding: 12px 22px;
      border-radius: 999px;
      background: linear-gradient(135deg, var(--purple), var(--pink));
      color: white;
      font-weight: 700;
      box-shadow: 0 15px 30px rgba(168,85,247,0.35);
      transition: transform 0.2s ease;
    }

    .nav-btn:hover {
      transform: translateY(-2px);
    }

    .hero {
      padding: 96px 0 50px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 38px;
      align-items: center;
    }

    .hero h1 {
      font-size: clamp(2.4rem, 5vw, 5rem);
      line-height: 1.05;
      letter-spacing: -0.05em;
      margin-bottom: 18px;
    }

    .gradient-text {
      background: linear-gradient(90deg, #d8b4fe, #f9a8d4, #a5b4fc);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero p {
      color: var(--muted);
      font-size: 1.05rem;
      max-width: 620px;
      margin-bottom: 30px;
    }

    .cta-row {
      display: flex;
      align-items: center;
      gap: 18px;
      flex-wrap: wrap;
    }

    .primary-btn, .secondary-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 14px 24px;
      border-radius: 14px;
      font-weight: 700;
      transition: 0.2s ease;
    }

    .primary-btn {
      background: linear-gradient(135deg, var(--purple), var(--pink));
      box-shadow: 0 16px 30px rgba(168,85,247,0.35);
    }

    .secondary-btn {
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.14);
    }

    .primary-btn:hover, .secondary-btn:hover {
      transform: translateY(-2px);
    }

    .stats {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      margin-top: 34px;
    }

    .stat-box {
      min-width: 120px;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--line);
      border-radius: 16px;
      padding: 16px 18px;
    }

    .stat-box strong {
      display: block;
      font-size: 1.5rem;
      color: white;
      margin-bottom: 4px;
    }

    .stat-box span {
      color: var(--muted);
      font-size: 0.85rem;
    }

    .hero-visual {
      position: relative;
      min-height: 520px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .device {
      position: relative;
      width: min(88%, 430px);
      min-height: 500px;
      padding: 18px;
      border-radius: 32px;
      background: linear-gradient(180deg, rgba(255,255,255,0.08), rgba(255,255,255,0.02));
      border: 1px solid rgba(255,255,255,0.11);
      box-shadow: 0 30px 80px rgba(7, 2, 15, 0.7);
    }

    .screen {
      background: linear-gradient(180deg, rgba(24,13,47,0.9), rgba(11,6,24,0.92));
      border-radius: 24px;
      height: 100%;
      padding: 20px;
      border: 1px solid rgba(255,255,255,0.08);
    }

    .screen-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 18px;
    }

    .dots {
      display: flex;
      gap: 8px;
    }

    .dots span {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      display: block;
    }

    .dots span:nth-child(1) { background: #f87171; }
    .dots span:nth-child(2) { background: #fbbf24; }
    .dots span:nth-child(3) { background: #34d399; }

    .mini-pill {
      padding: 7px 12px;
      border-radius: 999px;
      font-size: 0.72rem;
      color: white;
      background: rgba(168,85,247,0.18);
      border: 1px solid rgba(168,85,247,0.35);
    }

    .app-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(120px, 1fr));
      gap: 14px;
      margin-top: 18px;
    }

    .mini-app {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.09);
      border-radius: 18px;
      padding: 18px 14px;
      display: flex;
      align-items: center;
      gap: 12px;
      color: white;
      min-height: 78px;
    }

    .mini-app .icon {
      width: 38px;
      height: 38px;
      border-radius: 12px;
      display: grid;
      place-items: center;
      font-size: 18px;
      box-shadow: inset 0 0 0 1px rgba(255,255,255,0.08);
    }

    .fb { background: linear-gradient(135deg, #3b82f6, #2563eb); }
    .yt { background: linear-gradient(135deg, #f43f5e, #ef4444); }
    .ig { background: linear-gradient(135deg, #f59e0b, #ec4899, #8b5cf6); }
    .wa { background: linear-gradient(135deg, #22c55e, #16a34a); }
    .wb { background: linear-gradient(135deg, #10b981, #059669); }
    .ff { background: linear-gradient(135deg, #f97316, #facc15); }

    .profile-card {
      margin-top: 20px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 18px;
      padding: 16px;
    }

    .profile-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 12px;
    }

    .avatar {
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: linear-gradient(135deg, #a855f7, #ec4899);
      display: grid;
      place-items: center;
      font-weight: 700;
    }

    .live-dot {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      color: #a7f3d0;
      font-size: 0.8rem;
    }

    .live-dot::before {
      content: "";
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #22c55e;
      box-shadow: 0 0 0 5px rgba(34,197,94,0.18);
    }

    .chart-bar {
      height: 80px;
      border-radius: 18px;
      background: linear-gradient(180deg, rgba(168,85,247,0.18), rgba(168,85,247,0.04));
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: end;
      padding: 10px;
      gap: 8px;
    }

    .chart-bar span {
      flex: 1;
      border-radius: 12px 12px 0 0;
      background: linear-gradient(180deg, #a78bfa, #ec4899);
      opacity: 0.9;
    }

    .section {
      padding: 70px 0;
    }

    .section-head {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 20px;
      margin-bottom: 28px;
    }

    .section-head h2 {
      font-size: clamp(2rem, 3vw, 3rem);
      letter-spacing: -0.05em;
    }

    .section-head p {
      color: var(--muted);
      max-width: 580px;
    }

    .apps-grid {
      display: grid;
      grid-template-columns: repeat(5, minmax(180px, 1fr));
      gap: 20px;
    }

    .app-card {
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--line);
      border-radius: 24px;
      padding: 22px 18px;
      min-height: 220px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: transform 0.2s ease, border-color 0.2s ease;
    }

    .app-card:hover {
      transform: translateY(-6px);
      border-color: rgba(168,85,247,0.7);
    }

    .app-icon {
      width: 60px;
      height: 60px;
      border-radius: 18px;
      display: grid;
      place-items: center;
      font-size: 28px;
      margin-bottom: 18px;
      box-shadow: 0 12px 16px rgba(0,0,0,0.18);
    }

    .app-card h3 {
      margin-bottom: 8px;
      font-size: 1.2rem;
    }

    .app-card p {
      color: var(--muted);
      font-size: 0.92rem;
    }

    .tag {
      display: inline-flex;
      align-items: center;
      width: fit-content;
      background: rgba(168,85,247,0.12);
      border: 1px solid rgba(168,85,247,0.25);
      color: #ddd6fe;
      padding: 7px 10px;
      border-radius: 999px;
      font-size: 0.76rem;
      font-weight: 700;
      margin-top: 18px;
    }

    .feature-wrap {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 28px;
      align-items: center;
    }

    .feature-box {
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--line);
      border-radius: 28px;
      padding: 26px;
    }

    .feature-box h3 {
      font-size: clamp(1.8rem, 2vw, 2.6rem);
      margin-bottom: 14px;
    }

    .feature-box p {
      color: var(--muted);
      margin-bottom: 22px;
    }

    .list {
      list-style: none;
      display: grid;
      gap: 16px;
    }

    .list li {
      display: flex;
      align-items: center;
      gap: 12px;
      color: white;
    }

    .check {
      width: 26px;
      height: 26px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--purple), var(--pink));
      font-size: 0.82rem;
      font-weight: 700;
    }

    .game-panel {
      border-radius: 28px;
      padding: 22px;
      background:
        linear-gradient(180deg, rgba(249,115,22,0.18), rgba(168,85,247,0.12)),
        rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.12);
      min-height: 420px;
      position: relative;
      overflow: hidden;
    }

    .game-bg {
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at top right, rgba(251,191,36,0.30), transparent 30%);
    }

    .game-inner {
      position: relative;
      z-index: 1;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .game-head {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
    }

    .game-head .badges {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .badge {
      padding: 6px 10px;
      border-radius: 999px;
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.08);
      font-size: 0.76rem;
      color: var(--muted);
    }

    .fire-box {
      margin-top: 36px;
      display: grid;
      place-items: center;
      min-height: 200px;
      background: rgba(11, 6, 24, 0.18);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 24px;
      font-size: 6rem;
      text-shadow: 0 0 20px rgba(251,191,36,0.7);
    }

    .game-stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      margin-top: 18px;
    }

    .game-stat {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 16px;
      padding: 14px 12px;
      text-align: center;
    }

    .game-stat strong {
      display: block;
      font-size: 1.3rem;
      margin-bottom: 4px;
    }

    .cta-section {
      padding: 80px 0 100px;
    }

    .cta-card {
      background: linear-gradient(135deg, rgba(168,85,247,0.22), rgba(236,72,153,0.12));
      border: 1px solid rgba(168,85,247,0.32);
      border-radius: 32px;
      padding: 36px 28px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 18px;
      flex-wrap: wrap;
    }

    .cta-card h3 {
      font-size: clamp(1.8rem, 3vw, 3rem);
      margin-bottom: 8px;
      letter-spacing: -0.05em;
    }

    .cta-card p {
      color: var(--muted);
    }

    footer {
      border-top: 1px solid var(--line);
      padding: 28px 0 56px;
      color: var(--muted);
    }

    .footer-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      flex-wrap: wrap;
    }

    @media (max-width: 980px) {
      .hero-grid, .feature-wrap {
        grid-template-columns: 1fr;
      }

      .apps-grid {
        grid-template-columns: repeat(2, minmax(180px, 1fr));
      }
    }

    @media (max-width: 700px) {
      .nav-links {
        display: none;
      }

      .apps-grid {
        grid-template-columns: 1fr;
      }

      .game-stats {
        grid-template-columns: 1fr;
      }

      .cta-card {
        align-items: flex-start;
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <div class="topbar">
    <div class="container">
      <nav>
        <div class="logo">
          <div class="logo-badge">M</div>
          <span>Mobaail Hub</span>
        </div>

        <div class="nav-links">
          <a href="#apps">Apps</a>
          <a href="#features">Features</a>
          <a href="#games">Games</a>
          <a href="#contact">Contact</a>
        </div>

        <a href="#apps" class="nav-btn">Launch</a>
      </nav>
    </div>
  </div>

  <header class="hero">
    <div class="container hero-grid">
      <div>
        <h1>
          Connect your world in a
          <span class="gradient-text">purple universe</span>
        </h1>
        <p>
          Fast social access, entertainment, business messaging, and fearless gaming — all powered in one stylish digital hub.
        </p>

        <div class="cta-row">
          <a href="#apps" class="primary-btn">Explore Apps</a>
          <a href="#games" class="secondary-btn">Play Free Fire</a>
        </div>

        <div class="stats">
          <div class="stat-box">
            <strong>5K+</strong>
            <span>Daily Users</span>
          </div>
          <div class="stat-box">
            <strong>12+</strong>
            <span>Connected Apps</span>
          </div>
          <div class="stat-box">
            <strong>24/7</strong>
            <span>Always Active</span>
          </div>
        </div>
      </div>

      <div class="hero-visual">
        <div class="device">
          <div class="screen">
            <div class="screen-top">
              <div class="dots">
                <span></span>
                <span></span>
                <span></span>
              </div>
              <div class="mini-pill">Live Feed</div>
            </div>

            <div class="app-grid">
              <div class="mini-app">
                <div class="icon fb">f</div>
                <div>Facebook</div>
              </div>

              <div class="mini-app">
                <div class="icon yt">▶</div>
                <div>YouTube</div>
              </div>

              <div class="mini-app">
                <div class="icon ig">◎</div>
                <div>Instagram</div>
              </div>

              <div class="mini-app">
                <div class="icon wa">W</div>
                <div>WhatsApp</div>
              </div>

              <div class="mini-app">
                <div class="icon wb">B</div>
                <div>Business</div>
              </div>

              <div class="mini-app">
                <div class="icon ff">F</div>
                <div>Free Fire</div>
              </div>
            </div>

            <div class="profile-card">
              <div class="profile-row">
                <div style="display:flex; align-items:center; gap:12px;">
                  <div class="avatar">M</div>
                  <div>
                    <strong>Mr. Mobaail</strong><br>
                    <small style="color: var(--muted);">Gaming Network</small>
                  </div>
                </div>

                <div class="live-dot">Live</div>
              </div>

              <div class="chart-bar">
                <span style="height: 35%;"></span>
                <span style="height: 55%;"></span>
                <span style="height: 78%;"></span>
                <span style="height: 60%;"></span>
                <span style="height: 90%;"></span>
                <span style="height: 72%;"></span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>

  <section class="section" id="apps">
    <div class="container">
      <div class="section-head">
        <h2>Popular Social Apps</h2>
        <p>Everything you love in one smart place — community, videos, chats, business growth, and fun.</p>
      </div>

      <div class="apps-grid">
        <div class="app-card">
          <div>
            <div class="app-icon fb">f</div>
            <h3>Facebook</h3>
            <p>Connect with friends, groups, pages, and trending content.</p>
          </div>
          <div class="tag">Social</div>
        </div>

        <div class="app-card">
          <div>
            <div class="app-icon yt">▶</div>
            <h3>YouTube</h3>
            <p>Watch creators, shorts, tutorials, and live entertainment.</p>
          </div>
          <div class="tag">Video</div>
        </div>

        <div class="app-card">
          <div>
            <div class="app-icon ig">◎</div>
            <h3>Instagram</h3>
            <p>Share photos, reels, stories, and build your audience.</p>
          </div>
          <div class="tag">Creative</div>
        </div>

        <div class="app-card">
          <div>
            <div class="app-icon wa">W</div>
            <h3>WhatsApp</h3>
            <p>Fast personal messaging, voice, and video communication.</p>
          </div>
          <div class="tag">Chat</div>
        </div>

        <div class="app-card">
          <div>
            <div class="app-icon wb">B</div>
            <h3>Business</h3>
            <p>Promote your store, connect customers, and grow fast.</p>
          </div>
          <div class="tag">Brand</div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="features">
    <div class="container feature-wrap">
      <div class="feature-box">
        <h3>Built for connection, growth, and fun.</h3>
        <p>
          This platform is designed to keep your audience, your community, and your entertainment in a single powerful digital experience.
        </p>

        <ul class="list">
          <li><span class="check">✓</span> One-click access to all major social apps</li>
          <li><span class="check">✓</span> Simple and modern dashboard layout</li>
          <li><span class="check">✓</span> Optimized for mobile and desktop screens</li>
          <li><span class="check">✓</span> Premium purple design with vibrant glow effects</li>
        </ul>
      </div>

      <div class="game-panel" id="games">
        <div class="game-bg"></div>
        <div class="game-inner">
          <div class="game-head">
            <div>
              <h3 style="font-size: 1.7rem; margin-bottom: 8px;">Free Fire Arena</h3>
            </div>
            <div class="badges">
              <span class="badge">Battle</span>
              <span class="badge">Survival</span>
            </div>
          </div>

          <div class="fire-box">🔥</div>

          <div class="game-stats">
            <div class="game-stat">
              <strong>120+</strong>
              <span>Players</span>
            </div>
            <div class="game-stat">
              <strong>4.9</strong>
              <span>Rating</span>
            </div>
            <div class="game-stat">
              <strong>Live</strong>
              <span>Match</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="cta-section" id="contact">
    <div class="container">
      <div class="cta-card">
        <div>
          <h3>Launch your social experience.</h3>
          <p>Modern purple theme with entertainment, messaging, and gaming.</p>
        </div>

        <a href="#" class="primary-btn">Get Started</a>
      </div>
    </div>
  </section>

  <footer>
    <div class="container footer-row">
      <div class="logo">
        <div class="logo-badge">M</div>
        <span>Mobaail Hub</span>
      </div>
      <div>© 2026 Mobaail Hub. All rights reserved.</div>
    </div>
  </footer>
</body>
</html>
