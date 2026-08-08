<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Joyson Pinto — Profile</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600;700&display=swap');

  :root{
    --bg: #0F1417;
    --bg-raised: #151B1F;
    --bg-panel: #12181C;
    --line: #232B30;
    --line-soft: #1B2226;
    --text: #E7EEF0;
    --text-dim: #92A3AA;
    --text-faint: #5C6D74;
    --java: #ED8B00;
    --java-dim: #B96C09;
    --spring: #6DB33F;
    --spring-dim: #4F8A2C;
    --red-diff: #E5534B;
    --green-diff: #6DB33F;
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{background:var(--bg);}
  body{
    background:
      radial-gradient(ellipse 900px 500px at 15% -10%, rgba(237,139,0,0.07), transparent 60%),
      radial-gradient(ellipse 900px 500px at 85% 10%, rgba(109,179,63,0.06), transparent 60%),
      var(--bg);
    color:var(--text);
    font-family:'Inter', sans-serif;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  ::selection{background:var(--java); color:#0F1417;}

  a{color:inherit; text-decoration:none;}

  .wrap{max-width:900px; margin:0 auto; padding:64px 24px 100px;}

  /* ---------- shared: file-tab panel chrome ---------- */
  .panel{
    background:var(--bg-panel);
    border:1px solid var(--line);
    border-radius:10px;
    overflow:hidden;
    margin-bottom:28px;
  }
  .panel-bar{
    display:flex; align-items:center; gap:8px;
    padding:11px 16px;
    background:var(--bg-raised);
    border-bottom:1px solid var(--line);
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--text-faint);
  }
  .dot{width:9px; height:9px; border-radius:50%; background:#3A444A;}
  .panel-bar .filename{margin-left:6px; color:var(--text-dim);}
  .panel-bar .filename .ext{color:var(--java);}
  .panel-body{padding:22px 26px 26px;}

  /* ---------- HERO / terminal ---------- */
  .hero{margin-bottom:52px;}
  .term{
    background:var(--bg-panel);
    border:1px solid var(--line);
    border-radius:10px;
    box-shadow:0 30px 80px -30px rgba(0,0,0,0.6);
  }
  .term-bar{
    display:flex; align-items:center; gap:8px;
    padding:12px 16px;
    background:linear-gradient(180deg, var(--bg-raised), var(--bg-panel));
    border-bottom:1px solid var(--line);
  }
  .term-bar .tdot{width:10px; height:10px; border-radius:50%;}
  .tdot.r{background:#4a4a4a;}
  .tdot.y{background:#4a4a4a;}
  .tdot.g{background:#4a4a4a;}
  .term-title{
    flex:1; text-align:center;
    font-family:'JetBrains Mono', monospace;
    font-size:12px; color:var(--text-faint);
  }
  .term-body{
    padding:32px 30px 38px;
    font-family:'JetBrains Mono', monospace;
    font-size:15px;
    min-height:230px;
  }
  .term-line{margin-bottom:10px; opacity:0; animation:reveal 0.4s forwards;}
  .prompt{color:var(--spring);}
  .prompt::before{content:"❯ "; color:var(--text-faint);}
  .out{color:var(--text-dim); padding-left:18px; display:block;}
  .accent-o{color:var(--java); font-weight:600;}
  .accent-g{color:var(--spring); font-weight:600;}
  .name-line{
    font-family:'Space Grotesk', sans-serif;
    font-size:38px; font-weight:700;
    letter-spacing:-0.01em;
    color:var(--text);
    padding-left:18px;
    margin-top:2px; margin-bottom:6px;
  }
  .role-line{
    padding-left:18px; color:var(--text-dim); font-size:15px;
    margin-bottom:2px;
  }
  .cursor{display:inline-block; width:9px; height:17px; background:var(--java); vertical-align:middle; margin-left:2px; animation:blink 1s step-end infinite;}

  @keyframes reveal{ to{opacity:1;} }
  @keyframes blink{ 50%{opacity:0;} }

  @media (prefers-reduced-motion: reduce){
    .term-line{animation:none; opacity:1;}
    .cursor{animation:none;}
  }

  .hero-links{display:flex; gap:10px; margin-top:20px; flex-wrap:wrap;}
  .pill{
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    padding:8px 14px;
    border:1px solid var(--line);
    border-radius:100px;
    color:var(--text-dim);
    display:flex; align-items:center; gap:7px;
    transition:border-color .15s, color .15s, transform .15s;
  }
  .pill:hover{border-color:var(--java-dim); color:var(--text); transform:translateY(-1px);}
  .pill .dot-sm{width:6px; height:6px; border-radius:50%;}

  /* ---------- section labels ---------- */
  .sec-head{
    display:flex; align-items:baseline; gap:10px;
    margin:0 0 16px;
  }
  .sec-tag{
    font-family:'JetBrains Mono', monospace;
    font-size:11.5px; letter-spacing:0.06em;
    color:var(--java);
    background:rgba(237,139,0,0.09);
    border:1px solid rgba(237,139,0,0.25);
    padding:3px 9px; border-radius:5px;
    text-transform:uppercase;
  }
  .sec-title{
    font-family:'Space Grotesk', sans-serif;
    font-size:22px; font-weight:600;
    color:var(--text);
  }

  /* ---------- about: yaml block ---------- */
  .yaml-row{display:flex; gap:10px; margin-bottom:9px; font-family:'JetBrains Mono', monospace; font-size:14px;}
  .yaml-key{color:var(--java); min-width:150px; flex-shrink:0;}
  .yaml-key::after{content:":"; color:var(--text-faint);}
  .yaml-val{color:var(--text-dim);}
  .yaml-val .str{color:var(--spring);}
  .bracket{color:var(--text-faint);}

  /* ---------- dependency-style skill chips ---------- */
  .dep-group{margin-bottom:22px;}
  .dep-group:last-child{margin-bottom:0;}
  .dep-label{
    font-family:'JetBrains Mono', monospace;
    font-size:11px; text-transform:uppercase; letter-spacing:0.08em;
    color:var(--text-faint); margin-bottom:10px;
  }
  .dep-list{display:flex; flex-wrap:wrap; gap:9px;}
  .dep{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    padding:8px 12px;
    background:var(--bg-raised);
    border:1px solid var(--line);
    border-left:2px solid var(--line);
    border-radius:4px;
    color:var(--text-dim);
    transition:border-color .15s, color .15s, background .15s;
    cursor:default;
  }
  .dep:hover{border-left-color:var(--java); color:var(--text); background:#171E22;}
  .dep .pkg{color:var(--text-faint);}

  /* ---------- stats: image grid ---------- */
  .stat-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:16px;
    margin-bottom:16px;
  }
  .stat-grid img, .full-img{
    width:100%; display:block;
    border-radius:8px;
    border:1px solid var(--line);
  }
  .full-w{margin-bottom:16px;}

  /* ---------- quote ---------- */
  .quote-panel .panel-body{
    display:flex; align-items:center; justify-content:center;
    padding:14px 20px;
  }
  .quote-panel img{max-width:100%; border-radius:6px;}

  /* ---------- 3d graph note ---------- */
  .setup-note{
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    color:var(--text-faint);
    display:flex; gap:8px; align-items:flex-start;
    padding:12px 14px;
    background:rgba(237,139,0,0.06);
    border:1px solid rgba(237,139,0,0.18);
    border-radius:7px;
    margin-top:14px;
  }
  .setup-note .flag{color:var(--java); flex-shrink:0;}

  details.diff{
    margin-top:14px;
    border:1px solid var(--line);
    border-radius:8px;
    overflow:hidden;
  }
  details.diff summary{
    padding:12px 16px;
    background:var(--bg-raised);
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    color:var(--text-dim);
    cursor:pointer;
    list-style:none;
    display:flex; align-items:center; gap:8px;
  }
  details.diff summary::-webkit-details-marker{display:none;}
  details.diff summary::before{content:"▸"; color:var(--java); transition:transform .15s;}
  details.diff[open] summary::before{transform:rotate(90deg);}
  .diff-body{
    padding:18px 20px 22px;
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    color:var(--text-dim);
    border-top:1px solid var(--line);
  }
  .diff-body ol{padding-left:20px; margin:10px 0;}
  .diff-body li{margin-bottom:8px;}
  .code-block{
    background:#0B0F12;
    border:1px solid var(--line-soft);
    border-radius:6px;
    padding:14px 16px;
    margin:10px 0;
    overflow-x:auto;
    white-space:pre;
    font-size:12px;
    line-height:1.7;
  }
  .code-block .k{color:var(--java);}
  .code-block .c{color:var(--text-faint);}
  .code-block .s{color:var(--spring);}

  /* ---------- footer ---------- */
  .footer{
    text-align:center;
    margin-top:60px;
    padding-top:32px;
    border-top:1px solid var(--line);
  }
  .footer .lead{
    font-family:'Space Grotesk', sans-serif;
    font-size:20px; font-weight:600;
    margin-bottom:18px;
  }
  .footer .lead .accent-o{font-weight:700;}
  .foot-links{display:flex; gap:12px; justify-content:center; flex-wrap:wrap; margin-bottom:26px;}
  .foot-links .pill{background:var(--bg-panel);}
  .footer .sign{
    font-family:'JetBrains Mono', monospace;
    font-size:11.5px; color:var(--text-faint);
  }

  @media(max-width:640px){
    .stat-grid{grid-template-columns:1fr;}
    .name-line{font-size:28px;}
    .yaml-key{min-width:120px;}
  }
</style>
</head>
<body>

<div class="wrap">

  <!-- HERO -->
  <div class="hero">
    <div class="term">
      <div class="term-bar">
        <span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span>
        <span class="term-title">joyson@dev: ~</span>
      </div>
      <div class="term-body">
        <div class="term-line" style="animation-delay:0.1s">
          <span class="prompt">whoami</span>
        </div>
        <div class="name-line term-line" style="animation-delay:0.5s">Joyson Pinto</div>
        <div class="role-line term-line" style="animation-delay:0.9s">
          <span class="accent-o">Java</span> / <span class="accent-g">Spring Boot</span> Developer — Microservices · DSA · AI/GenAI
        </div>
        <div class="term-line" style="animation-delay:1.4s; margin-top:22px;">
          <span class="prompt">status</span>
        </div>
        <div class="out term-line" style="animation-delay:1.7s">
          building scalable backends, one commit at a time<span class="cursor"></span>
        </div>
      </div>
    </div>

    <div class="hero-links">
      <a class="pill" href="https://linkedin.com/in/joyson-pinto/"><span class="dot-sm" style="background:#0A66C2"></span>LinkedIn</a>
      <a class="pill" href="https://x.com/Joysonpinto77"><span class="dot-sm" style="background:#E7E9EA"></span>X / Twitter</a>
      <a class="pill" href="mailto:joysonpinto77@gmail.com"><span class="dot-sm" style="background:var(--java)"></span>joysonpinto77@gmail.com</a>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="sec-head"><span class="sec-tag">01</span><span class="sec-title">About</span></div>
  <div class="panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">about<span class="ext">.yaml</span></span>
    </div>
    <div class="panel-body">
      <div class="yaml-row"><span class="yaml-key">name</span><span class="yaml-val">Joyson Pinto</span></div>
      <div class="yaml-row"><span class="yaml-key">role</span><span class="yaml-val">Java Spring Boot Developer</span></div>
      <div class="yaml-row"><span class="yaml-key">focus</span><span class="yaml-val"><span class="bracket">[</span>Microservices, DSA, System Design, AI/GenAI<span class="bracket">]</span></span></div>
      <div class="yaml-row"><span class="yaml-key">currently_exploring</span><span class="yaml-val">Generative AI &amp; LLM-powered applications</span></div>
      <div class="yaml-row"><span class="yaml-key">databases</span><span class="yaml-val"><span class="bracket">[</span>MySQL, MongoDB, PostgreSQL<span class="bracket">]</span></span></div>
      <div class="yaml-row"><span class="yaml-key">fun_fact</span><span class="yaml-val">Passionate about building scalable applications 🚀</span></div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="sec-head"><span class="sec-tag">02</span><span class="sec-title">Tech Stack</span></div>
  <div class="panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">build<span class="ext">.gradle</span></span>
    </div>
    <div class="panel-body">

      <div class="dep-group">
        <div class="dep-label">Languages</div>
        <div class="dep-list">
          <span class="dep"><span class="pkg">lang:</span>Java</span>
          <span class="dep"><span class="pkg">lang:</span>C</span>
          <span class="dep"><span class="pkg">lang:</span>C#</span>
          <span class="dep"><span class="pkg">lang:</span>JavaScript</span>
          <span class="dep"><span class="pkg">lang:</span>Python</span>
        </div>
      </div>

      <div class="dep-group">
        <div class="dep-label">Frameworks &amp; Libraries</div>
        <div class="dep-list">
          <span class="dep"><span class="pkg">org.springframework:</span>spring-boot</span>
          <span class="dep"><span class="pkg">org:</span>react</span>
          <span class="dep"><span class="pkg">io:</span>fastapi</span>
        </div>
      </div>

      <div class="dep-group">
        <div class="dep-label">Databases</div>
        <div class="dep-list">
          <span class="dep"><span class="pkg">db:</span>MySQL</span>
          <span class="dep"><span class="pkg">db:</span>MongoDB</span>
          <span class="dep"><span class="pkg">db:</span>PostgreSQL</span>
        </div>
      </div>

      <div class="dep-group">
        <div class="dep-label">Tools &amp; Platforms</div>
        <div class="dep-list">
          <span class="dep"><span class="pkg">cloud:</span>AWS</span>
          <span class="dep"><span class="pkg">tool:</span>Docker</span>
          <span class="dep"><span class="pkg">tool:</span>Git</span>
          <span class="dep"><span class="pkg">tool:</span>Postman</span>
          <span class="dep"><span class="pkg">ide:</span>VS Code</span>
        </div>
      </div>

    </div>
  </div>

  <!-- STATS -->
  <div class="sec-head"><span class="sec-tag">03</span><span class="sec-title">GitHub Analytics</span></div>
  <div class="panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">stats<span class="ext">.log</span></span>
    </div>
    <div class="panel-body">
      <div class="stat-grid">
        <img src="https://github-readme-stats.vercel.app/api?username=joyson-git&show_icons=true&theme=radical&hide_border=true&include_all_commits=true&count_private=true" alt="GitHub stats" loading="lazy">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=joyson-git&layout=compact&theme=radical&hide_border=true" alt="Top languages" loading="lazy">
      </div>
      <img class="full-img full-w" src="https://nirzak-streak-stats.vercel.app/?user=joyson-git&theme=radical&hide_border=true" alt="Streak stats" loading="lazy">
      <img class="full-img" src="https://github-readme-activity-graph.vercel.app/graph?username=joyson-git&theme=redical&hide_border=true&area=true" alt="Activity graph" loading="lazy">
    </div>
  </div>

  <!-- TROPHIES -->
  <div class="sec-head"><span class="sec-tag">04</span><span class="sec-title">Trophies</span></div>
  <div class="panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">achievements<span class="ext">.json</span></span>
    </div>
    <div class="panel-body">
      <img class="full-img" src="https://github-profile-trophy.vercel.app/?username=joyson-git&theme=radical&no-frame=true&no-bg=true&margin-w=4&row=1" alt="GitHub trophies" loading="lazy">
    </div>
  </div>

  <!-- 3D CONTRIBUTION GRAPH -->
  <div class="sec-head"><span class="sec-tag">05</span><span class="sec-title">Contribution Graph</span></div>
  <div class="panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">snake<span class="ext">.svg</span></span>
    </div>
    <div class="panel-body">
      <img class="full-img" src="https://raw.githubusercontent.com/joyson-git/joyson-git/output/github-contribution-grid-snake-dark.svg" alt="3D contribution graph" loading="lazy">

      <div class="setup-note">
        <span class="flag">⚠</span>
        <span>This graph is generated by a GitHub Action, not a static badge — it stays blank until the workflow below is added to the profile repo.</span>
      </div>

      <details class="diff">
        <summary>Enable the real 3D contribution graph — one-time setup</summary>
        <div class="diff-body">
          <p>The stats, trophy, and streak badges above are live and need no setup. The 3D graph is different: a GitHub Action has to regenerate it daily inside <span style="color:var(--text)">joyson-git/joyson-git</span>.</p>

          <ol>
            <li>Create <span style="color:var(--text)">.github/workflows/3d-contrib.yml</span> in the profile repo with the workflow below.</li>
            <li>Commit, push, then trigger it once manually from the <span style="color:var(--text)">Actions</span> tab (<em>Run workflow</em>).</li>
            <li>It writes SVGs into a <span style="color:var(--text)">profile-3d-contrib/</span> folder — check the action's actual output filename and match the <span style="color:var(--text)">&lt;img src&gt;</span> path above to it.</li>
            <li>From then on, it updates automatically every day.</li>
          </ol>

          <div class="code-block"><span class="k">name:</span> 3D Contribution Graph

<span class="k">on:</span>
  <span class="k">schedule:</span>
    - <span class="k">cron:</span> <span class="s">"0 0 * * *"</span>
  <span class="k">workflow_dispatch:</span>

<span class="k">jobs:</span>
  <span class="k">build:</span>
    <span class="k">runs-on:</span> ubuntu-latest
    <span class="k">steps:</span>
      - <span class="k">uses:</span> actions/checkout@v4
      - <span class="k">uses:</span> yoshi389111/github-profile-3d-contrib@0.7.1
        <span class="k">env:</span>
          <span class="k">GITHUB_TOKEN:</span> <span class="s">${{ secrets.GITHUB_TOKEN }}</span>
        <span class="k">with:</span>
          <span class="k">username:</span> joyson-git
      - <span class="k">name:</span> Commit output
        <span class="k">run:</span> |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A
          git commit -m <span class="s">"Update 3D contribution graph"</span> || echo <span class="s">"No changes"</span>
          git push</div>

          <p>Want a graph that visibly animates, rather than an isometric-styled snapshot? Swap the action for <span style="color:var(--text)">Platane/snk</span> — it produces a snake that eats its way across the contribution grid as a moving GIF.</p>
        </div>
      </details>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="panel quote-panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">// random dev quote</span>
    </div>
    <div class="panel-body">
      <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical" alt="Dev quote" loading="lazy">
    </div>
  </div>

  <!-- TOP CONTRIBUTED REPO -->
  <div class="sec-head"><span class="sec-tag">06</span><span class="sec-title">Top Contributed Repo</span></div>
  <div class="panel">
    <div class="panel-bar">
      <span class="dot" style="background:#5C6D74"></span>
      <span class="filename">contrib<span class="ext">.log</span></span>
    </div>
    <div class="panel-body">
      <img class="full-img" src="https://github-contributor-stats.vercel.app/api?username=joyson-git&limit=5&theme=dark&combine_all_yearly_contributions=true" alt="Top contributed repo" loading="lazy">
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="lead">Let's <span class="accent-o">connect</span> <span class="accent-g">&amp;</span> build something.</div>
    <div class="foot-links">
      <a class="pill" href="https://linkedin.com/in/joyson-pinto/"><span class="dot-sm" style="background:#0A66C2"></span>LinkedIn</a>
      <a class="pill" href="https://x.com/Joysonpinto77"><span class="dot-sm" style="background:#E7E9EA"></span>X / Twitter</a>
      <a class="pill" href="mailto:joysonpinto77@gmail.com"><span class="dot-sm" style="background:var(--java)"></span>Email</a>
    </div>
    <div class="sign">$ git commit -m "always be building" <span class="cursor"></span></div>
  </div>

</div>

</body>
</html>
