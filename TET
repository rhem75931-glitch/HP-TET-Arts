<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<title>HP TET Smart Prep — Unlimited Practice</title>
<style>
:root {
  --bg: #0f0f17;
  --card: #1a1a28;
  --text: #ccc;
  --gold: #f59e0b;
  --green: #22c55e;
  --red: #ef4444;
  --blue: #818cf8;
  --teal: #34d399;
  --sky: #60a5fa;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: system-ui, -apple-system, sans-serif;
  min-height: 100vh;
  -webkit-tap-highlight-color: transparent;
  user-select: none;
}
.wrap { max-width: 540px; margin: 0 auto; padding: 0 16px 40px; }
/* Headers */
.urgTag {
  background: #ef444415; color: var(--red);
  display: inline-block; padding: 6px 16px;
  border-radius: 20px; font-size: 12px; font-weight: 800;
}
h1 { font-size: 26px; margin: 8px 0 4px; color: #ddd; text-align: center; }
.grad {
  background: linear-gradient(135deg, var(--blue), var(--gold));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
}
/* Progress Bar */
.progBox {
  background: var(--card); border-radius: 12px; padding: 14px;
  margin: 16px 0; text-align: left;
}
.bar { height: 8px; background: #2a2a3a; border-radius: 4px; margin-top: 6px; }
.barFill { height: 8px; border-radius: 4px; transition: width 0.4s; }
/* Subject Cards */
.subCard {
  width: 100%; background: #13131f; border: 1px solid #ffffff11;
  border-radius: 14px; padding: 16px; margin-bottom: 10px;
  cursor: pointer; text-align: left; color: #eee;
  transition: transform 0.1s, border-color 0.2s;
}
.subCard:active { transform: scale(0.98); }
.ico {
  width: 44px; height: 44px; border-radius: 12px;
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0; font-size: 22px;
}
/* Topic Rows */
.priHead {
  font-size: 12px; font-weight: 800; margin: 14px 0 6px; color: #555;
}
.tpRow {
  display: flex; align-items: center; gap: 10px;
  width: 100%; background: #13131f; border: 1px solid;
  border-radius: 12px; padding: 12px; margin-bottom: 8px;
  cursor: pointer; text-align: left;
  transition: transform 0.1s;
}
.tpRow:active { transform: scale(0.98); }
/* Buttons & Cards */
.btn {
  background: #2a2a3a; border: none; color: #ddd;
  padding: 10px 18px; border-radius: 10px; cursor: pointer;
  font-size: 13px; font-weight: 600;
}
.btn-accent { background: var(--gold); color: #0f0f17; font-weight: 800; }
.btn-small { padding: 6px 12px; font-size: 12px; }
.card {
  background: var(--card); border-radius: 12px; padding: 14px; margin-bottom: 10px;
}
.secHead { font-size: 13px; font-weight: 800; color: #ddd; margin-bottom: 10px; }
.chip {
  background: #1a1a28; padding: 2px 8px; border-radius: 6px;
  font-size: 11px; color: var(--blue);
}
.optBtn {
  width: 100%; padding: 12px; border-radius: 8px;
  font-size: 14px; color: #ddd; cursor: pointer;
  text-align: left; border: 1px solid #333; background: #1a1a2a;
  margin-bottom: 8px; transition: background 0.2s;
}
.optBtn:disabled { cursor: default; opacity: 0.8; }
.toggle {
  display: flex; border-radius: 8px; overflow: hidden; margin-bottom: 14px;
}
.toggleBtn {
  flex: 1; padding: 10px 0; border: 1px solid #333;
  background: #0f0f17; color: #777; font-size: 13px;
  font-weight: 700; cursor: pointer;
}
.backBtn { background: none; border: none; color: var(--gold); font-size: 14px; cursor: pointer; }
textarea {
  width: 100%; background: var(--card); border: 1px solid #333;
  border-radius: 10px; padding: 12px; color: #ddd;
  font-size: 13px; resize: vertical;
}
.spinner {
  width: 24px; height: 24px; border: 3px solid #333;
  border-top-color: var(--blue); border-radius: 50%;
  animation: spin 0.8s linear infinite; display: inline-block;
  vertical-align: middle; margin-right: 10px;
}
@keyframes spin { to { transform: rotate(360deg); } }
.flex-row { display: flex; align-items: center; gap: 8px; }
.mt-2 { margin-top: 8px; }
.mb-2 { margin-bottom: 8px; }
</style>
</head>
<body>
<div id="root"></div>

<script>
// ═══════════════════════════════════════════
// DATA — सारे टॉपिक्स और MCQs
// ═══════════════════════════════════════════
const SUBJECTS = [
  { id:"psy", label:"🧠 बाल मनोविज्ञान एवं शिक्षाशास्त्र", color:"#818cf8" },
  { id:"eng", label:"📖 अंग्रेजी", color:"#34d399" },
  { id:"sst", label:"🌍 सामाजिक विज्ञान", color:"#f59e0b" },
  { id:"gk",  label:"🏔️ हिमाचल प्रदेश GK", color:"#60a5fa" },
];

const ALL_TOPICS = {
  psy: [
    { id:"p01", name:"वृद्धि एवं विकास (अर्थ, अंतर, सिद्धांत)", freq:8, pri:"HIGH" },
    { id:"p02", name:"पियाजे का संज्ञानात्मक विकास सिद्धांत (4 अवस्थाएँ)", freq:9, pri:"HIGH" },
    { id:"p03", name:"एरिक्सन का मनोसामाजिक विकास सिद्धांत (8 अवस्थाएँ)", freq:7, pri:"HIGH" },
    { id:"p04", name:"कोहलबर्ग का नैतिक विकास सिद्धांत", freq:6, pri:"HIGH" },
    { id:"p05", name:"वायगोत्स्की का सामाजिक-सांस्कृतिक सिद्धांत (ZPD, स्कैफोल्डिंग)", freq:5, pri:"MEDIUM" },
    { id:"p06", name:"गार्डनर का बहु-बुद्धि सिद्धांत", freq:5, pri:"MEDIUM" },
    { id:"p07", name:"अधिगम सिद्धांत — पावलव, स्किनर, थार्नडाइक", freq:9, pri:"HIGH" },
    { id:"p08", name:"बंडूरा का सामाजिक अधिगम सिद्धांत", freq:7, pri:"HIGH" },
    { id:"p09", name:"कोहलर का अंतर्दृष्टि/सूझ सिद्धांत", freq:4, pri:"MEDIUM" },
    { id:"p10", name:"ब्रूनर का खोजपूर्ण अधिगम", freq:4, pri:"MEDIUM" },
    { id:"p11", name:"बुद्धि – प्रकार, बुद्धि लब्धि (IQ) सूत्र, मानसिक आयु", freq:7, pri:"HIGH" },
    { id:"p12", name:"अभिप्रेरणा – मास्लो का आवश्यकता पदानुक्रम", freq:7, pri:"HIGH" },
    { id:"p13", name:"मूल्यांकन – रचनात्मक/योगात्मक, CCE", freq:8, pri:"HIGH" },
    { id:"p14", name:"समावेशी शिक्षा, बाल-केंद्रित शिक्षा", freq:6, pri:"MEDIUM" },
    { id:"p15", name:"स्मृति एवं विस्मरण (एबिंगहॉस वक्र)", freq:5, pri:"MEDIUM" },
    { id:"p16", name:"आनुवंशिकता बनाम वातावरण", freq:4, pri:"MEDIUM" },
    { id:"p17", name:"फ्रायड का मनोविश्लेषण एवं रक्षा युक्तियाँ", freq:3, pri:"LOW" },
    { id:"p18", name:"शिक्षण विधियाँ एवं ब्लूम का वर्गीकरण", freq:6, pri:"MEDIUM" },
  ],
  eng: [
    { id:"e01", name:"Error Spotting (त्रुटि पहचान)", freq:9, pri:"HIGH" },
    { id:"e02", name:"Fill in the Blanks (रिक्त स्थान)", freq:8, pri:"HIGH" },
    { id:"e03", name:"Tenses (काल)", freq:8, pri:"HIGH" },
    { id:"e04", name:"Active / Passive Voice", freq:7, pri:"HIGH" },
    { id:"e05", name:"Direct / Indirect Narration", freq:7, pri:"HIGH" },
    { id:"e06", name:"Articles (a, an, the)", freq:6, pri:"HIGH" },
    { id:"e07", name:"Prepositions", freq:7, pri:"HIGH" },
    { id:"e08", name:"Subject-Verb Agreement", freq:7, pri:"HIGH" },
    { id:"e09", name:"Synonyms & Antonyms", freq:6, pri:"MEDIUM" },
    { id:"e10", name:"One-word Substitution", freq:5, pri:"MEDIUM" },
    { id:"e11", name:"Idioms & Phrases", freq:6, pri:"MEDIUM" },
    { id:"e12", name:"Reading Comprehension", freq:9, pri:"HIGH" },
    { id:"e13", name:"Spelling Correction", freq:4, pri:"MEDIUM" },
    { id:"e14", name:"Modals (सहायक क्रियाएँ)", freq:5, pri:"MEDIUM" },
    { id:"e15", name:"Sentence Rearrangement / Cloze Test", freq:6, pri:"MEDIUM" },
  ],
  sst: [
    { id:"s01", name:"गांधी युग (असहयोग, सविनय अवज्ञा, भारत छोड़ो)", freq:9, pri:"HIGH" },
    { id:"s02", name:"भारतीय राष्ट्रीय कांग्रेस के अधिवेशन एवं अध्यक्ष", freq:7, pri:"HIGH" },
    { id:"s03", name:"1857 का स्वतंत्रता संग्राम", freq:8, pri:"HIGH" },
    { id:"s04", name:"हड़प्पा सभ्यता", freq:7, pri:"HIGH" },
    { id:"s05", name:"वैदिक काल एवं धार्मिक आंदोलन (भक्ति, सूफी)", freq:5, pri:"MEDIUM" },
    { id:"s06", name:"संविधान निर्माण (संविधान सभा)", freq:8, pri:"HIGH" },
    { id:"s07", name:"भारत की नदियाँ एवं प्रमुख बाँध", freq:8, pri:"HIGH" },
    { id:"s08", name:"मृदा (मिट्टी) के प्रकार", freq:7, pri:"HIGH" },
    { id:"s09", name:"जलवायु – मानसून की उत्पत्ति, ऋतुएँ", freq:7, pri:"HIGH" },
    { id:"s10", name:"भारत की कृषि एवं प्रमुख फसलें", freq:7, pri:"HIGH" },
    { id:"s11", name:"मौलिक अधिकार (अनुच्छेद 14, 19, 21, 32)", freq:9, pri:"HIGH" },
    { id:"s12", name:"राज्य के नीति निदेशक तत्व (DPSP)", freq:8, pri:"HIGH" },
    { id:"s13", name:"संसद, राष्ट्रपति एवं राज्यपाल की शक्तियाँ", freq:8, pri:"HIGH" },
    { id:"s14", name:"पंचायती राज (73वाँ संशोधन)", freq:7, pri:"HIGH" },
    { id:"s15", name:"GDP, राष्ट्रीय आय, मुद्रास्फीति", freq:6, pri:"MEDIUM" },
    { id:"s16", name:"भारतीय बैंकिंग एवं RBI", freq:5, pri:"MEDIUM" },
  ],
  gk: [
    { id:"g01", name:"हिमाचल की नदियाँ, बाँध एवं झीलें", freq:8, pri:"HIGH" },
    { id:"g02", name:"राष्ट्रीय उद्यान, वन्यजीव अभयारण्य एवं दर्रे", freq:7, pri:"HIGH" },
    { id:"g03", name:"जिला तथ्य (जनसंख्या, क्षेत्रफल, मुख्य स्थान)", freq:7, pri:"HIGH" },
    { id:"g04", name:"प्रमुख मंदिर, मेले एवं त्यौहार", freq:6, pri:"MEDIUM" },
    { id:"g05", name:"हिमाचल का गठन एवं राज्यपाल/मुख्यमंत्री सूची", freq:7, pri:"HIGH" },
    { id:"g06", name:"बोलियाँ, जनजातियाँ एवं प्रमुख उद्योग (बागवानी, जलविद्युत)", freq:5, pri:"MEDIUM" },
    { id:"g07", name:"महत्वपूर्ण दिवस, पुरस्कार, खेल, पुस्तकें एवं लेखक", freq:6, pri:"MEDIUM" },
    { id:"g08", name:"समसामयिकी (राष्ट्रीय/राज्य स्तरीय योजनाएँ, नियुक्तियाँ)", freq:9, pri:"HIGH" },
  ],
};

// Pre-made MCQs — सैंपल (जगह बचाने के लिए थोड़े, लेकिन असल में और डालें)
const QUESTION_BANK = {
  "p01": [
    { q:"वृद्धि (Growth) का संबंध किससे है?", opts:{A:"गुणात्मक परिवर्तन", B:"मात्रात्मक परिवर्तन", C:"दोनों", D:"कोई नहीं"}, ans:"B", why:"वृद्धि = मात्रा में बढ़ोतरी (ऊँचाई, वज़न)। विकास = गुणात्मक परिवर्तन।" },
    { q:"विकास का सिद्धांत 'सिफैलो-कॉडल' का क्या अर्थ है?", opts:{A:"सिर से पैर की ओर", B:"केंद्र से बाहर की ओर", C:"सामान्य से विशिष्ट", D:"पैर से सिर की ओर"}, ans:"A", why:"Cephalo-caudal = सिर से पाँव की ओर विकास। यह विकास का एक प्रमुख सिद्धांत है।" },
  ],
  "p02": [
    { q:"पियाजे के अनुसार, 'वस्तु स्थायित्व' (Object Permanence) किस अवस्था में विकसित होता है?", opts:{A:"संवेदी-गतिक (0-2 वर्ष)", B:"पूर्व-संक्रियात्मक (2-7 वर्ष)", C:"मूर्त-संक्रियात्मक (7-11 वर्ष)", D:"औपचारिक-संक्रियात्मक (11+ वर्ष)"}, ans:"A", why:"0-2 वर्ष में बच्चा समझता है कि वस्तुएँ छिपने पर भी मौजूद रहती हैं।" },
    { q:"पियाजे के अनुसार, 'संरक्षण' (Conservation) की अवधारणा किस अवस्था में विकसित होती है?", opts:{A:"संवेदी-गतिक", B:"पूर्व-संक्रियात्मक", C:"मूर्त-संक्रियात्मक", D:"औपचारिक-संक्रियात्मक"}, ans:"C", why:"7-11 वर्ष: मात्रा, भार, आयतन का संरक्षण। पूर्व-संक्रियात्मक में नहीं होता।" },
  ],
  // ... बाकी टॉपिक्स के लिए MCQ ऐसे ही जोड़ें
};

// Default MCQ जब कोई कस्टम MCQ न मिले
function getDefaultMCQ(topicId) {
  const topic = Object.values(ALL_TOPICS).flat().find(t => t.id === topicId);
  return {
    q: `${topic?.name || "इस टॉपिक"} से संबंधित प्रश्न`,
    opts: { A:"विकल्प A", B:"विकल्प B", C:"विकल्प C", D:"विकल्प D" },
    ans: "A",
    why: "सही उत्तर की व्याख्या यहाँ दिखेगी।"
  };
}

// ═══════════════════════════════════════════
// STATE MANAGEMENT
// ═══════════════════════════════════════════
const MASTERY_STREAK = 5;

function loadProgress() {
  try { return JSON.parse(localStorage.getItem("hp-tet-progress")) || {}; }
  catch { return {}; }
}
function saveProgress(data) {
  localStorage.setItem("hp-tet-progress", JSON.stringify(data));
}

let state = {
  screen: "home",
  curSubId: null,
  curTopic: null,
  mode: "exp",
  qData: null,
  picked: null,
  answered: false,
  topicRec: loadProgress(),
};

function getRec(id) {
  return state.topicRec[id] || { att:0, cor:0, streak:0, mastered:false, sawExp:false };
}
function setRec(id, patch) {
  state.topicRec = { ...state.topicRec, [id]: { ...getRec(id), ...patch } };
  saveProgress(state.topicRec);
}
function getStatus(id) {
  const r = getRec(id);
  if (r.mastered || r.streak >= MASTERY_STREAK) return "mastered";
  if (r.att > 0 || r.sawExp) return "progress";
  return "pending";
}
function subProgress(sid) {
  const ts = ALL_TOPICS[sid] || [];
  return {
    total: ts.length,
    mastered: ts.filter(t => getStatus(t.id) === "mastered").length,
  };
}
function openTopic(tp, sid) {
  state.curTopic = tp;
  state.curSubId = sid;
  state.qData = null;
  state.picked = null;
  state.answered = false;
  const rec = getRec(tp.id);
  if (!rec.sawExp) {
    state.mode = "exp";
    state.screen = "topic";
    setRec(tp.id, { sawExp: true });
  } else {
    state.mode = "prac";
    state.screen = "topic";
    loadQuestion(tp.id);
  }
  render();
}
function loadQuestion(topicId) {
  const bank = QUESTION_BANK[topicId];
  const rec = getRec(topicId);
  if (bank && bank.length > 0) {
    const idx = rec.att % bank.length;
    state.qData = bank[idx];
  } else {
    state.qData = getDefaultMCQ(topicId);
  }
  state.picked = null;
  state.answered = false;
}
function pickAnswer(opt) {
  if (state.answered || !state.qData) return;
  state.picked = opt;
  state.answered = true;
  const correct = opt === state.qData.ans;
  const rec = getRec(state.curTopic.id);
  const newStreak = correct ? rec.streak + 1 : 0;
  setRec(state.curTopic.id, {
    att: rec.att + 1,
    cor: rec.cor + (correct ? 1 : 0),
    streak: newStreak,
    mastered: newStreak >= MASTERY_STREAK,
  });
  render();
}
function nextQuestion() {
  if (state.curTopic) {
    loadQuestion(state.curTopic.id);
    render();
  }
}

// ═══════════════════════════════════════════
// RENDERING
// ═══════════════════════════════════════════
const root = document.getElementById("root");

function h(tag, props, ...children) {
  const el = document.createElement(tag);
  if (props) Object.entries(props).forEach(([k,v]) => {
    if (k === "style" && typeof v === "object") Object.assign(el.style, v);
    else if (k.startsWith("on")) el.addEventListener(k.slice(2).toLowerCase(), v);
    else if (k === "className") el.className = v;
    else if (k === "disabled" && v === false) {} 
    else el.setAttribute(k, v);
  });
  children.flat().forEach(c => {
    if (typeof c === "string" || typeof c === "number") el.appendChild(document.createTextNode(c));
    else if (c instanceof Node) el.appendChild(c);
  });
  return el;
}

function renderHome() {
  const allTopics = Object.values(ALL_TOPICS).flat();
  const total = allTopics.length;
  const mastered = allTopics.filter(t => getStatus(t.id) === "mastered").length;
  const pct = total > 0 ? Math.round(mastered / total * 100) : 0;

  return h("div", { className: "wrap" },
    h("div", { style: { textAlign:"center", padding:"22px 0 18px" } },
      h("div", { className: "urgTag" }, "📚 डेली प्रैक्टिस मोड — रोज़ करें • Progress Save होती है"),
      h("h1", {}, "HP TET ", h("span", { className: "grad" }, "Smart Prep")),
      h("p", { style: { color:"#555", fontSize:12, margin:"0 0 18px" } }, "Unlimited Practice • सारे टॉपिक्स • PYQs • प्रोग्रेस सेव"),
      h("div", { className: "progBox" },
        h("div", { style: { display:"flex", justifyContent:"space-between", fontSize:12, color:"#777", marginBottom:6 } },
          h("span", {}, "Overall Mastery"),
          h("b", { style: { color:"#818cf8" } }, `${pct}% (${mastered}/${total} topics)`)
        ),
        h("div", { className: "bar" },
          h("div", { className: "barFill", style: { width:`${pct}%`, background:"#818cf8" } })
        )
      )
    ),
    ...SUBJECTS.map(s => {
      const p = subProgress(s.id);
      const p2 = p.total > 0 ? Math.round(p.mastered / p.total * 100) : 0;
      return h("button", {
        className: "subCard",
        style: { borderColor: s.color + "44" },
        onClick: () => { state.curSubId = s.id; state.screen = "list"; render(); }
      },
        h("div", { style: { display:"flex", alignItems:"center", gap:12, marginBottom:10 } },
          h("div", { className: "ico", style: { background: s.color+"22", color: s.color } }, s.label.split(" ")[0]),
          h("div", { style: { flex:1, textAlign:"left" } },
            h("div", { style: { fontWeight:800, fontSize:15, color:"#eee" } }, s.label.slice(2)),
            h("div", { style: { fontSize:11, color:"#555" } }, `${p.mastered}/${p.total} mastered`)
          ),
          h("b", { style: { color:s.color, fontSize:22 } }, `${p2}%`)
        ),
        h("div", { className: "bar" },
          h("div", { className: "barFill", style: { width:`${p2}%`, background:s.color } })
        )
      );
    })
  );
}

function renderList() {
  const sub = SUBJECTS.find(s => s.id === state.curSubId);
  const topics = ALL_TOPICS[state.curSubId] || [];
  const priLabel = { HIGH:"🔴 High Priority (ज़रूर करें)", MEDIUM:"🟡 Medium Priority", LOW:"🟢 Lower Priority" };

  return h("div", { className: "wrap" },
    h("div", { className: "flex-row", style: { justifyContent:"space-between", marginBottom:14 } },
      h("button", { className: "backBtn", onClick: () => { state.screen = "home"; render(); } }, "← Home"),
      h("span", { style: { color:sub.color, fontWeight:800 } }, sub.label)
    ),
    h("div", { className: "flex-row", style: { fontSize:11, color:"#555", marginBottom:14, gap:12 } },
      h("span", {}, "⬜ Pending"), h("span", {}, "🟡 Started"), h("span", {}, "✅ Mastered")
    ),
    ...["HIGH","MEDIUM","LOW"].map(pri => {
      const list = topics.filter(t => t.pri === pri);
      if (!list.length) return "";
      return h("div", {},
        h("div", { className: "priHead" }, priLabel[pri]),
        ...list.map(tp => {
          const rec = getRec(tp.id);
          const status = getStatus(tp.id);
          const acc = rec.att > 0 ? Math.round(rec.cor / rec.att * 100) : null;
          return h("button", {
            className: "tpRow",
            style: { borderColor: status==="mastered"?"#22c55e44":status==="progress"?"#f59e0b44":"#1a1a28" },
            onClick: () => openTopic(tp, state.curSubId)
          },
            h("span", { style: { fontSize:18, flexShrink:0 } }, status==="mastered"?"✅":status==="progress"?"🟡":"⬜"),
            h("div", { style: { flex:1, textAlign:"left" } },
              h("div", { style: { fontSize:13, fontWeight:700, color:"#ddd", lineHeight:1.4 } }, tp.name),
              h("div", { style: { fontSize:11, color:"#555", marginTop:2 } },
                `🔁 ${tp.freq}x HP TET में आया` +
                (rec.att>0 ? ` · ${rec.att} practiced, ${acc}% accuracy` : " · Not started") +
                (rec.streak>0 ? ` · 🔥${rec.streak}/${MASTERY_STREAK} streak` : "")
              )
            ),
            h("span", { style: { color:sub.color, fontSize:18, flexShrink:0 } }, "›")
          );
        })
      );
    })
  );
}

function renderTopic() {
  const sub = SUBJECTS.find(s => s.id === state.curSubId);
  const tp = state.curTopic;
  const rec = getRec(tp.id);
  const mastered = rec.mastered || rec.streak >= MASTERY_STREAK;
  const acc = rec.att > 0 ? Math.round(rec.cor / rec.att * 100) : null;

  return h("div", { className: "wrap" },
    h("div", { className: "flex-row", style: { justifyContent:"space-between", marginBottom:14 } },
      h("button", { className: "backBtn", onClick: () => { state.screen = "list"; state.curTopic = null; render(); } }, "← Topics"),
      h("span", { style: { color:sub.color, fontSize:12 } }, sub.label)
    ),
    // Topic info
    h("div", { style: { marginBottom:14 } },
      h("div", { style: { fontSize:14, fontWeight:800, color:"#eee", lineHeight:1.4, marginBottom:8 } }, tp.name),
      h("div", { style: { display:"flex", flexWrap:"wrap", gap:6 } },
        acc !== null ? h("span", { className: "chip" }, `${acc}% accuracy (${rec.att} attempted)`) : "",
        rec.streak > 0 ? h("span", { className: "chip", style: { color:"#f59e0b" } }, `🔥 ${rec.streak}/${MASTERY_STREAK} streak`) : "",
        mastered ? h("span", { className: "chip", style: { color:"#22c55e", background:"#22c55e15" } }, "✅ MASTERED!") : ""
      ),
      !mastered && rec.att > 0 ? h("div", {
