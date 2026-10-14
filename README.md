
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#0f766e">
<meta name="description" content="ডিজিটাল ডাকঘর — মনের কথা চিঠিতে লিখুন।">
<title>ডিজিটাল ডাকঘর | মনের কথা চিঠিতে</title>

<style>
:root {
  --green:#0f766e;
  --dark:#115e59;
  --mint:#ccfbf1;
  --ink:#193b38;
  --paper:#fffdf7;
}
* { box-sizing:border-box; }
html { scroll-behavior:smooth; }
body {
  margin:0;
  font-family:system-ui,"Noto Sans Bengali",sans-serif;
  background:#f7fbf8;
  color:var(--ink);
  line-height:1.7;
}
button,input,textarea { font:inherit; }
button,a { cursor:pointer; }
a { text-decoration:none; color:inherit; }
.container { width:min(1100px,92%); margin:auto; }
header {
  position:sticky; top:0; z-index:5;
  background:#ffffffef;
  border-bottom:1px solid #e1eee8;
}
nav {
  min-height:70px;
  display:flex; justify-content:space-between;
  align-items:center; gap:15px;
}
.logo { font-size:20px; font-weight:850; color:var(--green); }
nav a { font-weight:700; }
.btn {
  display:inline-block; border:0; border-radius:12px;
  padding:12px 17px; font-weight:750;
  transition:.2s;
}
.btn:hover { transform:translateY(-2px); }
.primary { background:var(--green); color:white; }
.light { background:white; color:var(--green); border:1px solid #d9e9e3; }
.soft { background:var(--mint); color:var(--dark); }

.hero {
  padding:65px 0;
  background:radial-gradient(circle at 90% 10%,#ffeac0,transparent 28%),
  linear-gradient(135deg,#f0fff9,#fffaf0);
}
.hero-grid {
  display:grid; grid-template-columns:1fr 1fr;
  align-items:center; gap:35px;
}
h1 { font-size:clamp(36px,5vw,62px); line-height:1.2; margin:15px 0; }
h1 span { color:var(--green); }
p { color:#647875; }
.actions { display:flex; flex-wrap:wrap; gap:10px; margin-top:22px; }
.art { display:grid; place-items:center; min-height:300px; }
.envelope {
  width:300px; height:195px; position:relative;
  background:#e9bd70; border-radius:12px;
  box-shadow:0 20px 40px #164e4a25;
}
.envelope:before {
  content:""; position:absolute; inset:0;
  background:#f7d99b;
  clip-path:polygon(0 0,50% 60%,100% 0);
  transform-origin:top; animation:flap 4s infinite;
  z-index:3;
}
.envelope:after {
  content:"♥"; position:absolute; top:45%; left:45%;
  display:grid; place-items:center;
  width:32px; height:32px; border-radius:50%;
  background:#d65b54; color:white; z-index:4;
}
.letter {
  position:absolute; background:white; padding:20px;
  top:10px; left:20px; right:20px; height:150px;
  border-radius:6px; animation:peek 4s infinite;
}
.letter span {
  display:block; height:5px; background:#e6e9e3;
  margin:10px 0; border-radius:5px;
}
@keyframes peek {
  0%,20%,80%,100% { transform:translateY(0); }
  40%,60% { transform:translateY(-22px); }
}
@keyframes flap {
  0%,20%,80%,100% { transform:rotateX(0); }
  40%,60% { transform:rotateX(150deg); }
}
section { padding:65px 0; }
.heading { text-align:center; max-width:650px; margin:0 auto 32px; }
.heading h2 { font-size:clamp(26px,4vw,38px); margin:0; }
.features { display:grid; grid-template-columns:repeat(3,1fr); gap:18px; }
.feature {
  background:white; border:1px solid #e3eee8;
  border-radius:18px; padding:22px;
}
.feature .emoji { font-size:32px; }
.feature h3 { margin-bottom:5px; }
.studio { background:#edf8f3; }
.editor-grid {
  display:grid; grid-template-columns:1fr 1fr;
  gap:22px; align-items:start;
}
.panel {
  background:white; padding:22px; border-radius:18px;
  border:1px solid #dfece5;
  box-shadow:0 10px 30px #164e4a0c;
}
.field { margin:16px 0; }
label { display:block; font-weight:750; margin-bottom:6px; }
input,textarea,select {
  width:100%; padding:12px;
  border:1px solid #d4e3dc; border-radius:10px;
  background:#fbfdfc; color:var(--ink);
}
textarea { min-height:150px; resize:vertical; }
.themes { display:flex; flex-wrap:wrap; gap:8px; }
.theme {
  background:#f6faf8; border:2px solid transparent;
  border-radius:10px; padding:8px 11px;
}
.theme.active { border-color:var(--green); }
.preview-area {
  background:linear-gradient(135deg,#f9e8c2,#d8f4e9);
  padding:20px; border-radius:16px;
}
.paper {
  background:var(--paper); min-height:360px;
  padding:25px; box-shadow:0 12px 30px #164e4a18;
  overflow-wrap:anywhere;
}
.paper.romantic { background:#fff4f8; }
.paper.nature { background:#f5fff1; }
.paper.romantic h3 { color:#be527b; }
.paper.nature h3 { color:#38734f; }
.paper-top {
  display:flex; justify-content:space-between;
  gap:10px; padding-bottom:12px;
  border-bottom:1px dashed #ccc; align-items:center;
}
.stamp { color:#d65b54; font-size:27px; }
.paper h3 { color:#a94f49; font-size:24px; margin-top:20px; }
#previewBody { white-space:pre-wrap; min-height:120px; }
.signature { text-align:right; margin-top:25px; }
.preview-actions { display:flex; flex-wrap:wrap; gap:9px; margin-top:15px; }
.envelope-box { display:none; margin:25px auto 0; max-width:320px; }
.envelope-box.show { display:block; }
.open-envelope {
  width:100%; height:150px; position:relative;
  background:#e9bd70; border-radius:10px; cursor:pointer;
}
.open-envelope .flap {
  position:absolute; inset:0; background:#f7d99b;
  clip-path:polygon(0 0,100% 0,50% 75%);
  transform-origin:top; transition:.7s; z-index:3;
}
.open-envelope .inside {
  position:absolute; inset:15px; background:white;
  padding:10px; text-align:center; transition:.7s;
}
.open-envelope.open .flap { transform:rotateX(170deg); }
.open-envelope.open .inside { transform:translateY(-75px); }
.steps { display:grid; grid-template-columns:repeat(3,1fr); gap:20px; }
.step { text-align:center; padding:15px; }
.number {
  display:grid; place-items:center; margin:auto auto 12px;
  background:var(--green); color:white; width:42px; height:42px;
  border-radius:50%; font-weight:850;
}
.cta {
  text-align:center; color:white; background:var(--dark);
  padding:45px 20px; border-radius:22px;
}
.cta h2 { font-size:32px; }
.cta p { color:#d8eae4; }
footer { padding:25px 0; font-size:14px; color:#71817b; }
.footer-row { display:flex; justify-content:space-between; gap:12px; flex-wrap:wrap; }
.toast {
  position:fixed; bottom:20px; left:50%;
  transform:translate(-50%,20px); opacity:0;
  background:#163f3a; color:white; padding:12px 18px;
  border-radius:10px; z-index:10; transition:.2s;
  max-width:90%; text-align:center;
}
.toast.show { opacity:1; transform:translate(-50%,0); }

@media(max-width:750px) {
  .hero-grid,.editor-grid { grid-template-columns:1fr; }
  .hero { padding:40px 0; }
  .art { min-height:230px; order:-1; }
  .envelope { transform:scale(.85); }
  .features,.steps { grid-template-columns:1fr; }
  section { padding:45px 0; }
  .panel { padding:16px; }
  .preview-area { padding:12px; }
  .paper { padding:20px; }
  nav .navlinks { display:none; }
}
@media(prefers-reduced-motion:reduce) {
  *,*::before,*::after {
    animation-duration:.01ms!important;
    transition-duration:.01ms!important;
  }
}
</style>
</head>

<body>
<header>
  <div class="container">
    <nav>
      <a class="logo" href="#home">✉ ডিজিটাল ডাকঘর</a>
      <div class="navlinks">
        <a href="#features">সুবিধা</a> &nbsp;
        <a href="#write">চিঠি লিখুন</a>
      </div>
      <a class="btn primary" href="#write">শুরু করুন ↗</a>
    </nav>
  </div>
</header>

<main>
<section class="hero" id="home">
  <div class="container hero-grid">
    <div>
      <p>💌 দূরত্ব পেরিয়ে মনের কথা</p>
      <h1>কিছু কথা থাকুক<br><span>চিঠির ভাঁজে।</span></h1>
      <p>প্রিয় কাউকে মনের কথা বলতে ইচ্ছে করছে? নিজের মতো করে একটি সুন্দর চিঠি লিখুন, সাজান এবং সংরক্ষণ করুন।</p>
      <div class="actions">
        <a class="btn primary" href="#write">✍️ চিঠি তৈরি করুন</a>
        <a class="btn light" href="#features">আরও জানুন</a>
      </div>
    </div>
    <div class="art" aria-label="চিঠির খাম">
      <div class="envelope">
        <div class="letter">
          <strong>প্রিয় মানুষ,</strong>
          <span></span><span></span><span></span>
          <span style="width:65%"></span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="features">
  <div class="container">
    <div class="heading">
      <h2>চিঠি লেখার সুন্দর এক ঠিকানা</h2>
      <p>সহজ, সুন্দর ও ব্যবহারবান্ধব অভিজ্ঞতা।</p>
    </div>
    <div class="features">
      <article class="feature">
        <div class="emoji">📝</div>
        <h3>নিজের মতো লিখুন</h3>
        <p>প্রাপকের নাম, শিরোনাম ও মনের কথা লিখুন।</p>
      </article>
      <article class="feature">
        <div class="emoji">🎨</div>
        <h3>পছন্দের থিম</h3>
        <p>ক্লাসিক, রোমান্টিক বা প্রকৃতির রং বেছে নিন।</p>
      </article>
      <article class="feature">
        <div class="emoji">💌</div>
        <h3>চিঠির অনুভূতি</h3>
        <p>খাম খুলুন, লেখা কপি করুন অথবা প্রিন্ট করুন।</p>
      </article>
    </div>
  </div>
</section>

<section class="studio" id="write">
  <div class="container">
    <div class="heading">
      <h2>তোমার চিঠি, তোমার ভাষায়</h2>
      <p>তথ্য লিখলেই পাশে চিঠির প্রিভিউ দেখতে পাবে।</p>
    </div>

    <div class="editor-grid">
      <div class="panel">
        <h3>✍️ চিঠি সাজান</h3>

        <div class="field">
          <label for="toName">প্রাপকের নাম</label>
          <input id="toName" placeholder="যেমন: প্রিয় নাদিয়া" maxlength="80">
        </div>

        <div class="field">
          <label for="letterTitle">চিঠির শিরোনাম</label>
          <input id="letterTitle" placeholder="যেমন: তোমার জন্য কিছু কথা" maxlength="100">
        </div>

        <div class="field">
          <label for="letterBody">চিঠির মূল লেখা</label>
          <textarea id="letterBody">কিছু কথা মুখে বলা যায় না, তাই আজ চিঠিতে লিখছি। তুমি ভালো থেকো, আর নিজের যত্ন নিও।</textarea>
        </div>

        <div class="field">
          <label for="fromName">প্রেরকের নাম</label>
          <input id="fromName" placeholder="ইতি, তোমার আপনজন" maxlength="80">
        </div>

        <div class="field">
          <label>চিঠির থিম</label>
          <div class="themes">
            <button class="theme active" data-theme="classic" type="button">🤎 ক্লাসিক</button>
            <button class="theme" data-theme="romantic" type="button">💗 রোমান্টিক</button>
            <button class="theme" data-theme="nature" type="button">🌿 প্রকৃতি</button>
          </div>
        </div>

        <div class="actions">
          <button class="btn primary" id="downloadBtn" type="button">⬇ ডাউনলোড</button>
          <button class="btn light" id="openBtn" type="button">💌 খাম খুলুন</button>
        </div>
      </div>

      <div>
        <div class="preview-area">
          <article class="paper" id="paper">
            <div class="paper-top">
              <div>
                <small>প্রাপক</small>
                <div id="previewTo"><strong>প্রিয় মানুষ</strong></div>
              </div>
              <div class="stamp">♥</div>
            </div>
            <h3 id="previewTitle">তোমার জন্য কিছু কথা</h3>
            <div id="previewBody">কিছু কথা মুখে বলা যায় না, তাই আজ চিঠিতে লিখছি। তুমি ভালো থেকো, আর নিজের যত্ন নিও।</div>
            <div class="signature">
              <div>ইতি,</div>
              <strong id="previewFrom">তোমার আপনজন</strong>
            </div>
          </article>
        </div>

        <div class="preview-actions">
          <button class="btn soft" id="copyBtn" type="button">📋 লেখা কপি করুন</button>
          <button class="btn light" id="printBtn" type="button">🖨️ প্রিন্ট / PDF</button>
        </div>

        <div class="envelope-box" id="envelopeBox">
          <div class="open-envelope" id="openEnvelope" role="button" tabindex="0" aria-label="খাম খুলুন">
            <div class="inside">
              <strong id="envelopeTitle">তোমার জন্য কিছু কথা</strong>
              <p>মনের কথা, চিঠির ভাষায় 💚</p>
            </div>
            <div class="flap"></div>
          </div>
          <p style="text-align:center;font-size:13px">খামটি আবার খুলতে বা বন্ধ করতে চাপ দাও।</p>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="how">
  <div class="container">
    <div class="heading">
      <h2>মাত্র তিনটি ধাপ</h2>
      <p>চিঠি তৈরি করা এখন খুব সহজ।</p>
    </div>
    <div class="steps">
      <div class="step">
        <div class="number">১</div>
        <h3>লিখে ফেলো</h3>
        <p>প্রাপকের নাম ও নিজের অনুভূতি লেখো।</p>
      </div>
      <div class="step">
        <div class="number">২</div>
        <h3>সাজিয়ে নাও</h3>
        <p>পছন্দমতো থিম নির্বাচন করো।</p>
      </div>
      <div class="step">
        <div class="number">৩</div>
        <h3>কপি বা প্রিন্ট</h3>
        <p>চিঠি কপি, ডাউনলোড অথবা PDF-এ প্রিন্ট করো।</p>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="container">
    <div class="cta">
      <h2>একটি চিঠি, একটুখানি ভালোবাসা 💚</h2>
      <p>আজই কাউকে জানিয়ে দাও—তোমার মনে তার জন্য কিছু সুন্দর কথা জমে আছে।</p>
      <a href="#write" class="btn" style="background:white;color:#115e59">এখনই চিঠি লিখুন ↓</a>
    </div>
  </div>
</section>
</main>

<footer>
  <div class="container footer-row">
    <strong>✉ ডিজিটাল ডাকঘর</strong>
    <span>© <span id="year"></span> ডিজিটাল ডাকঘর</span>
    <a href="#home">উপরে যান ↑</a>
  </div>
</footer>

<div class="toast" id="toast" role="status" aria-live="polite"></div>

<script>
const $ = id => document.getElementById(id);
const fields = ["toName", "letterTitle", "letterBody", "fromName"];
let toastTimer;

function valueOr(id, fallback) {
  return $(id).value.trim() || fallback;
}

function getLetterText() {
  return `${valueOr("toName","প্রিয় মানুষ")}

${valueOr("letterTitle","তোমার জন্য কিছু কথা")}

${valueOr("letterBody","এখানে চিঠির লেখা।")}

ইতি,
${valueOr("fromName","তোমার আপনজন")}`;
}

function updatePreview() {
  $("previewTo").textContent = valueOr("toName","প্রিয় মানুষ");
  $("previewTitle").textContent = valueOr("letterTitle","তোমার জন্য কিছু কথা");
  $("previewBody").textContent = valueOr("letterBody","এখানে চিঠির লেখা দেখা যাবে।");
  $("previewFrom").textContent = valueOr("fromName","তোমার আপনজন");
  $("envelopeTitle").textContent = valueOr("letterTitle","তোমার জন্য কিছু কথা");
}

fields.forEach(id => $(id).addEventListener("input", updatePreview));

function showToast(message) {
  $("toast").textContent = message;
  $("toast").classList.add("show");
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => $("toast").classList.remove("show"), 2600);
}

document.querySelectorAll(".theme").forEach(button => {
  button.addEventListener("click", () => {
    document.querySelectorAll(".theme").forEach(b => b.classList.remove("active"));
    button.classList.add("active");
    $("paper").className = "paper " + button.dataset.theme;
  });
});

$("copyBtn").addEventListener("click", async () => {
  try {
    await navigator.clipboard.writeText(getLetterText());
    showToast("চিঠির লেখা কপি হয়েছে!");
  } catch (error) {
    const area = document.createElement("textarea");
    area.value = getLetterText();
    document.body.appendChild(area);
    area.select();
    const copied = document.execCommand("copy");
    area.remove();
    showToast(copied ? "চিঠি কপি হয়েছে!" : "লেখা নির্বাচন করে কপি করুন।");
  }
});

function escapeHTML(text) {
  return String(text).replace(/[&<>"']/g, char => ({
    "&":"&amp;", "<":"&lt;", ">":"&gt;",
    '"':"&quot;", "'":"&#39;"
  })[char]);
}

$("downloadBtn").addEventListener("click", () => {
  const title = valueOr("letterTitle","আমার-চিঠি")
    .replace(/[^\p{L}\p{N}\-_ ]/gu,"")
    .trim().replace(/\s+/g,"-") || "amar-chithi";

  const html = `<!DOCTYPE html>
<html lang="bn"><head><meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>${escapeHTML(title)}</title>
<style>
body{font-family:system-ui,sans-serif;background:#f7fbf8;padding:20px;color:#193b38}
article{max-width:700px;margin:20px auto;padding:30px;background:#fffdf7;
box-shadow:0 8px 25px #0001;white-space:pre-wrap;line-height:1.9}
</style></head><body><article>${escapeHTML(getLetterText())}</article></body></html>`;

  const blob = new Blob([html], {type:"text/html;charset=utf-8"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url;
  a.download = title + ".html";
  document.body.appendChild(a);
  a.click();
  a.remove();
  setTimeout(() => URL.revokeObjectURL(url), 1000);
  showToast("চিঠির HTML ফাইল ডাউনলোড হয়েছে!");
});

$("printBtn").addEventListener("click", () => {
  const printWindow = window.open("", "_blank");
  if (!printWindow) {
    showToast("পপ-আপ অনুমতি দিন, তারপর আবার চেষ্টা করুন।");
    return;
  }

  printWindow.document.write(`<!DOCTYPE html><html lang="bn">
<head><meta charset="UTF-8"><title>চিঠি</title>
<style>
body{font-family:system-ui,sans-serif;padding:25px;color:#193b38}
article{max-width:700px;margin:auto;padding:30px;border:1px solid #ddd;
white-space:pre-wrap;line-height:1.9}
</style></head><body><article>${escapeHTML(getLetterText())}</article>
<script>window.onload=function(){window.print()}<\/script></body></html>`);
  printWindow.document.close();
});

$("openBtn").addEventListener("click", () => {
  $("envelopeBox").classList.add("show");
  $("openEnvelope").classList.remove("open");
  $("envelopeBox").scrollIntoView({behavior:"smooth",block:"center"});
  setTimeout(() => $("openEnvelope").classList.add("open"), 250);
});

function toggleEnvelope() {
  $("openEnvelope").classList.toggle("open");
}
$("openEnvelope").addEventListener("click", toggleEnvelope);
$("openEnvelope").addEventListener("keydown", event => {
  if (event.key === "Enter" || event.key === " ") {
    event.preventDefault();
    toggleEnvelope();
  }
});

$("year").textContent = new Date().getFullYear();
updatePreview();
</script>
</body>
</html>
