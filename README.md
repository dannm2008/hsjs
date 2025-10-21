/* Animated rainbow background */
:root{
    --card-bg: rgba(255,255,255,0.96);
}
body{
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
    background: linear-gradient(120deg,#ff9a9e 0%, #fecfef 10%, #f6d365 20%, #fda085 30%, #a1c4fd 45%, #c2e9fb 55%, #d4fc79 70%, #96e6a1 85%, #fbc2eb 100%);
    background-size: 400% 400%;
    animation: rainbow 18s linear infinite;
}
@keyframes rainbow{
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}

/* Container */
.container{
    width:100%;
    max-width:980px;
    background: var(--card-bg);
    border-radius:16px;
    box-shadow:0 15px 40px rgba(0,0,0,0.18);
    overflow:hidden;
    position:relative;
}

/* Header */
.header{
    padding:18px 22px;
    text-align:center;
    background: linear-gradient(90deg, rgba(255,255,255,0.06), rgba(255,255,255,0));
    border-bottom: 1px solid rgba(0,0,0,0.06);
}
.title{
    font-size:1.9rem;
    font-weight:800;
    letter-spacing:0.6px;
    display:flex;
    justify-content:center;
    align-items:center;
    gap:10px;
}
.title .heart{
    color:#ff5c9e;
    font-size:1.3rem;
    transform:translateY(-2px);
}
.subtitle{ color:#666; margin-top:6px; font-size:0.95rem; opacity:0.95 }

/* Timer / progress */
.timer-container{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:12px 20px;
    background:linear-gradient(to right, rgba(255,255,255,0.6), rgba(255,255,255,0.4));
    border-bottom:1px solid rgba(0,0,0,0.04);
}
.timer{ font-weight:700; color:#d6336c; background:#fff; padding:6px 12px;border-radius:20px; box-shadow:0 2px 6px rgba(0,0,0,0.06)}
.progress{ font-weight:600; color:#333 }

/* Selection screen */
.category-selection{ padding:26px; text-align:center }
.category-title{ font-size:1.4rem; font-weight:700; margin-bottom:16px; color:#222 }
.categories-container{ display:grid; gap:12px; grid-template-columns:repeat(auto-fit,minmax(160px,1fr)); margin:14px 0 22px }
.category-card{
    background:linear-gradient(180deg,rgba(255,255,255,0.7),rgba(255,255,255,0.5));
    padding:14px;border-radius:12px;border:2px solid rgba(0,0,0,0.04);
    cursor:pointer;transition:transform .18s ease, box-shadow .18s ease;
    display:flex;flex-direction:column;align-items:center;gap:8px;
    min-height:84px;justify-content:center;
}
.category-card:hover{ transform:translateY(-6px); box-shadow:0 10px 25px rgba(0,0,0,0.08) }
.category-card.selected{ outline:3px solid rgba(0,0,0,0.06); transform:translateY(-2px); }
.category-icon{ font-size:1.6rem }
.category-name{ font-weight:700 }

/* Quiz screen */
.quiz-container{ padding:22px 26px 30px }
.question-container{ margin-bottom:18px }
.question-number{ color:#6c757d; margin-bottom:6px }
.question-text{ font-size:1.25rem; font-weight:700; color:#222; line-height:1.4; margin-bottom:10px }
.category-tag{ display:inline-block; padding:6px 10px; border-radius:999px; font-weight:700; color:#fff; margin-bottom:10px }

.options-container{ display:flex; flex-direction:column; gap:12px; margin-top:10px }
.option{
    display:flex;align-items:center;gap:12px;padding:12px;border-radius:10px;border:2px solid rgba(0,0,0,0.06);
    background:linear-gradient(180deg, #fff, #f8f9fb); cursor:pointer; transition:transform .12s ease, box-shadow .12s ease;
}
.option:hover{ transform:translateY(-4px); box-shadow:0 8px 20px rgba(0,0,0,0.06) }
.option.selected{ background: linear-gradient(90deg,#6a11cb,#2575fc); color:#fff; border-color:transparent }
.option-letter{ width:34px;height:34px;border-radius:50%;display:inline-flex;align-items:center;justify-content:center;font-weight:800;background:#eef2ff }
.option.selected .option-letter{ background: rgba(255,255,255,0.25) }

/* Navigation buttons */
.navigation{ display:flex; justify-content:space-between; gap:8px; margin-top:18px }
.btn{ padding:12px 20px;border-radius:10px;border:none;font-weight:800; cursor:pointer; box-shadow:0 6px 18px rgba(0,0,0,0.06) }
.btn:disabled{ opacity:0.5; cursor:not-allowed; transform:none; box-shadow:none }
.btn-prev{ background:#adb5bd; color:#fff }
.btn-next{ background: linear-gradient(90deg,#4a00e0,#8e2de2); color:#fff }
.btn-start{ background: linear-gradient(90deg,#ff7eb3,#ff758c); color:#fff; padding:14px 28px; font-size:1.05rem }

/* Result screen */
.results-container{ padding:22px }
.results-title{ font-size:1.6rem; color:#6a11cb; font-weight:800; text-align:center }
.score{ font-size:2.4rem; font-weight:900; color:#4a00e0; text-align:center; margin:10px 0 6px }
.results-summary{ margin-top:18px; background:#fff; padding:16px; border-radius:10px; max-height:360px; overflow:auto; border:1px solid rgba(0,0,0,0.04) }
.result-item{ padding:12px;border-bottom:1px dashed rgba(0,0,0,0.04) }
.result-question{ font-weight:800; margin-bottom:6px }
.correct{ color:#28a745; font-weight:800 }
.incorrect{ color:#dc3545; font-weight:800 }

/* Feedback overlay */
.feedback{
    position: absolute;
    left:50%;
    transform:translateX(-50%);
    top:26%;
    z-index:60;
    min-width:260px;
    max-width:80%;
    text-align:center;
    padding:14px 18px;
    border-radius:12px;
    display:none;
    align-items:center;
    gap:10px;
    box-shadow:0 14px 40px rgba(0,0,0,0.18);
    font-weight:900;
    font-size:1.05rem;
}
.feedback.show{ display:flex; animation:pop .32s ease both }
@keyframes pop{ from{ transform:translateX(-50%) scale(0.8); opacity:0 } to{ transform:translateX(-50%) scale(1); opacity:1 } }

.feedback.correct{ background: linear-gradient(90deg,#e9ffea,#d6ffe0); color:#1f7a3a }
.feedback.incorrect{ background: linear-gradient(90deg,#ffe7e7,#ffdcdc); color:#8a1f2b }

/* Confetti canvas covers whole container */
#confetti-canvas{ position:absolute; inset:0; pointer-events:none; z-index:50 }

/* Shake animation for incorrect */
.shake{ animation:shake .45s ease both }
@keyframes shake{
    10%,90%{ transform:translateX(-1px) }
    20%,80%{ transform:translateX(2px) }
    30%,50%,70%{ transform:translateX(-4px) }
    40%,60%{ transform:translateX(4px) }
}

/* Mobile tweaks */
@media(max-width:640px){
    .title{ font-size:1.4rem }
    .question-text{ font-size:1.05rem }
    .btn{ padding:10px 14px }
}
