<!doctype html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>형광펜 단어장</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css">
<style>
:root{
  --bg:#f6f4ee; --surface:#fffdf8; --ink:#1d1f24; --muted:#6b6f78; --line:#e4e0d4;
  --hl:#a6dcf7; --hl-soft:#e3f3fc; --accent:#1576b8;
  --good:#2f8f5b; --good-soft:#e2f3e9; --bad:#c9503c; --bad-soft:#fbe7e3;
  --shadow:0 1px 2px rgba(0,0,0,.04),0 10px 28px rgba(0,0,0,.07);
}
@media (prefers-color-scheme: dark){
  :root{
    --bg:#15171b; --surface:#1f2228; --ink:#ecebe6; --muted:#9a9ea8; --line:#30343c;
    --hl:#2f6f93; --hl-soft:#1d3746; --accent:#7cc4f0;
    --good:#5cc28a; --good-soft:#1b3427; --bad:#ef7b67; --bad-soft:#3a201c;
    --shadow:0 1px 2px rgba(0,0,0,.3),0 10px 28px rgba(0,0,0,.35);
  }
}
*{box-sizing:border-box}
html,body{margin:0}
body{background:var(--bg);color:var(--ink);font-family:Pretendard,-apple-system,"Apple SD Gothic Neo","Malgun Gothic",sans-serif;line-height:1.5;-webkit-font-smoothing:antialiased}
button,input,select{font:inherit;color:inherit}
.wrap{max-width:860px;margin:0 auto;padding:0 16px 72px}

header{padding:36px 0 8px}
h1{font-size:30px;margin:0;letter-spacing:-.03em;font-weight:800}
.mark{background:linear-gradient(transparent 52%,var(--hl) 52%,var(--hl) 92%,transparent 92%);padding:0 3px}
.sub{color:var(--muted);margin:6px 0 0;font-size:14px}

nav.tabs{display:flex;gap:4px;margin:24px 0 20px;border-bottom:1px solid var(--line)}
.tab{appearance:none;border:0;background:none;font-weight:700;color:var(--muted);padding:10px 14px;cursor:pointer;border-bottom:2px solid transparent;margin-bottom:-1px}
.tab[aria-selected="true"]{color:var(--ink);border-color:var(--ink)}

/* ---------- 사전 ---------- */
.toolbar{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:12px}
.search{flex:1 1 220px;min-width:0;padding:11px 14px;border:1px solid var(--line);border-radius:10px;background:var(--surface)}
.select{padding:11px 12px;border:1px solid var(--line);border-radius:10px;background:var(--surface)}
.search:focus,.select:focus,.num:focus{outline:2px solid var(--hl);outline-offset:1px}
.count{color:var(--muted);font-size:13px;margin:0 2px 10px}

.list{list-style:none;margin:0;padding:0;background:var(--surface);border:1px solid var(--line);border-radius:14px;overflow:hidden}
.row{display:grid;grid-template-columns:44px minmax(150px,1fr) 2fr 40px;gap:12px;align-items:center;padding:12px 14px;border-top:1px solid var(--line)}
.row:first-child{border-top:0}
.idx{color:var(--muted);font-size:13px;font-variant-numeric:tabular-nums}
.word{font-weight:700;font-size:17px;letter-spacing:-.01em}
.word span{background:linear-gradient(transparent 55%,var(--hl) 55%,var(--hl) 95%,transparent 95%);padding:0 2px}
.meta{display:flex;gap:4px;margin-top:3px;flex-wrap:wrap}
.badge{font-size:11px;font-weight:600;color:var(--muted);border:1px solid var(--line);border-radius:999px;padding:1px 7px;white-space:nowrap}
.badge.note{color:var(--accent);border-color:var(--hl)}
.meaning{font-size:15px}
.meaning b{font-weight:700}
.speak{appearance:none;border:0;background:none;cursor:pointer;width:36px;height:36px;border-radius:8px;color:var(--muted);display:grid;place-items:center}
.speak:hover{background:var(--hl-soft);color:var(--ink)}
.empty{padding:40px 16px;text-align:center;color:var(--muted)}

/* ---------- 플래시카드 설정 ---------- */
.panel-box{background:var(--surface);border:1px solid var(--line);border-radius:14px;padding:20px}
.label{font-size:13px;font-weight:700;color:var(--muted);margin:0 0 8px}
.seg{display:inline-flex;border:1px solid var(--line);border-radius:10px;padding:3px;gap:3px;background:var(--bg)}
.seg button{appearance:none;border:0;background:none;padding:7px 14px;border-radius:7px;cursor:pointer;font-weight:600;color:var(--muted)}
.seg button[aria-pressed="true"]{background:var(--surface);color:var(--ink);box-shadow:0 1px 3px rgba(0,0,0,.1)}
.section{margin-top:20px}
.sets{display:grid;grid-template-columns:repeat(auto-fill,minmax(130px,1fr));gap:8px}
.set{appearance:none;border:1px solid var(--line);background:var(--bg);border-radius:12px;padding:12px;text-align:left;cursor:pointer}
.set strong{display:block;font-size:16px}
.set small{color:var(--muted);font-size:12px}
.set[aria-pressed="true"]{border-color:var(--accent);background:var(--hl-soft)}
.range{display:flex;align-items:center;gap:8px;flex-wrap:wrap}
.num{width:84px;padding:10px 12px;border:1px solid var(--line);border-radius:10px;background:var(--bg);text-align:center}
.hint{color:var(--muted);font-size:13px}
.err{color:var(--bad);font-size:13px;margin-top:6px;min-height:1em}
.opts{display:flex;gap:20px;flex-wrap:wrap;align-items:center}
.check{display:flex;gap:8px;align-items:center;cursor:pointer;font-weight:600}
.check input{width:18px;height:18px;accent-color:var(--accent)}
.primary{appearance:none;border:0;background:var(--ink);color:var(--bg);font-weight:700;padding:13px 22px;border-radius:12px;cursor:pointer;width:100%;margin-top:22px;font-size:16px}
.primary:hover{opacity:.9}

/* ---------- 카드 ---------- */
.study-top{display:flex;justify-content:space-between;align-items:center;gap:8px;margin-bottom:10px}
.ghost{appearance:none;border:1px solid var(--line);background:var(--surface);padding:8px 12px;border-radius:10px;cursor:pointer;font-weight:600;font-size:14px}
.ghost:hover{background:var(--hl-soft)}
.progress-text{font-variant-numeric:tabular-nums;color:var(--muted);font-size:14px;font-weight:600}
.bar{height:6px;background:var(--line);border-radius:99px;overflow:hidden;margin-bottom:18px}
.bar i{display:block;height:100%;background:var(--accent);width:0;transition:width .25s}

.scene{perspective:1200px;cursor:pointer;user-select:none;-webkit-tap-highlight-color:transparent}
.card{position:relative;height:300px;transform-style:preserve-3d;transition:transform .45s cubic-bezier(.2,.7,.2,1)}
.card.flipped{transform:rotateY(180deg)}
.face{position:absolute;inset:0;backface-visibility:hidden;-webkit-backface-visibility:hidden;background:var(--surface);border:1px solid var(--line);border-radius:20px;box-shadow:var(--shadow);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:28px;text-align:center}
.face.back{transform:rotateY(180deg);background:var(--hl-soft);border-color:var(--hl)}
.face .tag{position:absolute;top:14px;left:16px;font-size:12px;color:var(--muted);font-weight:600}
.face .side{position:absolute;top:14px;right:16px;font-size:12px;color:var(--muted)}
.face .big{font-size:clamp(28px,7vw,44px);font-weight:800;letter-spacing:-.02em;line-height:1.2;word-break:keep-all}
.face .mid{font-size:clamp(19px,4.6vw,24px);font-weight:700;line-height:1.45;word-break:keep-all}
.face .flip-hint{position:absolute;bottom:14px;font-size:12px;color:var(--muted)}
.face .speak{position:absolute;bottom:8px;right:10px}

.controls{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:16px}
.btn{appearance:none;border:1px solid var(--line);background:var(--surface);padding:14px;border-radius:12px;cursor:pointer;font-weight:700;font-size:15px}
.btn.bad{background:var(--bad-soft);border-color:transparent;color:var(--bad)}
.btn.good{background:var(--good-soft);border-color:transparent;color:var(--good)}
.btn:hover{filter:brightness(.97)}
.nav{display:flex;justify-content:space-between;margin-top:10px}
.keys{color:var(--muted);font-size:12px;text-align:center;margin-top:14px}
kbd{font-family:inherit;border:1px solid var(--line);border-bottom-width:2px;border-radius:5px;padding:0 5px;font-size:11px;background:var(--surface)}

/* ---------- 결과 ---------- */
.result h2{margin:0 0 4px;font-size:22px}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin:16px 0}
.stat{border:1px solid var(--line);border-radius:12px;padding:12px;text-align:center;background:var(--bg)}
.stat b{display:block;font-size:24px;font-variant-numeric:tabular-nums}
.stat span{font-size:12px;color:var(--muted)}
.stat.g b{color:var(--good)} .stat.b b{color:var(--bad)}
.miss{list-style:none;padding:0;margin:8px 0 0;border-top:1px solid var(--line)}
.miss li{display:flex;gap:10px;padding:9px 0;border-bottom:1px solid var(--line);font-size:14px}
.miss li b{min-width:130px}
.result .actions{display:grid;gap:8px;margin-top:18px}

@media (max-width:600px){
  header{padding-top:24px}
  h1{font-size:25px}
  .row{grid-template-columns:32px 1fr 36px;grid-template-areas:"i w s" "i m m";row-gap:4px}
  .row .idx{grid-area:i;align-self:start;padding-top:3px}
  .row .wcell{grid-area:w}
  .row .meaning{grid-area:m}
  .row .speak{grid-area:s}
  .card{height:260px}
  .panel-box{padding:16px}
  .miss li b{min-width:100px}
}
</style>
</head>
<body>
<div class="wrap">
  <header>
    <h1><span class="mark">형광펜</span> 단어장</h1>
    <p class="sub">모의고사 18~42번 지문에서 모르는 단어만 모았어요 · 총 <b id="total"></b>개</p>
  </header>

  <nav class="tabs" role="tablist">
    <button class="tab" role="tab" data-tab="dict" aria-selected="true">📖 사전</button>
    <button class="tab" role="tab" data-tab="flash" aria-selected="false">🃏 플래시카드</button>
  </nav>

  <!-- 사전 -->
  <section id="panel-dict" class="panel">
    <div class="toolbar">
      <input id="q" class="search" type="search" placeholder="영어 단어나 뜻으로 검색" autocomplete="off">
      <select id="qfilter" class="select" aria-label="문항 선택"></select>
    </div>
    <p class="count" id="count"></p>
    <ul class="list" id="list"></ul>
  </section>

  <!-- 플래시카드 -->
  <section id="panel-flash" class="panel" hidden>
    <!-- 설정 -->
    <div id="setup" class="panel-box">
      <p class="label">범위 고르기</p>
      <div class="seg" role="group" aria-label="범위 방식">
        <button type="button" data-mode="set" aria-pressed="true">20개씩 묶음</button>
        <button type="button" data-mode="range" aria-pressed="false">직접 지정</button>
      </div>

      <div class="section" id="mode-set">
        <div class="sets" id="sets"></div>
      </div>

      <div class="section" id="mode-range" hidden>
        <div class="range">
          <input id="from" class="num" type="number" inputmode="numeric" min="1">
          <span>번부터</span>
          <input id="to" class="num" type="number" inputmode="numeric" min="1">
          <span>번까지</span>
        </div>
        <p class="hint">사전 탭 왼쪽에 있는 번호 기준이에요.</p>
        <p class="err" id="err"></p>
      </div>

      <div class="section">
        <p class="label">옵션</p>
        <div class="opts">
          <div class="seg" role="group" aria-label="앞면">
            <button type="button" data-front="en" aria-pressed="true">앞면: 영어</button>
            <button type="button" data-front="ko" aria-pressed="false">앞면: 뜻</button>
          </div>
          <label class="check"><input type="checkbox" id="shuffle" checked> 순서 섞기</label>
        </div>
      </div>

      <button class="primary" id="start">시작하기</button>
    </div>

    <!-- 학습 -->
    <div id="study" hidden>
      <div class="study-top">
        <button class="ghost" id="quit">← 범위 다시 고르기</button>
        <span class="progress-text" id="ptext"></span>
      </div>
      <div class="bar"><i id="pbar"></i></div>

      <div class="scene" id="scene" tabindex="0" aria-label="카드 뒤집기">
        <div class="card" id="card">
          <div class="face front" id="front"></div>
          <div class="face back" id="back"></div>
        </div>
      </div>

      <div class="controls">
        <button class="btn bad" id="no">😵 몰라요</button>
        <button class="btn good" id="yes">😎 알아요</button>
      </div>
      <div class="nav">
        <button class="ghost" id="prev">← 이전</button>
        <button class="ghost" id="next">다음 →</button>
      </div>
      <p class="keys"><kbd>Space</kbd> 뒤집기 · <kbd>←</kbd><kbd>→</kbd> 이동 · <kbd>1</kbd> 몰라요 · <kbd>2</kbd> 알아요</p>
    </div>

    <!-- 결과 -->
    <div id="result" class="panel-box result" hidden></div>
  </section>
</div>

<script>
/* [문항, 단어, 뜻, 주석 여부] */
const RAW = [
  ["18","department","부서, 부처, 학과, (백화점) 매장",0],
  ["19","assignment","과제, 숙제, 임무, 배정",0],
  ["20","skeptical","회의적인, 의심 많은",0],
  ["21","stumble into","~을 우연히 마주치다",1],
  ["21","disenchanted","환상이 깨진",1],
  ["21","rearrange","재배치하다, 재배열하다, (일정 등을) 재조정하다",0],
  ["23","misconduct","위법 행위, 비행, (직무상) 부정행위",0],
  ["23","informant","제보자, 정보원, 정보 제공자",0],
  ["23","whistleblower","(기업 비리 등의) 내부 고발자",1],
  ["23","violation","위반, 침해",0],
  ["23","reprisal","보복",1],
  ["23","unlawful","불법의, 위법의",0],
  ["23","corruption","부패, 비리, 타락",0],
  ["24","premature","때 이른, 시기상조의, 너무 이른, 조산의",0],
  ["24","gloss over","~에 대해 얼버무리고 넘어가다",1],
  ["24","intricacy","복잡함",1],
  ["24","seduce","현혹시키다",1],
  ["24","ambitious","야심 찬, 의욕적인, 대규모의",0],
  ["29","excite","흥분시키다, 들뜨게 하다, (관심·반응을) 불러일으키다",0],
  ["29","gerontologist","노화학자",1],
  ["30","subsidy","보조금",1],
  ["30","power plant","발전소",0],
  ["30","transition","전환, 이행, 과도기",0],
  ["30","contraction","축소, 수축, 감소",0],
  ["31","allocate","배분하다, 할당하다, 배정하다",0],
  ["32","outward","외적인, 겉으로 드러나는, 겉보기의, 밖으로 향하는",0],
  ["33","take place","일어나다, 발생하다, 개최되다",0],
  ["33","beneath","(~의) 아래에, 밑에",0],
  ["33","intertwine","뒤얽히다",1],
  ["33","central","중심이 되는, 가장 중요한, 중앙의",0],
  ["33","literary","문학의, 문어의, 문학적인",0],
  ["33","elegantly","우아하게, 유려하게, 명쾌하게, 품위 있게",0],
  ["33","garment","의복",1],
  ["33","disguise","변장, 위장, 가장",0],
  ["33","backdrop","배경, (무대의) 배경막",0],
  ["34","delineate","~의 경계를 정하다",1],
  ["34","inheritance","유전, 유산, 상속",0],
  ["34","particle","입자, 미립자, 극소량",0],
  ["34","electron","전자",0],
  ["34","mass","질량, 덩어리, 다수",0],
  ["35","occupational","직업의, 직업과 관련된",0],
  ["35","clinical","임상의, 냉정한, 객관적인",0],
  ["35","intervention","개입, 간섭, 중재",0],
  ["35","cope","대처하다, 대응하다, 처리하다, 견디다",0],
  ["36","molecule","분자",0],
  ["36","gauge","측정기",1],
  ["36","riddle","난제, 수수께끼",0],
  ["36","eardrum","고막",0],
  ["37","subset","부분 집합, (큰 집단 속의) 소집단",0],
  ["37","seamless","갈라진 틈이 없는, 끊김 없는, 매끄러운, 이음매 없는",0],
  ["37","remotely","원격으로, 멀리서, (부정문에서) 조금도",0],
  ["37","conferencing","회의, 회담, 협의",0],
  ["38","interval","간격, (시간적) 사이, 중간 휴식 시간",0],
  ["38","versus","~와 대비하여, ~ 대, ~에 비해",0],
  ["39","submerge","물속에 잠그다",1],
  ["39","air cavity","공기가 들어 있는 공간",1],
  ["39","proportionally","비례하여, 균형 있게",0],
  ["40","goldenrod","미역취",1],
  ["40","comprehensible","이해할 수 있는, 알기 쉬운",0],
  ["40","loudspeaker","확성기, 스피커",0],
  ["40","pollinator","꽃가루 매개자",1],
  ["41~42","interfere with","~을 방해하다, ~에 지장을 주다, 간섭하다",0],
  ["41~42","default","기본값",1],
  ["41~42","disable","비활성화하다, 작동하지 않게 하다, 장애를 입히다",0],
  ["41~42","opt out","빠져나오다, 탈퇴하다, (참여하지 않기로) 거부하다",0],
  ["41~42","nudge","유도하다",1],
  ["41~42","transparent","투명한",1],
  ["41~42","reversible","되돌릴 수 있는, 뒤집을 수 있는, (옷이) 안팎 겸용의",0],
  ["41~42","aligned with","~와 일치하는, ~에 맞춰 조정된, ~와 제휴한",0]
];
const WORDS = RAW.map((r,i)=>({id:i+1,q:r[0],w:r[1],m:r[2],note:!!r[3]}));
const SET_SIZE = 20;
const $ = s => document.querySelector(s);
const $$ = s => [...document.querySelectorAll(s)];
const el = (tag, cls, text) => { const e=document.createElement(tag); if(cls) e.className=cls; if(text!=null) e.textContent=text; return e; };

$('#total').textContent = WORDS.length;

/* ---------- 탭 ---------- */
function showTab(name){
  $$('.tab').forEach(t=>t.setAttribute('aria-selected', String(t.dataset.tab===name)));
  $$('.panel').forEach(p=>p.hidden = p.id !== 'panel-'+name);
}
$$('.tab').forEach(t=>t.addEventListener('click',()=>showTab(t.dataset.tab)));

/* ---------- 발음 ---------- */
const SPEAKER_SVG = '<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M11 5 6 9H2v6h4l5 4V5z"/><path d="M15.5 8.5a5 5 0 0 1 0 7"/><path d="M19 5a10 10 0 0 1 0 14"/></svg>';
function speak(text){
  try{
    if(!('speechSynthesis' in window)) return;
    speechSynthesis.cancel();
    const u = new SpeechSynthesisUtterance(text.replace(/~/g,''));
    u.lang='en-US'; u.rate=.9;
    speechSynthesis.speak(u);
  }catch(e){}
}
function speakBtn(word){
  const b = el('button','speak');
  b.type='button'; b.title='발음 듣기'; b.setAttribute('aria-label', word+' 발음 듣기');
  b.innerHTML = SPEAKER_SVG;
  b.addEventListener('click', e=>{ e.stopPropagation(); speak(word); });
  return b;
}

/* ---------- 사전 ---------- */
const qfilter = $('#qfilter');
qfilter.append(new Option('전체 문항','all'));
[...new Set(WORDS.map(w=>w.q))].forEach(q=>qfilter.append(new Option(q+'번', q)));

function renderDict(){
  const term = $('#q').value.trim().toLowerCase();
  const qv = qfilter.value;
  const items = WORDS.filter(w =>
    (qv==='all' || w.q===qv) &&
    (!term || w.w.toLowerCase().includes(term) || w.m.includes(term))
  );
  const list = $('#list');
  list.replaceChildren();
  $('#count').textContent = `${items.length}개 단어`;
  if(!items.length){ list.append(el('li','empty','검색 결과가 없어요.')); return; }
  items.forEach(w=>{
    const li = el('li','row');
    li.append(el('span','idx', String(w.id)));
    const wc = el('div','wcell');
    const word = el('div','word'); word.append(el('span',null,w.w));
    const meta = el('div','meta');
    meta.append(el('span','badge', w.q+'번'));
    if(w.note) meta.append(el('span','badge note','지문 주석'));
    wc.append(word, meta);
    li.append(wc);
    li.append(el('div','meaning', w.m));
    li.append(speakBtn(w.w));
    list.append(li);
  });
}
$('#q').addEventListener('input', renderDict);
qfilter.addEventListener('change', renderDict);
renderDict();

/* ---------- 플래시카드: 설정 ---------- */
let mode = 'set', selectedSet = 0, frontSide = 'en';
const nSets = Math.ceil(WORDS.length / SET_SIZE);
const setsBox = $('#sets');
for(let i=0;i<nSets;i++){
  const a = i*SET_SIZE+1, b = Math.min((i+1)*SET_SIZE, WORDS.length);
  const btn = el('button','set');
  btn.type='button';
  btn.setAttribute('aria-pressed', String(i===0));
  btn.append(el('strong',null,`${i+1}묶음`), el('small',null,`${a}~${b}번 · ${b-a+1}개`));
  btn.addEventListener('click',()=>{
    selectedSet=i;
    $$('.set').forEach((s,j)=>s.setAttribute('aria-pressed', String(j===i)));
  });
  setsBox.append(btn);
}
$('#from').max = $('#to').max = WORDS.length;
$('#from').value = 1; $('#to').value = WORDS.length;

$$('[data-mode]').forEach(b=>b.addEventListener('click',()=>{
  mode = b.dataset.mode;
  $$('[data-mode]').forEach(x=>x.setAttribute('aria-pressed', String(x===b)));
  $('#mode-set').hidden = mode!=='set';
  $('#mode-range').hidden = mode!=='range';
}));
$$('[data-front]').forEach(b=>b.addEventListener('click',()=>{
  frontSide = b.dataset.front;
  $$('[data-front]').forEach(x=>x.setAttribute('aria-pressed', String(x===b)));
}));

function shuffle(arr){
  const a = arr.slice();
  for(let i=a.length-1;i>0;i--){ const j=Math.floor(Math.random()*(i+1)); [a[i],a[j]]=[a[j],a[i]]; }
  return a;
}

let lastPool = [];
$('#start').addEventListener('click',()=>{
  let pool;
  if(mode==='set'){
    pool = WORDS.slice(selectedSet*SET_SIZE, (selectedSet+1)*SET_SIZE);
  }else{
    const a = parseInt($('#from').value,10), b = parseInt($('#to').value,10);
    if(!Number.isInteger(a) || !Number.isInteger(b) || a<1 || b>WORDS.length || a>b){
      $('#err').textContent = `1부터 ${WORDS.length} 사이에서, 시작 번호가 끝 번호보다 작거나 같게 입력해 주세요.`;
      return;
    }
    $('#err').textContent = '';
    pool = WORDS.slice(a-1, b);
  }
  lastPool = pool;
  startDeck(pool);
});

/* ---------- 플래시카드: 학습 ---------- */
let deck = [], idx = 0, flipped = false, marks = new Map();

function startDeck(pool){
  deck = $('#shuffle').checked ? shuffle(pool) : pool.slice();
  idx = 0; marks = new Map();
  $('#setup').hidden = true; $('#result').hidden = true; $('#study').hidden = false;
  renderCard();
  $('#scene').focus({preventScroll:true});
}

function faceContent(face, w, side, isFront){
  face.replaceChildren();
  face.append(el('span','tag', `#${w.id} · ${w.q}번`));
  face.append(el('span','side', isFront ? '앞면' : '뒷면'));
  if(side==='en'){
    face.append(el('div','big', w.w));
    face.append(speakBtn(w.w));
  }else{
    face.append(el('div','mid', w.m));
  }
  if(isFront) face.append(el('span','flip-hint','탭해서 뒤집기'));
}

function renderCard(){
  const w = deck[idx];
  flipped = false;
  const card = $('#card');
  card.style.transition = 'none';
  card.classList.remove('flipped');
  void card.offsetWidth;
  card.style.transition = '';
  faceContent($('#front'), w, frontSide, true);
  faceContent($('#back'), w, frontSide==='en' ? 'ko' : 'en', false);
  $('#ptext').textContent = `${idx+1} / ${deck.length}`;
  $('#pbar').style.width = `${(idx/deck.length)*100}%`;
  $('#prev').disabled = idx===0;
  $('#prev').style.visibility = idx===0 ? 'hidden' : 'visible';
  $('#next').textContent = idx===deck.length-1 ? '결과 보기 →' : '다음 →';
}

function flip(){ flipped=!flipped; $('#card').classList.toggle('flipped', flipped); }
function go(d){
  const n = idx + d;
  if(n < 0) return;
  if(n >= deck.length){ finish(); return; }
  idx = n; renderCard();
}
function mark(known){ marks.set(deck[idx].id, known); go(1); }

$('#scene').addEventListener('click', flip);
$('#no').addEventListener('click', ()=>mark(false));
$('#yes').addEventListener('click', ()=>mark(true));
$('#prev').addEventListener('click', ()=>go(-1));
$('#next').addEventListener('click', ()=>go(1));
$('#quit').addEventListener('click', backToSetup);

function backToSetup(){
  $('#study').hidden = true; $('#result').hidden = true; $('#setup').hidden = false;
}

document.addEventListener('keydown', e=>{
  if($('#study').hidden || $('#panel-flash').hidden) return;
  if(e.target.matches('input,select,textarea')) return;
  if(e.key===' ' || e.key==='Enter'){ e.preventDefault(); flip(); }
  else if(e.key==='ArrowRight') go(1);
  else if(e.key==='ArrowLeft') go(-1);
  else if(e.key==='1') mark(false);
  else if(e.key==='2') mark(true);
});

/* ---------- 결과 ---------- */
function finish(){
  $('#pbar').style.width = '100%';
  const known = deck.filter(w=>marks.get(w.id)===true);
  const unknown = deck.filter(w=>marks.get(w.id)===false);
  const skipped = deck.filter(w=>!marks.has(w.id));
  const retry = unknown.concat(skipped);

  const box = $('#result');
  box.replaceChildren();
  box.append(el('h2',null, retry.length ? '수고했어요! 💪' : '전부 외웠어요! 🎉'));
  box.append(el('p','hint', `${deck.length}개 중 ${known.length}개를 알고 있어요.`));

  const stats = el('div','stats');
  [['g',known.length,'알아요'],['b',unknown.length,'몰라요'],['',skipped.length,'건너뜀']].forEach(([c,n,l])=>{
    const s = el('div','stat '+c); s.append(el('b',null,String(n)), el('span',null,l)); stats.append(s);
  });
  box.append(stats);

  if(retry.length){
    box.append(el('p','label','다시 볼 단어'));
    const ul = el('ul','miss');
    retry.forEach(w=>{ const li=el('li'); li.append(el('b',null,w.w), el('span',null,w.m)); ul.append(li); });
    box.append(ul);
  }

  const actions = el('div','actions');
  if(retry.length){
    const r = el('button','primary', `모르는 단어만 다시 (${retry.length}개)`);
    r.style.marginTop='0';
    r.addEventListener('click',()=>startDeck(retry));
    actions.append(r);
  }
  const again = el('button','btn','같은 범위 처음부터');
  again.addEventListener('click',()=>startDeck(lastPool));
  const back = el('button','btn','범위 다시 고르기');
  back.addEventListener('click',backToSetup);
  actions.append(again, back);
  box.append(actions);

  $('#study').hidden = true;
  box.hidden = false;
}
</script>
</body>
</html>
