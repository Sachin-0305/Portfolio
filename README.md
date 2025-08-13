# Ex01 Portfolio
## Date: 13/08/2025

## AIM
To create a Portfolio using HTML and CSS.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for introduction, about, projects, and contact details.

### STEP 5
Define global styles for fonts, colors, and layout.

### STEP 6
Style the header, navigation bar, and sections.

### STEP 7
Use Flexbox or CSS Grid for layout design.

### STEP 8
Add hover effects and transitions for interactivity.

### STEP 9
Add Images and Media.

### STEP 10
Use optimized images for a professional look.

### STEP 11
Open the HTML file in a browser to check layout and functionality.

### STEP 12
Fix styling issues and refine content placement.

### STEP 13
Deploy the Portfolio.

### STEP 14
Upload to GitHub Pages for free hosting.

## PROGRAM
```

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Your Name — Portfolio</title>
  <meta name="description" content="Personal portfolio of Your Name: projects, skills, experience, and contact." />
  <style>
    :root{
      --bg: #0b0c10;
      --panel: #111316;
      --text: #e6e6e6;
      --muted: #9aa3ab;
      --brand: #5eead4; /* teal */
      --brand-2: #a78bfa; /* violet */
      --ring: rgba(94, 234, 212, .45);
      --maxw: 1100px;
      --rad: 18px;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
    }
    @media (prefers-color-scheme: light){
      :root{
        --bg: #fbfbfc;
        --panel: #ffffff;
        --text: #0f172a;
        --muted: #475569;
        --ring: rgba(79,70,229,.35);
        --shadow: 0 10px 20px rgba(2,6,23,.08);
      }
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0; font: 16px/1.6 system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, "Helvetica Neue", Arial, "Apple Color Emoji", "Segoe UI Emoji";
      color: var(--text); background: radial-gradient(1200px 800px at 90% -10%, rgba(94,234,212,.15), transparent 60%),
               radial-gradient(900px 600px at -10% 10%, rgba(167,139,250,.15), transparent 55%), var(--bg);
    }
    a{color:inherit}
    .container{max-width:var(--maxw); margin-inline:auto; padding: 24px;}
    header{
      position:sticky; top:0; z-index:10; backdrop-filter: saturate(1.2) blur(10px);
      background: color-mix(in srgb, var(--bg) 60%, transparent);
      border-bottom: 1px solid color-mix(in srgb, var(--text) 12%, transparent);
    }
    .nav{display:flex; align-items:center; justify-content:space-between; gap:16px;}
    .nav a{padding:10px 12px; border-radius:12px; text-decoration:none; color:var(--muted)}
    .nav a:hover{background: color-mix(in srgb, var(--text) 8%, transparent); color:var(--text)}
    .brand{display:flex; align-items:center; gap:10px; font-weight:700; letter-spacing:.3px}
    .logo{width:34px;height:34px; border-radius:10px; background: linear-gradient(135deg, var(--brand), var(--brand-2)); box-shadow: var(--shadow)}

    /* Hero */
    .hero{display:grid; grid-template-columns: 1.1fr .9fr; gap:40px; align-items:center; padding: 60px 0}
    .hero .title{font-size: clamp(28px, 5vw, 48px); line-height:1.1; margin:0 0 12px}
    .hero .subtitle{color:var(--muted); margin:0 0 22px}
    .tags{display:flex; flex-wrap:wrap; gap:10px; margin:18px 0 28px}
    .tag{font-size:14px; padding:8px 12px; border-radius:999px; background: color-mix(in srgb, var(--text) 10%, transparent); color:var(--text)}
    .cta{display:flex; gap:12px; flex-wrap:wrap}
    .btn{display:inline-flex; align-items:center; gap:8px; padding:12px 16px; border-radius:14px; border:1px solid color-mix(in srgb, var(--text) 14%, transparent); text-decoration:none; font-weight:600; box-shadow: var(--shadow)}
    .btn.primary{background: linear-gradient(135deg, var(--brand), var(--brand-2)); color:#0b0c10; border: none}
    .portrait{
      aspect-ratio: 1/1; border-radius: 22px; background: linear-gradient(180deg, color-mix(in srgb, var(--brand) 25%, transparent), color-mix(in srgb, var(--brand-2) 20%, transparent)), url('') center/cover no-repeat, var(--panel);
      border:1px solid color-mix(in srgb, var(--text) 10%, transparent);
      box-shadow: var(--shadow);
      display:grid; place-items:center; color:var(--muted);
    }

    /* Sections */
    section{padding: 28px 0}
    .section-title{display:flex; align-items:center; gap:12px; font-size: 22px; margin: 12px 0 18px}
    .section-title .dot{width:10px; height:10px; border-radius:999px; background:linear-gradient(135deg, var(--brand), var(--brand-2)); box-shadow:0 0 0 6px var(--ring)}

    .panel{background: var(--panel); border:1px solid color-mix(in srgb, var(--text) 10%, transparent); border-radius: var(--rad); box-shadow: var(--shadow)}

    /* About */
    .about{display:grid; grid-template-columns: 1fr 1fr; gap:16px}
    .about .panel{padding:20px}

    /* Skills */
    .skills{display:grid; grid-template-columns: repeat(3, 1fr); gap:12px}
    .skill{padding:16px; display:flex; align-items:center; justify-content:space-between}
    .skill .name{font-weight:600}
    .meter{height:10px; width:55%; border-radius:999px; background: color-mix(in srgb, var(--text) 10%, transparent); overflow:hidden}
    .meter > span{display:block; height:100%; background: linear-gradient(90deg, var(--brand), var(--brand-2));}

    /* Projects */
    .grid{display:grid; grid-template-columns: repeat(3, 1fr); gap:16px}
    .card{padding:16px; display:flex; flex-direction:column; gap:12px}
    .card h3{margin:4px 0 0}
    .card p{color:var(--muted); margin:0}
    .chips{display:flex; flex-wrap:wrap; gap:8px}
    .chip{font-size:12px; padding:6px 10px; border-radius:999px; background: color-mix(in srgb, var(--text) 10%, transparent)}

    /* Experience */
    .timeline{display:grid; gap:12px}
    .item{display:grid; grid-template-columns: 1fr auto; gap:8px; padding:16px}
    .item small{color:var(--muted)}

    /* Contact */
    .contact{display:grid; grid-template-columns: 1.2fr .8fr; gap:16px}
    form{display:grid; gap:12px}
    input, textarea{padding:12px 14px; border-radius:12px; border:1px solid color-mix(in srgb, var(--text) 12%, transparent); background: transparent; color:var(--text)}
    input:focus, textarea:focus{outline: none; border-color: var(--brand); box-shadow: 0 0 0 6px var(--ring)}
    textarea{min-height:120px; resize:vertical}
    .note{color:var(--muted); font-size:14px}

    footer{padding: 30px 0; color:var(--muted); text-align:center}
    .socials{display:flex; gap:10px; flex-wrap:wrap; align-items:center; justify-content:center}
    .socials a{padding:8px 10px; border-radius:10px; text-decoration:none; border:1px solid color-mix(in srgb, var(--text) 12%, transparent)}

    .top{position: fixed; right:18px; bottom:18px; padding:12px 14px; border-radius:12px; border:1px solid color-mix(in srgb, var(--text) 14%, transparent); background: var(--panel); text-decoration:none; box-shadow: var(--shadow)}

    @media (max-width: 900px){
      .hero{grid-template-columns: 1fr;}
      .about{grid-template-columns: 1fr}
      .skills{grid-template-columns: repeat(2,1fr)}
      .grid{grid-template-columns: 1fr 1fr}
      .contact{grid-template-columns: 1fr}
    }
    @media (max-width: 600px){
      .skills{grid-template-columns: 1fr}
      .grid{grid-template-columns: 1fr}
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
        <div class="brand"><img src="SACHIN.jpeg" alt="Portrait placeholder" class="portrait" width="50" height="50"><span>SACHIN M</span></div>

      <nav aria-label="Primary">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#experience">Experience</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="hero" id="home">
      <div>
        <h1 class="title">Hi, I'm <span style="background:linear-gradient(135deg,var(--brand),var(--brand-2)); -webkit-background-clip:text; background-clip:text; color:transparent">SACHIN M</span> — a Developer crafting clean, human‑centered web experiences.</h1>
        <p class="subtitle">I specialize in building fast, accessible interfaces with HTML, CSS, and JavaScript. Currently exploring modern frameworks and design systems.</p>
        <div class="tags" aria-label="Areas of focus">
          <span class="tag">Frontend</span>
          <span class="tag">UI/UX</span>
          <span class="tag">Accessibility</span>
          <span class="tag">Performance</span>
        </div>
        <div class="cta">
          <a class="btn primary" href="#projects">View Projects →</a>
          <a class="btn" href="#contact" aria-label="Jump to contact">Contact</a>
          <a class="btn" href="resume.pdf" download>Download Résumé</a>
        </div>
      </div>

    </section>

    <section id="about">
      <h2 class="section-title"><span class="dot"></span> About</h2>
      <div class="about">
        <article class="panel">
          <p>
            I'm a developer with a passion for polished user interfaces and delightful details. I value clarity, performance,
            and inclusive design. I enjoy turning complex problems into simple, beautiful solutions.
          </p>
          <p>
            Outside work, you might find me tinkering with side projects, reading about product design, or mentoring new devs.
          </p>
        </article>
        <aside class="panel">
          <ul>
            <li>📍 Based in City, Country</li>
            <li>🎓 B.E.</li>
            <li>💼 Open to freelance and full‑time roles</li>
            <li>✉️ <a href="mailto:you@example.com">sachinmz800@gmail.com</a></li>
          </ul>
        </aside>
      </div>
    </section>

    <section id="skills">
      <h2 class="section-title"><span class="dot"></span> Skills</h2>
      <div class="skills">
        <div class="panel skill"><span class="name">HTML & Semantic Web</span><span class="meter"><span style="width:95%"></span></span></div>
        <div class="panel skill"><span class="name">CSS / Tailwind</span><span class="meter"><span style="width:90%"></span></span></div>
        <div class="panel skill"><span class="name">JavaScript / TypeScript</span><span class="meter"><span style="width:85%"></span></span></div>
        <div class="panel skill"><span class="name">React / Next.js</span><span class="meter"><span style="width:80%"></span></span></div>
        <div class="panel skill"><span class="name">Node / APIs</span><span class="meter"><span style="width:70%"></span></span></div>
        <div class="panel skill"><span class="name">Figma / Design Systems</span><span class="meter"><span style="width:75%"></span></span></div>
      </div>
    </section>

    <section id="projects">
      <h2 class="section-title"><span class="dot"></span> Projects</h2>
      <div class="grid">
        <article class="panel card">
          <div>
            <h3>Project In Web Application</h3>
            <p>Responsive web app with authentication and dashboard analytics.</p>
          </div>
          <div class="chips" aria-label="Tech stack">
            <span class="chip">HTML</span><span class="chip">CSS</span><span class="chip">JS</span>
          </div>
          <div class="cta">
            <a class="btn" href="#" target="_blank" rel="noopener">Live</a>
            <a class="btn" href="#" target="_blank" rel="noopener">Code</a>
          </div>
        </article>
        <article class="panel card">
          <div>
            <h3>Project In Designing</h3>
            <p>Design system starter kit with tokens, components, and docs site.</p>
          </div>
          <div class="chips"><span class="chip">Design</span><span class="chip">Docs</span><span class="chip">Components</span></div>
          <div class="cta">
            <a class="btn" href="#" target="_blank" rel="noopener">Live</a>
            <a class="btn" href="#" target="_blank" rel="noopener">Code</a>
          </div>
        </article>
        <article class="panel card">
          <div>
            <h3>Project In IOT</h3>
            <p>Real‑time collaborative editor with presence and comments.</p>
          </div>
          <div class="chips"><span class="chip">WebSockets</span><span class="chip">Auth</span><span class="chip">DB</span></div>
          <div class="cta">
            <a class="btn" href="#" target="_blank" rel="noopener">Live</a>
            <a class="btn" href="#" target="_blank" rel="noopener">Code</a>
          </div>
        </article>
      </div>
    </section>

    <section id="experience">
      <h2 class="section-title"><span class="dot"></span> Experience</h2>
      <div class="timeline">
        <article class="panel item">
          <div>
            <strong>Frontend Engineer</strong> — Company Name
            <div class="note">Built UI components, improved performance, and led accessibility efforts.</div>
          </div>
          <small>2023 — Present</small>
        </article>
        <article class="panel item">
          <div>
            <strong>Web Developer (Intern)</strong> — Another Co.
            <div class="note">Developed landing pages and automated build pipelines.</div>
          </div>
          <small>2022 — 2023</small>
        </article>
      </div>
    </section>

    <section id="contact">
      <h2 class="section-title"><span class="dot"></span> Contact</h2>
      <div class="contact">
        <form class="panel" onsubmit="event.preventDefault(); alert('Thanks! Your message was not actually sent in this demo.');">
          <input type="text" name="name" placeholder="Your name" required />
          <input type="email" name="email" placeholder="Your email" required />
          <textarea name="message" placeholder="Your message"></textarea>
          <button class="btn primary" type="submit">Send Message</button>
          <p class="note">This form is a demo. Hook it to your favorite form backend (e.g., Google Forms, Netlify Forms) or email.</p>
        </form>
        <aside class="panel" style="padding:16px">
          <h3 style="margin-top:0">Elsewhere</h3>
          <div class="socials">
            <a href="#" aria-label="GitHub">🐙 GitHub</a>
            <a href="#" aria-label="LinkedIn">💼 LinkedIn</a>
            <a href="#" aria-label="Twitter / X">🕊️ X</a>
            <a href="#" aria-label="Email">✉️ Email</a>
          </div>
        </aside>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      © <span id="year"></span> SACHIN M · Built with HTML & CSS
    </div>
  </footer>


  <a class="top" href="#home" aria-label="Back to top">↑</a>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>

```

## OUTPUT

<img width="1888" height="852" alt="Screenshot 2025-08-13 093858" src="https://github.com/user-attachments/assets/62929b11-1cd5-4a24-8faa-de592ac0dccd" />

<img width="1875" height="856" alt="image" src="https://github.com/user-attachments/assets/26920cf5-515f-4fca-bf4b-ecb6d0af4f58" />
<img width="1884" height="851" alt="Screenshot 2025-08-13 094011" src="https://github.com/user-attachments/assets/974ec1d3-843d-4b8f-bd50-1d900d32f64d" />
<img width="1879" height="860" alt="Screenshot 2025-08-13 094048" src="https://github.com/user-attachments/assets/1c6b55e5-b430-47a6-ad42-dc075779c44a" />


## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
