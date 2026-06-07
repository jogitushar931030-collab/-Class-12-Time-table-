[nios_class12_mobile (2).html](https://github.com/user-attachments/files/28675707/nios_class12_mobile.2.html)
# -Class-12-Time-table-<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>NIOS · Class XII Timetable</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;800;900&family=Rajdhani:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
:root{
  --bg:#04080f;--p1:#0a1628;--p2:#0d1f3c;
  --c1:#f59e0b;--c2:#fbbf24;--c3:#10b981;--c4:#00d4ff;
  --c5:#ec4899;--c6:#f97316;--c7:#34d399;--c8:#a78bfa;
  --tx:#e2e8f0;--mt:#64748b;--mt2:#94a3b8;
  --gold:#f59e0b;
}

html,body{
  background:var(--bg);color:var(--tx);
  font-family:'Rajdhani',sans-serif;
  min-height:100vh;width:100%;overflow-x:hidden;
}

/* ══════════════════════════════════════
   SPLASH SCREEN
══════════════════════════════════════ */
#splash{
  position:fixed;inset:0;z-index:9999;
  background:var(--bg);
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;gap:20px;
  animation:splashOut .6s ease 2.6s forwards;
}
@keyframes splashOut{to{opacity:0;pointer-events:none;visibility:hidden}}

.splash-logo{
  width:90px;height:90px;border-radius:22px;
  background:linear-gradient(135deg,rgba(245,158,11,.25),rgba(251,191,36,.1));
  border:2px solid rgba(245,158,11,.5);
  display:flex;align-items:center;justify-content:center;
  font-family:'Orbitron',monospace;font-size:22px;font-weight:900;color:var(--gold);
  box-shadow:0 0 40px rgba(245,158,11,.3),0 0 80px rgba(245,158,11,.1);
  animation:logoIn .7s cubic-bezier(.34,1.56,.64,1) .2s both, logoPulse 2s ease .9s infinite;
}
@keyframes logoIn{from{transform:scale(0) rotate(-20deg);opacity:0}to{transform:scale(1) rotate(0);opacity:1}}
@keyframes logoPulse{0%,100%{box-shadow:0 0 40px rgba(245,158,11,.3)}50%{box-shadow:0 0 60px rgba(245,158,11,.6),0 0 100px rgba(245,158,11,.2)}}

.splash-title{
  font-family:'Orbitron',monospace;font-size:26px;font-weight:900;letter-spacing:3px;
  background:linear-gradient(90deg,var(--c1),var(--c2),#fff8e1,var(--c2),var(--c1));
  background-size:200%;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:titleIn .7s ease .5s both, shimmerText 3s linear infinite;
}
@keyframes titleIn{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
.splash-sub{
  font-size:14px;color:var(--mt2);letter-spacing:2px;text-transform:uppercase;
  animation:titleIn .7s ease .7s both;
}
.splash-class{
  font-family:'Orbitron',monospace;font-size:48px;font-weight:900;color:var(--gold);
  text-shadow:0 0 30px rgba(245,158,11,.6);
  animation:titleIn .8s cubic-bezier(.34,1.56,.64,1) .9s both;
}
.splash-bar{
  width:180px;height:3px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden;
  animation:titleIn .5s ease 1.2s both;
}
.splash-fill{
  height:100%;background:linear-gradient(90deg,var(--c1),var(--c2));
  border-radius:3px;
  animation:barFill 1.2s ease 1.3s both;
}
@keyframes barFill{from{width:0}to{width:100%}}
.splash-by{
  font-size:11px;color:var(--mt);letter-spacing:1.5px;
  animation:titleIn .5s ease 1.6s both;
}

/* ══════════════════════════════════════
   CANVAS BG
══════════════════════════════════════ */
#bgc{position:fixed;inset:0;z-index:0;pointer-events:none}

/* ══════════════════════════════════════
   MAIN SHELL
══════════════════════════════════════ */
.shell{
  position:relative;z-index:1;
  display:flex;flex-direction:column;
  min-height:100vh;
  padding-bottom:env(safe-area-inset-bottom);
  opacity:0;animation:shellIn .5s ease 2.8s forwards;
}
@keyframes shellIn{to{opacity:1}}

/* ══════════════════════════════════════
   TOP BAR
══════════════════════════════════════ */
.topbar{
  display:flex;align-items:center;justify-content:space-between;
  padding:16px 18px 12px;
  background:linear-gradient(180deg,rgba(4,8,15,.98),rgba(4,8,15,.88));
  position:sticky;top:0;z-index:100;
  border-bottom:1px solid rgba(245,158,11,.15);
  backdrop-filter:blur(12px);
}
/* animated gold border sweep on topbar */
.topbar::after{
  content:'';position:absolute;bottom:0;left:-100%;width:60%;height:1px;
  background:linear-gradient(90deg,transparent,rgba(245,158,11,.8),transparent);
  animation:borderSweep 3s ease-in-out infinite;
}
@keyframes borderSweep{0%{left:-60%}100%{left:160%}}

.brand{display:flex;align-items:center;gap:12px}
.brand-logo{
  width:48px;height:48px;border-radius:12px;
  background:linear-gradient(135deg,rgba(245,158,11,.2),rgba(251,191,36,.1));
  border:2px solid rgba(245,158,11,.4);
  display:flex;align-items:center;justify-content:center;
  font-family:'Orbitron',monospace;font-size:13px;font-weight:900;color:var(--gold);
  box-shadow:0 0 20px rgba(245,158,11,.2);
  animation:logoBeat 4s ease infinite;
}
@keyframes logoBeat{0%,100%{box-shadow:0 0 20px rgba(245,158,11,.2)}50%{box-shadow:0 0 35px rgba(245,158,11,.45)}}
.brand-text{display:flex;flex-direction:column;gap:1px}
.brand-title{
  font-family:'Orbitron',monospace;font-size:16px;font-weight:900;letter-spacing:2px;
  background:linear-gradient(90deg,var(--c1),var(--c2),#fff8e1,var(--c2),var(--c1));
  background-size:300%;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:shimmerText 4s linear infinite;
}
@keyframes shimmerText{0%{background-position:0%}100%{background-position:300%}}
.brand-sub{font-size:11px;color:var(--mt2);letter-spacing:.5px}

.top-right{display:flex;align-items:center;gap:10px}
.livebadge{
  display:flex;align-items:center;gap:6px;
  background:rgba(16,185,129,.1);border:1px solid rgba(16,185,129,.3);
  border-radius:24px;padding:5px 12px;
  font-family:'Orbitron',monospace;font-size:10px;color:var(--c3);letter-spacing:1px;
}
.dot{width:6px;height:6px;border-radius:50%;background:var(--c3);animation:dotPulse 1.5s ease infinite}
@keyframes dotPulse{0%,100%{box-shadow:0 0 0 0 rgba(16,185,129,.7);transform:scale(1)}50%{box-shadow:0 0 0 5px rgba(16,185,129,0);transform:scale(1.2)}}

.clock-block{text-align:right}
#clk{font-family:'Orbitron',monospace;font-size:22px;font-weight:700;color:var(--gold);line-height:1;
  text-shadow:0 0 12px rgba(245,158,11,.4);}
#ddate{font-family:'Orbitron',monospace;font-size:10px;color:var(--mt);letter-spacing:.5px;margin-top:3px}

/* ══════════════════════════════════════
   CLASS BADGE  (entrance anim)
══════════════════════════════════════ */
.class-badge{
  margin:14px 18px 0;
  display:flex;align-items:center;gap:14px;
  background:linear-gradient(135deg,rgba(245,158,11,.12),rgba(251,191,36,.05));
  border:1px solid rgba(245,158,11,.25);
  border-radius:16px;padding:14px 18px;
  position:relative;overflow:hidden;
  animation:cardSlideIn .6s cubic-bezier(.34,1.3,.64,1) both;
}
@keyframes cardSlideIn{from{opacity:0;transform:translateY(24px) scale(.97)}to{opacity:1;transform:translateY(0) scale(1)}}
/* shimmer sweep */
.class-badge::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(105deg,transparent 40%,rgba(245,158,11,.07) 50%,transparent 60%);
  background-size:200%;
  animation:cardShimmer 4s ease-in-out infinite;
}
@keyframes cardShimmer{0%{background-position:-200%}100%{background-position:200%}}

.cb-icon{font-size:32px;line-height:1;animation:iconFloat 3s ease-in-out infinite}
@keyframes iconFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}
.cb-info{flex:1}
.cb-class{
  font-family:'Orbitron',monospace;font-size:22px;font-weight:900;color:var(--gold);letter-spacing:2px;
  text-shadow:0 0 20px rgba(245,158,11,.4);
}
.cb-name{font-size:14px;color:var(--mt2);margin-top:2px;letter-spacing:.5px}
.cb-pills{display:flex;gap:6px;margin-top:8px;flex-wrap:wrap}
.cb-pill{
  font-family:'Orbitron',monospace;font-size:9px;letter-spacing:1px;
  padding:4px 10px;border-radius:20px;
  background:rgba(245,158,11,.1);border:1px solid rgba(245,158,11,.25);color:var(--gold);
  animation:pillPop .4s cubic-bezier(.34,1.56,.64,1) both;
}
.cb-pill:nth-child(1){animation-delay:.1s}
.cb-pill:nth-child(2){animation-delay:.2s}
.cb-pill:nth-child(3){animation-delay:.3s}
@keyframes pillPop{from{opacity:0;transform:scale(0)}to{opacity:1;transform:scale(1)}}

/* ══════════════════════════════════════
   NOW CARD
══════════════════════════════════════ */
.now-card{
  margin:14px 18px 0;
  background:linear-gradient(135deg,rgba(245,158,11,.1),rgba(0,212,255,.06));
  border:1px solid rgba(245,158,11,.35);border-radius:16px;padding:16px 18px;
  position:relative;overflow:hidden;
  animation:cardSlideIn .6s cubic-bezier(.34,1.3,.64,1) .1s both;
}
/* rotating glow orb */
.now-card::before{
  content:'';position:absolute;top:-30px;right:-30px;width:120px;height:120px;
  border-radius:50%;
  background:radial-gradient(circle,rgba(245,158,11,.18),transparent 70%);
  animation:orbRotate 6s linear infinite;
}
@keyframes orbRotate{from{transform:rotate(0deg) translateX(20px)}to{transform:rotate(360deg) translateX(20px)}}
/* scanning line */
.now-card::after{
  content:'';position:absolute;left:0;right:0;height:1px;top:0;
  background:linear-gradient(90deg,transparent,rgba(245,158,11,.5),transparent);
  animation:scanLine 2.5s ease-in-out infinite;
}
@keyframes scanLine{0%{top:0;opacity:1}100%{top:100%;opacity:0}}

.nc-label{font-family:'Orbitron',monospace;font-size:9px;letter-spacing:2px;color:var(--mt);margin-bottom:6px;text-transform:uppercase}
.nc-sub{font-size:22px;font-weight:700;color:var(--tx);line-height:1.2}
.nc-tc{font-size:14px;color:var(--c3);margin-top:5px}
.nc-time{font-family:'Orbitron',monospace;font-size:13px;color:var(--gold);margin-top:4px}

/* ══════════════════════════════════════
   STATS ROW
══════════════════════════════════════ */
.stats-row{display:flex;gap:10px;margin:14px 18px 0}
.scard{
  flex:1;background:var(--p1);border:1px solid rgba(255,255,255,.06);
  border-radius:14px;padding:14px 12px;text-align:center;
  position:relative;overflow:hidden;
  animation:cardSlideIn .6s cubic-bezier(.34,1.3,.64,1) .15s both;
  transition:transform .2s, box-shadow .2s;
}
.scard:active{transform:scale(.95)}
.scard::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,transparent,rgba(255,255,255,.03),transparent);
  animation:cardShimmer 5s ease-in-out infinite;
}
.sv{font-family:'Orbitron',monospace;font-size:28px;font-weight:700;line-height:1}
.sl{font-size:12px;color:var(--mt);margin-top:4px;letter-spacing:.5px}

/* ══════════════════════════════════════
   PROGRESS RING
══════════════════════════════════════ */
.ring-card{
  margin:14px 18px 0;
  background:var(--p1);border:1px solid rgba(255,255,255,.06);
  border-radius:16px;padding:16px 18px;
  display:flex;align-items:center;gap:18px;
  animation:cardSlideIn .6s cubic-bezier(.34,1.3,.64,1) .2s both;
  position:relative;overflow:hidden;
}
.ring-card::after{content:'';position:absolute;inset:0;background:linear-gradient(135deg,transparent,rgba(245,158,11,.03),transparent);animation:cardShimmer 6s ease-in-out infinite}
#pring{width:80px;height:80px;flex-shrink:0;filter:drop-shadow(0 0 8px rgba(245,158,11,.3))}
.ring-text{flex:1}
.ring-title{font-family:'Orbitron',monospace;font-size:10px;letter-spacing:2px;color:var(--mt);margin-bottom:4px}
#rpct2{font-family:'Orbitron',monospace;font-size:36px;font-weight:700;color:var(--gold);line-height:1;text-shadow:0 0 16px rgba(245,158,11,.4)}
.ring-sub{font-size:12px;color:var(--mt2);margin-top:4px}

/* ══════════════════════════════════════
   DAY TABS
══════════════════════════════════════ */
.day-tabs{
  display:flex;gap:8px;padding:14px 18px 0;
  overflow-x:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;
}
.day-tabs::-webkit-scrollbar{display:none}
.dtab{
  flex-shrink:0;padding:10px 14px;text-align:center;
  font-family:'Orbitron',monospace;font-size:11px;letter-spacing:1px;
  border-radius:12px;border:1px solid rgba(255,255,255,.07);
  background:var(--p1);cursor:pointer;
  transition:all .25s cubic-bezier(.34,1.3,.64,1);color:var(--mt);
  min-width:56px;position:relative;overflow:hidden;
}
.dtab::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(245,158,11,.08),transparent);
  opacity:0;transition:opacity .2s;
}
.dtab:active{transform:scale(.92)}
.dtab.act{
  background:rgba(245,158,11,.12);border-color:var(--gold);color:var(--gold);
  box-shadow:0 0 16px rgba(245,158,11,.2);transform:scale(1.05);
}
.dtab.act::after{opacity:1}

/* ══════════════════════════════════════
   TIMETABLE
══════════════════════════════════════ */
.tt-section{padding:14px 18px 0}
.sec-header{
  font-family:'Orbitron',monospace;font-size:10px;letter-spacing:2px;
  color:var(--mt);margin-bottom:10px;text-transform:uppercase;
  display:flex;align-items:center;gap:8px;
}
.sec-header::after{content:'';flex:1;height:1px;background:linear-gradient(90deg,rgba(245,158,11,.2),transparent)}

.prow{
  display:flex;align-items:center;gap:12px;
  background:var(--p1);border:1px solid rgba(255,255,255,.05);
  border-radius:14px;padding:13px 14px;
  position:relative;overflow:hidden;
  margin-bottom:8px;
  transition:border-color .25s, background .25s, transform .2s, box-shadow .2s;
  animation:rowIn .4s cubic-bezier(.34,1.2,.64,1) both;
  opacity:0;
}
@keyframes rowIn{
  from{opacity:0;transform:translateX(-20px) scale(.97)}
  to{opacity:1;transform:translateX(0) scale(1)}
}
.prow:active{transform:scale(.97);background:rgba(255,255,255,.03)}
.prow.now{
  border-color:var(--gold);
  background:rgba(245,158,11,.07);
  box-shadow:0 0 20px rgba(245,158,11,.15), inset 0 0 30px rgba(245,158,11,.04);
}
/* pulsing glow on current period */
.prow.now{animation:rowIn .4s cubic-bezier(.34,1.2,.64,1) both, nowGlow 2s ease-in-out infinite}
@keyframes nowGlow{0%,100%{box-shadow:0 0 16px rgba(245,158,11,.15)}50%{box-shadow:0 0 30px rgba(245,158,11,.35)}}

.prow.now::after{
  content:'NOW';position:absolute;right:12px;top:50%;transform:translateY(-50%);
  font-family:'Orbitron',monospace;font-size:8px;letter-spacing:1px;
  color:var(--c3);background:rgba(16,185,129,.12);border:1px solid rgba(16,185,129,.35);
  border-radius:6px;padding:3px 8px;
  animation:nowBadge 1.5s ease-in-out infinite;
}
@keyframes nowBadge{0%,100%{opacity:1}50%{opacity:.5}}

.prow.brk{
  justify-content:center;
  background:rgba(245,158,11,.03);border-color:rgba(245,158,11,.1);padding:10px 14px;
}
/* left accent bar */
.pbar{position:absolute;left:0;top:0;bottom:0;width:4px;background:var(--sc,var(--gold));border-radius:0;
  box-shadow:2px 0 10px var(--sc,var(--gold));
}
.pn{font-family:'Orbitron',monospace;font-size:10px;color:var(--mt);min-width:18px;text-align:center}
.ptime{min-width:72px}
.ptime .pt{font-family:'Orbitron',monospace;font-size:12px;font-weight:600;color:var(--sc,var(--gold));display:block;line-height:1.3}
.ptime small{font-size:10px;color:var(--mt)}
.psbj{flex:1;min-width:0}
.psbj strong{font-size:16px;font-weight:700;display:block;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:var(--tx)}
.psbj span{font-size:12px;color:var(--mt2);display:block;margin-top:2px}
.pico{font-size:22px;min-width:28px;text-align:center;transition:transform .3s}
.prow:active .pico{transform:scale(1.4) rotate(15deg)}
.brkt{font-family:'Orbitron',monospace;font-size:11px;letter-spacing:2px;color:var(--c1)}

/* ══════════════════════════════════════
   TEACHERS
══════════════════════════════════════ */
.tc-section{padding:14px 18px 0}
.teacher-list{display:flex;flex-direction:column;gap:8px}
.trow{
  display:flex;align-items:center;gap:12px;
  background:var(--p1);border:1px solid rgba(255,255,255,.05);
  border-radius:12px;padding:12px 14px;
  animation:cardSlideIn .5s cubic-bezier(.34,1.2,.64,1) both;
  transition:transform .2s;
}
.trow:active{transform:scale(.97)}
.tavatar{
  width:38px;height:38px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:11px;font-weight:700;font-family:'Orbitron',monospace;flex-shrink:0;
  animation:avatarSpin 0s;transition:transform .3s;
}
.trow:active .tavatar{transform:rotate(360deg)}
.tname{font-size:15px;font-weight:600;color:var(--tx);flex:1}
.tbar-wrap{width:60px;height:5px;background:rgba(255,255,255,.06);border-radius:3px}
.tbar-fill{height:100%;border-radius:3px;transition:width .8s cubic-bezier(.34,1.2,.64,1)}
.tcount{font-family:'Orbitron',monospace;font-size:12px;color:var(--mt);min-width:28px;text-align:right}

/* ══════════════════════════════════════
   WEEKLY BARS
══════════════════════════════════════ */
.week-section{padding:14px 18px 0}
.wbars{display:flex;align-items:flex-end;gap:6px;height:52px}
.wb{flex:1;border-radius:5px 5px 0 0;transition:height .7s cubic-bezier(.34,1.2,.64,1), opacity .4s;min-height:4px}
.wlabels{display:flex;gap:6px;margin-top:6px}
.wlabels span{flex:1;font-family:'Orbitron',monospace;font-size:9px;color:var(--mt);text-align:center}

/* ══════════════════════════════════════
   SUBJECTS
══════════════════════════════════════ */
.subj-section{padding:14px 18px 0}
.subj-pills{display:flex;flex-wrap:wrap;gap:8px}
.spill{
  font-family:'Rajdhani',sans-serif;font-size:13px;font-weight:600;
  padding:7px 14px;border-radius:24px;border:1px solid;letter-spacing:.3px;
  transition:transform .2s, box-shadow .2s;
  animation:pillPop .4s cubic-bezier(.34,1.56,.64,1) both;
}
.spill:active{transform:scale(.92)}

/* ══════════════════════════════════════
   TICKER
══════════════════════════════════════ */
.ticker-outer{
  overflow:hidden;height:22px;
  background:rgba(245,158,11,.04);
  border-top:1px solid rgba(245,158,11,.1);
  padding:0 12px;display:flex;align-items:center;
  margin-top:20px;
}
.ticker-inner{
  white-space:nowrap;
  font-family:'Orbitron',monospace;font-size:10px;
  color:rgba(245,158,11,.5);letter-spacing:1.5px;
  animation:tick 35s linear infinite;
}
@keyframes tick{0%{transform:translateX(100%)}100%{transform:translateX(-200%)}}

/* ══════════════════════════════════════
   WATERMARK — MADE BY TUSHAR
══════════════════════════════════════ */
.watermark{
  position:fixed;
  bottom:env(safe-area-inset-bottom, 16px);
  right:16px;
  z-index:500;
  display:flex;align-items:center;gap:7px;
  background:rgba(4,8,15,.75);
  border:1px solid rgba(245,158,11,.2);
  border-radius:30px;
  padding:6px 14px 6px 10px;
  backdrop-filter:blur(8px);
  box-shadow:0 4px 20px rgba(0,0,0,.4), 0 0 20px rgba(245,158,11,.08);
  animation:wmIn 1s cubic-bezier(.34,1.4,.64,1) 3.4s both, wmGlow 4s ease-in-out 4s infinite;
  cursor:default;user-select:none;
}
@keyframes wmIn{from{opacity:0;transform:translateY(30px) scale(.8)}to{opacity:1;transform:translateY(0) scale(1)}}
@keyframes wmGlow{0%,100%{box-shadow:0 4px 20px rgba(0,0,0,.4),0 0 16px rgba(245,158,11,.08)}50%{box-shadow:0 4px 28px rgba(0,0,0,.5),0 0 28px rgba(245,158,11,.22)}}

.wm-avatar{
  width:26px;height:26px;border-radius:50%;
  background:linear-gradient(135deg,var(--gold),#fb923c);
  display:flex;align-items:center;justify-content:center;
  font-family:'Orbitron',monospace;font-size:11px;font-weight:900;color:#000;
  flex-shrink:0;
  animation:avatarRotate 8s linear infinite;
}
@keyframes avatarRotate{0%{box-shadow:0 0 8px rgba(245,158,11,.6)}50%{box-shadow:0 0 18px rgba(245,158,11,.9)}100%{box-shadow:0 0 8px rgba(245,158,11,.6)}}

.wm-text{display:flex;flex-direction:column;gap:0}
.wm-made{font-size:8px;color:var(--mt);letter-spacing:1px;text-transform:uppercase}
.wm-name{
  font-family:'Orbitron',monospace;font-size:12px;font-weight:700;
  background:linear-gradient(90deg,var(--c1),var(--c2),#fff8e1,var(--c2),var(--c1));
  background-size:300%;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:shimmerText 3s linear infinite;
  letter-spacing:1px;
}

/* ══════════════════════════════════════
   FLOATING SPARKLES
══════════════════════════════════════ */
.sparkle{
  position:fixed;pointer-events:none;z-index:2;
  width:4px;height:4px;border-radius:50%;
  background:var(--gold);
  animation:sparkleFloat linear infinite;
  opacity:0;
}
@keyframes sparkleFloat{
  0%{opacity:0;transform:translateY(0) scale(0)}
  10%{opacity:.8}
  90%{opacity:.3}
  100%{opacity:0;transform:translateY(-120px) scale(.3)}
}

/* RIPPLE on tap */
.ripple{
  position:absolute;border-radius:50%;
  background:rgba(245,158,11,.25);
  transform:scale(0);
  animation:rippleAnim .5s linear;
  pointer-events:none;
}
@keyframes rippleAnim{to{transform:scale(4);opacity:0}}

/* foot space */
.foot-space{height:70px}
</style>
</head>
<body>

<!-- SPLASH -->
<div id="splash">
  <div class="splash-logo">NV</div>
  <div class="splash-title">NIOS · VIDYA</div>
  <div class="splash-sub">Class XII Dashboard</div>
  <div class="splash-class">XII</div>
  <div class="splash-bar"><div class="splash-fill"></div></div>
  <div class="splash-by">✦ Made by Tushar ✦</div>
</div>

<!-- FLOATING SPARKLES -->
<div id="sparkles"></div>

<!-- CANVAS BG -->
<canvas id="bgc"></canvas>

<div class="shell">

  <!-- TOP BAR -->
  <div class="topbar">
    <div class="brand">
      <div class="brand-logo">NV</div>
      <div class="brand-text">
        <div class="brand-title">NIOS · VIDYA</div>
        <div class="brand-sub">Vidya &amp; Child Development Centre</div>
      </div>
    </div>
    <div class="top-right">
      <div class="livebadge"><span class="dot"></span>LIVE</div>
      <div class="clock-block">
        <div id="clk">--:--:--</div>
        <div id="ddate">---</div>
      </div>
    </div>
  </div>

  <!-- CLASS BADGE -->
  <div class="class-badge">
    <div class="cb-icon">🏆</div>
    <div class="cb-info">
      <div class="cb-class">CLASS XII</div>
      <div class="cb-name">Senior Secondary · NIOS Board</div>
      <div class="cb-pills">
        <span class="cb-pill">CUET PREP</span>
        <span class="cb-pill">6 DAYS / WEEK</span>
        <span class="cb-pill">ENGLISH MEDIUM</span>
      </div>
    </div>
  </div>

  <!-- NOW IN CLASS -->
  <div class="now-card">
    <div class="nc-label">Now In Class</div>
    <div class="nc-sub" id="ncSub">—</div>
    <div class="nc-tc" id="ncTc"></div>
    <div class="nc-time" id="ncTime"></div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="scard">
      <div class="sv" style="color:#10b981" id="sdone">0</div>
      <div class="sl">Done</div>
    </div>
    <div class="scard">
      <div class="sv" style="color:#a78bfa" id="srem">0</div>
      <div class="sl">Remaining</div>
    </div>
    <div class="scard">
      <div class="sv" style="color:var(--gold)" id="rpct">0%</div>
      <div class="sl">Progress</div>
    </div>
  </div>

  <!-- PROGRESS RING -->
  <div class="ring-card">
    <svg id="pring" viewBox="0 0 80 80">
      <circle cx="40" cy="40" r="32" fill="none" stroke="rgba(245,158,11,.08)" stroke-width="6"/>
      <circle id="rarc" cx="40" cy="40" r="32" fill="none" stroke="var(--gold)" stroke-width="6"
        stroke-linecap="round" stroke-dasharray="201" stroke-dashoffset="201"
        transform="rotate(-90 40 40)" style="transition:stroke-dashoffset .9s cubic-bezier(.34,1.2,.64,1)"/>
    </svg>
    <div class="ring-text">
      <div class="ring-title">School Day Progress</div>
      <div id="rpct2" style="font-family:Orbitron,monospace;font-size:36px;font-weight:700;color:var(--gold);line-height:1;text-shadow:0 0 16px rgba(245,158,11,.4)">0%</div>
      <div class="ring-sub">9:00 AM – 4:00 PM</div>
    </div>
  </div>

  <!-- DAY TABS -->
  <div class="day-tabs">
    <div class="dtab" data-d="MON" onclick="selDay('MON',this)">MON</div>
    <div class="dtab" data-d="TUE" onclick="selDay('TUE',this)">TUE</div>
    <div class="dtab" data-d="WED" onclick="selDay('WED',this)">WED</div>
    <div class="dtab" data-d="THUR" onclick="selDay('THUR',this)">THU</div>
    <div class="dtab" data-d="FRI" onclick="selDay('FRI',this)">FRI</div>
    <div class="dtab" data-d="SAT" onclick="selDay('SAT',this)">SAT</div>
  </div>

  <!-- TIMETABLE -->
  <div class="tt-section">
    <div class="sec-header">📅 Timetable</div>
    <div id="ttPanel"></div>
  </div>

  <!-- TEACHERS -->
  <div class="tc-section">
    <div class="sec-header">👤 Teachers Today</div>
    <div class="teacher-list" id="tcList"></div>
  </div>

  <!-- WEEKLY BARS -->
  <div class="week-section">
    <div class="sec-header">📊 Weekly Periods</div>
    <div class="wbars" id="wbars"></div>
    <div class="wlabels" id="wlabels"></div>
  </div>

  <!-- SUBJECTS -->
  <div class="subj-section">
    <div class="sec-header">📚 Subjects This Day</div>
    <div class="subj-pills" id="spills"></div>
  </div>

  <!-- TICKER -->
  <div class="ticker-outer">
    <div class="ticker-inner">
      ● CLASS XII · NIOS VIDYA &amp; CHILD DEVELOPMENT CENTRE &nbsp;&nbsp;
      ● TEACHERS: DHRITI · PRIYA · UMESH · DURGA · SIDDHARTH · RK · CHITRA &nbsp;&nbsp;
      ● SUBJECTS: ENGLISH · HINDI · MATHS · HOME SCIENCE · DATA ENTRY · REASONING · PAINTING · LIFE SKILL · CUET · MATR &nbsp;&nbsp;
      ● Keep striving for excellence every day! &nbsp;&nbsp;
      ✦ Made by Tushar ✦ &nbsp;&nbsp;
    </div>
  </div>

  <div class="foot-space"></div>
</div>

<!-- WATERMARK -->
<div class="watermark">
  <div class="wm-avatar">T</div>
  <div class="wm-text">
    <span class="wm-made">Made by</span>
    <span class="wm-name">TUSHAR</span>
  </div>
</div>

<script>
/* ─── DATA ─── */
const DB={
  'XII':{
    color:'#f59e0b',
    MON:[
      {t:'9:00',t2:'9:45',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'9:45',t2:'10:30',s:'Career',tc:'RK',i:'🎯',c:'#a78bfa'},
      {t:'10:30',t2:'11:15',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'11:15',t2:'12:00',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'12:00',t2:'12:20',s:'LUNCH BREAK',tc:'',i:'🍱',c:''},
      {t:'12:20',t2:'1:05',s:'Reasoning',tc:'Umesh',i:'🧮',c:'#06b6d4'},
      {t:'1:05',t2:'1:50',s:'Life Skill',tc:'Siddharth',i:'🌱',c:'#ec4899'},
      {t:'1:50',t2:'2:35',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'2:35',t2:'2:50',s:'SHORT BREAK',tc:'',i:'☕',c:''},
      {t:'2:50',t2:'3:25',s:'MATR',tc:'Siddharth',i:'📐',c:'#fb923c'},
      {t:'3:25',t2:'4:00',s:'MATR',tc:'Siddharth',i:'📐',c:'#fb923c'},
    ],
    TUE:[
      {t:'9:00',t2:'9:45',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'9:45',t2:'10:30',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'10:30',t2:'11:15',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'11:15',t2:'12:00',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'12:00',t2:'12:20',s:'LUNCH BREAK',tc:'',i:'🍱',c:''},
      {t:'12:20',t2:'1:05',s:'Reasoning',tc:'Umesh',i:'🧮',c:'#06b6d4'},
      {t:'1:05',t2:'1:50',s:'Life Skill',tc:'Siddharth',i:'🌱',c:'#ec4899'},
      {t:'1:50',t2:'2:35',s:'Life Skill',tc:'Siddharth',i:'🌱',c:'#ec4899'},
      {t:'2:35',t2:'2:50',s:'SHORT BREAK',tc:'',i:'☕',c:''},
      {t:'2:50',t2:'3:25',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'3:25',t2:'4:00',s:'MATR',tc:'Siddharth',i:'📐',c:'#fb923c'},
    ],
    WED:[
      {t:'9:00',t2:'9:45',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'9:45',t2:'10:30',s:'Data Entry',tc:'Durga',i:'💻',c:'#10b981'},
      {t:'10:30',t2:'11:15',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'11:15',t2:'12:00',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'12:00',t2:'12:20',s:'LUNCH BREAK',tc:'',i:'🍱',c:''},
      {t:'12:20',t2:'1:05',s:'Maths',tc:'Umesh',i:'📐',c:'#7c3aed'},
      {t:'1:05',t2:'1:50',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'1:50',t2:'2:35',s:'Painting',tc:'Umesh',i:'🎨',c:'#f97316'},
      {t:'2:35',t2:'2:50',s:'SHORT BREAK',tc:'',i:'☕',c:''},
      {t:'2:50',t2:'3:25',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'3:25',t2:'4:00',s:'MATR',tc:'Siddharth',i:'📐',c:'#fb923c'},
    ],
    THUR:[
      {t:'9:00',t2:'9:45',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'9:45',t2:'10:30',s:'Data Entry',tc:'Durga',i:'💻',c:'#10b981'},
      {t:'10:30',t2:'11:15',s:'Home Science',tc:'Chitra',i:'🏠',c:'#a78bfa'},
      {t:'11:15',t2:'12:00',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'12:00',t2:'12:20',s:'LUNCH BREAK',tc:'',i:'🍱',c:''},
      {t:'12:20',t2:'1:05',s:'Maths',tc:'Umesh',i:'📐',c:'#7c3aed'},
      {t:'1:05',t2:'1:50',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'1:50',t2:'2:35',s:'Painting',tc:'Umesh',i:'🎨',c:'#f97316'},
      {t:'2:35',t2:'2:50',s:'SHORT BREAK',tc:'',i:'☕',c:''},
      {t:'2:50',t2:'3:25',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'3:25',t2:'4:00',s:'CUET Prep',tc:'Faculty',i:'🏆',c:'#34d399'},
    ],
    FRI:[
      {t:'9:00',t2:'9:45',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'9:45',t2:'10:30',s:'Data Entry',tc:'Durga',i:'💻',c:'#10b981'},
      {t:'10:30',t2:'11:15',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'11:15',t2:'12:00',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'12:00',t2:'12:20',s:'LUNCH BREAK',tc:'',i:'🍱',c:''},
      {t:'12:20',t2:'1:05',s:'Free Period',tc:'—',i:'📋',c:'#64748b'},
      {t:'1:05',t2:'1:50',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'1:50',t2:'2:35',s:'Painting',tc:'Umesh',i:'🎨',c:'#f97316'},
      {t:'2:35',t2:'2:50',s:'SHORT BREAK',tc:'',i:'☕',c:''},
      {t:'2:50',t2:'3:25',s:'Data Entry',tc:'Durga',i:'💻',c:'#10b981'},
      {t:'3:25',t2:'4:00',s:'CUET Prep',tc:'Faculty',i:'🏆',c:'#34d399'},
    ],
    SAT:[
      {t:'9:00',t2:'9:45',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'9:45',t2:'10:30',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'10:30',t2:'11:15',s:'Eng Expression',tc:'Siddharth',i:'✍️',c:'#38bdf8'},
      {t:'11:15',t2:'12:00',s:'Hindi',tc:'Priya',i:'🇮🇳',c:'#f59e0b'},
      {t:'12:00',t2:'12:20',s:'LUNCH BREAK',tc:'',i:'🍱',c:''},
      {t:'12:20',t2:'1:05',s:'Games',tc:'Durga',i:'🏃',c:'#34d399'},
      {t:'1:05',t2:'1:50',s:'English',tc:'Dhriti',i:'📖',c:'#00d4ff'},
      {t:'1:50',t2:'2:35',s:'Painting',tc:'Umesh',i:'🎨',c:'#f97316'},
      {t:'2:35',t2:'2:50',s:'SHORT BREAK',tc:'',i:'☕',c:''},
      {t:'2:50',t2:'3:25',s:'Data Entry',tc:'Durga',i:'💻',c:'#10b981'},
      {t:'3:25',t2:'4:00',s:'CUET Prep',tc:'Faculty',i:'🏆',c:'#34d399'},
    ],
  }
};
const TEACHER_COLORS={
  'Dhriti':'#00d4ff','Priya':'#f59e0b','Umesh':'#7c3aed',
  'Durga':'#10b981','Siddharth':'#ec4899','RK':'#a78bfa',
  'Chitra':'#f97316','Faculty':'#34d399'
};
const jdm=[null,'MON','TUE','WED','THUR','FRI','SAT'];
let curDay='MON';

function toMin(ts){
  const p=ts.split(':');let h=parseInt(p[0]),m=parseInt(p[1]||0);
  if(h<8)h+=12;return h*60+m;
}
function nowMin(){const n=new Date();return n.getHours()*60+n.getMinutes();}

/* ─── RIPPLE ─── */
function addRipple(e,el){
  const r=document.createElement('span');
  r.className='ripple';
  const rect=el.getBoundingClientRect();
  const size=Math.max(rect.width,rect.height);
  const x=(e.clientX||e.touches?.[0]?.clientX||rect.left+rect.width/2)-rect.left-size/2;
  const y=(e.clientY||e.touches?.[0]?.clientY||rect.top+rect.height/2)-rect.top-size/2;
  r.style.cssText=`width:${size}px;height:${size}px;left:${x}px;top:${y}px`;
  el.appendChild(r);
  setTimeout(()=>r.remove(),500);
}

function selDay(d,el){
  curDay=d;
  document.querySelectorAll('.dtab').forEach(x=>x.classList.remove('act'));
  el.classList.add('act');
  render();
}

function render(){
  const periods=(DB['XII'][curDay]||[]);
  const nm=nowMin();
  const panel=document.getElementById('ttPanel');
  panel.innerHTML='';
  let pn=1;
  periods.forEach((p,i)=>{
    const isB=!p.tc;
    const isNow=!isB&&nm>=toMin(p.t)&&nm<toMin(p.t2);
    const div=document.createElement('div');
    div.className='prow'+(isB?' brk':'')+(isNow?' now':'');
    div.style.animationDelay=(i*.05)+'s';
    if(isB){
      div.innerHTML=`<span class="brkt">— ${p.s} &nbsp; ${p.t} – ${p.t2} —</span>`;
    } else {
      div.style.setProperty('--sc',p.c||'#f59e0b');
      div.innerHTML=`<div class="pbar"></div>
        <span class="pn">${pn}</span>
        <div class="ptime"><span class="pt">${p.t}</span><small>–${p.t2}</small></div>
        <div class="psbj"><strong>${p.s}</strong><span>👤 ${p.tc}</span></div>
        <div class="pico">${p.i}</div>`;
      pn++;
    }
    div.addEventListener('touchstart',e=>addRipple(e,div),{passive:true});
    div.addEventListener('mousedown',e=>addRipple(e,div));
    panel.appendChild(div);
  });
  updateSide(periods,nm);
  buildTeacherList(periods);
  buildSubjPills(periods);
  buildWeeklyBars();
}

function updateSide(periods,nm){
  const real=periods.filter(p=>p.tc&&p.tc!=='');
  let cur=null,done=0,rem=0;
  real.forEach(p=>{
    const s=toMin(p.t),e=toMin(p.t2);
    if(nm>=e)done++;else if(nm<s)rem++;
    if(nm>=s&&nm<e)cur=p;
  });
  document.getElementById('sdone').textContent=done;
  document.getElementById('srem').textContent=rem;
  const sub=document.getElementById('ncSub');
  const tc=document.getElementById('ncTc');
  const ti=document.getElementById('ncTime');
  if(cur){sub.textContent=cur.s;tc.textContent='👤 '+cur.tc;ti.textContent=cur.t+' – '+cur.t2;}
  else{
    const nxt=real.find(p=>toMin(p.t)>nm);
    if(nxt){sub.textContent='Next: '+nxt.s;tc.textContent='👤 '+nxt.tc;ti.textContent='Starting @ '+nxt.t;}
    else{sub.textContent='School Over';tc.textContent='See you tomorrow!';ti.textContent='';}
  }
  const pct=Math.min(100,Math.max(0,Math.round((nm-9*60)/(7*60)*100)));
  document.getElementById('rarc').style.strokeDashoffset=201-(201*pct/100);
  document.getElementById('rpct').textContent=pct+'%';
  document.getElementById('rpct2').textContent=pct+'%';
}

function buildTeacherList(periods){
  const real=periods.filter(p=>p.tc&&p.tc!=='—'&&p.tc!=='');
  const counts={};
  real.forEach(p=>{const k=p.tc.split('/')[0];counts[k]=(counts[k]||0)+1;});
  const sorted=Object.entries(counts).sort((a,b)=>b[1]-a[1]).slice(0,6);
  const max=sorted[0]?sorted[0][1]:1;
  const el=document.getElementById('tcList');
  el.innerHTML='';
  sorted.forEach(([name,cnt],idx)=>{
    const col=TEACHER_COLORS[name]||'#64748b';
    const init=name.substring(0,2).toUpperCase();
    const pct=Math.round(cnt/max*100);
    const row=document.createElement('div');
    row.className='trow';
    row.style.animationDelay=(idx*.07)+'s';
    row.innerHTML=`<div class="tavatar" style="background:${col}22;color:${col};border:1px solid ${col}55">${init}</div>
      <div class="tname">${name}</div>
      <div class="tbar-wrap"><div class="tbar-fill" style="width:0%;background:${col}" data-w="${pct}"></div></div>
      <div class="tcount">${cnt}p</div>`;
    row.addEventListener('touchstart',e=>addRipple(e,row),{passive:true});
    el.appendChild(row);
  });
  // animate bars after paint
  requestAnimationFrame(()=>requestAnimationFrame(()=>{
    document.querySelectorAll('.tbar-fill[data-w]').forEach(b=>{
      b.style.width=b.dataset.w+'%';
    });
  }));
}

function buildSubjPills(periods){
  const real=periods.filter(p=>p.tc&&p.tc!=='');
  const seen=new Set();
  const el=document.getElementById('spills');
  el.innerHTML='';
  let delay=0;
  real.forEach(p=>{
    if(!seen.has(p.s)){
      seen.add(p.s);
      const pill=document.createElement('div');
      pill.className='spill';
      pill.style.cssText=`color:${p.c||'#64748b'};border-color:${p.c||'#64748b'}44;background:${p.c||'#64748b'}11;animation-delay:${delay}s`;
      pill.textContent=p.i+' '+p.s;
      pill.addEventListener('touchstart',e=>addRipple(e,pill),{passive:true});
      el.appendChild(pill);
      delay+=.06;
    }
  });
}

function buildWeeklyBars(){
  const days=['MON','TUE','WED','THUR','FRI','SAT'];
  const lbl=['MON','TUE','WED','THU','FRI','SAT'];
  const cols=['#00d4ff','#f59e0b','#7c3aed','#10b981','#ec4899','#f97316'];
  const counts=days.map(d=>(DB['XII'][d]||[]).filter(p=>p.tc&&p.tc!=='').length);
  const mx=Math.max(...counts)||1;
  const wb=document.getElementById('wbars');
  const wl=document.getElementById('wlabels');
  wb.innerHTML='';wl.innerHTML='';
  days.forEach((d,i)=>{
    const b=document.createElement('div');
    b.className='wb';
    b.style.cssText=`height:0;background:${cols[i]};opacity:${d===curDay?'1':'0.3'}`;
    wb.appendChild(b);
    // animate height
    setTimeout(()=>{b.style.height=Math.round(counts[i]/mx*50)+'px';},100+i*80);
    const l=document.createElement('span');
    l.textContent=lbl[i];
    l.style.cssText=`flex:1;font-family:Orbitron,monospace;font-size:9px;color:${d===curDay?cols[i]:'#64748b'};text-align:center`;
    wl.appendChild(l);
  });
}

function tickClock(){
  const n=new Date();
  const h=String(n.getHours()).padStart(2,'0');
  const m=String(n.getMinutes()).padStart(2,'0');
  const s=String(n.getSeconds()).padStart(2,'0');
  document.getElementById('clk').textContent=`${h}:${m}:${s}`;
  const days=['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
  const months=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  document.getElementById('ddate').textContent=`${days[n.getDay()]} ${n.getDate()} ${months[n.getMonth()]} ${n.getFullYear()}`;
  updateSide((DB['XII'][curDay]||[]).filter(x=>x.tc&&x.tc!==''),nowMin());
}

/* ─── CANVAS ANIMATED BACKGROUND ─── */
const canvas=document.getElementById('bgc');
const ctx=canvas.getContext('2d');
function resizeCv(){canvas.width=window.innerWidth;canvas.height=document.documentElement.scrollHeight||window.innerHeight;}
resizeCv();
window.addEventListener('resize',resizeCv);
window.addEventListener('scroll',()=>{canvas.height=document.documentElement.scrollHeight||window.innerHeight;},{ passive:true });

const pts=Array.from({length:55},()=>({
  x:Math.random()*window.innerWidth,
  y:Math.random()*(window.innerHeight*2),
  vx:(Math.random()-.5)*.3,vy:(Math.random()-.5)*.3,
  r:Math.random()*2+.4,a:Math.random()*.22+.05,
  hue:Math.random()>0.7?220:45 // mostly gold, some blue
}));
// Large slow orbs
const orbs=Array.from({length:5},()=>({
  x:Math.random()*window.innerWidth,y:Math.random()*window.innerHeight,
  vx:(Math.random()-.5)*.05,vy:(Math.random()-.5)*.05,
  r:Math.random()*80+50
}));

function animBg(){
  const W=canvas.width,H=canvas.height;
  ctx.clearRect(0,0,W,H);
  // grid dots
  for(let x=0;x<W;x+=52)for(let y=0;y<H;y+=52){
    ctx.beginPath();ctx.arc(x,y,.8,0,Math.PI*2);
    ctx.fillStyle='rgba(245,158,11,.025)';ctx.fill();
  }
  // slow glow orbs
  orbs.forEach(o=>{
    o.x+=o.vx;o.y+=o.vy;
    if(o.x<-o.r)o.x=W+o.r;if(o.x>W+o.r)o.x=-o.r;
    if(o.y<-o.r)o.y=H+o.r;if(o.y>H+o.r)o.y=-o.r;
    const g=ctx.createRadialGradient(o.x,o.y,0,o.x,o.y,o.r);
    g.addColorStop(0,'rgba(245,158,11,.04)');
    g.addColorStop(1,'transparent');
    ctx.beginPath();ctx.arc(o.x,o.y,o.r,0,Math.PI*2);
    ctx.fillStyle=g;ctx.fill();
  });
  // particles + connections
  pts.forEach(p=>{
    p.x+=p.vx;p.y+=p.vy;
    if(p.x<0)p.x=W;if(p.x>W)p.x=0;
    if(p.y<0)p.y=H;if(p.y>H)p.y=0;
    ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
    const c=p.hue===45?`rgba(245,158,11,${p.a})`:`rgba(0,212,255,${p.a*.6})`;
    ctx.fillStyle=c;ctx.fill();
  });
  for(let i=0;i<pts.length;i++)for(let j=i+1;j<pts.length;j++){
    const dx=pts[i].x-pts[j].x,dy=pts[i].y-pts[j].y,d=Math.sqrt(dx*dx+dy*dy);
    if(d<100){
      ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);
      ctx.strokeStyle=`rgba(245,158,11,${.04*(1-d/100)})`;ctx.lineWidth=.6;ctx.stroke();
    }
  }
  requestAnimationFrame(animBg);
}

/* ─── FLOATING SPARKLES ─── */
function spawnSparkle(){
  const s=document.createElement('div');
  s.className='sparkle';
  const x=Math.random()*window.innerWidth;
  const dur=3+Math.random()*4;
  const size=Math.random()*4+2;
  const colors=['#f59e0b','#fbbf24','#00d4ff','#10b981','#ec4899'];
  s.style.cssText=`left:${x}px;bottom:0;width:${size}px;height:${size}px;
    background:${colors[Math.floor(Math.random()*colors.length)]};
    box-shadow:0 0 ${size*2}px currentColor;
    animation-duration:${dur}s;animation-delay:0s`;
  document.getElementById('sparkles').appendChild(s);
  setTimeout(()=>s.remove(),dur*1000);
}
setInterval(spawnSparkle,400);

/* ─── INIT ─── */
const today=jdm[new Date().getDay()]||'MON';
const tEl=document.querySelector(`[data-d="${today}"]`);
if(tEl){document.querySelectorAll('.dtab').forEach(x=>x.classList.remove('act'));tEl.classList.add('act');curDay=today;}
render();
tickClock();
setInterval(tickClock,1000);
animBg();

/* ripple on day tabs */
document.querySelectorAll('.dtab').forEach(el=>{
  el.addEventListener('touchstart',e=>addRipple(e,el),{passive:true});
  el.addEventListener('mousedown',e=>addRipple(e,el));
});
</script>
</body>
</html>
