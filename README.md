<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>SMART KIDS GAMES — ألعاب الإنجليزية</title>
  <meta name="description" content="ألعاب تعليمية ممتعة للأطفال لتعلّم قواعد الإنجليزية." />

  <style>
    :root{
      --bg1:#f6fbff;
      --bg2:#fff7fb;
      --card:#ffffff;
      --ink:#0f172a;
      --muted:#475569;
      --brand:#ef2b5b;
      --brand2:#6d28d9;
      --ok:#16a34a;
      --bad:#ef4444;
      --shadow:0 14px 40px rgba(2,6,23,.12);
      --r:22px;
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, "Noto Kufi Arabic", Arial, sans-serif;
      color:var(--ink);
      background:
        radial-gradient(1100px 500px at 10% 10%, #dff5ff 0%, transparent 60%),
        radial-gradient(900px 500px at 90% 20%, #ffe0ec 0%, transparent 55%),
        linear-gradient(180deg, var(--bg1), var(--bg2));
      min-height:100vh;
    }

    /* full width container (بالعرض) */
    .wrap{
      width:min(1200px, calc(100vw - 28px));
      margin: 18px auto 60px;
    }

    .topbar{
      background: linear-gradient(90deg, var(--brand2), #2563eb);
      color:#fff;
      border-radius: 26px;
      box-shadow: var(--shadow);
      padding: 18px 18px;
      position: relative;
      overflow:hidden;
    }
    .topbar::before{
      content:"";
      position:absolute; inset:-120px -120px auto auto;
      width:240px; height:240px;
      background: radial-gradient(circle at 30% 30%, rgba(255,255,255,.35), transparent 60%);
      transform: rotate(18deg);
    }
    .brandrow{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      flex-wrap:wrap;
      position:relative;
      z-index:1;
    }
    .title{
      display:flex;
      flex-direction:column;
      gap:6px;
      min-width:260px;
    }
    .title h1{
      margin:0;
      font-size: clamp(22px, 2.6vw, 34px);
      line-height:1.15;
      letter-spacing:.2px;
    }
    .title p{
      margin:0;
      opacity:.92;
      font-size: 14.5px;
    }

    .pillrow{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      align-items:center;
      justify-content:flex-start;
    }
    .pill{
      background: rgba(255,255,255,.18);
      border:1px solid rgba(255,255,255,.25);
      color:#fff;
      padding:10px 12px;
      border-radius: 999px;
      font-weight:700;
      font-size:13px;
      display:flex; align-items:center; gap:8px;
      backdrop-filter: blur(8px);
    }
    .pill small{opacity:.9; font-weight:600}

    .nav{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:14px;
      position:relative;
      z-index:1;
    }
    .btn{
      border:0;
      cursor:pointer;
      padding: 12px 14px;
      border-radius: 14px;
      font-weight:800;
      font-size:14px;
      box-shadow: 0 10px 25px rgba(2,6,23,.12);
      transition: transform .12s ease, filter .12s ease;
      display:inline-flex; gap:9px; align-items:center;
    }
    .btn:hover{transform: translateY(-1px); filter:brightness(1.02)}
    .btn:active{transform: translateY(0px); filter:brightness(.98)}
    .btn.primary{background: #fff; color: #0f172a}
    .btn.accent{background: var(--brand); color:#fff}
    .btn.ghost{background: rgba(255,255,255,.18); color:#fff; border:1px solid rgba(255,255,255,.25)}

    .grid{
      display:grid;
      grid-template-columns: repeat(12, 1fr);
      gap:16px;
      margin-top:16px;
    }

    .card{
      background: var(--card);
      border-radius: var(--r);
      box-shadow: var(--shadow);
      padding: 16px;
      border: 1px solid rgba(15,23,42,.06);
    }

    .menu{
      grid-column: span 12;
      display:grid;
      grid-template-columns: repeat(12, 1fr);
      gap:16px;
    }

    .gameCard{
      grid-column: span 6;
      padding: 18px;
      border-radius: 22px;
      position:relative;
      overflow:hidden;
      min-height: 170px;
      background: linear-gradient(135deg, #fff, #fff);
    }
    .gameCard:nth-child(1){
      background: linear-gradient(135deg, #fff7e6, #ffe3f2);
    }
    .gameCard:nth-child(2){
      background: linear-gradient(135deg, #e8fff4, #dff0ff);
    }
    .gameCard:nth-child(3){
      background: linear-gradient(135deg, #eef2ff, #e0f2fe);
    }

    .gameCard h3{
      margin: 0 0 8px;
      font-size: 18.5px;
      display:flex; align-items:center; gap:10px;
    }
    .gameCard p{
      margin: 0 0 14px;
      color: var(--muted);
      line-height: 1.55;
      font-weight:600;
      font-size: 14.5px;
    }
    .tag{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding: 8px 10px;
      border-radius: 999px;
      font-weight:800;
      font-size: 12.5px;
      background: rgba(15,23,42,.06);
      color: #0f172a;
    }

    .playRow{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      align-items:center;
      justify-content:space-between;
    }
    .playRow .btn{
      box-shadow:none;
      border-radius: 999px;
      padding: 12px 14px;
    }

    .panel{
      grid-column: span 12;
      display:none;
      padding: 18px;
    }
    .panel.active{display:block}

    .panelHead{
      display:flex;
      gap:12px;
      flex-wrap:wrap;
      align-items:center;
      justify-content:space-between;
      margin-bottom: 12px;
    }
    .panelHead h2{
      margin:0;
      font-size: 20px;
      display:flex; gap:10px; align-items:center;
    }
    .panelHead .sub{
      margin:0;
      color: var(--muted);
      font-weight:700;
      font-size: 14px;
    }

    .hud{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      align-items:center;
      justify-content:flex-start;
      margin-top:10px;
    }
    .chip{
      background: rgba(2,6,23,.06);
      padding: 9px 12px;
      border-radius: 999px;
      font-weight:900;
      font-size: 13px;
      display:inline-flex; gap:8px; align-items:center;
    }
    .chip.ok{background: rgba(22,163,74,.12); color: #0a7a33}
    .chip.bad{background: rgba(239,68,68,.12); color: #b91c1c}

    .bar{
      width: 260px;
      height: 10px;
      background: rgba(2,6,23,.08);
      border-radius: 999px;
      overflow:hidden;
    }
    .bar > i{
      display:block;
      height:100%;
      width:0%;
      background: linear-gradient(90deg, var(--brand2), var(--brand));
      border-radius: 999px;
      transition: width .2s ease;
    }

    .qbox{
      margin-top: 14px;
      display:grid;
      grid-template-columns: 1fr;
      gap: 12px;
    }

    .question{
      background: linear-gradient(180deg, #ffffff, #fbfdff);
      border: 1px solid rgba(15,23,42,.08);
      border-radius: 18px;
      padding: 16px;
      box-shadow: 0 10px 25px rgba(2,6,23,.08);
    }
    .question h3{
      margin:0 0 10px;
      font-size: 17px;
      line-height: 1.6;
    }
    .choices{
      display:grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
    }
    .choice{
      border: 1px solid rgba(15,23,42,.10);
      background: #fff;
      border-radius: 14px;
      padding: 12px;
      font-weight:900;
      cursor:pointer;
      transition: transform .12s ease, border-color .12s ease, background .12s ease;
      text-align:center;
      user-select:none;
    }
    .choice:hover{transform: translateY(-1px)}
    .choice.ok{
      background: rgba(22,163,74,.10);
      border-color: rgba(22,163,74,.35);
    }
    .choice.bad{
      background: rgba(239,68,68,.10);
      border-color: rgba(239,68,68,.35);
    }

    .note{
      color: var(--muted);
      font-weight:700;
      font-size: 13.5px;
      margin-top: 10px;
      line-height:1.6;
    }

    .footer{
      margin-top: 16px;
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      align-items:center;
      justify-content:space-between;
      color: var(--muted);
      font-weight:700;
      font-size: 13px;
    }

    /* responsive */
    @media (max-width: 820px){
      .gameCard{grid-column: span 12}
      .choices{grid-template-columns: 1fr}
      .bar{width: 100%}
    }
  </style>
</head>

<body>
  <div class="wrap">
    <header class="topbar">
      <div class="brandrow">
        <div class="title">
          <h1>🎮 SMART KIDS GAMES — ألعاب الإنجليزية للأطفال</h1>
          <p>تعلّم + لعب + تحدّي ✨ (مناسبة للابتدائي والإعدادي)</p>
        </div>

        <div class="pillrow">
          <div class="pill">✅ <span>تفاعلية</span> <small>بدون إضافات</small></div>
          <div class="pill">⭐ <span>نظام نقاط</span> <small>تشجيع</small></div>
          <div class="pill">🔊 <span>مؤثرات</span> <small>اختياري</small></div>
        </div>
      </div>

      <div class="nav">
        <button class="btn primary" type="button" onclick="showPanel('home')">🏠 الرئيسية</button>
        <button class="btn ghost" type="button" onclick="showPanel('present')">✅ Present Simple</button>
        <button class="btn ghost" type="button" onclick="showPanel('past')">⏳ Past Simple</button>
        <button class="btn accent" type="button" onclick="toggleSound()">🔊 تشغيل/إيقاف الصوت</button>
      </div>
    </header>

    <main class="grid">

      <!-- HOME -->
      <section id="home" class="card panel active">
        <div class="panelHead">
          <div>
            <h2>🎯 اختاري لعبة وابدئي</h2>
            <p class="sub">اضغطي “ابدئي الآن” — ستحصلين على نقاط مع كل إجابة صحيحة ⭐</p>
          </div>
          <div class="hud">
            <span class="chip">⭐ النقاط: <b id="totalScore">0</b></span>
            <span class="chip">🔊 الصوت: <b id="soundState">OFF</b></span>
          </div>
        </div>

        <div class="menu">
          <div class="gameCard">
            <h3>✅ Present Simple <span class="tag">اختاري الإجابة</span></h3>
            <p>اختاري الفعل الصحيح (He/She/It + s) — ومع (I/You/We/They) بدون s.</p>
            <div class="playRow">
              <button class="btn accent" type="button" onclick="startGame('present')">▶ ابدئي الآن</button>
              <span class="tag">مستوى: سهل–متوسط</span>
            </div>
          </div>

          <div class="gameCard">
            <h3>⏳ Past Simple <span class="tag">Regular / Irregular</span></h3>
            <p>اختاري الماضي الصحيح للفعل: أفعال منتظمة (ed) + أفعال شاذة (go→went).</p>
            <div class="playRow">
              <button class="btn accent" type="button" onclick="startGame('past')">▶ ابدئي الآن</button>
              <span class="tag">مستوى: متوسط</span>
            </div>
          </div>

          <div class="gameCard">
            <h3>🧩 قريبًا: Word Games <span class="tag">Spelling</span></h3>
            <p>ألعاب كلمات وتكوين جُمل ومطابقة الصور… قريبًا إن شاء الله.</p>
            <div class="playRow">
              <button class="btn primary" type="button" onclick="alert('قريبًا ✨')">✨ قريبًا</button>
              <span class="tag">قيد التطوير</span>
            </div>
          </div>
        </div>

        <div class="footer">
          <span>© SMART KIDS WITH CONNECT</span>
          <span>ملاحظة: هذه الصفحة تعمل على GitHub Pages لأن WordPress.com يمنع تشغيل JavaScript.</span>
        </div>
      </section>

      <!-- PRESENT SIMPLE -->
      <section id="present" class="card panel">
        <div class="panelHead">
          <div>
            <h2>✅ لعبة المضارع البسيط (Present Simple)</h2>
            <p class="sub">اختاري الإجابة الصحيحة — ثم انتقلي للسؤال التالي</p>
          </div>
          <div class="hud">
            <span class="chip ok">⭐ نقاط اللعبة: <b id="psScore">0</b></span>
            <span class="chip">🧠 سؤال: <b id="psIndex">1</b>/<b id="psTotal">1</b></span>
            <span class="chip"><span class="bar"><i id="psBar"></i></span></span>
            <button class="btn primary" type="button" onclick="resetGame('present')">🔄 إعادة</button>
          </div>
        </div>

        <div class="qbox">
          <div class="question">
            <h3 id="psQ">...</h3>
            <div class="choices" id="psChoices"></div>
            <div class="note" id="psNote">💡 تلميح: He/She/It غالبًا يأخذ (s / es)</div>
          </div>
        </div>
      </section>

      <!-- PAST SIMPLE -->
      <section id="past" class="card panel">
        <div class="panelHead">
          <div>
            <h2>⏳ لعبة الماضي البسيط (Past Simple)</h2>
            <p class="sub">اختاري الماضي الصحيح للفعل (Regular/Irregular)</p>
          </div>
          <div class="hud">
            <span class="chip ok">⭐ نقاط اللعبة: <b id="pastScore">0</b></span>
            <span class="chip">🧠 سؤال: <b id="pastIndex">1</b>/<b id="pastTotal">1</b></span>
            <span class="chip"><span class="bar"><i id="pastBar"></i></span></span>
            <button class="btn primary" type="button" onclick="resetGame('past')">🔄 إعادة</button>
          </div>
        </div>

        <div class="qbox">
          <div class="question">
            <h3 id="pastQ">...</h3>
            <div class="choices" id="pastChoices"></div>
            <div class="note" id="pastNote">💡 تلميح: الأفعال الشاذة لازم حفظ (go→went / see→saw)</div>
          </div>
        </div>
      </section>

    </main>
  </div>

  <script>
    // ====== SOUND (WebAudio) ======
    let soundOn = false;
    const AudioCtx = window.AudioContext || window.webkitAudioContext;
    let ctx = null;

    function beep(freq=660, ms=120, type='sine', gain=0.06){
      if(!soundOn) return;
      try{
        if(!ctx) ctx = new AudioCtx();
        const o = ctx.createOscillator();
        const g = ctx.createGain();
        o.type = type;
        o.frequency.value = freq;
        g.gain.value = gain;
        o.connect(g); g.connect(ctx.destination);
        o.start();
        setTimeout(()=>{ o.stop(); }, ms);
      }catch(e){}
    }

    function toggleSound(){
      soundOn = !soundOn;
      document.getElementById('soundState').textContent = soundOn ? 'ON' : 'OFF';
      beep(880, 120, 'triangle', 0.05);
    }

    // ====== NAV / PANELS ======
    function showPanel(id){
      document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
      document.getElementById(id).classList.add('active');
      window.scrollTo({top: 0, behavior: 'smooth'});
    }

    // ====== DATA ======
    const presentQs = [
      { q:"She ____ to school every day.", a:"goes", choices:["go","goes","going","went"], tip:"She = مفرد → goes" },
      { q:"They ____ football on Fridays.", a:"play", choices:["plays","played","play","playing"], tip:"They = جمع → play" },
      { q:"My father ____ tea in the morning.", a:"drinks", choices:["drink","drinks","drinking","drank"], tip:"He/She/It → s" },
      { q:"I ____ my homework after school.", a:"do", choices:["does","do","did","doing"], tip:"I → بدون s" },
      { q:"The bus ____ at 7:00.", a:"starts", choices:["start","starts","starting","started"], tip:"The bus = مفرد" },
      { q:"We ____ English at school.", a:"study", choices:["studies","study","studying","studied"], tip:"We = جمع" }
    ];

    const pastQs = [
      { q:"Yesterday, I ____ to the park. (go)", a:"went", choices:["goed","went","goes","going"], tip:"go → went (شاذ)" },
      { q:"She ____ a cake last night. (make)", a:"made", choices:["maked","made","make","makes"], tip:"make → made (شاذ)" },
      { q:"They ____ TV after dinner. (watch)", a:"watched", choices:["watch","watched","watching","watches"], tip:"watch + ed" },
      { q:"We ____ a photo. (take)", a:"took", choices:["taked","took","take","takes"], tip:"take → took (شاذ)" },
      { q:"He ____ his room. (clean)", a:"cleaned", choices:["cleaned","cleant","clean","cleans"], tip:"clean + ed" },
      { q:"I ____ my friend. (see)", a:"saw", choices:["seed","saw","see","seen"], tip:"see → saw (شاذ)" }
    ];

    // ====== STATE ======
    let totalScore = 0;

    const state = {
      present: { i:0, score:0, lock:false },
      past: { i:0, score:0, lock:false }
    };

    // ====== HELPERS ======
    function shuffle(arr){
      const a = [...arr];
      for(let i=a.length-1;i>0;i--){
        const j = Math.floor(Math.random()*(i+1));
        [a[i],a[j]] = [a[j],a[i]];
      }
      return a;
    }

    function setTotalScore(){
      document.getElementById('totalScore').textContent = totalScore;
    }

    function startGame(which){
      resetGame(which);
      showPanel(which);
      render(which);
    }

    function resetGame(which){
      state[which].i = 0;
      state[which].score = 0;
      state[which].lock = false;

      if(which === 'present'){
        document.getElementById('psScore').textContent = '0';
      }else{
        document.getElementById('pastScore').textContent = '0';
      }
      render(which);
      beep(520, 120, 'sine', 0.05);
    }

    function render(which){
      const isPS = which === 'present';
      const qs = isPS ? presentQs : pastQs;
      const s = state[which];

      const totalEl = isPS ? 'psTotal' : 'pastTotal';
      const indexEl = isPS ? 'psIndex' : 'pastIndex';
      document.getElementById(totalEl).textContent = qs.length;
      document.getElementById(indexEl).textContent = Math.min(s.i+1, qs.length);

      const barEl = document.getElementById(isPS ? 'psBar' : 'pastBar');
      barEl.style.width = ((s.i)/qs.length)*100 + '%';

      // finished
      if(s.i >= qs.length){
        const qEl = document.getElementById(isPS ? 'psQ' : 'pastQ');
        const cEl = document.getElementById(isPS ? 'psChoices' : 'pastChoices');
        const noteEl = document.getElementById(isPS ? 'psNote' : 'pastNote');

        qEl.textContent = `🎉 ممتاز! خلّصتي اللعبة. مجموعك: ${s.score} ⭐`;
        cEl.innerHTML = `
          <button class="choice ok" type="button" onclick="resetGame('${which}')">🔄 العب تاني</button>
          <button class="choice" type="button" onclick="showPanel('home')">🏠 رجوع للرئيسية</button>
        `;
        noteEl.textContent = "✨ لو عايزة أضيف مستويات أكتر/أسئلة من منهجك ابعتيلي المحتوى.";
        barEl.style.width = '100%';
        return;
      }

      const item = qs[s.i];
      const qEl = document.getElementById(isPS ? 'psQ' : 'pastQ');
      const cEl = document.getElementById(isPS ? 'psChoices' : 'pastChoices');
      const noteEl = document.getElementById(isPS ? 'psNote' : 'pastNote');

      qEl.textContent = `سؤال ${s.i+1}: ${item.q}`;
      noteEl.textContent = `💡 تلميح: ${item.tip}`;

      s.lock = false;
      const choices = shuffle(item.choices);

      cEl.innerHTML = "";
      choices.forEach(ch=>{
        const b = document.createElement('button');
        b.className = 'choice';
        b.type = 'button';
        b.textContent = ch;
        b.onclick = () => answer(which, ch, b);
        cEl.appendChild(b);
      });
    }

    function answer(which, picked, btn){
      const isPS = which === 'present';
      const qs = isPS ? presentQs : pastQs;
      const s = state[which];
      if(s.lock) return;
      s.lock = true;

      const item = qs[s.i];
      const buttons = btn.parentElement.querySelectorAll('.choice');

      buttons.forEach(b=>{
        if(b.textContent === item.a) b.classList.add('ok');
        if(b.textContent === picked && picked !== item.a) b.classList.add('bad');
        b.disabled = true;
      });

      if(picked === item.a){
        s.score += 1;
        totalScore += 1;
        setTotalScore();
        beep(880, 120, 'triangle', 0.06);
        beep(1320, 90, 'triangle', 0.04);
      }else{
        beep(220, 160, 'sawtooth', 0.04);
      }

      // update score UI
      if(isPS){
        document.getElementById('psScore').textContent = s.score;
      }else{
        document.getElementById('pastScore').textContent = s.score;
      }

      // next
      setTimeout(()=>{
        s.i += 1;
        render(which);
      }, 700);
    }

    // init
    setTotalScore();
    document.getElementById('soundState').textContent = 'OFF';
    render('present');
    render('past');
  </script>
</body>
</html>
