# TabuXada
<!DOCTYPE html>

<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no,viewport-fit=cover">
<title>TabuXada</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;700;800;900&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#0e1621;--s1:#131f2e;--s2:#1a2d3f;--bd:#2a4058;--bd2:#3a5570;
  --gr:#58cc02;--g2:#46a302;--bl:#1cb0f6;--b2:#0d8fcc;
  --rd:#ff4b4b;--r2:#cc3b3b;--yl:#ffc800;--y2:#d4a800;
  --or:#fb923c;--pu:#a78bfa;--ai:#f59e0b;--ai2:#fbbf24;
  --tx:#e8f4fd;--tx2:#7a9ab0;--tx3:#3a5a70;
  --R:14px;--r:10px;--F:'Nunito',sans-serif;
}
*{box-sizing:border-box;margin:0;padding:0}
html{font-size:16px;-webkit-text-size-adjust:100%}
body{font-family:var(--F);background:var(--bg);color:var(--tx);height:100vh;overflow:hidden;-webkit-font-smoothing:antialiased;-webkit-tap-highlight-color:transparent;touch-action:manipulation}
input,textarea{font-size:16px!important;font-family:var(--F)}
::-webkit-scrollbar{width:4px}::-webkit-scrollbar-thumb{background:var(--bd);border-radius:2px}
/* Accessibility */
html.hc{filter:contrast(1.6)}
html.lg{font-size:19px!important}
html.lg .q-prompt{font-size:1.25rem}
html.lg .mc-btn{font-size:1rem}
html.lg .topt{font-size:1.1rem}
html.ra *{animation:none!important;transition:none!important}
.scr{display:none;position:fixed;inset:0;overflow:hidden;flex-direction:column}.scr.on{display:flex}
#sOb{background:var(--bg);align-items:center;justify-content:center;padding:20px;overflow-y:auto}
.ob-wrap{width:100%;max-width:420px;padding:10px 0 30px}
.logo{text-align:center;margin-bottom:4px;font-size:2.8rem;font-weight:900;letter-spacing:-1px}
.logo span{color:var(--rd)}
.ob-sub{text-align:center;color:var(--tx2);font-size:.82rem;margin-bottom:18px}
.ob-card{background:var(--s1);border:1.5px solid var(--bd);border-radius:20px;padding:24px 20px}
.lbl{font-size:.68rem;font-weight:900;text-transform:uppercase;letter-spacing:1.5px;color:var(--tx2);margin-bottom:6px}
.inp{width:100%;background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--r);color:var(--tx);font-size:1rem;font-weight:700;padding:12px 14px;outline:none;transition:border-color .2s;margin-bottom:18px}
.inp:focus{border-color:var(--bl)}
.sel-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:16px}
.sel-btn{background:var(--s2);border:2px solid var(--bd);border-radius:var(--R);padding:12px 8px;cursor:pointer;text-align:center;transition:all .15s}
.sel-btn.on{border-color:var(--gr);background:rgba(88,204,2,.07)}
.sel-btn .ei{font-size:1.4rem;margin-bottom:3px}
.sel-btn .nm{font-size:.83rem;font-weight:900}
.sel-btn .sb{font-size:.62rem;color:var(--tx2);margin-top:1px}
.lang-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;margin-bottom:20px}
.lang-btn{background:var(--s2);border:2px solid var(--bd);border-radius:var(--R);padding:14px 6px;cursor:pointer;text-align:center;transition:all .15s}
.lang-btn.on{border-color:var(--bl);background:rgba(28,176,246,.07)}
.lang-btn .lei{font-size:1.8rem;margin-bottom:4px}
.lang-btn .lnm{font-size:.8rem;font-weight:900}
.btn-main{display:block;width:100%;background:var(--gr);border:none;border-bottom:4px solid var(--g2);border-radius:var(--R);color:#fff;font-family:var(--F);font-size:.95rem;font-weight:900;padding:14px;cursor:pointer;transition:all .1s}
.btn-main:active:not(:disabled){transform:translateY(2px);border-bottom-width:2px}
.btn-main:disabled{opacity:.35;cursor:default}
.btn-red{background:var(--rd)!important;border-color:var(--r2)!important}
.btn-blue{background:var(--bl)!important;border-color:var(--b2)!important}
.btn-yl{background:var(--yl)!important;border-color:var(--y2)!important;color:#111!important}
#sApp.on{display:flex;flex-direction:column}
.topbar{background:var(--s1);border-bottom:1.5px solid var(--bd);padding:10px 14px;padding-top:calc(10px + env(safe-area-inset-top,0px));display:flex;align-items:center;gap:8px;flex-shrink:0;z-index:40}
.av{width:36px;height:36px;border-radius:50%;background:linear-gradient(135deg,var(--bl),var(--pu));display:flex;align-items:center;justify-content:center;font-size:1.3rem;border:2px solid var(--bd2);flex-shrink:0;cursor:pointer}
.uname{font-weight:900;font-size:.88rem;flex:1;min-width:0;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.stat-pill{display:flex;align-items:center;gap:4px;background:var(--s2);border:1.5px solid var(--bd);border-radius:99px;padding:5px 9px;font-size:.78rem;font-weight:900;cursor:pointer;flex-shrink:0}
.stat-pill svg{width:14px;height:14px}
.stat-pill.hrt{color:var(--rd)}.stat-pill.gem{color:var(--yl)}.stat-pill.xp{color:var(--pu)}
.scroll-main{flex:1;overflow-y:auto;-webkit-overflow-scrolling:touch}
.bot-nav{background:var(--s1);border-top:1.5px solid var(--bd);display:flex;padding-bottom:env(safe-area-inset-bottom,0px);flex-shrink:0}
.nb{flex:1;display:flex;flex-direction:column;align-items:center;gap:3px;padding:9px 4px;cursor:pointer;border:none;background:transparent;color:var(--tx3);font-family:var(--F);font-size:.54rem;font-weight:900;text-transform:uppercase;letter-spacing:.3px;transition:color .15s;position:relative;min-height:48px}
.nb svg{width:22px;height:22px}
.nb.on{color:var(--gr)}
.nb.on::after{content:'';position:absolute;bottom:0;left:50%;transform:translateX(-50%);width:26px;height:3px;background:var(--gr);border-radius:3px 3px 0 0}
.tab{display:none;padding:14px}.tab.on{display:block}
.sec-h{font-size:.88rem;font-weight:900;margin-bottom:10px;display:flex;align-items:center;gap:6px}
.clist{display:flex;flex-direction:column;gap:10px;margin-bottom:18px}
.ccard{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:14px;cursor:pointer;display:flex;align-items:center;gap:12px;transition:all .15s}
.ccard:active{transform:scale(.98)}
.cico{width:52px;height:52px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:1.6rem;flex-shrink:0}
.cinfo{flex:1;min-width:0}
.cnm{font-size:.88rem;font-weight:900;margin-bottom:2px}
.cds{font-size:.68rem;color:var(--tx2);margin-bottom:5px}
.clvl{display:inline-flex;font-size:.62rem;font-weight:900;padding:2px 7px;border-radius:99px;margin-bottom:5px;background:rgba(167,139,250,.12);color:var(--pu);border:1px solid rgba(167,139,250,.2)}
.pbar{background:var(--s2);border-radius:99px;height:6px;overflow:hidden;border:1px solid var(--bd)}
.pbarf{height:100%;border-radius:99px;transition:width .6s ease}
.cst{display:flex;justify-content:space-between;margin-top:4px}
.cst-t{font-size:.62rem;color:var(--tx2);font-weight:700}
.tag{display:inline-flex;align-items:center;font-size:.58rem;font-weight:900;padding:2px 7px;border-radius:99px;text-transform:uppercase;letter-spacing:.4px}
.tg{background:rgba(88,204,2,.12);color:var(--gr)}.tb{background:rgba(28,176,246,.12);color:var(--bl)}
.ty{background:rgba(255,200,0,.12);color:var(--yl)}.tr{background:rgba(255,75,75,.12);color:var(--rd)}
.tp{background:rgba(167,139,250,.12);color:var(--pu)}
.map-hdr{display:flex;align-items:center;gap:10px;margin-bottom:14px;position:sticky;top:0;background:var(--bg);padding:4px 0 10px;z-index:10}
.back-btn{background:var(--s2);border:1.5px solid var(--bd);border-radius:99px;color:var(--tx2);font-size:.72rem;font-weight:700;padding:7px 12px;cursor:pointer;font-family:var(--F);min-height:36px}
.map-ttl{font-weight:900;font-size:.95rem;flex:1}
.unit-box{margin-bottom:16px}
.unit-hdr{background:var(--s2);border-radius:var(--r);padding:10px 12px;margin-bottom:8px;border-left:3px solid var(--bl)}
.unit-n{font-size:.6rem;font-weight:900;text-transform:uppercase;letter-spacing:1px;color:var(--tx2)}
.unit-t{font-weight:800;font-size:.84rem;margin-top:1px}
.lnode{display:flex;align-items:center;gap:10px;padding:11px 12px;background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);cursor:pointer;transition:all .15s;margin-bottom:6px;min-height:60px}
.lnode:active:not(.locked){transform:scale(.98)}
.lnode.done{border-color:rgba(88,204,2,.3);background:rgba(88,204,2,.03)}
.lnode.locked{opacity:.4;cursor:default}
.lnode.active-next{border-color:var(--bl);background:rgba(28,176,246,.04)}
.lnode.chest-node{border-color:rgba(255,200,0,.5);background:rgba(255,200,0,.05)}
.lnode.chest-node .lico{background:rgba(255,200,0,.15);border-color:var(--yl)}
.lico{width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.1rem;flex-shrink:0;border:2px solid var(--bd)}
.lnode.done .lico{background:rgba(88,204,2,.1);border-color:var(--gr)}
.lnode.active-next .lico{background:rgba(28,176,246,.1);border-color:var(--bl)}
.linfo{flex:1;min-width:0}
.ltit{font-size:.84rem;font-weight:800;margin-bottom:2px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.lxp{font-size:.7rem;font-weight:900;color:var(--yl);flex-shrink:0}
#sLesson{background:var(--bg)}
.les-shell{display:flex;flex-direction:column;height:100%}
.les-hdr{padding:10px 14px;padding-top:calc(10px + env(safe-area-inset-top,0px));display:flex;align-items:center;gap:10px;background:var(--s1);border-bottom:1.5px solid var(--bd);flex-shrink:0}
.les-close{background:none;border:none;color:var(--tx2);font-size:1.3rem;cursor:pointer;padding:4px;min-width:36px;min-height:36px;display:flex;align-items:center;justify-content:center}
.les-pw{flex:1;background:var(--s2);border-radius:99px;height:12px;overflow:hidden;border:1.5px solid var(--bd)}
.les-pf{height:100%;border-radius:99px;background:linear-gradient(90deg,var(--gr),#7eff00);transition:width .4s cubic-bezier(.34,1.3,.64,1)}
.les-hts{display:flex;gap:2px;align-items:center}
.h-ic{font-size:.95rem;transition:all .25s}
.h-ic.lost{opacity:.2;transform:scale(.8)}
.les-body{flex:1;overflow-y:auto;-webkit-overflow-scrolling:touch;padding:16px 14px}
.les-foot{padding:12px 14px calc(12px + env(safe-area-inset-bottom,0px));background:var(--s1);border-top:1.5px solid var(--bd);flex-shrink:0}
.q-badge{display:inline-flex;align-items:center;gap:4px;font-size:.62rem;font-weight:900;text-transform:uppercase;letter-spacing:.8px;padding:3px 9px;border-radius:99px;margin-bottom:8px}
.q-prompt{font-size:1.1rem;font-weight:800;line-height:1.45;margin-bottom:12px}
.mc-opts{display:flex;flex-direction:column;gap:8px}
.mc-btn{background:var(--s1);border:2px solid var(--bd);border-radius:var(--R);padding:14px;cursor:pointer;text-align:left;font-family:var(--F);font-size:.92rem;font-weight:700;color:var(--tx);transition:border-color .1s;display:flex;align-items:center;gap:10px;min-height:52px}
.mc-btn.sel{border-color:var(--bl);background:rgba(28,176,246,.07)}
.mc-btn.correct{border-color:var(--gr);background:rgba(88,204,2,.08);color:var(--gr)}
.mc-btn.wrong{border-color:var(--rd);background:rgba(255,75,75,.08);color:var(--rd)}
.mc-ltr{width:28px;height:28px;border-radius:8px;background:var(--s2);border:1.5px solid var(--bd);display:flex;align-items:center;justify-content:center;font-size:.72rem;font-weight:900;flex-shrink:0}
.mc-btn.sel .mc-ltr{background:var(--bl);border-color:var(--bl);color:#fff}
.mc-btn.correct .mc-ltr{background:var(--gr);border-color:var(--gr);color:#fff}
.mc-btn.wrong .mc-ltr{background:var(--rd);border-color:var(--rd);color:#fff}
.type-inp{background:var(--s1);border:2px solid var(--bd);border-radius:var(--R);color:var(--tx);font-size:1.6rem;font-weight:900;text-align:center;padding:14px;width:100%;outline:none;transition:border-color .2s;margin-top:8px}
.type-inp:focus{border-color:var(--bl)}
.type-inp.ok{border-color:var(--gr);color:var(--gr)}
.type-inp.err{border-color:var(--rd);color:var(--rd)}
.expl-card{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:18px}
.expl-em{font-size:2.2rem;text-align:center;margin-bottom:8px}
.expl-ttl{font-size:1rem;font-weight:900;margin-bottom:8px}
.expl-body{font-size:.84rem;line-height:1.75;color:#b8d4e8;white-space:pre-wrap}
.expl-tip{background:rgba(28,176,246,.07);border-left:3px solid var(--bl);border-radius:0 8px 8px 0;padding:8px 12px;margin-top:12px;font-size:.78rem;color:var(--tx2);line-height:1.5}
.code-wrap{border-radius:var(--R);overflow:hidden;border:1.5px solid var(--bd);margin-bottom:8px}
.code-hdr{background:#080f17;padding:7px 12px;display:flex;align-items:center;gap:5px;border-bottom:1px solid var(--bd)}
.cdot{width:9px;height:9px;border-radius:50%}
.clang{font-size:.6rem;font-weight:900;color:var(--tx3);margin-left:auto;letter-spacing:1px;text-transform:uppercase}
.code-ta{background:#080f17;color:#e6edf3;font-family:'Courier New',monospace;font-size:.82rem;line-height:1.65;padding:12px;border:none;outline:none;resize:none;width:100%;min-height:110px;tab-size:4}
.code-out{background:#050c12;border-top:1px solid var(--bd);padding:8px 12px}
.cout-lbl{font-size:.58rem;font-weight:900;text-transform:uppercase;letter-spacing:1px;color:var(--tx3);margin-bottom:3px}
.cout-txt{font-family:'Courier New',monospace;font-size:.8rem;min-height:24px;white-space:pre-wrap;word-break:break-all}
.run-btn{display:inline-flex;align-items:center;gap:5px;background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--r);color:var(--tx);font-family:var(--F);font-size:.76rem;font-weight:800;padding:7px 13px;cursor:pointer;min-height:36px;margin-bottom:8px}
.fb-bar{border-radius:var(--R);padding:12px 14px;display:flex;align-items:flex-start;gap:9px;margin-bottom:10px}
.fb-bar.ok{background:rgba(88,204,2,.09);border:1.5px solid rgba(88,204,2,.22)}
.fb-bar.err{background:rgba(255,75,75,.07);border:1.5px solid rgba(255,75,75,.18)}
.fb-ic{font-size:1.4rem;flex-shrink:0}
.fb-ttl{font-size:.9rem;font-weight:900}
.fb-sub{font-size:.74rem;opacity:.7;margin-top:1px}
.chk-btn{display:block;width:100%;background:var(--gr);border:none;border-bottom:4px solid var(--g2);border-radius:var(--R);color:#fff;font-family:var(--F);font-size:.95rem;font-weight:900;padding:14px;cursor:pointer;transition:all .1s;min-height:52px}
.chk-btn:disabled{background:var(--s2);border-color:var(--bd);color:var(--tx3);cursor:default;border-bottom-color:var(--bd)}
.chk-btn.err-st{background:var(--rd);border-bottom-color:var(--r2)}
.chk-btn:active:not(:disabled){transform:translateY(2px);border-bottom-width:2px}
.modal-ov{position:fixed;inset:0;background:rgba(0,0,0,.8);z-index:500;display:none;align-items:flex-end;backdrop-filter:blur(4px)}
.modal-ov.on{display:flex}
.modal-sheet{background:var(--s1);border:1.5px solid var(--bd);border-radius:20px 20px 0 0;width:100%;padding:20px 20px calc(20px + env(safe-area-inset-bottom,0px));max-height:90vh;overflow-y:auto}
.modal-ttl{font-size:1.1rem;font-weight:900;margin-bottom:16px;text-align:center}
.heart-timer{text-align:center;background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--R);padding:10px;margin-bottom:12px}
.ht-label{font-size:.62rem;text-transform:uppercase;letter-spacing:1px;color:var(--tx2);margin-bottom:2px}
.ht-time{font-size:1.4rem;font-weight:900;color:var(--yl)}
.hrow{display:flex;align-items:center;gap:12px;border:1.5px solid var(--bd);border-radius:var(--R);padding:13px 14px;cursor:pointer;margin-bottom:10px;transition:all .15s;background:var(--s2)}
.hrow:active{transform:scale(.98)}
.hrow-ic{font-size:1.5rem;flex-shrink:0}
.hrow-nm{font-weight:900;font-size:.88rem}
.hrow-ds{font-size:.68rem;color:var(--tx2);margin-top:2px}
.hrow-price{font-size:.8rem;font-weight:900;color:var(--yl);background:rgba(255,200,0,.1);border:1.5px solid rgba(255,200,0,.3);border-radius:99px;padding:5px 10px;flex-shrink:0;white-space:nowrap}
.avatar-grid{display:grid;grid-template-columns:repeat(6,1fr);gap:8px;margin-bottom:16px}
.av-opt{font-size:1.6rem;text-align:center;padding:8px;border-radius:10px;border:2px solid var(--bd);cursor:pointer;min-height:48px;display:flex;align-items:center;justify-content:center}
.av-opt.sel{border-color:var(--bl);background:rgba(28,176,246,.1)}
.modal-btns{display:flex;gap:8px;margin-top:6px}
.btn-save{flex:1;background:var(--gr);border:none;border-radius:var(--R);color:#fff;font-family:var(--F);font-size:.9rem;font-weight:900;padding:13px;cursor:pointer;min-height:48px}
.btn-cancel{background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--R);color:var(--tx2);font-family:var(--F);font-size:.9rem;font-weight:800;padding:13px 18px;cursor:pointer;min-height:48px}
.win-ov{position:fixed;inset:0;background:rgba(0,0,0,.8);z-index:500;display:none;align-items:center;justify-content:center;padding:20px;backdrop-filter:blur(4px)}
.win-ov.on{display:flex}
.win-card{background:var(--s1);border:1.5px solid var(--bd);border-radius:22px;padding:24px 20px;width:100%;max-width:360px;text-align:center;animation:pop .4s cubic-bezier(.34,1.56,.64,1)}
.win-em{font-size:3.5rem;margin-bottom:5px}
.win-ttl{font-size:1.4rem;font-weight:900;margin-bottom:4px}
.win-sub{color:var(--tx2);font-size:.82rem;margin-bottom:16px}
.win-rewards{display:flex;justify-content:center;gap:10px;margin-bottom:20px}
.rw{display:flex;align-items:center;gap:5px;background:var(--s2);border:1.5px solid var(--bd);border-radius:99px;padding:7px 13px;font-size:.84rem;font-weight:900}
.chest-win{background:linear-gradient(135deg,#2d2000,#1a1200);border:2px solid var(--yl);border-radius:22px;padding:28px 20px;width:100%;max-width:340px;text-align:center;animation:pop .5s cubic-bezier(.34,1.56,.64,1);box-shadow:0 0 40px rgba(255,200,0,.3)}
#sTabu{background:var(--bg)}
.tabu-shell{display:flex;flex-direction:column;height:100%}
.tabu-hdr{padding:10px 14px;padding-top:calc(10px + env(safe-area-inset-top,0px));display:flex;align-items:center;gap:10px;background:var(--s1);border-bottom:1.5px solid var(--bd);flex-shrink:0}
.tabu-body{flex:1;overflow-y:auto;-webkit-overflow-scrolling:touch;padding:14px}
.tab-switch{display:flex;gap:6px;background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--R);padding:4px;margin-bottom:14px}
.tab-sw-btn{flex:1;background:transparent;border:none;border-radius:10px;color:var(--tx2);font-family:var(--F);font-size:.78rem;font-weight:900;padding:9px;cursor:pointer;transition:all .2s;min-height:38px}
.tab-sw-btn.on{background:var(--s1);color:var(--tx);border:1.5px solid var(--bd)}
.tlvl-card{background:var(--s1);border:2px solid var(--bd);border-radius:var(--R);padding:14px;cursor:pointer;display:flex;align-items:center;gap:12px;transition:all .15s;min-height:70px;margin-bottom:8px}
.tlvl-card:active{transform:scale(.98)}
.tlvl-ic{width:46px;height:46px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:1.5rem;flex-shrink:0}
.tlvl-nm{font-size:.88rem;font-weight:900;margin-bottom:2px}
.tlvl-ds{font-size:.68rem;color:var(--tx2)}
.tstats{display:flex;gap:8px}
.tstat{flex:1;background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--r);padding:8px;text-align:center}
.tstat-v{font-size:1.25rem;font-weight:900}
.tstat-l{font-size:.56rem;text-transform:uppercase;letter-spacing:.8px;color:var(--tx2);margin-top:1px}
.tprog{background:var(--s2);border-radius:99px;height:7px;overflow:hidden;border:1px solid var(--bd);margin-bottom:4px}
.tprogf{height:100%;border-radius:99px;background:linear-gradient(90deg,var(--rd),var(--or));transition:width .3s ease}
.ttimer{background:var(--s2);border-radius:99px;height:5px;overflow:hidden;border:1px solid var(--bd)}
.ttimerb{height:100%;border-radius:99px;background:var(--gr);transition:width .1s linear,background .3s}
.ttimerb.warn{background:var(--yl)}.ttimerb.danger{background:var(--rd)}
.tcard{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:16px}
.tq{font-size:2rem;font-weight:900;text-align:center;margin:6px 0 14px;animation:pop .3s cubic-bezier(.34,1.56,.64,1)}
.topts{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.topt{background:rgba(255,255,255,.04);border:2px solid var(--bd);border-radius:var(--r);padding:14px;cursor:pointer;font-family:var(--F);font-size:1rem;font-weight:800;color:var(--tx);text-align:center;min-height:54px;display:flex;align-items:center;justify-content:center}
.topt.correct{background:rgba(88,204,2,.1);border-color:var(--gr);color:var(--gr)}
.topt.wrong{background:rgba(255,75,75,.1);border-color:var(--rd);color:var(--rd)}
.ttype-inp{background:rgba(255,255,255,.05);border:2px solid var(--bd);border-radius:var(--R);color:var(--tx);font-family:var(--F);font-size:1.5rem;font-weight:900;text-align:center;padding:12px;width:100%;outline:none}
.ttype-inp:focus{border-color:var(--bl)}
.ttype-inp.ok{border-color:var(--gr);color:var(--gr)}.ttype-inp.err{border-color:var(--rd);color:var(--rd)}
.tfb{text-align:center;font-weight:900;font-size:.86rem;min-height:20px;margin-top:6px}
.tfb.ok{color:var(--gr)}.tfb.err{color:var(--rd)}
.tnext{display:block;width:100%;background:var(--yl);color:#111;border:none;border-radius:var(--R);font-family:var(--F);font-size:.9rem;font-weight:900;padding:12px;cursor:pointer;margin-top:8px;animation:pop .25s cubic-bezier(.34,1.56,.64,1);min-height:48px}
.tres{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:20px;text-align:center}
.tres-em{font-size:3rem;margin-bottom:5px}
.tres-ttl{font-size:1.5rem;font-weight:900;margin-bottom:4px}
.tres-pts{font-size:2.8rem;font-weight:900;background:linear-gradient(135deg,var(--yl),var(--or));-webkit-background-clip:text;-webkit-text-fill-color:transparent;margin:4px 0 12px}
.tres-grid{display:flex;justify-content:center;gap:10px;margin-bottom:14px}
.tres-st{background:var(--s2);border-radius:var(--r);padding:8px 13px;text-align:center}
.tres-sv{font-size:1.25rem;font-weight:900}
.tres-sl{font-size:.56rem;text-transform:uppercase;letter-spacing:.7px;color:var(--tx2);margin-top:1px}
.missed-list{background:rgba(255,75,75,.06);border:1px solid rgba(255,75,75,.14);border-radius:var(--R);padding:10px 12px;margin:8px 0;text-align:left}
.missed-hdr{font-size:.6rem;text-transform:uppercase;letter-spacing:1px;color:var(--rd);font-weight:900;margin-bottom:6px}
.missed-row{display:flex;justify-content:space-between;padding:3px 0;border-bottom:1px solid rgba(255,255,255,.04);font-size:.78rem}
.missed-row:last-child{border-bottom:none}
.pfab{position:fixed;bottom:calc(72px + env(safe-area-inset-bottom,0px));right:14px;width:54px;height:54px;background:linear-gradient(135deg,#1a1200,#2d2000);border:2px solid var(--ai);border-radius:50%;cursor:pointer;z-index:300;display:none;align-items:center;justify-content:center;box-shadow:0 6px 24px rgba(245,158,11,.4)}
.pfab.show{display:flex}
.pfab-dot{position:absolute;top:-2px;right:-2px;width:14px;height:14px;border-radius:50%;background:var(--rd);color:#fff;font-size:.5rem;font-weight:900;display:none;align-items:center;justify-content:center;border:2px solid var(--bg)}
.pfab-dot.show{display:flex}
.pchat{position:fixed;bottom:calc(136px + env(safe-area-inset-bottom,0px));right:10px;width:min(330px,calc(100vw - 20px));height:min(450px,calc(100vh - 180px));background:#0a0a0f;border:1.5px solid rgba(245,158,11,.25);border-radius:20px;box-shadow:0 20px 60px rgba(0,0,0,.95);z-index:299;display:flex;flex-direction:column;overflow:hidden;transform:scale(.85) translateY(20px);opacity:0;pointer-events:none;transform-origin:bottom right;transition:transform .25s cubic-bezier(.34,1.3,.64,1),opacity .2s}
.pchat.open{transform:scale(1) translateY(0);opacity:1;pointer-events:all}
.pc-hdr{background:linear-gradient(135deg,#0f0f1a,#1a1200);border-bottom:1px solid rgba(245,158,11,.15);padding:12px 14px;display:flex;align-items:center;gap:10px;flex-shrink:0}
.pc-logo-wrap{width:34px;height:34px;background:rgba(245,158,11,.1);border:1.5px solid rgba(245,158,11,.3);border-radius:10px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.pc-nm{font-size:.9rem;font-weight:900;color:var(--ai2)}
.pc-st{font-size:.6rem;color:rgba(245,158,11,.5);display:flex;align-items:center;gap:4px;margin-top:1px}
.sdot{width:6px;height:6px;background:var(--gr);border-radius:50%;animation:blink 2s ease-in-out infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.3}}
.pc-cls{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.08);color:rgba(255,255,255,.4);width:26px;height:26px;border-radius:50%;cursor:pointer;font-size:.8rem;display:flex;align-items:center;justify-content:center;margin-left:auto}
.pc-prog{background:rgba(245,158,11,.06);border-bottom:1px solid rgba(245,158,11,.1);padding:8px 14px;flex-shrink:0;display:none}
.pc-prog.show{display:block}
.ppb-row{display:flex;justify-content:space-between;align-items:center;margin-bottom:4px}
.ppb-label{font-size:.6rem;text-transform:uppercase;letter-spacing:.8px;color:var(--ai2);font-weight:900}
.ppb-val{font-size:.6rem;color:var(--tx2);font-weight:700}
.ppb-bar{height:4px;background:rgba(245,158,11,.1);border-radius:99px;overflow:hidden}
.ppb-fill{height:100%;border-radius:99px;background:linear-gradient(90deg,var(--ai),var(--ai2));transition:width .6s ease}
.pc-chips{padding:8px 10px 4px;display:flex;gap:6px;flex-wrap:wrap;flex-shrink:0;border-bottom:1px solid rgba(255,255,255,.04)}
.pc-chip{background:rgba(245,158,11,.07);border:1px solid rgba(245,158,11,.15);color:var(--ai2);font-size:.62rem;font-weight:800;padding:5px 10px;border-radius:99px;cursor:pointer;white-space:nowrap;min-height:28px;display:flex;align-items:center}
.pc-msgs{flex:1;overflow-y:auto;padding:10px 12px;display:flex;flex-direction:column;gap:8px}
.pc-msg{max-width:88%;display:flex;flex-direction:column;gap:2px}
.pc-msg.ai{align-self:flex-start}.pc-msg.usr{align-self:flex-end}
.pc-mb{padding:9px 12px;border-radius:14px;font-size:.8rem;line-height:1.6}
.pc-msg.ai .pc-mb{background:#161620;border:1px solid rgba(245,158,11,.1);border-bottom-left-radius:4px;color:var(--tx)}
.pc-msg.usr .pc-mb{background:linear-gradient(135deg,#b36a00,#f59e0b);color:#000;font-weight:700;border-bottom-right-radius:4px}
.pc-mt{font-size:.52rem;color:#333;padding:0 4px}.pc-msg.usr .pc-mt{text-align:right}
.pc-inp-row{padding:8px 10px;border-top:1px solid rgba(245,158,11,.08);display:flex;gap:6px;align-items:flex-end;flex-shrink:0;background:#0a0a0f}
.pc-inp{flex:1;background:#141418;border:1px solid rgba(245,158,11,.12);border-radius:12px;color:var(--tx);font-size:.82rem;padding:9px 12px;outline:none;resize:none;max-height:70px;font-family:var(--F);line-height:1.5}
.pc-inp:focus{border-color:var(--ai)}
.pc-send{width:36px;height:36px;flex-shrink:0;background:linear-gradient(135deg,#c27a00,#f59e0b);border:none;border-radius:10px;color:#000;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:.9rem;font-weight:900}
.prof-sec{padding:16px 14px}
.prof-hdr{text-align:center;margin-bottom:18px}
.prof-av-big{width:74px;height:74px;border-radius:50%;background:linear-gradient(135deg,var(--bl),var(--pu));display:flex;align-items:center;justify-content:center;font-size:2.2rem;margin:0 auto 8px;border:2.5px solid var(--bd2);cursor:pointer}
.prof-nm{font-size:1.25rem;font-weight:900}
.prof-sub{font-size:.72rem;color:var(--tx2);margin-top:2px}
.sg{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:16px}
.sb{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:12px;text-align:center}
.sv{font-size:1.3rem;font-weight:900}
.sl{font-size:.56rem;text-transform:uppercase;letter-spacing:.7px;color:var(--tx2);margin-top:2px}
.divider{height:1px;background:var(--bd);margin:14px 0}
.acc-row{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:12px 14px;display:flex;align-items:center;justify-content:space-between;margin-bottom:8px}
.acc-nm{font-size:.84rem;font-weight:800}
.acc-ds{font-size:.66rem;color:var(--tx2);margin-top:2px}
.tog{width:46px;height:26px;background:var(--s2);border:1.5px solid var(--bd);border-radius:99px;cursor:pointer;position:relative;transition:background .2s;flex-shrink:0}
.tog.on{background:var(--gr);border-color:var(--g2)}
.tog::after{content:'';position:absolute;top:3px;left:3px;width:16px;height:16px;border-radius:50%;background:#fff;transition:transform .2s}
.tog.on::after{transform:translateX(20px)}
.bdg-wrap{display:flex;flex-wrap:wrap;gap:7px}
.bdg{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--r);width:48px;height:48px;display:flex;align-items:center;justify-content:center;font-size:1.4rem}
.bdg.lck{opacity:.25;filter:grayscale(1)}
.lang-selector-row{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--R);padding:12px 14px;margin-bottom:8px}
.lang-opts{display:flex;gap:8px;margin-top:8px}
.lang-opt-btn{flex:1;background:var(--s2);border:2px solid var(--bd);border-radius:var(--r);padding:8px;cursor:pointer;text-align:center;font-family:var(--F);font-size:.72rem;font-weight:900;color:var(--tx)}
.lang-opt-btn.on{border-color:var(--bl);background:rgba(28,176,246,.07);color:var(--bl)}
.pg-ta{background:#080f17;color:#e6edf3;font-family:'Courier New',monospace;font-size:.82rem;line-height:1.7;padding:12px;border:none;outline:none;resize:none;width:100%;min-height:180px;tab-size:4}
.pg-snips{display:grid;grid-template-columns:1fr 1fr;gap:7px;margin-top:10px}
.snip{background:var(--s1);border:1.5px solid var(--bd);border-radius:var(--r);padding:10px 11px;cursor:pointer;min-height:48px}
.snip-nm{font-size:.73rem;font-weight:800;margin-bottom:2px;color:var(--bl)}
.snip-ds{font-size:.62rem;color:var(--tx2)}
.pg-btns{display:flex;gap:8px;margin-top:8px}
.pg-run{flex:1;background:var(--gr);border:none;border-bottom:3px solid var(--g2);border-radius:var(--r);color:#fff;font-family:var(--F);font-size:.85rem;font-weight:900;padding:10px;cursor:pointer;min-height:44px}
.pg-clear{background:var(--s2);border:1.5px solid var(--bd);border-radius:var(--r);color:var(--tx2);font-family:var(--F);font-size:.82rem;font-weight:800;padding:10px 13px;cursor:pointer;min-height:44px}
.toast{position:fixed;bottom:calc(82px + env(safe-area-inset-bottom,0px));left:50%;transform:translateX(-50%) translateY(16px);background:var(--s1);border:1.5px solid var(--bd);border-radius:99px;padding:9px 18px;font-size:.78rem;font-weight:800;z-index:700;opacity:0;transition:all .3s;pointer-events:none;white-space:nowrap;max-width:calc(100vw - 28px);text-align:center}
.toast.on{opacity:1;transform:translateX(-50%) translateY(0)}
.cf-wrap{position:fixed;inset:0;pointer-events:none;z-index:600;overflow:hidden}
.cf{position:absolute;animation:cfFall linear forwards}
@keyframes cfFall{to{transform:translateY(110vh) rotate(720deg);opacity:0}}
@keyframes pop{from{transform:scale(.6);opacity:0}to{transform:scale(1);opacity:1}}
@keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-5px)}75%{transform:translateX(5px)}}
.tgame-wrap{display:flex;flex-direction:column;gap:10px}
</style>
</head>
<body>
<div class="cf-wrap" id="cfWrap"></div>
<div class="toast" id="toast"></div>

<!-- ONBOARDING -->

<div class="scr on" id="sOb">
  <div class="ob-wrap">
    <div class="logo">Tabu<span>X</span>ada</div>
    <p class="ob-sub" id="obSubTxt">Aprenda matemática, programação e idiomas ⚡</p>
    <div class="ob-card">
      <div class="lbl">Idioma / Language / Sprache</div>
      <div class="lang-grid">
        <div class="lang-btn on" onclick="obLang(this,'pt')"><div class="lei">🇧🇷</div><div class="lnm">Português</div></div>
        <div class="lang-btn" onclick="obLang(this,'en')"><div class="lei">🇺🇸</div><div class="lnm">English</div></div>
        <div class="lang-btn" onclick="obLang(this,'de')"><div class="lei">🇩🇪</div><div class="lnm">Deutsch</div></div>
      </div>
      <div class="lbl" id="lblName">Seu nome</div>
      <input class="inp" id="obName" type="text" placeholder="..." maxlength="20" oninput="obChk()">
      <div class="lbl" id="lblAge">Sua faixa de idade</div>
      <div class="sel-grid" id="ageGrid">
        <div class="sel-btn" onclick="obAge(this,'6-10')"><div class="ei">🌱</div><div class="nm">6–10</div><div class="sb" id="age1sb">Básico</div></div>
        <div class="sel-btn" onclick="obAge(this,'11-14')"><div class="ei">⚡</div><div class="nm">11–14</div><div class="sb" id="age2sb">Médio</div></div>
        <div class="sel-btn" onclick="obAge(this,'15-18')"><div class="ei">🔥</div><div class="nm">15–18</div><div class="sb" id="age3sb">Avançado</div></div>
        <div class="sel-btn" onclick="obAge(this,'adult')"><div class="ei">🏆</div><div class="nm">Adulto</div><div class="sb" id="age4sb">Expert</div></div>
      </div>
      <button class="btn-main" id="obBtn" disabled onclick="startApp()">Começar →</button>
    </div>
  </div>
</div>

<!-- APP -->

<div class="scr" id="sApp">
  <div class="topbar">
    <div class="av" id="topAv" onclick="openEditProfile()">😊</div>
    <div class="uname" id="topNm"></div>
    <div class="stat-pill hrt" onclick="openHeartsShop()">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 21.593c-5.63-5.539-11-10.297-11-14.402 0-3.791 3.068-5.191 5.281-5.191 1.312 0 4.151.501 5.719 4.457 1.59-3.968 4.464-4.447 5.726-4.447 2.54 0 5.274 1.621 5.274 5.181 0 4.069-5.136 8.625-11 14.402z"/></svg>
      <span id="spHrt">5</span>
    </div>
    <div class="stat-pill gem">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M6 2l-6 8 12 12 12-12-6-8z"/></svg>
      <span id="spGem">100</span>
    </div>
    <div class="stat-pill xp">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
      <span id="spXp">0</span>
    </div>
  </div>
  <div class="scroll-main">
    <div class="tab on" id="tabHome"></div>
    <div class="tab" id="tabMap"></div>
    <div class="tab" id="tabPg"></div>
    <div class="tab" id="tabProf"></div>
  </div>
  <div class="bot-nav">
    <button class="nb on" id="nbHome" onclick="navTo('home')">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M10 20v-6h4v6h5v-8h3L12 3 2 12h3v8z"/></svg>
      <span id="nbHomeTxt">Início</span>
    </button>
    <button class="nb" id="nbPg" onclick="navTo('pg')">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9.4 16.6L4.8 12l4.6-4.6L8 6l-6 6 6 6 1.4-1.4zm5.2 0l4.6-4.6-4.6-4.6L16 6l6 6-6 6-1.4-1.4z"/></svg>
      <span id="nbPgTxt">Código</span>
    </button>
    <button class="nb" id="nbProf" onclick="navTo('prof')">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>
      <span id="nbProfTxt">Perfil</span>
    </button>
  </div>
</div>

<!-- TABU -->

<div class="scr" id="sTabu">
  <div class="tabu-shell">
    <div class="tabu-hdr">
      <button class="les-close" onclick="goBack()">✕</button>
      <span style="font-weight:900;font-size:.9rem;flex:1" id="tabuHdrTtl">TabuXada</span>
    </div>
    <div class="tabu-body" id="tabuBody"></div>
  </div>
</div>

<!-- LESSON -->

<div class="scr" id="sLesson">
  <div class="les-shell">
    <div class="les-hdr">
      <button class="les-close" onclick="goBack()">✕</button>
      <div class="les-pw"><div class="les-pf" id="lesProg" style="width:0%"></div></div>
      <div class="les-hts" id="lesHts"></div>
    </div>
    <div class="les-body" id="lesBody"></div>
    <div class="les-foot" id="lesFoot"></div>
  </div>
</div>

<!-- Hearts modal (dynamic) -->

<div class="modal-ov" id="heartsModal"></div>

<!-- Edit profile modal -->

<div class="modal-ov" id="editModal">
  <div class="modal-sheet" onclick="event.stopPropagation()">
    <div class="modal-ttl" id="editModalTtl">✏️ Editar Perfil</div>
    <div class="lbl" id="editNameLbl">Nome</div>
    <input class="inp" id="editNameInp" type="text" maxlength="20" style="margin-bottom:14px">
    <div class="lbl" id="editAvatarLbl">Avatar</div>
    <div class="avatar-grid" id="avGrid"></div>
    <div class="modal-btns">
      <button class="btn-cancel" id="editCancelBtn" onclick="document.getElementById('editModal').classList.remove('on')">Cancelar</button>
      <button class="btn-save" id="editSaveBtn" onclick="saveProfile()">Salvar ✓</button>
    </div>
  </div>
</div>

<div class="win-ov" id="winModal">
  <div class="win-card">
    <div class="win-em" id="winEm">🎉</div>
    <div class="win-ttl" id="winTtl"></div>
    <div class="win-sub" id="winSub"></div>
    <div class="win-rewards" id="winRw"></div>
    <button class="btn-main" onclick="closeWin()">Continuar →</button>
  </div>
</div>
<div class="win-ov" id="chestModal">
  <div class="chest-win" id="chestWinInner"></div>
</div>

<!-- POWER AI -->

<button class="pfab" id="pfab" onclick="toggleChat()">
  <svg width="24" height="24" viewBox="0 0 24 24"><path d="M13 2L4.5 13.5H11.5L11 22L19.5 10.5H12.5L13 2Z" fill="#f59e0b"/></svg>
  <div class="pfab-dot" id="pfabDot"></div>
</button>
<div class="pchat" id="pchat">
  <div class="pc-hdr">
    <div class="pc-logo-wrap"><svg width="16" height="16" viewBox="0 0 24 24"><path d="M13 2L4.5 13.5H11.5L11 22L19.5 10.5H12.5L13 2Z" fill="#fbbf24"/></svg></div>
    <div style="flex:1"><div class="pc-nm">Power AI</div><div class="pc-st"><div class="sdot"></div><span id="pcStTxt">Coach</span></div></div>
    <div class="pc-cls" onclick="toggleChat()">✕</div>
  </div>
  <div class="pc-prog" id="pcProg">
    <div class="ppb-row"><span class="ppb-label">Progresso</span><span class="ppb-val" id="ppbVal">0%</span></div>
    <div class="ppb-bar"><div class="ppb-fill" id="ppbFill" style="width:0%"></div></div>
  </div>
  <div class="pc-chips" id="pcChips"></div>
  <div class="pc-msgs" id="pcMsgs"></div>
  <div class="pc-inp-row">
    <textarea class="pc-inp" id="pcInp" placeholder="..." rows="1" onkeydown="if(event.key==='Enter'&&!event.shiftKey){event.preventDefault();pcSend()}" oninput="this.style.height='auto';this.style.height=Math.min(this.scrollHeight,70)+'px'"></textarea>
    <button class="pc-send" id="pcSendBtn" onclick="pcSend()">➤</button>
  </div>
</div>

<script>
'use strict';

// ══════════════════════════════════════════
// I18N
// ══════════════════════════════════════════
var TX={
pt:{tagline:'Aprenda matemática, programação e idiomas ⚡',start:'Começar →',yourName:'Seu nome',yourAge:'Sua faixa de idade',age1:'Básico',age2:'Médio',age3:'Avançado',age4:'Expert',home:'Início',code:'Código',profile:'Perfil',myCourses:'📚 Meus Cursos',reviewErrors:'🔁 Revisar Erros',lessons:'lições',complete:'completo',locked:'🔒 Complete a anterior!',next:'Próxima',math:'Matemática',mathDesc:'300 lições de matemática',python:'Python',pyDesc:'300 lições de Python',tabu:'TabuXada',tabuDesc:'Modo jogo — tabuada',lv:'Nível',unit:'Unidade',check:'Verificar',cont:'Continuar →',nxt:'Próxima →',gotIt:'Entendi! →',ok:'Correto! 🎉',almost:'Quase lá!',correctAns:'Resposta correta:',noHearts:'Sem vidas! Compre mais.',done:'Lição completa!',alreadyDone:'Já concluída!',tabuMath:'🔢 Matemática',tabuLang:'🌍 Idiomas',chooseMode:'🎮 Escolha o Modo',chooseLang:'🌍 Escolha o Idioma',result:'Resultado',playAgain:'🔄 Jogar de novo',chooseLevel:'← Modos',pts:'Pontos',qs:'Questões',hits:'Acertos',livs:'Vidas',acc:'Precisão',errs:'Erros',tout:'Tempo!',noTimer:'Sem timer',missed:'erros',back:'← Voltar',xp:'XP',gems:'Gemas',pgTitle:'💻 Playground Python',run:'▶ Executar',clr:'🗑 Limpar',exs:'📋 Exemplos',achievements:'🎖 Conquistas',accessibility:'♿ Acessibilidade',highContrast:'Alto Contraste',largeText:'Texto Grande',reduceAnim:'Reduzir Animações',appLang:'🌐 Idioma',cancel:'Cancelar',save:'Salvar ✓',updated:'✅ Perfil atualizado!',resetAll:'🗑 Reiniciar tudo',resetCourse:'🔄 Resetar este curso',notEnoughGems:'💎 Gemas insuficientes!',alreadyFull:'❤️ Já tens 5 vidas!',hvTitle:'Vidas',hvReset:'Recarrega à meia-noite',hvB1:'+ 1 Vida',hvB1ds:'Comprar uma vida agora',hvBF:'5 Vidas cheias',hvBFds:'Restaurar todas as 5 vidas',hvWait:'⏳ Esperar (grátis)',hvWaitDs:'Corações recarregam toda meia-noite',hvRev:'📝 Fazer lição de revisão',hvRevDs:'Complete para ganhar +1 ❤️',hvRevErr:' erros para revisar',hvWarn:'Errar não perde vida nesta lição',hvClose:'Fechar',hvFree:'Grátis',chestTitle:'💰 Baú de Gemas',chestCollect:'Coletar! 💎',aiOnline:'Coach · Offline inteligente',aiHow:'Como estou?',aiHint:'Dica rápida',aiWeak:'Minha fraqueza',aiProg:'Meu progresso',transLbl:'Tradução',
  conceptLabel:'Conceito',practiceLabel:'Prática',noOutput:'(sem saída)',runPrompt:'Pressione Executar...',heartRecovered:'Vida recuperada!',tabuResetted:'resetado!',
  editProfileTitle:'✏️ Editar Perfil',editName:'Nome',editAvatar:'Avatar',accApplied:'♿ Acessibilidade aplicada!',
  muArith:'Aritmética',muMul:'Multiplicação',muFrac:'Frações',muPct:'Porcentagem',muAlg:'Álgebra',muGeo:'Geometria',muStat:'Estatística',muSeq:'Sequências',muAdv:'Avançado',
  mtAdd:'Adição',mtSub:'Subtração',mtMul:'Tabuada',mtDiv:'Divisão',mtFrac:'Frações',mtDec:'Decimais',mtPct:'Porcentagem',mtAlg1:'Equação 1º Grau',mtAlg2:'Equação 2 termos',mtSys:'Sistemas',mtQuad:'Equação 2º Grau',mtGeo:'Área & Perímetro',mtPit:'Pitágoras',mtTrig:'Trigonometria',mtStat:'Média/Mediana',mtProb:'Probabilidade',mtSeq:'PA e PG',mtMat:'Matrizes',mtPoly:'Polinômios',
  puBasic:'Básico',puCond:'Condições',puLoops:'Loops',puLists:'Listas',puFunc:'Funções',puOop:'OOP',puAdv:'Avançado',puAlgo:'Algoritmos',
  luVocab:'Vocabulário',luGrammar:'Gramática',
  mAddT:'Adição',mAddB:'Adição: juntar quantidades!\na + b = c\n3 + 4 = 7',mAddTip:'Comece do maior e conte!',
  mSubT:'Subtração',mSubB:'Subtração: remover parte.\na − b = c\n10 − 4 = 6',mSubTip:'Subtração é o inverso da adição!',
  mMulT:'Tabuada',mMulB:'Multiplicação = adição repetida!\n3 × 4 = 12',mMulTip:'Truque do 9: 9×n = (n-1) dezenas e (10-n) unidades',
  mDivT:'Divisão',mDivB:'Divisão é o inverso da multiplicação!\n12 ÷ 4 = 3 pois 4×3=12',mDivTip:'Pense na multiplicação para resolver!',
  mFracT:'Frações',mFracB:'Frações = partes de um todo\n1/2 = metade, 1/4 = quarto',mFracTip:'Pense em pizza: 3/8 = 3 fatias de 8!',
  mDecT:'Decimais',mDecB:'Decimais = frações de 10\n0.5 = 5/10 = metade',mDecTip:'0.1 = décimo, 0.01 = centésimo!',
  mPctT:'Porcentagem',mPctB:'% = por cem\n25% de 80 = 80×0.25 = 20',mPctTip:'X% de Y = Y × (X/100)!',
  mAlg1T:'Equação 1º Grau',mAlg1B:'x + 5 = 12\nx = 12 − 5 = 7\nVerifique: 7+5=12 ✓',mAlg1Tip:'O que faz de um lado, faz do outro!',
  mAlg2T:'Equação com coef.',mAlg2B:'2x + 3 = 11\n2x = 8\nx = 4',mAlg2Tip:'Isole o x passo a passo!',
  mGeoT:'Geometria',mGeoB:'Retângulo:\nÁrea = base × altura\nPerímetro = 2×(b+h)',mGeoTip:'π ≈ 3.14 para círculos',
  mPitT:'Pitágoras',mPitB:'a² + b² = c²\n(c = hipotenusa)\n3²+4²=5² ✓',mPitTip:'Memorize: 3-4-5, 5-12-13, 8-15-17!',
  mTrigT:'Trigonometria',mTrigB:'sin=oposto/hipotenusa\ncos=adjacente/hipotenusa\ntan=oposto/adjacente',mTrigTip:'30°: sin=0.5, 45°: sin=cos=0.71',
  mStatT:'Estatística',mStatB:'Média = soma ÷ quantidade\nMediana = valor do meio\nModa = mais frequente',mStatTip:'Média é sensível a outliers!',
  mProbT:'Probabilidade',mProbB:'P = favoráveis ÷ possíveis\nDado: P(6) = 1/6',mProbTip:'P sempre entre 0 e 1!',
  mSeqT:'PA e PG',mSeqB:'PA: aₙ = a₁ + (n-1)×d\nPG: aₙ = a₁ × q^(n-1)',mSeqTip:'PA: diferença constante. PG: razão constante!',
  pyPrintT:'print()',pyPrintB:'print() exibe na tela!\nprint("Olá!")\nprint(42)\nprint(3+5)',pyPrintTip:'Textos precisam de aspas!',
  pyVarsT:'Variáveis',pyVarsB:'nome = "Ana"\nidade = 15\nprint(nome)',pyVarsTip:'Use nomes descritivos!',
  pyTypesT:'Tipos',pyTypesB:'str: "texto"\nint: 42\nfloat: 3.14\nbool: True/False',pyTypesTip:'type(x) mostra o tipo!',
  pyOpsT:'Operadores',pyOpsB:'+  -  *  /\n// inteiro\n%  resto\n** potência',pyOpsTip:'10//3=3; 10%3=1',
  pyInputT:'input()',pyInputB:'nome = input("Seu nome: ")\nprint("Olá,", nome)',pyInputTip:'input() sempre retorna string!',
  pyIfT:'if / else',pyIfB:'if condição:\n    # executar\nelse:\n    # senão',pyIfTip:'Indentação é obrigatória!',
  pyElifT:'elif',pyElifB:'if nota>=9: print("A")\nelif nota>=7: print("B")\nelse: print("C")',pyElifTip:'Múltiplas condições!',
  pyForT:'for + range()',pyForB:'for i in range(5):\n    print(i) # 0,1,2,3,4',pyForTip:'range(início,fim,passo)',
  pyWhileT:'while',pyWhileB:'while condição:\n    # repetir',pyWhileTip:'Evite loops infinitos!',
  pyListT:'Listas',pyListB:'nums=[1,2,3]\nnums[0] # 1\nlen(nums) # 3\nnums.append(4)',pyListTip:'Índices começam em 0!',
  pyDictT:'Dicionários',pyDictB:'p={"nome":"Ana"}\nprint(p["nome"]) # Ana',pyDictTip:'Busca rápida por chave!',
  pyTupT:'Tuplas/Sets',pyTupB:'t=(1,2,3) # imutável\ns={1,2,3} # sem duplicatas',pyTupTip:'Tuplas são mais rápidas!',
  pyFuncT:'Funções',pyFuncB:'def saudar(nome):\n    print("Olá,",nome)',pyFuncTip:'return devolve valor!',
  pyParT:'Parâmetros',pyParB:'def area(b,h):\n    return b*h\ndef pot(n,exp=2):\n    return n**exp',pyParTip:'Parâmetros padrão são opcionais!',
  pyLamT:'Lambda',pyLamB:'dobro = lambda x: x*2\nprint(dobro(5)) # 10',pyLamTip:'Funções anônimas de uma linha!',
  pyOopT:'Classes',pyOopB:'class Carro:\n    def __init__(self,m):\n        self.marca=m',pyOopTip:'__init__ é o construtor!',
  pyInhT:'Herança',pyInhB:'class Animal:\n    def falar(self): pass\nclass Cão(Animal):\n    def falar(self): print("Au!")',pyInhTip:'super() acessa a classe pai!',
  pyExcT:'try/except',pyExcB:'try:\n    op()\nexcept Erro:\n    print("Ops!")',pyExcTip:'Capture erros específicos!',
  pyCompT:'List Comprehension',pyCompB:'q=[x**2 for x in range(5)]\n# [0,1,4,9,16]',pyCompTip:'Mais Pythônico!',
  pyAlgoT:'Busca Binária',pyAlgoB:'O(log n) vs O(n)\nDivide a lista ao meio!',pyAlgoTip:'Requer lista ordenada!',
  pySortT:'Ordenação',pySortB:'lista.sort()\nsorted(lst)\nlista.sort(key=lambda x:x[0])',pySortTip:'Prefira o sort() embutido!',
  pyQ:{
    print:[{q:'O que print() faz?',opts:['Mostra na tela','Lê teclado','Cria variável','Apaga'],ans:'Mostra na tela'},{q:'print("Olá") mostra:',opts:['Olá','"Olá"','print','Erro'],ans:'Olá'},{q:'print(3+5) mostra:',opts:['8','3+5','35','Erro'],ans:'8'},{q:'Para texto usar:',opts:['Aspas','Parênteses','Colchetes','Ponto'],ans:'Aspas'},{q:'print(2*6) mostra:',opts:['12','2*6','8','Erro'],ans:'12'}],
    vars:[{q:'x = 5 é:',opts:['Atribuição','Comparação','Erro','Equação'],ans:'Atribuição'},{q:'x=5; print(x+3) →',opts:['8','x+3','5','3'],ans:'8'},{q:'Nome válido:',opts:['_nome','2var','minha var','def'],ans:'_nome'}],
    ifelse:[{q:'"if" significa:',opts:['Se/Condição','Enquanto','Para','Fazer'],ans:'Se/Condição'},{q:'Indentação Python:',opts:['Obrigatória','Opcional','Proibida','Irrelevante'],ans:'Obrigatória'},{q:'== significa:',opts:['Comparação','Atribuição','Diferente','Maior'],ans:'Comparação'}],
    forr:[{q:'range(5) gera:',opts:['0,1,2,3,4','1,2,3,4,5','0-5','1-4'],ans:'0,1,2,3,4'},{q:'range(2,5) gera:',opts:['2,3,4','2,3,4,5','1,2,3','0,1,2'],ans:'2,3,4'}],
    func:[{q:'"def" serve para:',opts:['Definir função','Definir variável','Importar','Loop'],ans:'Definir função'},{q:'def f(x): return x*2; f(5) →',opts:['10','5','25','Erro'],ans:'10'},{q:'Sem return retorna:',opts:['None','0','""','Erro'],ans:'None'}],
    list:[{q:'nums=[1,2,3]; nums[0] →',opts:['1','2','3','Erro'],ans:'1'},{q:'len([4,5,6]) →',opts:['3','6','0','Erro'],ans:'3'},{q:'Último elemento:',opts:['lista[-1]','lista[last]','lista[fim]','lista[0]'],ans:'lista[-1]'}],
    default:[{q:'Python é uma linguagem?',opts:['Sim','Não','Talvez','Nunca'],ans:'Sim'}]
  },
  langs:{en:{name:'Inglês',desc:'300 lições A1→B2',flag:'🇺🇸'},fr:{name:'Francês',desc:'300 lições A1→B2',flag:'🇫🇷'},it:{name:'Italiano',desc:'300 lições A1→B2',flag:'🇮🇹'},de:{name:'Alemão',desc:'300 lições A1→B2',flag:'🇩🇪'},es:{name:'Espanhol',desc:'300 lições A1→B2',flag:'🇪🇸'}}},

en:{tagline:'Learn math, coding and languages ⚡',start:'Start →',yourName:'Your name',yourAge:'Your age range',age1:'Elementary',age2:'Middle School',age3:'High School',age4:'Advanced',home:'Home',code:'Code',profile:'Profile',myCourses:'📚 My Courses',reviewErrors:'🔁 Review Errors',lessons:'lessons',complete:'complete',locked:'🔒 Complete the previous one!',next:'Next',math:'Mathematics',mathDesc:'300 math lessons',python:'Python',pyDesc:'300 Python lessons',tabu:'TabuXada',tabuDesc:'Game mode — tables',lv:'Level',unit:'Unit',check:'Check',cont:'Continue →',nxt:'Next →',gotIt:'Got it! →',ok:'Correct! 🎉',almost:'Almost!',correctAns:'Correct answer:',noHearts:'No lives! Buy more.',done:'Lesson complete!',alreadyDone:'Already done!',tabuMath:'🔢 Math',tabuLang:'🌍 Languages',chooseMode:'🎮 Choose Mode',chooseLang:'🌍 Choose Language',result:'Result',playAgain:'🔄 Play again',chooseLevel:'← Modes',pts:'Points',qs:'Questions',hits:'Correct',livs:'Lives',acc:'Accuracy',errs:'Errors',tout:'Time up!',noTimer:'No timer',missed:'errors',back:'← Back',xp:'XP',gems:'Gems',pgTitle:'💻 Python Playground',run:'▶ Run',clr:'🗑 Clear',exs:'📋 Examples',achievements:'🎖 Achievements',accessibility:'♿ Accessibility',highContrast:'High Contrast',largeText:'Large Text',reduceAnim:'Reduce Animations',appLang:'🌐 Language',cancel:'Cancel',save:'Save ✓',updated:'✅ Profile updated!',resetAll:'🗑 Reset all',resetCourse:'🔄 Reset this course',notEnoughGems:'💎 Not enough gems!',alreadyFull:'❤️ Already at 5 lives!',hvTitle:'Lives',hvReset:'Refills at midnight',hvB1:'+1 Life',hvB1ds:'Buy one life now',hvBF:'Full Lives',hvBFds:'Restore all 5 lives',hvWait:'⏳ Wait (free)',hvWaitDs:'Hearts refill every night at midnight',hvRev:'📝 Review lesson',hvRevDs:'Complete to earn +1 ❤️',hvRevErr:' errors to review',hvWarn:'Mistakes do not cost lives here',hvClose:'Close',hvFree:'Free',chestTitle:'💰 Gem Chest',chestCollect:'Collect! 💎',aiOnline:'Coach · Smart Offline',aiHow:'How am I doing?',aiHint:'Quick tip',aiWeak:'My weakness',aiProg:'My progress',transLbl:'Translation',
  conceptLabel:'Concept',practiceLabel:'Practice',noOutput:'(no output)',runPrompt:'Press Run...',heartRecovered:'Life recovered!',tabuResetted:'reset!',
  editProfileTitle:'✏️ Edit Profile',editName:'Name',editAvatar:'Avatar',accApplied:'♿ Accessibility applied!',
  muArith:'Arithmetic',muMul:'Multiplication',muFrac:'Fractions',muPct:'Percentage',muAlg:'Algebra',muGeo:'Geometry',muStat:'Statistics',muSeq:'Sequences',muAdv:'Advanced',
  mtAdd:'Addition',mtSub:'Subtraction',mtMul:'Times Tables',mtDiv:'Division',mtFrac:'Fractions',mtDec:'Decimals',mtPct:'Percentage',mtAlg1:'1st Degree Eq.',mtAlg2:'2-term Eq.',mtSys:'Systems',mtQuad:'2nd Degree Eq.',mtGeo:'Area & Perimeter',mtPit:'Pythagoras',mtTrig:'Trigonometry',mtStat:'Mean/Median',mtProb:'Probability',mtSeq:'AP and GP',mtMat:'Matrices',mtPoly:'Polynomials',
  puBasic:'Basics',puCond:'Conditions',puLoops:'Loops',puLists:'Lists',puFunc:'Functions',puOop:'OOP',puAdv:'Advanced',puAlgo:'Algorithms',
  luVocab:'Vocabulary',luGrammar:'Grammar',
  mAddT:'Addition',mAddB:'Addition: join quantities!\na + b = c\n3 + 4 = 7',mAddTip:'Start from the larger and count!',
  mSubT:'Subtraction',mSubB:'Subtraction: remove part.\na − b = c\n10 − 4 = 6',mSubTip:'Subtraction is the inverse of addition!',
  mMulT:'Times Tables',mMulB:'Multiplication = repeated addition!\n3 × 4 = 12',mMulTip:'Trick for 9: 9×n = (n-1) tens and (10-n) units',
  mDivT:'Division',mDivB:'Division is the inverse of multiplication!\n12 ÷ 4 = 3 because 4×3=12',mDivTip:'Think of multiplication to solve it!',
  mFracT:'Fractions',mFracB:'Fractions = parts of a whole\n1/2 = half, 1/4 = quarter',mFracTip:'Think of pizza: 3/8 = 3 slices of 8!',
  mDecT:'Decimals',mDecB:'Decimals = fractions of 10\n0.5 = 5/10 = half',mDecTip:'0.1 = tenth, 0.01 = hundredth!',
  mPctT:'Percentage',mPctB:'% = per hundred\n25% of 80 = 80×0.25 = 20',mPctTip:'X% of Y = Y × (X/100)!',
  mAlg1T:'1st Degree Equation',mAlg1B:'x + 5 = 12\nx = 12 − 5 = 7\nCheck: 7+5=12 ✓',mAlg1Tip:'What you do to one side, do to the other!',
  mAlg2T:'Equation with coefficient',mAlg2B:'2x + 3 = 11\n2x = 8\nx = 4',mAlg2Tip:'Isolate x step by step!',
  mGeoT:'Geometry',mGeoB:'Rectangle:\nArea = base × height\nPerimeter = 2×(b+h)',mGeoTip:'π ≈ 3.14 for circles',
  mPitT:'Pythagoras',mPitB:'a² + b² = c²\n(c = hypotenuse)\n3²+4²=5² ✓',mPitTip:'Memorise: 3-4-5, 5-12-13, 8-15-17!',
  mTrigT:'Trigonometry',mTrigB:'sin=opposite/hypotenuse\ncos=adjacent/hypotenuse\ntan=opposite/adjacent',mTrigTip:'30°: sin=0.5, 45°: sin=cos=0.71',
  mStatT:'Statistics',mStatB:'Mean = sum ÷ count\nMedian = middle value\nMode = most frequent',mStatTip:'Mean is sensitive to outliers!',
  mProbT:'Probability',mProbB:'P = favourable ÷ possible\nDie: P(6) = 1/6',mProbTip:'P always between 0 and 1!',
  mSeqT:'AP and GP',mSeqB:'AP: aₙ = a₁ + (n-1)×d\nGP: aₙ = a₁ × q^(n-1)',mSeqTip:'AP: constant difference. GP: constant ratio!',
  pyPrintT:'print()',pyPrintB:'print() displays on screen!\nprint("Hello!")\nprint(42)\nprint(3+5)',pyPrintTip:'Strings need quotes!',
  pyVarsT:'Variables',pyVarsB:'name = "Ana"\nage = 15\nprint(name)',pyVarsTip:'Use descriptive names!',
  pyTypesT:'Types',pyTypesB:'str: "text"\nint: 42\nfloat: 3.14\nbool: True/False',pyTypesTip:'type(x) shows the type!',
  pyOpsT:'Operators',pyOpsB:'+  -  *  /\n// integer\n%  remainder\n** power',pyOpsTip:'10//3=3; 10%3=1',
  pyInputT:'input()',pyInputB:'name = input("Your name: ")\nprint("Hello,", name)',pyInputTip:'input() always returns string!',
  pyIfT:'if / else',pyIfB:'if condition:\n    # run\nelse:\n    # otherwise',pyIfTip:'Indentation is mandatory!',
  pyElifT:'elif',pyElifB:'if grade>=9: print("A")\nelif grade>=7: print("B")\nelse: print("C")',pyElifTip:'Multiple conditions!',
  pyForT:'for + range()',pyForB:'for i in range(5):\n    print(i) # 0,1,2,3,4',pyForTip:'range(start,end,step)',
  pyWhileT:'while',pyWhileB:'while condition:\n    # repeat',pyWhileTip:'Avoid infinite loops!',
  pyListT:'Lists',pyListB:'nums=[1,2,3]\nnums[0] # 1\nlen(nums) # 3\nnums.append(4)',pyListTip:'Indices start at 0!',
  pyDictT:'Dictionaries',pyDictB:'p={"name":"Ana"}\nprint(p["name"]) # Ana',pyDictTip:'Fast lookup by key!',
  pyTupT:'Tuples/Sets',pyTupB:'t=(1,2,3) # immutable\ns={1,2,3} # no duplicates',pyTupTip:'Tuples are faster!',
  pyFuncT:'Functions',pyFuncB:'def greet(name):\n    print("Hello,",name)',pyFuncTip:'return gives back a value!',
  pyParT:'Parameters',pyParB:'def area(b,h):\n    return b*h\ndef pow(n,exp=2):\n    return n**exp',pyParTip:'Default parameters are optional!',
  pyLamT:'Lambda',pyLamB:'double = lambda x: x*2\nprint(double(5)) # 10',pyLamTip:'Anonymous one-line functions!',
  pyOopT:'Classes',pyOopB:'class Car:\n    def __init__(self,m):\n        self.brand=m',pyOopTip:'__init__ is the constructor!',
  pyInhT:'Inheritance',pyInhB:'class Animal:\n    def speak(self): pass\nclass Dog(Animal):\n    def speak(self): print("Woof!")',pyInhTip:'super() accesses the parent class!',
  pyExcT:'try/except',pyExcB:'try:\n    op()\nexcept Error:\n    print("Oops!")',pyExcTip:'Catch specific errors!',
  pyCompT:'List Comprehension',pyCompB:'q=[x**2 for x in range(5)]\n# [0,1,4,9,16]',pyCompTip:'More Pythonic!',
  pyAlgoT:'Binary Search',pyAlgoB:'O(log n) vs O(n)\nDivides the list in half!',pyAlgoTip:'Requires sorted list!',
  pySortT:'Sorting',pySortB:'list.sort()\nsorted(lst)\nlist.sort(key=lambda x:x[0])',pySortTip:'Prefer the built-in sort()!',
  pyQ:{
    print:[{q:'What does print() do?',opts:['Shows on screen','Reads keyboard','Creates variable','Deletes'],ans:'Shows on screen'},{q:'print("Hi") shows:',opts:['Hi','"Hi"','print','Error'],ans:'Hi'},{q:'print(3+5) shows:',opts:['8','3+5','35','Error'],ans:'8'},{q:'For text use:',opts:['Quotes','Parentheses','Brackets','Period'],ans:'Quotes'}],
    vars:[{q:'x = 5 is:',opts:['Assignment','Comparison','Error','Equation'],ans:'Assignment'},{q:'x=5; print(x+3) →',opts:['8','x+3','5','3'],ans:'8'},{q:'Valid name:',opts:['_name','2var','my var','def'],ans:'_name'}],
    ifelse:[{q:'"if" means:',opts:['If/Condition','While','For','Do'],ans:'If/Condition'},{q:'Python indentation:',opts:['Mandatory','Optional','Forbidden','Irrelevant'],ans:'Mandatory'},{q:'== means:',opts:['Comparison','Assignment','Different','Greater'],ans:'Comparison'}],
    forr:[{q:'range(5) generates:',opts:['0,1,2,3,4','1,2,3,4,5','0-5','1-4'],ans:'0,1,2,3,4'},{q:'range(2,5) generates:',opts:['2,3,4','2,3,4,5','1,2,3','0,1,2'],ans:'2,3,4'}],
    func:[{q:'"def" is used to:',opts:['Define function','Define variable','Import','Loop'],ans:'Define function'},{q:'def f(x): return x*2; f(5) →',opts:['10','5','25','Error'],ans:'10'},{q:'Without return gives:',opts:['None','0','""','Error'],ans:'None'}],
    list:[{q:'nums=[1,2,3]; nums[0] →',opts:['1','2','3','Error'],ans:'1'},{q:'len([4,5,6]) →',opts:['3','6','0','Error'],ans:'3'},{q:'Last element:',opts:['list[-1]','list[last]','list[end]','list[0]'],ans:'list[-1]'}],
    default:[{q:'Is Python a language?',opts:['Yes','No','Maybe','Never'],ans:'Yes'}]
  },
  langs:{fr:{name:'French',desc:'300 lessons A1→B2',flag:'🇫🇷'},it:{name:'Italian',desc:'300 lessons A1→B2',flag:'🇮🇹'},de:{name:'German',desc:'300 lessons A1→B2',flag:'🇩🇪'},es:{name:'Spanish',desc:'300 lessons A1→B2',flag:'🇪🇸'},pt:{name:'Portuguese',desc:'300 lessons A1→B2',flag:'🇧🇷'}}},

de:{tagline:'Lerne Mathe, Programmieren und Sprachen ⚡',start:'Beginnen →',yourName:'Dein Name',yourAge:'Deine Altersgruppe',age1:'Grundschule',age2:'Mittelschule',age3:'Oberschule',age4:'Fortgeschritten',home:'Start',code:'Code',profile:'Profil',myCourses:'📚 Meine Kurse',reviewErrors:'🔁 Fehler wiederholen',lessons:'Lektionen',complete:'abgeschl.',locked:'🔒 Vorherige abschließen!',next:'Nächste',math:'Mathematik',mathDesc:'300 Mathematik-Lektionen',python:'Python',pyDesc:'300 Python-Lektionen',tabu:'TabuXada',tabuDesc:'Spielmodus — Einmaleins',lv:'Niveau',unit:'Einheit',check:'Prüfen',cont:'Weiter →',nxt:'Nächste →',gotIt:'Verstanden! →',ok:'Richtig! 🎉',almost:'Fast!',correctAns:'Richtige Antwort:',noHearts:'Keine Leben! Kaufe mehr.',done:'Lektion abgeschlossen!',alreadyDone:'Bereits abgeschlossen!',tabuMath:'🔢 Mathematik',tabuLang:'🌍 Sprachen',chooseMode:'🎮 Modus wählen',chooseLang:'🌍 Sprache wählen',result:'Ergebnis',playAgain:'🔄 Nochmal',chooseLevel:'← Modi',pts:'Punkte',qs:'Fragen',hits:'Richtig',livs:'Leben',acc:'Genauigkeit',errs:'Fehler',tout:'Zeit!',noTimer:'Kein Timer',missed:'Fehler',back:'← Zurück',xp:'EP',gems:'Edelsteine',pgTitle:'💻 Python Playground',run:'▶ Ausführen',clr:'🗑 Löschen',exs:'📋 Beispiele',achievements:'🎖 Erfolge',accessibility:'♿ Barrierefreiheit',highContrast:'Hoher Kontrast',largeText:'Großer Text',reduceAnim:'Animationen reduzieren',appLang:'🌐 Sprache',cancel:'Abbrechen',save:'Speichern ✓',updated:'✅ Profil aktualisiert!',resetAll:'🗑 Alles zurücksetzen',resetCourse:'🔄 Kurs zurücksetzen',notEnoughGems:'💎 Zu wenig Edelsteine!',alreadyFull:'❤️ Bereits 5 Leben!',hvTitle:'Leben',hvReset:'Lädt um Mitternacht auf',hvB1:'+1 Leben',hvB1ds:'Jetzt ein Leben kaufen',hvBF:'Volle Leben',hvBFds:'Alle 5 Leben wiederherstellen',hvWait:'⏳ Warten (gratis)',hvWaitDs:'Herzen laden jede Nacht um Mitternacht auf',hvRev:'📝 Wiederholungslektion',hvRevDs:'Abschließen für +1 ❤️',hvRevErr:' Fehler zu wiederholen',hvWarn:'Fehler kosten hier keine Leben',hvClose:'Schließen',hvFree:'Gratis',chestTitle:'💰 Edelstein-Truhe',chestCollect:'Einsammeln! 💎',aiOnline:'Coach · Offline intelligent',aiHow:'Wie läuft es?',aiHint:'Schneller Tipp',aiWeak:'Meine Schwäche',aiProg:'Mein Fortschritt',transLbl:'Übersetzung',
  conceptLabel:'Konzept',practiceLabel:'Übung',noOutput:'(keine Ausgabe)',runPrompt:'Ausführen drücken...',heartRecovered:'Leben zurück!',tabuResetted:'zurückgesetzt!',
  editProfileTitle:'✏️ Profil bearbeiten',editName:'Name',editAvatar:'Avatar',accApplied:'♿ Barrierefreiheit angewendet!',
  muArith:'Arithmetik',muMul:'Multiplikation',muFrac:'Brüche',muPct:'Prozent',muAlg:'Algebra',muGeo:'Geometrie',muStat:'Statistik',muSeq:'Folgen',muAdv:'Fortgeschritten',
  mtAdd:'Addition',mtSub:'Subtraktion',mtMul:'Einmaleins',mtDiv:'Division',mtFrac:'Brüche',mtDec:'Dezimalzahlen',mtPct:'Prozent',mtAlg1:'Gleichung 1. Grades',mtAlg2:'2-Term-Gleichung',mtSys:'Systeme',mtQuad:'Gleichung 2. Grades',mtGeo:'Fläche & Umfang',mtPit:'Pythagoras',mtTrig:'Trigonometrie',mtStat:'Mittelwert/Median',mtProb:'Wahrscheinlichkeit',mtSeq:'AP und GP',mtMat:'Matrizen',mtPoly:'Polynome',
  puBasic:'Grundlagen',puCond:'Bedingungen',puLoops:'Schleifen',puLists:'Listen',puFunc:'Funktionen',puOop:'OOP',puAdv:'Fortgeschritten',puAlgo:'Algorithmen',
  luVocab:'Vokabeln',luGrammar:'Grammatik',
  mAddT:'Addition',mAddB:'Addition: Mengen zusammenfügen!\na + b = c\n3 + 4 = 7',mAddTip:'Beginne mit der größeren Zahl!',
  mSubT:'Subtraktion',mSubB:'Subtraktion: Teil entfernen.\na − b = c\n10 − 4 = 6',mSubTip:'Subtraktion ist die Umkehrung der Addition!',
  mMulT:'Einmaleins',mMulB:'Multiplikation = wiederholte Addition!\n3 × 4 = 12',mMulTip:'Trick für 9: 9×n = (n-1) Zehner und (10-n) Einer',
  mDivT:'Division',mDivB:'Division ist die Umkehrung der Multiplikation!\n12 ÷ 4 = 3 weil 4×3=12',mDivTip:'Denke an die Multiplikation!',
  mFracT:'Brüche',mFracB:'Brüche = Teile eines Ganzen\n1/2 = halb, 1/4 = viertel',mFracTip:'Denke an Pizza: 3/8 = 3 Stücke von 8!',
  mDecT:'Dezimalzahlen',mDecB:'Dezimal = Brüche von 10\n0.5 = 5/10 = halb',mDecTip:'0.1 = Zehntel, 0.01 = Hundertstel!',
  mPctT:'Prozent',mPctB:'% = pro hundert\n25% von 80 = 80×0.25 = 20',mPctTip:'X% von Y = Y × (X/100)!',
  mAlg1T:'Gleichung 1. Grades',mAlg1B:'x + 5 = 12\nx = 12 − 5 = 7\nProbe: 7+5=12 ✓',mAlg1Tip:'Was auf einer Seite, auch auf der anderen!',
  mAlg2T:'Gleichung mit Koeff.',mAlg2B:'2x + 3 = 11\n2x = 8\nx = 4',mAlg2Tip:'x Schritt für Schritt isolieren!',
  mGeoT:'Geometrie',mGeoB:'Rechteck:\nFläche = Basis × Höhe\nUmfang = 2×(b+h)',mGeoTip:'π ≈ 3.14 für Kreise',
  mPitT:'Pythagoras',mPitB:'a² + b² = c²\n(c = Hypotenuse)\n3²+4²=5² ✓',mPitTip:'Merke: 3-4-5, 5-12-13, 8-15-17!',
  mTrigT:'Trigonometrie',mTrigB:'sin=Gegenkathete/Hypotenuse\ncos=Ankathete/Hypotenuse\ntan=Gegenkathete/Ankathete',mTrigTip:'30°: sin=0.5, 45°: sin=cos=0.71',
  mStatT:'Statistik',mStatB:'Mittelwert = Summe ÷ Anzahl\nMedian = mittlerer Wert\nModus = häufigster Wert',mStatTip:'Mittelwert ist empfindlich gegenüber Ausreißern!',
  mProbT:'Wahrscheinlichkeit',mProbB:'P = günstig ÷ möglich\nWürfel: P(6) = 1/6',mProbTip:'P immer zwischen 0 und 1!',
  mSeqT:'AP und GP',mSeqB:'AP: aₙ = a₁ + (n-1)×d\nGP: aₙ = a₁ × q^(n-1)',mSeqTip:'AP: konstante Differenz. GP: konstantes Verhältnis!',
  pyPrintT:'print()',pyPrintB:'print() zeigt auf dem Bildschirm an!\nprint("Hallo!")\nprint(42)\nprint(3+5)',pyPrintTip:'Texte brauchen Anführungszeichen!',
  pyVarsT:'Variablen',pyVarsB:'name = "Ana"\nalter = 15\nprint(name)',pyVarsTip:'Beschreibende Namen verwenden!',
  pyTypesT:'Typen',pyTypesB:'str: "Text"\nint: 42\nfloat: 3.14\nbool: True/False',pyTypesTip:'type(x) zeigt den Typ!',
  pyOpsT:'Operatoren',pyOpsB:'+  -  *  /\n// ganzzahlig\n%  Rest\n** Potenz',pyOpsTip:'10//3=3; 10%3=1',
  pyInputT:'input()',pyInputB:'name = input("Dein Name: ")\nprint("Hallo,", name)',pyInputTip:'input() gibt immer String zurück!',
  pyIfT:'if / else',pyIfB:'if Bedingung:\n    # ausführen\nelse:\n    # sonst',pyIfTip:'Einrückung ist Pflicht!',
  pyElifT:'elif',pyElifB:'if note>=9: print("A")\nelif note>=7: print("B")\nelse: print("C")',pyElifTip:'Mehrere Bedingungen!',
  pyForT:'for + range()',pyForB:'for i in range(5):\n    print(i) # 0,1,2,3,4',pyForTip:'range(Anfang,Ende,Schritt)',
  pyWhileT:'while',pyWhileB:'while Bedingung:\n    # wiederholen',pyWhileTip:'Endlosschleifen vermeiden!',
  pyListT:'Listen',pyListB:'nums=[1,2,3]\nnums[0] # 1\nlen(nums) # 3\nnums.append(4)',pyListTip:'Indizes beginnen bei 0!',
  pyDictT:'Wörterbücher',pyDictB:'p={"name":"Ana"}\nprint(p["name"]) # Ana',pyDictTip:'Schneller Zugriff per Schlüssel!',
  pyTupT:'Tupel/Mengen',pyTupB:'t=(1,2,3) # unveränderlich\ns={1,2,3} # keine Duplikate',pyTupTip:'Tupel sind schneller!',
  pyFuncT:'Funktionen',pyFuncB:'def grüßen(name):\n    print("Hallo,",name)',pyFuncTip:'return gibt Wert zurück!',
  pyParT:'Parameter',pyParB:'def fläche(b,h):\n    return b*h\ndef pot(n,exp=2):\n    return n**exp',pyParTip:'Standardparameter sind optional!',
  pyLamT:'Lambda',pyLamB:'doppelt = lambda x: x*2\nprint(doppelt(5)) # 10',pyLamTip:'Anonyme Einzeiler-Funktionen!',
  pyOopT:'Klassen',pyOopB:'class Auto:\n    def __init__(self,m):\n        self.marke=m',pyOopTip:'__init__ ist der Konstruktor!',
  pyInhT:'Vererbung',pyInhB:'class Tier:\n    def sprechen(self): pass\nclass Hund(Tier):\n    def sprechen(self): print("Wau!")',pyInhTip:'super() greift auf Elternklasse zu!',
  pyExcT:'try/except',pyExcB:'try:\n    op()\nexcept Fehler:\n    print("Ups!")',pyExcTip:'Spezifische Fehler abfangen!',
  pyCompT:'List Comprehension',pyCompB:'q=[x**2 for x in range(5)]\n# [0,1,4,9,16]',pyCompTip:'Pythonischer Stil!',
  pyAlgoT:'Binäre Suche',pyAlgoB:'O(log n) vs O(n)\nTeilt die Liste in der Mitte!',pyAlgoTip:'Erfordert sortierte Liste!',
  pySortT:'Sortierung',pySortB:'liste.sort()\nsorted(lst)\nliste.sort(key=lambda x:x[0])',pySortTip:'Eingebautes sort() bevorzugen!',
  pyQ:{
    print:[{q:'Was macht print()?',opts:['Auf Bildschirm anzeigen','Tastatur lesen','Variable erstellen','Löschen'],ans:'Auf Bildschirm anzeigen'},{q:'print("Hallo") zeigt:',opts:['Hallo','"Hallo"','print','Fehler'],ans:'Hallo'},{q:'print(3+5) zeigt:',opts:['8','3+5','35','Fehler'],ans:'8'}],
    vars:[{q:'x = 5 ist:',opts:['Zuweisung','Vergleich','Fehler','Gleichung'],ans:'Zuweisung'},{q:'x=5; print(x+3) →',opts:['8','x+3','5','3'],ans:'8'}],
    ifelse:[{q:'"if" bedeutet:',opts:['Wenn/Bedingung','Während','Für','Tun'],ans:'Wenn/Bedingung'},{q:'Python Einrückung:',opts:['Pflicht','Optional','Verboten','Egal'],ans:'Pflicht'}],
    forr:[{q:'range(5) erzeugt:',opts:['0,1,2,3,4','1,2,3,4,5','0-5','1-4'],ans:'0,1,2,3,4'}],
    func:[{q:'"def" dient zum:',opts:['Funktion definieren','Variable definieren','Importieren','Schleifen'],ans:'Funktion definieren'},{q:'def f(x): return x*2; f(5) →',opts:['10','5','25','Fehler'],ans:'10'}],
    list:[{q:'nums=[1,2,3]; nums[0] →',opts:['1','2','3','Fehler'],ans:'1'},{q:'len([4,5,6]) →',opts:['3','6','0','Fehler'],ans:'3'}],
    default:[{q:'Ist Python eine Sprache?',opts:['Ja','Nein','Vielleicht','Nie'],ans:'Ja'}]
  },
  langs:{en:{name:'Englisch',desc:'300 Lektionen A1→B2',flag:'🇺🇸'},fr:{name:'Französisch',desc:'300 Lektionen A1→B2',flag:'🇫🇷'},it:{name:'Italienisch',desc:'300 Lektionen A1→B2',flag:'🇮🇹'},es:{name:'Spanisch',desc:'300 Lektionen A1→B2',flag:'🇪🇸'},pt:{name:'Portugiesisch',desc:'300 Lektionen A1→B2',flag:'🇧🇷'}}}
};
function T(k){var t=TX[P.lang]||TX.pt;return t[k]!==undefined?t[k]:(TX.pt[k]!==undefined?TX.pt[k]:k);}
function TL(tl){var t=TX[P.lang]||TX.pt;return(t.langs&&t.langs[tl])?t.langs[tl]:{name:tl,desc:'',flag:'🌍'};}

// ══════════════════════════════════════════
// VOCAB DB (abbreviated — same as before)
// ══════════════════════════════════════════
var VOCAB_DB={
  en:[
    {title:'Greetings',icon:'👋',words:[['Hello','Olá','Hi','Hallo'],['Good morning','Bom dia','Good morning','Guten Morgen'],['Goodbye','Tchau','Bye','Auf Wiedersehen'],['Please','Por favor','Please','Bitte'],['Thank you','Obrigado','Thanks','Danke'],['Sorry','Desculpe','Sorry','Entschuldigung'],['Yes','Sim','Yes','Ja'],['No','Não','No','Nein'],['Welcome','De nada','Welcome','Willkommen'],['Excuse me','Com licença','Excuse me','Entschuldigung']]},
    {title:'Numbers',icon:'🔢',words:[['one','um','one','eins'],['two','dois','two','zwei'],['three','três','three','drei'],['four','quatro','four','vier'],['five','cinco','five','fünf'],['six','seis','six','sechs'],['seven','sete','seven','sieben'],['eight','oito','eight','acht'],['nine','nove','nine','neun'],['ten','dez','ten','zehn']]},
    {title:'Colors',icon:'🎨',words:[['red','vermelho','red','rot'],['blue','azul','blue','blau'],['green','verde','green','grün'],['yellow','amarelo','yellow','gelb'],['white','branco','white','weiß'],['black','preto','black','schwarz'],['orange','laranja','orange','orange'],['pink','rosa','pink','rosa'],['purple','roxo','purple','lila'],['brown','marrom','brown','braun']]},
    {title:'Family',icon:'👨‍👩‍👧',words:[['mother','mãe','mother','Mutter'],['father','pai','father','Vater'],['sister','irmã','sister','Schwester'],['brother','irmão','brother','Bruder'],['son','filho','son','Sohn'],['daughter','filha','daughter','Tochter'],['grandmother','avó','grandmother','Großmutter'],['grandfather','avô','grandfather','Großvater'],['cousin','primo','cousin','Cousin'],['family','família','family','Familie']]},
    {title:'Food',icon:'🍎',words:[['apple','maçã','apple','Apfel'],['bread','pão','bread','Brot'],['water','água','water','Wasser'],['milk','leite','milk','Milch'],['rice','arroz','rice','Reis'],['egg','ovo','egg','Ei'],['fish','peixe','fish','Fisch'],['chicken','frango','chicken','Hähnchen'],['coffee','café','coffee','Kaffee'],['cheese','queijo','cheese','Käse']]},
    {title:'Days',icon:'📅',words:[['Monday','segunda','Monday','Montag'],['Tuesday','terça','Tuesday','Dienstag'],['Wednesday','quarta','Wednesday','Mittwoch'],['Thursday','quinta','Thursday','Donnerstag'],['Friday','sexta','Friday','Freitag'],['Saturday','sábado','Saturday','Samstag'],['Sunday','domingo','Sunday','Sonntag'],['today','hoje','today','heute'],['tomorrow','amanhã','tomorrow','morgen'],['yesterday','ontem','yesterday','gestern']]},
    {title:'Animals',icon:'🐶',words:[['dog','cachorro','dog','Hund'],['cat','gato','cat','Katze'],['bird','pássaro','bird','Vogel'],['horse','cavalo','horse','Pferd'],['cow','vaca','cow','Kuh'],['lion','leão','lion','Löwe'],['elephant','elefante','elephant','Elefant'],['rabbit','coelho','rabbit','Kaninchen'],['fish','peixe','fish','Fisch'],['frog','sapo','frog','Frosch']]},
    {title:'Weather',icon:'🌤',words:[['sunny','ensolarado','sunny','sonnig'],['rainy','chuvoso','rainy','regnerisch'],['cold','frio','cold','kalt'],['hot','quente','hot','heiß'],['wind','vento','wind','Wind'],['snow','neve','snow','Schnee'],['cloud','nuvem','cloud','Wolke'],['storm','tempestade','storm','Sturm'],['fog','neblina','fog','Nebel'],['rainbow','arco-íris','rainbow','Regenbogen']]}
  ],
  fr:[
    {title:'Salutations',icon:'👋',words:[['Bonjour','Olá / Bom dia','Hello','Hallo'],['Au revoir','Tchau','Goodbye','Auf Wiedersehen'],["S'il vous plaît",'Por favor','Please','Bitte'],['Merci','Obrigado','Thank you','Danke'],['Pardon','Desculpe','Sorry','Entschuldigung'],['Oui','Sim','Yes','Ja'],['Non','Não','No','Nein']]},
    {title:'Nombres',icon:'🔢',words:[['un','um','one','eins'],['deux','dois','two','zwei'],['trois','três','three','drei'],['quatre','quatro','four','vier'],['cinq','cinco','five','fünf'],['six','seis','six','sechs'],['sept','sete','seven','sieben'],['huit','oito','eight','acht'],['neuf','nove','nine','neun'],['dix','dez','ten','zehn']]},
    {title:'Couleurs',icon:'🎨',words:[['rouge','vermelho','red','rot'],['bleu','azul','blue','blau'],['vert','verde','green','grün'],['jaune','amarelo','yellow','gelb'],['blanc','branco','white','weiß'],['noir','preto','black','schwarz'],['rose','rosa','pink','rosa']]},
    {title:'Famille',icon:'👨‍👩‍👧',words:[['mère','mãe','mother','Mutter'],['père','pai','father','Vater'],['sœur','irmã','sister','Schwester'],['frère','irmão','brother','Bruder'],['fils','filho','son','Sohn'],['fille','filha','daughter','Tochter']]},
    {title:'Nourriture',icon:'🍎',words:[['pomme','maçã','apple','Apfel'],['pain','pão','bread','Brot'],['eau','água','water','Wasser'],['lait','leite','milk','Milch'],['riz','arroz','rice','Reis'],['œuf','ovo','egg','Ei'],['poisson','peixe','fish','Fisch']]}
  ],
  es:[
    {title:'Saludos',icon:'👋',words:[['Hola','Olá','Hello','Hallo'],['Buenos días','Bom dia','Good morning','Guten Morgen'],['Adiós','Tchau','Goodbye','Auf Wiedersehen'],['Por favor','Por favor','Please','Bitte'],['Gracias','Obrigado','Thank you','Danke'],['Sí','Sim','Yes','Ja'],['No','Não','No','Nein']]},
    {title:'Números',icon:'🔢',words:[['uno','um','one','eins'],['dos','dois','two','zwei'],['tres','três','three','drei'],['cuatro','quatro','four','vier'],['cinco','cinco','five','fünf'],['seis','seis','six','sechs'],['siete','sete','seven','sieben'],['ocho','oito','eight','acht'],['nueve','nove','nine','neun'],['diez','dez','ten','zehn']]},
    {title:'Colores',icon:'🎨',words:[['rojo','vermelho','red','rot'],['azul','azul','blue','blau'],['verde','verde','green','grün'],['amarillo','amarelo','yellow','gelb'],['blanco','branco','white','weiß'],['negro','preto','black','schwarz']]},
    {title:'Familia',icon:'👨‍👩‍👧',words:[['madre','mãe','mother','Mutter'],['padre','pai','father','Vater'],['hermana','irmã','sister','Schwester'],['hermano','irmão','brother','Bruder'],['hijo','filho','son','Sohn'],['hija','filha','daughter','Tochter']]},
    {title:'Comida',icon:'🍎',words:[['manzana','maçã','apple','Apfel'],['pan','pão','bread','Brot'],['agua','água','water','Wasser'],['leche','leite','milk','Milch'],['arroz','arroz','rice','Reis'],['huevo','ovo','egg','Ei']]}
  ],
  it:[
    {title:'Saluti',icon:'👋',words:[['Ciao','Olá','Hello','Hallo'],['Buongiorno','Bom dia','Good morning','Guten Morgen'],['Arrivederci','Tchau','Goodbye','Auf Wiedersehen'],['Per favore','Por favor','Please','Bitte'],['Grazie','Obrigado','Thank you','Danke'],['Sì','Sim','Yes','Ja'],['No','Não','No','Nein']]},
    {title:'Numeri',icon:'🔢',words:[['uno','um','one','eins'],['due','dois','two','zwei'],['tre','três','three','drei'],['quattro','quatro','four','vier'],['cinque','cinco','five','fünf'],['sei','seis','six','sechs'],['sette','sete','seven','sieben'],['otto','oito','eight','acht'],['nove','nove','nine','neun'],['dieci','dez','ten','zehn']]},
    {title:'Colori',icon:'🎨',words:[['rosso','vermelho','red','rot'],['blu','azul','blue','blau'],['verde','verde','green','grün'],['giallo','amarelo','yellow','gelb'],['bianco','branco','white','weiß'],['nero','preto','black','schwarz']]},
    {title:'Famiglia',icon:'👨‍👩‍👧',words:[['madre','mãe','mother','Mutter'],['padre','pai','father','Vater'],['sorella','irmã','sister','Schwester'],['fratello','irmão','brother','Bruder']]},
    {title:'Cibo',icon:'🍎',words:[['mela','maçã','apple','Apfel'],['pane','pão','bread','Brot'],['acqua','água','water','Wasser'],['latte','leite','milk','Milch'],['riso','arroz','rice','Reis'],['uovo','ovo','egg','Ei']]}
  ],
  de:[
    {title:'Begrüßungen',icon:'👋',words:[['Hallo','Olá','Hello','Hallo'],['Guten Morgen','Bom dia','Good morning','Guten Morgen'],['Auf Wiedersehen','Tchau','Goodbye','Auf Wiedersehen'],['Bitte','Por favor','Please','Bitte'],['Danke','Obrigado','Thank you','Danke'],['Ja','Sim','Yes','Ja'],['Nein','Não','No','Nein']]},
    {title:'Zahlen',icon:'🔢',words:[['eins','um','one','eins'],['zwei','dois','two','zwei'],['drei','três','three','drei'],['vier','quatro','four','vier'],['fünf','cinco','five','fünf'],['sechs','seis','six','sechs'],['sieben','sete','seven','sieben'],['acht','oito','eight','acht'],['neun','nove','nine','neun'],['zehn','dez','ten','zehn']]},
    {title:'Farben',icon:'🎨',words:[['rot','vermelho','red','rot'],['blau','azul','blue','blau'],['grün','verde','green','grün'],['gelb','amarelo','yellow','gelb'],['weiß','branco','white','weiß'],['schwarz','preto','black','schwarz']]},
    {title:'Familie',icon:'👨‍👩‍👧',words:[['Mutter','mãe','mother','Mutter'],['Vater','pai','father','Vater'],['Schwester','irmã','sister','Schwester'],['Bruder','irmão','brother','Bruder']]},
    {title:'Essen',icon:'🍎',words:[['Apfel','maçã','apple','Apfel'],['Brot','pão','bread','Brot'],['Wasser','água','water','Wasser'],['Milch','leite','milk','Milch'],['Reis','arroz','rice','Reis'],['Ei','ovo','egg','Ei']]}
  ],
  pt:[
    {title:'Cumprimentos',icon:'👋',words:[['Olá','Hello','Hola','Hallo'],['Bom dia','Good morning','Buenos días','Guten Morgen'],['Tchau','Goodbye','Adiós','Auf Wiedersehen'],['Por favor','Please','Por favor','Bitte'],['Obrigado','Thank you','Gracias','Danke'],['Sim','Yes','Sí','Ja'],['Não','No','No','Nein']]},
    {title:'Números',icon:'🔢',words:[['um','one','uno','eins'],['dois','two','dos','zwei'],['três','three','tres','drei'],['quatro','four','cuatro','vier'],['cinco','five','cinco','fünf']]}
  ]
};
function getTransIdx(){return{pt:1,en:2,de:3}[P.lang]||1;}

// ══════════════════════════════════════════
// STATE
// ══════════════════════════════════════════
var SK='tbx9';
var P={name:'',age:'adult',avatar:'😊',lang:'pt',xp:0,gems:100,hearts:5,heartNextReset:0,done:[],errors:[],badges:[],lessonCount:0,langProgress:{},acc:{hc:false,lg:false,ra:false}};
var NAV={tab:'home',courseId:null};
var TIMER=null;

function save(){try{localStorage.setItem(SK,JSON.stringify(P));}catch(e){}}
function load(){
  try{
    var r=JSON.parse(localStorage.getItem(SK)||'');
    if(r&&r.name){
      P=r;
      if(!P.done)P.done=[];
      if(!P.errors)P.errors=[];
      if(!P.langProgress)P.langProgress={};
      if(!P.acc)P.acc={hc:false,lg:false,ra:false};
      if(!P.heartNextReset)P.heartNextReset=nextMidnight();
      return true;
    }
  }catch(e){}
  return false;
}
function doneHas(id){return P.done.indexOf(id)>=0;}
function doneAdd(id){if(!doneHas(id))P.done.push(id);}
function killTimer(){if(TIMER){clearInterval(TIMER);TIMER=null;}}

// ── Midnight hearts refill ──
function nextMidnight(){
  var now=new Date();
  return new Date(now.getFullYear(),now.getMonth(),now.getDate()+1,0,0,0,0).getTime();
}
function checkHeartReset(){
  if(P.hearts<5&&Date.now()>=P.heartNextReset){
    P.hearts=5;P.heartNextReset=nextMidnight();save();updStats();
  }
}
setInterval(checkHeartReset,10000);
function heartCountdown(){
  var rem=Math.max(0,(P.heartNextReset||nextMidnight())-Date.now());
  return pad(Math.floor(rem/3600000))+':'+pad(Math.floor((rem%3600000)/60000))+':'+pad(Math.floor((rem%60000)/1000));
}
function pad(n){return n<10?'0'+n:''+n;}

// ── Accessibility ──
function applyAcc(){
  document.documentElement.classList.toggle('hc',!!P.acc.hc);
  document.documentElement.classList.toggle('lg',!!P.acc.lg);
  document.documentElement.classList.toggle('ra',!!P.acc.ra);
}
function togAcc(k){P.acc[k]=!P.acc[k];save();applyAcc();buildProfile();toast(T('accApplied'));}

// ══════════════════════════════════════════
// HEARTS SHOP
// ══════════════════════════════════════════
function openHeartsShop(){
  checkHeartReset();
  var ov=document.getElementById('heartsModal');
  ov.innerHTML='';
  var sheet=document.createElement('div');
  sheet.className='modal-sheet';
  sheet.addEventListener('click',function(e){e.stopPropagation();});

  var hd='';for(var i=0;i<5;i++)hd+=(i<P.hearts?'❤️':'🖤');
  var ttl=document.createElement('div');ttl.className='modal-ttl';ttl.textContent='❤️ '+T('hvTitle');
  var hdDiv=document.createElement('div');
  hdDiv.style.cssText='text-align:center;font-size:1.8rem;margin-bottom:14px;letter-spacing:4px';
  hdDiv.textContent=hd;
  var timerDiv=document.createElement('div');timerDiv.className='heart-timer';
  timerDiv.innerHTML='<div class="ht-label">🕛 '+T('hvReset')+'</div><div class="ht-time" id="hvTimer">'+heartCountdown()+'</div>';

  function makeRow(ic,nm,ds,priceText,bc,bg,fn){
    var row=document.createElement('div');row.className='hrow';
    row.style.borderColor=bc;row.style.background=bg;
    if(fn)row.addEventListener('click',fn);else row.style.cursor='default';
    row.innerHTML='<div class="hrow-ic">'+ic+'</div><div style="flex:1"><div class="hrow-nm">'+nm+'</div><div class="hrow-ds">'+ds+'</div></div><div class="hrow-price">'+priceText+'</div>';
    return row;
  }

  var row1=makeRow('❤️',T('hvB1'),T('hvB1ds'),'💎 50','rgba(255,75,75,.3)','rgba(255,75,75,.06)',function(){buyHeart(1);});
  var row2=makeRow('💖',T('hvBF'),T('hvBFds'),'💎 200','rgba(255,200,0,.3)','rgba(255,200,0,.06)',function(){buyHeart(5);});
  var row3=makeRow('⏳',T('hvWait'),T('hvWaitDs'),T('hvFree'),'rgba(28,176,246,.25)','rgba(28,176,246,.05)',null);

  var revRow=document.createElement('div');
  revRow.className='hrow';
  revRow.style.cssText='border-color:rgba(88,204,2,.4);background:rgba(88,204,2,.07);flex-direction:column;align-items:flex-start;gap:4px;cursor:pointer';
  revRow.innerHTML='<div style="display:flex;align-items:center;gap:10px;width:100%"><div class="hrow-ic">📝</div><div style="flex:1"><div class="hrow-nm" style="color:var(--gr)">'+T('hvRev')+'</div><div class="hrow-ds">'+(P.errors.length>0?P.errors.length+T('hvRevErr'):T('hvRevDs'))+'</div></div><div class="hrow-price" style="color:var(--gr);border-color:rgba(88,204,2,.4);background:rgba(88,204,2,.1)">+1 ❤️</div></div><div style="font-size:.62rem;color:var(--tx3);padding-left:2px">⚠️ '+T('hvWarn')+'</div>';
  revRow.addEventListener('click',function(){startHeartReview();});

  var closeBtn=document.createElement('button');
  closeBtn.className='btn-main btn-red';closeBtn.style.marginTop='4px';
  closeBtn.textContent=T('hvClose');
  closeBtn.addEventListener('click',closeHeartsShop);

  sheet.appendChild(ttl);sheet.appendChild(hdDiv);sheet.appendChild(timerDiv);
  sheet.appendChild(row1);sheet.appendChild(row2);sheet.appendChild(row3);
  sheet.appendChild(revRow);sheet.appendChild(closeBtn);
  ov.appendChild(sheet);
  ov.classList.add('on');
  ov.addEventListener('click',function(e){if(e.target===ov)closeHeartsShop();},{once:true});

  killTimer();
  TIMER=setInterval(function(){var el=document.getElementById('hvTimer');if(el)el.textContent=heartCountdown();else killTimer();},1000);
}
function closeHeartsShop(){killTimer();var ov=document.getElementById('heartsModal');ov.classList.remove('on');ov.innerHTML='';}
function buyHeart(n){
  var cost=n===1?50:200;
  if(P.gems<cost){toast(T('notEnoughGems'));return;}
  if(P.hearts>=5){toast(T('alreadyFull'));return;}
  P.gems-=cost;P.hearts=n===1?Math.min(5,P.hearts+1):5;
  save();updStats();closeHeartsShop();setTimeout(openHeartsShop,80);
}
function startHeartReview(){
  closeHeartsShop();
  var qs=[];
  if(P.errors.length>0){
    shuffle(P.errors.slice()).slice(0,8).forEach(function(e){
      qs.push({type:'mc',q:e.q,opts:shuffle([e.right].concat(genDis(e.right,3))),ans:e.right});
    });
  }else{
    for(var j=0;j<6;j++){var a=rnd(2,12),b=rnd(2,12);qs.push({type:'mc',q:a+' × '+b+' = ?',opts:mkOpts(a*b,Math.max(4,Math.round(a*b*.2))),ans:a*b});}
  }
  LS={lesson:{id:'__heart_review__',title:'Review',xp:0,isHeartReview:true},questions:qs,step:0,hearts:99,xp:0,errors:[],checked:false,selAns:null};
  NAV.courseId=null;show('sLesson');renderStep();
}

// ══════════════════════════════════════════
// NAVIGATION
// ══════════════════════════════════════════
function show(id){document.querySelectorAll('.scr').forEach(function(s){s.classList.remove('on');});var el=document.getElementById(id);if(el)el.classList.add('on');}
function navTo(tab){
  ['home','map','pg','prof'].forEach(function(t){var el=document.getElementById('tab'+t[0].toUpperCase()+t.slice(1));if(el)el.classList.toggle('on',t===tab);});
  document.querySelectorAll('.nb').forEach(function(b){b.classList.remove('on');});
  var nb=document.getElementById('nb'+tab[0].toUpperCase()+tab.slice(1));if(nb)nb.classList.add('on');
  NAV.tab=tab;
  if(tab==='prof')buildProfile();else if(tab==='pg')buildPlayground();else if(tab==='home')buildHome();
}
function goBack(){killTimer();show('sApp');if(NAV.courseId&&NAV.courseId!=='tabu')openMap(NAV.courseId);else navTo('home');}

// ══════════════════════════════════════════
// ONBOARDING
// ══════════════════════════════════════════
var _obLang='pt',_obAge=null;
function obLang(el,v){
  document.querySelectorAll('.lang-btn').forEach(function(b){b.classList.remove('on');});
  el.classList.add('on');_obLang=v;P.lang=v;
  var t=TX[v]||TX.pt;
  document.getElementById('obSubTxt').textContent=t.tagline;
  document.getElementById('obBtn').textContent=t.start;
  document.getElementById('lblName').textContent=t.yourName;
  document.getElementById('lblAge').textContent=t.yourAge;
  document.getElementById('age1sb').textContent=t.age1;
  document.getElementById('age2sb').textContent=t.age2;
  document.getElementById('age3sb').textContent=t.age3;
  document.getElementById('age4sb').textContent=t.age4;
  obChk();
}
function obAge(el,v){document.querySelectorAll('#ageGrid .sel-btn').forEach(function(b){b.classList.remove('on');});el.classList.add('on');_obAge=v;obChk();}
function obChk(){document.getElementById('obBtn').disabled=!document.getElementById('obName').value.trim()||!_obAge;}
function startApp(){
  P.name=document.getElementById('obName').value.trim();
  P.age=_obAge;P.lang=_obLang;
  P.heartNextReset=nextMidnight();
  save();show('sApp');initApp();
}

// ══════════════════════════════════════════
// APP INIT
// ══════════════════════════════════════════
function initApp(){
  applyAcc();
  document.getElementById('topAv').textContent=P.avatar||P.name[0]||'?';
  document.getElementById('topNm').textContent=P.name;
  document.getElementById('pfab').classList.add('show');
  document.getElementById('nbHomeTxt').textContent=T('home');
  document.getElementById('nbPgTxt').textContent=T('code');
  document.getElementById('nbProfTxt').textContent=T('profile');
  document.getElementById('pcStTxt').textContent=T('aiOnline');
  document.getElementById('pcInp').placeholder=P.lang==='en'?'Ask...':P.lang==='de'?'Fragen...':'Pergunte...';
  buildPcChips();updStats();buildHome();checkHeartReset();
  setTimeout(function(){if(!_pcHist.length)pcGreet();},1200);
}
function updStats(){document.getElementById('spHrt').textContent=P.hearts;document.getElementById('spGem').textContent=P.gems;document.getElementById('spXp').textContent=P.xp;}
function updPcProgress(){
  var courses=getCourses();var total=0,done=0;
  courses.forEach(function(c){if(!c)return;total+=(c.allLessons||[]).length;done+=(c.allLessons||[]).filter(function(l){return doneHas(l.id);}).length;});
  var pct=total?Math.round(done/total*100):0;
  var vEl=document.getElementById('ppbVal'),fEl=document.getElementById('ppbFill'),pEl=document.getElementById('pcProg');
  if(vEl)vEl.textContent=pct+'%';if(fEl)fEl.style.width=pct+'%';if(pEl)pEl.classList.toggle('show',done>0);
}
var LANG_LEVELS=['A1','A2','B1','B2'];
function getLLP(cid){return P.langProgress[cid]||{level:'A1',count:0};}
function getLLvl(cid){return getLLP(cid).level;}
function updLLP(cid){if(!P.langProgress[cid])P.langProgress[cid]={level:'A1',count:0};var lp=P.langProgress[cid];lp.count++;var idx=LANG_LEVELS.indexOf(lp.level);if(lp.count>=75&&idx<3){lp.level=LANG_LEVELS[idx+1];lp.count=0;return lp.level;}return null;}
function diffScale(){return{adult:1.0,'15-18':.75,'11-14':.5,'6-10':.2}[P.age]||1.0;}

// ══════════════════════════════════════════
// COURSES
// ══════════════════════════════════════════
function getLangTargets(){return['en','fr','it','de','es'].filter(function(l){return l!==P.lang;});}
function getCourses(){
  var cs=[buildMathCourse(),buildCodeCourse(),buildTabuCourse()];
  getLangTargets().forEach(function(tl){cs.push(buildLangCourse(tl));});
  return cs.filter(Boolean);
}
function injectChests(ls,prefix){
  var r=[],c=0;
  for(var i=0;i<ls.length;i++){r.push(ls[i]);c++;if(c>=8&&i<ls.length-1){r.push({id:'chest-'+prefix+'-'+i,title:'💰 '+T('chestTitle'),icon:'💰',type:'chest',xp:0,isChest:true});c=0;}}
  return r;
}

// ── MATH ──
var MATH_TOPICS=[
  ['add','muArith','🔢','mtAdd','➕',20,'add',200,200],
  ['sub','muArith','🔢','mtSub','➖',20,'sub',200,200],
  ['mul','muMul','✖️','mtMul','✖️',22,'mulx',12,12],
  ['div','muMul','✖️','mtDiv','➗',18,'divx',12,12],
  ['frac','muFrac','½','mtFrac','½',22,'fracAll',12,0],
  ['dec','muFrac','½','mtDec','.',16,'dec',10,10],
  ['pct','muPct','%','mtPct','%',18,'pct',1000,0],
  ['alg1','muAlg','📈','mtAlg1','📈',20,'alg1',20,20],
  ['alg2','muAlg','📈','mtAlg2','📈',18,'alg2',15,15],
  ['sys','muAlg','📈','mtSys','⚖️',16,'sys',10,10],
  ['quad','muAlg','📈','mtQuad','x²',16,'quad',8,0],
  ['geo','muGeo','📐','mtGeo','📐',20,'geo',20,0],
  ['pit','muGeo','📐','mtPit','⊿',14,'pit',0,0],
  ['trig','muGeo','📐','mtTrig','📏',14,'trig',0,0],
  ['stat','muStat','📉','mtStat','📉',16,'stat',0,0],
  ['prob','muStat','📉','mtProb','🎲',14,'prob',0,0],
  ['seq','muSeq','📊','mtSeq','📊',16,'pgpa',50,0],
  ['mat','muAdv','🔲','mtMat','🔲',14,'mat',6,0],
  ['poly','muAdv','🔲','mtPoly','p(x)',14,'poly',5,0]
];
function buildMathCourse(){
  var unitMap={};
  MATH_TOPICS.forEach(function(t){
    var id=t[0],uKey=t[1],uIcon=t[2],tKey=t[3],tIcon=t[4],n=t[5],gen=t[6],mA=t[7],mB=t[8];
    var uName=T(uKey),tName=T(tKey);
    if(!unitMap[uKey])unitMap[uKey]={name:uName,icon:uIcon,color:'#58cc02',lessons:[]};
    var ls=[];
    ls.push({id:id+'-0',title:tName+': '+T('conceptLabel'),icon:'📖',type:'learn',xp:5,gen:gen,params:{mA:mA,mB:mB,diff:0}});
    for(var d=1;d<n;d++){
      ls.push({id:id+'-'+d,title:tName+' '+T('lv')+' '+d,icon:tIcon,type:d>=n-1?'challenge':'lesson',xp:5+d*2,gen:gen,params:{mA:mA,mB:mB,diff:(d/(n-1))*diffScale()}});
    }
    ls.forEach(function(l){unitMap[uKey].lessons.push(l);});
  });
  var ua=Object.values(unitMap).map(function(u,i){return Object.assign({},u,{id:'mu'+i});});
  var flat=[];ua.forEach(function(u){u.lessons.forEach(function(l){flat.push(l);});});
  return{id:'math',name:T('math'),icon:'🔢',bg:'linear-gradient(135deg,#58cc02,#2d8a00)',color:'#58cc02',desc:T('mathDesc'),units:ua,allLessons:injectChests(flat,'math')};
}

// ── PYTHON ──
var PY_CONCEPTS=[
  {id:'print',uKey:'puBasic',uIcon:'🐍',name:'print()',icon:'👋',n:18,lessonType:'code',code:'print("Hello!")',check:function(o){return o.trim().length>0;},hint:'print("Texto")',get expl(){return{emoji:'👋',title:T('pyPrintT'),body:T('pyPrintB'),tip:T('pyPrintTip')};}},
  {id:'vars',uKey:'puBasic',uIcon:'🐍',name:'Variables',icon:'📦',n:18,lessonType:'mc',get expl(){return{emoji:'📦',title:T('pyVarsT'),body:T('pyVarsB'),tip:T('pyVarsTip')};}},
  {id:'types',uKey:'puBasic',uIcon:'🐍',name:'Types',icon:'🗂',n:16,lessonType:'mc',get expl(){return{emoji:'🗂',title:T('pyTypesT'),body:T('pyTypesB'),tip:T('pyTypesTip')};}},
  {id:'ops',uKey:'puBasic',uIcon:'🐍',name:'Operators',icon:'🔧',n:16,lessonType:'mc',get expl(){return{emoji:'🔧',title:T('pyOpsT'),body:T('pyOpsB'),tip:T('pyOpsTip')};}},
  {id:'input',uKey:'puBasic',uIcon:'🐍',name:'input()',icon:'⌨️',n:12,lessonType:'mc',get expl(){return{emoji:'⌨️',title:T('pyInputT'),body:T('pyInputB'),tip:T('pyInputTip')};}},
  {id:'ifelse',uKey:'puCond',uIcon:'🔀',name:'if/else',icon:'🔀',n:20,lessonType:'code',code:'x=10\nif x>5:\n    print("ok")',check:function(o){return o.trim().length>0;},hint:'if x>5:\n    print("ok")',get expl(){return{emoji:'🔀',title:T('pyIfT'),body:T('pyIfB'),tip:T('pyIfTip')};}},
  {id:'elif',uKey:'puCond',uIcon:'🔀',name:'elif',icon:'🔀',n:16,lessonType:'mc',get expl(){return{emoji:'🔀',title:T('pyElifT'),body:T('pyElifB'),tip:T('pyElifTip')};}},
  {id:'forr',uKey:'puLoops',uIcon:'🔁',name:'for+range()',icon:'🔁',n:20,lessonType:'code',code:'for i in range(5):\n    print(i)',check:function(o){return o.includes('0')&&o.includes('4');},hint:'for i in range(5):\n    print(i)',get expl(){return{emoji:'🔁',title:T('pyForT'),body:T('pyForB'),tip:T('pyForTip')};}},
  {id:'while',uKey:'puLoops',uIcon:'🔁',name:'while',icon:'⟳',n:16,lessonType:'code',code:'n=5\nwhile n>0:\n    print(n)\n    n-=1',check:function(o){return o.includes('5')&&o.includes('1');},hint:'while n>0:\n    n-=1',get expl(){return{emoji:'⟳',title:T('pyWhileT'),body:T('pyWhileB'),tip:T('pyWhileTip')};}},
  {id:'list',uKey:'puLists',uIcon:'📋',name:'Lists',icon:'📋',n:20,lessonType:'code',code:'nums=[3,1,4,1,5]\nprint(len(nums))',check:function(o){return o.includes('5');},hint:'print(len(nums))',get expl(){return{emoji:'📋',title:T('pyListT'),body:T('pyListB'),tip:T('pyListTip')};}},
  {id:'dict',uKey:'puLists',uIcon:'📋',name:'Dicts',icon:'📒',n:16,lessonType:'mc',get expl(){return{emoji:'📒',title:T('pyDictT'),body:T('pyDictB'),tip:T('pyDictTip')};}},
  {id:'tuples',uKey:'puLists',uIcon:'📋',name:'Tuples',icon:'🔒',n:14,lessonType:'mc',get expl(){return{emoji:'🔒',title:T('pyTupT'),body:T('pyTupB'),tip:T('pyTupTip')};}},
  {id:'func',uKey:'puFunc',uIcon:'📦',name:'Functions',icon:'📦',n:20,lessonType:'code',code:'def dobrar(n):\n    return n*2\nprint(dobrar(5))',check:function(o){return o.includes('10');},hint:'def dobrar(n):\n    return n*2',get expl(){return{emoji:'📦',title:T('pyFuncT'),body:T('pyFuncB'),tip:T('pyFuncTip')};}},
  {id:'params',uKey:'puFunc',uIcon:'📦',name:'Params',icon:'🔧',n:16,lessonType:'mc',get expl(){return{emoji:'🔧',title:T('pyParT'),body:T('pyParB'),tip:T('pyParTip')};}},
  {id:'lambda',uKey:'puFunc',uIcon:'📦',name:'Lambda',icon:'λ',n:14,lessonType:'mc',get expl(){return{emoji:'λ',title:T('pyLamT'),body:T('pyLamB'),tip:T('pyLamTip')};}},
  {id:'oop',uKey:'puOop',uIcon:'🏗',name:'Classes',icon:'🏗',n:18,lessonType:'mc',get expl(){return{emoji:'🏗',title:T('pyOopT'),body:T('pyOopB'),tip:T('pyOopTip')};}},
  {id:'inherit',uKey:'puOop',uIcon:'🏗',name:'Inheritance',icon:'🧬',n:14,lessonType:'mc',get expl(){return{emoji:'🧬',title:T('pyInhT'),body:T('pyInhB'),tip:T('pyInhTip')};}},
  {id:'exc',uKey:'puAdv',uIcon:'⚙️',name:'Exceptions',icon:'⚡',n:16,lessonType:'code',code:'try:\n    x=10/0\nexcept ZeroDivisionError:\n    print("Erro!")',check:function(o){return o.includes('Erro');},hint:'except ZeroDivisionError:',get expl(){return{emoji:'⚡',title:T('pyExcT'),body:T('pyExcB'),tip:T('pyExcTip')};}},
  {id:'comp',uKey:'puAdv',uIcon:'⚙️',name:'Comprehension',icon:'⚡',n:16,lessonType:'mc',get expl(){return{emoji:'⚡',title:T('pyCompT'),body:T('pyCompB'),tip:T('pyCompTip')};}},
  {id:'algo',uKey:'puAlgo',uIcon:'🧩',name:'Binary Search',icon:'🔍',n:14,lessonType:'code',code:'def busca(lst,alvo):\n    pass\nprint(busca([1,3,5,7,9],5))',check:function(o){return o.includes('2')||o.includes('True');},hint:'Compare com o meio!',get expl(){return{emoji:'🔍',title:T('pyAlgoT'),body:T('pyAlgoB'),tip:T('pyAlgoTip')};}},
  {id:'sort',uKey:'puAlgo',uIcon:'🧩',name:'Sorting',icon:'📊',n:14,lessonType:'mc',get expl(){return{emoji:'📊',title:T('pySortT'),body:T('pySortB'),tip:T('pySortTip')};}}
];
function buildCodeCourse(){
  var unitMap={};
  PY_CONCEPTS.forEach(function(c){
    var uKey=c.uKey;
    var uName=T(uKey);
    if(!unitMap[uKey])unitMap[uKey]={name:uName,icon:c.uIcon,color:'#1cb0f6',lessons:[]};
    var ls=[];
    ls.push({id:'c-'+c.id+'-0',title:c.name+': '+T('conceptLabel'),icon:'📖',type:'learn',xp:5,conceptId:c.id,lessonType:'expl',expl:c.expl});
    for(var d=1;d<c.n;d++){
      ls.push({id:'c-'+c.id+'-'+d,title:c.name+' '+T('practiceLabel')+' '+d,icon:c.icon,type:d>=c.n-1?'challenge':'lesson',xp:5+d*3,conceptId:c.id,diff:d,lessonType:d%3===0?'code':'mc',codeData:c});
    }
    ls.forEach(function(l){unitMap[uKey].lessons.push(l);});
  });
  var ua=Object.values(unitMap).map(function(u,i){return Object.assign({},u,{id:'cu'+i});});
  var flat=[];ua.forEach(function(u){u.lessons.forEach(function(l){flat.push(l);});});
  return{id:'code',name:T('python'),icon:'💻',bg:'linear-gradient(135deg,#1cb0f6,#0d6fa8)',color:'#1cb0f6',desc:T('pyDesc'),units:ua,allLessons:injectChests(flat,'code')};
}
function buildTabuCourse(){
  return{id:'tabu',name:T('tabu'),icon:'🎮',bg:'linear-gradient(135deg,#ff4b4b,#fb923c)',color:'#fb923c',desc:T('tabuDesc'),units:[],allLessons:[]};
}

// ── LANG COURSE ──
function getLangBg(tl){return{en:'linear-gradient(135deg,#1cb0f6,#0d6fa8)',fr:'linear-gradient(135deg,#3b82f6,#1e3a8a)',it:'linear-gradient(135deg,#22c55e,#15803d)',pt:'linear-gradient(135deg,#fb923c,#c2410c)',de:'linear-gradient(135deg,#a78bfa,#6d28d9)',es:'linear-gradient(135deg,#f59e0b,#b45309)'}[tl]||'linear-gradient(135deg,#a78bfa,#7c3aed)';}
function getLangFlag(tl){return{en:'🇺🇸',fr:'🇫🇷',it:'🇮🇹',pt:'🇧🇷',de:'🇩🇪',es:'🇪🇸'}[tl]||'🌍';}
function buildLangCourse(tl){
  var info=TL(tl);if(!info||!info.name)return null;
  var vocabSets=VOCAB_DB[tl]||VOCAB_DB.en;
  var units=buildLangUnits(tl,vocabSets);
  var flat=[];units.forEach(function(u){u.lessons.forEach(function(l){flat.push(l);});});
  return{id:'lang-'+tl,name:info.name,icon:info.flag,bg:getLangBg(tl),color:'#a78bfa',desc:info.desc,isLang:true,targetLang:tl,units:units,allLessons:injectChests(flat,tl)};
}
function getGrammarItems(tl){
  var items={
    en:[['To Be','I am / You are / He is',[['I am happy','Estou feliz'],['She is a teacher','Ela é professora']]],
        ['Articles','a/an (indefinite) · the (definite)',[['a dog, an apple','um cachorro, uma maçã']]],
        ['Plural','cats · men · women',[['one cat → two cats','um→dois gatos']]],
        ['Have/Has','I/You have · He/She has',[['I have a book','Tenho um livro']]],
        ['Simple Present','I eat · He eats',[['I eat at 7','Como às 7']]],
        ['WH Questions','What/Where/When/Who/Why/How',[['What do you do?','O que você faz?']]],
        ['Negatives',"I don't · She doesn't",[["I don't like fish",'Não gosto de peixe']]],
        ['Past Simple','walked · went/saw',[['I walked home','Fui a pé']]]],
    fr:[['Être','je suis / tu es / il est',[['Je suis heureux','Estou feliz']]],
        ['Articles','le/la/les · un/une',[['le chat','o gato']]],
        ['Avoir',"j'ai / tu as / il a",[["J'ai un livre",'Tenho um livro']]],
        ['Présent','je mange / tu manges',[['Je mange à 7h','Como às 7']]],
        ['Passé composé','avoir/être + participe',[["J'ai mangé",'Comi']]],
        ['Négation','ne...pas',[['Je ne mange pas de poisson','Não como peixe']]]],
    es:[['Ser/Estar','soy/eres/es · estoy/estás',[['Soy feliz','Estou feliz']]],
        ['Tener','tengo/tienes/tiene',[['Tengo un libro','Tenho um livro']]],
        ['Presente','como/comes/come',[['Como a las 7','Como às 7']]],
        ['Negación','No + verbo',[['No me gusta el pescado','Não gosto de peixe']]],
        ['Pretérito','comí/comiste/comió',[['Caminé a casa','Fui a pé']]],
        ['Futuro','comeré/comerás',[['Te llamaré','Te ligarei']]]],
    it:[['Essere','sono/sei/è/siamo',[['Sono felice','Estou feliz']]],
        ['Avere','ho/hai/ha/abbiamo',[['Ho un libro','Tenho um livro']]],
        ['Presente','mangio/mangi/mangia',[['Mangio alle 7','Como às 7']]],
        ['Negazione','non + verbo',[['Non mi piace il pesce','Não gosto de peixe']]],
        ['Passato prossimo','ho/sono + participio',[['Ho mangiato','Comi']]],
        ['Futuro','mangerò/mangerai',[['Ti chiamerò','Te ligarei']]]],
    de:[['Sein','ich bin/du bist/er ist',[['Ich bin glücklich','Estou feliz']]],
        ['Haben','ich habe/du hast/er hat',[['Ich habe ein Buch','Tenho um livro']]],
        ['Präsens','ich esse/du isst/er isst',[['Ich esse um 7','Como às 7']]],
        ['Verneinung','nicht/kein',[['Ich mag keinen Fisch','Não gosto de peixe']]],
        ['Perfekt','haben/sein + Partizip II',[['Ich bin gelaufen','Fui a pé']]],
        ['Futur I','werden + Infinitiv',[['Ich werde dich anrufen','Te ligarei']]]]
  };
  return items[tl]||items.en;
}
function buildLangUnits(tl,vocabSets){
  var units=[];
  var gramItems=getGrammarItems(tl);
  var levels=['A1','A2','B1','B2'];
  var perLevel=Math.ceil(vocabSets.length/4);
  levels.forEach(function(lvl,li){
    var vs=vocabSets.slice(li*perLevel,Math.min((li+1)*perLevel,vocabSets.length));
    var gs=gramItems.slice(li*2,Math.min((li+1)*2,gramItems.length));
    if(vs.length){
      var vLessons=[];
      vs.forEach(function(v,vi){
        vLessons.push({id:tl+'-'+lvl+'-v'+vi+'-0',title:v.title+': '+T('luVocab'),icon:v.icon,type:'learn',xp:5+li*2,langLevel:lvl,isLang:true,targetLang:tl,lessonData:v,category:'vocab'});
        for(var d=1;d<=20;d++){
          vLessons.push({id:tl+'-'+lvl+'-v'+vi+'-'+d,title:v.title+' '+T('practiceLabel')+' '+d,icon:v.icon,type:d===20?'challenge':'lesson',xp:5+li*2+d,langLevel:lvl,isLang:true,targetLang:tl,lessonData:v,category:'vocab'});
        }
      });
      units.push({id:'lu'+li+'v',name:lvl+' — '+T('luVocab'),icon:getLangFlag(tl),color:'#a78bfa',langLevel:lvl,lessons:vLessons});
    }
    if(gs.length){
      var gLessons=[];
      gs.forEach(function(g,gi){
        gLessons.push({id:tl+'-'+lvl+'-g'+gi+'-0',title:g[0]+': '+T('luGrammar'),icon:'📝',type:'learn',xp:8+li*2,langLevel:lvl,isLang:true,targetLang:tl,lessonData:{isGrammar:true,title:g[0],rule:g[1],examples:g[2]},category:'grammar'});
        for(var d=1;d<=18;d++){
          gLessons.push({id:tl+'-'+lvl+'-g'+gi+'-'+d,title:g[0]+' '+T('practiceLabel')+' '+d,icon:'📝',type:d===18?'challenge':'lesson',xp:8+li*2+d,langLevel:lvl,isLang:true,targetLang:tl,lessonData:{isGrammar:true,title:g[0],rule:g[1],examples:g[2]},category:'grammar'});
        }
      });
      units.push({id:'lu'+li+'g',name:lvl+' — '+T('luGrammar'),icon:'📝',color:'#1cb0f6',langLevel:lvl,lessons:gLessons});
    }
  });
  return units;
}

// ══════════════════════════════════════════
// HOME
// ══════════════════════════════════════════
function buildHome(){
  var courses=getCourses();
  var h='<div class="sec-h">'+T('myCourses')+'</div><div class="clist">';
  courses.forEach(function(c){
    if(!c)return;
    var ls=c.allLessons||[];
    var done=ls.filter(function(l){return doneHas(l.id);}).length;
    var pct=ls.length?Math.round(done/ls.length*100):0;
    var lvlBadge=c.isLang?'<div class="clvl">'+T('lv')+' '+getLLvl(c.id)+'</div>':'';
    h+='<div class="ccard" onclick="openCourse(\''+c.id+'\')">';
    h+='<div class="cico" style="background:'+c.bg+'">'+c.icon+'</div>';
    h+='<div class="cinfo"><div class="cnm">'+esc(c.name)+'</div>'+lvlBadge;
    h+='<div class="cds">'+esc(c.desc)+'</div>';
    h+='<div class="pbar"><div class="pbarf" style="width:'+pct+'%;background:'+c.color+'"></div></div>';
    h+='<div class="cst"><span class="cst-t">'+done+'/'+ls.length+' '+T('lessons')+'</span><span class="tag '+(pct===100?'tg':'tb')+'">'+pct+'% '+T('complete')+'</span></div>';
    h+='</div></div>';
  });
  h+='</div>';
  if(P.errors.length){
    h+='<div class="sec-h">'+T('reviewErrors')+'</div>';
    h+='<div class="ccard" onclick="startReview()"><div class="cico" style="background:linear-gradient(135deg,#ff4b4b,#fb923c)">🔁</div>';
    h+='<div class="cinfo"><div class="cnm">'+T('reviewErrors')+'</div><div class="cds">'+P.errors.length+' '+T('missed')+'</div>';
    h+='<div class="pbar"><div class="pbarf" style="width:100%;background:var(--rd)"></div></div></div></div>';
  }
  document.getElementById('tabHome').innerHTML=h;
}
function openCourse(id){NAV.courseId=id;if(id==='tabu'){show('sTabu');tabuLevelSelect();return;}openMap(id);}

// ══════════════════════════════════════════
// MAP
// ══════════════════════════════════════════
function openMap(cid){
  var course=getCourses().find(function(c){return c&&c.id===cid;});if(!course)return;
  navTo('map');
  var lessons=course.allLessons||[];
  var firstUndone=null;for(var i=0;i<lessons.length;i++){if(!doneHas(lessons[i].id)){firstUndone=lessons[i].id;break;}}
  var h='<div class="map-hdr"><button class="back-btn" onclick="navTo(\'home\')">'+T('back')+'</button><div class="map-ttl">'+esc(course.name)+'</div>';
  h+='<button class="back-btn" style="background:rgba(255,75,75,.08);border-color:rgba(255,75,75,.3);color:var(--rd)" onclick="resetCourse(\''+cid+'\')">🔄</button></div>';
  var unlocked=true;
  (course.units||[]).forEach(function(u,ui){
    h+='<div class="unit-box"><div class="unit-hdr" style="border-left-color:'+(u.color||'#1cb0f6')+'"><div class="unit-n">'+T('unit')+' '+(ui+1)+'</div><div class="unit-t">'+(u.icon||'📚')+' '+esc(u.name)+'</div></div>';
    (u.lessons||[]).forEach(function(l){
      var done=doneHas(l.id);var isNext=l.id===firstUndone;var locked=!unlocked&&!done&&!isNext;var isChest=l.isChest;
      var cls='lnode'+(done?' done':'')+(locked?' locked':'')+(isNext&&!done?' active-next':'')+(isChest?' chest-node':'');
      var onclick=locked?"toast('"+T('locked')+"')":'openLesson(\''+l.id+'\')';
      var tMap={learn:'tb',lesson:'tg',challenge:'ty',code:'tp',chest:'ty'};
      h+='<div class="'+cls+'" onclick="'+onclick+'"><div class="lico">'+(done?'✅':l.icon||'📖')+'</div>';
      h+='<div class="linfo"><div class="ltit">'+esc(l.title)+'</div><span class="tag '+(tMap[l.type]||'tb')+'">'+(isChest?'💎':l.type)+'</span>';
      if(isNext&&!done)h+='<span class="tag tb" style="margin-left:4px">'+T('next')+'</span>';
      h+='</div><div class="lxp">'+(l.xp?'+'+l.xp+'⭐':'')+'</div></div>';
      if(!done&&!isNext)unlocked=false;
    });
    h+='</div>';
  });
  document.getElementById('tabMap').innerHTML=h;
}
function resetCourse(cid){
  var course=getCourses().find(function(c){return c&&c.id===cid;});if(!course)return;
  showConfirm(T('resetCourse')+' "'+course.name+'"?',function(){
    var ids=(course.allLessons||[]).map(function(l){return l.id;});
    P.done=P.done.filter(function(id){return ids.indexOf(id)<0;});
    if(cid.startsWith('lang-'))delete P.langProgress[cid];
    save();toast('✅ '+course.name+' '+T('tabuResetted'));openMap(cid);
  });
}
function showConfirm(msg,cb){
  var ov=document.createElement('div');
  ov.style.cssText='position:fixed;inset:0;background:rgba(0,0,0,.85);z-index:9999;display:flex;align-items:center;justify-content:center;padding:20px';
  var box=document.createElement('div');
  box.style.cssText='background:#131f2e;border:1.5px solid #2a4058;border-radius:20px;padding:24px 20px;width:100%;max-width:320px;text-align:center';
  box.innerHTML='<div style="font-size:2rem;margin-bottom:8px">⚠️</div><div style="font-size:.95rem;font-weight:900;margin-bottom:18px">'+esc(msg)+'</div><div style="display:flex;gap:10px"><button id="_cancelBtn" style="flex:1;background:#1a2d3f;border:1.5px solid #2a4058;border-radius:12px;color:#7a9ab0;font-family:Nunito,sans-serif;font-size:.9rem;font-weight:900;padding:12px;cursor:pointer">'+T('cancel')+'</button><button id="_confirmBtn" style="flex:1;background:#ff4b4b;border:none;border-bottom:3px solid #cc3b3b;border-radius:12px;color:#fff;font-family:Nunito,sans-serif;font-size:.9rem;font-weight:900;padding:12px;cursor:pointer">OK</button></div>';
  ov.appendChild(box);document.body.appendChild(ov);
  document.getElementById('_cancelBtn').onclick=function(){document.body.removeChild(ov);};
  document.getElementById('_confirmBtn').onclick=function(){document.body.removeChild(ov);cb();};
}

// ══════════════════════════════════════════
// LESSON ENGINE
// ══════════════════════════════════════════
var LS={lesson:null,questions:[],step:0,hearts:5,xp:0,errors:[],checked:false,selAns:null};
function openLesson(lid){
  var course=getCourses().find(function(c){return c&&(c.allLessons||[]).some(function(l){return l.id===lid;});});
  var lesson=course?(course.allLessons||[]).find(function(l){return l.id===lid;}):null;
  if(!lesson)return;
  if(lesson.isChest){openChest(lesson);return;}
  if(P.hearts<=0){toast('❤️ '+T('noHearts'));return;}
  NAV.courseId=course.id;
  var qs=buildLessonSteps(lesson);
  LS={lesson:lesson,questions:qs,step:0,hearts:Math.min(P.hearts,5),xp:0,errors:[],checked:false,selAns:null};
  show('sLesson');renderStep();
}
function openChest(lesson){
  var gems=rnd(20,130);P.gems+=gems;doneAdd(lesson.id);save();updStats();
  if(!P.acc.ra)confetti(8);snd('win');
  document.getElementById('chestWinInner').innerHTML='<div style="font-size:4rem;margin-bottom:10px">💰</div><div style="font-size:1.4rem;font-weight:900;color:var(--yl);margin-bottom:6px">'+T('chestTitle')+'</div><div style="font-size:3rem;font-weight:900;color:var(--yl);margin:8px 0">+'+gems+' 💎</div><div style="font-size:.8rem;color:var(--tx2);margin-bottom:20px">'+T('chestCollect').replace('! 💎','')+'!</div><button class="btn-main btn-yl" onclick="closeChest()">'+T('chestCollect')+'</button>';
  document.getElementById('chestModal').classList.add('on');
}
function closeChest(){document.getElementById('chestModal').classList.remove('on');show('sApp');if(NAV.courseId)openMap(NAV.courseId);else navTo('home');}

function buildLessonSteps(l){
  if(l.lessonType==='expl')return[Object.assign({type:'explain'},l.expl)].concat(genMCFromConcept(l.conceptId,12));
  if(l.lessonType==='code'&&l.codeData){
    var cd=l.codeData;
    return[Object.assign({type:'explain'},cd.expl),
      {type:'code',title:cd.name,instruction:cd.expl.tip||'',starterCode:cd.code||'',check:cd.check||(function(o){return o.trim().length>0;}),hint:cd.hint||''}
    ].concat(genMCFromConcept(l.conceptId,10));
  }
  if(l.isLang){
    if(l.category==='vocab')return buildVocabSteps(l);
    if(l.category==='grammar')return buildGrammarSteps(l);
  }
  if(l.gen)return buildMathSteps(l);
  return[{type:'explain',emoji:'📖',title:l.title,body:'',tip:''},{type:'mc',q:'Ready?',opts:['Yes!','OK!','Sure!','Go!'],ans:'Yes!'}];
}
function buildVocabSteps(lesson){
  var v=lesson.lessonData;if(!v)return[];
  var tl=lesson.targetLang;var transIdx=getTransIdx();var words=v.words||[];
  var bodyLines=words.slice(0,6).map(function(w){return'• '+w[0]+' → '+w[transIdx];}).join('\n');
  var steps=[{type:'explain',emoji:v.icon||'📚',title:v.title,body:bodyLines,tip:words.slice(6,8).map(function(w){return w[0]+' = '+w[transIdx];}).join(' · ')}];
  shuffle(words.slice()).slice(0,14).forEach(function(w){
    var correct=w[transIdx];
    var dis=shuffle(words.filter(function(x){return x[0]!==w[0];}).map(function(x){return x[transIdx];})).slice(0,3);
    while(dis.length<3)dis.push(correct+'?');
    steps.push({type:'mc',q:'"'+w[0]+'" → ?',opts:shuffle([correct].concat(dis)),ans:correct,isLang:true});
  });
  return steps;
}
function buildGrammarSteps(lesson){
  var g=lesson.lessonData;if(!g)return[];
  var exArr=g.examples||[];
  var body=g.rule+(exArr.length?'\n\n'+exArr.slice(0,3).map(function(e){return'✅ '+e[0]+(e[1]?'\n   ('+e[1]+')':'');}).join('\n'):'');
  var steps=[{type:'explain',emoji:'📝',title:g.title,body:body,tip:exArr[0]?exArr[0][0]:''}];
  if(exArr.length){
    var pool=[];
    exArr.forEach(function(e){
      var q='"'+e[1]+'" → ('+g.title+')?';
      var correct=e[0];
      var dis=exArr.filter(function(x){return x[0]!==e[0];}).slice(0,3).map(function(x){return x[0];});
      while(dis.length<3)dis.push(correct+'.');
      pool.push({type:'mc',q:q,opts:shuffle([correct].concat(dis)),ans:correct,isLang:true});
    });
    for(var i=0;i<Math.min(12,pool.length*4);i++)steps.push(pool[i%pool.length]);
  }
  return steps.slice(0,15);
}
function buildMathSteps(l){
  var explain=Object.assign({},getLearnContent(l.gen),{type:'explain'});
  var qs=[explain];
  for(var i=0;i<13;i++){var q=genMathQ(l.gen,l.params,i);q.type=i<7?'mc':'type';q.isNum=true;qs.push(q);}
  return qs;
}
function getLearnContent(gen){
  var c={add:{emoji:'➕',title:T('mAddT'),body:T('mAddB'),tip:T('mAddTip')},sub:{emoji:'➖',title:T('mSubT'),body:T('mSubB'),tip:T('mSubTip')},mulx:{emoji:'✖️',title:T('mMulT'),body:T('mMulB'),tip:T('mMulTip')},divx:{emoji:'➗',title:T('mDivT'),body:T('mDivB'),tip:T('mDivTip')},fracAll:{emoji:'½',title:T('mFracT'),body:T('mFracB'),tip:T('mFracTip')},dec:{emoji:'.',title:T('mDecT'),body:T('mDecB'),tip:T('mDecTip')},pct:{emoji:'%',title:T('mPctT'),body:T('mPctB'),tip:T('mPctTip')},alg1:{emoji:'📈',title:T('mAlg1T'),body:T('mAlg1B'),tip:T('mAlg1Tip')},alg2:{emoji:'📈',title:T('mAlg2T'),body:T('mAlg2B'),tip:T('mAlg2Tip')},geo:{emoji:'📐',title:T('mGeoT'),body:T('mGeoB'),tip:T('mGeoTip')},pit:{emoji:'⊿',title:T('mPitT'),body:T('mPitB'),tip:T('mPitTip')},trig:{emoji:'📏',title:T('mTrigT'),body:T('mTrigB'),tip:T('mTrigTip')},stat:{emoji:'📉',title:T('mStatT'),body:T('mStatB'),tip:T('mStatTip')},prob:{emoji:'🎲',title:T('mProbT'),body:T('mProbB'),tip:T('mProbTip')},pgpa:{emoji:'📊',title:T('mSeqT'),body:T('mSeqB'),tip:T('mSeqTip')}};
  return c[gen]||{emoji:'📖',title:gen,body:'',tip:''};
}
function genMCFromConcept(id,n){
  var t=TX[P.lang]||TX.pt;
  var bank=(t.pyQ&&t.pyQ[id])||((TX.pt.pyQ||{})[id])||TX.pt.pyQ.default;
  return shuffle(bank.slice()).slice(0,n);
}

// ══════════════════════════════════════════
// RENDER LESSON
// ══════════════════════════════════════════
function renderStep(){
  var s=LS.questions[LS.step];if(!s){finishLesson();return;}
  var pct=Math.round(LS.step/LS.questions.length*100);
  document.getElementById('lesProg').style.width=pct+'%';
  var htsEl=document.getElementById('lesHts');
  if(LS.lesson.isHeartReview){
    htsEl.innerHTML='<span style="font-size:.72rem;font-weight:900;color:var(--gr);white-space:nowrap">+❤️</span>';
  }else{
    var hh='';for(var i=0;i<5;i++)hh+='<span class="h-ic'+(i>=LS.hearts?' lost':'')+'">❤️</span>';
    htsEl.innerHTML=hh;
  }
  LS.checked=false;LS.selAns=null;
  var body=document.getElementById('lesBody');var foot=document.getElementById('lesFoot');
  body.scrollTop=0;
  if(s.type==='explain')renderExplain(s,body,foot);
  else if(s.type==='mc')renderMC(s,body,foot);
  else if(s.type==='type')renderType(s,body,foot);
  else if(s.type==='code')renderCode(s,body,foot);
  else{LS.step++;renderStep();}
}
function renderExplain(s,b,f){
  b.innerHTML='<div class="expl-card"><div class="expl-em">'+(s.emoji||'📖')+'</div><div class="expl-ttl">'+esc(s.title||'')+'</div><div class="expl-body">'+esc(s.body||'')+'</div>'+(s.tip?'<div class="expl-tip">💡 '+esc(s.tip)+'</div>':'')+'</div>';
  f.innerHTML='<button class="chk-btn" onclick="nextStep()">'+T('gotIt')+'</button>';
}
function renderMC(s,b,f){
  var ltrs='ABCD';
  var h='<div><span class="q-badge tb">'+(s.isLang?'🌍':'📝')+'</span><div class="q-prompt">'+esc(s.q)+'</div></div><div class="mc-opts">';
  (s.opts||[]).forEach(function(o,i){h+='<button class="mc-btn" id="mo'+i+'" onclick="selMC('+i+')"><span class="mc-ltr">'+ltrs[i]+'</span>'+esc(String(o))+'</button>';});
  b.innerHTML=h+'</div>';
  f.innerHTML='<button class="chk-btn" id="chkBtn" disabled onclick="checkMC()">'+T('check')+'</button>';
}
function selMC(i){if(LS.checked)return;document.querySelectorAll('.mc-btn').forEach(function(b){b.classList.remove('sel');});var el=document.getElementById('mo'+i);if(el)el.classList.add('sel');LS.selAns=LS.questions[LS.step].opts[i];var btn=document.getElementById('chkBtn');if(btn)btn.disabled=false;}
function checkMC(){
  if(LS.checked)return;LS.checked=true;
  var s=LS.questions[LS.step];var ok=String(LS.selAns)===String(s.ans);
  document.querySelectorAll('.mc-btn').forEach(function(b,i){b.disabled=true;if(String(s.opts[i])===String(s.ans))b.classList.add('correct');});
  if(!ok){document.querySelectorAll('.mc-btn.sel').forEach(function(b){b.classList.add('wrong');});loseHeart();LS.errors.push({topic:'mc',q:s.q,wrong:LS.selAns,right:s.ans});}
  showFb(ok,ok?'':s.ans);
}
function renderType(s,b,f){
  b.innerHTML='<div><span class="q-badge tg">✍</span><div class="q-prompt">'+esc(s.q)+'</div></div><input class="type-inp" id="typeInp" type="'+(s.isNum?'number':'text')+'" inputmode="'+(s.isNum?'numeric':'text')+'" placeholder="?" autocomplete="off" onkeydown="if(event.key===\'Enter\')checkType()">';
  f.innerHTML='<button class="chk-btn" onclick="checkType()">'+T('check')+'</button>';
  setTimeout(function(){var el=document.getElementById('typeInp');if(el)el.focus();},80);
}
function checkType(){
  if(LS.checked)return;var inp=document.getElementById('typeInp');if(!inp||inp.value.trim()==='')return;
  LS.checked=true;inp.disabled=true;
  var s=LS.questions[LS.step];var ok=inp.value.trim().toLowerCase()===String(s.ans).toLowerCase();
  inp.classList.add(ok?'ok':'err');
  if(!ok){loseHeart();LS.errors.push({topic:'type',q:s.q,wrong:inp.value,right:s.ans});}
  showFb(ok,ok?'':s.ans);
}
function renderCode(s,b,f){
  var tid='ct'+Date.now(),oid='co'+Date.now();
  b.innerHTML='<div><span class="q-badge tp">💻</span><div class="q-prompt">'+esc(s.title)+'</div></div><div class="code-wrap"><div class="code-hdr"><div class="cdot" style="background:#ff5f57"></div><div class="cdot" style="background:#fbbf24"></div><div class="cdot" style="background:#28c840"></div><span class="clang">Python</span></div><textarea class="code-ta" id="'+tid+'" spellcheck="false" onkeydown="tabInd(event)">'+esc(s.starterCode||'')+'</textarea><div class="code-out"><div class="cout-lbl">Output</div><div class="cout-txt" id="'+oid+'" style="color:var(--tx3)">Click Run...</div></div></div><button class="run-btn" onclick="runCode(\''+tid+'\',\''+oid+'\')">▶ '+T('run')+'</button>';

f.innerHTML=’<button class="chk-btn" id="chkBtn" onclick="checkCode(\''+tid+'\',\''+oid+'\')">’+T(‘check’)+’</button>’;
}
function runCode(tid,oid){var ta=document.getElementById(tid);if(!ta)return;var r=pyRun(ta.value);var out=document.getElementById(oid);if(out){out.textContent=r.output||T(‘noOutput’);out.style.color=r.ok?’#7ee787’:’#ff7b7b’;}}
function checkCode(tid,oid){
if(LS.checked)return;var s=LS.questions[LS.step];var ta=document.getElementById(tid);if(!ta)return;
var res=pyRun(ta.value);LS.checked=true;var btn=document.getElementById(‘chkBtn’);if(btn)btn.disabled=true;
var ok=res.ok&&s.check(res.output);
if(!ok){loseHeart();showFb(false,s.hint||’’);}else showFb(true,’’);
}
function loseHeart(){
if(LS.lesson.isHeartReview)return;
LS.hearts=Math.max(0,LS.hearts-1);
var hh=’’;for(var i=0;i<5;i++)hh+=’<span class="h-ic'+(i>=LS.hearts?' lost':'')+'">❤️</span>’;
document.getElementById(‘lesHts’).innerHTML=hh;
snd(‘err’);
var bb=document.getElementById(‘lesBody’);if(bb){bb.style.animation=’’;void bb.offsetHeight;bb.style.animation=‘shake .3s ease’;setTimeout(function(){if(bb)bb.style.animation=’’;},350);}
}
function showFb(ok,ans){
snd(ok?‘ok’:‘err’);if(ok&&!P.acc.ra)confetti();if(ok)LS.xp+=5;
var f=document.getElementById(‘lesFoot’);
f.innerHTML=’<div class="fb-bar '+(ok?'ok':'err')+'"><div class="fb-ic">’+(ok?‘🎉’:‘💡’)+’</div><div style="flex:1"><div class="fb-ttl" style="color:'+(ok?'var(--gr)':'var(--rd)')+'">’+(ok?T(‘ok’):T(‘almost’))+’</div>’+(!ok&&ans?’<div class="fb-sub">’+T(‘correctAns’)+’ <b>’+esc(String(ans))+’</b></div>’:’’)+’</div></div><button class="chk-btn '+(ok?'':'err-st')+'" onclick="nextStep()">’+(ok?T(‘cont’):T(‘nxt’))+’</button>’;
}
function nextStep(){LS.step++;renderStep();}
function finishLesson(){
if(LS.lesson.isHeartReview){
if(P.hearts<5){P.hearts=Math.min(5,P.hearts+1);save();updStats();snd(‘win’);if(!P.acc.ra)confetti(6);}
document.getElementById(‘winEm’).textContent=‘❤️’;
document.getElementById(‘winTtl’).textContent=T(‘heartRecovered’);
document.getElementById(‘winSub’).textContent=’+1 ❤️’;
document.getElementById(‘winRw’).innerHTML=’<div class="rw">❤️ +1</div>’;
document.getElementById(‘winModal’).classList.add(‘on’);return;
}
var alr=doneHas(LS.lesson.id);
if(!alr){doneAdd(LS.lesson.id);P.xp+=LS.lesson.xp+LS.xp;P.gems+=Math.floor(LS.lesson.xp/2);P.lessonCount++;}
P.hearts=Math.min(5,LS.hearts);
LS.errors.forEach(function(e){if(!P.errors.find(function(x){return x.q===e.q;}))P.errors.push(e);});
P.errors=P.errors.slice(-30);
var lvlUp=’’;if(LS.lesson.isLang){var lu=updLLP(NAV.courseId);if(lu)lvlUp=lu;}
save();updStats();updPcProgress();snd(‘win’);if(!P.acc.ra)confetti(6);
document.getElementById(‘winEm’).textContent=‘🏆’;
document.getElementById(‘winTtl’).textContent=T(‘done’);
document.getElementById(‘winSub’).textContent=alr?T(‘alreadyDone’):’+’+(LS.lesson.xp+LS.xp)+’ ‘+T(‘xp’);
document.getElementById(‘winRw’).innerHTML=’<div class="rw">⭐ ‘+(alr?0:(LS.lesson.xp+LS.xp))+’ ‘+T(‘xp’)+’</div><div class="rw">💎 +’+Math.floor(LS.lesson.xp/2)+’</div>’+(lvlUp?’<div class="rw">🎊 ‘+lvlUp+’</div>’:’’);
document.getElementById(‘winModal’).classList.add(‘on’);
}
function closeWin(){document.getElementById(‘winModal’).classList.remove(‘on’);show(‘sApp’);if(NAV.courseId&&NAV.courseId!==‘tabu’)openMap(NAV.courseId);else navTo(‘home’);}
function startReview(){
if(!P.errors.length)return;
var qs=shuffle(P.errors.slice()).slice(0,14).map(function(e){return{type:‘mc’,q:e.q,opts:shuffle([e.right].concat(genDis(e.right,3))),ans:e.right};});
LS={lesson:{id:’**rev**’,title:‘Review’,xp:5},questions:qs,step:0,hearts:5,xp:0,errors:[],checked:false,selAns:null};
P.errors=[];save();NAV.courseId=null;show(‘sLesson’);renderStep();
}
function genDis(ans,n){if(typeof ans===‘number’)return[ans-1,ans+1,ans+2].slice(0,n);return[ans+’?’,ans+’!’,‘None’].slice(0,n);}

// ══════════════════════════════════════════
// MATH GENERATORS
// ══════════════════════════════════════════
function genMathQ(gen,params,idx){
var ds=diffScale();var p=params||{};
var mA=Math.max(2,Math.round((p.mA||10)*(0.4+ds*0.6)));
var mB=Math.max(2,Math.round((p.mB||p.mA||10)*(0.4+ds*0.6)));
switch(gen){
case ‘add’:{var a=rnd(1,mA),b=rnd(1,mB);return{q:a+’ + ‘+b+’ = ?’,ans:a+b,opts:mkOpts(a+b,Math.max(3,Math.round((a+b)*.2)))};}
case ‘sub’:{var a=rnd(mA>>1,mA),b=rnd(1,a);return{q:a+’ − ‘+b+’ = ?’,ans:a-b,opts:mkOpts(a-b,Math.max(3,Math.round(a*.2)))};}
case ‘mulx’:{var a=rnd(2,Math.min(mA,12)),b=rnd(2,Math.min(mB,12));return{q:a+’ × ‘+b+’ = ?’,ans:a*b,opts:mkOpts(a*b,Math.max(4,Math.round(a*b*.2)))};}
case ‘divx’:{var b=rnd(2,Math.min(mA,12)),q=rnd(1,Math.min(mB,10));return{q:(b*q)+’ ÷ ‘+b+’ = ?’,ans:q,opts:mkOpts(q,Math.max(2,Math.round(q*.4)))};}
case ‘fracAll’:{var d=rnd(2,Math.min(mA,10)),n1=rnd(1,d-1),n2=rnd(1,d-1);if(idx%3===0)return{q:n1+’/’+d+’ + ‘+n2+’/’+d+’ = ?’,opts:shuffle([’’+(n1+n2)+’/’+d,’’+(n1+n2+1)+’/’+d,’’+n1+’/’+d,’’+n2+’/’+d]),ans:’’+(n1+n2)+’/’+d};if(idx%3===1){var bigger=(n1>=n2?n1+’/’+d:n2+’/’+d);return{q:n1+’/’+d+’ ou ‘+n2+’/’+d+’: maior?’,opts:shuffle([n1+’/’+d,n2+’/’+d,(n1+1)+’/’+d,Math.max(1,n2-1)+’/’+d]),ans:bigger};}return{q:n1+’/’+d+’ = ?’,opts:shuffle([n1+’ de ‘+d,d+’ de ‘+n1,(n1+1)+’/’+d,n1+’/’+(d+1)]),ans:n1+’ de ‘+d};}
case ‘dec’:{var a=rnd(1,mA),b=rnd(1,9),ans=parseFloat((a+b/10).toFixed(1));return{q:a+’ + 0.’+b+’ = ?’,ans:ans,opts:mkOpts(ans,.5)};}
case ‘pct’:{var base=Math.round(mA/10)*10||100,pct=[10,20,25,50][idx%4],ans=base*pct/100;return{q:pct+’% de ‘+base+’ = ?’,ans:ans,opts:mkOpts(ans,Math.max(5,Math.round(ans*.3)))};}
case ‘alg1’:{var x=rnd(1,mA),b=rnd(1,mB);return{q:‘x + ‘+b+’ = ‘+(x+b)+’, x = ?’,ans:x,opts:mkOpts(x,Math.max(2,Math.round(x*.4)))};}
case ‘alg2’:{var x=rnd(2,mA),a=rnd(2,6),b=rnd(1,mB);return{q:a+‘x + ‘+b+’ = ‘+(a*x+b)+’, x = ?’,ans:x,opts:mkOpts(x,3)};}
case ‘sys’:{var x=rnd(1,mA),y=rnd(1,mB);return{q:‘x+y=’+(x+y)+’, x−y=’+(x-y)+’. x=?’,ans:x,opts:mkOpts(x,3)};}
case ‘quad’:{var r1=rnd(1,mA),r2=rnd(1,mA),bb=-(r1+r2),c=r1*r2;return{q:‘x²’+(bb>=0?’+’:’’)+bb+‘x+’+c+’=0?’,ans:r1,opts:mkOpts(r1,3)};}
case ‘geo’:{var l=rnd(2,mA),w=rnd(2,mA);if(idx%3===0)return{q:‘Área ‘+l+‘×’+w+’?’,ans:l*w,opts:mkOpts(l*w,Math.max(8,Math.round(l*w*.3)))};if(idx%3===1)return{q:‘Perímetro ‘+l+‘×’+w+’?’,ans:2*(l+w),opts:mkOpts(2*(l+w),Math.max(5,(l+w)>>1))};var r=rnd(1,10);return{q:‘Área círculo r=’+r+’? (π≈3.14)’,ans:Math.round(3.14*r*r),opts:mkOpts(Math.round(3.14*r*r),Math.max(10,Math.round(3.14*r*r*.3)))};}
case ‘pit’:{var pairs=[[3,4,5],[5,12,13],[8,15,17],[7,24,25]];var pair=pairs[idx%4];var aa=pair[0],bb=pair[1],cc=pair[2];if(idx%3===0)return{q:‘b=’+bb+’, c=’+cc+’. a=?’,ans:aa,opts:mkOpts(aa,3)};if(idx%3===1)return{q:‘a=’+aa+’, c=’+cc+’. b=?’,ans:bb,opts:mkOpts(bb,4)};return{q:‘a=’+aa+’, b=’+bb+’. hip=?’,ans:cc,opts:mkOpts(cc,3)};}
case ‘trig’:{var angs=[{a:30,s:.5,c:.87,t:.58},{a:45,s:.71,c:.71,t:1},{a:60,s:.87,c:.5,t:1.73}];var f=angs[idx%3];var tp=[‘sin’,‘cos’,‘tan’][idx%3];var val=[f.s,f.c,f.t][idx%3];return{q:tp+’(’+f.a+‘°)?’,ans:String(val),opts:shuffle([String(val)].concat([.5,.71,.87,1,1.73].filter(function(v){return v!==val;}).slice(0,3).map(String)))};}
case ‘stat’:{var ns=[];for(var k=0;k<5;k++)ns.push(rnd(1,20));if(idx%3===0){var avg=Math.round(ns.reduce(function(s,v){return s+v;},0)/ns.length);return{q:‘Média [’+ns.join(’,’)+’]?’,ans:avg,opts:mkOpts(avg,Math.max(3,avg>>2))};}if(idx%3===1){var s2=ns.slice().sort(function(a,b){return a-b;});return{q:‘Mediana [’+ns.join(’,’)+’]?’,ans:s2[2],opts:mkOpts(s2[2],3)};}var mo=ns.reduce(function(a,b){return ns.filter(function(v){return v===a;}).length>=ns.filter(function(v){return v===b;}).length?a:b;});return{q:‘Moda [’+ns.join(’,’)+’]?’,ans:mo,opts:mkOpts(mo,3)};}
case ‘prob’:{var f=[[1,6,‘dado=6’],[1,2,‘cara’],[4,52,‘ás’]];var fi=f[idx%3];return{q:‘P(’+fi[2]+’)=?’,ans:fi[0]+’/’+fi[1],opts:shuffle([fi[0]+’/’+fi[1],(fi[0]+1)+’/’+fi[1],fi[0]+’/’+(fi[1]+1),(fi[0]*2)+’/’+fi[1]])};}
case ‘pgpa’:{if(idx%2===0){var a=rnd(1,10),d=rnd(2,8),n=rnd(3,8);return{q:‘PA a₁=’+a+’, d=’+d+’, n=’+n+’. aₙ=?’,ans:a+(n-1)*d,opts:mkOpts(a+(n-1)*d,Math.max(3,d*2))};}var a=rnd(1,4),q=rnd(2,3),n=rnd(3,5);return{q:‘PG a₁=’+a+’, q=’+q+’, n=’+n+’. aₙ=?’,ans:a*Math.pow(q,n-1),opts:mkOpts(a*Math.pow(q,n-1),Math.max(3,a*2))};}
case ‘mat’:{var a=rnd(1,mA),b=rnd(1,mA),c=rnd(1,mA),d=rnd(1,mA),det=a*d-b*c;return{q:‘det|’+a+’ ‘+b+’; ‘+c+’ ‘+d+’|=?’,ans:det,opts:mkOpts(det,Math.max(3,Math.abs(det)>>1))};}
case ‘poly’:{var a=rnd(1,mA),bb=rnd(-mA,mA),x=rnd(1,4);return{q:‘p(x)=’+a+‘x’+(bb>=0?’+’:’’)+bb+’. p(’+x+’)=?’,ans:a*x+bb,opts:mkOpts(a*x+bb,Math.max(3,mA))};}
default:{var a=rnd(1,10),b=rnd(1,10);return{q:a+’ + ‘+b+’ = ?’,ans:a+b,opts:mkOpts(a+b,4)};}
}
}

// ══════════════════════════════════════════
// TABU GAME
// ══════════════════════════════════════════
function TABU_LEVELS(){
var d={pt:{easy:‘Fácil’,med:‘Médio’,hard:‘Difícil’,hidden:‘Número Oculto’,frac:‘Frações’,mixEasy:‘Mix Fácil’,mixHard:‘Mix Difícil’},en:{easy:‘Easy’,med:‘Medium’,hard:‘Hard’,hidden:‘Hidden Number’,frac:‘Fractions’,mixEasy:‘Easy Mix’,mixHard:‘Hard Mix’},de:{easy:‘Leicht’,med:‘Mittel’,hard:‘Schwer’,hidden:‘Versteckte Zahl’,frac:‘Brüche’,mixEasy:‘Leichter Mix’,mixHard:‘Schwerer Mix’}};
var t=d[P.lang]||d.pt;
return[
{id:‘t-mul-easy’,icon:‘🌱’,name:‘× ‘+t.easy,op:‘mult’,timer:0,lives:99,total:15,mA:5,mB:5,modes:[‘mc’]},
{id:‘t-mul-med’,icon:‘⚡’,name:‘× ‘+t.med,op:‘mult’,timer:12,lives:3,total:20,mA:10,mB:10,modes:[‘mc’,‘type’]},
{id:‘t-mul-hard’,icon:‘🔥’,name:‘× ‘+t.hard,op:‘mult’,timer:8,lives:3,total:20,mA:12,mB:12,modes:[‘type’]},
{id:‘t-div-easy’,icon:‘🌱’,name:‘÷ ‘+t.easy,op:‘div’,timer:0,lives:99,total:15,mA:5,mB:5,modes:[‘mc’]},
{id:‘t-div-med’,icon:‘⚡’,name:‘÷ ‘+t.med,op:‘div’,timer:12,lives:3,total:20,mA:10,mB:10,modes:[‘mc’,‘type’]},
{id:‘t-add-med’,icon:‘⚡’,name:’+/− ‘+t.med,op:‘addsub’,timer:12,lives:3,total:20,mA:99,mB:99,modes:[‘mc’,‘type’]},
{id:‘t-hidden’,icon:‘❓’,name:t.hidden,op:‘hidden’,timer:10,lives:3,total:20,mA:50,mB:50,modes:[‘mc’]},
{id:‘t-frac’,icon:‘½’,name:t.frac,op:‘frac’,timer:0,lives:99,total:15,mA:8,mB:8,modes:[‘mc’]},
{id:‘t-mix-easy’,icon:‘🎯’,name:t.mixEasy,op:‘mix’,timer:0,lives:99,total:20,mA:10,mB:10,modes:[‘mc’]},
{id:‘t-mix-hard’,icon:‘🏆’,name:t.mixHard,op:‘mix’,timer:8,lives:3,total:25,mA:12,mB:12,modes:[‘mc’,‘type’]}
];
}
var TS={};var _tabuTab=‘math’;
function tabuLevelSelect(){
document.getElementById(‘tabuHdrTtl’).textContent=‘TabuXada’;
var h=’<div class="tab-switch"><button class="tab-sw-btn'+(_tabuTab==='math'?' on':'')+'" onclick="tabuTab(\'math\')">’+T(‘tabuMath’)+’</button><button class="tab-sw-btn'+(_tabuTab==='lang'?' on':'')+'" onclick="tabuTab(\'lang\')">’+T(‘tabuLang’)+’</button></div>’;
if(_tabuTab===‘math’){
h+=’<div class="sec-h">’+T(‘chooseMode’)+’</div>’;
TABU_LEVELS().forEach(function(lv){
var done=doneHas(lv.id)?‘✅ ‘:’’;
var timerTag=lv.timer>0?’<span class="tag ty">⏱ ‘+lv.timer+‘s</span>’:’<span class="tag tg">’+T(‘noTimer’)+’</span>’;
var col=lv.icon===‘🌱’?’#58cc02,#2d8a00’:lv.icon===‘⚡’?’#ffc800,#d4a800’:lv.icon===‘½’||lv.icon===‘❓’?’#a78bfa,#7c5cbf’:lv.icon===‘🎯’||lv.icon===‘🏆’?’#1cb0f6,#0d6fa8’:’#ff4b4b,#cc0000’;
h+=’<div class="tlvl-card" onclick="tabuStart(\''+lv.id+'\',\'math\')"><div class="tlvl-ic" style="background:linear-gradient(135deg,'+col+')">’+lv.icon+’</div><div style="flex:1"><div class="tlvl-nm">’+done+lv.name+’</div><div class="tlvl-ds">’+timerTag+’</div></div></div>’;
});
}else{
h+=’<div class="sec-h">’+T(‘chooseLang’)+’</div>’;
getLangTargets().forEach(function(tl){
var info=TL(tl);if(!info||!info.name)return;
h+=’<div class="tlvl-card" onclick="tabuStart(\''+tl+'\',\'lang\')"><div class="tlvl-ic" style="background:'+getLangBg(tl)+';font-size:2rem">’+info.flag+’</div><div style="flex:1"><div class="tlvl-nm">’+(doneHas(‘tlang-’+tl)?‘✅ ‘:’’)+info.name+’</div><div class="tlvl-ds">’+T(‘lv’)+’ ‘+getLLvl(‘lang-’+tl)+’ · 20 ‘+T(‘qs’)+’</div></div></div>’;
});
}
document.getElementById(‘tabuBody’).innerHTML=h;
}
function tabuTab(t){_tabuTab=t;tabuLevelSelect();}
function tabuStart(id,mode){
if(P.hearts<=0){toast(‘❤️ ‘+T(‘noHearts’));return;}
if(mode===‘lang’){
var tl=id;
var vocabSets=VOCAB_DB[tl]||VOCAB_DB.en;
var transIdx=getTransIdx();
var allWords=[];
vocabSets.slice(0,4).forEach(function(v){v.words.forEach(function(w){allWords.push({word:w[0],trans:w[transIdx]});});});
var picked=shuffle(allWords).slice(0,20);
TS={lv:{id:‘tlang-’+tl,name:TL(tl).name,lives:3,timer:0,total:picked.length,modes:[‘mc’]},qn:0,pts:0,cc:0,combo:0,lives:3,hist:[],cerr:0,answered:false,langWords:picked,mode:‘lang’};
document.getElementById(‘tabuHdrTtl’).textContent=TL(tl).name;
renderTabuGame();return;
}
var lv=TABU_LEVELS().find(function(l){return l.id===id;});if(!lv)return;
TS={lv:lv,qn:0,pts:0,cc:0,combo:0,lives:lv.lives,hist:[],cerr:0,answered:false,mode:‘math’};
document.getElementById(‘tabuHdrTtl’).textContent=lv.name;
renderTabuGame();
}
function renderTabuGame(){
var s=TS,lv=s.lv;
var livH=lv.lives<99?[0,1,2,3,4].slice(0,Math.min(lv.lives,5)).map(function(i){return i<s.lives?‘❤️’:‘🖤’;}).join(’’):’’;
var h=’<div class="tgame-wrap"><div class="tstats">’;
h+=’<div class="tstat"><div class="tstat-v" style="color:var(--yl)">’+s.pts+’</div><div class="tstat-l">’+T(‘pts’)+’</div></div>’;
h+=’<div class="tstat"><div class="tstat-v" style="color:var(--rd)">’+s.qn+’/’+lv.total+’</div><div class="tstat-l">’+T(‘qs’)+’</div></div>’;
h+=’<div class="tstat"><div class="tstat-v" style="color:var(--gr)">’+s.cc+’</div><div class="tstat-l">’+T(‘hits’)+’</div></div>’;
if(lv.lives<99)h+=’<div class="tstat"><div class="tstat-v" style="font-size:.85rem">’+livH+’</div><div class="tstat-l">’+T(‘livs’)+’</div></div>’;
h+=’</div>’;
h+=’<div class="tprog"><div class="tprogf" id="tprogf" style="width:'+(s.qn/lv.total*100)+'%"></div></div>’;
if(lv.timer>0)h+=’<div class="ttimer"><div class="ttimerb" id="ttimerb" style="width:100%"></div></div>’;
h+=’<div style="text-align:center;min-height:22px;font-size:.8rem;font-weight:900" id="tcombo"></div>’;
h+=’<div class="tcard" id="tcard"></div></div>’;
document.getElementById(‘tabuBody’).innerHTML=h;
tabuNextQ();
}
function tabuNextQ(){
var s=TS,lv=s.lv;
if(s.qn>=lv.total){tabuResult();return;}
s.answered=false;
var q;
if(s.mode===‘lang’){
var w=s.langWords[s.qn%s.langWords.length];
var dis=shuffle(s.langWords.filter(function(x){return x.word!==w.word;})).slice(0,3).map(function(x){return x.trans;});
while(dis.length<3)dis.push(w.trans+’?’);
q={display:w.word,opts:shuffle([w.trans].concat(dis)),ans:w.trans,qmode:‘mc’};
}else{
var qmode=lv.modes[Math.floor(Math.random()*lv.modes.length)];
q=Object.assign({qmode:qmode},tabuGenQ(lv));
}
s.curQ=q;s.tStart=Date.now();
renderTabuQ(q);
if(lv.timer>0)startTabuTimer();
}
function tabuGenQ(lv){
var op=lv.op===‘mix’?[‘mult’,‘div’,‘add’,‘addsub’][Math.floor(Math.random()*4)]:lv.op;
var mA=lv.mA,mB=lv.mB;
if(op===‘mult’){var a=rnd(2,mA),b=rnd(2,mB);return{display:a+’ × ’+b,ans:a*b};}
if(op===‘div’){var b=rnd(2,mB),q=rnd(1,mA);return{display:(b*q)+’ ÷ ‘+b,ans:q};}
if(op===‘addsub’){if(Math.random()<.5){var a=rnd(1,mA),b=rnd(1,mB);return{display:a+’ + ‘+b,ans:a+b};}var b=rnd(1,Math.floor(mA*.5)),a=rnd(b,mA);return{display:a+’ − ‘+b,ans:a-b};}
if(op===‘add’){var a=rnd(1,mA),b=rnd(1,mB);return{display:a+’ + ‘+b,ans:a+b};}
if(op===‘hidden’){var ans=rnd(1,Math.floor(mA*.5)),b=rnd(1,Math.floor(mB*.4));return{display:’? + ‘+b+’ = ‘+(ans+b),ans:ans};}
if(op===‘frac’){var d=rnd(3,mA),n1=rnd(1,d-1),n2=rnd(1,d-1);var bigger=n1>=n2?n1+’/’+d:n2+’/’+d;return{display:n1+’/’+d+’ ou ‘+n2+’/’+d+’?’,opts:shuffle([n1+’/’+d,n2+’/’+d,(n1+1)+’/’+d,Math.max(1,n2-1)+’/’+d]),ans:bigger,qmode:‘mc’};}
var a=rnd(1,mA),b=rnd(1,mB);return{display:a+’ × ‘+b,ans:a*b};
}
function renderTabuQ(q){
var card=document.getElementById(‘tcard’);
var qmode=q.qmode||‘mc’;
var inner=’<div class="q-badge '+(qmode==='type'?'tg':'tb')+'">’+(TS.mode===‘lang’?‘🌍’:‘✦’)+’</div><div class="tq">’+esc(q.display)+’</div>’;
if(qmode===‘mc’||q.opts){
var opts=q.opts||mkOpts(q.ans,Math.max(5,Math.floor(typeof q.ans===‘number’?q.ans*.3:4)));
inner+=’<div class="topts">’+opts.map(function(o){var oa=String(o).replace(/’/g,”\’”);var aa=String(q.ans).replace(/’/g,”\’”);return’<button class="topt" onclick="tabuMC(this,\''+oa+'\',\''+aa+'\')">’+esc(String(o))+’</button>’;}).join(’’)+’</div>’;
}else{
inner+=’<div style="display:flex;flex-direction:column;align-items:center;gap:10px;margin-top:8px"><input class="ttype-inp" id="tabuInp" type="number" inputmode="numeric" placeholder="?" autocomplete="off" onkeydown="if(event.key===\'Enter\')tabuType()"><button style="background:linear-gradient(135deg,var(--rd),var(--or));border:none;border-radius:var(--r);color:#fff;font-family:var(--F);font-size:.88rem;font-weight:900;padding:10px 24px;cursor:pointer;min-height:44px" onclick="tabuType()">’+T(‘check’)+’ →</button></div>’;
setTimeout(function(){var el=document.getElementById(‘tabuInp’);if(el)el.focus();},80);
}
inner+=’<div class="tfb" id="tfb"></div>’;
card.innerHTML=inner;
}
function tabuMC(btn,chosen,correct){if(TS.answered)return;TS.answered=true;killTimer();var ok=String(chosen)===String(correct);document.querySelectorAll(’.topt’).forEach(function(b){b.disabled=true;if(b.textContent.trim()===String(correct).trim())b.classList.add(‘correct’);});btn.classList.add(ok?‘correct’:‘wrong’);tabuFeedback(ok,correct);}
function tabuType(){if(TS.answered)return;var inp=document.getElementById(‘tabuInp’);if(!inp||inp.value.trim()===’’)return;TS.answered=true;killTimer();var ok=Number(inp.value)===TS.curQ.ans;inp.classList.add(ok?‘ok’:‘err’);inp.disabled=true;tabuFeedback(ok,TS.curQ.ans);}
function tabuFeedback(ok,correct){
var s=TS,lv=s.lv;var fb=document.getElementById(‘tfb’);var cb=document.getElementById(‘tcombo’);
if(ok){
s.cc++;s.combo++;
var t=lv.timer>0?Math.max(1,Math.round((lv.timer-(Date.now()-s.tStart)/1000)*10)):10;
s.pts+=t+(s.combo>=3?5:0);
if(fb)fb.innerHTML=’<span class="tfb ok">✅ +’+t+(s.combo>=3?’ 🔥×’+s.combo:’’)+’</span>’;
if(s.combo>=3&&cb)cb.innerHTML=’<span style="display:inline-block;background:linear-gradient(135deg,var(--yl),var(--or));color:#111;font-size:.75rem;font-weight:900;padding:2px 12px;border-radius:99px">🔥 COMBO ×’+s.combo+’!</span>’;
snd(‘ok’);if(!P.acc.ra&&s.combo>=3)confetti(3);
s.hist.push({q:String(s.curQ.display),a:String(correct),ok:true});
}else{
s.combo=0;s.lives=Math.max(0,s.lives-1);s.cerr++;
if(fb)fb.innerHTML=’<span class="tfb err">❌ ‘+esc(String(correct))+’</span>’;
if(cb)cb.innerHTML=’’;snd(‘err’);
s.hist.push({q:String(s.curQ.display),a:String(correct),ok:false});
}
s.qn++;
// Update stats bar live
var statsDiv=document.querySelector(’.tstats’);
if(statsDiv){
var livH=lv.lives<99?[0,1,2,3,4].slice(0,Math.min(lv.lives,5)).map(function(i){return i<s.lives?‘❤️’:‘🖤’;}).join(’’):’’;
statsDiv.innerHTML=’<div class="tstat"><div class="tstat-v" style="color:var(--yl)">’+s.pts+’</div><div class="tstat-l">’+T(‘pts’)+’</div></div><div class="tstat"><div class="tstat-v" style="color:var(--rd)">’+s.qn+’/’+lv.total+’</div><div class="tstat-l">’+T(‘qs’)+’</div></div><div class="tstat"><div class="tstat-v" style="color:var(--gr)">’+s.cc+’</div><div class="tstat-l">’+T(‘hits’)+’</div></div>’+(lv.lives<99?’<div class="tstat"><div class="tstat-v" style="font-size:.85rem">’+livH+’</div><div class="tstat-l">’+T(‘livs’)+’</div></div>’:’’);
}
var pf=document.getElementById(‘tprogf’);if(pf)pf.style.width=(s.qn/lv.total*100)+’%’;
if(s.lives<=0&&lv.lives<99){setTimeout(tabuResult,900);return;}
var nb=document.createElement(‘button’);nb.className=‘tnext’;nb.textContent=s.qn>=lv.total?T(‘result’)+’ →’:T(‘cont’);nb.onclick=function(){if(cb)cb.innerHTML=’’;tabuNextQ();};
var card=document.getElementById(‘tcard’);if(card)card.appendChild(nb);
if(s.qn>=lv.total)setTimeout(tabuResult,1200);
}
function startTabuTimer(){
killTimer();var lv=TS.lv;var rem=lv.timer;
TIMER=setInterval(function(){
rem-=0.1;var pct=Math.max(0,rem/lv.timer*100);
var bar=document.getElementById(‘ttimerb’);if(bar){bar.style.width=pct+’%’;bar.className=‘ttimerb’+(pct<30?’ danger’:pct<60?’ warn’:’’);}
if(rem<=0){killTimer();if(!TS.answered){TS.answered=true;var fb=document.getElementById(‘tfb’);if(fb)fb.innerHTML=’<span class="tfb err">⏰ ‘+T(‘tout’)+’ → ‘+esc(String(TS.curQ.ans))+’</span>’;TS.combo=0;TS.lives=Math.max(0,TS.lives-1);TS.cerr++;TS.qn++;TS.hist.push({q:String(TS.curQ.display),a:String(TS.curQ.ans),ok:false});if(TS.lives<=0&&lv.lives<99){setTimeout(tabuResult,900);return;}setTimeout(tabuNextQ,900);}}
},100);
}
function tabuResult(){
killTimer();var s=TS,lv=s.lv;
var acc=s.qn>0?Math.round(s.cc/s.qn*100):0;
var missed=s.hist.filter(function(h){return!h.ok;});
doneAdd(lv.id);P.xp+=s.pts;P.gems+=Math.floor(s.pts/10);
missed.forEach(function(e){if(!P.errors.find(function(x){return x.q===e.q;}))P.errors.push({topic:‘tabu’,q:e.q,wrong:’?’,right:e.a});});
P.errors=P.errors.slice(-30);save();updStats();if(!P.acc.ra)confetti(6);snd(‘win’);
var h=’<div class="tres"><div class="tres-em">’+(acc>=80?‘🏆’:acc>=60?‘🎯’:‘💪’)+’</div><div class="tres-ttl">’+T(‘result’)+’</div><div class="tres-pts">’+s.pts+’</div><div class="tres-grid"><div class="tres-st"><div class="tres-sv" style="color:var(--gr)">’+s.cc+’</div><div class="tres-sl">’+T(‘hits’)+’</div></div><div class="tres-st"><div class="tres-sv" style="color:var(--rd)">’+s.cerr+’</div><div class="tres-sl">’+T(‘errs’)+’</div></div><div class="tres-st"><div class="tres-sv" style="color:var(--bl)">’+acc+’%</div><div class="tres-sl">’+T(‘acc’)+’</div></div></div>’;
if(missed.length){h+=’<div class="missed-list"><div class="missed-hdr">❌ ‘+T(‘missed’)+’</div>’;missed.slice(0,8).forEach(function(m){h+=’<div class="missed-row"><span>’+esc(m.q)+’</span><span style="color:var(--gr);font-weight:900">’+esc(m.a)+’</span></div>’;});h+=’</div>’;}
h+=’<div style="display:flex;gap:8px;margin-top:12px"><button class="btn-main btn-blue" style="flex:1;font-size:.8rem" onclick="tabuLevelSelect()">’+T(‘chooseLevel’)+’</button><button class="btn-main" style="flex:1;font-size:.8rem" onclick="tabuStart(\''+lv.id+'\',\''+s.mode+'\')">’+T(‘playAgain’)+’</button></div></div>’;
document.getElementById(‘tabuBody’).innerHTML=h;
}

// ══════════════════════════════════════════
// PROFILE
// ══════════════════════════════════════════
var AVATARS=[‘😊’,‘😎’,‘🤩’,‘🥳’,‘🦊’,‘🐼’,‘🐸’,‘🦁’,‘🐯’,‘🤖’,‘👾’,‘🦄’,‘🐉’,‘🌟’,‘🔥’,‘💎’,‘🎯’,‘🚀’,‘⚡’,‘🌈’];
function buildProfile(){
var doneLessons=P.done.length;
var badges=[‘🏆’,‘⭐’,‘🔥’,‘💎’,‘🎯’,‘🌟’,‘🥇’,‘🎖’,‘🏅’,‘🎪’,‘🐍’,‘🔢’,‘🌍’,‘📚’,‘💡’];
var earned=P.badges||[];
var h=’<div class="prof-sec"><div class="prof-hdr"><div class="prof-av-big" onclick="openEditProfile()">’+(P.avatar||‘😊’)+’</div><div class="prof-nm">’+esc(P.name)+’</div><div class="prof-sub">’+P.age+’</div></div>’;
h+=’<div class="sg"><div class="sb"><div class="sv" style="color:var(--yl)">’+P.xp+’</div><div class="sl">’+T(‘xp’)+’</div></div><div class="sb"><div class="sv" style="color:var(--yl)">’+P.gems+’</div><div class="sl">’+T(‘gems’)+’</div></div><div class="sb"><div class="sv" style="color:var(--gr)">’+doneLessons+’</div><div class="sl">’+T(‘lessons’)+’</div></div></div>’;
h+=’<div class="divider"></div>’;
h+=’<div class="sec-h">’+T(‘achievements’)+’</div><div class="bdg-wrap">’+badges.map(function(b){return’<div class="bdg'+(earned.indexOf(b)>=0?'':' lck')+'">’+b+’</div>’;}).join(’’)+’</div>’;
h+=’<div class="divider"></div>’;
h+=’<div class="lang-selector-row"><div class="acc-nm">’+T(‘appLang’)+’</div><div class="lang-opts"><button class="lang-opt-btn'+(P.lang==='pt'?' on':'')+'" onclick="changeLang(\'pt\')">🇧🇷 PT</button><button class="lang-opt-btn'+(P.lang==='en'?' on':'')+'" onclick="changeLang(\'en\')">🇺🇸 EN</button><button class="lang-opt-btn'+(P.lang==='de'?' on':'')+'" onclick="changeLang(\'de\')">🇩🇪 DE</button></div></div>’;
h+=’<div class="divider"></div>’;
h+=’<div class="sec-h">’+T(‘accessibility’)+’</div>’;
h+=’<div class="acc-row"><div><div class="acc-nm">’+T(‘highContrast’)+’</div></div><div class="tog'+(P.acc.hc?' on':'')+'" onclick="togAcc(\'hc\')"></div></div>’;
h+=’<div class="acc-row"><div><div class="acc-nm">’+T(‘largeText’)+’</div></div><div class="tog'+(P.acc.lg?' on':'')+'" onclick="togAcc(\'lg\')"></div></div>’;
h+=’<div class="acc-row"><div><div class="acc-nm">’+T(‘reduceAnim’)+’</div></div><div class="tog'+(P.acc.ra?' on':'')+'" onclick="togAcc(\'ra\')"></div></div>’;
h+=’<div class="divider"></div>’;
h+=’<button class="btn-main btn-red" style="margin-bottom:16px" onclick="resetAll()">’+T(‘resetAll’)+’</button></div>’;
document.getElementById(‘tabProf’).innerHTML=h;
}
function changeLang(l){P.lang=l;save();initApp();buildHome();buildProfile();}
function resetAll(){
showConfirm(T(‘resetAll’)+’?’,function(){
try{localStorage.removeItem(SK);}catch(e){}
P={name:’’,age:‘adult’,avatar:‘😊’,lang:‘pt’,xp:0,gems:100,hearts:5,heartNextReset:nextMidnight(),done:[],errors:[],badges:[],lessonCount:0,langProgress:{},acc:{hc:false,lg:false,ra:false}};
applyAcc();_pcHist=[];NAV={tab:‘home’,courseId:null};
show(‘sOb’);
document.querySelectorAll(’.lang-btn’).forEach(function(b){b.classList.remove(‘on’);});
document.querySelectorAll(’.lang-btn’)[0].classList.add(‘on’);
document.querySelectorAll(’#ageGrid .sel-btn’).forEach(function(b){b.classList.remove(‘on’);});
document.getElementById(‘obName’).value=’’;document.getElementById(‘obBtn’).disabled=true;
_obLang=‘pt’;_obAge=null;
});
}
function openEditProfile(){
var ttlEl=document.getElementById(‘editModalTtl’);
var nmLEl=document.getElementById(‘editNameLbl’);
var avLEl=document.getElementById(‘editAvatarLbl’);
var cancelBtn=document.getElementById(‘editCancelBtn’);
var saveBtn=document.getElementById(‘editSaveBtn’);
if(ttlEl)ttlEl.textContent=T(‘editProfileTitle’);
if(nmLEl)nmLEl.textContent=T(‘editName’);
if(avLEl)avLEl.textContent=T(‘editAvatar’);
if(cancelBtn)cancelBtn.textContent=T(‘cancel’);
if(saveBtn)saveBtn.textContent=T(‘save’);
document.getElementById(‘editNameInp’).value=P.name;
document.getElementById(‘avGrid’).innerHTML=AVATARS.map(function(a){return’<div class="av-opt'+(P.avatar===a?' sel':'')+'" onclick="selAv(\''+a+'\')">’+a+’</div>’;}).join(’’);
document.getElementById(‘editModal’).classList.add(‘on’);
}
function selAv(a){document.querySelectorAll(’.av-opt’).forEach(function(b){b.classList.toggle(‘sel’,b.textContent===a);});}
function saveProfile(){
var nm=document.getElementById(‘editNameInp’).value.trim();if(!nm)return;
var av=document.querySelector(’.av-opt.sel’);
P.name=nm;P.avatar=av?av.textContent:P.avatar;
document.getElementById(‘topAv’).textContent=P.avatar;
document.getElementById(‘topNm’).textContent=P.name;
document.getElementById(‘editModal’).classList.remove(‘on’);
save();buildProfile();toast(T(‘updated’));
}

// ══════════════════════════════════════════
// PLAYGROUND
// ══════════════════════════════════════════
var SNIPS=[
{nm:‘Hello World’,ds:‘First program’,code:‘print(“Hello, World!”)\nprint(“TabuXada!”)’},
{nm:‘Calculator’,ds:‘Basic math’,code:‘a = 15\nb = 4\nprint(f”{a} + {b} = {a+b}”)\nprint(f”{a} * {b} = {a*b}”)’},
{nm:‘For loop’,ds:‘Count 1 to 10’,code:‘for i in range(1, 11):\n    print(i)’},
{nm:‘List’,ds:‘Work with lists’,code:‘fruits = [“banana”, “apple”, “mango”]\nfruits.sort()\nfor f in fruits:\n    print(f)’},
{nm:‘Function’,ds:‘Create a function’,code:‘def greet(name):\n    return f”Hello, {name}!”\nprint(greet(“World”))’},
{nm:‘Fibonacci’,ds:‘Classic sequence’,code:‘def fib(n):\n    a, b = 0, 1\n    for i in range(n):\n        print(a, end=” “)\n        a, b = b, a+b\nfib(10)’},
{nm:‘Prime’,ds:‘Check primes’,code:‘def primo(n):\n    if n<2: return False\n    for i in range(2,n):\n        if n%i==0: return False\n    return True\nfor n in range(2,20):\n    if primo(n): print(n, end=” “)’},
{nm:‘Dictionary’,ds:‘Key and value’,code:‘p = {“name”:“Ana”,“age”:20}\nfor k,v in p.items():\n    print(f”{k}: {v}”)’}
];
function buildPlayground(){
var h=’<div class="sec-h">’+T(‘pgTitle’)+’</div>’;
h+=’<div class="code-wrap"><div class="code-hdr"><div class="cdot" style="background:#ff5f57"></div><div class="cdot" style="background:#fbbf24"></div><div class="cdot" style="background:#28c840"></div><span class="clang">Python 🐍</span></div>’;
h+=’<textarea class="pg-ta" id="pgCode" spellcheck="false" onkeydown="tabInd(event)">print(“Hello, World!”)</textarea>’;
h+=’<div class="code-out"><div class="cout-lbl">Output</div><div class="cout-txt" id="pgOut" style="color:var(--tx3)">’+T(‘runPrompt’)+’</div></div></div>’;
h+=’<div class="pg-btns"><button class="pg-run" onclick="pgRun()">’+T(‘run’)+’</button><button class="pg-clear" onclick="pgClear()">’+T(‘clr’)+’</button></div>’;
h+=’<div class="sec-h" style="margin-top:14px">’+T(‘exs’)+’</div>’;
h+=’<div class="pg-snips">’+SNIPS.map(function(s,i){return’<div class="snip" onclick="pgLoad('+i+')"><div class="snip-nm">’+s.nm+’</div><div class="snip-ds">’+s.ds+’</div></div>’;}).join(’’)+’</div>’;
document.getElementById(‘tabPg’).innerHTML=h;
}
function pgRun(){var ta=document.getElementById(‘pgCode’);if(!ta)return;var r=pyRun(ta.value);var o=document.getElementById(‘pgOut’);if(o){o.textContent=r.output||T(‘noOutput’);o.style.color=r.ok?’#7ee787’:’#ff7b7b’;}}
function pgClear(){var c=document.getElementById(‘pgCode’);if(c)c.value=’’;var o=document.getElementById(‘pgOut’);if(o){o.textContent=’’;o.style.color=‘var(–tx3)’;}}
function pgLoad(i){var s=SNIPS[i];if(s){var c=document.getElementById(‘pgCode’);if(c){c.value=s.code;pgRun();}}}

// ══════════════════════════════════════════
// POWER AI
// ══════════════════════════════════════════
var _pcHist=[];var _pcOpen=false;
function toggleChat(){_pcOpen=!_pcOpen;document.getElementById(‘pchat’).classList.toggle(‘open’,_pcOpen);document.getElementById(‘pfabDot’).classList.remove(‘show’);if(_pcOpen)updPcProgress();}
function pcGreet(){
var msg=P.lang===‘en’?‘Hi ‘+P.name+’! ⚡ I'm Power AI, your smart offline coach. How can I help?’:P.lang===‘de’?‘Hallo ‘+P.name+’! ⚡ Ich bin Power AI. Wie kann ich helfen?’:‘Olá ‘+P.name+’! ⚡ Sou o Power AI. Como posso te ajudar?’;
addMsg(‘ai’,msg);document.getElementById(‘pfabDot’).classList.add(‘show’);
}
function buildPcChips(){
var chips=[T(‘aiHow’),T(‘aiHint’),T(‘aiWeak’),T(‘aiProg’)];
document.getElementById(‘pcChips’).innerHTML=chips.map(function(t){return’<span class=“pc-chip” onclick=“chip('’+t.replace(/’/g,”\’”)+’')”>’+t+’</span>’;}).join(’’);
}
function chip(t){document.getElementById(‘pcInp’).value=t;pcSend();}
function addMsg(who,txt){
var d=document.getElementById(‘pcMsgs’);if(!d)return;
var now=new Date().toLocaleTimeString([],{hour:‘2-digit’,minute:‘2-digit’});
var div=document.createElement(‘div’);div.className=‘pc-msg ‘+who;
div.innerHTML=’<div class="pc-mb">’+esc(txt)+’</div><div class="pc-mt">’+now+’</div>’;
d.appendChild(div);d.scrollTop=d.scrollHeight;
}
function pcSend(){
var inp=document.getElementById(‘pcInp’);if(!inp)return;
var v=inp.value.trim();if(!v)return;
inp.value=’’;inp.style.height=‘auto’;
addMsg(‘usr’,v);
var btn=document.getElementById(‘pcSendBtn’);if(btn)btn.disabled=true;
setTimeout(function(){addMsg(‘ai’,genAIReply(v));if(btn)btn.disabled=false;},400);
}
function genAIReply(q){
var l=P.lang;
var total=0,done=0;
var courses=getCourses();
courses.forEach(function(c){if(!c)return;total+=(c.allLessons||[]).length;done+=(c.allLessons||[]).filter(function(x){return doneHas(x.id);}).length;});
var pct=total?Math.round(done/total*100):0;
var errCount=P.errors.length;
var name=P.name;
var ql=q.toLowerCase();

// topic detection
var isMath=/(mat|tabuada|multiplic|divis|fracção|fração|equação|álgebra|geometri|rechnen|multiplik|gleichung|math|multipl|divis|fraction|equation|algebra|geometry)/i.test(ql);
var isPy=/(python|código|code|progr|função|function|loop|lista|list|variável|variable)/i.test(ql);
var isLang=/(idioma|língua|language|inglês|francês|espanhol|alemão|sprache|french|english|spanish|german|italian)/i.test(ql);
var isProgress=/(progresso|progress|como estou|how am i|wie.*lauf|quanto.*fiz|quanto.*complete)/i.test(ql);
var isWeak=/(fraque|weak|erro|error|schwäche|dificuldade|difficulty|precis.*melhor)/i.test(ql);
var isHint=/(dica|hint|tipp|truque|trick|tip|ajuda|help|como.*aprender|how.*learn)/i.test(ql);
var isMotiv=/(motivação|motivation|desanimai|desistir|difícil|hard|difficult|cansad|tired|quit)/i.test(ql);
var isTabu=/(tabu|jogo|game|pontua|score|record)/i.test(ql);
var isCongrats=/(obrigad|thanks|thank|danke|parabé|congrats|ótimo|great|excelente)/i.test(ql);
var isWhat=/(o que|what|was ist|what is|o que é|explain|explica)/i.test(ql);

// course breakdown
var mathCourse=courses.find(function(c){return c&&c.id===‘math’;});
var codeCourse=courses.find(function(c){return c&&c.id===‘code’;});
var mathDone=mathCourse?(mathCourse.allLessons||[]).filter(function(x){return doneHas(x.id);}).length:0;
var mathTotal=mathCourse?(mathCourse.allLessons||[]).length:0;
var codeDone=codeCourse?(codeCourse.allLessons||[]).filter(function(x){return doneHas(x.id);}).length:0;
var codeTotal=codeCourse?(codeCourse.allLessons||[]).length:0;

// recent errors topic
var recentTopic=’’;
if(P.errors.length>0){var last=P.errors[P.errors.length-1];recentTopic=last.topic||’’;}

var T_=function(k){return T(k);};

var R={
pt:{
progress:function(){
var lines=[‘📊 Aqui está o teu resumo, ‘+name+’:’,
‘• Total: ‘+done+’/’+total+’ lições (’+pct+’% completo)’,
‘• Matemática: ‘+mathDone+’/’+mathTotal,
‘• Python: ‘+codeDone+’/’+codeTotal,
‘• Erros guardados: ‘+errCount,
pct===0?‘Ainda não começaste — abre uma lição agora! 💪’:pct<25?‘Boa largada! Mantém o ritmo diário.’:pct<50?‘Quase a meio! Não pares agora, ‘+name+’.’:pct<75?‘Mais de metade feito 🔥 Impressionante!’:pct<100?‘Quase lá! Falta pouco, ‘+name+’!’:‘🏆 100%! Incrível, ‘+name+’! Tenta o modo TabuXada!’
];return lines.join(’\n’);},
weak:function(){
if(errCount===0)return ‘✅ Sem erros guardados, ‘+name+’! Estás a ir muito bem.\n\nContinua a praticar para manter esse registo limpo! 💎’;
var tips={math:‘Erra muito em matemática? Tenta as lições de revisão ou o modo TabuXada — a repetição é chave!’,code:‘Python a dar trabalho? Volta às lições de conceito (📖) e usa o Playground para experimentar.’,tabu:‘Nos jogos TabuXada, tenta o modo sem timer primeiro para ganhar confiança.’};
return ‘⚠️ Tens ‘+errCount+’ erros para rever, ‘+name+’.\n\n’+(tips[recentTopic]||‘Toca no coração ❤️ no topo para fazer a lição de revisão e recuperar uma vida!’)+’\n\nDica extra: revê os tópicos difíceis nas lições de “Conceito” (📖) antes de avançar.’;},
hintMath:function(){
var hints=[‘🔢 Tabuada do 9: 9×n = junta (n-1) dezenas com (10-n) unidades. Ex: 9×7 = 63, 9×8 = 72!’,‘📐 Pitágoras: 3²+4²=5², 5²+12²=13², 8²+15²=17². Decora estes trios!’,’% Porcentagem: X% de Y = Y × (X÷100). Ex: 30% de 80 = 80×0.3 = 24.’,‘➗ Divisão: pensa sempre na multiplicação inversa. 56÷8=? → 8×?=56 → 7!’,‘½ Frações: para comparar, converte ao mesmo denominador. 2/3 vs 3/4 → 8/12 vs 9/12.’,‘📈 Equações: o que fazes a um lado, fazes ao outro! 3x=15 → x=15÷3=5.’];
return hints[Math.floor(Math.random()*hints.length)];},
hintPy:function(){
var hints=[‘🐍 f-strings: f”Olá {nome}, tens {idade} anos!” — muito mais limpo que concatenar strings!’,‘🔁 List comprehension: quadrados=[x**2 for x in range(10)] — Pythónico e rápido!’,‘📋 enumerate(): for i,v in enumerate(lista): — obtém índice e valor ao mesmo tempo.’,‘🔧 .get() em dicionários: d.get(“chave”, “padrão”) — evita erros KeyError!’,‘⚡ zip(): for a,b in zip(lista1,lista2): — itera duas listas ao mesmo tempo!’,‘🧩 *args e **kwargs: def f(*args, **kwargs) — aceita qualquer número de argumentos!’];
return hints[Math.floor(Math.random()*hints.length)];},
hintLang:function(){return ‘🌍 Para aprender idiomas mais rápido:\n\n1. Faz pelo menos 1 lição de vocabulário por dia\n2. Repete em voz alta — o som ajuda a memorizar\n3. Usa as palavras numa frase própria\n4. Revê os erros antes de avançar\n\nNa TabuXada → Idiomas podes testar o teu vocabulário em modo jogo! 🎮’;},
hint:function(){
var hints=[‘⏱️ 10 minutos por dia supera 2 horas ao fim de semana. Consistência é tudo, ‘+name+’!’,‘🧠 Interleaving: alterna entre matemática e Python na mesma sessão — o cérebro aprende melhor!’,‘😴 Dormir consolida memória. Estuda antes de dormir e revê de manhã!’,‘🎯 Método dos erros: cada erro é uma lição gratuita. Abraça-os, ‘+name+’!’,‘🔥 Combos no TabuXada dão pontos extra — treina velocidade nas lições primeiro!’,‘💎 Completa os baús (💰) no mapa de lições para ganhar gemas grátis!’];
return hints[Math.floor(Math.random()*hints.length)];},
motiv:function(){return ‘💪 Ei, ‘+name+’! Toda a gente sente isso às vezes.\n\nLembra-te: cada lição que completas, mesmo pequena, constrói sinapses novas no teu cérebro. Não é motivação — é biologia!\n\nUm truque: começa por apenas UMA questão. Só uma. Muitas vezes o difícil é começar. 🚀\n\nEstás a ‘+pct+’% — demasiado longe para desistir agora!’;},
tabu:function(){return ‘🎮 Dicas para o TabuXada:\n\n• Modo Fácil (🌱): sem timer, ideal para aquecimento\n• Modo Médio (⚡): 12s por resposta, 3 vidas\n• Modo Difícil (🔥): 8s, escreve a resposta!\n• Combos (3+ acertos seguidos): +5 pontos bónus cada\n• Mix Difícil 🏆: o desafio final!\n\nO teu maior score ainda está por bater, ‘+name+’! 🏆’;},
congrats:function(){return ‘🙌 Obrigado, ‘+name+’! Fico feliz em ajudar.\n\nLembra-te: estou aqui 24/7, mesmo sem internet! Podes perguntar sobre qualquer tópico das lições, pedir dicas, ou simplesmente verificar o teu progresso. ⚡’;},
whatPy:function(){return ‘🐍 Python é uma das linguagens de programação mais populares do mundo!\n\nÉ usada em:\n• Inteligência Artificial e Machine Learning\n• Desenvolvimento web (Django, Flask)\n• Ciência de dados e análise\n• Automação de tarefas\n• Jogos e scripts\n\nNo TabuXada aprendes desde print() básico até classes e algoritmos. Começa pelo curso Python! 💻’;},
whatMath:function(){return ‘🔢 A matemática é a linguagem do universo!\n\nNo TabuXada tens:\n• Aritmética (adição, subtração, multiplicação, divisão)\n• Frações e decimais\n• Álgebra (equações de 1º e 2º grau)\n• Geometria (área, perímetro, Pitágoras)\n• Trigonometria, Estatística, Probabilidade\n• Sequências e Matrizes\n\n300 lições do básico ao avançado! Começa pelo curso Matemática. 📐’;},
general:function(){
var greets=[‘Olá ‘+name+’!’,‘Ei ‘+name+’!’,‘Oi ‘+name+’!’];
var g=greets[Math.floor(Math.random()*greets.length)];
return g+’ Estou aqui para te ajudar. 💡\n\nPodes perguntar-me sobre:\n• O teu progresso (“Como estou?”)\n• Dicas de matemática ou Python\n• Os teus pontos fracos\n• Estratégias de estudo\n• Como funciona o TabuXada\n\nEstás em ‘+pct+’% (’+done+’/’+total+’ lições). ’+(errCount>0?‘Tens ‘+errCount+’ erros para rever!’:‘Sem erros — a arrasar! 🔥’);}
},

```
en:{
  progress:function(){return '📊 Your summary, '+name+':\n• Total: '+done+'/'+total+' lessons ('+pct+'% done)\n• Math: '+mathDone+'/'+mathTotal+'\n• Python: '+codeDone+'/'+codeTotal+'\n• Saved errors: '+errCount+'\n'+(pct===0?'Not started yet — open a lesson now! 💪':pct<25?'Good start! Keep your daily streak.':pct<50?'Almost halfway! Don\'t stop now, '+name+'.':pct<75?'Over halfway 🔥 Impressive!':pct<100?'Almost there! Nearly done, '+name+'!':'🏆 100%! Amazing, '+name+'! Try TabuXada game mode!');},
  weak:function(){if(errCount===0)return '✅ No saved errors, '+name+'! You\'re doing great.\n\nKeep practising to maintain that clean record! 💎';return '⚠️ You have '+errCount+' errors to review, '+name+'.\n\nTap the heart ❤️ at the top to start a review lesson and recover a life!\n\nExtra tip: revisit "Concept" lessons (📖) for tricky topics before moving on.';},
  hintMath:function(){var hints=['🔢 9× trick: 9×n = (n-1) tens + (10-n) units. E.g. 9×7=63, 9×8=72!','📐 Pythagorean triples: 3-4-5, 5-12-13, 8-15-17. Memorise these!','% Percentage: X% of Y = Y × (X÷100). E.g. 30% of 80 = 24.','➗ Division: think multiplication in reverse. 56÷8=? → 8×?=56 → 7!','½ Fractions: to compare, use the same denominator. 2/3 vs 3/4 → 8/12 vs 9/12.','📈 Equations: whatever you do to one side, do to the other! 3x=15 → x=5.'];return hints[Math.floor(Math.random()*hints.length)];},
  hintPy:function(){var hints=['🐍 f-strings: f"Hello {name}, you are {age}!" — cleaner than concatenation!','🔁 List comprehension: squares=[x**2 for x in range(10)] — Pythonic and fast!','📋 enumerate(): for i,v in enumerate(lst): — get index and value at once.','🔧 .get() on dicts: d.get("key","default") — avoids KeyError!','⚡ zip(): for a,b in zip(list1,list2): — iterate two lists simultaneously!'];return hints[Math.floor(Math.random()*hints.length)];},
  hintLang:function(){return '🌍 Language learning tips:\n\n1. Do at least 1 vocab lesson per day\n2. Say words out loud — sound helps memory\n3. Use new words in your own sentence\n4. Review errors before moving on\n\nTabuXada → Languages lets you test vocab in game mode! 🎮';},
  hint:function(){var hints=['⏱️ 10 minutes daily beats 2 hours on weekends. Consistency is everything, '+name+'!','🧠 Interleaving: alternate Math and Python in the same session — your brain learns better!','😴 Sleep consolidates memory. Study before bed and review in the morning!','🎯 Every error is a free lesson. Embrace them, '+name+'!','🔥 Combos in TabuXada give bonus points — train speed in lessons first!','💎 Complete chests (💰) on the lesson map to earn free gems!'];return hints[Math.floor(Math.random()*hints.length)];},
  motiv:function(){return '💪 Hey '+name+'! Everyone feels that way sometimes.\n\nRemember: every lesson you complete builds new synapses in your brain. It\'s not motivation — it\'s biology!\n\nTrick: start with just ONE question. Just one. The hardest part is starting. 🚀\n\nYou\'re at '+pct+'% — too far to quit now!';},
  tabu:function(){return '🎮 TabuXada tips:\n\n• Easy (🌱): no timer, great for warm-up\n• Medium (⚡): 12s per answer, 3 lives\n• Hard (🔥): 8s, type the answer!\n• Combos (3+ correct in a row): +5 bonus points each\n• Hard Mix 🏆: the ultimate challenge!\n\nYour high score is still waiting to be set, '+name+'! 🏆';},
  congrats:function(){return '🙌 Thanks, '+name+'! Happy to help.\n\nRemember: I\'m here 24/7, even offline! Ask me about any lesson topic, request tips, or check your progress anytime. ⚡';},
  whatPy:function(){return '🐍 Python is one of the most popular programming languages in the world!\n\nUsed in:\n• AI and Machine Learning\n• Web development (Django, Flask)\n• Data science and analysis\n• Task automation\n• Games and scripts\n\nIn TabuXada you learn from basic print() to classes and algorithms. Start the Python course! 💻';},
  whatMath:function(){return '🔢 Math is the language of the universe!\n\nIn TabuXada you have:\n• Arithmetic (add, subtract, multiply, divide)\n• Fractions and decimals\n• Algebra (1st and 2nd degree equations)\n• Geometry (area, perimeter, Pythagoras)\n• Trigonometry, Statistics, Probability\n• Sequences and Matrices\n\n300 lessons from basic to advanced! Start the Math course. 📐';},
  general:function(){return 'Hey '+name+'! I\'m here to help. 💡\n\nYou can ask me about:\n• Your progress ("How am I doing?")\n• Math or Python tips\n• Your weak points\n• Study strategies\n• How TabuXada works\n\nYou\'re at '+pct+'% ('+done+'/'+total+' lessons). '+(errCount>0?'You have '+errCount+' errors to review!':'No errors — crushing it! 🔥');}
},

de:{
  progress:function(){return '📊 Deine Übersicht, '+name+':\n• Gesamt: '+done+'/'+total+' Lektionen ('+pct+'% fertig)\n• Mathe: '+mathDone+'/'+mathTotal+'\n• Python: '+codeDone+'/'+codeTotal+'\n• Gespeicherte Fehler: '+errCount+'\n'+(pct===0?'Noch nicht begonnen — öffne jetzt eine Lektion! 💪':pct<50?'Guter Start! Täglich üben, '+name+'.':pct<100?'Mehr als die Hälfte! Weiter so, '+name+'! 🔥':'🏆 100%! Fantastisch, '+name+'!');},
  weak:function(){if(errCount===0)return '✅ Keine gespeicherten Fehler, '+name+'! Du machst das super.\n\nWeiter üben, um diese saubere Bilanz zu halten! 💎';return '⚠️ Du hast '+errCount+' Fehler zu wiederholen, '+name+'.\n\nTippe auf das Herz ❤️ oben für eine Wiederholungslektion und hol dir ein Leben zurück!\n\nExtra-Tipp: Schau dir "Konzept"-Lektionen (📖) für schwierige Themen nochmal an.';},
  hintMath:function(){var hints=['🔢 9er-Trick: 9×n = (n-1) Zehner + (10-n) Einer. z.B. 9×7=63, 9×8=72!','📐 Pythagoreische Tripel: 3-4-5, 5-12-13, 8-15-17. Auswendig lernen!','% Prozent: X% von Y = Y × (X÷100). z.B. 30% von 80 = 24.','➗ Division: denke an die Multiplikation umgekehrt. 56÷8=? → 8×?=56 → 7!'];return hints[Math.floor(Math.random()*hints.length)];},
  hintPy:function(){var hints=['🐍 f-Strings: f"Hallo {name}, du bist {alter}!" — viel sauberer als Verkettung!','🔁 List comprehension: quadrate=[x**2 for x in range(10)] — Pythonisch und schnell!','📋 enumerate(): for i,v in enumerate(lst): — Index und Wert gleichzeitig.','🔧 .get() bei Dicts: d.get("schlüssel","standard") — vermeidet KeyError!'];return hints[Math.floor(Math.random()*hints.length)];},
  hintLang:function(){return '🌍 Sprachtipps:\n\n1. Täglich mind. 1 Vokabellektion\n2. Laut sprechen — Klang hilft beim Merken\n3. Neue Wörter in eigenen Sätzen verwenden\n4. Fehler vor dem Weitermachen wiederholen\n\nTabuXada → Sprachen: teste Vokabeln im Spielmodus! 🎮';},
  hint:function(){var hints=['⏱️ 10 Minuten täglich schlägt 2 Stunden am Wochenende. Konsequenz ist alles, '+name+'!','🧠 Wechsle zwischen Mathe und Python in einer Session — dein Gehirn lernt besser!','😴 Schlaf festigt Erinnerungen. Vor dem Schlafen lernen und morgens wiederholen!','🔥 Combos bei TabuXada geben Bonuspunkte — zuerst Schnelligkeit in Lektionen üben!'];return hints[Math.floor(Math.random()*hints.length)];},
  motiv:function(){return '💪 Hey '+name+'! Das fühlt jeder manchmal.\n\nDenk daran: Jede abgeschlossene Lektion baut neue Synapsen in deinem Gehirn auf. Das ist keine Motivation — das ist Biologie!\n\nTrick: Fang mit nur EINER Frage an. Nur einer. Der schwierigste Teil ist der Anfang. 🚀\n\nDu bist bei '+pct+'% — zu weit, um jetzt aufzugeben!';},
  tabu:function(){return '🎮 TabuXada-Tipps:\n\n• Leicht (🌱): kein Timer, ideal zum Aufwärmen\n• Mittel (⚡): 12s pro Antwort, 3 Leben\n• Schwer (🔥): 8s, Antwort eintippen!\n• Combos (3+ richtig hintereinander): +5 Bonuspunkte\n• Schweres Mix 🏆: die ultimative Herausforderung!\n\nDein Highscore wartet noch auf dich, '+name+'! 🏆';},
  congrats:function(){return '🙌 Danke, '+name+'! Helfe gerne.\n\nDenk daran: Ich bin 24/7 da, auch offline! Frage mich über Lektionsthemen, bitte um Tipps oder prüfe deinen Fortschritt jederzeit. ⚡';},
  whatPy:function(){return '🐍 Python ist eine der beliebtesten Programmiersprachen der Welt!\n\nWird verwendet für:\n• KI und maschinelles Lernen\n• Webentwicklung (Django, Flask)\n• Datenwissenschaft und Analyse\n• Aufgabenautomatisierung\n• Spiele und Skripte\n\nBei TabuXada lernst du von print() bis Klassen und Algorithmen. Starte den Python-Kurs! 💻';},
  whatMath:function(){return '🔢 Mathematik ist die Sprache des Universums!\n\nBei TabuXada hast du:\n• Arithmetik (Add., Sub., Mult., Div.)\n• Brüche und Dezimalzahlen\n• Algebra (Gleichungen 1. und 2. Grades)\n• Geometrie (Fläche, Umfang, Pythagoras)\n• Trigonometrie, Statistik, Wahrscheinlichkeit\n• Folgen und Matrizen\n\n300 Lektionen vom Grundniveau bis Fortgeschritten! 📐';},
  general:function(){return 'Hey '+name+'! Ich bin hier, um zu helfen. 💡\n\nDu kannst mich fragen über:\n• Deinen Fortschritt ("Wie läuft es?")\n• Mathe- oder Python-Tipps\n• Deine Schwachstellen\n• Lernstrategien\n• Wie TabuXada funktioniert\n\nDu bist bei '+pct+'% ('+done+'/'+total+' Lektionen). '+(errCount>0?errCount+' Fehler zu wiederholen!':'Keine Fehler — Feuer! 🔥');}
}
```

};

var r=R[l]||R.pt;
if(isProgress)return r.progress();
if(isWeak)return r.weak();
if(isMotiv)return r.motiv();
if(isCongrats)return r.congrats();
if(isTabu)return r.tabu();
if(isHint&&isMath)return r.hintMath();
if(isHint&&isPy)return r.hintPy();
if(isHint&&isLang)return r.hintLang();
if(isHint)return r.hint();
if(isWhat&&isPy)return r.whatPy();
if(isWhat&&isMath)return r.whatMath();
if(isMath)return r.hintMath();
if(isPy)return r.hintPy();
if(isLang)return r.hintLang();
return r.general();
}

// ══════════════════════════════════════════
// PYTHON EMULATOR
// ══════════════════════════════════════════
function pyRun(code){
var out=’’,ok=true;
try{var js=py2js(code);new Function(’__print’,js)(function(){out+=Array.prototype.slice.call(arguments).map(String).join(’ ‘)+’\n’;});}
catch(e){out=‘Erro: ‘+e.message;ok=false;}
return{output:out.trim(),ok:ok};
}
function py2js(src){
var lines=src.split(’\n’),res=[],vars={},indStack=[0];
function closeAt(ci){while(indStack.length>1&&ci<=indStack[indStack.length-1]){indStack.pop();res.push(’}’);}}
for(var li=0;li<lines.length;li++){
var raw=lines[li];if(!raw.trim()||raw.trim()[0]===’#’){res.push(’’);continue;}
var ci=(raw.match(/^(\s*)/)||[’’,’’])[1].length;
var l=raw.trimStart();
closeAt(ci);
l=l.replace(/\bTrue\b/g,‘true’).replace(/\bFalse\b/g,‘false’).replace(/\bNone\b/g,‘null’);
l=l.replace(/\bnot\s+/g,’!’).replace(/\band\b/g,’&&’).replace(/\bor\b/g,’||’);
l=l.replace(/f([”’])([^”’]*?)\1/g,function(_,q,s){return’`'+s.replace(/\{([^}]+)\}/g,'${$1}')+'`’;});
l=l.replace(/\bprint\s*(([\s\S]*?))\s*$/,function(*,a){a=a.replace(/,\s*end\s*=\s*[”’][^”’]*[”’]/,’’).replace(/,\s*sep\s*=\s*[”’][^”’]*[”’]/,’’);return’__print(’+(a||’””’)+’)’;});
l=l.replace(/\blen\s*(([^)]+))/g,’($1).length’);
l=l.replace(/\brange\s*(([^)]+))/g,function(*,a){var p=a.split(’,’).map(function(s){return s.trim();});return p.length===1?’[…Array(Number(’+p[0]+’)).keys()]’:p.length===2?’[…Array(Math.max(0,’+p[1]+’-’+p[0]+’)).keys()].map(function(i){return i+(’+p[0]+’);})’:‘Array.from({length:Math.max(0,Math.ceil((’+p[1]+’-’+p[0]+’)/(’+p[2]+’)))},function(*,i){return i*(’+p[2]+’)+(’+p[0]+’);})’;});
l=l.replace(/.append\s*(([^)]+))/,’.push($1)’);
l=l.replace(/\babs\s*(/g,‘Math.abs(’);
l=l.replace(/\bint\s*(/g,‘Math.floor(Number(’);
l=l.replace(/.items()/g,’.entries()’);
var isBlock=false;
if(/^if\s+/.test(l)){res.push(‘if(’+l.replace(/^if\s+(.*?)\s*:$/,’$1’).replace(/([^!<>=])=([^=])/g,’$1===$2’).replace(/!===/g,’!==’)+’){’);indStack.push(ci+1);isBlock=true;}
else if(/^elif\s+/.test(l)){if(res.length)res[res.length-1]=res[res.length-1].replace(/}$/,’’);res.push(’} else if(’+l.replace(/^elif\s+(.*?)\s*:$/,’$1’).replace(/([^!<>=])=([^=])/g,’$1===$2’).replace(/!===/g,’!==’)+’){’);indStack.push(ci+1);isBlock=true;}
else if(/^else\s*:/.test(l)){if(res.length)res[res.length-1]=res[res.length-1].replace(/}$/,’’);res.push(’} else {’);indStack.push(ci+1);isBlock=true;}
else if(/^while\s+/.test(l)){res.push(‘while(’+l.replace(/^while\s+(.*?)\s*:$/,’$1’)+’){’);indStack.push(ci+1);isBlock=true;}
else if(/^for\s+(\w+)\s+in\s+/.test(l)){var m=l.match(/^for\s+(\w+)\s+in\s+(.*?)\s*:$/);if(m){res.push(‘for(var ‘+m[1]+’ of ‘+m[2]+’){’);indStack.push(ci+1);isBlock=true;}}
else if(/^def\s+/.test(l)){var m=l.match(/^def\s+(\w+)\s*((.*?))\s*:/);if(m){res.push(‘function ‘+m[1]+’(’+m[2]+’){’);indStack.push(ci+1);isBlock=true;}}
else if(/^return\b/.test(l)){res.push(l.replace(/^return\s*/,‘return ‘)+’;’);}
else if(/^(pass|break|continue)$/.test(l)){res.push({pass:’// pass’,break:‘break;’,continue:‘continue;’}[l]);}
else{
var asgn=l.match(/^([a-zA-Z*]\w*)\s*=(?!=)\s*([\s\S]+)$/);
if(asgn){var nm=asgn[1],val=asgn[2];res.push((vars[nm]?’’:‘var ‘)+nm+’ = ‘+val+’;’);vars[nm]=1;}
else if(/^[a-zA-Z_]\w*\s*(+=|-=|*=|/=|%=)/.test(l)){res.push(l+’;’);}
else{res.push(l+(l.endsWith(’;’)?’’:’;’));}
}
}
while(indStack.length>1){indStack.pop();res.push(’}’);}
return res.join(’\n’);
}

// ══════════════════════════════════════════
// UTILS
// ══════════════════════════════════════════
function rnd(a,b){return Math.floor(Math.random()*(b-a+1))+a;}
function shuffle(a){var r=a.slice();for(var i=r.length-1;i>0;i–){var j=Math.floor(Math.random()*(i+1));var t=r[i];r[i]=r[j];r[j]=t;}return r;}
function mkOpts(ans,range){
var r=Math.max(1,range),set=[ans];
[ans-r,ans-Math.ceil(r/2),ans+Math.ceil(r/2),ans+r,ans-1,ans+1,ans+2,ans-2].forEach(function(v){if(set.length<4&&set.indexOf(v)<0&&typeof v===‘number’)set.push(v);});
while(set.length<4){var v=ans+rnd(-Math.max(3,r*2),Math.max(3,r*2));if(set.indexOf(v)<0)set.push(v);}
return shuffle(set);
}
function esc(s){return String(s).replace(/&/g,’&’).replace(/</g,’<’).replace(/>/g,’>’).replace(/”/g,’"’);}
function tabInd(e){if(e.key===‘Tab’){e.preventDefault();var s=e.target,st=s.selectionStart;s.value=s.value.slice(0,st)+’    ‘+s.value.slice(s.selectionEnd);s.selectionStart=s.selectionEnd=st+4;}}
function snd(t){if(P.acc.ra)return;try{var ctx=new(window.AudioContext||window.webkitAudioContext)(),o=ctx.createOscillator(),g=ctx.createGain();o.connect(g);g.connect(ctx.destination);if(t===‘ok’){o.frequency.setValueAtTime(523,ctx.currentTime);o.frequency.setValueAtTime(659,ctx.currentTime+.1);g.gain.setValueAtTime(.1,ctx.currentTime);g.gain.exponentialRampToValueAtTime(.001,ctx.currentTime+.3);}else if(t===‘err’){o.frequency.setValueAtTime(200,ctx.currentTime);g.gain.setValueAtTime(.08,ctx.currentTime);g.gain.exponentialRampToValueAtTime(.001,ctx.currentTime+.2);}else{o.frequency.setValueAtTime(523,ctx.currentTime);o.frequency.setValueAtTime(784,ctx.currentTime+.12);o.frequency.setValueAtTime(1047,ctx.currentTime+.24);g.gain.setValueAtTime(.1,ctx.currentTime);g.gain.exponentialRampToValueAtTime(.001,ctx.currentTime+.5);}o.start();o.stop(ctx.currentTime+.6);}catch(e){}}
function confetti(n){if(P.acc.ra)return;n=n||5;var w=document.getElementById(‘cfWrap’);if(!w)return;var cols=[’#ff4b4b’,’#1cb0f6’,’#58cc02’,’#ffc800’,’#a78bfa’,’#fb923c’];for(var i=0;i<n*4;i++){var d=document.createElement(‘div’);d.className=‘cf’;var sz=rnd(6,12);d.style.cssText=‘width:’+sz+‘px;height:’+sz+‘px;background:’+cols[rnd(0,cols.length-1)]+’;left:’+rnd(5,95)+’%;top:-10px;border-radius:’+(Math.random()>.5?‘50%’:‘2px’)+’;animation-duration:’+rnd(8,14)/10+‘s;animation-delay:’+rnd(0,5)/10+‘s’;w.appendChild(d);setTimeout(function(){if(d.parentNode)d.parentNode.removeChild(d);},1600);}}
function toast(msg,ms){ms=ms||2500;var t=document.getElementById(‘toast’);if(!t)return;t.textContent=msg;t.classList.add(‘on’);setTimeout(function(){t.classList.remove(‘on’);},ms);}

// ══════════════════════════════════════════
// BOOT
// ══════════════════════════════════════════
(function init(){
if(load()){applyAcc();show(‘sApp’);initApp();}
else{document.getElementById(‘obBtn’).disabled=true;_obLang=‘pt’;P.lang=‘pt’;}
})();
</script>

</body>
</html>
