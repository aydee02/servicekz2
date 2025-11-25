<!-- index.html -->
<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>ServiceKz — Главная</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --g1: #076653;
      --g2: #E2FBCE;
      --g3: #E3EF26;
      --bg: #f7faf6;
      --muted: #6b6f72;
      --card: #ffffff;
      --glass: rgba(255,255,255,0.65);
      --radius: 14px;
      --shadow: 0 10px 30px rgba(6,30,20,0.08);
      --accent-gradient: linear-gradient(135deg, var(--g1) 0%, var(--g2) 60%, var(--g3) 100%);
    }
    *{box-sizing:border-box}
    html,body{height:100%;font-family:Inter,system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;color:#033; background:linear-gradient(180deg,#f6fbf9 0%, #f4f9f4 100%);margin:0}
    a{color:inherit;text-decoration:none}
    header{position:sticky;top:0;backdrop-filter: blur(6px);background:linear-gradient(180deg, rgba(255,255,255,0.6), rgba(255,255,255,0.45));border-bottom:1px solid rgba(6,30,20,0.04);padding:18px 36px;display:flex;align-items:center;gap:20px;z-index:50}
    .logo{display:flex;align-items:center;gap:12px;font-weight:700}
    .logo .mark{width:46px;height:46px;border-radius:10px;background:var(--accent-gradient);display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;box-shadow:var(--shadow)}
    nav{margin-left:10px;display:flex;gap:18px;align-items:center}
    .btn{padding:10px 16px;border-radius:10px;background:var(--accent-gradient);color:#04331f;font-weight:700;border:none;cursor:pointer;box-shadow:0 6px 18px rgba(7,102,83,0.12)}
    .btn.secondary{background:transparent;border:1px solid rgba(7,102,83,0.08);font-weight:600;color:var(--g1)}
    .lang-switch{margin-left:auto;display:flex;gap:8px;align-items:center}
    .lang-switch button{background:transparent;border:none;padding:6px 10px;border-radius:8px;cursor:pointer;color:var(--muted)}
    .lang-switch button.active{background:rgba(7,102,83,0.08);color:var(--g1);font-weight:700}
    .container{max-width:1200px;margin:28px auto;padding:0 22px}
    .search-card{background:linear-gradient(180deg,rgba(255,255,255,0.9), rgba(255,255,255,0.85));padding:18px;border-radius:16px;display:flex;gap:12px;align-items:center;box-shadow:var(--shadow)}
    .search-field{flex:1;display:flex;gap:10px;align-items:center}
    .search-field input{width:100%;padding:12px 14px;border-radius:10px;border:1px solid #e6efe7;background:transparent;outline:none}
    .map-block{margin-top:18px;border-radius:16px;padding:18px;background:var(--card);box-shadow:var(--shadow);display:grid;grid-template-columns:1fr 360px;gap:18px;align-items:start}
    .map-canvas{height:320px;border-radius:10px;background:linear-gradient(180deg,#eaf7ee,#fff);display:flex;align-items:center;justify-content:center;color:var(--g1);font-weight:700}
    .map-sidebar{display:flex;flex-direction:column;gap:10px}
    .chips{display:flex;gap:8px;flex-wrap:wrap}
    .chip{padding:8px 10px;background:linear-gradient(90deg,#fff,#f7fff0);border-radius:999px;border:1px solid rgba(7,102,83,0.06);font-weight:600;color:var(--g1)}
    .features{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;margin-top:20px}
    .feature{background:linear-gradient(180deg,#fff,#fbfff6);padding:18px;border-radius:12px;display:flex;gap:12px;align-items:center;box-shadow:var(--shadow)}
    .feature .icon{width:56px;height:56px;border-radius:12px;display:flex;align-items:center;justify-content:center;background:var(--accent-gradient);color:#fff;font-weight:800}
    .how{margin-top:20px;background:linear-gradient(180deg,#fff,#fbfff8);padding:18px;border-radius:12px;display:flex;gap:12px;align-items:center;box-shadow:var(--shadow)}
    .steps{display:flex;gap:12px;flex:1}
    .step{background:linear-gradient(180deg,#fff,#f8fff4);padding:18px;border-radius:12px;flex:1;text-align:center;transition:transform .25s ease, box-shadow .25s ease;cursor:pointer}
    .step:hover{transform:translateY(-6px);box-shadow:0 12px 30px rgba(6,30,20,0.06)}
    .masters{margin-top:20px;display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
    .card{background:var(--card);padding:14px;border-radius:12px;box-shadow:var(--shadow);display:flex;gap:12px;align-items:center}
    .avatar{width:64px;height:64px;border-radius:12px;background:linear-gradient(135deg,#dff6e9,#eafbe6);display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--g1)}
    .rating{color:#6a8c6f;font-weight:700}
    footer{padding:28px 36px;margin-top:28px;background:linear-gradient(180deg,#fff,#f7fff7);border-top:1px solid rgba(6,30,20,0.03)}
    
    .modal-backdrop{position:fixed;inset:0;background:rgba(2,10,6,0.36);display:none;align-items:center;justify-content:center;padding:24px;z-index:120}
    .modal{width:720px;max-width:98%;background:linear-gradient(180deg,#fff,#fbfff8);padding:18px;border-radius:14px;box-shadow:0 20px 40px rgba(5,30,20,0.3)}
    .modal h3{margin:0 0 8px}
    .form-row{display:flex;gap:10px;margin-top:8px}
    .form-row > *{flex:1}
    textarea{min-height:120px;padding:12px;border-radius:10px;border:1px solid #e6efe7;resize:vertical}
    .small{font-size:13px;color:var(--muted)}
    
    .fm-enter{transform:translateY(12px) scale(.98);opacity:0}
    .fm-enter.in{transform:none;opacity:1;transition:all .48s cubic-bezier(.2,.9,.3,1)}
    .fm-hover{transition:transform .28s cubic-bezier(.2,.9,.3,1)}
    .badge{background:linear-gradient(90deg,var(--g1),var(--g2));color:#04331f;padding:6px 10px;border-radius:10px;font-weight:700;display:inline-block}
    @media (max-width:980px){
      .map-block{grid-template-columns:1fr}
      .masters{grid-template-columns:repeat(2,1fr)}
      header{padding:12px}
      .container{padding:0 12px}
    }
  </style>
</head>
<body>
  <header>
    <div class="logo" aria-hidden="true">
      <div class="mark">SK</div>
      <div>
        <div style="font-size:18px">ServiceKz</div>
        <div style="font-size:12px;color:var(--muted)">marketplace локальных услуг</div>
      </div>
    </div>

    <nav aria-label="Main navigation">
      <a href="#" onclick="navigateTo('home')"><strong data-i18n="nav.home">Главная</strong></a>
      <a href="catalog.html"><span data-i18n="nav.catalog">Каталог</span></a>
      <a href="master_profile.html"><span data-i18n="nav.masters">Мастера</span></a>
    </nav>

    <div class="lang-switch" role="navigation" aria-label="Language">
      <button id="btn-ru" class="active" onclick="switchLang('ru')">RU</button>
      <button id="btn-kz" onclick="switchLang('kz')">KZ</button>
      <button class="btn" onclick="openCreateRequest()"><span data-i18n="header.create">Создать заявку</span></button>
    </div>
  </header>

  <main class="container">
    
    <div class="search-card fm-enter in">
      <div style="flex:1" class="search-field">
        <input id="s-service" placeholder="Что нужно сделать?" data-i18n-placeholder="search.service">
        <input id="s-city" placeholder="Город" data-i18n-placeholder="search.city" style="width:240px">
      </div>
      <button class="btn" onclick="doSearch()"><span data-i18n="search.find">Найти</span></button>
    </div>

    
    <div class="map-block">
      <div class="map-canvas" id="kaz-map" title="Карта Казахстана (заглушка)">
        
        <svg width="320" height="240" viewBox="0 0 320 240" aria-hidden="true">
          <rect width="320" height="240" rx="12" fill="url(#g)" />
          <defs>
            <linearGradient id="g" x1="0" x2="1">
              <stop offset="0" stop-color="#eaf7ee"/>
              <stop offset="1" stop-color="#fff"/>
            </linearGradient>
          </defs>
          <g transform="translate(32,18)" fill="none" stroke="#076653" stroke-width="2" stroke-linejoin="round">
            <path d="M10 40 L60 30 L110 50 L150 30 L200 60 L260 58 L280 90 L240 110 L200 120 L150 110 L100 140 L40 120 L10 100 Z" opacity="0.9"/>
          </g>
          
          <circle cx="70" cy="80" r="6" fill="#E3EF26" />
          <circle cx="180" cy="60" r="6" fill="#E2FBCE" />
          <circle cx="220" cy="120" r="6" fill="#076653" />
        </svg>
      </div>
      <aside class="map-sidebar">
        <div class="chips">
          <div class="chip">Нур-Султан</div>
          <div class="chip">Алматы</div>
          <div class="chip">Шымкент</div>
          <div class="chip">Костанай</div>
        </div>
        <div style="margin-top:10px">
          <div style="font-weight:700" data-i18n="map.title">Мастера рядом</div>
          <div class="small" id="nearby-list">Показаны города с доступными мастерами.</div>
        </div>
        <div style="margin-top:auto">
          <div class="badge" id="secure-badge" data-i18n="header.secure">Платёж защищён</div>
        </div>
      </aside>
    </div>

    <!-- Features -->
    <div class="features">
      <div class="feature fm-hover">
        <div class="icon">ES</div>
        <div>
          <div style="font-weight:700" data-i18n="feat.escrow">Эскроу — безопасность</div>
          <div class="small" data-i18n="feat.escrowDesc">Деньги переводятся только после подтверждения работы.</div>
        </div>
      </div>
      <div class="feature fm-hover">
        <div class="icon">DOC</div>
        <div>
          <div style="font-weight:700" data-i18n="feat.verify">Проверка документов</div>
          <div class="small" data-i18n="feat.verifyDesc">Сертификаты и лицензии в профиле мастера.</div>
        </div>
      </div>
      <div class="feature fm-hover">
        <div class="icon">QA</div>
        <div>
          <div style="font-weight:700" data-i18n="feat.guarantee">Гарантия качества</div>
          <div class="small" data-i18n="feat.guaranteeDesc">Гарантия по срокам и качеству работ.</div>
        </div>
      </div>
    </div>

    <!-- How it works -->
    <div class="how">
      <div style="font-weight:700;width:180px" data-i18n="how.title">Как это работает</div>
      <div class="steps">
        <div class="step" onclick="focusSearch()">
          <div style="font-size:22px;font-weight:800;color:var(--g1)">1</div>
          <div style="font-weight:700" data-i18n="how.find">Найти</div>
          <div class="small" data-i18n="how.findDesc">Выберите услугу и мастера.</div>
        </div>
        <div class="step">
          <div style="font-size:22px;font-weight:800;color:var(--g1)">2</div>
          <div style="font-weight:700" data-i18n="how.order">Заказать</div>
          <div class="small" data-i18n="how.orderDesc">Отправьте заявку мастеру.</div>
        </div>
        <div class="step">
          <div style="font-size:22px;font-weight:800;color:var(--g1)">3</div>
          <div style="font-weight:700" data-i18n="how.pay">Оплатить</div>
          <div class="small" data-i18n="how.payDesc">Оплата удерживается до подтверждения.</div>
        </div>
        <div class="step">
          <div style="font-size:22px;font-weight:800;color:var(--g1)">4</div>
          <div style="font-weight:700" data-i18n="how.rate">Оценить</div>
          <div class="small" data-i18n="how.rateDesc">Поставьте отзыв и рейтинг.</div>
        </div>
      </div>
    </div>

    <!-- Top Masters -->
    <div style="display:flex;justify-content:space-between;align-items:center;margin-top:18px">
      <h2 style="margin:0" data-i18n="top.title">Топ мастеров</h2>
      <a href="catalog.html" class="small" style="color:var(--g1);font-weight:700" data-i18n="top.viewAll">Смотреть все</a>
    </div>
    <div class="masters" id="top-masters">
      <!-- JS will inject master cards -->
    </div>

    <!-- CTA -->
    <div style="margin-top:22px;display:flex;justify-content:center">
      <button class="btn" onclick="openCreateRequest()"><span data-i18n="cta.create">Создать заявку</span></button>
    </div>
  </main>

  <footer>
    <div class="container" style="display:flex;justify-content:space-between;align-items:center">
      <div>
        <div style="font-weight:800">ServiceKz</div>
        <div class="small">© ServiceKz, 2025</div>
      </div>
      <div class="small">Гарантия качества • Эскроу • Поддержка</div>
    </div>
  </footer>

  <!-- Create Request Modal -->
  <div class="modal-backdrop" id="modal-backdrop" role="dialog" aria-hidden="true">
    <div class="modal fm-enter in" id="modal">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <h3 data-i18n="modal.title">Создать заявку</h3>
        <div style="display:flex;gap:8px">
          <button class="btn secondary" onclick="saveDraft()"><span data-i18n="modal.save">Сохранить черновик</span></button>
          <button class="btn" onclick="submitRequest()"><span data-i18n="modal.submit">Опубликовать</span></button>
        </div>
      </div>
      <div style="margin-top:12px" class="small" data-i18n="modal.hint">Заполните форму — мы поможем подобрать мастеров.</div>
      <div style="margin-top:12px">
        <input id="req-title" placeholder="Краткий заголовок заявки" data-i18n-placeholder="modal.titlePlaceholder" style="padding:10px;border-radius:10px;border:1px solid #e6efe7;width:100%">
      </div>
      <div class="form-row">
        <input id="req-min" placeholder="Бюджет мин" data-i18n-placeholder="modal.budgetMin" style="padding:10px;border-radius:10px;border:1px solid #e6efe7">
        <input id="req-max" placeholder="Бюджет макс" data-i18n-placeholder="modal.budgetMax" style="padding:10px;border-radius:10px;border:1px solid #e6efe7">
      </div>
      <div style="margin-top:10px">
        <textarea id="req-desc" placeholder="Опишите задачу подробно" data-i18n-placeholder="modal.descPlaceholder"></textarea>
      </div>
      <div style="margin-top:10px;display:flex;gap:10px;align-items:center">
        <input type="file" id="req-media" accept="image/*,video/*">
        <div class="small" id="auto-cat" style="color:var(--g1);font-weight:700">Категория: —</div>
      </div>

      <div style="margin-top:12px;display:flex;gap:8px;justify-content:flex-end">
        <button class="btn secondary" onclick="closeModal()"><span data-i18n="modal.cancel">Отмена</span></button>
        <button class="btn" onclick="submitRequest()"><span data-i18n="modal.submit2">Опубликовать</span></button>
      </div>
    </div>
  </div>

  <script>
    
    const i18n = {
      ru: {
        "nav.home":"Главная",
        "nav.catalog":"Каталог",
        "nav.masters":"Мастера",
        "header.create":"Создать заявку",
        "header.secure":"Платёж защищён",
        "search.service":"Например: Сантехник, Ремонт кондиционера",
        "search.city":"Город",
        "search.find":"Найти",
        "map.title":"Мастера рядом",
        "feat.escrow":"Эскроу — безопасность",
        "feat.escrowDesc":"Деньги переводятся только после подтверждения работы.",
        "feat.verify":"Проверка документов",
        "feat.verifyDesc":"Сертификаты и лицензии в профиле мастера.",
        "feat.guarantee":"Гарантия качества",
        "feat.guaranteeDesc":"Гарантия по срокам и качеству работ.",
        "how.title":"Как это работает",
        "how.find":"Найти",
        "how.findDesc":"Выберите услугу и мастера.",
        "how.order":"Заказать",
        "how.orderDesc":"Отправьте заявку мастеру.",
        "how.pay":"Оплатить",
        "how.payDesc":"Оплата удерживается до подтверждения.",
        "how.rate":"Оценить",
        "how.rateDesc":"Поставьте отзыв и рейтинг.",
        "top.title":"Топ мастеров",
        "top.viewAll":"Смотреть все",
        "cta.create":"Создать заявку",
        "modal.title":"Создать заявку",
        "modal.save":"Сохранить черновик",
        "modal.submit":"Опубликовать",
        "modal.hint":"Заполните форму — мы поможем подобрать мастеров.",
        "modal.titlePlaceholder":"Краткий заголовок (напр. Ремонт крана)",
        "modal.budgetMin":"Мин. бюджет",
        "modal.budgetMax":"Макс. бюджет",
        "modal.descPlaceholder":"Опишите задачу, сроки и предпочтения",
        "modal.cancel":"Отмена",
        "modal.submit2":"Опубликовать"
      },
      kz: {
        "nav.home":"Басты бет",
        "nav.catalog":"Каталог",
        "nav.masters":"Мамандар",
        "header.create":"Тапсырыс жасау",
        "header.secure":"Төлем қорғалған",
        "search.service":"Мысалы: сантехник, кондиционерді жөндеу",
        "search.city":"Қала",
        "search.find":"Іздеу",
        "map.title":"Жақын мамандар",
        "feat.escrow":"Эскроу — қауіпсіздік",
        "feat.escrowDesc":"Жұмыс расталғаннан кейін ғана ақша беріледі.",
        "feat.verify":"Құжаттарды тексеру",
        "feat.verifyDesc":"Сертификаттар мен лицензиялар профильде көрсетіледі.",
        "feat.guarantee":"Сапа кепілдігі",
        "feat.guaranteeDesc":"Уақыт пен сапа бойынша кепілдік.",
        "how.title":"Қалай жұмыс істейді",
        "how.find":"Табу",
        "how.findDesc":"Қызмет пен маманды таңдаңыз.",
        "how.order":"Тапсырыс беру",
        "how.orderDesc":"Мамырға сұраныс жіберіңіз.",
        "how.pay":"Төлеу",
        "how.payDesc":"Төлем растауға дейін ұсталады.",
        "how.rate":"Бағалау",
        "how.rateDesc":"Пікір мен рейтинг қалдырыңыз.",
        "top.title":"Таңдаулы мамандар",
        "top.viewAll":"Барлығын көру",
        "cta.create":"Тапсырыс жасау",
        "modal.title":"Тапсырыс жасау",
        "modal.save":"Көкпірді сақтау",
        "modal.submit":"Жариялау",
        "modal.hint":"Форманы толтырыңыз — біз мамандарды табамыз.",
        "modal.titlePlaceholder":"Тапсырма атауы (мыс. Кранды жөндеу)",
        "modal.budgetMin":"Мин. бюджет",
        "modal.budgetMax":"Макс. бюджет",
        "modal.descPlaceholder":"Тапсырманы, мерзімдерді және қалауларды сипаттаңыз",
        "modal.cancel":"Бас тарту",
        "modal.submit2":"Жариялау"
      }
    };

    let currentLang = localStorage.getItem('sk_lang') || 'ru';
    function switchLang(lang){
      currentLang = lang;
      localStorage.setItem('sk_lang', lang);
      document.getElementById('btn-ru').classList.toggle('active', lang==='ru');
      document.getElementById('btn-kz').classList.toggle('active', lang==='kz');
      applyLang();
    }
    function applyLang(){
      const map = i18n[currentLang];
      document.querySelectorAll('[data-i18n]').forEach(el=>{
        const key = el.getAttribute('data-i18n');
        if(map[key]) el.innerText = map[key];
      });
      document.querySelectorAll('[data-i18n-placeholder]').forEach(el=>{
        const key = el.getAttribute('data-i18n-placeholder');
        if(map[key]) el.placeholder = map[key];
      });
    }
    // initialize
    switchLang(currentLang);

    
    const masters = [
      {id:1,name:'Алексей',spec:'Сантехник',city:'Алматы',rating:4.9,level:'Pro'},
      {id:2,name:'Жанна',spec:'Электрик',city:'Нур-Султан',rating:4.8,level:'Verified'},
      {id:3,name:'Кайрат',spec:'Ремонт кондиционеров',city:'Шымкент',rating:4.7,level:'Elite'},
      {id:4,name:'Мария',spec:'Клининг',city:'Алматы',rating:4.6,level:'Starter'},
      {id:5,name:'Бек',spec:'Мебель на заказ',city:'Костанай',rating:4.85,level:'Pro'},
      {id:6,name:'Айнур',spec:'Плиточник',city:'Нур-Султан',rating:4.5,level:'Verified'}
    ];
    function renderTopMasters(){
      const wrap = document.getElementById('top-masters');
      wrap.innerHTML = '';
      masters.slice(0,6).forEach(m=>{
        const el = document.createElement('div');
        el.className = 'card fm-hover';
        el.innerHTML = `
          <div style="flex:0"><div class="avatar">${m.name[0]}</div></div>
          <div style="flex:1">
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div style="font-weight:800">${m.name}</div>
              <div class="small" style="color:#6b6f72">${m.city}</div>
            </div>
            <div style="display:flex;gap:10px;align-items:center;margin-top:6px">
              <div class="rating">★ ${m.rating}</div>
              <div style="font-size:13px;color:var(--muted)">${m.spec}</div>
              <div style="margin-left:auto"><span class="small" style="padding:6px 8px;border-radius:8px;background:linear-gradient(90deg,#fff,#f2fff0);border:1px solid rgba(7,102,83,0.06)">${m.level}</span></div>
            </div>
          </div>
        `;
        wrap.appendChild(el);
      });
    }
    renderTopMasters();

    function doSearch(){
      const svc = document.getElementById('s-service').value;
      const city = document.getElementById('s-city').value;
    
      console.info('API-Call: Search services', {svc, city});
      alert((currentLang==='ru' ? 'Поиск выполнен (заглушка).' : 'Іздеу орындалды (эмуляция).') + '\n' + 'service: '+svc + '\ncity: '+city);
    }
    function focusSearch(){ document.getElementById('s-service').focus() }

    
    const backdrop = document.getElementById('modal-backdrop');
    function openCreateRequest(){
      backdrop.style.display = 'flex';
      backdrop.setAttribute('aria-hidden','false');
      loadDraft();
      
      document.getElementById('modal').classList.add('in');
    }
    function closeModal(){
      backdrop.style.display = 'none';
      backdrop.setAttribute('aria-hidden','true');
    }
    // Draft autosave
    const DRAFT_KEY = 'sk_draft';
    function saveDraft(){
      const draft = {
        title: document.getElementById('req-title').value,
        min: document.getElementById('req-min').value,
        max: document.getElementById('req-max').value,
        desc: document.getElementById('req-desc').value,
        time: Date.now()
      };
      localStorage.setItem(DRAFT_KEY, JSON.stringify(draft));
      alert(currentLang==='ru' ? 'Черновик сохранён' : 'Көкпір сақталды');
    }
    function loadDraft(){
      const raw = localStorage.getItem(DRAFT_KEY);
      if(!raw) return;
      const d = JSON.parse(raw);
      document.getElementById('req-title').value = d.title||'';
      document.getElementById('req-min').value = d.min||'';
      document.getElementById('req-max').value = d.max||'';
      document.getElementById('req-desc').value = d.desc||'';
      autopickCategory();
    }
    
    let autosaveInterval = setInterval(()=>{
      if(backdrop.style.display==='flex') saveDraft();
    }, 8000);

    function submitRequest(){
      const title = document.getElementById('req-title').value.trim();
      const desc = document.getElementById('req-desc').value.trim();
      if(!title || !desc){
        alert(currentLang==='ru' ? 'Пожалуйста, заполните заголовок и описание.' : 'Тақырып пен сипаттаманы толтырыңыз.');
        return;
      }
      
      console.info('API-Call: CreateRequest', {title, desc, min:document.getElementById('req-min').value, max:document.getElementById('req-max').value});
      
      localStorage.removeItem(DRAFT_KEY);
      closeModal();
      alert(currentLang==='ru' ? 'Заявка опубликована (эмуляция).' : 'Тапсырыс жарияланды (эмуляция).');
    }

    
    const keywordsCategory = [
      {keys:['кран','сантехник','труба','водопровод'],'cat':'Сантехника'},
      {keys:['электрик','розетка','провод','свет'],'cat':'Электрика'},
      {keys:['кондицион','охлажд','сплит'],'cat':'Кондиционеры'},
      {keys:['уборк','клининг','пылесос','мыть'],'cat':'Клининг'},
      {keys:['мебел','шкаф','стол','стул'],'cat':'Мебель на заказ'},
      {keys:['плит','плиточник','плитка'],'cat':'Отделочные работы'}
    ];
    function autopickCategory(){
      const text = ((document.getElementById('req-title').value||'') + ' ' + (document.getElementById('req-desc').value||'')).toLowerCase();
      let found = '—';
      for(const k of keywordsCategory){
        for(const kw of k.keys){
          if(text.includes(kw)){
            found = k.cat;
            break;
          }
        }
        if(found !== '—') break;
      }
      document.getElementById('auto-cat').innerText = (currentLang==='ru' ? 'Категория: ' : 'Санат: ') + found;
    }
   
    ['req-title','req-desc'].forEach(id=>{
      document.getElementById(id).addEventListener('input', ()=>{
        autopickCategory();
      });
    });

    
    function navigateTo(page){
      if(page==='home') window.location.href = 'index.html';
     
    }

    
    backdrop.addEventListener('click',(e)=>{
      if(e.target===backdrop) closeModal();
    });

   
    setTimeout(autopickCategory, 300);
  </script>
</body>
</html>
