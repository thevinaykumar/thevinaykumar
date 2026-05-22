<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vinay Kumar — Product Manager · AI Strategist</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
:root{
  --neon-cyan:#00f5ff;
  --neon-green:#39ff14;
  --neon-amber:#ffb300;
  --acid-lime:#c6f135;
  --blood-red:#ff2233;
  --dark-0:#020408;
  --dark-1:#050d14;
  --dark-2:#091520;
  --dark-3:#0d1f2e;
  --grid-line:rgba(0,245,255,0.04);
  --glow-cyan:0 0 20px rgba(0,245,255,0.4),0 0 60px rgba(0,245,255,0.15);
  --glow-green:0 0 20px rgba(57,255,20,0.4),0 0 60px rgba(57,255,20,0.1);
  --mono:'Share Tech Mono',monospace;
  --display:'Orbitron',sans-serif;
  --body:'Rajdhani',sans-serif;
}
html{scroll-behavior:smooth;}
body{
  background:var(--dark-0);
  color:#c8d8e8;
  font-family:var(--body);
  font-size:16px;
  line-height:1.7;
  overflow-x:hidden;
}

/* === GRID BACKGROUND === */
body::before{
  content:'';
  position:fixed;
  inset:0;
  background-image:
    linear-gradient(var(--grid-line) 1px,transparent 1px),
    linear-gradient(90deg,var(--grid-line) 1px,transparent 1px);
  background-size:40px 40px;
  pointer-events:none;
  z-index:0;
}
body::after{
  content:'';
  position:fixed;
  inset:0;
  background:
    radial-gradient(ellipse 60% 50% at 20% 10%,rgba(0,80,120,0.18) 0%,transparent 60%),
    radial-gradient(ellipse 50% 60% at 80% 80%,rgba(0,40,80,0.22) 0%,transparent 60%),
    radial-gradient(ellipse 30% 40% at 50% 50%,rgba(0,120,60,0.06) 0%,transparent 70%);
  pointer-events:none;
  z-index:0;
}

/* === SCANLINES === */
.scanlines{
  position:fixed;
  inset:0;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.08) 2px,rgba(0,0,0,0.08) 4px);
  pointer-events:none;
  z-index:1;
  animation:scanMove 8s linear infinite;
}
@keyframes scanMove{from{transform:translateY(0)}to{transform:translateY(4px)}}

.wrapper{position:relative;z-index:2;max-width:960px;margin:0 auto;padding:0 32px;}

/* ===========================
   HERO HEADER
=========================== */
.hero{
  padding:80px 0 60px;
  text-align:center;
  position:relative;
}
.hero-circuit{
  position:absolute;
  top:0;left:0;right:0;bottom:0;
  opacity:0.12;
  overflow:hidden;
  pointer-events:none;
}
.hero-circuit svg{width:100%;height:100%;}

.hero-status{
  display:inline-flex;align-items:center;gap:8px;
  font-family:var(--mono);font-size:11px;
  color:var(--neon-green);
  background:rgba(57,255,20,0.06);
  border:1px solid rgba(57,255,20,0.2);
  padding:5px 16px;border-radius:2px;
  letter-spacing:0.15em;
  margin-bottom:32px;
  animation:statusBlink 3s ease-in-out infinite;
}
@keyframes statusBlink{0%,100%{opacity:1}50%{opacity:0.6}}
.status-dot{width:6px;height:6px;border-radius:50%;background:var(--neon-green);animation:dotPulse 2s ease-in-out infinite;box-shadow:0 0 8px var(--neon-green);}
@keyframes dotPulse{0%,100%{transform:scale(1);opacity:1}50%{transform:scale(1.6);opacity:0.5}}

.hero-name{
  font-family:var(--display);
  font-size:clamp(42px,8vw,88px);
  font-weight:900;
  letter-spacing:0.08em;
  line-height:1;
  color:#ffffff;
  text-shadow:
    0 0 30px rgba(0,245,255,0.5),
    0 0 80px rgba(0,245,255,0.2),
    0 0 120px rgba(0,245,255,0.1);
  margin-bottom:20px;
  animation:nameReveal 1.2s cubic-bezier(0.16,1,0.3,1) both;
  position:relative;
}
@keyframes nameReveal{
  from{opacity:0;transform:translateY(30px) scale(0.96);filter:blur(8px);}
  to{opacity:1;transform:translateY(0) scale(1);filter:blur(0);}
}
.hero-name .letter{
  display:inline-block;
  animation:letterDrop 0.8s cubic-bezier(0.16,1,0.3,1) both;
}

.hero-title{
  font-family:var(--mono);
  font-size:clamp(11px,1.8vw,14px);
  letter-spacing:0.25em;
  color:var(--neon-cyan);
  text-transform:uppercase;
  margin-bottom:40px;
  opacity:0;
  animation:fadeUp 0.8s 0.8s ease both;
}
.hero-title span{opacity:0.5;margin:0 10px;}

/* TYPING STRIP — SUPERCAR STYLE */
.typing-strip{
  position:relative;
  margin:0 auto 48px;
  max-width:700px;
  padding:18px 28px;
  background:linear-gradient(135deg,rgba(0,15,25,0.95),rgba(0,25,40,0.9));
  border:1px solid rgba(0,245,255,0.25);
  border-left:3px solid var(--neon-cyan);
  overflow:hidden;
}
.typing-strip::before{
  content:'';
  position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--neon-cyan),transparent);
  animation:scanStrip 3s linear infinite;
}
@keyframes scanStrip{from{transform:translateX(-100%)}to{transform:translateX(100%)}}
.typing-strip::after{
  content:'';
  position:absolute;
  inset:0;
  background:linear-gradient(90deg,rgba(0,245,255,0.05) 0%,transparent 30%);
}
.typing-lines{
  position:relative;z-index:1;
  display:flex;flex-direction:column;gap:6px;
  min-height:72px;
}
.t-line{
  font-family:var(--mono);
  font-size:clamp(12px,2vw,15px);
  letter-spacing:0.05em;
  white-space:nowrap;
  overflow:hidden;
  width:0;
  border-right:2px solid var(--neon-cyan);
  animation-timing-function:steps(40,end);
  animation-fill-mode:both;
}
.t-line:nth-child(1){color:var(--neon-cyan);animation:type1 1.8s 1s steps(48,end) both,cursorFade1 0.6s 2.8s ease both;}
.t-line:nth-child(2){color:var(--acid-lime);animation:type2 2s 3.2s steps(52,end) both,cursorFade2 0.6s 5.2s ease both;}
.t-line:nth-child(3){color:var(--neon-amber);animation:type3 1.6s 5.6s steps(44,end) both;}

@keyframes type1{from{width:0}to{width:100%}}
@keyframes type2{from{width:0}to{width:100%}}
@keyframes type3{from{width:0}to{width:100%}}
@keyframes cursorFade1{to{border-color:transparent}}
@keyframes cursorFade2{to{border-color:transparent}}

/* SPEED LINES DECORATORS */
.speed-left,.speed-right{
  position:absolute;
  top:50%;transform:translateY(-50%);
  display:flex;flex-direction:column;gap:4px;
}
.speed-left{left:-60px;}
.speed-right{right:-60px;}
.speed-line{
  height:1px;
  background:linear-gradient(90deg,transparent,var(--neon-cyan));
  animation:speedBlur 1.5s ease-in-out infinite;
}
.speed-right .speed-line{background:linear-gradient(270deg,transparent,var(--neon-cyan));}
.speed-line:nth-child(1){width:40px;animation-delay:0s;}
.speed-line:nth-child(2){width:25px;animation-delay:0.2s;}
.speed-line:nth-child(3){width:35px;animation-delay:0.4s;}
@keyframes speedBlur{0%,100%{opacity:0.3;transform:scaleX(0.6)}50%{opacity:1;transform:scaleX(1)}}

/* SOCIAL BADGES */
.social-row{
  display:flex;justify-content:center;flex-wrap:wrap;gap:12px;
  opacity:0;animation:fadeUp 0.8s 1.4s ease both;
}
.badge{
  display:inline-flex;align-items:center;gap:8px;
  font-family:var(--mono);font-size:11px;letter-spacing:0.1em;
  padding:6px 14px;
  border:1px solid;
  border-radius:2px;
  text-decoration:none;
  transition:all 0.3s ease;
  position:relative;overflow:hidden;
}
.badge::before{content:'';position:absolute;top:0;left:-100%;width:100%;height:100%;background:rgba(255,255,255,0.05);transition:left 0.4s ease;}
.badge:hover::before{left:0;}
.badge-linkedin{color:#4fc3f7;border-color:rgba(79,195,247,0.3);background:rgba(79,195,247,0.05);}
.badge-email{color:#ef9a9a;border-color:rgba(239,154,154,0.3);background:rgba(239,154,154,0.05);}
.badge-github{color:#a5d6a7;border-color:rgba(165,214,167,0.3);background:rgba(165,214,167,0.05);}
.badge-location{color:#ce93d8;border-color:rgba(206,147,216,0.3);background:rgba(206,147,216,0.05);}
.badge:hover{transform:translateY(-2px);box-shadow:0 4px 20px rgba(0,0,0,0.4);}

/* ===========================
   ARCHITECT LINE — HERO
=========================== */
.architect-block{
  padding:60px 0;
  text-align:center;
  position:relative;
}
.arch-line-wrap{
  position:relative;
  display:inline-block;
  padding:32px 60px;
}
.arch-bg{
  position:absolute;inset:0;
  background:linear-gradient(135deg,
    rgba(0,10,20,0.98),
    rgba(0,20,35,0.95));
  border:1px solid rgba(0,245,255,0.12);
  clip-path:polygon(12px 0%,100% 0%,calc(100% - 12px) 100%,0% 100%);
  overflow:hidden;
}
.arch-bg::before{
  content:'';
  position:absolute;
  top:-50%;left:-50%;
  width:200%;height:200%;
  background:conic-gradient(from 0deg,transparent 0%,rgba(0,245,255,0.03) 10%,transparent 20%,rgba(57,255,20,0.02) 30%,transparent 40%);
  animation:bgRotate 12s linear infinite;
}
@keyframes bgRotate{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
.arch-bg::after{
  content:'';
  position:absolute;
  bottom:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--neon-cyan),transparent);
  animation:bottomGlow 2s ease-in-out infinite;
}
@keyframes bottomGlow{0%,100%{opacity:0.4}50%{opacity:1}}

.arch-corner{
  position:absolute;
  width:16px;height:16px;
  border-color:var(--neon-cyan);
  border-style:solid;
}
.arch-corner.tl{top:-1px;left:-1px;border-width:2px 0 0 2px;}
.arch-corner.tr{top:-1px;right:-1px;border-width:2px 2px 0 0;}
.arch-corner.bl{bottom:-1px;left:-1px;border-width:0 0 2px 2px;}
.arch-corner.br{bottom:-1px;right:-1px;border-width:0 2px 2px 0;}

.arch-text{
  position:relative;z-index:2;
  font-family:var(--display);
  font-weight:700;
  letter-spacing:0.12em;
  line-height:1.4;
}
.arch-word{
  display:inline-block;
  font-size:clamp(13px,2.2vw,18px);
  transition:all 0.3s ease;
  position:relative;
}
.arch-word.dim{
  color:rgba(100,130,150,0.7);
  animation:dimFloat 4s ease-in-out infinite;
}
.arch-word.dim:nth-child(2){animation-delay:0.5s;}
.arch-word.dim:nth-child(3){animation-delay:1s;}
.arch-word.dim:nth-child(4){animation-delay:1.5s;}
@keyframes dimFloat{0%,100%{opacity:0.5;transform:translateY(0)}50%{opacity:0.8;transform:translateY(-2px)}}

.arch-sep{color:rgba(0,245,255,0.25);margin:0 12px;font-size:14px;}

.arch-word.ARCHITECT{
  color:var(--neon-cyan);
  font-size:clamp(22px,4vw,42px);
  font-weight:900;
  letter-spacing:0.2em;
  display:block;
  margin-top:8px;
  text-shadow:var(--glow-cyan);
  animation:architectPulse 2s ease-in-out infinite;
  position:relative;
}
@keyframes architectPulse{
  0%,100%{
    text-shadow:0 0 20px rgba(0,245,255,0.6),0 0 60px rgba(0,245,255,0.3),0 0 120px rgba(0,245,255,0.1);
    letter-spacing:0.2em;
  }
  50%{
    text-shadow:0 0 40px rgba(0,245,255,1),0 0 100px rgba(0,245,255,0.5),0 0 200px rgba(0,245,255,0.2);
    letter-spacing:0.25em;
  }
}
.arch-word.ARCHITECT::before{
  content:'I ARCHITECT';
  position:absolute;
  top:0;left:0;right:0;
  color:var(--blood-red);
  clip-path:polygon(0 0,100% 0,100% 30%,0 30%);
  transform:translateX(-3px);
  opacity:0;
  animation:glitchR 6s ease-in-out infinite;
  text-shadow:0 0 10px var(--blood-red);
}
.arch-word.ARCHITECT::after{
  content:'I ARCHITECT';
  position:absolute;
  top:0;left:0;right:0;
  color:var(--acid-lime);
  clip-path:polygon(0 60%,100% 60%,100% 90%,0 90%);
  transform:translateX(3px);
  opacity:0;
  animation:glitchG 6s ease-in-out infinite;
  text-shadow:0 0 10px var(--acid-lime);
}
@keyframes glitchR{0%,88%,100%{opacity:0;transform:translateX(-3px)}89%,91%{opacity:0.8;transform:translateX(-6px)}90%{opacity:0;}}
@keyframes glitchG{0%,88%,100%{opacity:0;transform:translateX(3px)}89.5%,91.5%{opacity:0.8;transform:translateX(6px)}90.5%{opacity:0;}}

.arch-particles{
  position:absolute;inset:0;overflow:hidden;pointer-events:none;
}
.arch-particle{
  position:absolute;
  width:2px;height:2px;
  background:var(--neon-cyan);
  border-radius:50%;
  animation:particleDrift linear infinite;
  opacity:0;
  box-shadow:0 0 4px var(--neon-cyan);
}
@keyframes particleDrift{
  0%{opacity:0;transform:translateY(0) translateX(0);}
  10%{opacity:0.8;}
  90%{opacity:0.3;}
  100%{opacity:0;transform:translateY(-80px) translateX(var(--drift,20px));}
}

/* === DIVIDER === */
.divider{
  display:flex;align-items:center;gap:16px;
  margin:12px 0 40px;
  opacity:0.25;
}
.divider::before,.divider::after{content:'';flex:1;height:1px;background:linear-gradient(90deg,transparent,var(--neon-cyan),transparent);}
.divider span{font-family:var(--mono);font-size:10px;letter-spacing:0.3em;color:var(--neon-cyan);}

/* ===========================
   SECTION HEADERS
=========================== */
.section{padding:40px 0;}
.section-head{
  display:flex;align-items:center;gap:16px;
  margin-bottom:32px;
}
.section-head .label{
  font-family:var(--display);
  font-size:11px;
  font-weight:700;
  letter-spacing:0.3em;
  color:var(--neon-cyan);
  text-transform:uppercase;
}
.section-head .line{flex:1;height:1px;background:linear-gradient(90deg,rgba(0,245,255,0.4),transparent);}
.section-head .num{
  font-family:var(--mono);font-size:10px;
  color:rgba(0,245,255,0.3);
}

/* ===========================
   OPERATING SYSTEM GRID
=========================== */
.os-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:1px;
  background:rgba(0,245,255,0.06);
  border:1px solid rgba(0,245,255,0.08);
}
.os-cell{
  padding:28px 24px;
  background:var(--dark-1);
  transition:background 0.3s ease;
  position:relative;
  overflow:hidden;
}
.os-cell::before{
  content:'';
  position:absolute;top:0;left:0;
  width:3px;height:0;
  background:var(--neon-cyan);
  transition:height 0.4s ease;
}
.os-cell:hover{background:var(--dark-2);}
.os-cell:hover::before{height:100%;}
.os-num{
  font-family:var(--mono);font-size:10px;
  color:rgba(0,245,255,0.3);
  letter-spacing:0.2em;
  margin-bottom:8px;
}
.os-title{
  font-family:var(--display);
  font-size:13px;font-weight:700;
  letter-spacing:0.15em;
  color:#ffffff;margin-bottom:10px;
}
.os-desc{
  font-family:var(--body);font-size:13px;
  color:rgba(160,180,200,0.7);
  line-height:1.6;
}

/* ===========================
   PROJECTS
=========================== */
.projects-list{display:flex;flex-direction:column;gap:2px;}
.project-row{
  display:flex;align-items:flex-start;gap:20px;
  padding:20px 24px;
  background:var(--dark-1);
  border-left:3px solid transparent;
  transition:all 0.3s ease;
  position:relative;
  overflow:hidden;
}
.project-row::after{
  content:'';
  position:absolute;bottom:0;left:0;right:0;height:1px;
  background:rgba(0,245,255,0.05);
}
.project-row:hover{
  background:var(--dark-2);
  border-left-color:var(--neon-cyan);
  transform:translateX(4px);
}
.proj-num{
  font-family:var(--mono);font-size:10px;
  color:rgba(0,245,255,0.25);
  min-width:28px;
  margin-top:2px;
  letter-spacing:0.1em;
}
.proj-body{flex:1;}
.proj-title{
  font-family:var(--display);font-size:14px;font-weight:700;
  color:#e8f0f8;letter-spacing:0.08em;
  margin-bottom:4px;
}
.proj-scope{
  font-family:var(--mono);font-size:10px;
  color:var(--neon-amber);
  letter-spacing:0.12em;margin-bottom:8px;
  opacity:0.8;
}
.proj-desc{
  font-family:var(--body);font-size:13px;
  color:rgba(140,165,185,0.75);
  line-height:1.5;
}
.proj-tags{
  display:flex;flex-wrap:wrap;gap:6px;margin-top:10px;
}
.tag{
  font-family:var(--mono);font-size:9px;
  letter-spacing:0.12em;
  padding:3px 8px;
  border:1px solid;
  border-radius:1px;
}
.tag-py{color:#74b9e8;border-color:rgba(116,185,232,0.25);}
.tag-ml{color:#ff8a65;border-color:rgba(255,138,101,0.25);}
.tag-sql{color:#a5d6a7;border-color:rgba(165,214,167,0.25);}
.tag-bi{color:#ffd54f;border-color:rgba(255,213,79,0.25);}
.tag-rpa{color:#ce93d8;border-color:rgba(206,147,216,0.25);}
.tag-web{color:#80cbc4;border-color:rgba(128,203,196,0.25);}
.tag-cv{color:#ef9a9a;border-color:rgba(239,154,154,0.25);}

/* ===========================
   SKILLS
=========================== */
.skills-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(400px,1fr));
  gap:2px;
}
.skill-block{
  background:var(--dark-1);
  padding:28px 24px;
}
.skill-block-title{
  font-family:var(--display);font-size:11px;font-weight:700;
  letter-spacing:0.25em;color:var(--neon-cyan);
  margin-bottom:20px;text-transform:uppercase;
}
.skill-row{
  display:flex;align-items:center;gap:12px;
  margin-bottom:14px;
}
.skill-name{
  font-family:var(--mono);font-size:12px;
  color:rgba(180,200,220,0.85);
  min-width:180px;
  letter-spacing:0.04em;
}
.skill-bar{flex:1;height:3px;background:rgba(255,255,255,0.05);border-radius:0;overflow:hidden;}
.skill-fill{height:100%;border-radius:0;animation:barGrow 1.5s cubic-bezier(0.16,1,0.3,1) both;}
@keyframes barGrow{from{width:0}to{width:var(--w)}}
.fill-exp{background:linear-gradient(90deg,var(--neon-cyan),rgba(0,245,255,0.4));}
.fill-adv{background:linear-gradient(90deg,var(--acid-lime),rgba(198,241,53,0.3));}
.fill-pro{background:linear-gradient(90deg,var(--neon-amber),rgba(255,179,0,0.3));}
.fill-int{background:linear-gradient(90deg,rgba(160,100,200,0.8),rgba(160,100,200,0.2));}
.skill-level{
  font-family:var(--mono);font-size:9px;
  min-width:72px;text-align:right;
  letter-spacing:0.1em;
}
.lv-exp{color:var(--neon-cyan);}
.lv-adv{color:var(--acid-lime);}
.lv-pro{color:var(--neon-amber);}
.lv-int{color:rgba(160,100,200,0.8);}

/* ===========================
   CERTIFICATIONS — UNIFIED LIST
=========================== */
.cert-count-banner{
  display:flex;align-items:center;gap:24px;
  padding:24px 28px;
  background:linear-gradient(135deg,rgba(0,10,20,0.98),rgba(0,20,35,0.9));
  border:1px solid rgba(0,245,255,0.15);
  border-left:4px solid var(--neon-cyan);
  margin-bottom:4px;
}
.cert-big-num{
  font-family:var(--display);
  font-size:56px;
  font-weight:900;
  color:var(--neon-cyan);
  line-height:1;
  text-shadow:var(--glow-cyan);
  animation:numPulse 3s ease-in-out infinite;
}
@keyframes numPulse{0%,100%{opacity:1}50%{opacity:0.75}}
.cert-count-label{
  font-family:var(--display);font-size:12px;font-weight:700;
  letter-spacing:0.2em;color:rgba(160,190,210,0.7);
  text-transform:uppercase;
}
.cert-count-sub{
  font-family:var(--mono);font-size:10px;
  color:rgba(0,245,255,0.4);
  letter-spacing:0.12em;
  margin-top:4px;
}

.cert-table{
  width:100%;
  border-collapse:collapse;
  font-family:var(--body);
}
.cert-table tbody tr{
  border-bottom:1px solid rgba(0,245,255,0.04);
  transition:background 0.25s;
}
.cert-table tbody tr:hover{background:rgba(0,245,255,0.03);}
.cert-table td{
  padding:13px 16px;
  font-size:13.5px;
  vertical-align:middle;
}
.cert-idx{
  font-family:var(--mono);font-size:10px;
  color:rgba(0,245,255,0.2);
  letter-spacing:0.1em;
  width:40px;
  text-align:right;
}
.cert-name{
  color:rgba(200,218,235,0.9);
}
.cert-issuer{
  font-family:var(--mono);font-size:10px;
  color:rgba(0,245,255,0.4);
  letter-spacing:0.08em;
  text-align:right;
  white-space:nowrap;
  width:1px;
}
.cert-domain{
  width:1px;
  white-space:nowrap;
}
.domain-pill{
  font-family:var(--mono);font-size:9px;
  letter-spacing:0.1em;
  padding:2px 8px;
  border:1px solid;
  border-radius:1px;
  text-transform:uppercase;
}
.dp-pm{color:var(--neon-cyan);border-color:rgba(0,245,255,0.25);}
.dp-ai{color:var(--acid-lime);border-color:rgba(198,241,53,0.25);}
.dp-auto{color:var(--neon-amber);border-color:rgba(255,179,0,0.25);}
.dp-data{color:#ef9a9a;border-color:rgba(239,154,154,0.25);}
.dp-net{color:#ce93d8;border-color:rgba(206,147,216,0.25);}

/* ===========================
   CONNECT
=========================== */
.connect-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:2px;
}
.connect-card{
  display:flex;flex-direction:column;align-items:center;
  justify-content:center;
  padding:32px 20px;
  background:var(--dark-1);
  text-decoration:none;
  transition:all 0.3s ease;
  position:relative;
  overflow:hidden;
  gap:12px;
}
.connect-card::before{
  content:'';
  position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(0,245,255,0.03),transparent);
  opacity:0;transition:opacity 0.3s;
}
.connect-card:hover::before{opacity:1;}
.connect-card:hover{transform:translateY(-4px);box-shadow:0 12px 40px rgba(0,0,0,0.5);}
.connect-icon{
  font-size:28px;
  line-height:1;
  margin-bottom:4px;
}
.connect-label{
  font-family:var(--display);font-size:11px;font-weight:700;
  letter-spacing:0.2em;
  text-transform:uppercase;
}
.connect-val{
  font-family:var(--mono);font-size:11px;
  letter-spacing:0.04em;
  opacity:0.6;
}
.cc-li{color:#4fc3f7;}
.cc-em{color:#ef9a9a;}
.cc-gh{color:#a5d6a7;}

/* ===========================
   IDENTITY
=========================== */
.identity-block{
  background:var(--dark-1);
  padding:40px;
  position:relative;
  overflow:hidden;
}
.identity-block::before{
  content:'';
  position:absolute;top:0;right:0;
  width:200px;height:200px;
  background:radial-gradient(circle,rgba(0,245,255,0.04) 0%,transparent 70%);
  pointer-events:none;
}
.identity-text{
  font-family:var(--body);
  font-size:16px;
  line-height:1.85;
  color:rgba(175,200,220,0.85);
  position:relative;z-index:1;
}
.identity-text strong{
  color:#e8f4ff;
  font-weight:600;
}
.identity-text .pull{
  font-family:var(--display);
  font-size:13px;
  font-weight:700;
  letter-spacing:0.18em;
  color:var(--neon-cyan);
  display:block;
  margin-top:20px;
  opacity:0.8;
}

/* === FOOTER === */
.footer{
  padding:48px 0 60px;
  text-align:center;
}
.footer-line{
  font-family:var(--mono);font-size:10px;
  letter-spacing:0.2em;
  color:rgba(0,245,255,0.2);
}
.footer-name{
  font-family:var(--display);
  font-size:11px;font-weight:700;
  letter-spacing:0.3em;
  color:rgba(0,245,255,0.3);
  margin-top:8px;
}

/* === ANIMATIONS === */
@keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}

.reveal{
  opacity:0;
  transform:translateY(20px);
  transition:opacity 0.7s ease,transform 0.7s ease;
}
.reveal.visible{opacity:1;transform:translateY(0);}
</style>
</head>
<body>
<div class="scanlines"></div>

<div class="wrapper">

<!-- ======================== HERO ======================== -->
<section class="hero">
  <div class="hero-circuit" aria-hidden="true">
    <svg viewBox="0 0 960 300" preserveAspectRatio="xMidYMid slice">
      <!-- Circuit trace lines -->
      <g stroke="rgba(0,245,255,1)" stroke-width="0.5" fill="none">
        <polyline points="0,80 120,80 140,60 300,60"/>
        <polyline points="300,60 320,40 500,40 520,60 700,60 720,80 960,80"/>
        <polyline points="0,180 80,180 100,200 200,200"/>
        <polyline points="200,200 220,220 400,220 420,200 600,200 620,180 800,180 820,200 960,200"/>
        <polyline points="140,60 140,0"/>
        <polyline points="520,60 520,0"/>
        <polyline points="720,80 720,0"/>
        <polyline points="220,220 220,300"/>
        <polyline points="620,180 620,300"/>
        <!-- Nodes -->
        <circle cx="140" cy="60" r="3" fill="rgba(0,245,255,0.4)"/>
        <circle cx="300" cy="60" r="3" fill="rgba(0,245,255,0.4)"/>
        <circle cx="520" cy="60" r="3" fill="rgba(0,245,255,0.4)"/>
        <circle cx="720" cy="80" r="3" fill="rgba(0,245,255,0.4)"/>
        <circle cx="200" cy="200" r="3" fill="rgba(0,245,255,0.4)"/>
        <circle cx="420" cy="200" r="3" fill="rgba(0,245,255,0.4)"/>
        <circle cx="620" cy="180" r="3" fill="rgba(0,245,255,0.4)"/>
        <rect x="136" y="56" width="8" height="8" fill="rgba(0,245,255,0.15)" stroke="rgba(0,245,255,0.6)"/>
        <rect x="516" y="56" width="8" height="8" fill="rgba(57,255,20,0.1)" stroke="rgba(57,255,20,0.5)"/>
        <rect x="416" y="196" width="8" height="8" fill="rgba(255,179,0,0.1)" stroke="rgba(255,179,0,0.5)"/>
      </g>
    </svg>
  </div>

  <div class="hero-status">
    <span class="status-dot"></span>
    SYSTEM ONLINE — VINAY KUMAR — v2025.1
  </div>

  <h1 class="hero-name" id="heroName">VINAY KUMAR</h1>

  <p class="hero-title">
    Product Manager <span>·</span> Business Analyst <span>·</span> AI &amp; Automation Strategist
  </p>

  <!-- SUPERCAR TYPING STRIP -->
  <div class="typing-strip" style="position:relative;">
    <div class="speed-left" aria-hidden="true">
      <div class="speed-line"></div>
      <div class="speed-line"></div>
      <div class="speed-line"></div>
    </div>
    <div class="speed-right" aria-hidden="true">
      <div class="speed-line"></div>
      <div class="speed-line"></div>
      <div class="speed-line"></div>
    </div>
    <div class="typing-lines">
      <div class="t-line">Building at the intersection of AI + Product + Operations</div>
      <div class="t-line">Turning ambiguity into architecture &amp; decisions into systems</div>
      <div class="t-line">Precision. Product. Technology. — This is the entire brief.</div>
    </div>
  </div>

  <div class="social-row">
    <a href="https://linkedin.com/in/thevinaykumar57" class="badge badge-linkedin" target="_blank">⬡ LinkedIn</a>
    <a href="mailto:thevinaykumar57@gmail.com" class="badge badge-email" target="_blank">⬡ Email</a>
    <a href="https://github.com/thevinaykumar" class="badge badge-github" target="_blank">⬡ GitHub</a>
    <span class="badge badge-location">⬡ Hyderabad, India</span>
  </div>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== ARCHITECT LINE ======================== -->
<section class="architect-block reveal">
  <div class="arch-line-wrap">
    <div class="arch-bg">
      <div class="arch-particles" id="archParticles"></div>
    </div>
    <div class="arch-corner tl"></div>
    <div class="arch-corner tr"></div>
    <div class="arch-corner bl"></div>
    <div class="arch-corner br"></div>
    <div class="arch-text">
      <span class="arch-word dim">Technology moves.</span>
      <span class="arch-sep">◈</span>
      <span class="arch-word dim">Most people watch.</span>
      <span class="arch-sep">◈</span>
      <span class="arch-word dim">Some build.</span>
      <span class="arch-word ARCHITECT">I ARCHITECT.</span>
    </div>
  </div>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== IDENTITY ======================== -->
<section class="section reveal">
  <div class="section-head">
    <span class="label">◈ Identity</span>
    <div class="line"></div>
    <span class="num">01</span>
  </div>
  <div class="identity-block">
    <p class="identity-text">
      I work exclusively at the intersection of technology and technical innovation —
      AI systems, intelligent product ecosystems, and digital execution at the highest level.
      <strong>Product Manager. Business Analyst. Creative Technologist.</strong> The title shifts. The domain never does.
      <br/><br/>
      Premium digital products don't need explaining — they're felt the moment someone lands on them. That's the standard I hold every experience to. Technology either commands attention or it doesn't. The same goes for the people shaping it.
      <span class="pull">Precision. &nbsp;Product. &nbsp;Technology.</span>
    </p>
  </div>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== OPERATING SYSTEM ======================== -->
<section class="section reveal">
  <div class="section-head">
    <span class="label">◈ Operating System</span>
    <div class="line"></div>
    <span class="num">02</span>
  </div>
  <div class="os-grid">
    <div class="os-cell"><div class="os-num">01 —</div><div class="os-title">PRODUCT THINKING</div><p class="os-desc">Translating ambiguity into product requirements. Defining KPIs, roadmaps, and stakeholder narratives that align teams and drive outcomes.</p></div>
    <div class="os-cell"><div class="os-num">02 —</div><div class="os-title">AI SYSTEMS</div><p class="os-desc">Deploying intelligent automation, prompt engineering, and ML-backed workflows that scale operations without scaling headcount.</p></div>
    <div class="os-cell"><div class="os-num">03 —</div><div class="os-title">ANALYTICS</div><p class="os-desc">SQL-driven insights, Power BI dashboards, and structured reporting pipelines that convert raw data into operational decisions.</p></div>
    <div class="os-cell"><div class="os-num">04 —</div><div class="os-title">AUTOMATION</div><p class="os-desc">UiPath & RPA-powered pipelines that eliminate manual bottlenecks. Robotic workflows built for reliability, not complexity.</p></div>
    <div class="os-cell"><div class="os-num">05 —</div><div class="os-title">OPERATIONS</div><p class="os-desc">Cross-functional coordination, risk management, and process optimization across technical and non-technical environments.</p></div>
    <div class="os-cell"><div class="os-num">06 —</div><div class="os-title">EXECUTION</div><p class="os-desc">Agile delivery, project coordination, stakeholder communication, and measurable output — from concept to shipped product.</p></div>
  </div>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== PROJECTS ======================== -->
<section class="section reveal">
  <div class="section-head">
    <span class="label">◈ Featured Projects</span>
    <div class="line"></div>
    <span class="num">03</span>
  </div>
  <div class="projects-list">
    <div class="project-row"><div class="proj-num">01</div><div class="proj-body"><div class="proj-title">AI SaaS Product Analytics Dashboard</div><div class="proj-scope">Product Analytics · KPI Reporting · Retention Intelligence</div><p class="proj-desc">Built a product analytics dashboard tracking user engagement, feature adoption, retention trends, subscription KPIs, and operational reporting metrics for a simulated AI SaaS platform using structured SQL reporting workflows and interactive Power BI dashboards.</p><div class="proj-tags"><span class="tag tag-sql">SQL</span><span class="tag tag-bi">Power BI</span><span class="tag tag-bi">Excel</span></div></div></div>
    <div class="project-row"><div class="proj-num">02</div><div class="proj-body"><div class="proj-title">Cryptocurrency Market Data Analysis Bot</div><div class="proj-scope">Automation Pipelines · Anomaly Detection · Market Intelligence</div><p class="proj-desc">Automated cryptocurrency market monitoring, anomaly detection, and operational reporting workflows using UiPath automation pipelines — delivering continuous market surveillance without manual intervention.</p><div class="proj-tags"><span class="tag tag-py">Python</span><span class="tag tag-rpa">UiPath</span></div></div></div>
    <div class="project-row"><div class="proj-num">03</div><div class="proj-body"><div class="proj-title">Professional Website Development & Deployment</div><div class="proj-scope">Frontend Architecture · Deployment Operations · Responsive UI</div><p class="proj-desc">Designed and deployed a premium multi-page business website with responsive frontend architecture, structured deployment workflows, cross-browser debugging coordination, and continuous operational optimization. End-to-end ownership.</p><div class="proj-tags"><span class="tag tag-web">HTML5</span><span class="tag tag-web">CSS3</span><span class="tag tag-web">JavaScript</span><span class="tag tag-web">Netlify</span></div></div></div>
    <div class="project-row"><div class="proj-num">04</div><div class="proj-body"><div class="proj-title">Sign Detector AI</div><div class="proj-scope">Computer Vision · Gesture Recognition · AI Inference</div><p class="proj-desc">Developed an AI-powered sign language recognition system capable of detecting and interpreting hand gestures in real time using machine learning and computer vision — bridging accessibility gaps through intelligent automation.</p><div class="proj-tags"><span class="tag tag-py">Python</span><span class="tag tag-ml">Machine Learning</span><span class="tag tag-cv">OpenCV</span></div></div></div>
    <div class="project-row"><div class="proj-num">05</div><div class="proj-body"><div class="proj-title">ML Adult & Child Detection System</div><div class="proj-scope">Visual AI · Demographic Classification · Monitoring Systems</div><p class="proj-desc">Built a machine learning-based detection system for identifying adults and children in visual datasets — supporting AI-based operational analysis workflows and intelligent monitoring infrastructure.</p><div class="proj-tags"><span class="tag tag-py">Python</span><span class="tag tag-ml">Machine Learning</span></div></div></div>
    <div class="project-row"><div class="proj-num">06</div><div class="proj-body"><div class="proj-title">Pedestrian Detector</div><div class="proj-scope">Real-Time Detection · Human Movement Analysis</div><p class="proj-desc">Developed a pedestrian detection system using computer vision techniques for identifying human movement patterns and supporting real-time monitoring workflows at scale.</p><div class="proj-tags"><span class="tag tag-py">Python</span><span class="tag tag-cv">OpenCV</span></div></div></div>
    <div class="project-row"><div class="proj-num">07</div><div class="proj-body"><div class="proj-title">ML Travel Time Prediction</div><div class="proj-scope">Predictive Analytics · Transportation Intelligence</div><p class="proj-desc">Built a predictive analytics model for estimating travel time using machine learning algorithms and structured transportation data analysis — enabling data-driven logistics and route optimization decisions.</p><div class="proj-tags"><span class="tag tag-py">Python</span><span class="tag tag-ml">Scikit-learn</span></div></div></div>
    <div class="project-row"><div class="proj-num">08</div><div class="proj-body"><div class="proj-title">IPL Win & Score Predictor</div><div class="proj-scope">Sports Analytics · Statistical Modeling · Predictive Systems</div><p class="proj-desc">Dual-model analytics system — one predicting match outcomes, another estimating live scores — both using historical match statistics, structured data pipelines, and machine learning inference.</p><div class="proj-tags"><span class="tag tag-py">Python</span><span class="tag tag-ml">ML</span></div></div></div>
    <div class="project-row"><div class="proj-num">09</div><div class="proj-body"><div class="proj-title">Car Buyer Bot — Automation Anywhere</div><div class="proj-scope">RPA · Workflow Automation · Operational Efficiency</div><p class="proj-desc">Automated car purchasing and inquiry workflows using robotic process automation to eliminate repetitive operational tasks, reduce cycle time, and improve end-to-end workflow efficiency.</p><div class="proj-tags"><span class="tag tag-rpa">Automation Anywhere</span></div></div></div>
    <div class="project-row"><div class="proj-num">10</div><div class="proj-body"><div class="proj-title">Autonomous Harvesting Robot — AgriTech</div><div class="proj-scope">AgriTech · Intelligent Automation · Robotics Concept</div><p class="proj-desc">Designed an autonomous harvesting system concept for vegetable farms using intelligent automation and AI-assisted agricultural monitoring workflows.</p><div class="proj-tags"><span class="tag tag-ml">ML</span><span class="tag tag-py">Python</span></div></div></div>
    <div class="project-row"><div class="proj-num">11</div><div class="proj-body"><div class="proj-title">Additional Systems</div><div class="proj-scope">Systems Engineering · Web Frontend · Health Analytics</div><p class="proj-desc">Restaurant Menu & Billing System · Priority Scheduling Algorithm · Health Monitoring System · Kawasaki Frontend Demo · Portfolio Website — foundational engineering across C programming, web frontend, and health analytics.</p><div class="proj-tags"><span class="tag tag-web">C</span><span class="tag tag-web">HTML</span><span class="tag tag-py">Python</span></div></div></div>
  </div>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== SKILLS ======================== -->
<section class="section reveal">
  <div class="section-head">
    <span class="label">◈ Technical Infrastructure</span>
    <div class="line"></div>
    <span class="num">04</span>
  </div>
  <div class="skills-grid">
    <div class="skill-block">
      <div class="skill-block-title">Project & Operations</div>
      <div class="skill-row"><span class="skill-name">Project Coordination</span><div class="skill-bar"><div class="skill-fill fill-exp" style="--w:100%"></div></div><span class="skill-level lv-exp">Expert</span></div>
      <div class="skill-row"><span class="skill-name">Workflow Management</span><div class="skill-bar"><div class="skill-fill fill-exp" style="--w:100%"></div></div><span class="skill-level lv-exp">Expert</span></div>
      <div class="skill-row"><span class="skill-name">Agile Methodologies</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">Stakeholder Communication</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">Process Optimization</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:85%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">KPI Tracking</span><div class="skill-bar"><div class="skill-fill fill-exp" style="--w:100%"></div></div><span class="skill-level lv-exp">Expert</span></div>
      <div class="skill-row"><span class="skill-name">Risk Management</span><div class="skill-bar"><div class="skill-fill fill-pro" style="--w:76%"></div></div><span class="skill-level lv-pro">Proficient</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">Analytics & Tools</div>
      <div class="skill-row"><span class="skill-name">SQL</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">Power BI</span><div class="skill-bar"><div class="skill-fill fill-pro" style="--w:76%"></div></div><span class="skill-level lv-pro">Proficient</span></div>
      <div class="skill-row"><span class="skill-name">Excel</span><div class="skill-bar"><div class="skill-fill fill-exp" style="--w:100%"></div></div><span class="skill-level lv-exp">Expert</span></div>
      <div class="skill-row"><span class="skill-name">Data Visualization</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">GitHub</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">VS Code</span><div class="skill-bar"><div class="skill-fill fill-exp" style="--w:100%"></div></div><span class="skill-level lv-exp">Expert</span></div>
      <div class="skill-row"><span class="skill-name">Reporting Dashboards</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">AI & Automation</div>
      <div class="skill-row"><span class="skill-name">UiPath RPA</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">Machine Learning</span><div class="skill-bar"><div class="skill-fill fill-pro" style="--w:76%"></div></div><span class="skill-level lv-pro">Proficient</span></div>
      <div class="skill-row"><span class="skill-name">Generative AI</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">Prompt Engineering</span><div class="skill-bar"><div class="skill-fill fill-exp" style="--w:100%"></div></div><span class="skill-level lv-exp">Expert</span></div>
      <div class="skill-row"><span class="skill-name">Automation Anywhere</span><div class="skill-bar"><div class="skill-fill fill-pro" style="--w:76%"></div></div><span class="skill-level lv-pro">Proficient</span></div>
      <div class="skill-row"><span class="skill-name">AI Systems Design</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:85%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">Development</div>
      <div class="skill-row"><span class="skill-name">Python</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">HTML / CSS / JS</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:85%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
      <div class="skill-row"><span class="skill-name">C / C++</span><div class="skill-bar"><div class="skill-fill fill-int" style="--w:60%"></div></div><span class="skill-level lv-int">Intermediate</span></div>
      <div class="skill-row"><span class="skill-name">Java</span><div class="skill-bar"><div class="skill-fill fill-int" style="--w:60%"></div></div><span class="skill-level lv-int">Intermediate</span></div>
      <div class="skill-row"><span class="skill-name">Computer Vision</span><div class="skill-bar"><div class="skill-fill fill-pro" style="--w:76%"></div></div><span class="skill-level lv-pro">Proficient</span></div>
      <div class="skill-row"><span class="skill-name">Linux · macOS · Windows</span><div class="skill-bar"><div class="skill-fill fill-adv" style="--w:88%"></div></div><span class="skill-level lv-adv">Advanced</span></div>
    </div>
  </div>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== CERTIFICATIONS ======================== -->
<section class="section reveal">
  <div class="section-head">
    <span class="label">◈ Certifications</span>
    <div class="line"></div>
    <span class="num">05</span>
  </div>

  <div class="cert-count-banner">
    <div class="cert-big-num">22</div>
    <div>
      <div class="cert-count-label">Verified Certifications</div>
      <div class="cert-count-sub">Across Product · AI · Automation · Data · Networks · Systems</div>
    </div>
  </div>

  <table class="cert-table">
    <tbody>
      <tr><td class="cert-idx">01</td><td class="cert-name">Project Management Specialization</td><td class="cert-domain"><span class="domain-pill dp-pm">PM</span></td><td class="cert-issuer">Univ. of Colorado Boulder</td></tr>
      <tr><td class="cert-idx">02</td><td class="cert-name">Project Management Foundations and Initiation</td><td class="cert-domain"><span class="domain-pill dp-pm">PM</span></td><td class="cert-issuer">Univ. of Colorado Boulder</td></tr>
      <tr><td class="cert-idx">03</td><td class="cert-name">Generative AI with Large Language Models</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">DeepLearning.AI</td></tr>
      <tr><td class="cert-idx">04</td><td class="cert-name">Prompt Engineering for ChatGPT</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">Vanderbilt University</td></tr>
      <tr><td class="cert-idx">05</td><td class="cert-name">Generative AI for Everyone</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">DeepLearning.AI</td></tr>
      <tr><td class="cert-idx">06</td><td class="cert-name">Introduction to Generative AI</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">Google Cloud</td></tr>
      <tr><td class="cert-idx">07</td><td class="cert-name">Introduction to Large Language Models</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">Google Cloud</td></tr>
      <tr><td class="cert-idx">08</td><td class="cert-name">Build AI Apps with ChatGPT, DALL·E and GPT-4</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">Scrimba</td></tr>
      <tr><td class="cert-idx">09</td><td class="cert-name">ChatGPT Advanced Data Analysis</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">Coursera Project Network</td></tr>
      <tr><td class="cert-idx">10</td><td class="cert-name">Learn to Code with AI</td><td class="cert-domain"><span class="domain-pill dp-ai">AI</span></td><td class="cert-issuer">Scrimba</td></tr>
      <tr><td class="cert-idx">11</td><td class="cert-name">UiPath Certified Professional Automation Developer Associate</td><td class="cert-domain"><span class="domain-pill dp-auto">AUTO</span></td><td class="cert-issuer">UiPath</td></tr>
      <tr><td class="cert-idx">12</td><td class="cert-name">SQL for Data Science</td><td class="cert-domain"><span class="domain-pill dp-data">DATA</span></td><td class="cert-issuer">Great Learning</td></tr>
      <tr><td class="cert-idx">13</td><td class="cert-name">Supervised Machine Learning: Regression & Classification</td><td class="cert-domain"><span class="domain-pill dp-data">DATA</span></td><td class="cert-issuer">Stanford / DeepLearning.AI</td></tr>
      <tr><td class="cert-idx">14</td><td class="cert-name">Data Structures and Algorithms (Self-Paced)</td><td class="cert-domain"><span class="domain-pill dp-data">DATA</span></td><td class="cert-issuer">GeeksforGeeks</td></tr>
      <tr><td class="cert-idx">15</td><td class="cert-name">Dynamic Programming and Greedy Algorithms</td><td class="cert-domain"><span class="domain-pill dp-data">DATA</span></td><td class="cert-issuer">Univ. of Colorado Boulder</td></tr>
      <tr><td class="cert-idx">16</td><td class="cert-name">Algorithms on Strings</td><td class="cert-domain"><span class="domain-pill dp-data">DATA</span></td><td class="cert-issuer">UC San Diego</td></tr>
      <tr><td class="cert-idx">17</td><td class="cert-name">Approximation Algorithms and Linear Programming</td><td class="cert-domain"><span class="domain-pill dp-data">DATA</span></td><td class="cert-issuer">Univ. of Colorado Boulder</td></tr>
      <tr><td class="cert-idx">18</td><td class="cert-name">Specialization in Computer Communications</td><td class="cert-domain"><span class="domain-pill dp-net">NET</span></td><td class="cert-issuer">Univ. of Colorado Boulder</td></tr>
      <tr><td class="cert-idx">19</td><td class="cert-name">The Bits and Bytes of Computer Networking</td><td class="cert-domain"><span class="domain-pill dp-net">NET</span></td><td class="cert-issuer">Google</td></tr>
      <tr><td class="cert-idx">20</td><td class="cert-name">TCP/IP and Advanced Topics</td><td class="cert-domain"><span class="domain-pill dp-net">NET</span></td><td class="cert-issuer">Univ. of Colorado Boulder</td></tr>
      <tr><td class="cert-idx">21</td><td class="cert-name">Introduction to Hardware and Operating Systems</td><td class="cert-domain"><span class="domain-pill dp-net">SYS</span></td><td class="cert-issuer">IBM</td></tr>
      <tr><td class="cert-idx">22</td><td class="cert-name">Introduction to Internet of Things</td><td class="cert-domain"><span class="domain-pill dp-net">SYS</span></td><td class="cert-issuer">NPTEL</td></tr>
    </tbody>
  </table>
</section>

<div class="divider"><span>◈</span></div>

<!-- ======================== CONNECT ======================== -->
<section class="section reveal">
  <div class="section-head">
    <span class="label">◈ Connect</span>
    <div class="line"></div>
    <span class="num">06</span>
  </div>
  <div class="connect-grid">
    <a href="https://linkedin.com/in/thevinaykumar57" class="connect-card cc-li" target="_blank">
      <div class="connect-icon">⬡</div>
      <div class="connect-label">LinkedIn</div>
      <div class="connect-val">thevinaykumar57</div>
    </a>
    <a href="mailto:thevinaykumar57@gmail.com" class="connect-card cc-em" target="_blank">
      <div class="connect-icon">⬡</div>
      <div class="connect-label">Email</div>
      <div class="connect-val">thevinaykumar57@gmail.com</div>
    </a>
    <a href="https://github.com/thevinaykumar" class="connect-card cc-gh" target="_blank">
      <div class="connect-icon">⬡</div>
      <div class="connect-label">GitHub</div>
      <div class="connect-val">thevinaykumar</div>
    </a>
  </div>
</section>

<!-- ======================== FOOTER ======================== -->
<footer class="footer">
  <div class="footer-line">// END OF FILE — VINAY_KUMAR.PROFILE — 2025</div>
  <div class="footer-name">PRECISION · PRODUCT · TECHNOLOGY</div>
</footer>

</div><!-- /wrapper -->

<script>
// Staggered letter animation for name
const nameEl = document.getElementById('heroName');
const name = nameEl.textContent;
nameEl.innerHTML = name.split('').map((ch,i) =>
  ch === ' ' ? ' ' :
  `<span class="letter" style="animation-delay:${i*0.04}s">${ch}</span>`
).join('');

// Architect block particles
const container = document.getElementById('archParticles');
if(container){
  for(let i=0;i<20;i++){
    const p = document.createElement('div');
    p.className = 'arch-particle';
    p.style.cssText = `
      left:${Math.random()*100}%;
      bottom:${Math.random()*40}%;
      animation-duration:${2+Math.random()*3}s;
      animation-delay:${Math.random()*4}s;
      --drift:${(Math.random()-0.5)*60}px;
    `;
    container.appendChild(p);
  }
}

// Intersection observer for reveal
const obs = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if(e.isIntersecting) e.target.classList.add('visible');
  });
},{threshold:0.1});
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>
</body>
</html>
