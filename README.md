[index.html](https://github.com/user-attachments/files/25620326/index.html)
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Deutsch Tippen — German Typing Practice</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --black:#0a0a0a;--white:#f5f0e8;
  --gold:#c8952a;--gold-l:#e8b84b;
  --green-l:#52b788;--red-l:#e63946;
  --blue:#1d3a6e;--blue-l:#4a7fc1;--blue-dim:#0e1520;
  --grey:#8a8070;--grey-l:#ccc5b5;
  --card:#1a1a1a;
  --verb:#2d6a3f;--verb-l:#6fcf97;
  --noun:#1a3a6e;--noun-l:#74b3f0;
  --adj:#6a3a0a;--adj-l:#f0b45a;
  /* theme tokens */
  --bg:var(--black);--surface:var(--card);--text:var(--white);
  --border:#1e1e1e;--subtext:#8a8070;--input-bg:#0d0d0d;
}
/* ── LIGHT MODE ── */
body.light{
  --bg:#f0ede6;--surface:#ffffff;--text:#1a1612;
  --border:#ddd8ce;--subtext:#7a7060;--input-bg:#faf8f4;
  --black:#f0ede6;--white:#1a1612;--card:#ffffff;
  --grey:#7a7060;--grey-l:#555045;
  --gold:#a06a0a;--gold-l:#b87a18;
  --blue:#1d3a6e;--blue-l:#2a5a9e;
  --verb-l:#1a7a3f;--noun-l:#1a4a9e;--adj-l:#8a5a0a;
}
body.light header{background:rgba(240,237,230,.98);border-color:#ddd8ce}
body.light .panel{box-shadow:0 2px 12px rgba(0,0,0,.08)}
body.light .panel-header{background:#f5f2ec;border-color:#e8e4dc}
body.light .gt-topbar{background:#eeeae2;border-color:#ddd8ce}
body.light .gt-out-col{background:#e8e4dc}
body.light .gt-mid{background:#e8e4dc;border-color:#ddd8ce}
body.light .gt-ta{color:#1a1612}
body.light .gt-ta::placeholder{color:#b0a898}
body.light .gt-output{color:#2a2218}
body.light .ptext{background:#faf8f4;border-color:#e0dcd2;color:#2a2218}
body.light .tarea{background:#faf8f4;border-color:#d0ccc2;color:#1a1612}
body.light .tarea::placeholder{color:#b0a898}
body.light .cmp{background:#f5f2ec;border-color:#e0dcd2}
body.light .topic-sel{background:#faf8f4;border-color:#d0ccc2;color:#1a1612}
body.light .gt-sel{background:#e8e4dc;border-color:#ccc8be;color:#2a2218}
body.light .legend{background:#f5f2ec;border-color:#e0dcd2}
body.light .copy-bar{background:#eef4ee;border-color:#c0d8c0}
body.light .refresh-bar{background:#f5f2ec;border-color:#e0dcd2}
body.light .refresh-hint{color:#b0a898}
body.light .csep{background:#e0dcd2}
body.light .gt-mini{border-color:#ccc8be;color:#6a6050}
body.light .gt-mini:hover{color:#2a4060}
body.light .tt{background:#fffdf8;border-color:#c8b898;box-shadow:0 8px 24px rgba(0,0,0,.15)}
body.light .tt-sep{background:#e8e0d0}
body.light .tt-en{color:#2a2218}
body.light .rcard{background:#fff;border-color:#d8c880}
body.light .rstat{background:#f5f2ec;border-color:#e0dcd2}
body.light .btn-sec{border-color:#c0bbb0;color:#4a4538}
body.light .prog-wrap{background:#e0dcd2}
body.light .lstats{color:#6a6050}
body.light .refresh-hint{color:#aaa89a}
body.light .empty-t{color:#888070}
body.light body::before{opacity:.08}
*{box-sizing:border-box;margin:0;padding:0}
body{background:var(--bg);color:var(--text);font-family:'DM Sans',sans-serif;min-height:100vh;overflow-x:hidden;transition:background .25s,color .25s}
body::before{content:'';position:fixed;inset:0;pointer-events:none;z-index:9999;opacity:.28;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.05'/%3E%3C/svg%3E")}
.spin{animation:spin 1s linear infinite;display:inline-block}
@keyframes spin{to{transform:rotate(360deg)}}

/* HEADER */
header{display:flex;align-items:center;justify-content:space-between;padding:1rem 2.5rem;border-bottom:1px solid #1c1c1c;background:rgba(6,6,6,.98);position:sticky;top:0;z-index:200;backdrop-filter:blur(14px)}
.logo-main{font-family:'DM Serif Display',serif;font-size:1.4rem;color:var(--gold-l);line-height:1}
.logo-sub{font-size:.64rem;color:var(--grey);letter-spacing:.15em;text-transform:uppercase;margin-top:1px}
.hstats{display:flex;gap:1.8rem}

/* TOOLBAR — theme switch + font size */
.toolbar{display:flex;align-items:center;gap:1rem;flex-wrap:wrap}
/* Dark/Light toggle switch */
.theme-toggle{display:flex;align-items:center;gap:.5rem;cursor:pointer;user-select:none}
.theme-toggle-lbl{font-size:.68rem;color:var(--subtext);letter-spacing:.08em;text-transform:uppercase;white-space:nowrap}
.toggle-track{
  width:42px;height:22px;border-radius:11px;
  background:#2a2a2a;border:1px solid #383838;
  position:relative;transition:background .25s,border-color .25s;cursor:pointer;flex-shrink:0;
}
body.light .toggle-track{background:#c8d8f0;border-color:#a0b8d8}
.toggle-thumb{
  position:absolute;top:2px;left:2px;
  width:16px;height:16px;border-radius:50%;
  background:#555;transition:transform .25s,background .25s;
}
body.light .toggle-thumb{background:#2a5a9e;transform:translateX(20px)}
/* Font size control */
.font-ctrl{display:flex;align-items:center;gap:.4rem}
.font-lbl{font-size:.68rem;color:var(--subtext);letter-spacing:.08em;text-transform:uppercase;white-space:nowrap}
.font-btn{
  width:26px;height:26px;border-radius:6px;border:1px solid #2a2a2a;
  background:transparent;color:var(--grey-l);font-size:1rem;line-height:1;
  cursor:pointer;display:flex;align-items:center;justify-content:center;
  transition:all .18s;font-family:'DM Sans',sans-serif;font-weight:600;
}
.font-btn:hover{border-color:var(--gold-l);color:var(--gold-l)}
.font-size-val{
  font-family:'DM Mono',monospace;font-size:.75rem;
  color:var(--gold-l);min-width:32px;text-align:center;
}
.hstat{text-align:center}
.hsv{font-family:'DM Mono',monospace;font-size:1.25rem;color:var(--gold-l);font-weight:500;line-height:1}
.hsl{font-size:.6rem;color:var(--grey);letter-spacing:.1em;text-transform:uppercase;margin-top:2px}

/* DRAG LAYOUT */
.page{max-width:1200px;margin:0 auto;padding:1.4rem 1.8rem 4rem}
.drag-area{display:flex;flex-direction:column;gap:1rem}

/* DRAGGABLE PANEL */
.panel{background:var(--card);border:1px solid #1e1e1e;border-radius:14px;overflow:hidden;transition:box-shadow .2s}
.panel.dragging{opacity:.55;box-shadow:0 12px 40px rgba(0,0,0,.7);cursor:grabbing}
.panel.drag-over{border-color:var(--gold);box-shadow:0 0 0 2px rgba(200,149,42,.25)}
.panel-header{
  display:flex;align-items:center;gap:.7rem;
  padding:.65rem 1.2rem;
  background:#131313;border-bottom:1px solid #1a1a1a;
  cursor:grab;user-select:none;
}
.panel-header:active{cursor:grabbing}
.drag-handle{color:#333;font-size:1rem;line-height:1;letter-spacing:1px;flex-shrink:0}
.drag-handle::before{content:'⠿'}
.panel-title{font-size:.69rem;color:var(--grey);letter-spacing:.13em;text-transform:uppercase;font-weight:500}
.panel-body{padding:1rem 1.3rem;display:flex;flex-direction:column;gap:.85rem}

/* CONTROLS inside panel */
.crow{display:flex;gap:.75rem;align-items:center;flex-wrap:wrap}
.csep{height:1px;background:#181818}
.clbl{font-size:.65rem;color:var(--grey);letter-spacing:.12em;text-transform:uppercase;white-space:nowrap}
.lvl-btns{display:flex;gap:.28rem}
.lvl-btn{padding:.32rem .85rem;border:1px solid #252525;background:transparent;color:var(--grey-l);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.81rem;cursor:pointer;transition:all .2s;font-weight:500}
.lvl-btn:hover{border-color:var(--gold);color:var(--gold-l)}
.lvl-btn.on{background:var(--gold);border-color:var(--gold);color:#000;font-weight:600}
.ctx-btns{display:flex;gap:.26rem;flex-wrap:wrap}
.ctx-btn{padding:.3rem .78rem;border:1px solid #1e2038;background:transparent;color:#5566aa;border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.79rem;cursor:pointer;transition:all .2s;display:flex;align-items:center;gap:.26rem}
.ctx-btn:hover{border-color:var(--blue-l);color:#99bbee}
.ctx-btn.on{background:var(--blue);border-color:var(--blue-l);color:#c8deff;font-weight:500}
.topic-sel{padding:.35rem .82rem;background:#111;border:1px solid #252525;color:var(--white);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.81rem;cursor:pointer;outline:none;flex:1;min-width:165px;max-width:225px}
.topic-sel:focus{border-color:var(--gold)}
.gen-btn{display:flex;align-items:center;gap:.38rem;padding:.42rem 1.25rem;background:var(--gold);color:#000;border:none;border-radius:8px;font-family:'DM Sans',sans-serif;font-size:.85rem;font-weight:600;cursor:pointer;transition:all .2s;margin-left:auto}
.gen-btn:hover{background:var(--gold-l);transform:translateY(-1px)}
.gen-btn:disabled{opacity:.5;cursor:not-allowed;transform:none}

/* TRANSLATE PANEL */
.gt-topbar{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:.6rem;padding:.6rem 1.2rem;background:#0d1018;border-bottom:1px solid #1a2030}
.gt-lbl{font-size:.67rem;color:var(--blue-l);letter-spacing:.12em;text-transform:uppercase;font-weight:500}
.gt-ctrls{display:flex;align-items:center;gap:.65rem;flex-wrap:wrap}
.gt-sel{padding:.28rem .65rem;background:#141820;border:1px solid #1e2a40;color:#99aac8;border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.79rem;cursor:pointer;outline:none}
.gt-sel:focus{border-color:var(--blue-l)}
.gt-arrow{color:#2a4060;font-weight:bold}
.spd-row{display:flex;gap:.22rem;align-items:center}
.spd-lbl{font-size:.63rem;color:#2a4060;text-transform:uppercase;letter-spacing:.08em}
.spd-btn{padding:.18rem .46rem;border:1px solid #1a2a40;background:transparent;color:#3a5070;border-radius:4px;font-size:.68rem;cursor:pointer;font-family:'DM Mono',monospace;transition:all .2s}
.spd-btn.on{background:var(--blue);color:#c8deff;border-color:var(--blue-l)}

.gt-body{display:grid;grid-template-columns:1fr 48px 1fr;min-height:150px}
.gt-col{display:flex;flex-direction:column;padding:.85rem 1rem;gap:.65rem}
.gt-col-lbl{font-size:.61rem;text-transform:uppercase;letter-spacing:.1em}
.gt-ta{flex:1;width:100%;background:transparent;border:none;color:#c8deff;font-family:'DM Sans',sans-serif;font-size:.94rem;line-height:1.7;resize:none;outline:none;min-height:80px}
.gt-ta::placeholder{color:#1a2535}
.gt-out-col{background:#0a0d14}
.gt-output{flex:1;font-family:'DM Sans',sans-serif;font-size:.94rem;line-height:1.7;color:#b8c8e0;min-height:80px;white-space:pre-wrap;word-break:break-word}
.gt-btns{display:flex;gap:.4rem;align-items:center;flex-wrap:wrap}

/* PLAY/PAUSE button */
.play-btn{
  display:flex;align-items:center;gap:.3rem;
  padding:.33rem .82rem;background:var(--blue);border:1px solid var(--blue-l);
  color:#c8deff;border-radius:7px;font-family:'DM Sans',sans-serif;font-size:.79rem;
  font-weight:500;cursor:pointer;transition:all .2s;white-space:nowrap;min-width:110px;
}
.play-btn:hover{background:#254888}
.play-btn.playing{background:#1a3870;border-color:#6aafff;animation:glow 1.4s ease infinite}
@keyframes glow{0%,100%{box-shadow:0 0 0 0 rgba(74,127,193,.4)}50%{box-shadow:0 0 0 5px rgba(74,127,193,0)}}

.gt-mid{display:flex;align-items:center;justify-content:center;background:#0a0d14;border-left:1px solid #1a2030;border-right:1px solid #1a2030}
.tr-btn{display:flex;align-items:center;justify-content:center;width:36px;height:36px;background:var(--blue);border:2px solid var(--blue-l);border-radius:50%;cursor:pointer;transition:all .2s;color:#c8deff;font-size:.95rem;box-shadow:0 4px 14px rgba(0,0,0,.5)}
.tr-btn:hover{background:#2a4a8a;transform:scale(1.08)}
.tr-btn:disabled{opacity:.4;cursor:not-allowed;transform:none}
.gt-mini{padding:.28rem .65rem;background:transparent;border:1px solid #1a2535;color:#2a3a55;border-radius:6px;font-size:.73rem;cursor:pointer;font-family:'DM Sans',sans-serif;transition:all .2s}
.gt-mini:hover{border-color:#2a4060;color:#4a6080}

/* PASSAGE PANEL */
.phead{display:flex;justify-content:space-between;align-items:flex-start;gap:.8rem;flex-wrap:wrap}
.ptitle{font-family:'DM Serif Display',serif;font-size:1.08rem;color:var(--gold-l)}
.pmeta-row{display:flex;gap:.35rem;align-items:center;flex-wrap:wrap}
.badge{padding:.14rem .48rem;border-radius:4px;font-size:.65rem;font-weight:600;letter-spacing:.07em;text-transform:uppercase}
.b-lvl{background:#28260e;color:var(--gold);border:1px solid #383615}
.b-ctx{background:#0a1020;color:var(--blue-l);border:1px solid #182040}
.b-wrd{background:#0a180a;color:var(--green-l);border:1px solid #182818}

/* COPY BAR */
.copy-bar{
  display:none;align-items:center;gap:.7rem;
  padding:.5rem .85rem;background:#0d0f0d;border:1px solid #1a2a1a;border-radius:8px;
}
.copy-bar.vis{display:flex}
.copy-btn{
  display:flex;align-items:center;gap:.35rem;
  padding:.32rem .85rem;background:transparent;border:1px solid #1a3a1a;
  color:var(--green-l);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.79rem;cursor:pointer;transition:all .2s;
}
.copy-btn:hover{background:rgba(82,183,136,.08);border-color:var(--green-l)}
.copy-btn.copied{background:rgba(82,183,136,.12);border-color:var(--green-l);color:#fff}
.copy-hint{font-size:.72rem;color:#1a3a1a}
.paste-to-tr-btn{
  display:flex;align-items:center;gap:.32rem;
  padding:.32rem .85rem;background:transparent;border:1px solid #1a2a40;
  color:var(--blue-l);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.79rem;cursor:pointer;transition:all .2s;
}
.paste-to-tr-btn:hover{background:rgba(74,127,193,.08);border-color:var(--blue-l)}

/* PASSAGE TEXT — hover tooltips on every word */
.ptext{
  font-size:1rem;line-height:2;color:#d8d2c5;font-family:'DM Sans',sans-serif;font-weight:300;
  padding:.88rem 1rem;background:#0d0d0d;border-radius:8px;border:1px solid #181818;
  min-height:70px;user-select:text;
}
/* word types */
.w-verb{color:var(--verb-l);font-weight:500;cursor:pointer;border-bottom:1.5px dashed rgba(111,207,151,.45);transition:all .15s}
.w-verb:hover{background:rgba(45,106,63,.15);border-radius:3px}
.w-noun{color:var(--noun-l);font-weight:500;cursor:pointer;border-bottom:1.5px dashed rgba(116,179,240,.4);transition:all .15s}
.w-noun:hover{background:rgba(26,58,110,.18);border-radius:3px}
.w-adj{color:var(--adj-l);font-weight:500;cursor:pointer;border-bottom:1.5px dashed rgba(240,180,90,.4);transition:all .15s}
.w-adj:hover{background:rgba(106,58,10,.15);border-radius:3px}
.w-key{color:var(--gold-l);font-weight:600;cursor:pointer;border-bottom:1.5px dashed rgba(200,149,42,.5);transition:all .15s}
.w-key:hover{background:rgba(200,149,42,.09);border-radius:3px}

/* SELECTION COPY POPUP */
.sel-popup{
  position:fixed;z-index:2000;
  background:#1a1a1a;border:1px solid var(--gold);border-radius:8px;
  padding:.38rem .75rem;display:none;align-items:center;gap:.5rem;
  box-shadow:0 6px 20px rgba(0,0,0,.7);animation:fadeUp .15s ease;
}
body.light .sel-popup{background:#fff;border-color:var(--gold-l)}
@keyframes fadeUp{from{opacity:0;transform:translateY(4px)}to{opacity:1;transform:translateY(0)}}
.sel-popup.vis{display:flex}
.sel-copy-btn{
  display:flex;align-items:center;gap:.3rem;
  padding:.22rem .65rem;background:var(--gold);color:#000;
  border:none;border-radius:5px;font-family:'DM Sans',sans-serif;
  font-size:.75rem;font-weight:600;cursor:pointer;transition:all .15s;white-space:nowrap;
}
.sel-copy-btn:hover{background:var(--gold-l)}
.sel-speak-btn{
  display:flex;align-items:center;gap:.28rem;
  padding:.22rem .6rem;background:transparent;border:1px solid var(--blue-l);
  color:var(--blue-l);border-radius:5px;font-family:'DM Sans',sans-serif;
  font-size:.75rem;cursor:pointer;transition:all .15s;white-space:nowrap;
}
.sel-speak-btn:hover{background:rgba(74,127,193,.1)}
.sel-text-preview{font-size:.72rem;color:var(--subtext);max-width:180px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}

/* RICH TOOLTIP */
.tt{
  position:fixed;background:#0f0c08;border:1px solid #2a2420;border-radius:10px;
  padding:.7rem .95rem;max-width:230px;min-width:160px;
  pointer-events:none;z-index:1000;opacity:0;transition:opacity .12s;
  box-shadow:0 10px 30px rgba(0,0,0,.85);
}
.tt.vis{opacity:1}
.tt-word{font-family:'DM Serif Display',serif;font-size:1.05rem;line-height:1.2}
.tt-type{font-size:.62rem;text-transform:uppercase;letter-spacing:.1em;margin-top:2px;opacity:.7}
.tt-sep{height:1px;background:#1e1e1e;margin:.45rem 0}
.tt-en{font-size:.82rem;color:#ccc;font-weight:300}
.tt-hi{font-size:.78rem;color:#9a8ad8;margin-top:3px}
.tt-ex{font-size:.73rem;color:var(--grey);margin-top:.35rem;font-style:italic;line-height:1.45}
/* type colours in tooltip */
.tt-verb .tt-word{color:var(--verb-l)} .tt-verb .tt-type{color:var(--verb-l)}
.tt-noun .tt-word{color:var(--noun-l)} .tt-noun .tt-type{color:var(--noun-l)}
.tt-adj  .tt-word{color:var(--adj-l)}  .tt-adj  .tt-type{color:var(--adj-l)}
.tt-key  .tt-word{color:var(--gold-l)} .tt-key  .tt-type{color:var(--gold-l)}
/* colour legend */
.legend{display:flex;gap:.9rem;flex-wrap:wrap;padding:.45rem .85rem;background:#0d0d0d;border:1px solid #181818;border-radius:7px}
.leg-item{display:flex;align-items:center;gap:.3rem;font-size:.7rem}
.leg-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}

/* REFRESH BAR */
.refresh-bar{display:none;align-items:center;justify-content:center;gap:.85rem;padding:.6rem .85rem;background:#0d0d0d;border:1px solid #1a1a1a;border-radius:9px}
.refresh-bar.vis{display:flex}
.refresh-btn{display:flex;align-items:center;gap:.45rem;padding:.38rem 1.05rem;background:transparent;border:1.5px solid #262626;color:var(--grey-l);border-radius:8px;font-family:'DM Sans',sans-serif;font-size:.81rem;cursor:pointer;transition:all .25s}
.refresh-btn:hover{border-color:var(--gold-l);color:var(--gold-l);background:rgba(200,149,42,.04)}
.ricon{display:inline-block;transition:transform .4s}
.refresh-btn:hover .ricon{transform:rotate(180deg)}
.refresh-hint{font-size:.72rem;color:#252525}

/* TYPING */
.prog-wrap{height:3px;background:#161616;border-radius:2px;overflow:hidden}
.prog-bar{height:100%;background:linear-gradient(90deg,var(--gold),var(--gold-l));border-radius:2px;transition:width .3s ease;width:0%}
.tlabel{font-size:.65rem;color:var(--grey);letter-spacing:.12em;text-transform:uppercase;display:flex;align-items:center;gap:.42rem}
.tlabel::after{content:'';flex:1;height:1px;background:#181818}
.tarea{width:100%;min-height:112px;background:#090909;border:1.5px solid #222;border-radius:8px;padding:.82rem 1rem;color:var(--white);font-family:'DM Mono',monospace;font-size:.91rem;line-height:1.8;resize:none;outline:none;transition:border-color .2s}
.tarea:focus{border-color:var(--gold)}
.tarea::placeholder{color:#242424}
.tarea:disabled{opacity:.26;cursor:not-allowed}
.cmp{font-family:'DM Mono',monospace;font-size:.85rem;line-height:1.9;padding:.62rem 1rem;background:#070707;border-radius:8px;border:1px solid #131313;word-break:break-all;display:none}
.cmp.vis{display:block}
.cc{color:var(--green-l)} .cw{color:var(--red-l);background:rgba(230,57,70,.1);border-radius:2px} .cp{color:#2d2d2d}
.cur{border-left:2px solid var(--gold-l);animation:blink 1s step-end infinite}
@keyframes blink{50%{border-color:transparent}}
.arow{display:flex;gap:.55rem;align-items:center}
.btn-sec{padding:.34rem .8rem;background:transparent;border:1px solid #222;color:var(--grey-l);border-radius:6px;font-family:'DM Sans',sans-serif;font-size:.79rem;cursor:pointer;transition:all .2s}
.btn-sec:hover{border-color:var(--gold);color:var(--gold-l)}
.lstats{margin-left:auto;font-family:'DM Mono',monospace;font-size:.79rem;color:var(--grey);display:flex;gap:.85rem}
.ag{color:var(--green-l)} .ab{color:var(--red-l)}

/* EMPTY / LOADING */
.empty{text-align:center;padding:2.2rem 1rem;color:var(--grey)}
.empty-i{font-size:2.5rem;margin-bottom:.65rem;opacity:.35}
.empty-t{font-family:'DM Serif Display',serif;font-size:1.12rem;color:#383838;margin-bottom:.32rem}
.empty-s{font-size:.8rem;line-height:1.65}
.lstate{text-align:center;padding:1.6rem 1rem;display:none}
.lstate.vis{display:block}
.ldots{display:flex;justify-content:center;gap:.28rem;margin-bottom:.65rem}
.dot{width:7px;height:7px;background:var(--gold);border-radius:50%;animation:bnc 1.2s ease-in-out infinite}
.dot:nth-child(2){animation-delay:.2s} .dot:nth-child(3){animation-delay:.4s}
@keyframes bnc{0%,80%,100%{transform:scale(.55);opacity:.4}40%{transform:scale(1);opacity:1}}
.ltxt{color:var(--grey);font-size:.8rem}

/* RESULTS */
.roverlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.9);backdrop-filter:blur(8px);z-index:300;align-items:center;justify-content:center}
.roverlay.vis{display:flex}
.rcard{background:var(--card);border:1px solid #383820;border-radius:16px;padding:1.9rem;width:415px;text-align:center;animation:popIn .3s cubic-bezier(.34,1.56,.64,1)}
@keyframes popIn{from{transform:scale(.8);opacity:0}to{transform:scale(1);opacity:1}}
.re{font-size:2.5rem;margin-bottom:.55rem}
.rt{font-family:'DM Serif Display',serif;font-size:1.55rem;color:var(--gold-l);margin-bottom:.18rem}
.rs{color:var(--grey);font-size:.85rem;margin-bottom:1.3rem}
.rstats{display:grid;grid-template-columns:repeat(3,1fr);gap:.65rem;margin-bottom:1.4rem}
.rstat{background:#0d0d0d;border:1px solid #1a1a1a;border-radius:9px;padding:.75rem}
.rsv{font-family:'DM Mono',monospace;font-size:1.35rem;color:var(--gold-l);font-weight:500}
.rsl{font-size:.59rem;color:var(--grey);letter-spacing:.1em;text-transform:uppercase;margin-top:3px}
.rbtns{display:flex;gap:.55rem;justify-content:center}
.btn-pri{padding:.48rem 1.25rem;background:var(--gold);color:#000;border:none;border-radius:8px;font-family:'DM Sans',sans-serif;font-size:.85rem;font-weight:600;cursor:pointer;transition:all .2s}
.btn-pri:hover{background:var(--gold-l)}

/* DRAG ghost */
.drag-ghost{opacity:.35;pointer-events:none}

@media(max-width:800px){
  .gt-body{grid-template-columns:1fr}
  .gt-mid{height:44px;border-left:none;border-right:none;border-top:1px solid #1a2030;border-bottom:1px solid #1a2030}
  .ctx-btn .clbl{display:none}
  header{padding:.9rem 1.1rem} .hstats{gap:1.1rem}
  .page{padding:1rem 1rem 3rem}
}
</style>
</head>
<body>

<header>
  <div>
    <div class="logo-main">Deutsch Tippen</div>
    <div class="logo-sub">German Typing Practice</div>
  </div>
  <div class="toolbar">
    <!-- FONT SIZE -->
    <div class="font-ctrl">
      <span class="font-lbl">A</span>
      <button class="font-btn" onclick="changeFont(-1)" title="Decrease font size">−</button>
      <span class="font-size-val" id="fontVal">16px</span>
      <button class="font-btn" onclick="changeFont(1)" title="Increase font size">+</button>
    </div>
    <!-- DARK / LIGHT SWITCH -->
    <label class="theme-toggle" onclick="toggleTheme()" title="Toggle dark / light mode">
      <span class="theme-toggle-lbl" id="themeLbl">🌙 Dark</span>
      <div class="toggle-track"><div class="toggle-thumb"></div></div>
    </label>
  </div>
  <div class="hstats">
    <div class="hstat"><div class="hsv" id="hdr-wpm">—</div><div class="hsl">WPM</div></div>
    <div class="hstat"><div class="hsv" id="hdr-acc">—</div><div class="hsl">Accuracy</div></div>
    <div class="hstat"><div class="hsv" id="hdr-streak">0</div><div class="hsl">Streak</div></div>
  </div>
</header>

<div class="page">
  <!-- DRAGGABLE AREA — panels can be reordered by dragging their header -->
  <div class="drag-area" id="dragArea">

    <!-- ═══ PANEL 1: CONTROLS ═══ -->
    <div class="panel" id="panel-controls" draggable="true">
      <div class="panel-header" title="Drag to reorder">
        <span class="drag-handle"></span>
        <span class="panel-title">⚙️ Level, Topic &amp; Context</span>
      </div>
      <div class="panel-body">
        <div class="crow">
          <span class="clbl">Level</span>
          <div class="lvl-btns">
            <button class="lvl-btn on" data-lv="A1" onclick="setLevel(this)">A1</button>
            <button class="lvl-btn" data-lv="A2" onclick="setLevel(this)">A2</button>
            <button class="lvl-btn" data-lv="B1" onclick="setLevel(this)">B1</button>
          </div>
          <span class="clbl" style="margin-left:.3rem">Topic</span>
          <select class="topic-sel" id="topicSel">
            <option value="daily_life">🏠 Daily Life in Berlin</option>
            <option value="university">🎓 University &amp; Studies</option>
            <option value="food">🍕 Food &amp; Restaurants</option>
            <option value="transport">🚌 Transport &amp; Travel</option>
            <option value="shopping">🛒 Shopping</option>
            <option value="weather">🌤️ Weather &amp; Seasons</option>
            <option value="family">👨‍👩‍👧 Family &amp; Friends</option>
            <option value="work">💼 Work &amp; Career</option>
            <option value="health">🏥 Health &amp; Body</option>
            <option value="hobbies">🎵 Hobbies &amp; Free Time</option>
          </select>
          <button class="gen-btn" id="genBtn" onclick="generate()">
            <span id="genIco">✦</span> Generate Passage
          </button>
        </div>
        <div class="csep"></div>
        <div class="crow">
          <span class="clbl">Context</span>
          <div class="ctx-btns">
            <button class="ctx-btn on" data-ctx="friend" onclick="setCtx(this)">👋 <span class="clbl">With a Friend</span></button>
            <button class="ctx-btn" data-ctx="university" onclick="setCtx(this)">🎓 <span class="clbl">University</span></button>
            <button class="ctx-btn" data-ctx="family" onclick="setCtx(this)">🏠 <span class="clbl">With Family</span></button>
            <button class="ctx-btn" data-ctx="professional" onclick="setCtx(this)">💼 <span class="clbl">Professional</span></button>
            <button class="ctx-btn" data-ctx="government" onclick="setCtx(this)">🏛️ <span class="clbl">Government</span></button>
          </div>
        </div>
      </div>
    </div>

    <!-- ═══ PANEL 2: TRANSLATE & LISTEN ═══ -->
    <div class="panel" id="panel-translate" draggable="true">
      <div class="panel-header" title="Drag to reorder">
        <span class="drag-handle"></span>
        <span class="panel-title">🌐 Translate &amp; Listen</span>
      </div>
      <!-- topbar -->
      <div class="gt-topbar">
        <div class="gt-lbl">Paste German text → translate → hear it spoken</div>
        <div class="gt-ctrls">
          <select class="gt-sel" id="gtFrom"><option value="de-DE">🇩🇪 German</option></select>
          <span class="gt-arrow">→</span>
          <select class="gt-sel" id="gtTo">
            <option value="English">🇬🇧 English</option>
            <option value="Hindi">🇮🇳 Hindi (Hinglish)</option>
            <option value="Punjabi">Punjabi</option>
            <option value="Bengali">Bengali</option>
            <option value="Tamil">Tamil</option>
            <option value="Telugu">Telugu</option>
            <option value="Marathi">Marathi</option>
            <option value="French">🇫🇷 French</option>
            <option value="Spanish">🇪🇸 Spanish</option>
            <option value="Turkish">Turkish</option>
            <option value="Arabic">Arabic (العربية)</option>
            <option value="Chinese Simplified">🇨🇳 Chinese</option>
            <option value="Japanese">🇯🇵 Japanese</option>
            <option value="Korean">🇰🇷 Korean</option>
            <option value="Urdu">Urdu (Roman)</option>
          </select>
          <div class="spd-row">
            <span class="spd-lbl">Speed</span>
            <button class="spd-btn" data-r="0.6" onclick="setSpd(this)">Slow</button>
            <button class="spd-btn on" data-r="0.85" onclick="setSpd(this)">Normal</button>
            <button class="spd-btn" data-r="1.1" onclick="setSpd(this)">Fast</button>
          </div>
        </div>
      </div>
      <!-- two columns -->
      <div class="gt-body">
        <!-- LEFT -->
        <div class="gt-col">
          <div class="gt-col-lbl" style="color:#1e3a55">🇩🇪 German text</div>
          <textarea class="gt-ta" id="gtInput" placeholder="Paste or type German text here…&#10;&#10;Tip: Click 'Copy Passage' on the passage below then 'Paste Passage' here, or click any word in the passage to hear it."></textarea>
          <div class="gt-btns">
            <!-- PLAY/PAUSE button -->
            <button class="play-btn" id="playBtn" onclick="togglePlay()">▶ Play</button>
            <button class="gt-mini" onclick="gtClear()">✕ Clear</button>
            <button class="gt-mini" style="border-color:#1a2a40;color:#2a4a6a" onclick="gtUsePassage()" id="pasteBtn">📋 Paste Passage</button>
          </div>
        </div>
        <!-- MID -->
        <div class="gt-mid">
          <button class="tr-btn" id="trBtn" onclick="gtTranslate()" title="Translate"><span id="trIco">⇄</span></button>
        </div>
        <!-- RIGHT -->
        <div class="gt-col gt-out-col">
          <div class="gt-col-lbl" style="color:#2a1e50" id="gtOutLbl">🌐 Translation</div>
          <div class="gt-output" id="gtOut"><span style="color:#1a2535">Translation will appear here…</span></div>
          <div class="gt-btns">
            <button class="play-btn" id="playOutBtn" onclick="togglePlayOut()" style="background:#0e0818;border-color:#3a1e60;color:#c8a8f0">▶ Play Translation</button>
          </div>
        </div>
      </div>
    </div>

    <!-- ═══ PANEL 3: PASSAGE ═══ -->
    <div class="panel" id="panel-passage" draggable="true">
      <div class="panel-header" title="Drag to reorder">
        <span class="drag-handle"></span>
        <span class="panel-title">📖 German Passage</span>
      </div>
      <div class="panel-body">
        <div class="phead">
          <span class="ptitle" id="pTitle">German Typing Practice</span>
          <div class="pmeta-row">
            <span class="badge b-lvl" id="bLvl">A1</span>
            <span class="badge b-ctx" id="bCtx">Friend</span>
            <span class="badge b-wrd" id="bWrd">— words</span>
          </div>
        </div>

        <div class="empty" id="emptyEl">
          <div class="empty-i">🇩🇪</div>
          <div class="empty-t">Ready to practice?</div>
          <div class="empty-s">Choose level, context &amp; topic, then click <strong style="color:var(--gold-l)">Generate Passage</strong>.</div>
        </div>
        <div class="lstate" id="lEl">
          <div class="ldots"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div>
          <div class="ltxt" id="lTxt">Generating…</div>
        </div>

        <!-- Colour legend -->
        <div class="legend" id="legend" style="display:none">
          <span class="leg-item"><span class="leg-dot" style="background:var(--verb-l)"></span><span style="color:var(--verb-l);font-size:.7rem">Verb</span></span>
          <span class="leg-item"><span class="leg-dot" style="background:var(--noun-l)"></span><span style="color:var(--noun-l);font-size:.7rem">Noun</span></span>
          <span class="leg-item"><span class="leg-dot" style="background:var(--adj-l)"></span><span style="color:var(--adj-l);font-size:.7rem">Adjective / Adverb</span></span>
          <span class="leg-item"><span class="leg-dot" style="background:var(--gold-l)"></span><span style="color:var(--gold-l);font-size:.7rem">Key phrase</span></span>
          <span style="font-size:.68rem;color:#2a2a2a;margin-left:.3rem">← hover any highlighted word to see its meaning</span>
        </div>

        <div class="ptext" id="pText" style="display:none"></div>

        <!-- Copy & paste-to-translate bar -->
        <div class="copy-bar" id="copyBar">
          <button class="copy-btn" id="copyBtn" onclick="copyPassage()">📋 Copy Passage</button>
          <button class="paste-to-tr-btn" onclick="pasteAndScroll()">→ Send to Translate</button>
          <span class="copy-hint">or click any highlighted word to hear its pronunciation</span>
        </div>

        <!-- Refresh bar -->
        <div class="refresh-bar" id="refreshBar">
          <button class="refresh-btn" onclick="generate()"><span class="ricon">↻</span> Get Different Passage</button>
          <span class="refresh-hint">Same level &amp; topic — brand new text</span>
        </div>

        <!-- Typing -->
        <div class="prog-wrap" id="progWrap" style="display:none"><div class="prog-bar" id="progBar"></div></div>
        <div class="tlabel" id="tLabel" style="display:none">Type the passage below</div>
        <textarea class="tarea" id="tArea" placeholder="Start typing the German passage here…" disabled style="display:none" oninput="onType()" onkeydown="if(event.key==='Tab')event.preventDefault()"></textarea>
        <div class="cmp" id="cmpEl"></div>
        <div class="arow" id="aRow" style="display:none">
          <button class="btn-sec" onclick="resetTyping()">↺ Restart</button>
          <button class="btn-sec" onclick="hint()">💡 Hint</button>
          <div class="lstats" id="lstats"></div>
        </div>
      </div>
    </div>

  </div><!-- /drag-area -->
</div><!-- /page -->

<!-- RESULTS -->
<div class="roverlay" id="rOvl">
  <div class="rcard">
    <div class="re" id="rEmo">🎉</div>
    <div class="rt" id="rTit">Ausgezeichnet!</div>
    <div class="rs" id="rSub">You completed the passage!</div>
    <div class="rstats">
      <div class="rstat"><div class="rsv" id="r-wpm">—</div><div class="rsl">WPM</div></div>
      <div class="rstat"><div class="rsv" id="r-acc">—</div><div class="rsl">Accuracy</div></div>
      <div class="rstat"><div class="rsv" id="r-tim">—</div><div class="rsl">Time</div></div>
    </div>
    <div class="rbtns">
      <button class="btn-sec" onclick="closeR();resetTyping()">Try Again</button>
      <button class="btn-pri" onclick="closeR();generate()">New Passage ✦</button>
    </div>
  </div>
</div>

<!-- SELECTION COPY POPUP -->
<div class="sel-popup" id="selPopup">
  <span class="sel-text-preview" id="selPreview"></span>
  <button class="sel-copy-btn" onclick="selCopy()">📋 Copy</button>
  <button class="sel-speak-btn" onclick="selSpeak()">🔊 Listen</button>
</div>

<!-- RICH TOOLTIP -->
<div class="tt" id="tt">
  <div class="tt-word" id="ttWord"></div>
  <div class="tt-type" id="ttType"></div>
  <div class="tt-sep"></div>
  <div class="tt-en" id="ttEn"></div>
  <div class="tt-hi" id="ttHi"></div>
  <div class="tt-ex" id="ttEx"></div>
</div>

<script>
// ── STATE ─────────────────────────────────────────────────────
let lvl='A1', ctx='friend', passage='', vocab=[];
let t0=null, done=false, spkRate=0.85;
let translatedText='', isSpeaking=false, isOutSpeaking=false;
let streak=parseInt(localStorage.getItem('dt_s')||'0');
let passageHistory=JSON.parse(localStorage.getItem('dt_history')||'[]');
document.getElementById('hdr-streak').textContent=streak;

// ── DRAG & DROP PANELS ────────────────────────────────────────
let dragSrc=null;
document.querySelectorAll('.panel').forEach(p=>{
  p.addEventListener('dragstart',e=>{
    dragSrc=p;
    setTimeout(()=>p.classList.add('dragging'),0);
    e.dataTransfer.effectAllowed='move';
  });
  p.addEventListener('dragend',()=>{
    p.classList.remove('dragging');
    document.querySelectorAll('.panel').forEach(x=>x.classList.remove('drag-over'));
  });
  p.addEventListener('dragover',e=>{
    e.preventDefault();
    if(p!==dragSrc) p.classList.add('drag-over');
  });
  p.addEventListener('dragleave',()=>p.classList.remove('drag-over'));
  p.addEventListener('drop',e=>{
    e.preventDefault();
    p.classList.remove('drag-over');
    if(!dragSrc||dragSrc===p)return;
    const area=document.getElementById('dragArea');
    const panels=[...area.children];
    const srcIdx=panels.indexOf(dragSrc);
    const tgtIdx=panels.indexOf(p);
    if(srcIdx<tgtIdx) area.insertBefore(dragSrc,p.nextSibling);
    else area.insertBefore(dragSrc,p);
  });
});

// ── LEVEL / CONTEXT ───────────────────────────────────────────
function setLevel(b){
  document.querySelectorAll('.lvl-btn').forEach(x=>x.classList.remove('on'));
  b.classList.add('on'); lvl=b.dataset.lv;
  document.getElementById('bLvl').textContent=lvl;
}
const ctxL={friend:'Friend',university:'University',family:'Family',professional:'Professional',government:'Official'};
function setCtx(b){
  document.querySelectorAll('.ctx-btn').forEach(x=>x.classList.remove('on'));
  b.classList.add('on'); ctx=b.dataset.ctx;
  document.getElementById('bCtx').textContent=ctxL[ctx]||ctx;
}
function setSpd(b){
  document.querySelectorAll('.spd-btn').forEach(x=>x.classList.remove('on'));
  b.classList.add('on'); spkRate=parseFloat(b.dataset.r);
}

// ── SPEECH helpers ────────────────────────────────────────────
function getVoice(lang){
  const vv=speechSynthesis.getVoices();
  return vv.find(v=>v.lang===lang)||vv.find(v=>v.lang.startsWith(lang.split('-')[0]))||null;
}
const langBCP={
  'English':'en-US','Hindi':'hi-IN','Punjabi':'pa-IN','Bengali':'bn-IN',
  'Tamil':'ta-IN','Telugu':'te-IN','Marathi':'mr-IN','French':'fr-FR',
  'Spanish':'es-ES','Turkish':'tr-TR','Arabic':'ar-SA',
  'Chinese Simplified':'zh-CN','Japanese':'ja-JP','Korean':'ko-KR','Urdu':'ur-PK'
};

// ── PLAY / PAUSE — German input ───────────────────────────────
function togglePlay(){
  const btn=document.getElementById('playBtn');
  if(isSpeaking){
    speechSynthesis.pause();
    isSpeaking=false;
    btn.textContent='▶ Play';
    btn.classList.remove('playing');
  } else {
    const txt=document.getElementById('gtInput').value.trim();
    if(!txt){alert('Please paste or type some German text first.');return;}
    if(speechSynthesis.paused){
      speechSynthesis.resume();
      isSpeaking=true;
      btn.textContent='⏸ Pause';
      btn.classList.add('playing');
    } else {
      speechSynthesis.cancel();
      const u=new SpeechSynthesisUtterance(txt);
      u.lang='de-DE'; u.rate=spkRate; u.pitch=1;
      const gv=getVoice('de-DE'); if(gv)u.voice=gv;
      btn.textContent='⏸ Pause'; btn.classList.add('playing');
      isSpeaking=true;
      u.onend=u.onerror=()=>{
        isSpeaking=false;
        btn.textContent='▶ Play'; btn.classList.remove('playing');
      };
      speechSynthesis.speak(u);
    }
  }
}

// ── PLAY / PAUSE — translated output ─────────────────────────
function togglePlayOut(){
  const btn=document.getElementById('playOutBtn');
  if(isOutSpeaking){
    speechSynthesis.pause();
    isOutSpeaking=false;
    btn.textContent='▶ Play Translation'; btn.classList.remove('playing');
  } else {
    if(!translatedText){alert('Translate something first!');return;}
    const lang=document.getElementById('gtTo').value;
    const bcp=langBCP[lang]||'en-US';
    if(speechSynthesis.paused){
      speechSynthesis.resume();
      isOutSpeaking=true;
      btn.textContent='⏸ Pause'; btn.classList.add('playing');
    } else {
      speechSynthesis.cancel();
      const u=new SpeechSynthesisUtterance(translatedText);
      u.lang=bcp; u.rate=spkRate; u.pitch=1;
      const gv=getVoice(bcp); if(gv)u.voice=gv;
      btn.textContent='⏸ Pause'; btn.classList.add('playing');
      isOutSpeaking=true;
      u.onend=u.onerror=()=>{
        isOutSpeaking=false;
        btn.textContent='▶ Play Translation'; btn.classList.remove('playing');
      };
      speechSynthesis.speak(u);
    }
  }
}

// ── speak a single word (click on passage) ───────────────────
function speakWord(w){
  speechSynthesis.cancel();
  isSpeaking=false;
  document.getElementById('playBtn').textContent='▶ Play';
  document.getElementById('playBtn').classList.remove('playing');
  const u=new SpeechSynthesisUtterance(w);
  u.lang='de-DE'; u.rate=spkRate; u.pitch=1;
  const gv=getVoice('de-DE'); if(gv)u.voice=gv;
  speechSynthesis.speak(u);
}

// ── CLEAR ─────────────────────────────────────────────────────
function gtClear(){
  speechSynthesis.cancel(); isSpeaking=false;
  document.getElementById('playBtn').textContent='▶ Play';
  document.getElementById('playBtn').classList.remove('playing');
  document.getElementById('gtInput').value='';
  document.getElementById('gtOut').innerHTML='<span style="color:#1a2535">Translation will appear here…</span>';
  translatedText='';
}
function gtUsePassage(){
  if(!passage){alert('Generate a passage first!');return;}
  document.getElementById('gtInput').value=passage;
}

// ── COPY PASSAGE ──────────────────────────────────────────────
function copyPassage(){
  if(!passage)return;
  navigator.clipboard.writeText(passage).then(()=>{
    const btn=document.getElementById('copyBtn');
    btn.textContent='✓ Copied!'; btn.classList.add('copied');
    setTimeout(()=>{btn.textContent='📋 Copy Passage';btn.classList.remove('copied');},2000);
  });
}
// Copy & scroll to translate panel
function pasteAndScroll(){
  if(!passage){alert('Generate a passage first!');return;}
  document.getElementById('gtInput').value=passage;
  document.getElementById('panel-translate').scrollIntoView({behavior:'smooth',block:'start'});
}

// ── TRANSLATE ─────────────────────────────────────────────────
async function gtTranslate(){
  const txt=document.getElementById('gtInput').value.trim();
  const lang=document.getElementById('gtTo').value;
  if(!txt){alert('Please paste or type some German text first.');return;}
  const out=document.getElementById('gtOut');
  const btn=document.getElementById('trBtn');
  document.getElementById('gtOutLbl').textContent='🌐 '+lang;
  out.innerHTML='<span style="color:#1e3050;font-style:italic">Translating…</span>';
  btn.disabled=true; document.getElementById('trIco').innerHTML='<span class="spin">⟳</span>';
  const isHindi=lang==='Hindi'||lang==='Urdu';
  const prompt=`Translate the following German text into ${lang}.${isHindi?' Write in easy Roman script. After the translation, add: "Key words: " with 3 important German words and their meanings.':''}\nKeep it natural. Respond ONLY with the translation, no preamble.\n\nGerman:\n"${txt}"`;
  try{
    const r=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',headers:{'Content-Type':'application/json'},
      body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:600,messages:[{role:'user',content:prompt}]})
    });
    const d=await r.json();
    translatedText=d.content.map(i=>i.text||'').join('').trim();
    out.innerHTML=translatedText.replace(/\n/g,'<br>');
  }catch(e){
    out.innerHTML='<span style="color:#6a1a1a">Translation failed — please try again.</span>';
    translatedText='';
  }
  btn.disabled=false; document.getElementById('trIco').textContent='⇄';
}

// ── GENERATE ──────────────────────────────────────────────────
async function generate(){
  document.getElementById('emptyEl').style.display='none';
  document.getElementById('pText').style.display='none';
  document.getElementById('legend').style.display='none';
  document.getElementById('copyBar').classList.remove('vis');
  document.getElementById('refreshBar').classList.remove('vis');
  document.getElementById('lEl').classList.add('vis');
  document.getElementById('progWrap').style.display='none';
  document.getElementById('tLabel').style.display='none';
  document.getElementById('tArea').style.display='none';
  document.getElementById('cmpEl').classList.remove('vis');
  document.getElementById('aRow').style.display='none';
  document.getElementById('gtOut').innerHTML='<span style="color:#1a2535">Translation will appear here…</span>';
  translatedText='';
  const gb=document.getElementById('genBtn');
  gb.disabled=true; document.getElementById('genIco').innerHTML='<span class="spin">⟳</span>';
  resetState();

  const topic=document.getElementById('topicSel').value;
  const lvlDesc={
    A1:'A1 beginner — very simple present tense, short sentences, basic vocabulary, 80-100 words',
    A2:'A2 elementary — Perfekt past tense, modal verbs, simple subordinate clauses, 100-120 words',
    B1:'B1 intermediate — varied tenses, richer vocabulary, subordinate clauses, 120-150 words'
  };
  const ctxDesc={
    friend:'casual between close friends — informal "du", relaxed everyday language',
    university:'university/college — mix of informal with classmates and respectful with professors',
    family:'warm conversation with family — familiar tone, domestic vocabulary',
    professional:'professional office — formal "Sie", business vocabulary, polite structured language',
    government:'official government context (Bürgeramt, Ausländerbehörde, Finanzamt) — very formal "Sie", bureaucratic vocabulary'
  };
  const topicMap={
    daily_life:'daily life in Berlin as an Indian student',university:'university studies',
    food:'food and eating',transport:'public transport and travel',shopping:'shopping',
    weather:'weather and seasons',family:'family and relationships',
    work:'work and career',health:'health and doctor visits',hobbies:'hobbies and free time'
  };
  document.getElementById('lTxt').textContent=`Writing ${lvl} ${ctxDesc[ctx].split(' — ')[0].toLowerCase()} passage…`;

  const avoidBlock=passageHistory.length>0
    ? `\n\nIMPORTANT — do NOT reuse any of these already-given passages (different scenario, characters, vocabulary):\n`
      +passageHistory.map((h,i)=>`${i+1}. "${h.title}" — starts: "${h.start}"`).join('\n')
    : '';

  const prompt=`You are a German language teacher writing a typing practice passage for an Indian student in Berlin.

Level: ${lvlDesc[lvl]}
Topic: ${topicMap[topic]}
Context: ${ctxDesc[ctx]}

The passage MUST match the register (formal Sie vs informal du).
Make it authentic and practical, not textbook-y.
Include 10-14 key vocabulary words covering VERBS, NOUNS, ADJECTIVES, and key phrases.
For each vocab word, specify the type as exactly one of: verb, noun, adjective, adverb, phrase.
${avoidBlock}

Respond ONLY with valid JSON (no markdown):
{
  "title": "Short German title",
  "passage": "The German passage text...",
  "vocab": [
    {"word":"word as it appears in passage","type":"verb","meaning":"English meaning","hindi":"Hinglish meaning","example":"Short example sentence"}
  ]
}`;

  try{
    const r=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',headers:{'Content-Type':'application/json'},
      body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:1100,messages:[{role:'user',content:prompt}]})
    });
    const d=await r.json();
    const raw=d.content.map(i=>i.text||'').join('');
    const p=JSON.parse(raw.replace(/```json|```/g,'').trim());
    passage=p.passage; vocab=p.vocab||[];
    render(p.title,p.passage,p.vocab);
  }catch(e){ fallback(); }

  document.getElementById('lEl').classList.remove('vis');
  gb.disabled=false; document.getElementById('genIco').textContent='✦';
}

function fallback(){
  const f={
    title:'Mein Tag in Berlin',
    passage:'Ich heiße Raj und ich wohne in Berlin. Ich studiere International Business Management. Jeden Morgen stehe ich um sieben Uhr auf. Dann trinke ich Kaffee und esse Brot zum Frühstück. Um neun Uhr fahre ich mit der U-Bahn zur Universität. Die U-Bahn ist schnell und günstig. An der Uni lerne ich viel und treffe meine Freunde. Mittags esse ich in der Mensa. Das Essen ist billig aber gut. Am Abend koche ich zu Hause. Ich mag Berlin sehr. Die Stadt ist groß und interessant.',
    vocab:[
      {word:'wohne',type:'verb',meaning:'live / reside',hindi:'rehta/rehti hoon',example:'Ich wohne in Berlin.'},
      {word:'studiere',type:'verb',meaning:'study',hindi:'padhta/padhti hoon',example:'Ich studiere hier.'},
      {word:'Universität',type:'noun',meaning:'university',hindi:'vishwavidyalay',example:'Ich fahre zur Universität.'},
      {word:'günstig',type:'adjective',meaning:'affordable / cheap',hindi:'sasta',example:'Die U-Bahn ist günstig.'},
      {word:'Mensa',type:'noun',meaning:'university cafeteria',hindi:'uni ka khana ghar',example:'Ich esse in der Mensa.'},
      {word:'treffe',type:'verb',meaning:'meet',hindi:'milta/milti hoon',example:'Ich treffe meine Freunde.'},
      {word:'interessant',type:'adjective',meaning:'interesting',hindi:'dilchasp',example:'Berlin ist interessant.'},
      {word:'schnell',type:'adjective',meaning:'fast / quick',hindi:'tez',example:'Die U-Bahn ist schnell.'}
    ]
  };
  passage=f.passage; vocab=f.vocab;
  render(f.title,f.passage,f.vocab);
}

// ── RENDER PASSAGE — highlight every vocab word by type ──────
function render(title,p,voc){
  // save to history
  const entry={title,start:p.trim().split(/\s+/).slice(0,8).join(' ')};
  passageHistory.push(entry);
  if(passageHistory.length>10)passageHistory.shift();
  localStorage.setItem('dt_history',JSON.stringify(passageHistory));

  document.getElementById('pTitle').textContent=title;
  document.getElementById('bWrd').textContent=p.trim().split(/\s+/).length+' words';

  // type → CSS class mapping
  const typeClass={verb:'w-verb',noun:'w-noun',adjective:'w-adj',adverb:'w-adj',phrase:'w-key'};

  // tokenise
  const tokens=p.split(/(\s+)/);
  let html='';
  tokens.forEach(tok=>{
    const bare=tok.replace(/[.,!?;:'"()\-–«»„"‚']/g,'').toLowerCase();
    const m=voc.find(v=>{
      const vl=v.word.toLowerCase();
      return vl===bare||vl===tok.toLowerCase().replace(/[.,!?;:'"()\-–«»„"‚']/g,'');
    });
    if(m){
      const i=voc.indexOf(m);
      const cls=typeClass[m.type]||'w-key';
      const safe=tok.replace(/\\/g,'\\\\').replace(/'/g,"\\'");
      html+=`<span class="${cls}" onmouseenter="showTT(event,${i})" onmouseleave="hideTT()" onclick="speakWord('${safe}')">${tok}</span>`;
    } else html+=tok;
  });
  document.getElementById('pText').innerHTML=html;
  document.getElementById('pText').style.display='block';
  document.getElementById('legend').style.display='flex';
  document.getElementById('copyBar').classList.add('vis');
  document.getElementById('refreshBar').classList.add('vis');

  // prefill translate input
  document.getElementById('gtInput').value=p;

  // typing UI
  document.getElementById('progWrap').style.display='block';
  document.getElementById('progBar').style.width='0%';
  document.getElementById('tLabel').style.display='flex';
  const ta=document.getElementById('tArea');
  ta.style.display='block'; ta.disabled=false; ta.value=''; ta.focus();
  document.getElementById('aRow').style.display='flex';
  document.getElementById('lstats').innerHTML='<span style="color:#222">Start typing to see live stats</span>';
}

// ── TOOLTIP ───────────────────────────────────────────────────
const typeLabel={verb:'Verb',noun:'Noun',adjective:'Adjective',adverb:'Adverb',phrase:'Key Phrase'};
const typeClass2={verb:'tt-verb',noun:'tt-noun',adjective:'tt-adj',adverb:'tt-adj',phrase:'tt-key'};
function showTT(e,i){
  const v=vocab[i]; if(!v)return;
  const t=document.getElementById('tt');
  t.className='tt vis '+(typeClass2[v.type]||'tt-key');
  document.getElementById('ttWord').textContent=v.word;
  document.getElementById('ttType').textContent=typeLabel[v.type]||v.type;
  document.getElementById('ttEn').textContent='🇬🇧 '+v.meaning;
  document.getElementById('ttHi').textContent='🇮🇳 '+v.hindi;
  document.getElementById('ttEx').textContent=v.example?'e.g. "'+v.example+'"':'';
  // position
  let x=e.clientX+16, y=e.clientY-10;
  if(x+240>window.innerWidth) x=e.clientX-250;
  if(y+160>window.innerHeight) y=e.clientY-160;
  t.style.left=x+'px'; t.style.top=y+'px';
}
function hideTT(){document.getElementById('tt').classList.remove('vis');}

// ── TYPING ────────────────────────────────────────────────────
function onType(){
  const typed=document.getElementById('tArea').value;
  if(!typed){resetState();return;}
  if(!t0)t0=Date.now();
  const tgt=passage;
  document.getElementById('progBar').style.width=(Math.min(typed.length/tgt.length,1)*100)+'%';
  renderCmp(typed,tgt);
  const el=(Date.now()-t0)/60000;
  const wpm=el>0?Math.round(typed.trim().split(/\s+/).length/el):0;
  const cor=[...typed].filter((c,i)=>c===tgt[i]).length;
  const acc=typed.length>0?Math.round(cor/typed.length*100):100;
  document.getElementById('hdr-wpm').textContent=wpm||'—';
  document.getElementById('hdr-acc').textContent=acc+'%';
  document.getElementById('lstats').innerHTML=`<span class="${acc>=90?'ag':'ab'}">${acc}%</span><span style="color:#1e1e1e">·</span><span style="color:var(--grey)">${wpm} wpm</span>`;
  if(typed.length>=tgt.length&&!done){
    const fa=Math.round(cor/typed.length*100);
    if(fa>=85||typed===tgt)finish(wpm,fa,el);
  }
}
function renderCmp(typed,tgt){
  const cd=document.getElementById('cmpEl');
  if(!typed){cd.classList.remove('vis');return;}
  cd.classList.add('vis');
  let h='';
  for(let i=0;i<Math.max(typed.length,Math.min(typed.length+1,tgt.length));i++){
    if(i===typed.length) h+=`<span class="cur cp">${tgt[i]===' '?'&nbsp;':(tgt[i]||'')}</span>`;
    else{const ok=typed[i]===tgt[i];h+=`<span class="${ok?'cc':'cw'}">${typed[i]===' '?'&nbsp;':typed[i]}</span>`;}
  }
  cd.innerHTML=h;
}
function resetState(){
  t0=null; done=false;
  document.getElementById('progBar').style.width='0%';
  document.getElementById('cmpEl').classList.remove('vis');
  document.getElementById('hdr-wpm').textContent='—';
  document.getElementById('hdr-acc').textContent='—';
}
function resetTyping(){
  resetState();
  const ta=document.getElementById('tArea'); ta.value=''; ta.focus();
  document.getElementById('lstats').innerHTML='<span style="color:#222">Start typing to see live stats</span>';
}
function hint(){
  const ta=document.getElementById('tArea');
  const nx=passage[ta.value.length];
  if(nx){ta.value+=nx;onType();}
}
function finish(wpm,acc,el){
  done=true; streak++;
  localStorage.setItem('dt_s',streak);
  document.getElementById('hdr-streak').textContent=streak;
  const s=Math.round(el*60);
  const ts=s<60?s+'s':Math.floor(s/60)+'m '+(s%60)+'s';
  let em='🎉',ti='Sehr gut!',su='Great job!';
  if(acc>=97){em='🏆';ti='Perfekt!';su='Flawless — outstanding accuracy!';}
  else if(acc>=90){em='🌟';ti='Ausgezeichnet!';su='Excellent! Keep it up.';}
  else{em='👍';ti='Gut gemacht!';su='Good effort! Aim for 90%+ accuracy.';}
  document.getElementById('rEmo').textContent=em;
  document.getElementById('rTit').textContent=ti;
  document.getElementById('rSub').textContent=su;
  document.getElementById('r-wpm').textContent=wpm;
  document.getElementById('r-acc').textContent=acc+'%';
  document.getElementById('r-tim').textContent=ts;
  setTimeout(()=>document.getElementById('rOvl').classList.add('vis'),400);
}
function closeR(){document.getElementById('rOvl').classList.remove('vis');}

// ── THEME TOGGLE ─────────────────────────────────────────────
const savedTheme = localStorage.getItem('dt_theme')||'dark';
if(savedTheme==='light'){
  document.body.classList.add('light');
  document.getElementById('themeLbl').textContent='☀️ Light';
}
function toggleTheme(){
  const isLight=document.body.classList.toggle('light');
  document.getElementById('themeLbl').textContent=isLight?'☀️ Light':'🌙 Dark';
  localStorage.setItem('dt_theme',isLight?'light':'dark');
}

// ── FONT SIZE ─────────────────────────────────────────────────
let fontSize=parseInt(localStorage.getItem('dt_font')||'16');
applyFont();
function applyFont(){
  // apply to passage text, translate areas and typing area
  document.documentElement.style.setProperty('--passage-fs', fontSize+'px');
  document.querySelectorAll('.ptext,.gt-ta,.gt-output,.tarea,.cmp').forEach(el=>{
    el.style.fontSize=fontSize+'px';
  });
  document.getElementById('fontVal').textContent=fontSize+'px';
  localStorage.setItem('dt_font',fontSize);
}
function changeFont(delta){
  fontSize=Math.min(28,Math.max(11,fontSize+delta));
  applyFont();
}

// ── SELECTION COPY POPUP ──────────────────────────────────────
let selText='';
document.getElementById('pText').addEventListener('mouseup',showSelPopup);
document.addEventListener('mousedown',e=>{
  if(!e.target.closest('#selPopup'))hideSelPopup();
});
function showSelPopup(e){
  const sel=window.getSelection();
  const txt=sel?sel.toString().trim():'';
  if(!txt){hideSelPopup();return;}
  selText=txt;
  const preview=txt.length>30?txt.slice(0,28)+'…':txt;
  document.getElementById('selPreview').textContent='"'+preview+'"';
  const popup=document.getElementById('selPopup');
  // position just above the mouse
  let x=e.clientX-60, y=e.clientY-58;
  if(x<8)x=8;
  if(x+320>window.innerWidth)x=window.innerWidth-325;
  if(y<8)y=e.clientY+18;
  popup.style.left=x+'px'; popup.style.top=y+'px';
  popup.classList.add('vis');
}
function hideSelPopup(){
  document.getElementById('selPopup').classList.remove('vis');
  selText='';
}
function selCopy(){
  if(!selText)return;
  navigator.clipboard.writeText(selText).then(()=>{
    const btn=document.querySelector('.sel-copy-btn');
    btn.textContent='✓ Copied!';
    setTimeout(()=>{btn.textContent='📋 Copy';hideSelPopup();},1400);
  });
}
function selSpeak(){
  if(!selText)return;
  speakWord(selText);
  hideSelPopup();
}

// init voices
if(window.speechSynthesis){
  speechSynthesis.getVoices();
  speechSynthesis.addEventListener('voiceschanged',()=>speechSynthesis.getVoices());
}
</script>
</body>
</html>
