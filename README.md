<!DOCTYPE html>

<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lettres 🌸</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Lora:ital@0;1&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–cream: #fdf0f3;
–parchment: #f9dde4;
–ink: #3a1a24;
–ink-light: #8a4a5e;
–wax: #c0546e;
–wax-dark: #9c3a52;
–envelope: #f5c8d4;
–envelope-dark: #e09ab0;
–envelope-mid: #f0b0c4;
–ribbon: #d4547a;
–shadow: rgba(58,26,36,0.12);
}

body {
font-family: ‘Lora’, Georgia, serif;
background: var(–cream);
color: var(–ink);
min-height: 100vh;
display: flex; align-items: center; justify-content: center;
padding: 20px;
background-image:
radial-gradient(ellipse at 15% 40%, rgba(192,84,110,0.06) 0%, transparent 55%),
radial-gradient(ellipse at 85% 70%, rgba(224,154,176,0.1) 0%, transparent 50%);
}

.page { display: none; width: 100%; max-width: 680px; }
.page.active { display: flex; flex-direction: column; align-items: center; }

/* ── HEADER ── */
.page-header { text-align: center; margin-bottom: 36px; }
.page-header h1 {
font-family: ‘Playfair Display’, serif; font-style: italic;
font-size: clamp(1.9rem, 5vw, 2.8rem); color: var(–ink);
line-height: 1.15;
}
.page-header p { color: var(–ink-light); font-style: italic; margin-top: 8px; font-size: 0.95rem; }

/* ── PAPER ── */
.paper {
background: white; border-radius: 2px; padding: 44px 52px; width: 100%;
box-shadow: 0 1px 1px var(–shadow), 0 4px 20px var(–shadow), inset 0 0 0 1px rgba(224,154,176,0.2);
position: relative; overflow: hidden;
}
.paper::before {
content: ‘’; position: absolute; left: 72px; top: 0; bottom: 0;
width: 1px; background: rgba(192,84,110,0.09);
}

/* ── FIELDS ── */
.field-group { margin-bottom: 22px; }
.field-label {
display: block; font-size: 0.68rem; letter-spacing: 0.16em;
text-transform: uppercase; color: var(–ink-light); margin-bottom: 6px; padding-left: 4px;
}
input[type=“text”], textarea, input[type=“password”] {
width: 100%; border: none; border-bottom: 1px solid rgba(58,26,36,0.13);
padding: 8px 4px; font-family: ‘Lora’, serif; font-size: 1rem;
color: var(–ink); background: transparent; outline: none;
transition: border-color 0.2s; resize: none;
}
input:focus, textarea:focus { border-bottom-color: var(–wax); }
input::placeholder, textarea::placeholder { color: rgba(58,26,36,0.28); font-style: italic; }
textarea { min-height: 200px; line-height: 1.9; }

/* ── BUTTONS ── */
.btn {
display: inline-flex; align-items: center; gap: 10px;
padding: 13px 30px; border: none; cursor: pointer;
font-family: ‘Playfair Display’, serif; font-size: 1rem;
letter-spacing: 0.02em; border-radius: 2px; transition: all 0.2s;
}
.btn-primary { background: var(–wax); color: white; box-shadow: 0 2px 12px rgba(192,84,110,0.28); }
.btn-primary:hover { background: var(–wax-dark); box-shadow: 0 4px 20px rgba(192,84,110,0.38); transform: translateY(-1px); }
.btn-secondary { background: transparent; color: var(–ink-light); border: 1px solid var(–envelope-dark); font-size: 0.88rem; }
.btn-secondary:hover { background: var(–parchment); }
.btn-ghost { background: transparent; color: var(–ink-light); font-size: 0.85rem; font-family: ‘Lora’, serif; font-style: italic; text-decoration: underline; cursor: pointer; border: none; padding: 4px 0; }
.actions { display: flex; justify-content: flex-end; gap: 12px; margin-top: 28px; flex-wrap: wrap; }

/* ── HOME ── */
.home-card {
background: white; border-radius: 2px; padding: 48px 40px; width: 100%;
box-shadow: 0 4px 24px var(–shadow); text-align: center;
}
.home-seal {
width: 72px; height: 72px; background: var(–wax); border-radius: 50%;
margin: 0 auto 28px; display: flex; align-items: center; justify-content: center;
font-size: 32px; box-shadow: 0 2px 12px rgba(192,84,110,0.35);
}
.home-card h1 {
font-family: ‘Playfair Display’, serif; font-style: italic;
font-size: clamp(1.8rem, 4vw, 2.4rem); margin-bottom: 10px;
}
.home-card .subtitle { color: var(–ink-light); font-style: italic; margin-bottom: 36px; font-size: 0.95rem; }
.home-actions { display: flex; flex-direction: column; gap: 14px; align-items: center; }
.home-actions .btn { width: 100%; max-width: 320px; justify-content: center; }
.divider { width: 100%; max-width: 320px; display: flex; align-items: center; gap: 12px; color: var(–ink-light); font-size: 0.8rem; font-style: italic; }
.divider::before, .divider::after { content: ‘’; flex: 1; height: 1px; background: var(–envelope-dark); }

/* ── LINK CARD ── */
.link-card {
background: white; border-radius: 2px; padding: 44px; width: 100%;
text-align: center; box-shadow: 0 4px 24px var(–shadow);
}
.link-card .seal { width: 58px; height: 58px; background: var(–wax); border-radius: 50%; margin: 0 auto 22px; display: flex; align-items: center; justify-content: center; font-size: 26px; box-shadow: 0 2px 8px rgba(192,84,110,0.35); }
.link-card h2 { font-family:‘Playfair Display’,serif; font-style:italic; font-size:1.6rem; margin-bottom:10px; }
.link-card p { color:var(–ink-light); font-style:italic; margin-bottom:24px; font-size:0.9rem; }
.link-box {
background: var(–cream); border: 1px solid var(–envelope-dark); border-radius: 2px;
padding: 13px 16px; font-family: monospace; font-size: 0.75rem; color: var(–ink);
word-break: break-all; text-align: left; margin-bottom: 14px; max-height: 75px; overflow-y: auto;
}
.copy-ok { font-size:0.82rem; color:var(–wax); font-style:italic; height:18px; margin-bottom:20px; }

/* ── ENVELOPE ── */
#page-envelope { perspective: 1000px; }
.envelope-scene { position: relative; width: min(380px, 90vw); cursor: pointer; }
.envelope-wrap { position: relative; width: 100%; padding-top: 65%; }
.envelope-body {
position: absolute; inset: 0; background: var(–envelope);
border-radius: 3px 3px 6px 6px;
box-shadow: 0 8px 32px rgba(58,26,36,0.18), 0 2px 6px rgba(58,26,36,0.08);
}
.env-bottom { position:absolute; bottom:0; left:0; right:0; height:55%; background:var(–envelope-dark); clip-path:polygon(0% 100%,50% 0%,100% 100%); }
.env-left { position:absolute; top:0; left:0; bottom:0; width:50%; background:color-mix(in srgb,var(–envelope) 85%,var(–envelope-dark)); clip-path:polygon(0% 0%,100% 50%,0% 100%); }
.env-right { position:absolute; top:0; right:0; bottom:0; width:50%; background:color-mix(in srgb,var(–envelope) 75%,var(–envelope-dark)); clip-path:polygon(100% 0%,0% 50%,100% 100%); }
.env-flap { position:absolute; top:0; left:0; right:0; height:52%; transform-origin:top center; transition:transform 0.65s cubic-bezier(0.4,0,0.2,1); z-index:3; }
.env-flap-inner { width:100%; height:100%; background:var(–envelope-mid); clip-path:polygon(0% 0%,50% 100%,100% 0%); filter:drop-shadow(0 2px 4px rgba(58,26,36,0.08)); }
.envelope-scene.open .env-flap { transform: rotateX(-180deg); }
.env-ribbon-h { position:absolute; top:50%; left:-4%; right:-4%; height:11%; transform:translateY(-50%); background:var(–ribbon); z-index:5; box-shadow:0 1px 4px rgba(58,26,36,0.15); transition:opacity 0.25s; }
.env-ribbon-h::after { content:’’; position:absolute; top:0; left:0; right:0; height:38%; background:rgba(255,255,255,0.2); }
.env-ribbon-v { position:absolute; left:50%; top:-4%; bottom:-4%; width:11%; transform:translateX(-50%); background:var(–ribbon); z-index:5; box-shadow:0 1px 4px rgba(58,26,36,0.15); transition:opacity 0.25s; }
.env-ribbon-v::after { content:’’; position:absolute; top:0; left:0; width:38%; bottom:0; background:rgba(255,255,255,0.2); }
.env-bow { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); z-index:6; font-size:clamp(28px,7vw,42px); line-height:1; filter:drop-shadow(0 2px 4px rgba(58,26,36,0.2)); transition:opacity 0.25s; pointer-events:none; }
.envelope-scene.open .env-ribbon-h,
.envelope-scene.open .env-ribbon-v,
.envelope-scene.open .env-bow { opacity:0; }
.env-letter { position:absolute; left:8%; right:8%; bottom:4%; height:90%; background:white; border-radius:1px; z-index:2; transform:translateY(0); transition:transform 0.7s cubic-bezier(0.4,0,0.2,1) 0.35s; box-shadow:0 2px 8px rgba(58,26,36,0.08); display:flex; align-items:center; justify-content:center; font-family:‘Playfair Display’,serif; font-style:italic; color:var(–ink-light); font-size:0.8rem; }
.envelope-scene.open .env-letter { transform:translateY(-55%); }
.env-hint { text-align:center; margin-top:20px; color:var(–ink-light); font-style:italic; font-size:0.9rem; animation:pulse 2s ease-in-out infinite; transition:opacity 0.3s; }
@keyframes pulse { 0%,100%{opacity:.6} 50%{opacity:1} }

/* ── LETTER ── */
#page-letter { animation:fadeUp 0.8s ease forwards; }
#page-reply-sent { animation:fadeUp 0.6s ease forwards; }
@keyframes fadeUp { from{opacity:0;transform:translateY(20px)} to{opacity:1;transform:translateY(0)} }

.letter-paper {
background:white; width:100%; padding:52px 56px 48px;
box-shadow:0 1px 1px var(–shadow),0 8px 32px var(–shadow),inset 0 0 0 1px rgba(224,154,176,0.18);
border-radius:2px; position:relative; line-height:1.95; overflow:hidden;
}
.letter-paper::before { content:’’; position:absolute; left:76px; top:0; bottom:0; width:1px; background:rgba(192,84,110,0.08); z-index:0; }
.letter-lines { position:absolute; inset:0; background:repeating-linear-gradient(transparent,transparent calc(1.95em - 1px),rgba(58,26,36,0.04) calc(1.95em - 1px),rgba(58,26,36,0.04) 1.95em); pointer-events:none; border-radius:2px; z-index:0; }
.flower-corner { position:absolute; width:90px; height:90px; opacity:0.2; pointer-events:none; }
.flower-tl{top:0;left:0} .flower-tr{top:0;right:0;transform:scaleX(-1)} .flower-bl{bottom:0;left:0;transform:scaleY(-1)} .flower-br{bottom:0;right:0;transform:scale(-1,-1)}
.letter-content { position:relative; z-index:1; }
.letter-to { font-family:‘Playfair Display’,serif; font-style:italic; font-size:1.1rem; margin-bottom:24px; color:var(–ink); }
.letter-body { font-size:1rem; white-space:pre-wrap; color:var(–ink); }
.letter-from { margin-top:28px; text-align:right; font-family:‘Playfair Display’,serif; font-style:italic; font-size:1rem; color:var(–ink); }
.ornament { text-align:center; color:var(–wax); font-size:0.95rem; letter-spacing:0.4em; margin:18px 0; opacity:0.45; }

/* Reply section */
.reply-section {
margin-top: 32px; padding-top: 28px;
border-top: 1px solid var(–parchment);
position: relative; z-index: 1;
}
.reply-section h3 {
font-family:‘Playfair Display’,serif; font-style:italic;
font-size:1.1rem; color:var(–ink-light); margin-bottom:18px; text-align:center;
}
.reply-toggle {
display: flex; justify-content: center; margin-bottom: 4px;
}
.reply-form { display: none; }
.reply-form.visible { display: block; }
.reply-actions { display:flex; justify-content:flex-end; gap:10px; margin-top:18px; }

/* Success card */
.success-card {
background:white; border-radius:2px; padding:48px 40px; width:100%;
text-align:center; box-shadow:0 4px 24px var(–shadow);
}
.success-card .seal { width:60px; height:60px; background:var(–wax); border-radius:50%; margin:0 auto 22px; display:flex; align-items:center; justify-content:center; font-size:26px; box-shadow:0 2px 8px rgba(192,84,110,0.35); }
.success-card h2 { font-family:‘Playfair Display’,serif; font-style:italic; font-size:1.6rem; margin-bottom:10px; }
.success-card p { color:var(–ink-light); font-style:italic; margin-bottom:24px; }

/* ── INBOX ── */
.inbox-list { width:100%; display:flex; flex-direction:column; gap:12px; }
.inbox-item {
background:white; border-radius:2px; padding:20px 24px;
box-shadow:0 1px 6px var(–shadow); cursor:pointer;
border-left:3px solid var(–envelope-dark);
transition:all 0.2s; display:flex; align-items:center; gap:16px;
}
.inbox-item:hover { border-left-color:var(–wax); transform:translateX(3px); box-shadow:0 2px 12px var(–shadow); }
.inbox-item-icon { font-size:22px; flex-shrink:0; }
.inbox-item-info { flex:1; min-width:0; }
.inbox-item-from { font-family:‘Playfair Display’,serif; font-style:italic; font-size:1rem; color:var(–ink); }
.inbox-item-preview { font-size:0.82rem; color:var(–ink-light); margin-top:3px; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
.inbox-empty { text-align:center; color:var(–ink-light); font-style:italic; padding:40px 20px; }

/* ── ADMIN LOGIN ── */
.login-card { background:white; border-radius:2px; padding:48px 44px; width:100%; max-width:420px; box-shadow:0 4px 24px var(–shadow); }
.login-card h2 { font-family:‘Playfair Display’,serif; font-style:italic; font-size:1.6rem; margin-bottom:6px; text-align:center; }
.login-card p { color:var(–ink-light); font-style:italic; font-size:0.88rem; text-align:center; margin-bottom:28px; }
.login-error { color:var(–wax-dark); font-size:0.85rem; font-style:italic; margin-top:8px; min-height:20px; }

/* ── MISC ── */
.back-link { align-self:flex-start; margin-bottom:20px; }
.tag { display:inline-block; background:var(–parchment); color:var(–ink-light); font-size:0.72rem; letter-spacing:0.1em; text-transform:uppercase; padding:3px 10px; border-radius:20px; margin-bottom:16px; }

@media(max-width:520px){
.paper,.letter-paper{padding:28px 22px}
.paper::before,.letter-paper::before{left:40px}
.link-card,.login-card,.home-card,.success-card{padding:28px 20px}
.flower-corner{width:60px;height:60px}
}
</style>

</head>
<body>

<!-- ══════════════════════════════════════
     PAGE : ACCUEIL
══════════════════════════════════════ -->

<div class="page active" id="page-home">
  <div class="home-card">
    <div class="home-seal">🌸</div>
    <h1>Lettres</h1>
    <p class="subtitle">Des lettres privées, pour les gens qu'on aime</p>
    <div class="home-actions">
      <button class="btn btn-primary" onclick="showPage('page-write')">✍️ &nbsp;Écrire une lettre</button>
      <div class="divider">ou</div>
      <button class="btn btn-secondary" onclick="showPage('page-login')">📥 &nbsp;Voir mes réponses</button>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : ÉCRIRE
══════════════════════════════════════ -->

<div class="page" id="page-write">
  <button class="btn-ghost back-link" onclick="showPage('page-home')">← Retour</button>
  <div class="page-header">
    <h1>Écrire une lettre</h1>
    <p>Elle sera scellée jusqu'à ce que ton ami l'ouvre 🎀</p>
  </div>
  <div class="paper">
    <div class="field-group">
      <label class="field-label" for="w-to">Pour</label>
      <input type="text" id="w-to" placeholder="À qui écris-tu ?">
    </div>
    <div class="field-group">
      <label class="field-label" for="w-body">Ta lettre</label>
      <textarea id="w-body" placeholder="Commence à écrire…"></textarea>
    </div>
    <div class="field-group">
      <label class="field-label" for="w-from">De la part de</label>
      <input type="text" id="w-from" placeholder="Ton prénom">
    </div>
    <div class="actions">
      <button class="btn btn-primary" onclick="generateLetterLink()">Sceller &amp; envoyer 🎀</button>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : LIEN GÉNÉRÉ
══════════════════════════════════════ -->

<div class="page" id="page-link">
  <div class="link-card">
    <div class="seal">💌</div>
    <h2>Ta lettre est scellée !</h2>
    <p>Envoie ce lien à ton ami — il clique et découvre sa lettre</p>
    <div class="link-box" id="generated-link"></div>
    <div class="copy-ok" id="copy-ok"></div>
    <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap;">
      <button class="btn btn-primary" onclick="copyLink()">Copier le lien</button>
      <button class="btn btn-secondary" onclick="showPage('page-write')">Écrire une autre</button>
    </div>
    <div style="margin-top:20px;text-align:center;">
      <button class="btn-ghost" onclick="showPage('page-home')">← Accueil</button>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : ENVELOPPE (destinataire)
══════════════════════════════════════ -->

<div class="page" id="page-envelope">
  <div class="page-header">
    <h1>Tu as reçu une lettre</h1>
    <p>Clique sur l'enveloppe pour l'ouvrir 🎀</p>
  </div>
  <div class="envelope-scene" id="envelope" onclick="openEnvelope()">
    <div class="envelope-wrap">
      <div class="envelope-body">
        <div class="env-bottom"></div>
        <div class="env-left"></div>
        <div class="env-right"></div>
        <div class="env-letter">✦</div>
      </div>
      <div class="env-flap"><div class="env-flap-inner"></div></div>
      <div class="env-ribbon-h"></div>
      <div class="env-ribbon-v"></div>
      <div class="env-bow">🎀</div>
    </div>
  </div>
  <div class="env-hint" id="env-hint">Cliquer pour ouvrir</div>
</div>

<!-- ══════════════════════════════════════
     PAGE : LETTRE OUVERTE + RÉPONDRE
══════════════════════════════════════ -->

<div class="page" id="page-letter">
  <div class="letter-paper">
    <div class="letter-lines"></div>
    <!-- Fleurs SVG -->
    <svg class="flower-corner flower-tl" viewBox="0 0 96 96" fill="none"><g><ellipse cx="22" cy="10" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="34" cy="22" rx="8" ry="5" fill="#d4748e"/><ellipse cx="22" cy="34" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="10" cy="22" rx="8" ry="5" fill="#d4748e"/><circle cx="22" cy="22" r="7" fill="#f5c8d4" stroke="#c0546e" stroke-width="1"/><circle cx="22" cy="22" r="3.5" fill="#c0546e"/><path d="M22 29 Q18 50 20 70" stroke="#8faa62" stroke-width="2" fill="none" stroke-linecap="round"/><ellipse cx="14" cy="52" rx="9" ry="4.5" fill="#a8bf7a" transform="rotate(-35 14 52)"/><ellipse cx="26" cy="63" rx="8" ry="4" fill="#8faa62" transform="rotate(25 26 63)"/><ellipse cx="52" cy="10" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="60" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><ellipse cx="52" cy="26" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="44" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><circle cx="52" cy="18" r="5" fill="#f9dde4" stroke="#d4748e" stroke-width="0.8"/><circle cx="52" cy="18" r="2.5" fill="#d4748e"/><circle cx="75" cy="14" r="4" fill="#e09ab0"/><ellipse cx="75" cy="9" rx="2.5" ry="4" fill="#c0546e"/><ellipse cx="80" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(90 75 14)"/><ellipse cx="75" cy="19" rx="2.5" ry="4" fill="#c0546e" transform="rotate(180 75 14)"/><ellipse cx="70" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(270 75 14)"/><circle cx="75" cy="14" r="2" fill="#f9dde4"/></g></svg>
    <svg class="flower-corner flower-tr" viewBox="0 0 96 96" fill="none"><g><ellipse cx="22" cy="10" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="34" cy="22" rx="8" ry="5" fill="#d4748e"/><ellipse cx="22" cy="34" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="10" cy="22" rx="8" ry="5" fill="#d4748e"/><circle cx="22" cy="22" r="7" fill="#f5c8d4" stroke="#c0546e" stroke-width="1"/><circle cx="22" cy="22" r="3.5" fill="#c0546e"/><path d="M22 29 Q18 50 20 70" stroke="#8faa62" stroke-width="2" fill="none" stroke-linecap="round"/><ellipse cx="14" cy="52" rx="9" ry="4.5" fill="#a8bf7a" transform="rotate(-35 14 52)"/><ellipse cx="26" cy="63" rx="8" ry="4" fill="#8faa62" transform="rotate(25 26 63)"/><ellipse cx="52" cy="10" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="60" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><ellipse cx="52" cy="26" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="44" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><circle cx="52" cy="18" r="5" fill="#f9dde4" stroke="#d4748e" stroke-width="0.8"/><circle cx="52" cy="18" r="2.5" fill="#d4748e"/><circle cx="75" cy="14" r="4" fill="#e09ab0"/><ellipse cx="75" cy="9" rx="2.5" ry="4" fill="#c0546e"/><ellipse cx="80" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(90 75 14)"/><ellipse cx="75" cy="19" rx="2.5" ry="4" fill="#c0546e" transform="rotate(180 75 14)"/><ellipse cx="70" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(270 75 14)"/><circle cx="75" cy="14" r="2" fill="#f9dde4"/></g></svg>
    <svg class="flower-corner flower-bl" viewBox="0 0 96 96" fill="none"><g><ellipse cx="22" cy="10" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="34" cy="22" rx="8" ry="5" fill="#d4748e"/><ellipse cx="22" cy="34" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="10" cy="22" rx="8" ry="5" fill="#d4748e"/><circle cx="22" cy="22" r="7" fill="#f5c8d4" stroke="#c0546e" stroke-width="1"/><circle cx="22" cy="22" r="3.5" fill="#c0546e"/><path d="M22 29 Q18 50 20 70" stroke="#8faa62" stroke-width="2" fill="none" stroke-linecap="round"/><ellipse cx="14" cy="52" rx="9" ry="4.5" fill="#a8bf7a" transform="rotate(-35 14 52)"/><ellipse cx="26" cy="63" rx="8" ry="4" fill="#8faa62" transform="rotate(25 26 63)"/><ellipse cx="52" cy="10" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="60" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><ellipse cx="52" cy="26" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="44" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><circle cx="52" cy="18" r="5" fill="#f9dde4" stroke="#d4748e" stroke-width="0.8"/><circle cx="52" cy="18" r="2.5" fill="#d4748e"/><circle cx="75" cy="14" r="4" fill="#e09ab0"/><ellipse cx="75" cy="9" rx="2.5" ry="4" fill="#c0546e"/><ellipse cx="80" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(90 75 14)"/><ellipse cx="75" cy="19" rx="2.5" ry="4" fill="#c0546e" transform="rotate(180 75 14)"/><ellipse cx="70" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(270 75 14)"/><circle cx="75" cy="14" r="2" fill="#f9dde4"/></g></svg>
    <svg class="flower-corner flower-br" viewBox="0 0 96 96" fill="none"><g><ellipse cx="22" cy="10" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="34" cy="22" rx="8" ry="5" fill="#d4748e"/><ellipse cx="22" cy="34" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="10" cy="22" rx="8" ry="5" fill="#d4748e"/><circle cx="22" cy="22" r="7" fill="#f5c8d4" stroke="#c0546e" stroke-width="1"/><circle cx="22" cy="22" r="3.5" fill="#c0546e"/><path d="M22 29 Q18 50 20 70" stroke="#8faa62" stroke-width="2" fill="none" stroke-linecap="round"/><ellipse cx="14" cy="52" rx="9" ry="4.5" fill="#a8bf7a" transform="rotate(-35 14 52)"/><ellipse cx="26" cy="63" rx="8" ry="4" fill="#8faa62" transform="rotate(25 26 63)"/><ellipse cx="52" cy="10" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="60" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><ellipse cx="52" cy="26" rx="3.5" ry="5.5" fill="#f0b0c4"/><ellipse cx="44" cy="18" rx="5.5" ry="3.5" fill="#e09ab0"/><circle cx="52" cy="18" r="5" fill="#f9dde4" stroke="#d4748e" stroke-width="0.8"/><circle cx="52" cy="18" r="2.5" fill="#d4748e"/><circle cx="75" cy="14" r="4" fill="#e09ab0"/><ellipse cx="75" cy="9" rx="2.5" ry="4" fill="#c0546e"/><ellipse cx="80" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(90 75 14)"/><ellipse cx="75" cy="19" rx="2.5" ry="4" fill="#c0546e" transform="rotate(180 75 14)"/><ellipse cx="70" cy="14" rx="4" ry="2.5" fill="#d4748e" transform="rotate(270 75 14)"/><circle cx="75" cy="14" r="2" fill="#f9dde4"/></g></svg>

```
<div class="letter-content">
  <div class="letter-to" id="letter-to"></div>
  <div class="ornament">— 🌸 —</div>
  <div class="letter-body" id="letter-body"></div>
  <div class="letter-from" id="letter-from"></div>

  <!-- Section réponse -->
  <div class="reply-section">
    <h3>Veux-tu répondre ? 💌</h3>
    <div class="reply-toggle">
      <button class="btn btn-secondary" id="reply-toggle-btn" onclick="toggleReply()">Écrire une réponse</button>
    </div>
    <div class="reply-form" id="reply-form">
      <div class="field-group" style="margin-top:16px;">
        <label class="field-label" for="r-from">Ton prénom</label>
        <input type="text" id="r-from" placeholder="Comment tu t'appelles ?">
      </div>
      <div class="field-group">
        <label class="field-label" for="r-body">Ta réponse</label>
        <textarea id="r-body" style="min-height:140px;" placeholder="Écris ta réponse…"></textarea>
      </div>
      <div class="reply-actions">
        <button class="btn btn-secondary" onclick="toggleReply()">Annuler</button>
        <button class="btn btn-primary" onclick="generateReplyLink()">Sceller ma réponse 🎀</button>
      </div>
    </div>
  </div>
</div>
```

  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : RÉPONSE ENVOYÉE
══════════════════════════════════════ -->

<div class="page" id="page-reply-sent">
  <div class="success-card">
    <div class="seal">🌸</div>
    <h2>Ta réponse est prête !</h2>
    <p>Envoie ce lien à ton ami pour qu'il puisse lire ta réponse</p>
    <div class="link-box" id="reply-link"></div>
    <div class="copy-ok" id="copy-reply-ok"></div>
    <button class="btn btn-primary" onclick="copyReplyLink()">Copier le lien</button>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : CONNEXION ADMIN
══════════════════════════════════════ -->

<div class="page" id="page-login">
  <button class="btn-ghost back-link" onclick="showPage('page-home')">← Retour</button>
  <div class="login-card">
    <div style="text-align:center;font-size:28px;margin-bottom:16px;">🗝️</div>
    <h2>Mes réponses</h2>
    <p>Entre ton mot de passe pour accéder à ta boîte aux lettres</p>
    <div class="field-group">
      <label class="field-label" for="admin-pw">Mot de passe</label>
      <input type="password" id="admin-pw" placeholder="••••••••" onkeydown="if(event.key==='Enter')checkLogin()">
    </div>
    <div class="login-error" id="login-error"></div>
    <div style="display:flex;justify-content:flex-end;margin-top:8px;">
      <button class="btn btn-primary" onclick="checkLogin()">Entrer</button>
    </div>
    <p style="margin-top:20px;font-size:0.78rem;color:var(--ink-light);font-style:italic;text-align:center;">
      💡 Mot de passe par défaut : <strong>fleurs</strong><br>
      Pour le changer, modifie la ligne <code>ADMIN_PASSWORD</code> dans le fichier HTML
    </p>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : BOÎTE AUX LETTRES (admin)
══════════════════════════════════════ -->

<div class="page" id="page-inbox">
  <button class="btn-ghost back-link" onclick="showPage('page-home')">← Retour</button>
  <div class="page-header">
    <h1>Mes réponses</h1>
    <p>Les lettres que tes amis t'ont envoyées</p>
  </div>
  <div class="inbox-list" id="inbox-list">
    <div class="inbox-empty">Aucune réponse pour l'instant 🌸<br><br><span style="font-size:0.82rem;">Les réponses de tes amis apparaîtront ici une fois que tu auras cliqué sur leur lien de réponse.</span></div>
  </div>
  <div style="margin-top:16px;text-align:center;">
    <button class="btn-ghost" onclick="clearInbox()" style="font-size:0.78rem;color:var(--ink-light);">Vider la boîte</button>
  </div>
</div>

<!-- ══════════════════════════════════════
     PAGE : LIRE UNE RÉPONSE
══════════════════════════════════════ -->

<div class="page" id="page-read-reply">
  <button class="btn-ghost back-link" onclick="showPage('page-inbox')">← Retour aux réponses</button>
  <div class="letter-paper">
    <div class="letter-lines"></div>
    <svg class="flower-corner flower-tl" viewBox="0 0 96 96" fill="none"><g><ellipse cx="22" cy="10" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="34" cy="22" rx="8" ry="5" fill="#d4748e"/><ellipse cx="22" cy="34" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="10" cy="22" rx="8" ry="5" fill="#d4748e"/><circle cx="22" cy="22" r="7" fill="#f5c8d4" stroke="#c0546e" stroke-width="1"/><circle cx="22" cy="22" r="3.5" fill="#c0546e"/><path d="M22 29 Q18 50 20 70" stroke="#8faa62" stroke-width="2" fill="none" stroke-linecap="round"/><ellipse cx="14" cy="52" rx="9" ry="4.5" fill="#a8bf7a" transform="rotate(-35 14 52)"/></g></svg>
    <svg class="flower-corner flower-br" viewBox="0 0 96 96" fill="none"><g><ellipse cx="22" cy="10" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="34" cy="22" rx="8" ry="5" fill="#d4748e"/><ellipse cx="22" cy="34" rx="5" ry="8" fill="#e09ab0"/><ellipse cx="10" cy="22" rx="8" ry="5" fill="#d4748e"/><circle cx="22" cy="22" r="7" fill="#f5c8d4" stroke="#c0546e" stroke-width="1"/><circle cx="22" cy="22" r="3.5" fill="#c0546e"/><path d="M22 29 Q18 50 20 70" stroke="#8faa62" stroke-width="2" fill="none" stroke-linecap="round"/><ellipse cx="26" cy="63" rx="8" ry="4" fill="#8faa62" transform="rotate(25 26 63)"/></g></svg>
    <div class="letter-content">
      <div class="tag">Réponse reçue</div>
      <div class="letter-to" id="reply-to"></div>
      <div class="ornament">— 🌸 —</div>
      <div class="letter-body" id="reply-body"></div>
      <div class="letter-from" id="reply-from-display"></div>
    </div>
  </div>
</div>

<script>
// ══ CONFIG ══
const ADMIN_PASSWORD = 'fleurs'; // ← Change ce mot de passe !
const STORAGE_KEY = 'lettres_inbox';

// ══ NAVIGATION ══
function showPage(id) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
}

// ══ ENCODE / DECODE ══
function enc(obj) { return btoa(unescape(encodeURIComponent(JSON.stringify(obj)))); }
function dec(str) { try { return JSON.parse(decodeURIComponent(escape(atob(str)))); } catch(e) { return null; } }

// ══ ÉCRIRE UNE LETTRE ══
function generateLetterLink() {
  const to   = document.getElementById('w-to').value.trim();
  const body = document.getElementById('w-body').value.trim();
  const from = document.getElementById('w-from').value.trim();
  if (!body) { document.getElementById('w-body').focus(); return; }
  const base = window.location.href.split('?')[0];
  const url  = base + '?l=' + enc({ type:'letter', to, body, from });
  document.getElementById('generated-link').textContent = url;
  showPage('page-link');
}

function copyLink() {
  copy(document.getElementById('generated-link').textContent, 'copy-ok');
}

// ══ OUVRIR L'ENVELOPPE ══
let envelopeOpened = false;
function openEnvelope() {
  if (envelopeOpened) return;
  envelopeOpened = true;
  document.getElementById('envelope').classList.add('open');
  document.getElementById('env-hint').style.opacity = '0';
  setTimeout(() => showPage('page-letter'), 1300);
}

// ══ RÉPONDRE ══
function toggleReply() {
  const form = document.getElementById('reply-form');
  const btn  = document.getElementById('reply-toggle-btn');
  const open = form.classList.toggle('visible');
  btn.textContent = open ? 'Annuler' : 'Écrire une réponse';
}

function generateReplyLink() {
  const from = document.getElementById('r-from').value.trim();
  const body = document.getElementById('r-body').value.trim();
  if (!body) { document.getElementById('r-body').focus(); return; }
  const base = window.location.href.split('?')[0];
  // On inclut le prénom de l'expéditeur original pour contextualiser la réponse
  const originalFrom = document.getElementById('letter-from').textContent.replace(/^—\s*/, '').trim();
  const url = base + '?l=' + enc({ type:'reply', from, body, originalFrom });
  document.getElementById('reply-link').textContent = url;
  showPage('page-reply-sent');
}

function copyReplyLink() {
  copy(document.getElementById('reply-link').textContent, 'copy-reply-ok');
}

// ══ ADMIN LOGIN ══
function checkLogin() {
  const pw = document.getElementById('admin-pw').value;
  if (pw === ADMIN_PASSWORD) {
    document.getElementById('admin-pw').value = '';
    document.getElementById('login-error').textContent = '';
    loadInbox();
    showPage('page-inbox');
  } else {
    document.getElementById('login-error').textContent = 'Mot de passe incorrect 🌹';
  }
}

// ══ BOÎTE AUX LETTRES (localStorage, local seulement) ══
function loadInbox() {
  const data = JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]');
  const list = document.getElementById('inbox-list');
  if (!data.length) {
    list.innerHTML = '<div class="inbox-empty">Aucune réponse pour l\'instant 🌸<br><br><span style="font-size:0.82rem;">Les réponses de tes amis apparaîtront ici quand tu cliqueras sur leur lien de réponse.</span></div>';
    return;
  }
  list.innerHTML = data.map((item, i) => `
    <div class="inbox-item" onclick="readReply(${i})">
      <div class="inbox-item-icon">💌</div>
      <div class="inbox-item-info">
        <div class="inbox-item-from">${esc(item.from || 'Anonyme')}</div>
        <div class="inbox-item-preview">${esc(item.body.substring(0,80))}${item.body.length>80?'…':''}</div>
      </div>
    </div>
  `).join('');
}

function saveReplyToInbox(data) {
  const inbox = JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]');
  inbox.unshift(data);
  localStorage.setItem(STORAGE_KEY, JSON.stringify(inbox));
}

function readReply(i) {
  const data = JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]')[i];
  if (!data) return;
  document.getElementById('reply-to').textContent = data.originalFrom ? 'En réponse à ' + data.originalFrom + ',' : '';
  document.getElementById('reply-body').textContent = data.body;
  document.getElementById('reply-from-display').textContent = data.from || '';
  showPage('page-read-reply');
}

function clearInbox() {
  if (confirm('Vider toute la boîte aux lettres ?')) {
    localStorage.removeItem(STORAGE_KEY);
    loadInbox();
  }
}

// ══ UTILITAIRES ══
function copy(text, feedbackId) {
  navigator.clipboard.writeText(text).then(() => {
    const el = document.getElementById(feedbackId);
    el.textContent = 'Lien copié ✓';
    setTimeout(() => el.textContent = '', 2500);
  });
}
function esc(str) {
  return str.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

// ══ CHARGEMENT DE LA PAGE ══
window.addEventListener('DOMContentLoaded', () => {
  const l = new URLSearchParams(window.location.search).get('l');
  if (!l) return;

  const data = dec(l);
  if (!data) return;

  if (data.type === 'letter') {
    // Afficher la lettre
    document.getElementById('letter-to').textContent   = data.to   ? 'Pour ' + data.to + ',' : '';
    document.getElementById('letter-body').textContent = data.body || '';
    document.getElementById('letter-from').textContent = data.from || '';
    envelopeOpened = false;
    showPage('page-envelope');

  } else if (data.type === 'reply') {
    // C'est une réponse → la sauvegarder et montrer page inbox si connecté
    saveReplyToInbox(data);
    // Afficher directement la réponse
    document.getElementById('reply-to').textContent = data.originalFrom ? 'En réponse à ' + data.originalFrom + ',' : '';
    document.getElementById('reply-body').textContent = data.body;
    document.getElementById('reply-from-display').textContent = data.from || '';
    showPage('page-read-reply');
    // Remplacer le bouton retour pour aller à l'accueil si pas connecté
    document.querySelector('#page-read-reply .back-link').onclick = () => showPage('page-home');
  }
});
</script>

</body>
</html>
