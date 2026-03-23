<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>DataMate — AI Data Intelligence para Latinoamérica</title>
<meta name="description" content="Construimos modelos de AI que llegan a producción. Datos sintéticos + validación humana + AutoML. DataRobot Official Partner LatAm.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400&family=Roboto+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/three@0.157.0/build/three.min.js"></script>
<script type="module" src="https://unpkg.com/@splinetool/viewer@1.9.96/build/spline-viewer.js"></script>
<style>
:root{--m:#00FFB3;--v:#746AFC;--bg:#000;--mu:rgba(255,255,255,.55);--bd:rgba(0,255,179,.15);--bdh:rgba(0,255,179,.4);--ca:rgba(255,255,255,.04);--ff:'DM Sans',sans-serif;--fm:'Roboto Mono',monospace}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:var(--bg);color:#fff;font-family:var(--ff);overflow-x:hidden}
body::before{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(116,106,252,.07) 1px,transparent 1px),linear-gradient(90deg,rgba(116,106,252,.07) 1px,transparent 1px);background-size:56px 56px;pointer-events:none;z-index:0}
.c{max-width:1180px;margin:0 auto;padding:0 24px;position:relative;z-index:1}
section{padding:96px 0;position:relative}
.sh{margin-bottom:52px}
.ey{font-family:var(--fm);font-size:11px;letter-spacing:.2em;text-transform:uppercase;color:var(--v);margin-bottom:12px}
.h2{font-family:var(--ff);font-size:clamp(32px,4vw,52px);font-weight:700;line-height:1.15;letter-spacing:-.02em}
.mint{color:var(--m)} .vi{color:var(--v)} .mu{color:var(--mu)}
.btn{display:inline-flex;align-items:center;gap:8px;padding:14px 28px;border:none;border-radius:6px;cursor:pointer;font-family:var(--ff);font-weight:700;font-size:15px;text-decoration:none;transition:.3s;white-space:nowrap}
.bm{background:var(--m);color:#000}.bm:hover{box-shadow:0 0 32px rgba(0,255,179,.4);transform:scale(1.03)}
.bv{background:transparent;color:var(--v);border:1px solid var(--v)}.bv:hover{background:rgba(116,106,252,.1)}
.bfw{width:100%;justify-content:center;padding:14px;font-size:14px}
.glass{background:var(--ca);border:1px solid var(--bd);border-radius:12px}
/* Nav */
#nav{position:fixed;top:0;left:0;right:0;z-index:900;padding:18px 0;transition:.4s}
#nav.s{background:rgba(0,0,0,.95);border-bottom:1px solid var(--bd);padding:12px 0;backdrop-filter:blur(20px)}
.ni{display:flex;align-items:center;justify-content:space-between;gap:20px}
.logo{display:flex;align-items:center;gap:10px;text-decoration:none}
.lw{font-family:var(--fm);font-size:13px;letter-spacing:.25em;color:#fff}
.nl{display:flex;align-items:center;gap:28px;list-style:none}
.nl a{font-family:var(--fm);font-size:10px;letter-spacing:.12em;text-transform:uppercase;color:var(--mu);text-decoration:none;transition:.2s}
.nl a:hover{color:#fff}
.nc{display:flex;align-items:center;gap:10px}
.ng{font-family:var(--fm);font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:var(--mu);text-decoration:none;transition:.2s}
.ng:hover{color:#fff}
.np{font-family:var(--ff);font-size:13px;font-weight:700;background:var(--m);color:#000;padding:10px 20px;border-radius:6px;text-decoration:none;transition:.3s}
.np:hover{box-shadow:0 0 24px rgba(0,255,179,.4)}
.np.pulse{animation:npulse 2.5s ease-in-out infinite}
@keyframes npulse{0%,100%{box-shadow:0 0 0 0 rgba(0,255,179,.3)}50%{box-shadow:0 0 0 8px rgba(0,255,179,0)}}
.hb{display:none;flex-direction:column;gap:5px;cursor:pointer}
.hb span{display:block;width:22px;height:2px;background:#fff;border-radius:2px}
/* Hero */
#hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;overflow:hidden}
#hc{position:absolute;inset:0;z-index:0}
#spline-hero-wrap{width:100%;height:500px;position:relative;overflow:hidden;border-radius:24px;mask-image:radial-gradient(ellipse at center,black 60%,transparent 100%);-webkit-mask-image:-webkit-radial-gradient(center,ellipse cover,black 58%,transparent 100%)}
#spline-hero{position:absolute;width:220%;height:180%;left:-55%;top:-40%;pointer-events:auto}
#spline-hero::part(logo){display:none}
.hct{position:relative;z-index:2;padding:100px 0 40px}
.hg{display:grid;grid-template-columns:60% 40%;gap:52px;align-items:center}
.tb{display:inline-flex;align-items:center;gap:8px;padding:5px 12px;background:rgba(0,255,179,.07);border:1px solid var(--m);border-radius:100px;font-family:var(--fm);font-size:10px;color:var(--m);margin-bottom:18px;opacity:0;transform:translateY(-10px)}
.h1x{font-family:var(--ff);font-size:clamp(44px,6vw,80px);font-weight:800;line-height:1.08;letter-spacing:-.03em}
.hl{display:block;overflow:hidden}
.hl span{display:block;transform:translateY(110%)}
.hq{font-family:var(--fm);font-size:11px;letter-spacing:.15em;color:var(--mu);margin:18px 0;text-transform:uppercase}
.hs{font-size:17px;line-height:1.7;color:rgba(255,255,255,.7);max-width:520px;margin-bottom:30px;opacity:0}
.hca{display:flex;flex-direction:column;gap:10px;opacity:0}
.hcar{display:flex;align-items:center;gap:14px;flex-wrap:wrap}
.hst{font-family:var(--fm);font-size:11px;color:var(--mu)}
/* ROI Card */
.rc{background:var(--ca);border:1px solid var(--bd);border-radius:16px;padding:26px;opacity:0;transform:translateX(40px)}
.rch{display:flex;align-items:center;justify-content:space-between;margin-bottom:22px}
.rct{font-family:var(--fm);font-size:9px;letter-spacing:.15em;color:var(--mu);text-transform:uppercase}
.rcb{font-family:var(--fm);font-size:9px;color:var(--v);background:rgba(116,106,252,.1);border:1px solid rgba(116,106,252,.3);padding:3px 10px;border-radius:100px}
.rm{margin-bottom:18px}
.rmh{display:flex;justify-content:space-between;align-items:center;margin-bottom:7px}
.rml{font-size:13px;color:rgba(255,255,255,.8)}
.rmv{font-family:var(--fm);font-size:13px;font-weight:600;color:var(--m)}
.rbt{height:4px;background:rgba(255,255,255,.08);border-radius:2px;overflow:hidden}
.rbf{height:100%;background:linear-gradient(90deg,var(--m),rgba(0,255,179,.5));border-radius:2px;width:0;transition:width 2s ease;box-shadow:0 0 8px rgba(0,255,179,.5)}
.rs{font-family:var(--fm);font-size:9px;color:var(--mu);margin-top:18px;padding-top:14px;border-top:1px solid rgba(255,255,255,.06);text-transform:uppercase;letter-spacing:.08em}
/* Proof strip */
.ps{margin-top:48px;padding-top:22px;border-top:1px solid rgba(255,255,255,.06);position:relative;z-index:2;display:flex;align-items:center;gap:24px;flex-wrap:wrap}
.pst{font-family:var(--fm);font-size:9px;letter-spacing:.12em;color:var(--mu);text-transform:uppercase;flex-shrink:0}
.plr{display:flex;align-items:center;gap:24px;flex-wrap:wrap}
.lp{font-family:var(--fm);font-size:11px;letter-spacing:.2em;color:rgba(255,255,255,.18);text-transform:uppercase;font-weight:600}
/* Use Cases */
.tsw{display:flex;gap:8px;margin-bottom:36px;flex-wrap:wrap}
.tbt{font-family:var(--fm);font-size:10px;letter-spacing:.15em;text-transform:uppercase;padding:9px 18px;border-radius:100px;border:1px solid rgba(255,255,255,.15);background:transparent;color:rgba(255,255,255,.4);cursor:pointer;transition:.3s}
.tbt:hover{border-color:rgba(255,255,255,.4);color:rgba(255,255,255,.8)}
.tbt.a{border-color:var(--m);color:var(--m);background:rgba(0,255,179,.05)}
.tc{display:none}
.tc.a{display:grid;grid-template-columns:1fr 1fr;gap:36px;animation:fi .4s ease}
@keyframes fi{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
.plb,.slb{font-family:var(--fm);font-size:10px;letter-spacing:.2em;text-transform:uppercase;color:var(--v);margin-bottom:8px}
.pt,.st{color:rgba(255,255,255,.75);font-size:15px;line-height:1.7;margin-bottom:20px}
.rca{background:rgba(0,255,179,.04);border:1px solid rgba(0,255,179,.2);border-radius:10px;padding:22px;margin-top:20px}
.rcat{font-family:var(--fm);font-size:9px;letter-spacing:.2em;text-transform:uppercase;color:var(--m);margin-bottom:12px}
.ri{display:flex;align-items:flex-start;gap:8px;color:rgba(255,255,255,.9);font-size:14px;line-height:1.5;margin-bottom:7px}
.ri::before{content:'↑';color:var(--m);font-family:var(--fm);font-size:11px;flex-shrink:0}
.proofla{font-family:var(--fm);font-size:9px;letter-spacing:.1em;color:var(--mu);margin-top:10px}
.ucta{display:inline-flex;align-items:center;gap:6px;font-size:13px;font-weight:600;color:var(--m);text-decoration:none;margin-top:18px;transition:.2s}
.ucta:hover{gap:10px}
/* Stats */
#stats{position:relative;overflow:hidden}
#sc{position:absolute;inset:0;z-index:0;opacity:.35}
.scn{position:relative;z-index:1}
.sg{display:grid;grid-template-columns:repeat(4,1fr);gap:18px;margin-bottom:48px}
.scard{background:var(--ca);border:1px solid var(--bd);border-radius:12px;padding:26px 22px;text-align:center;transition:.3s;cursor:default}
.scard:hover{transform:translateY(-6px);box-shadow:0 16px 40px rgba(0,255,179,.1);border-color:var(--bdh)}
.sn{font-family:var(--fm);font-size:52px;font-weight:700;color:var(--m);line-height:1;margin-bottom:8px;text-shadow:0 0 30px rgba(0,255,179,.4)}
.sl{font-size:14px;color:rgba(255,255,255,.85);margin-bottom:10px;line-height:1.4}
.ss{font-family:var(--fm);font-size:9px;letter-spacing:.1em;color:var(--v);text-transform:uppercase;line-height:1.4}
.pb{background:var(--ca);border:1px solid var(--bd);border-radius:12px;padding:28px 36px;display:flex;align-items:center;gap:36px}
.pbi{width:52px;height:52px;background:rgba(0,255,179,.1);border:2px solid var(--m);border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:22px;flex-shrink:0}
.pbl{font-family:var(--fm);font-size:8px;letter-spacing:.15em;color:var(--m);text-transform:uppercase;line-height:1.5;margin-top:6px;text-align:center}
.pq{font-size:17px;font-style:italic;line-height:1.6;color:rgba(255,255,255,.8)}
.pa{font-family:var(--fm);font-size:9px;letter-spacing:.1em;color:var(--mu);text-transform:uppercase;margin-top:8px}
/* Timeline */
.tl{position:relative;margin-bottom:40px}
.tll{position:absolute;top:22px;left:10%;right:10%;height:1px;background:rgba(255,255,255,.08);z-index:0}
.tllf{position:absolute;top:22px;left:10%;height:1px;background:linear-gradient(90deg,var(--m),var(--v));width:0;z-index:1;transition:width 2s ease;box-shadow:0 0 8px rgba(0,255,179,.5)}
.tls{display:grid;grid-template-columns:repeat(5,1fr);gap:16px;position:relative;z-index:2}
.ts{padding:0 6px;opacity:0;transform:translateY(20px)}
.tsn{font-family:var(--fm);font-size:10px;letter-spacing:.2em;color:var(--mu);margin-bottom:14px;text-align:center}
.tsd{width:10px;height:10px;border-radius:50%;border:2px solid rgba(255,255,255,.2);background:#000;margin:0 auto 16px;transition:.3s}
.ts.act .tsd{border-color:var(--m);box-shadow:0 0 12px rgba(0,255,179,.5)}
.tsc{background:var(--ca);border:1px solid var(--bd);border-radius:10px;padding:18px 14px;transition:.3s}
.ts:hover .tsc{background:rgba(0,255,179,.04)}
.tstag{font-family:var(--fm);font-size:8px;letter-spacing:.15em;text-transform:uppercase;color:var(--m);margin-bottom:7px}
.tsi{font-size:20px;margin-bottom:8px}
.tstt{font-size:14px;font-weight:700;color:#fff;margin-bottom:7px;line-height:1.3}
.tsb{font-size:12px;line-height:1.6;color:var(--mu)}
.tsdur{display:inline-block;margin-top:9px;font-family:var(--fm);font-size:8px;letter-spacing:.1em;color:var(--v);background:rgba(116,106,252,.1);border:1px solid rgba(116,106,252,.2);padding:3px 8px;border-radius:100px}
.tlcta{text-align:center;margin-top:40px}
/* Who We Serve */
.pg{display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-bottom:36px}
.pc{background:var(--ca);border:1px solid var(--bd);border-radius:12px;padding:26px 22px;transition:.3s}
.pc:hover{border-color:var(--bdh);transform:translateY(-4px)}
.pbdg{display:inline-block;font-family:var(--fm);font-size:8px;letter-spacing:.15em;text-transform:uppercase;color:var(--v);background:rgba(116,106,252,.1);border:1px solid rgba(116,106,252,.2);padding:3px 10px;border-radius:100px;margin-bottom:12px}
.ptt{font-size:18px;font-weight:700;margin-bottom:16px}
.til{list-style:none;display:flex;flex-direction:column;gap:9px}
.tix{display:flex;align-items:flex-start;gap:9px;font-size:13px;color:rgba(255,255,255,.8);line-height:1.5}
.tck{color:var(--m);font-family:var(--fm);font-size:11px;flex-shrink:0}
.nfy{background:rgba(255,255,255,.02);border:1px solid rgba(255,255,255,.06);border-radius:10px;padding:22px 26px;font-family:var(--fm);font-size:11px;letter-spacing:.04em;color:var(--mu);line-height:1.8}
/* Lead Magnet */
#lm{position:relative}
#lm::before{content:'';position:absolute;inset:0;background:rgba(116,106,252,.04);pointer-events:none}
.lg{display:grid;grid-template-columns:55% 45%;gap:52px;align-items:center;position:relative;z-index:1}
.lchk{list-style:none;display:flex;flex-direction:column;gap:11px;margin:22px 0 24px}
.lci{display:flex;align-items:flex-start;gap:10px;font-size:15px;color:rgba(255,255,255,.85);line-height:1.5}
.lck{color:var(--m);font-family:var(--fm);font-size:12px;flex-shrink:0}
.lsp{font-family:var(--fm);font-size:9px;letter-spacing:.1em;color:var(--v);text-transform:uppercase}
.lf{background:var(--ca);border:1px solid var(--bd);border-radius:16px;padding:32px 28px}
.ff{margin-bottom:14px}
.fll{display:block;font-size:12px;font-weight:500;color:var(--mu);margin-bottom:5px}
.fi,.fsel,.fta{width:100%;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.1);border-radius:6px;padding:11px 13px;color:#fff;font-family:var(--ff);font-size:14px;outline:none;transition:.2s}
.fi:focus,.fsel:focus,.fta:focus{border-color:var(--m)}
.fsel{appearance:none;cursor:pointer}
.fsel option{background:#111;color:#fff}
.fta{resize:vertical;min-height:75px}
.fd{font-family:var(--fm);font-size:9px;color:var(--mu);margin-top:10px;line-height:1.6}
/* FAQ */
.fqi{border-bottom:1px solid rgba(255,255,255,.06)}
.fqi:first-child{border-top:1px solid rgba(255,255,255,.06)}
.fqq{display:flex;align-items:center;justify-content:space-between;padding:22px 0;cursor:pointer;gap:18px}
.fqqt{font-size:17px;font-weight:600;color:rgba(255,255,255,.85);line-height:1.4;transition:.2s}
.fqi.op .fqqt{color:#fff}
.fqic{width:30px;height:30px;border:1px solid rgba(255,255,255,.15);border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:16px;color:var(--mu);transition:.3s}
.fqi.op .fqic{border-color:var(--v);color:var(--v);transform:rotate(45deg)}
.fqa{max-height:0;overflow:hidden;transition:max-height .4s ease,padding .4s ease}
.fqi.op .fqa{max-height:300px;padding-bottom:22px}
.fqat{font-size:15px;line-height:1.7;color:var(--mu);border-left:2px solid var(--v);padding-left:18px}
/* Final CTA */
#fcta{min-height:100vh;display:flex;align-items:center;position:relative;overflow:hidden}
#cc{position:absolute;inset:0;z-index:0}
.fcc{position:relative;z-index:1;text-align:center;max-width:760px;margin:0 auto}
.fch{font-family:var(--ff);font-size:clamp(34px,5vw,58px);font-weight:800;line-height:1.15;letter-spacing:-.03em;margin-bottom:18px}
.fcs{font-size:18px;color:var(--mu);margin-bottom:44px;line-height:1.6}
.fcf{background:var(--ca);border:1px solid var(--bd);border-radius:16px;padding:36px;text-align:left;max-width:540px;margin:0 auto 20px}
.fcfg{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px}
.cts{display:flex;align-items:center;justify-content:center;gap:18px;flex-wrap:wrap}
.ct{font-family:var(--fm);font-size:10px;letter-spacing:.08em;color:var(--mu)}
.alt{font-size:13px;color:var(--mu);text-align:center;margin-top:18px}
.alt a{color:var(--v);text-decoration:underline;cursor:pointer}
/* Footer */
#footer{background:#0A0A0A;border-top:1px solid var(--m);padding:60px 0 0}
.fg{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:44px;margin-bottom:44px}
.fgt{font-size:14px;color:var(--mu);line-height:1.6;margin:12px 0 18px}
.fct{font-family:var(--fm);font-size:9px;letter-spacing:.2em;text-transform:uppercase;color:var(--mu);margin-bottom:14px}
.fl2{list-style:none;display:flex;flex-direction:column;gap:9px}
.fl2 a{font-size:14px;color:rgba(255,255,255,.6);text-decoration:none;transition:.2s}
.fl2 a:hover{color:#fff}
.fbot{border-top:1px solid rgba(255,255,255,.06);padding:18px 0;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:10px}
.fleg{font-family:var(--fm);font-size:9px;letter-spacing:.08em;color:var(--mu)}
.fll{display:flex;gap:18px}
.fll a{font-family:var(--fm);font-size:9px;letter-spacing:.08em;color:var(--mu);text-decoration:none}
.fll a:hover{color:#fff}
/* Mobile sticky */
.msb{display:none;position:fixed;bottom:0;left:0;right:0;z-index:800;background:rgba(0,0,0,.95);border-top:1px solid var(--bd);padding:10px 20px;backdrop-filter:blur(20px)}
/* Mobile menu */
#mm{display:none;position:fixed;inset:0;z-index:950;background:rgba(0,0,0,.97);backdrop-filter:blur(20px);flex-direction:column;align-items:center;justify-content:center;gap:28px}
#mm.op{display:flex}
#mm a{font-family:var(--fm);font-size:18px;letter-spacing:.15em;text-transform:uppercase;color:#fff;text-decoration:none}
.mmc{position:absolute;top:22px;right:22px;background:none;border:none;color:#fff;font-size:22px;cursor:pointer}
/* Reveal */
.rv{opacity:0;transform:translateY(28px);transition:opacity .7s ease,transform .7s ease}
.rv.vis{opacity:1;transform:translateY(0)}
/* Responsive */
@media(max-width:1024px){.hg{grid-template-columns:1fr}.sg{grid-template-columns:1fr 1fr}.tls{grid-template-columns:1fr 1fr}.pg{grid-template-columns:1fr}.lg{grid-template-columns:1fr}.fg{grid-template-columns:1fr 1fr}}
@media(max-width:768px){.nl,.ng{display:none}.hb{display:flex}.msb{display:block}section{padding:64px 0}.tc.a{grid-template-columns:1fr}.tls{grid-template-columns:1fr}.tll,.tllf{display:none}.pb{flex-direction:column;text-align:center}.fcfg{grid-template-columns:1fr}.fg{grid-template-columns:1fr}.hcar{flex-direction:column;align-items:flex-start}}
</style>
</head>
<body>
<!-- Mobile Menu -->
<div id="mm">
  <button class="mmc" id="mmc">✕</button>
  <a href="#use-cases">Casos de Uso</a>
  <a href="#how-it-works">Cómo Funciona</a>
  <a href="#who-we-serve">Industrias</a>
  <a href="#fcta">Partners</a>
  <a href="#fcta" class="btn bm" style="margin-top:16px">Agendar diagnóstico →</a>
</div>
<!-- Nav -->
<nav id="nav">
  <div class="c"><div class="ni">
    <a href="#" class="logo">
      <svg width="34" height="34" viewBox="0 0 36 36" fill="none">
        <circle cx="18" cy="18" r="16" stroke="#00FFB3" stroke-width="1.5"/>
        <circle cx="18" cy="18" r="3" fill="#00FFB3"/>
        <circle cx="18" cy="8" r="1.5" fill="#00FFB3" opacity=".6"/>
        <circle cx="28" cy="13" r="1.5" fill="#00FFB3" opacity=".6"/>
        <circle cx="28" cy="23" r="1.5" fill="#00FFB3" opacity=".6"/>
        <circle cx="18" cy="28" r="1.5" fill="#00FFB3" opacity=".6"/>
        <circle cx="8" cy="23" r="1.5" fill="#00FFB3" opacity=".6"/>
        <circle cx="8" cy="13" r="1.5" fill="#00FFB3" opacity=".6"/>
        <line x1="18" y1="18" x2="18" y2="8" stroke="#00FFB3" stroke-width=".75" opacity=".4"/>
        <line x1="18" y1="18" x2="28" y2="13" stroke="#00FFB3" stroke-width=".75" opacity=".4"/>
        <line x1="18" y1="18" x2="28" y2="23" stroke="#00FFB3" stroke-width=".75" opacity=".4"/>
        <line x1="18" y1="18" x2="18" y2="28" stroke="#00FFB3" stroke-width=".75" opacity=".4"/>
        <line x1="18" y1="18" x2="8" y2="23" stroke="#00FFB3" stroke-width=".75" opacity=".4"/>
        <line x1="18" y1="18" x2="8" y2="13" stroke="#00FFB3" stroke-width=".75" opacity=".4"/>
      </svg>
      <span class="lw">D A T A M A T E</span>
    </a>
    <ul class="nl">
      <li><a href="#use-cases">Casos de Uso</a></li>
      <li><a href="#how-it-works">Cómo Funciona</a></li>
      <li><a href="#who-we-serve">Industrias</a></li>
      <li><a href="#stats">Partners</a></li>
    </ul>
    <div class="nc">
      <a href="#use-cases" class="ng">Ver casos de uso</a>
      <a href="#fcta" class="np" id="ncp">Agendar diagnóstico →</a>
    </div>
    <div class="hb" id="hb"><span></span><span></span><span></span></div>
  </div></div>
</nav>
<!-- HERO -->
<section id="hero">
  <div class="c hct">
    <div class="hg">
      <div>
        <div class="tb" id="tb">🤝 DataRobot Official Partner — Latin America</div>
        <div class="ey" id="ey" style="margin-bottom:14px;opacity:0">AI DATA INTELLIGENCE · LATAM</div>
        <h1 class="h1x">
          <span class="hl"><span id="hl1">De datos desordenados a</span></span>
          <span class="hl"><span id="hl2">modelos que generan</span></span>
          <span class="hl"><span id="hl3" class="mint">impacto real.</span></span>
        </h1>
        <p class="hq">Para equipos de banca · telecom · retail · salud</p>
        <p class="hs" id="hs">Ayudamos a empresas en Latinoamérica a construir modelos de AI que llegan a producción — incluso cuando los datos son incompletos, regulados o fragmentados. AutoML + datos sintéticos + validación humana experta.</p>
        <div class="hca" id="hca">
          <div class="hcar">
            <a href="#fcta" class="btn bm">Agendar diagnóstico gratuito →</a>
            <a href="#use-cases" class="btn bv">Ver casos de uso ↓</a>
          </div>
          <span class="hst">Llamada de 30 min · Sin compromiso · Respuesta en 24h</span>
        </div>
      </div>
      <div>
        <div id="spline-hero-wrap">
          <spline-viewer id="spline-hero" url="https://prod.spline.design/7cXMHe7RkWdRTG4d/scene.splinecode" loading-anim-type="none"></spline-viewer>
        </div>
      </div>
    </div>
    <div class="ps">
      <span class="pst">Ya usan esta metodología:</span>
      <div class="plr">
        <span class="lp">BANCOLOMBIA</span><span class="lp">CLARO</span>
        <span class="lp">FALABELLA</span><span class="lp">SURA</span>
        <span class="lp">NUTRESA</span><span class="lp">GRUPO ISS</span>
      </div>
    </div>
  </div>
</section>
<!-- USE CASES -->
<section id="use-cases">
  <div class="c">
    <div class="sh rv">
      <div class="ey">CASOS DE USO COMPROBADOS</div>
      <h2 class="h2">¿Tu industria ya está usando AI predictiva?</h2>
    </div>
    <div class="tsw">
      <button class="tbt a" data-tab="banca">🏦 Banca</button>
      <button class="tbt" data-tab="telecom">📡 Telecom</button>
      <button class="tbt" data-tab="retail">🛒 Retail</button>
      <button class="tbt" data-tab="salud">🏥 Salud</button>
    </div>
    <div class="tc a" id="tab-banca">
      <div>
        <div class="plb">PROBLEMA PRINCIPAL</div>
        <p class="pt">Alta morosidad en cartera retail con modelos de scoring desactualizados y datos fragmentados entre core bancario, CRM y burós externos.</p>
        <div class="slb">SOLUCIÓN DATAMATE</div>
        <p class="st">Generación de datos sintéticos de comportamiento crediticio + validación por expertos en riesgo financiero + modelo de scoring en DataRobot en producción.</p>
        <a href="#fcta" class="ucta">Ver cómo funciona para banca →</a>
      </div>
      <div>
        <div class="rca">
          <div class="rcat">RESULTADOS</div>
          <div class="ri">34% reducción en tasa de morosidad</div>
          <div class="ri">66% menos tiempo de delivery de modelos</div>
          <div class="ri">Modelo en producción en 8 semanas</div>
          <div class="proofla">↳ Metodología aplicada en banco multinacional — DataRobot</div>
        </div>
      </div>
    </div>
    <div class="tc" id="tab-telecom">
      <div>
        <div class="plb">PROBLEMA PRINCIPAL</div>
        <p class="pt">Churn impredecible en base prepago con señales de comportamiento en silos: app, call center, red, facturación.</p>
        <div class="slb">SOLUCIÓN DATAMATE</div>
        <p class="st">Síntesis de datos de comportamiento multisistema + modelo predictivo de churn con RLHF de expertos en UX de telecom.</p>
        <a href="#fcta" class="ucta">Ver cómo funciona para telecom →</a>
      </div>
      <div>
        <div class="rca">
          <div class="rcat">RESULTADOS</div>
          <div class="ri">Reducción de churn en segmento prepago</div>
          <div class="ri">Intervención 30 días antes del abandono</div>
          <div class="ri">ROI positivo en 3 meses</div>
          <div class="proofla">↳ Metodología aplicada en operador regional — DataRobot</div>
        </div>
      </div>
    </div>
    <div class="tc" id="tab-retail">
      <div>
        <div class="plb">PROBLEMA PRINCIPAL</div>
        <p class="pt">Forecasting de demanda inexacto genera sobre-stock en 40% de SKUs y quiebres en productos de alta rotación.</p>
        <div class="slb">SOLUCIÓN DATAMATE</div>
        <p class="st">Datos sintéticos de demanda estacional + variables externas (clima, eventos, macro) + modelo de forecast en DataRobot con validación de category managers.</p>
        <a href="#fcta" class="ucta">Ver cómo funciona para retail →</a>
      </div>
      <div>
        <div class="rca">
          <div class="rcat">RESULTADOS</div>
          <div class="ri">25% reducción en costos de inventario</div>
          <div class="ri">Accuracy &gt;90% en forecast de 30 días</div>
          <div class="ri">Desplegado en 30 tiendas</div>
          <div class="proofla">↳ Fabricante multinacional — DataRobot</div>
        </div>
      </div>
    </div>
    <div class="tc" id="tab-salud">
      <div>
        <div class="plb">PROBLEMA PRINCIPAL</div>
        <p class="pt">Datos de pacientes regulados (HIPAA, marcos locales de privacidad) imposibles de usar directamente para entrenar modelos clínicos de riesgo.</p>
        <div class="slb">SOLUCIÓN DATAMATE</div>
        <p class="st">Generación de datos clínicos sintéticos privacy-safe + anotación por médicos especialistas + modelo de riesgo clínico auditable en DataRobot.</p>
        <a href="#fcta" class="ucta">Ver cómo funciona para salud →</a>
      </div>
      <div>
        <div class="rca">
          <div class="rcat">RESULTADOS</div>
          <div class="ri">Datos 100% compliance-safe</div>
          <div class="ri">Modelo clínico en producción</div>
          <div class="ri">Auditado por equipo de riesgo médico</div>
          <div class="proofla">↳ Red de salud multinacional — DataRobot</div>
        </div>
      </div>
    </div>
  </div>
</section>
<!-- STATS -->
<section id="stats">
  <canvas id="sc"></canvas>
  <div class="c scn">
    <div class="sh rv">
      <div class="ey">RESULTADOS COMPROBADOS</div>
      <h2 class="h2">Números reales de empresas reales</h2>
    </div>
    <div class="sg">
      <div class="scard rv">
        <div class="sn" id="s1">66</div>
        <div class="sl">Reducción en tiempo de delivery de modelos</div>
        <div class="ss">Banco multinacional · vía DataRobot</div>
      </div>
      <div class="scard rv">
        <div class="sn" id="s2">20x</div>
        <div class="sl">Más casos de uso en producción en el mismo período</div>
        <div class="ss">CVS Health · vía DataRobot</div>
      </div>
      <div class="scard rv">
        <div class="sn" id="s3">25</div>
        <div class="sl">Reducción de costos de producción por vehículo</div>
        <div class="ss">Fabricante multinacional · vía DataRobot</div>
      </div>
      <div class="scard rv">
        <div class="sn" id="s4">8</div>
        <div class="sl">Semanas promedio: datos a modelo en producción</div>
        <div class="ss">Proyectos DataMate LatAm</div>
      </div>
    </div>
    <div class="pb rv" style="gap:36px">
      <div style="flex-shrink:0;text-align:center">
        <div class="pbi">🤝</div>
        <div class="pbl">DataRobot<br>Official Partner<br>Latin America</div>
      </div>
      <div>
        <p class="pq">"La velocidad y calidad que obtenemos en casos de uso es asombrosa. Los modelos llegan a producción en una fracción del tiempo normal."</p>
        <div class="pa">↳ Fabricante multinacional · vía DataRobot</div>
      </div>
    </div>
  </div>
</section>
<!-- HOW IT WORKS -->
<section id="how-it-works">
  <div class="c">
    <div class="sh rv">
      <div class="ey">METODOLOGÍA</div>
      <h2 class="h2">De datos imperfectos a modelos<br>en producción — sin fricción.</h2>
    </div>
    <div class="tl">
      <div class="tll"></div>
      <div class="tllf" id="tllf"></div>
      <div class="tls">
        <div class="ts" id="ts0">
          <div class="tsn">01</div>
          <div class="tsd"></div>
          <div class="tsc">
            <div class="tstag">SIN COSTO</div>
            <div class="tsi">🔍</div>
            <div class="tstt">Auditoría de datos y objetivos</div>
            <div class="tsb">Evaluamos tu landscape de datos, gaps de calidad, restricciones de compliance y el caso de uso con mayor ROI potencial.</div>
            <span class="tsdur">30 min · Remoto</span>
          </div>
        </div>
        <div class="ts" id="ts1">
          <div class="tsn">02</div>
          <div class="tsd"></div>
          <div class="tsc">
            <div class="tsi">🧪</div>
            <div class="tstt">Generación de datos sintéticos</div>
            <div class="tsb">Creamos datasets de entrenamiento de alta calidad, privacidad-safe, específicos a tu dominio.</div>
            <span class="tsdur">1–2 semanas</span>
          </div>
        </div>
        <div class="ts" id="ts2">
          <div class="tsn">03</div>
          <div class="tsd"></div>
          <div class="tsc">
            <div class="tsi">👥</div>
            <div class="tstt">Red de expertos humanos</div>
            <div class="tsb">Especialistas en tu vertical validan, anotan y rankean los datos. RLHF real, no crowdsourcing.</div>
            <span class="tsdur">1–2 semanas</span>
          </div>
        </div>
        <div class="ts" id="ts3">
          <div class="tsn">04</div>
          <div class="tsd"></div>
          <div class="tsc">
            <div class="tsi">⚡</div>
            <div class="tstt">AutoML + Fine-tuning</div>
            <div class="tsb">Entrenamos en DataRobot con los datos validados. Modelo auditado, explicable y listo para producción.</div>
            <span class="tsdur">2–3 semanas</span>
          </div>
        </div>
        <div class="ts" id="ts4">
          <div class="tsn">05</div>
          <div class="tsd"></div>
          <div class="tsc">
            <div class="tsi">🚀</div>
            <div class="tstt">Deploy y monitoreo continuo</div>
            <div class="tsb">Tu modelo entra a producción con monitoreo de drift, alertas automáticas y mejora continua.</div>
            <span class="tsdur">Ongoing</span>
          </div>
        </div>
      </div>
    </div>
    <div class="tlcta rv">
      <a href="#fcta" class="btn bm" style="font-size:16px;padding:16px 36px">Empieza con el diagnóstico gratuito →</a>
    </div>
  </div>
</section>
<!-- WHO WE SERVE -->
<section id="who-we-serve">
  <div class="c">
    <div class="sh rv">
      <div class="ey">PARA QUIÉN ES DATAMATE</div>
      <h2 class="h2">Construido para equipos que no<br>pueden permitirse fallar en AI.</h2>
    </div>
    <div class="pg">
      <div class="pc rv">
        <div class="pbdg">COMPRADOR PRINCIPAL</div>
        <div class="ptt">CTO / Head of AI</div>
        <ul class="til">
          <li class="tix"><span class="tck">✓</span>Tienes datos pero no modelos en producción</li>
          <li class="tix"><span class="tck">✓</span>Tu equipo lleva 6+ meses sin delivery</li>
          <li class="tix"><span class="tck">✓</span>Compliance bloquea el uso de datos reales</li>
          <li class="tix"><span class="tck">✓</span>Necesitas justificar ROI al directorio</li>
        </ul>
      </div>
      <div class="pc rv">
        <div class="pbdg">USUARIO TÉCNICO</div>
        <div class="ptt">VP Data / Chief Data Officer</div>
        <ul class="til">
          <li class="tix"><span class="tck">✓</span>Modelos que se degradan en producción</li>
          <li class="tix"><span class="tck">✓</span>Falta de datos anotados por expertos</li>
          <li class="tix"><span class="tck">✓</span>AutoML sin contexto de dominio</li>
          <li class="tix"><span class="tck">✓</span>Equipos pequeños, demanda alta</li>
        </ul>
      </div>
      <div class="pc rv">
        <div class="pbdg">PATROCINADOR</div>
        <div class="ptt">Innovation Lead / DX Manager</div>
        <ul class="til">
          <li class="tix"><span class="tck">✓</span>Necesitas un caso de uso de AI exitoso en &lt;6 meses</li>
          <li class="tix"><span class="tck">✓</span>Buscas partner, no proveedor</li>
          <li class="tix"><span class="tck">✓</span>Presupuesto definido, falta ejecución</li>
        </ul>
      </div>
    </div>
    <div class="nfy rv">
      <strong style="color:rgba(255,255,255,.5)">DataMate no es para:</strong> startups sin datos, proyectos de exploración sin presupuesto, o empresas que buscan reemplazar su equipo. Somos el acelerador que hace que tu equipo entregue más, más rápido.
    </div>
  </div>
</section>
<!-- LEAD MAGNET -->
<section id="lm">
  <div class="c">
    <div class="lg">
      <div class="rv">
        <div class="ey">RECURSO GRATUITO</div>
        <h2 class="h2" style="margin:12px 0 0">5 Casos de Uso de AI<br>Listos para Tu Industria</h2>
        <ul class="lchk">
          <li class="lci"><span class="lck">✓</span>Plantillas de casos de uso por vertical</li>
          <li class="lci"><span class="lck">✓</span>ROI benchmark de proyectos reales</li>
          <li class="lci"><span class="lck">✓</span>Checklist de madurez de datos</li>
          <li class="lci"><span class="lck">✓</span>Guía de evaluación de proveedores AI</li>
          <li class="lci"><span class="lck">✓</span>Framework de priorización de modelos</li>
        </ul>
        <div class="lsp">↳ Descargado por +200 equipos de data en LatAm</div>
      </div>
      <div class="rv">
        <div class="lf">
          <div class="ff">
            <label class="fll">Nombre</label>
            <input class="fi" type="text" placeholder="Tu nombre">
          </div>
          <div class="ff">
            <label class="fll">Email corporativo</label>
            <input class="fi" type="email" placeholder="tu@empresa.com">
          </div>
          <div class="ff">
            <label class="fll">Industria</label>
            <select class="fsel">
              <option value="">Selecciona tu industria</option>
              <option>Banca / Finanzas</option>
              <option>Telecom</option>
              <option>Retail / CPG</option>
              <option>Salud</option>
              <option>Otro</option>
            </select>
          </div>
          <button class="btn bm bfw">Descargar guía gratuita →</button>
          <div class="fd">Sin spam. Solo contenido útil para equipos de AI. Puedes darte de baja cuando quieras.</div>
        </div>
      </div>
    </div>
  </div>
</section>
<!-- FAQ -->
<section id="faq">
  <div class="c">
    <div class="sh rv">
      <h2 class="h2">Preguntas que hacen los CDOs<br>antes de agendar</h2>
    </div>
    <div>
      <div class="fqi">
        <div class="fqq"><span class="fqqt">"No tenemos suficientes datos de calidad."</span><span class="fqic">+</span></div>
        <div class="fqa"><p class="fqat">Nadie los tiene. Ese es exactamente el problema que resolvemos. Generamos datos sintéticos específicos a tu dominio para compensar los gaps. El primer paso es diagnosticar qué tienes y qué necesitas.</p></div>
      </div>
      <div class="fqi">
        <div class="fqq"><span class="fqqt">"Ya tenemos un equipo de data science interno."</span><span class="fqic">+</span></div>
        <div class="fqa"><p class="fqat">Perfecto. DataMate acelera su ejecución, no la reemplaza. Aportamos la capa de datos sintéticos y validación humana que típicamente cuesta 6+ meses construir. Tus ingenieros hacen más, más rápido.</p></div>
      </div>
      <div class="fqi">
        <div class="fqq"><span class="fqqt">"¿Por qué DataRobot y no otro AutoML?"</span><span class="fqic">+</span></div>
        <div class="fqa"><p class="fqat">DataRobot es la plataforma con mejor track record en producción enterprise: 66% menos tiempo de delivery, 20x más casos de uso desplegados. Como partner oficial para LatAm, ofrecemos implementación local con soporte en español y comprensión del contexto regulatorio regional.</p></div>
      </div>
      <div class="fqi">
        <div class="fqq"><span class="fqqt">"¿Cuánto tiempo tarda en verse ROI?"</span><span class="fqic">+</span></div>
        <div class="fqa"><p class="fqat">El primer modelo puede estar en producción en 8 semanas. El ROI depende del caso de uso — morosidad, churn y forecasting típicamente generan retorno en el primer trimestre.</p></div>
      </div>
      <div class="fqi">
        <div class="fqq"><span class="fqqt">"¿Qué pasa con mis datos regulados?"</span><span class="fqic">+</span></div>
        <div class="fqa"><p class="fqat">Los datos sintéticos son privacy-safe por diseño — no son datos reales, son datos estadísticamente equivalentes. Cumplimos con marcos de privacidad locales e internacionales. El diagnóstico gratuito incluye un mapeo de compliance.</p></div>
      </div>
    </div>
  </div>
</section>
<!-- FINAL CTA -->
<section id="fcta">
  <canvas id="cc"></canvas>
  <div class="c" style="width:100%;padding:96px 24px">
    <div class="fcc">
      <div class="ey" style="margin-bottom:16px">EMPIEZA HOY</div>
      <h2 class="fch">¿Cuándo fue la última vez que un modelo de AI llegó a producción en tu empresa?</h2>
      <p class="fcs">Si la respuesta te incomoda, la llamada de diagnóstico es para ti.</p>
      <div class="fcf">
        <div class="fcfg">
          <div class="ff"><label class="fll">Nombre</label><input class="fi" type="text" placeholder="Tu nombre"></div>
          <div class="ff"><label class="fll">Email corporativo</label><input class="fi" type="email" placeholder="tu@empresa.com"></div>
          <div class="ff"><label class="fll">Empresa</label><input class="fi" type="text" placeholder="Nombre de tu empresa"></div>
          <div class="ff"><label class="fll">País</label><input class="fi" type="text" placeholder="México, Colombia, Chile…"></div>
        </div>
        <div class="ff">
          <label class="fll">¿Cuál es tu mayor desafío con AI ahora mismo?</label>
          <textarea class="fta" placeholder="Cuéntanos brevemente tu situación actual..."></textarea>
        </div>
        <button class="btn bm bfw" style="font-size:16px;padding:16px">Agendar diagnóstico gratuito →</button>
      </div>
      <div class="cts">
        <span class="ct">🔒 Sin spam</span>
        <span class="ct">⏱ Llamada 30 min</span>
        <span class="ct">📅 Confirmación en 24h</span>
        <span class="ct">💬 En español</span>
      </div>
      <div class="alt">¿Prefieres empezar con contenido? <a onclick="document.getElementById('lm').scrollIntoView({behavior:'smooth'})">Descarga la guía gratuita</a></div>
    </div>
  </div>
</section>
<!-- FOOTER -->
<footer id="footer">
  <div class="c">
    <div class="fg">
      <div>
        <a href="#" class="logo" style="margin-bottom:4px;display:inline-flex">
          <svg width="28" height="28" viewBox="0 0 36 36" fill="none">
            <circle cx="18" cy="18" r="16" stroke="#00FFB3" stroke-width="1.5"/>
            <circle cx="18" cy="18" r="3" fill="#00FFB3"/>
          </svg>
          <span class="lw" style="font-size:12px;margin-left:8px">D A T A M A T E</span>
        </a>
        <p class="fgt">Cerrando la brecha de AI en Latinoamérica.<br>Datos sintéticos + Expertos humanos + AutoML.</p>
        <div style="display:inline-flex;align-items:center;gap:8px;padding:5px 12px;background:rgba(0,255,179,.07);border:1px solid rgba(0,255,179,.3);border-radius:100px;font-family:var(--fm);font-size:9px;color:var(--m);letter-spacing:.12em">🤝 DataRobot Official Partner LatAm</div>
      </div>
      <div>
        <div class="fct">Solución</div>
        <ul class="fl2">
          <li><a href="#how-it-works">Cómo funciona</a></li>
          <li><a href="#use-cases">Casos de uso</a></li>
          <li><a href="#how-it-works">Metodología</a></li>
          <li><a href="#stats">DataRobot</a></li>
        </ul>
      </div>
      <div>
        <div class="fct">Empresa</div>
        <ul class="fl2">
          <li><a href="#">Sobre nosotros</a></li>
          <li><a href="#">Partners</a></li>
          <li><a href="#">Blog AI</a></li>
          <li><a href="#">Podcast</a></li>
        </ul>
      </div>
      <div>
        <div class="fct">Contacto</div>
        <ul class="fl2">
          <li><a href="mailto:hola@datamate.ai">hola@datamate.ai</a></li>
          <li><a href="#">LinkedIn</a></li>
          <li><a href="#fcta" class="btn bm" style="padding:10px 18px;font-size:13px;margin-top:8px;display:inline-flex">Agendar llamada →</a></li>
        </ul>
      </div>
    </div>
    <div class="fbot">
      <span class="fleg">© 2025 DataMate · DataRobot Official Partner Latin America</span>
      <div class="fll">
        <a href="#">Privacidad</a>
        <a href="#">Términos</a>
        <a href="#">Cookies</a>
      </div>
    </div>
  </div>
</footer>
<!-- Mobile Sticky Bar -->
<div class="msb">
  <a href="#fcta" class="btn bm" style="width:100%;justify-content:center;font-size:14px;padding:14px">Agendar diagnóstico gratuito →</a>
</div>
<script>
// ── NAVBAR ──────────────────────────────────────────────
const nav = document.getElementById('nav');
window.addEventListener('scroll', () => {
  nav.classList.toggle('s', scrollY > 60);
});
setTimeout(() => document.getElementById('ncp').classList.add('pulse'), 8000);
document.getElementById('hb').addEventListener('click', () => document.getElementById('mm').classList.add('op'));
document.getElementById('mmc').addEventListener('click', () => document.getElementById('mm').classList.remove('op'));

// ── SPLINE replaces THREE.JS hero background ─────────────
// (spline-viewer web component handles its own rendering)

// ── PARTICLE CANVAS (FINAL CTA) ──────────────────────────
(function() {
  const cv = document.getElementById('cc');
  const ctx = cv.getContext('2d');
  function resize() { cv.width = cv.offsetWidth; cv.height = cv.offsetHeight; }
  resize();
  window.addEventListener('resize', resize);
  const pts = Array.from({ length: 70 }, () => ({
    x: Math.random() * cv.width, y: Math.random() * cv.height,
    vx: (Math.random() - .5) * .35, vy: (Math.random() - .5) * .35,
    r: Math.random() * 1.8 + 0.8
  }));
  (function draw() {
    requestAnimationFrame(draw);
    ctx.clearRect(0, 0, cv.width, cv.height);
    pts.forEach(p => {
      p.x += p.vx; p.y += p.vy;
      if (p.x < 0 || p.x > cv.width) p.vx *= -1;
      if (p.y < 0 || p.y > cv.height) p.vy *= -1;
      ctx.beginPath(); ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fillStyle = 'rgba(116,106,252,0.55)'; ctx.fill();
    });
    for (let i = 0; i < pts.length; i++)
      for (let j = i + 1; j < pts.length; j++) {
        const d = Math.hypot(pts[i].x - pts[j].x, pts[i].y - pts[j].y);
        if (d < 110) {
          ctx.beginPath(); ctx.moveTo(pts[i].x, pts[i].y); ctx.lineTo(pts[j].x, pts[j].y);
          ctx.strokeStyle = `rgba(116,106,252,${(1 - d / 110) * 0.13})`; ctx.lineWidth = 1; ctx.stroke();
        }
      }
  })();
})();

// ── STATS PARTICLE BG ────────────────────────────────────
(function() {
  const cv = document.getElementById('sc');
  const ctx = cv.getContext('2d');
  function resize() { cv.width = cv.offsetWidth; cv.height = cv.offsetHeight; }
  resize(); window.addEventListener('resize', resize);
  const pts = Array.from({ length: 40 }, () => ({
    x: Math.random() * cv.width, y: Math.random() * cv.height,
    vx: (Math.random() - .5) * .2, vy: (Math.random() - .5) * .2, r: 1.2
  }));
  (function draw() {
    requestAnimationFrame(draw);
    ctx.clearRect(0, 0, cv.width, cv.height);
    pts.forEach(p => {
      p.x += p.vx; p.y += p.vy;
      if (p.x < 0 || p.x > cv.width) p.vx *= -1;
      if (p.y < 0 || p.y > cv.height) p.vy *= -1;
      ctx.beginPath(); ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fillStyle = 'rgba(0,255,179,0.5)'; ctx.fill();
    });
  })();
})();

// ── GSAP HERO TIMELINE ───────────────────────────────────
gsap.registerPlugin(ScrollTrigger);
const tl = gsap.timeline({ delay: 0.1 });
tl.to('#tb',  { opacity: 1, y: 0, duration: .5 })
  .to('#ey',  { opacity: 1, duration: .4 }, '-=.2')
  .to('#hl1', { y: '0%', duration: .65, ease: 'power3.out' }, '-=.2')
  .to('#hl2', { y: '0%', duration: .65, ease: 'power3.out' }, '-=.45')
  .to('#hl3', { y: '0%', duration: .65, ease: 'power3.out' }, '-=.45')
  .to('#hs',  { opacity: 1, duration: .5 }, '-=.2')
  .to('#hca', { opacity: 1, duration: .5 }, '-=.2')
  .to('#rc',  { opacity: 1, x: 0, duration: .7, ease: 'power3.out' }, '-=.4')
  .call(() => { document.querySelectorAll('.rbf').forEach(b => { b.style.width = b.dataset.w + '%'; }); });

// ── SCROLL REVEAL (IntersectionObserver) ────────────────
const io = new IntersectionObserver((entries) => {
  entries.forEach((e, i) => { if (e.isIntersecting) { setTimeout(() => e.target.classList.add('vis'), i * 60); io.unobserve(e.target); } });
}, { threshold: 0.12 });
document.querySelectorAll('.rv').forEach(el => io.observe(el));

// ── STATS COUNTER ────────────────────────────────────────
function countUp(id, end, suffix) {
  const el = document.getElementById(id);
  let n = 0; const step = end / 55;
  const iv = setInterval(() => {
    n = Math.min(n + step, end);
    el.textContent = Math.floor(n) + suffix;
    if (n >= end) clearInterval(iv);
  }, 28);
}
ScrollTrigger.create({
  trigger: '#stats', start: 'top 70%',
  onEnter: () => { countUp('s1', 66, '%'); countUp('s2', 20, 'x'); countUp('s3', 25, '%'); countUp('s4', 8, ''); }
});

// ── TIMELINE ANIMATION ───────────────────────────────────
ScrollTrigger.create({
  trigger: '#how-it-works', start: 'top 65%',
  onEnter: () => {
    document.getElementById('tllf').style.width = '80%';
    document.querySelectorAll('.ts').forEach((el, i) => {
      setTimeout(() => { el.style.opacity = 1; el.style.transform = 'translateY(0)'; el.style.transition = '.5s ease'; el.classList.add('act'); }, i * 200);
    });
  }
});

// ── TAB SWITCHER ─────────────────────────────────────────
document.querySelectorAll('.tbt').forEach(btn => {
  btn.addEventListener('click', () => {
    document.querySelectorAll('.tbt').forEach(b => b.classList.remove('a'));
    document.querySelectorAll('.tc').forEach(t => t.classList.remove('a'));
    btn.classList.add('a');
    document.getElementById('tab-' + btn.dataset.tab).classList.add('a');
  });
});

// ── FAQ ACCORDION ────────────────────────────────────────
document.querySelectorAll('.fqq').forEach(q => {
  q.addEventListener('click', () => {
    const item = q.parentElement;
    const wasOpen = item.classList.contains('op');
    document.querySelectorAll('.fqi').forEach(i => i.classList.remove('op'));
    if (!wasOpen) item.classList.add('op');
  });
});
</script>
</body>
</html>
