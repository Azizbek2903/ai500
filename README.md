<!doctype html>
<html lang="uz">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>AcaGenie — AI shaxsiy ta'lim yordamchisi (Demo)</title>
<meta name="description" content="AcaGenie: AI-driven personalised learning assistant. Problem→Solution, Team, Why us, Roadmap, Implementation plan." />
<style>
  :root{
    --bg:#0f1724; --card:#0b1220; --accent:#7c3aed; --muted:#9aa4b2;
    --glass: rgba(255,255,255,0.03);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  }
  *{box-sizing:border-box}
  body{margin:0;background:linear-gradient(180deg,var(--bg),#071024);color:#eef2ff;line-height:1.5}
  .container{max-width:1100px;margin:32px auto;padding:24px}
  header{display:flex;align-items:center;justify-content:space-between;gap:16px}
  .logo{display:flex;gap:12px;align-items:center;font-weight:700}
  .logo .mark{width:46px;height:46px;border-radius:10px;background:linear-gradient(135deg,#5b21b6,#06b6d4);display:flex;align-items:center;justify-content:center;font-weight:800;color:white}
  nav a{color:var(--muted);text-decoration:none;margin-left:14px;font-size:14px}
  .hero{display:grid;grid-template-columns:1fr 380px;gap:28px;margin-top:28px;align-items:center}
  .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent); padding:22px;border-radius:14px;box-shadow:0 6px 24px rgba(2,6,23,0.6);border:1px solid rgba(255,255,255,0.03)}
  h1{font-size:28px;margin:0 0 8px}
  .lead{color:var(--muted);margin-bottom:14px}
  .cta{display:inline-block;padding:10px 16px;border-radius:10px;background:linear-gradient(90deg,var(--accent),#06b6d4);color:white;font-weight:600;box-shadow:0 6px 18px rgba(124,58,237,0.18);text-decoration:none}
  .features{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;margin-top:14px}
  .feature{padding:12px;border-radius:10px;background:var(--glass);border:1px solid rgba(255,255,255,0.02)}
  .demo-chat{display:flex;flex-direction:column;height:420px}
  .messages{flex:1;overflow:auto;padding:12px;border-radius:10px;background:linear-gradient(180deg,#021026,#04102a);margin-bottom:12px}
  .msg{margin:8px 0;max-width:78%}
  .msg.user{align-self:flex-end;background:#08223b;padding:10px;border-radius:10px 10px 4px 10px;color:#bfe0ff}
  .msg.bot{background:#0b1530;padding:10px;border-radius:10px 10px 10px 4px;color:#dbeafe}
  .chat-input{display:flex;gap:8px}
  .chat-input input{flex:1;padding:10px;border-radius:10px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit}
  .small{font-size:13px;color:var(--muted)}
  section{margin-top:20px}
  .grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
  .tag{display:inline-block;padding:6px 10px;border-radius:999px;background:rgba(255,255,255,0.03);font-size:13px;color:var(--muted)}
  footer{margin-top:28px;padding:18px;border-radius:12px;text-align:center;color:var(--muted);font-size:13px}
  /* Responsive */
  @media (max-width:980px){
    .hero{grid-template-columns:1fr}
    .grid-3{grid-template-columns:1fr}
  }
</style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo"><div class="mark">AG</div><div>AcaGenie <div class="small">AI Personal Tutor — Demo</div></div></div>
      <nav>
        <a href="#problem">Muammo</a>
        <a href="#team">Jamoa</a>
        <a href="#roadmap">Yo'l xaritasi</a>
        <a href="#plan">Qanday amalga oshirish</a>
      </nav>
    </header>

    <main>
      <div class="hero">
        <div class="card">
          <h1>Har talaba uchun shaxsiy AI repetitor.</h1>
          <p class="lead">AcaGenie - har bir talabaning kuchli va zaif tomonlarini tahlil qilib, moslashtirilgan o'quv reja, interaktiv mashqlar va real-vaqt feedback beradi.</p>
          <a class="cta" href="#plan">Loyihani ko‘rish</a>

          <div class="features" style="margin-top:18px">
            <div class="feature"><strong>Muammo → Yechim</strong><div class="small">Aniq diagnostika, personalizatsiya, natija monitoringi</div></div>
            <div class="feature"><strong>AI Stack</strong><div class="small">GPT-5/LLM, embeddings, vector DB, fine-tuning</div></div>
            <div class="feature"><strong>MVP</strong><div class="small">Adaptive quiz + progress dashboard</div></div>
            <div class="feature"><strong>Host</strong><div class="small">Vercel / Netlify / Firebase</div></div>
          </div>
        </div>

        <aside class="card">
          <h3 style="margin:0 0 8px">Jonli demo chat</h3>
          <div class="demo-chat">
            <div class="messages" id="messages" aria-live="polite">
              <div class="msg bot">Salom! Men AcaGenie demo chatiman. Qanday mavzuda yordam kerak?</div>
            </div>
            <div class="chat-input">
              <input id="chatInput" placeholder="Savolingizni yozing (misol: Algebra — kvadrat tenglama)"/>
              <button id="sendBtn" class="cta" style="padding:8px 12px">Yuborish</button>
            </div>
            <div class="small" style="margin-top:8px">Demo: Bu chat frontendda mock AI javoblarini ko‘rsatadi. API integratsiyasiga tayyor.</div>
          </div>
        </aside>
      </div>

      <!-- REQUIRED SECTIONS -->
      <section id="problem" class="card">
        <h2>1. Muammo → Yechim</h2>
        <p><strong>Muammo:</strong> O‘quvchilar uchun umumiy o‘qitish metodlari individual ehtiyojlarni qondirmayapti: nazariyani tushunmaslik, amal qilinmaydigan mashqlar, motivatsiya pasayishi va o‘qituvchilar resurs cheklovi.</p>
        <p><strong>Yechim (AcaGenie):</strong> AI orqali shaxsiylashtirilgan o‘qish rejalari, adaptiv testlar, darhol feedback va progress monitoring. Platforma:</p>
        <ul class="small">
          <li>1) Avval diagnostika test — zaif/ kuchli tomonlarni aniqlash</li>
          <li>2) Dinamik mashqlar va izohlar (step-by-step)</li>
          <li>3) Progress dashboard va o‘qituvchi/ota-ona hisobotlari</li>
        </ul>
      </section>

      <section id="team" class="card">
        <h2>2. Jamoa (rollar, ko'nikmalar, tex stack, havolalar)</h2>
        <div style="display:flex;gap:12px;flex-wrap:wrap;margin-top:8px">
          <div style="flex:1;min-width:220px">
            <h3>Founder / Product</h3>
            <div class="small">Vision + Biznes strategiya. Link: —</div>
            <div class="tag">Role: Founder</div>
          </div>
          <div style="flex:1;min-width:220px">
            <h3>AI Engineer</h3>
            <div class="small">Ko‘nikmalar: LLM fine-tuning, embeddings, LangChain, prompt engineering.</div>
            <div class="tag">Python • LangChain • OpenAI</div>
          </div>
          <div style="flex:1;min-width:220px">
            <h3>Frontend</h3>
            <div class="small">React / Next.js, Tailwind, accessible UI, testing.</div>
            <div class="tag">React • Next.js • TypeScript</div>
          </div>
          <div style="flex:1;min-width:220px;margin-top:10px">
            <h3>Backend / DevOps</h3>
            <div class="small">Node.js, FastAPI, Supabase/Firebase, Vercel. CI/CD & infra.</div>
            <div class="tag">Node • Supabase • Vercel</div>
          </div>
          <div style="flex:1;min-width:220px;margin-top:10px">
            <h3>UI/UX Designer</h3>
            <div class="small">Figma dizayn, komponent kutubxonasi, accessibility.</div>
            <div class="tag">Figma • Prototyping</div>
          </div>
        </div>

        <h4 style="margin-top:12px">Texnologiyalar (stack)</h4>
        <div class="grid-3" style="margin-top:8px">
          <div class="card small">
            <strong>Frontend</strong><div>React / Next.js, TypeScript, Tailwind</div>
          </div>
          <div class="card small">
            <strong>Backend</strong><div>Node.js / FastAPI, Supabase/Firebase</div>
          </div>
          <div class="card small">
            <strong>AI / ML</strong><div>OpenAI (GPT-5 / GPT-4o), LangChain, Hugging Face, embeddings, Pinecone</div>
          </div>
        </div>
      </section>

      <section id="why" class="card">
        <h2>3. Nima uchun jamoamiz bu muammoni hal qila oladi</h2>
        <p>Jamoamizda mahsulot vizioneri, tajribali AI injener, full-stack dasturchi va dizayner bor. Biz:</p>
        <ul class="small">
          <li>AI va ta'lim mahsulotlarini birlashtira olamiz (prompt engineering + pedagogy)</li>
          <li>Kichik iteratsiyalar bilan tez MVP chiqaramiz va real foydalanuvchi feedbackiga moslashamiz</li>
          <li>Vector DB va test metrikalari yordamida adaptiv algoritmlarni sinovdan o‘tkazamiz</li>
        </ul>
      </section>

      <section id="roadmap" class="card">
        <h2>4. Yo'l xaritasi: Idea → Prototype → MVP → Launched</h2>
        <ol class="small">
          <li><strong>Idea (week 0-1)</strong>: Bozorga tahlil, user persona, core features</li>
          <li><strong>Prototype (week 2-3)</strong>: Figma prototip + basic frontend demo (static)</li>
          <li><strong>MVP (week 4-8)</strong>: Adaptive quiz, basic LLM integration (Q&A & explainers), user auth, progress dashboard</li>
          <li><strong>Launched (week 9-12)</strong>: Beta launch, real-user testing, analytics, monetization (subscription + school licensing)</li>
        </ol>
      </section>

      <section id="plan" class="card">
        <h2>5. Yechimni qanday amalga oshirish (bosqichlar, texnologiyalar, AI vositalari)</h2>
        <h4 style="margin-top:8px">Bosqichlar (texnik)</h4>
        <ol class="small">
          <li><strong>Arxitektura & infra:</strong> Next.js frontend, Node/FastAPI backend, Supabase auth & Postgres, Pinecone yoki Weaviate for vector search.</li>
          <li><strong>Core AI:</strong> Diagnostics pipeline: quiz → embed responses → similarity search → skill profile. LLM prompts for explanations and hints.</li>
          <li><strong>Iteratsiya:</strong> Telemetry, A/B test, metrics (mastery, retention, time-to-improve)</li>
          <li><strong>Security & Compliance:</strong> data retention, opt-in for training, GDPR-friendly patterns</li>
        </ol>

        <h4 style="margin-top:10px">AI vositalari va xizmatlar</h4>
        <div class="small">
          • <strong>OpenAI APIs (GPT-5 Thinking mini / GPT-4o)</strong> — explainers, question answering, content generation.<br>
          • <strong>LangChain</strong> — prompt chaining, orchestration.<br>
          • <strong>Pinecone / Weaviate</strong> — vector DB for embeddings + personalized recommendations.<br>
          • <strong>Hugging Face / Replicate</strong> — optional fine-tuned models or TTS/ASR.<br>
          • <strong>Supabase / Firebase</strong> — auth, DB, realtime features.<br>
          • <strong>Figma</strong> — UI/UX and design system.<br>
          • <strong>CI/CD</strong>: GitHub Actions → Vercel (deploy).
        </div>

        <h4 style="margin-top:10px">Texnik ish rejimi (qisqacha)</h4>
        <ul class="small">
          <li>Prompt library & tests (automated smoke prompts)</li>
          <li>Embeddings generation — store per-user profile</li>
          <li>Real-time assistant — socket/Realtime to push hints during quiz</li>
          <li>Monitoring — Sentry + analytics</li>
        </ul>

        <h4 style="margin-top:10px">MVP minimal xususiyatlar</h4>
        <div class="small">Diagnostika test, 10 adaptive mashq turi, AI explainers, progress dashboard, user auth, admin panel.</div>
      </section>

      <section class="card">
        <h2>Keyingi qadamlar & Deploy</h2>
        <p class="small">Bu demo faylni joylash: <strong>1)</strong> GitHub-ga commit qiling, <strong>2)</strong> Vercel yoki Netlify-ga ulab deploy qiling. Quyidagi single-click variantlar yetarli:</p>
        <div style="display:flex;gap:10px;flex-wrap:wrap;margin-top:8px">
          <div class="tag">GitHub repo</div>
          <div class="tag">Vercel Deploy</div>
          <div class="tag">Netlify Deploy</div>
        </div>
        <p class="small" style="margin-top:8px">Agar xohlasangiz, men faylni GitHub-ready qilib qo‘yib, deploy linkini hozirshayoq taqdim etaman.</p>
      </section>

    </main>

    <footer class="card">
      <div style="font-weight:600">AcaGenie — Demo</div>
      <div class="small" style="margin-top:6px">Sahifa: muammo→yechim, jamoa, nima uchun biz, roadmap, va amalga oshirish rejasi to'liq. Tayyor deploy uchun yordam kerak bo'lsa yozing.</div>
      <div style="margin-top:8px" class="small">© AcaGenie • Demo version</div>
    </footer>
  </div>

<script>
  // Simple mock AI demo logic (frontend only)
  const messagesEl = document.getElementById('messages');
  const input = document.getElementById('chatInput');
  const btn = document.getElementById('sendBtn');

  function append(role, text){
    const d = document.createElement('div');
    d.className = 'msg ' + (role === 'user' ? 'user': 'bot');
    d.textContent = text;
    messagesEl.appendChild(d);
    messagesEl.scrollTop = messagesEl.scrollHeight;
  }

  function mockAiReply(userText){
    // lightweight heuristics to demonstrate "smart" replies
    const t = userText.toLowerCase();
    if(t.includes('algebra') || t.includes('kvadrat') || t.includes('tenglama')){
      return "Ajoyib — kvadrat tenglamani bosqichma-bosq ko‘rib chiqamiz: ax^2+bx+c=0 - diskriminant D=b^2-4ac hisoblanadi. D>0 bo'lsa 2 yechim, D=0 -> 1 yechim. Xohlasangiz misol yechib beraman.";
    }
    if(t.includes('ingliz') || t.includes('english')){
      return "Ingliz tilida so'zlarni kontekst orqali o'rgatamiz: biron gap yuboring, men grammatik va sinonimlarni ko'rsataman.";
    }
    if(t.includes('diagnostika') || t.includes('test')){
      return "Diagnostika testi: sizga 8ta savol yuboraman va zaif tomonlaringizni qayd qilaman. Boshlashni xohlaysizmi?";
    }
    // default
    const defaults = [
      "Ajoyib savol! Qisqacha: bu mavzuda avval qaysi asosiy qiyinchilikni sezayapsiz?",
      "Men tushunmadim — aniqlik kiritasizmi? (masalan: fan, daraja, vaqt)",
      "Xo‘p — mana qisqacha action plan: 1) Quick diagnostic 2) Personalized exercises 3) Progress checks."
    ];
    return defaults[Math.floor(Math.random()*defaults.length)];
  }

  btn.addEventListener('click', ()=>{
    const v = input.value.trim();
    if(!v) return;
    append('user', v);
    input.value = '';
    // small simulated thinking delay
    setTimeout(()=> append('bot', '...'), 300);
    setTimeout(()=> {
      // remove the '...' last bot message
      const last = Array.from(messagesEl.querySelectorAll('.msg.bot')).pop();
      if(last && last.textContent === '...') last.remove();
      append('bot', mockAiReply(v));
    }, 900);
  });

  input.addEventListener('keydown', (e)=>{ if(e.key === 'Enter') btn.click(); });
</script>
</body>
</html>
