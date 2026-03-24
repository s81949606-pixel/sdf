<!DOCTYPE html>
<html lang="ru" class="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>Супраграм</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;-webkit-tap-highlight-color:transparent}
:root{--bg:#0e1621;--sb:#17212b;--chat:#0e1621;--out:#2b5278;--in:#182533;--tx:#e1e3e6;--tx2:#6c7883;--ac:#5288c1;--hv:#202b36;--bd:#0f1924;--gn:#5dc452;--rd:#e5533a;--inp:#242f3d;--sc:#2b3845;--mdbg:rgba(0,0,0,.55)}
html.light{--bg:#ffffff;--sb:#ffffff;--chat:#e8ecf0;--out:#effdde;--in:#ffffff;--tx:#222222;--tx2:#707579;--ac:#3390ec;--hv:#f0f0f0;--bd:#e0e0e0;--gn:#5dc452;--rd:#e5533a;--inp:#f0f2f5;--sc:#c4c9cc;--mdbg:rgba(0,0,0,.35)}
html.light .m-o{color:#000}
html.light .m-i{color:#000;border:1px solid var(--bd)}
html.light .m-ft{color:rgba(0,0,0,.35)!important}
html.light .m-sys span{background:#d6e6f2}
html.light .msg-date span{background:#d6e6f2;color:#555}
html.light .pop,.light .rbar{background:#fff;box-shadow:0 2px 16px rgba(0,0,0,.15)}
html.light .pop-i:hover,.light .dri:hover,.light .ci:hover{background:#f0f0f0}
html.light .ci.act{background:var(--ac)}
html.light .ci.act *{color:#fff!important}
html.light .md{background:#fff;color:#222}
html.light .toast{background:#fff;color:#222;box-shadow:0 2px 16px rgba(0,0,0,.12)}
html.light .dr{background:#fff}
html.light .dr-head{background:linear-gradient(135deg,#3390ec,#5bb8ff)}
html.light .dr-head *{color:#fff}
html.light .cpost{background:#fff;border:1px solid var(--bd)}
html.light .auth{background:#e8ecf0}
html.light .auth-c{background:#fff;box-shadow:0 2px 20px rgba(0,0,0,.08)}
html.light input,html.light textarea{color:#222!important}
html.light .rx{background:rgba(0,0,0,.04);color:#222}
html.light .rx:hover{background:rgba(0,0,0,.08)}
html.light .rx.my{background:rgba(51,144,236,.12)}
html.light ::selection{background:var(--ac);color:#fff}
html.light .sticker-panel{background:#fff;border:1px solid var(--bd)}
html.light .stk-tab{color:#555}
html.light .stk-tab.active{color:var(--ac);border-color:var(--ac)}
html.light .stk-item:hover{background:rgba(0,0,0,.05)}
html,body{height:100%;overflow:hidden;overscroll-behavior:none}
body{background:var(--bg);color:var(--tx);transition:background .3s,color .3s}
.hid{display:none!important}
::selection{background:var(--ac);color:#fff}
input,textarea,button{font-family:inherit;outline:none}
::-webkit-scrollbar{width:6px}
::-webkit-scrollbar-track{background:transparent}
::-webkit-scrollbar-thumb{background:var(--sc);border-radius:3px}
.fade-t{transition:opacity .25s ease,transform .25s ease}
.auth{display:flex;align-items:center;justify-content:center;height:100vh;background:var(--bg);transition:background .3s}
.auth-c{background:var(--sb);border-radius:14px;padding:40px 32px;width:380px;max-width:94vw;box-shadow:0 4px 60px rgba(0,0,0,.4);animation:slideUp .5s cubic-bezier(.4,0,.2,1);transition:background .3s}
@keyframes slideUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:none}}
.auth-logo{width:90px;height:90px;margin:0 auto 16px;border-radius:50%;background:linear-gradient(135deg,#5288c1,#6eb0f7);display:flex;align-items:center;justify-content:center;box-shadow:0 4px 20px rgba(82,136,193,.4);transition:transform .3s}
.auth-logo:hover{transform:scale(1.05) rotate(5deg)}
.auth-logo svg{width:46px;height:46px;fill:#fff}
.auth-c h1{text-align:center;font-size:24px;font-weight:700;margin-bottom:4px}
.auth-c .sub{text-align:center;font-size:13px;color:var(--tx2);margin-bottom:20px}
.auth-c .err{color:var(--rd);font-size:13px;text-align:center;min-height:18px;margin-bottom:6px;transition:.3s}
.fi{position:relative;margin-bottom:14px}
.fi input{width:100%;padding:14px 16px 6px;background:var(--inp);border:2px solid transparent;border-radius:10px;color:var(--tx);font-size:15px;transition:border .25s,background .25s}
.fi input:focus{border-color:var(--ac)}
.fi label{position:absolute;left:16px;top:50%;transform:translateY(-50%);font-size:14px;color:var(--tx2);pointer-events:none;transition:.25s}
.fi input:focus~label,.fi input:not(:placeholder-shown)~label{top:8px;font-size:10px;transform:none;color:var(--ac)}
.abtn{width:100%;padding:14px;background:var(--ac);color:#fff;border:none;border-radius:10px;font-size:15px;font-weight:600;cursor:pointer;transition:all .2s;margin-top:6px}
.abtn:hover{filter:brightness(1.1)}
.abtn:active{transform:scale(.97);filter:brightness(.95)}
.alink{text-align:center;margin-top:16px;color:var(--tx2);font-size:13px}
.alink span{color:var(--ac);cursor:pointer;transition:color .15s}
.alink span:hover{text-decoration:underline}
.iface-tog{display:flex;justify-content:center;gap:8px;margin-top:16px}
.iface-btn{padding:8px 18px;border-radius:20px;border:2px solid var(--ac);background:none;color:var(--ac);font-size:13px;cursor:pointer;transition:all .25s;font-weight:600}
.iface-btn.sel{background:var(--ac);color:#fff}
.iface-btn:hover{filter:brightness(1.1)}
.app{display:flex;height:100vh;width:100%;position:relative;transition:all .3s}
.app.phone .sb{width:100%;min-width:100%}
.app.phone .cha{position:fixed;inset:0;z-index:10;transform:translateX(100%);transition:transform .3s cubic-bezier(.4,0,.2,1)}
.app.phone .cha.open{transform:translateX(0)}
.app.phone .ch{padding-left:6px}
.app.phone .ch-back{display:flex!important}
.sb{width:320px;min-width:320px;background:var(--sb);display:flex;flex-direction:column;border-right:1px solid var(--bd);z-index:2;transition:background .3s,border .3s}
.sb-top{padding:8px 10px;display:flex;align-items:center;gap:8px}
.ham{width:40px;height:40px;display:flex;align-items:center;justify-content:center;cursor:pointer;border-radius:50%;transition:all .2s;flex-shrink:0}
.ham:hover{background:var(--hv)}
.ham:active{transform:scale(.9)}
.ham svg{fill:var(--tx2);width:22px;height:22px}
.sb-s{flex:1;position:relative}
.sb-s input{width:100%;padding:9px 12px 9px 36px;background:var(--inp);border:none;border-radius:22px;color:var(--tx);font-size:14px;transition:all .2s}
.sb-s input:focus{background:var(--sc)}
.sb-s input::placeholder{color:#4e5d6b}
.sb-s svg{position:absolute;left:11px;top:50%;transform:translateY(-50%);fill:#4e5d6b;width:16px;height:16px}
.sb-l{flex:1;overflow-y:auto}
.ci{display:flex;align-items:center;padding:8px 10px;cursor:pointer;transition:all .15s;gap:10px}
.ci:hover{background:var(--hv)}
.ci:active{transform:scale(.99);opacity:.85}
.ci.act{background:var(--ac)}
.ci-av{width:50px;height:50px;border-radius:50%;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:20px;font-weight:600;color:#fff;position:relative;overflow:hidden}
.ci-av img{width:100%;height:100%;object-fit:cover;border-radius:50%}
.ci-dot{position:absolute;bottom:2px;right:2px;width:12px;height:12px;background:var(--gn);border-radius:50%;border:2px solid var(--sb)}
.ci-nfo{flex:1;min-width:0}
.ci-nm{font-size:15px;font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;display:flex;align-items:center;gap:4px}
.ci-last{font-size:13px;color:var(--tx2);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;margin-top:2px}
.ci-meta{display:flex;flex-direction:column;align-items:flex-end;gap:5px;flex-shrink:0}
.ci-time{font-size:12px;color:var(--tx2)}
.ci-badge{background:var(--ac);color:#fff;font-size:11px;min-width:20px;height:20px;line-height:20px;text-align:center;padding:0 6px;border-radius:10px;font-weight:700}
.dr-ov{position:fixed;inset:0;background:rgba(0,0,0,.45);z-index:50;opacity:0;pointer-events:none;transition:opacity .3s}
.dr-ov.open{opacity:1;pointer-events:auto}
.dr{position:fixed;top:0;left:0;width:280px;height:100%;background:var(--sb);z-index:51;transform:translateX(-100%);transition:transform .3s cubic-bezier(.4,0,.2,1),background .3s;display:flex;flex-direction:column}
.dr.open{transform:translateX(0)}
.dr-head{padding:18px 16px;background:linear-gradient(135deg,#1a2636,#1e3048);position:relative;overflow:hidden}
.dr-head-bg{position:absolute;inset:0;background-size:cover;background-position:center;opacity:.35}
.dr-av{margin-bottom:8px;position:relative;z-index:1}
.dr-nm{font-size:15px;font-weight:600;display:flex;align-items:center;gap:4px;position:relative;z-index:1}
.dr-u{font-size:12px;color:var(--tx2);margin-top:2px;position:relative;z-index:1}
.dr-items{flex:1;padding:6px 0;overflow-y:auto}
.dri{display:flex;align-items:center;gap:16px;padding:12px 18px;cursor:pointer;transition:all .15s;font-size:15px}
.dri:hover{background:var(--hv)}
.dri:active{opacity:.7}
.dri svg{fill:var(--tx2);width:20px;height:20px;flex-shrink:0}
.dri.red{color:var(--rd)}.dri.red svg{fill:var(--rd)}
.dr-foot{padding:14px 18px;border-top:1px solid var(--bd);font-size:11px;color:#3d4d5c}
.cha{flex:1;display:flex;flex-direction:column;min-width:0;background:var(--chat);transition:background .3s}
.cha-e{flex:1;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:10px;color:var(--tx2);user-select:none}
.cha-e svg{width:120px;height:120px;fill:var(--sc);opacity:.5}
.ch{padding:8px 14px;background:var(--sb);border-bottom:1px solid var(--bd);display:flex;align-items:center;gap:10px;min-height:56px;z-index:3;transition:background .3s}
.ch-back{width:36px;height:36px;display:none;align-items:center;justify-content:center;border-radius:50%;cursor:pointer;transition:.15s;flex-shrink:0;border:none;background:none}
.ch-back:hover{background:var(--hv)}
.ch-back svg{fill:var(--tx2);width:22px;height:22px}
.ch-nfo{flex:1;min-width:0;cursor:pointer}
.ch-nm{font-size:15px;font-weight:600;display:flex;align-items:center;gap:4px}
.ch-st{font-size:12px;color:var(--tx2);margin-top:1px}
.ch-btn{width:38px;height:38px;display:flex;align-items:center;justify-content:center;border-radius:50%;cursor:pointer;transition:all .15s;border:none;background:none;flex-shrink:0}
.ch-btn:hover{background:var(--hv)}
.ch-btn:active{transform:scale(.9)}
.ch-btn svg{fill:var(--tx2);width:20px;height:20px}
.pin-bar{padding:6px 14px;background:var(--sb);border-bottom:1px solid var(--bd);display:flex;align-items:center;gap:8px;cursor:pointer;transition:background .2s;font-size:13px}
.pin-bar:hover{background:var(--hv)}
.pin-bar .pin-icon{color:var(--ac);font-size:16px;flex-shrink:0}
.pin-bar .pin-text{flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:var(--tx)}
.pin-bar .pin-close{color:var(--tx2);cursor:pointer;font-size:16px;padding:4px}
.pin-bar .pin-close:hover{color:var(--rd)}
.edit-bar{padding:6px 14px;background:var(--sb);border-top:1px solid var(--bd);display:flex;align-items:center;gap:8px;font-size:13px}
.edit-bar .edit-label{color:var(--ac);font-weight:600}
.edit-bar .edit-text{flex:1;color:var(--tx2);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.edit-bar .edit-close{color:var(--tx2);cursor:pointer;font-size:16px;padding:4px}
.edit-bar .edit-close:hover{color:var(--rd)}
.fwd-bar{padding:6px 14px;background:var(--sb);border-top:1px solid var(--bd);display:flex;align-items:center;gap:8px;font-size:13px}
.fwd-bar .fwd-label{color:var(--ac);font-weight:600}
.fwd-bar .fwd-text{flex:1;color:var(--tx2);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.fwd-bar .fwd-close{color:var(--tx2);cursor:pointer;font-size:16px;padding:4px}
.fwd-bar .fwd-close:hover{color:var(--rd)}
.msgs{flex:1;overflow-y:auto;padding:8px 14px;display:flex;flex-direction:column;gap:2px;background:var(--chat);transition:background .3s}
.msg-date{text-align:center;padding:6px 0}
.msg-date span{background:#1a2636;padding:4px 12px;border-radius:10px;font-size:12px;color:var(--tx2)}
.m{max-width:65%;padding:7px 11px 20px;border-radius:12px;position:relative;word-wrap:break-word;font-size:14px;line-height:1.45;animation:mIn .25s ease}
@keyframes mIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
.m-o{background:var(--out);align-self:flex-end;border-bottom-right-radius:4px}
.m-i{background:var(--in);align-self:flex-start;border-bottom-left-radius:4px}
.m-tx{white-space:pre-wrap}
.m-edited{font-size:10px;color:rgba(255,255,255,.35);margin-left:4px;font-style:italic}
.m-fwd{border-left:2px solid var(--ac);padding-left:8px;margin-bottom:4px;font-size:12px;color:var(--ac)}
.m-fwd-from{font-weight:600}
.m-ft{position:absolute;bottom:4px;right:8px;display:flex;align-items:center;gap:3px;font-size:11px;color:rgba(255,255,255,.4)}
.m-ck{font-size:13px}
.m-rx{display:flex;gap:3px;margin-top:4px;flex-wrap:wrap}
.rx{padding:2px 8px;background:rgba(255,255,255,.06);border-radius:12px;font-size:13px;cursor:pointer;transition:all .15s;border:1px solid transparent;user-select:none;line-height:1.6}
.rx:hover{background:rgba(255,255,255,.12);transform:scale(1.05)}
.rx.my{border-color:var(--ac);background:rgba(82,136,193,.18)}
.m-gift{text-align:center;padding:16px 20px 26px;min-width:240px;position:relative;overflow:hidden}
.m-gift-anim{position:relative;width:120px;height:120px;margin:0 auto 12px;display:flex;align-items:center;justify-content:center}
.m-gift-circle{position:absolute;inset:0;border-radius:50%;animation:giftPulse 2s ease-in-out infinite}
@keyframes giftPulse{0%,100%{transform:scale(1);opacity:.3}50%{transform:scale(1.15);opacity:.6}}
.m-gift-circle2{position:absolute;inset:8px;border-radius:50%;animation:giftPulse2 2s ease-in-out infinite .5s}
@keyframes giftPulse2{0%,100%{transform:scale(1);opacity:.2}50%{transform:scale(1.1);opacity:.5}}
.m-gift-svg{position:relative;z-index:2;width:80px;height:80px}
.m-gift-sparkles{position:absolute;inset:-10px;pointer-events:none;z-index:3}
.m-gift-sparkle{position:absolute;width:6px;height:6px;border-radius:50%;animation:sparkle 2s ease-in-out infinite}
@keyframes sparkle{0%,100%{opacity:0;transform:scale(0)}50%{opacity:1;transform:scale(1)}}
.m-gift-t{font-size:16px;font-weight:700;background:linear-gradient(135deg,var(--ac),#6eb0f7);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.m-gift-x{font-size:13px;color:var(--tx2);margin-top:6px;font-style:italic}
.m-sys{text-align:center;padding:6px 0;font-size:12px;color:var(--tx2);align-self:center;animation:mIn .25s ease}
.m-sys span{background:#1a2636;padding:3px 10px;border-radius:10px}
.pop{position:fixed;background:#1e2c3a;border-radius:10px;padding:5px 0;z-index:100;box-shadow:0 4px 24px rgba(0,0,0,.5);min-width:200px;animation:popIn .15s cubic-bezier(.4,0,.2,1)}
@keyframes popIn{from{opacity:0;transform:scale(.92) translateY(-4px)}to{opacity:1;transform:none}}
.pop-i{padding:10px 16px;cursor:pointer;font-size:14px;display:flex;align-items:center;gap:10px;transition:background .12s}
.pop-i:hover{background:var(--hv)}
.pop-i.red{color:var(--rd)}
.rbar{position:fixed;background:#1e2c3a;border-radius:20px;padding:4px 8px;display:flex;gap:2px;z-index:100;box-shadow:0 4px 20px rgba(0,0,0,.5);animation:popIn .15s cubic-bezier(.4,0,.2,1)}
.rbtn{font-size:22px;cursor:pointer;padding:4px;border-radius:8px;transition:all .15s;line-height:1}
.rbtn:hover{background:var(--hv);transform:scale(1.25)}
.inp{padding:8px 10px;background:var(--sb);border-top:1px solid var(--bd);display:flex;align-items:center;gap:8px;transition:background .3s}
.inp input[type="text"]{flex:1;padding:10px 14px;background:var(--inp);border:none;border-radius:22px;color:var(--tx);font-size:14px;transition:all .2s}
.inp input[type="text"]::placeholder{color:#4e5d6b}
.inp input[type="text"]:focus{background:var(--sc)}
.attach-btn,.sticker-btn{width:40px;height:40px;border-radius:50%;background:none;border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .2s;flex-shrink:0}
.attach-btn:hover,.sticker-btn:hover{background:var(--hv)}
.attach-btn:active,.sticker-btn:active{transform:scale(.85)}
.attach-btn svg,.sticker-btn svg{fill:var(--tx2);width:22px;height:22px}
.snd{width:40px;height:40px;border-radius:50%;background:var(--ac);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .2s;flex-shrink:0}
.snd:hover{filter:brightness(1.1)}
.snd:active{transform:scale(.85)}
.snd svg{fill:#fff;width:18px;height:18px}
.sticker-panel{position:absolute;bottom:60px;right:10px;width:340px;height:360px;background:var(--sb);border-radius:14px;box-shadow:0 4px 30px rgba(0,0,0,.5);z-index:20;display:flex;flex-direction:column;animation:popIn .2s ease;overflow:hidden}
.stk-tabs{display:flex;border-bottom:1px solid var(--bd);padding:0 8px;gap:4px;flex-shrink:0;overflow-x:auto}
.stk-tab{padding:10px 12px;font-size:13px;cursor:pointer;color:var(--tx2);border-bottom:2px solid transparent;transition:all .15s;white-space:nowrap;font-weight:500}
.stk-tab.active{color:var(--ac);border-color:var(--ac)}
.stk-tab:hover{color:var(--tx)}
.stk-grid{flex:1;overflow-y:auto;padding:8px;display:grid;grid-template-columns:repeat(4,1fr);gap:6px}
.stk-item{width:100%;aspect-ratio:1;border-radius:10px;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .15s;padding:6px}
.stk-item:hover{background:rgba(255,255,255,.08);transform:scale(1.08)}
.stk-item:active{transform:scale(.95)}
.stk-item svg{width:100%;height:100%}
.m-sticker{width:140px;height:140px;padding:4px}
.m-sticker svg{width:100%;height:100%}
.m.sticker-msg{background:none!important;border:none!important;padding:4px 4px 20px!important;box-shadow:none!important}
.mo{position:fixed;inset:0;background:var(--mdbg);z-index:60;display:flex;align-items:center;justify-content:center;animation:fi .2s ease}
@keyframes fi{from{opacity:0}to{opacity:1}}
.md{background:var(--sb);border-radius:14px;padding:24px;width:420px;max-width:94vw;max-height:85vh;overflow-y:auto;box-shadow:0 10px 50px rgba(0,0,0,.4);animation:mdIn .25s cubic-bezier(.4,0,.2,1);transition:background .3s}
@keyframes mdIn{from{opacity:0;transform:scale(.95) translateY(8px)}to{opacity:1;transform:none}}
.md h2{font-size:18px;font-weight:600;margin-bottom:14px;display:flex;align-items:center;gap:8px}
.md h2 .x{margin-left:auto;cursor:pointer;width:30px;height:30px;display:flex;align-items:center;justify-content:center;border-radius:50%;color:var(--tx2);font-size:18px;transition:all .15s}
.md h2 .x:hover{background:var(--hv);transform:rotate(90deg)}
.md label{display:block;font-size:12px;color:var(--tx2);margin:12px 0 4px;text-transform:uppercase;letter-spacing:.5px}
.md input[type="text"],.md input[type="password"],.md textarea{width:100%;padding:10px 14px;background:var(--inp);border:2px solid transparent;border-radius:8px;color:var(--tx);font-size:14px;transition:border .2s,background .2s}
.md input:focus,.md textarea:focus{border-color:var(--ac)}
.md textarea{resize:vertical;min-height:50px;font-family:inherit}
.btn{padding:11px 20px;background:var(--ac);color:#fff;border:none;border-radius:8px;font-size:14px;font-weight:600;cursor:pointer;transition:all .2s}
.btn:hover{filter:brightness(1.1)}
.btn:active{transform:scale(.97)}
.btn.red{background:var(--rd)}.btn.red:hover{filter:brightness(1.1)}
.btn.outline{background:none;border:2px solid var(--ac);color:var(--ac)}
.btn.outline:hover{background:rgba(82,136,193,.1)}
.av-ops{display:flex;gap:8px;margin-top:6px;flex-wrap:wrap;align-items:center}
.av-o{width:52px;height:52px;border-radius:50%;cursor:pointer;border:3px solid transparent;transition:all .2s;display:flex;align-items:center;justify-content:center;font-size:22px;font-weight:700;color:#fff;overflow:hidden;flex-shrink:0}
.av-o:hover,.av-o.sel{border-color:var(--ac);transform:scale(1.1)}
.av-o img{width:100%;height:100%;object-fit:cover}
.av-upload-btn{width:52px;height:52px;border-radius:50%;cursor:pointer;border:3px dashed var(--ac);display:flex;align-items:center;justify-content:center;font-size:24px;color:var(--ac);transition:all .2s;flex-shrink:0;background:none}
.av-upload-btn:hover{background:rgba(82,136,193,.1);transform:scale(1.1)}
.av-custom-wrap{position:relative;display:inline-flex}
.av-custom-del{position:absolute;top:-4px;right:-4px;width:20px;height:20px;border-radius:50%;background:var(--rd);color:#fff;font-size:12px;cursor:pointer;display:flex;align-items:center;justify-content:center;border:2px solid var(--sb);transition:transform .15s}
.av-custom-del:hover{transform:scale(1.2)}
.gc{display:flex;justify-content:center;gap:16px;margin:14px 0;flex-wrap:wrap}
.gci{display:flex;flex-direction:column;align-items:center;padding:18px 14px;background:var(--inp);border-radius:16px;cursor:pointer;transition:all .3s;width:140px;border:2px solid transparent;position:relative;overflow:hidden}
.gci::before{content:'';position:absolute;inset:0;border-radius:14px;opacity:0;transition:opacity .3s}
.gci:hover,.gci.sel{border-color:var(--ac);transform:scale(1.05)}
.gci.sel::before{opacity:1}
.gci-svg{width:80px;height:80px;margin-bottom:8px;position:relative;z-index:1}
.gci-svg svg{width:100%;height:100%}
.gci-n{font-size:13px;color:var(--tx);font-weight:600;position:relative;z-index:1}
.pg{display:inline-flex;flex-direction:column;align-items:center;padding:8px;background:var(--inp);border-radius:10px;cursor:pointer;margin:3px;position:relative;width:72px;transition:all .15s}
.pg:hover{background:var(--sc);transform:scale(1.05)}
.pg-i{font-size:32px;line-height:1}
.pg.dim{opacity:.35}
.pg-bd{position:absolute;top:3px;right:3px;font-size:9px;background:rgba(0,0,0,.55);padding:2px 5px;border-radius:4px}
.aci{display:flex;align-items:center;padding:10px;gap:10px;cursor:pointer;border-radius:8px;transition:all .15s;margin-bottom:4px}
.aci:hover{background:var(--hv);transform:translateX(2px)}
.aci.cur{background:rgba(82,136,193,.12);border:1px solid var(--ac)}
.cpost{background:var(--in);border-radius:12px;padding:12px;margin-bottom:6px;animation:mIn .25s ease;transition:background .3s,box-shadow .3s;position:relative}
.cpost.highlight{box-shadow:0 0 0 2px var(--ac);background:rgba(82,136,193,.1)}
.cpost-t{font-size:14px;line-height:1.5;margin-bottom:6px;white-space:pre-wrap}
.cpost-m{display:flex;align-items:center;gap:10px;font-size:12px;color:var(--tx2)}
.cpost-rx{display:flex;gap:3px;margin-top:6px;flex-wrap:wrap}
.cpost-pinned{position:absolute;top:6px;right:8px;font-size:11px;color:var(--ac);display:flex;align-items:center;gap:3px}
.sr{display:flex;align-items:center;padding:9px 12px;cursor:pointer;gap:10px;transition:all .15s}
.sr:hover{background:var(--hv)}
.sr:active{opacity:.7}
.sec{padding:8px 12px;color:#4e5d6b;font-size:11px;text-transform:uppercase;letter-spacing:.6px;display:flex;justify-content:space-between;align-items:center}
.sec span{color:var(--ac);text-transform:none;cursor:pointer;font-size:12px;letter-spacing:0}
.sec span:hover{text-decoration:underline}
.cfw{position:fixed;inset:0;pointer-events:none;z-index:200;overflow:hidden}
.cf{position:absolute;opacity:.9;will-change:transform}
.toast{position:fixed;bottom:30px;left:50%;transform:translateX(-50%) translateY(20px);background:#1e2c3a;color:var(--tx);padding:10px 22px;border-radius:10px;font-size:14px;z-index:300;box-shadow:0 4px 20px rgba(0,0,0,.4);animation:toastIn .35s cubic-bezier(.4,0,.2,1) forwards;pointer-events:none}
@keyframes toastIn{from{opacity:0;transform:translateX(-50%) translateY(30px)}to{opacity:1;transform:translateX(-50%) translateY(0)}}
.vf{color:var(--ac)!important}
.adm-u{display:flex;align-items:center;gap:10px;padding:8px 10px;border-radius:8px;transition:all .15s;margin-bottom:4px}
.adm-u:hover{background:var(--hv)}
.adm-u .vfb{cursor:pointer;padding:4px 10px;border-radius:6px;font-size:12px;border:1px solid var(--ac);color:var(--ac);background:none;transition:all .2s}
.adm-u .vfb:hover{background:var(--ac);color:#fff}
.theme-tog{display:flex;gap:8px;margin-top:6px}
.theme-btn{flex:1;padding:10px;border-radius:8px;border:2px solid transparent;background:var(--inp);cursor:pointer;text-align:center;font-size:13px;font-weight:600;color:var(--tx);transition:all .2s}
.theme-btn:hover{border-color:var(--ac);opacity:.85}
.theme-btn.sel{border-color:var(--ac);background:rgba(82,136,193,.15)}
.if-tog{display:flex;gap:8px;margin-top:6px}
.if-btn{flex:1;padding:10px;border-radius:8px;border:2px solid transparent;background:var(--inp);cursor:pointer;text-align:center;font-size:13px;font-weight:600;color:var(--tx);transition:all .2s}
.if-btn:hover{border-color:var(--ac);opacity:.85}
.if-btn.sel{border-color:var(--ac);background:rgba(82,136,193,.15)}
.typing{font-size:12px;color:var(--ac);font-style:italic;animation:blink 1.2s infinite}
@keyframes blink{0%,100%{opacity:.4}50%{opacity:1}}
.prv-row{display:flex;align-items:center;justify-content:space-between;padding:10px 0;border-bottom:1px solid var(--bd)}
.prv-row:last-child{border:none}
.prv-label{font-size:14px;flex:1}
.prv-sub{font-size:11px;color:var(--tx2);margin-top:2px}
.prv-tog{width:44px;height:24px;border-radius:12px;background:var(--sc);cursor:pointer;position:relative;transition:background .25s;flex-shrink:0}
.prv-tog.on{background:var(--ac)}
.prv-tog::after{content:'';position:absolute;top:2px;left:2px;width:20px;height:20px;border-radius:50%;background:#fff;transition:transform .25s;box-shadow:0 1px 3px rgba(0,0,0,.3)}
.prv-tog.on::after{transform:translateX(20px)}
.exc-list{margin-top:6px;padding:4px 0}
.exc-item{display:flex;align-items:center;gap:8px;padding:4px 8px;background:var(--inp);border-radius:6px;margin:3px 0;font-size:13px}
.exc-rm{cursor:pointer;color:var(--rd);font-size:16px;margin-left:auto;transition:transform .15s}
.exc-rm:hover{transform:scale(1.3)}
.blocked-msg{text-align:center;padding:16px;color:var(--tx2);font-size:13px;background:var(--inp);border-radius:10px;margin:8px 14px}
.m-media{margin:4px 0;max-width:100%;border-radius:8px;overflow:hidden}
.m-media img{max-width:280px;max-height:300px;border-radius:8px;cursor:pointer;display:block;transition:opacity .2s}
.m-media img:hover{opacity:.9}
.m-media video{max-width:280px;max-height:300px;border-radius:8px;display:block}
.m-media audio{width:250px;margin:4px 0}
.m-media .m-file{display:flex;align-items:center;gap:8px;padding:8px 12px;background:rgba(255,255,255,.06);border-radius:8px;cursor:pointer;transition:background .15s;text-decoration:none;color:var(--tx)}
.m-media .m-file:hover{background:rgba(255,255,255,.12)}
.m-media .m-file-icon{font-size:28px}
.m-media .m-file-info{flex:1;min-width:0}
.m-media .m-file-name{font-size:13px;font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.m-media .m-file-size{font-size:11px;color:var(--tx2)}
.img-viewer{position:fixed;inset:0;background:rgba(0,0,0,.92);z-index:500;display:flex;align-items:center;justify-content:center;cursor:pointer;animation:fi .2s ease}
.img-viewer img{max-width:95vw;max-height:95vh;object-fit:contain;border-radius:4px}
.prof-av-wrap{position:relative;display:inline-block;cursor:pointer}
.prof-av-wrap .prof-av-edit{position:absolute;bottom:0;right:0;width:30px;height:30px;border-radius:50%;background:var(--ac);display:flex;align-items:center;justify-content:center;border:2px solid var(--sb);cursor:pointer;transition:transform .15s}
.prof-av-wrap .prof-av-edit:hover{transform:scale(1.15)}
.prof-av-wrap .prof-av-edit svg{fill:#fff;width:16px;height:16px}
.dr-av-wrap{position:relative;display:inline-block}
.dr-av-big{width:60px;height:60px;border-radius:50%;overflow:hidden;display:flex;align-items:center;justify-content:center;font-size:26px;font-weight:700;color:#fff}
.dr-av-big img{width:100%;height:100%;object-fit:cover}
.ghost-av{background:linear-gradient(135deg,#555,#888)!important;font-size:24px!important}
.deleted-name{color:var(--tx2)!important;font-style:italic}
.cpost-views{font-size:11px;color:var(--tx2);display:flex;align-items:center;gap:3px}
.cpost-views svg{width:14px;height:14px;fill:var(--tx2)}
.del-acc-btn{width:100%;padding:12px;background:none;border:2px solid var(--rd);color:var(--rd);border-radius:8px;font-size:14px;font-weight:600;cursor:pointer;transition:all .2s;margin-top:14px}
.del-acc-btn:hover{background:var(--rd);color:#fff}
.fwd-list{max-height:300px;overflow-y:auto}
.fwd-item{display:flex;align-items:center;gap:10px;padding:8px 10px;cursor:pointer;border-radius:8px;transition:all .15s;margin-bottom:2px}
.fwd-item:hover{background:var(--hv)}
.fwd-item:active{transform:scale(.98)}
.m.highlight-msg{box-shadow:0 0 0 2px var(--ac);background:rgba(82,136,193,.15)!important;transition:box-shadow .3s,background .3s}
.prof-bg-picker{display:flex;gap:8px;flex-wrap:wrap;margin-top:6px}
.prof-bg-swatch{width:44px;height:44px;border-radius:8px;cursor:pointer;border:3px solid transparent;transition:all .2s}
.prof-bg-swatch:hover,.prof-bg-swatch.sel{border-color:var(--ac);transform:scale(1.1)}
.prof-bg-upload{width:44px;height:44px;border-radius:8px;cursor:pointer;border:3px dashed var(--ac);display:flex;align-items:center;justify-content:center;font-size:20px;color:var(--ac);transition:all .2s;background:none}
.prof-bg-upload:hover{background:rgba(82,136,193,.1)}
.saved-icon{background:linear-gradient(135deg,#7B68EE,#9370DB)!important}
</style>
</head>
<body>

<div id="authScreen" class="auth">
<div class="auth-c">
<div class="auth-logo"><svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg></div>
<h1>Супраграм</h1>
<div class="sub" id="authSub">Создайте аккаунт</div>
<div class="err" id="authErr"></div>
<div id="regB">
<div class="fi"><input id="rNm" placeholder=" "><label>Имя</label></div>
<div class="fi"><input id="rUn" placeholder=" "><label>Username (англ, от 3 букв)</label></div>
<div class="fi"><input id="rPw" type="password" placeholder=" "><label>Пароль (от 4 символов)</label></div>
</div>
<div id="logB" class="hid">
<div class="fi"><input id="lUn" placeholder=" "><label>Username</label></div>
<div class="fi"><input id="lPw" type="password" placeholder=" "><label>Пароль</label></div>
</div>
<button class="abtn" id="authBtn" onclick="doAuth()">Создать аккаунт</button>
<div class="alink">Уже есть аккаунт? <span id="authTog" onclick="togAuth()">Войти</span></div>
<div class="iface-tog">
<button class="iface-btn sel" onclick="preIf('pc',this)">💻 ПК</button>
<button class="iface-btn" onclick="preIf('phone',this)">📱 Телефон</button>
</div>
</div>
</div>

<div id="app" class="app hid">
<div class="dr-ov" id="drOv" onclick="clDr()"></div>
<div class="dr" id="drawer">
<div class="dr-head">
<div class="dr-head-bg" id="drBg"></div>
<div class="dr-av" id="drAv"></div>
<div class="dr-nm" id="drNm"></div>
<div class="dr-u" id="drU"></div>
</div>
<div class="dr-items">
<div class="dri" onclick="clDr();openChat('saved')"><svg viewBox="0 0 24 24"><path d="M17 3H7c-1.1 0-2 .9-2 2v16l7-3 7 3V5c0-1.1-.9-2-2-2z"/></svg>Избранное</div>
<div class="dri" onclick="clDr();modal('profile')"><svg viewBox="0 0 24 24"><path d="M12 12c2.7 0 5-2.3 5-5s-2.3-5-5-5-5 2.3-5 5 2.3 5 5 5zm0 2c-3.3 0-10 1.7-10 5v2h20v-2c0-3.3-6.7-5-10-5z"/></svg>Мой профиль</div>
<div class="dri" onclick="clDr();modal('settings')"><svg viewBox="0 0 24 24"><path d="M19.14 12.94c.04-.31.06-.63.06-.94 0-.31-.02-.63-.06-.94l2.03-1.58c.18-.14.23-.41.12-.61l-1.92-3.32c-.12-.22-.37-.29-.59-.22l-2.39.96c-.5-.38-1.03-.7-1.62-.94l-.36-2.54c-.04-.24-.24-.41-.48-.41h-3.84c-.24 0-.43.17-.47.41l-.36 2.54c-.59.24-1.13.57-1.62.94l-2.39-.96c-.22-.08-.47 0-.59.22L2.74 8.87c-.12.21-.08.47.12.61l2.03 1.58c-.04.31-.06.63-.06.94s.02.63.06.94l-2.03 1.58c-.18.14-.23.41-.12.61l1.92 3.32c.12.22.37.29.59.22l2.39-.96c.5.38 1.03.7 1.62.94l.36 2.54c.05.24.24.41.48.41h3.84c.24 0 .44-.17.47-.41l.36-2.54c.59-.24 1.13-.56 1.62-.94l2.39.96c.22.08.47 0 .59-.22l1.92-3.32c.12-.22.07-.47-.12-.61l-2.01-1.58zM12 15.6c-1.98 0-3.6-1.62-3.6-3.6s1.62-3.6 3.6-3.6 3.6 1.62 3.6 3.6-1.62 3.6-3.6 3.6z"/></svg>Настройки</div>
<div class="dri" onclick="clDr();modal('privacy')"><svg viewBox="0 0 24 24"><path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm0 10.99h7c-.53 4.12-3.28 7.79-7 8.94V12H5V6.3l7-3.11v8.8z"/></svg>Конфиденциальность</div>
<div class="dri" onclick="clDr();modal('accounts')"><svg viewBox="0 0 24 24"><path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5c-1.66 0-3 1.34-3 3s1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5C6.34 5 5 6.34 5 8s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05 1.16.84 1.97 1.97 1.97 3.45V19h6v-2.5c0-2.33-4.67-3.5-7-3.5z"/></svg>Аккаунты</div>
<div class="dri" onclick="clDr();modal('newch')"><svg viewBox="0 0 24 24"><path d="M20 2H4c-1.1 0-2 .9-2 2v18l4-4h14c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zm-7 9h-2v2H9v-2H7V9h2V7h2v2h2v2z"/></svg>Создать канал</div>
<div class="dri" onclick="clDr();modal('newgroup')"><svg viewBox="0 0 24 24"><path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5c-1.66 0-3 1.34-3 3s1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5C6.34 5 5 6.34 5 8s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5z"/><path d="M20 15v-3h-2v3h-3v2h3v3h2v-3h3v-2h-3z"/></svg>Создать группу</div>
<div class="dri" id="adminBtn" onclick="clDr();modal('admin')"><svg viewBox="0 0 24 24"><path d="M17 11c.34 0 .67.04 1 .09V6.27L10.5 3 3 6.27v4.91c0 4.54 3.2 8.79 7.5 9.82.55-.13 1.08-.32 1.6-.55-.69-.98-1.1-2.17-1.1-3.45 0-3.31 2.69-6 6-6z"/><path d="M17 13c-2.21 0-4 1.79-4 4s1.79 4 4 4 4-1.79 4-4-1.79-4-4-4zm0 1.38c.62 0 1.12.51 1.12 1.12s-.51 1.12-1.12 1.12-1.12-.51-1.12-1.12.5-1.12 1.12-1.12zm0 5.37c-.93 0-1.74-.46-2.24-1.17.05-.72 1.51-1.08 2.24-1.08s2.19.36 2.24 1.08c-.5.71-1.31 1.17-2.24 1.17z"/></svg>Админ панель</div>
<div class="dri red" onclick="clDr();logout()"><svg viewBox="0 0 24 24"><path d="M17 7l-1.41 1.41L18.17 11H8v2h10.17l-2.58 2.58L17 17l5-5zM4 5h8V3H4c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h8v-2H4V5z"/></svg>Выйти</div>
</div>
<div class="dr-foot">Супраграм v9.0</div>
</div>
<div class="sb">
<div class="sb-top">
<div class="ham" onclick="opDr()"><svg viewBox="0 0 24 24"><path d="M3 18h18v-2H3v2zm0-5h18v-2H3v2zm0-7v2h18V6H3z"/></svg></div>
<div class="sb-s"><svg viewBox="0 0 24 24"><path d="M15.5 14h-.79l-.28-.27C15.41 12.59 16 11.11 16 9.5 16 5.91 13.09 3 9.5 3S3 5.91 3 9.5 5.91 16 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"/></svg><input placeholder="Поиск..." oninput="doSearch(this.value)"></div>
</div>
<div class="sb-l" id="chatList"></div>
</div>
<div class="cha" id="chatArea">
<div class="cha-e" id="emptyChat">
<svg viewBox="0 0 24 24"><path d="M20 2H4c-1.1 0-2 .9-2 2v18l4-4h14c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zm0 14H5.17L4 17.17V4h16v12z"/></svg>
<div style="font-size:18px;font-weight:600">Выберите чат</div>
<div style="font-size:13px">или найдите собеседника в поиске</div>
</div>
<div id="chatView" class="hid" style="display:flex;flex-direction:column;flex:1;min-height:0">
<div class="ch" id="chatHead"></div>
<div id="pinBar" class="hid"></div>
<div class="msgs" id="msgList"></div>
<div id="blockedArea"></div>
<div id="editBar" class="hid"></div>
<div id="fwdBar" class="hid"></div>
<div class="inp" id="inputArea" style="position:relative">
<button class="attach-btn" onclick="attachFile()" title="Прикрепить файл"><svg viewBox="0 0 24 24"><path d="M16.5 6v11.5c0 2.21-1.79 4-4 4s-4-1.79-4-4V5c0-1.38 1.12-2.5 2.5-2.5s2.5 1.12 2.5 2.5v10.5c0 .55-.45 1-1 1s-1-.45-1-1V6H10v9.5c0 1.38 1.12 2.5 2.5 2.5s2.5-1.12 2.5-2.5V5c0-2.21-1.79-4-4-4S7 2.79 7 5v12.5c0 3.04 2.46 5.5 5.5 5.5s5.5-2.46 5.5-5.5V6h-1.5z"/></svg></button>
<button class="sticker-btn" onclick="toggleStickerPanel()" title="Стикеры"><svg viewBox="0 0 24 24"><path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm3.5-9c.83 0 1.5-.67 1.5-1.5S16.33 8 15.5 8 14 8.67 14 9.5s.67 1.5 1.5 1.5zm-7 0c.83 0 1.5-.67 1.5-1.5S9.33 8 8.5 8 7 8.67 7 9.5 7.67 11 8.5 11zm3.5 6.5c2.33 0 4.31-1.46 5.11-3.5H6.89c.8 2.04 2.78 3.5 5.11 3.5z"/></svg></button>
<input type="text" id="msgInp" placeholder="Сообщение..." onkeydown="if(event.key==='Enter')sendMsg()">
<input type="file" id="fileInp" style="display:none" accept="image/*,video/*,audio/*,.pdf,.doc,.docx,.zip,.rar,.txt" onchange="handleFileSelect(this)">
<button class="snd" onclick="sendMsg()"><svg viewBox="0 0 24 24"><path d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/></svg></button>
<div class="sticker-panel hid" id="stickerPanel"></div>
</div>
</div>
</div>
</div>
<div id="mdlB"></div>
<div id="popB"></div>
<div id="imgViewer"></div>

<script>
var AVATARS=[
{id:1,bg:'linear-gradient(135deg,#5288c1,#6eb0f7)'},
{id:2,bg:'linear-gradient(135deg,#e17076,#f7a0a4)'},
{id:3,bg:'linear-gradient(135deg,#7bc862,#a8e063)'},
{id:4,bg:'linear-gradient(135deg,#f5a623,#f7c948)'},
{id:5,bg:'linear-gradient(135deg,#9b59b6,#c39bd3)'},
{id:6,bg:'linear-gradient(135deg,#e67e22,#f39c12)'},
{id:7,bg:'linear-gradient(135deg,#1abc9c,#2ecc71)'},
{id:8,bg:'linear-gradient(135deg,#3498db,#2980b9)'}
];
var PROF_BG_COLORS=['linear-gradient(135deg,#1a2636,#1e3048)','linear-gradient(135deg,#2d1b4e,#4a2d7a)','linear-gradient(135deg,#1b3a2d,#2d6b4a)','linear-gradient(135deg,#3a1b1b,#6b2d2d)','linear-gradient(135deg,#1b2a3a,#2d4a6b)','linear-gradient(135deg,#3a351b,#6b5f2d)','linear-gradient(135deg,#1b3a36,#2d6b63)','linear-gradient(135deg,#3a1b35,#6b2d5f)'];
var GIFT_SNOOP_SVG='<svg viewBox="0 0 120 120"><circle cx="60" cy="60" r="55" fill="#2D1810"/><ellipse cx="38" cy="35" rx="12" ry="18" fill="#3D2817" transform="rotate(-15,38,35)"/><ellipse cx="82" cy="35" rx="12" ry="18" fill="#3D2817" transform="rotate(15,82,35)"/><circle cx="60" cy="62" r="32" fill="#4A3225"/><ellipse cx="60" cy="68" rx="18" ry="14" fill="#D4A574"/><circle cx="48" cy="55" r="4" fill="#111"/><circle cx="72" cy="55" r="4" fill="#111"/><circle cx="48" cy="54" r="1.5" fill="#fff"/><circle cx="72" cy="54" r="1.5" fill="#fff"/><ellipse cx="60" cy="70" rx="4" ry="3" fill="#1a1a1a"/><path d="M50 78 Q60 86 70 78" fill="none" stroke="#1a1a1a" stroke-width="2"/><rect x="35" y="18" width="50" height="12" rx="6" fill="#333" opacity=".7"/><path d="M92 65 C95 62,100 65,100 70 C100 75,92 80,92 80" fill="none" stroke="#4A3225" stroke-width="3" stroke-linecap="round"/><text x="60" y="108" text-anchor="middle" fill="#D4A574" font-size="8" font-weight="bold">SNOOP</text></svg>';
var GIFT_BEAR_SVG='<svg viewBox="0 0 120 120"><circle cx="40" cy="32" r="16" fill="#8B4513"/><circle cx="40" cy="32" r="9" fill="#D2691E"/><circle cx="80" cy="32" r="16" fill="#8B4513"/><circle cx="80" cy="32" r="9" fill="#D2691E"/><ellipse cx="60" cy="65" rx="35" ry="38" fill="#8B4513"/><ellipse cx="60" cy="65" rx="28" ry="32" fill="#A0522D"/><path d="M44 55 Q47 50 52 55" fill="none" stroke="#3E2723" stroke-width="1.8" stroke-linecap="round"/><path d="M68 55 Q71 50 76 55" fill="none" stroke="#3E2723" stroke-width="1.8" stroke-linecap="round"/><ellipse cx="60" cy="78" rx="16" ry="14" fill="#E8C99A"/><circle cx="56" cy="76" r="1.5" fill="#D2691E"/><circle cx="64" cy="76" r="1.5" fill="#D2691E"/><path d="M55 81 Q60 85 65 81" fill="none" stroke="#D2691E" stroke-width="1.2"/><ellipse cx="38" cy="72" rx="8" ry="10" fill="#8B4513" transform="rotate(-10,38,72)"/><ellipse cx="82" cy="72" rx="8" ry="10" fill="#8B4513" transform="rotate(10,82,72)"/><path d="M44 90 Q50 102 56 95" fill="#8B4513"/><path d="M76 90 Q70 102 64 95" fill="#8B4513"/><text x="60" y="108" text-anchor="middle" fill="#D2691E" font-size="5">❤</text></svg>';

var GIFTS=[
{id:'g1',name:'Снуп Дог',svg:GIFT_SNOOP_SVG,colors:['#f5a623','#8B4513','#D4A574','#fff']},
{id:'g2',name:'Мишка',svg:GIFT_BEAR_SVG,colors:['#D2691E','#8B4513','#E8B87A','#fff']}
];

function makeStickerSVG(type){
var svgs={
'hi':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg1" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="60" cy="55" r="38" fill="url(#sg1)" stroke="#E8A800" stroke-width="1.5"/><ellipse cx="45" cy="48" r="5" ry="6" fill="#333"/><ellipse cx="75" cy="48" r="5" ry="6" fill="#333"/><circle cx="43" cy="46" r="2" fill="#fff"/><circle cx="73" cy="46" r="2" fill="#fff"/><path d="M43 67 Q60 82 77 67" fill="none" stroke="#333" stroke-width="3" stroke-linecap="round"/><path d="M95 30 L107 18 L102 32 L114 28" fill="none" stroke="#FFD93D" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Привет!</text></svg>',
'love':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg2" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="60" cy="52" r="36" fill="url(#sg2)" stroke="#E8A800" stroke-width="1.5"/><ellipse cx="48" cy="46" r="4" ry="5" fill="#333"/><ellipse cx="72" cy="46" r="4" ry="5" fill="#333"/><circle cx="46" cy="44" r="1.5" fill="#fff"/><circle cx="70" cy="44" r="1.5" fill="#fff"/><path d="M48 63 Q60 74 72 63" fill="none" stroke="#333" stroke-width="2.5" stroke-linecap="round"/><path d="M35 16 C35 8,47 4,47 14 C47 4,59 8,59 16 L47 28Z" fill="#e5533a"><animateTransform attributeName="transform" type="scale" values="1;1.1;1" dur="0.8s" repeatCount="indefinite" additive="sum" origin="47 20"/></path><path d="M72 12 C72 5,83 1,83 10 C83 1,94 5,94 12 L83 23Z" fill="#e5533a"><animateTransform attributeName="transform" type="scale" values="1;1.1;1" dur="0.8s" repeatCount="indefinite" additive="sum"/></path><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Люблю!</text></svg>',
'laugh':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg3" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="60" cy="55" r="38" fill="url(#sg3)" stroke="#E8A800" stroke-width="1.5"/><path d="M42 46 Q47 40 52 46" fill="none" stroke="#333" stroke-width="3" stroke-linecap="round"/><path d="M68 46 Q73 40 78 46" fill="none" stroke="#333" stroke-width="3" stroke-linecap="round"/><path d="M40 62 Q60 85 80 62" fill="#fff" stroke="#333" stroke-width="2.5"/><path d="M44 62 L76 62" fill="none" stroke="#333" stroke-width="1.5"/><circle cx="32" cy="60" r="6" fill="#F4845F" opacity=".4"/><circle cx="88" cy="60" r="6" fill="#F4845F" opacity=".4"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="11" font-weight="600">Ахахаха</text></svg>',
'sad':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg4" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="60" cy="55" r="38" fill="url(#sg4)" stroke="#E8A800" stroke-width="1.5"/><ellipse cx="46" cy="48" r="4" ry="5" fill="#333"/><ellipse cx="74" cy="48" r="4" ry="5" fill="#333"/><path d="M44 72 Q60 62 76 72" fill="none" stroke="#333" stroke-width="3" stroke-linecap="round"/><path d="M78 48 L85 35" stroke="#5288c1" stroke-width="3" stroke-linecap="round"/><circle cx="87" cy="31" r="3.5" fill="#5288c1"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Грустно</text></svg>',
'cool':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg5" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="60" cy="55" r="38" fill="url(#sg5)" stroke="#E8A800" stroke-width="1.5"/><rect x="34" y="44" width="52" height="14" rx="7" fill="#333"/><rect x="37" y="47" width="19" height="9" rx="4.5" fill="#1a6fc4"/><rect x="64" y="47" width="19" height="9" rx="4.5" fill="#1a6fc4"/><path d="M46 70 Q60 80 74 70" fill="none" stroke="#333" stroke-width="3" stroke-linecap="round"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Круто!</text></svg>',
'wave':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg6" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="55" cy="55" r="36" fill="url(#sg6)" stroke="#E8A800" stroke-width="1.5"/><ellipse cx="43" cy="48" r="4" ry="5" fill="#333"/><ellipse cx="67" cy="48" r="4" ry="5" fill="#333"/><circle cx="41" cy="46" r="1.5" fill="#fff"/><circle cx="65" cy="46" r="1.5" fill="#fff"/><path d="M43 65 Q55 75 67 65" fill="none" stroke="#333" stroke-width="2.5" stroke-linecap="round"/><g transform="translate(88,25) rotate(10)"><path d="M0 0 C4-5,10-3,8 3 C12-2,18 0,16 6 C20 2,26 6,22 12 L14 22 L2 12Z" fill="#FFD93D" stroke="#E8A800" stroke-width="1.5"><animateTransform attributeName="transform" type="rotate" values="-5;10;-5" dur="0.6s" repeatCount="indefinite"/></path></g><text x="60" y="110" text-anchor="middle" fill="#999" font-size="11" font-weight="600">Привет! 👋</text></svg>',
'think':'<svg viewBox="0 0 120 120"><defs><radialGradient id="sg7" cx="50%" cy="40%"><stop offset="0%" stop-color="#FFE066"/><stop offset="100%" stop-color="#FFD93D"/></radialGradient></defs><circle cx="60" cy="55" r="38" fill="url(#sg7)" stroke="#E8A800" stroke-width="1.5"/><ellipse cx="46" cy="48" r="4" ry="5" fill="#333"/><ellipse cx="74" cy="48" r="4" ry="5" fill="#333"/><path d="M48 68 L68 65" fill="none" stroke="#333" stroke-width="3" stroke-linecap="round"/><circle cx="34" cy="74" r="5" fill="#E8A800"/><path d="M78 40 Q83 34 90 40" fill="none" stroke="#333" stroke-width="2.5" stroke-linecap="round"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Хмм...</text></svg>',
'fire':'<svg viewBox="0 0 120 120"><path d="M60 10 C60 10,32 38,32 68 C32 86,44 98,60 100 C76 98,88 86,88 68 C88 38,60 10,60 10Z" fill="#F97316"><animate attributeName="d" values="M60 10 C60 10,32 38,32 68 C32 86,44 98,60 100 C76 98,88 86,88 68 C88 38,60 10,60 10Z;M60 12 C60 12,34 38,34 66 C34 84,45 96,60 98 C75 96,86 84,86 66 C86 38,60 12,60 12Z;M60 10 C60 10,32 38,32 68 C32 86,44 98,60 100 C76 98,88 86,88 68 C88 38,60 10,60 10Z" dur="1s" repeatCount="indefinite"/></path><path d="M60 30 C60 30,42 50,42 68 C42 80,49 88,60 90 C71 88,78 80,78 68 C78 50,60 30,60 30Z" fill="#FBBF24"/><path d="M60 50 C60 50,50 62,50 72 C50 80,54 84,60 85 C66 84,70 80,70 72 C70 62,60 50,60 50Z" fill="#FDE68A"/><text x="60" y="115" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Огонь!</text></svg>',
'ok':'<svg viewBox="0 0 120 120"><circle cx="60" cy="50" r="10" fill="#FFD93D" stroke="#E8A800" stroke-width="3"/><rect x="55" y="60" width="10" height="24" rx="5" fill="#FFD93D" stroke="#E8A800" stroke-width="2"/><path d="M45 68 C32 62,22 56,24 48 C26 40,34 44,38 50 L45 60" fill="#FFD93D" stroke="#E8A800" stroke-width="2"/><path d="M75 60 L80 48 C82 40,92 40,90 50 C88 58,78 62,75 65" fill="#FFD93D" stroke="#E8A800" stroke-width="2"/><path d="M62 84 L62 96" stroke="#E8A800" stroke-width="3.5" stroke-linecap="round"/><path d="M58 84 L53 98" stroke="#E8A800" stroke-width="3.5" stroke-linecap="round"/><text x="60" y="115" text-anchor="middle" fill="#999" font-size="12" font-weight="600">OK!</text></svg>',
'party':'<svg viewBox="0 0 120 120"><circle cx="60" cy="55" r="36" fill="#FFD93D" stroke="#E8A800" stroke-width="1.5"/><ellipse cx="48" cy="48" r="4" ry="5" fill="#333"/><ellipse cx="72" cy="48" r="4" ry="5" fill="#333"/><path d="M42 62 Q60 82 78 62" fill="#fff" stroke="#333" stroke-width="2.5"/><polygon points="24,12 32,35 16,35" fill="#e5533a"/><polygon points="96,10 104,33 88,33" fill="#5288c1"/><circle cx="16" cy="42" r="4" fill="#7bc862"/><circle cx="104" cy="40" r="4" fill="#f5a623"/><circle cx="34" cy="16" r="3" fill="#9b59b6"/><circle cx="88" cy="14" r="3" fill="#e17076"/><rect x="20" y="24" width="6" height="6" fill="#f5a623" transform="rotate(30,23,27)"/><rect x="94" y="22" width="6" height="6" fill="#7bc862" transform="rotate(-20,97,25)"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Ура!</text></svg>',
'sleep':'<svg viewBox="0 0 120 120"><circle cx="60" cy="55" r="38" fill="#FFD93D" stroke="#E8A800" stroke-width="1.5"/><path d="M40 50 L52 50" stroke="#333" stroke-width="3" stroke-linecap="round"/><path d="M68 50 L80 50" stroke="#333" stroke-width="3" stroke-linecap="round"/><ellipse cx="60" cy="68" rx="6" ry="8" fill="#333"/><text x="90" y="28" fill="#5288c1" font-size="18" font-weight="bold">Z</text><text x="100" y="18" fill="#5288c1" font-size="13" font-weight="bold">z</text><text x="108" y="10" fill="#5288c1" font-size="9" font-weight="bold">z</text><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Сплю...</text></svg>',
'shock':'<svg viewBox="0 0 120 120"><circle cx="60" cy="55" r="38" fill="#FFD93D" stroke="#E8A800" stroke-width="1.5"/><circle cx="46" cy="46" r="7" fill="#fff" stroke="#333" stroke-width="2.5"/><circle cx="46" cy="46" r="3.5" fill="#333"/><circle cx="74" cy="46" r="7" fill="#fff" stroke="#333" stroke-width="2.5"/><circle cx="74" cy="46" r="3.5" fill="#333"/><ellipse cx="60" cy="72" rx="9" ry="11" fill="#333"/><path d="M32 34 L24 22" stroke="#FFD93D" stroke-width="4" stroke-linecap="round"/><path d="M88 34 L96 22" stroke="#FFD93D" stroke-width="4" stroke-linecap="round"/><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">ШОК!</text></svg>',
'thumbsup':'<svg viewBox="0 0 120 120"><path d="M40 56 L40 98 L58 98 L58 56Z" fill="#FFD93D" rx="5"/><path d="M58 56 L64 30 C66 24,74 22,76 30 L74 50 L94 50 C100 50,102 55,100 60 L95 92 C92 98,88 100,82 100 L58 100 L58 56Z" fill="#FFD93D" stroke="#E8A800" stroke-width="2"/><path d="M40 56 L40 98 L58 98 L58 56Z" fill="#E8A800" opacity=".2"/><text x="60" y="115" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Класс!</text></svg>',
'heart':'<svg viewBox="0 0 120 120"><path d="M60 100 C22 72,4 48,16 30 C28 12,46 18,60 36 C74 18,92 12,104 30 C116 48,98 72,60 100Z" fill="#e5533a"><animate attributeName="d" values="M60 100 C22 72,4 48,16 30 C28 12,46 18,60 36 C74 18,92 12,104 30 C116 48,98 72,60 100Z;M60 96 C24 70,8 46,20 28 C32 10,48 16,60 34 C72 16,88 10,100 28 C112 46,96 70,60 96Z;M60 100 C22 72,4 48,16 30 C28 12,46 18,60 36 C74 18,92 12,104 30 C116 48,98 72,60 100Z" dur="1.2s" repeatCount="indefinite"/></path><path d="M40 42 Q44 36 50 42" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" opacity=".4"/></svg>',
'star':'<svg viewBox="0 0 120 120"><polygon points="60,10 73,46 112,46 80,70 93,108 60,84 27,108 40,70 8,46 47,46" fill="#FBBF24" stroke="#E8A800" stroke-width="2"><animateTransform attributeName="transform" type="rotate" values="0 60 60;8 60 60;-8 60 60;0 60 60" dur="2s" repeatCount="indefinite"/></polygon></svg>',
'cry':'<svg viewBox="0 0 120 120"><circle cx="60" cy="55" r="38" fill="#FFD93D" stroke="#E8A800" stroke-width="1.5"/><path d="M42 46 Q47 40 52 46" fill="none" stroke="#333" stroke-width="3"/><path d="M68 46 Q73 40 78 46" fill="none" stroke="#333" stroke-width="3"/><path d="M44 72 Q60 62 76 72" fill="none" stroke="#333" stroke-width="2.5" stroke-linecap="round"/><path d="M44 52 C44 52,42 68,38 74 C35 80,42 80,44 74" fill="#5288c1" opacity=".5"><animate attributeName="opacity" values=".5;.8;.5" dur="1.5s" repeatCount="indefinite"/></path><path d="M78 52 C78 52,80 68,84 74 C87 80,80 80,78 74" fill="#5288c1" opacity=".5"><animate attributeName="opacity" values=".5;.8;.5" dur="1.5s" repeatCount="indefinite"/></path><text x="60" y="110" text-anchor="middle" fill="#999" font-size="12" font-weight="600">Плачу...</text></svg>'
};
return svgs[type]||'';
}

var STICKER_PACKS=[
{name:'Привет!',stickers:[
{id:'hi',svg:makeStickerSVG('hi')},{id:'wave',svg:makeStickerSVG('wave')},{id:'cool',svg:makeStickerSVG('cool')},{id:'ok',svg:makeStickerSVG('ok')},
{id:'party',svg:makeStickerSVG('party')},{id:'thumbsup',svg:makeStickerSVG('thumbsup')},{id:'fire',svg:makeStickerSVG('fire')},{id:'star',svg:makeStickerSVG('star')}
]},
{name:'Эмоции',stickers:[
{id:'love',svg:makeStickerSVG('love')},{id:'laugh',svg:makeStickerSVG('laugh')},{id:'sad',svg:makeStickerSVG('sad')},{id:'think',svg:makeStickerSVG('think')},
{id:'sleep',svg:makeStickerSVG('sleep')},{id:'shock',svg:makeStickerSVG('shock')},{id:'cry',svg:makeStickerSVG('cry')},{id:'heart',svg:makeStickerSVG('heart')}
]}
];

var REACTIONS=['👍','❤️','😂','😮','😢','🔥','👎','🎉'];
var cur=null,authMode=0,tmpAv=null,tmpGift=null,poll=null;
var editingMsg=null,forwardMsg=null;
var theme=localStorage.getItem('supra_theme')||'dark';
var iface=localStorage.getItem('supra_iface')||'pc';
var stickerOpen=false;
var lastListHTML='',lastMsgHTML='',lastHeadHTML='',lastPinHTML='';

function esc(s){if(!s)return'';var d=document.createElement('div');d.textContent=s;return d.innerHTML;}
function D(){try{return JSON.parse(localStorage.getItem('supra_data'))||{a:[],m:{},ch:{},gr:{},sh:{},vf:{}};}catch(e){return{a:[],m:{},ch:{},gr:{},sh:{},vf:{}};}}
function S(d){localStorage.setItem('supra_data',JSON.stringify(d));}
function me(){var d=D(),sid=localStorage.getItem('supra_sid');return d.a.find(function(x){return x.u===sid;})||null;}
function isVf(u){var d=D();return d.vf&&d.vf[u];}
function isDeleted(u){var d=D(),acc=d.a.find(function(x){return x.u===u;});return acc&&acc.deleted;}
function isOn(u){var t=localStorage.getItem('supra_on_'+u);return t&&(Date.now()-parseInt(t))<120000;}
function ck(a,b){return[a,b].sort().join('|');}
function svKey(u){return'sv|'+u;}
function canMsg(from,to){var d=D(),acc=d.a.find(function(x){return x.u===to;});if(!acc)return false;if(acc.deleted)return false;if(!acc.prv||!acc.prv.noMsg)return true;if(acc.prv.excMsg&&acc.prv.excMsg.indexOf(from)>=0)return true;return false;}
function canGift(from,to){var d=D(),acc=d.a.find(function(x){return x.u===to;});if(!acc||acc.deleted||!acc.prv||!acc.prv.noGift)return true;if(acc.prv.excGift&&acc.prv.excGift.indexOf(from)>=0)return true;return false;}
function canAddCh(to){var u=me();if(!u)return true;var d=D(),acc=d.a.find(function(x){return x.u===to;});if(!acc||acc.deleted||!acc.prv||!acc.prv.noCh)return true;if(acc.prv.excCh&&acc.prv.excCh.indexOf(u.u)>=0)return true;return false;}
function W(h){return'<div class="mo" onclick="if(event.target===this)clM()"><div class="md">'+h+'</div></div>';}
function toast(t){var e=document.createElement('div');e.className='toast';e.textContent=t;document.body.appendChild(e);setTimeout(function(){e.style.opacity='0';e.style.transition='opacity .3s';setTimeout(function(){e.remove();},300);},2500);}
function fmtTime(ts){var d=new Date(ts);return d.getHours().toString().padStart(2,'0')+':'+d.getMinutes().toString().padStart(2,'0');}
function fmtDate(ts){return new Date(ts).toLocaleDateString('ru-RU',{day:'numeric',month:'long'});}
function applyTheme(){document.documentElement.className=theme;}
function applyIface(){var a=document.getElementById('app');if(!a)return;a.classList.remove('phone');if(iface==='phone')a.classList.add('phone');}

function avHTML(acc,sz){
if(!acc)return'<div class="ci-av" style="width:'+sz+'px;height:'+sz+'px;background:linear-gradient(135deg,#5288c1,#6eb0f7)">?</div>';
if(acc.deleted)return'<div class="ci-av ghost-av" style="width:'+sz+'px;height:'+sz+'px;background:linear-gradient(135deg,#555,#888)">👻</div>';
if(acc.customAv)return'<div class="ci-av" style="width:'+sz+'px;height:'+sz+'px"><img src="'+acc.customAv+'"></div>';
var av=AVATARS.find(function(x){return x.id===acc.av;})||AVATARS[0];
return'<div class="ci-av" style="width:'+sz+'px;height:'+sz+'px;background:'+av.bg+'">'+((acc.nm||'?')[0].toUpperCase())+'</div>';
}

function getDisplayName(acc){if(!acc)return'Неизвестный';if(acc.deleted)return'Аккаунт удалён';return acc.nm;}
function getNick(u,acc){var me2=me();if(me2&&me2.nk&&me2.nk[u])return me2.nk[u];if(acc&&acc.deleted)return'Аккаунт удалён';return acc?acc.nm:u;}
function preIf(v,el){iface=v;localStorage.setItem('supra_iface',v);document.querySelectorAll('.iface-btn').forEach(function(e){e.classList.remove('sel');});el.classList.add('sel');}

// Auth
function togAuth(){
authMode=authMode?0:1;
document.getElementById('regB').classList.toggle('hid');
document.getElementById('logB').classList.toggle('hid');
document.getElementById('authBtn').textContent=authMode?'Войти':'Создать аккаунт';
document.getElementById('authSub').textContent=authMode?'Войдите в аккаунт':'Создайте аккаунт';
document.getElementById('authTog').textContent=authMode?'Создать аккаунт':'Войти';
document.getElementById('authErr').textContent='';
}
function doAuth(){
var err=document.getElementById('authErr'),d=D();
if(authMode===0){
var nm=(document.getElementById('rNm').value||'').trim();
var un=(document.getElementById('rUn').value||'').trim().toLowerCase();
var pw=document.getElementById('rPw').value||'';
if(!nm){err.textContent='Введите имя';return;}
if(!/^[a-z][a-z0-9_]{2,}$/.test(un)){err.textContent='Username: англ буквы/цифры, от 3 символов';return;}
if(pw.length<4){err.textContent='Пароль: минимум 4 символа';return;}
var existing=d.a.find(function(x){return x.u===un;});
if(existing&&!existing.deleted){err.textContent='Username занят';return;}
if(existing&&existing.deleted){var ei=d.a.findIndex(function(x){return x.u===un;});d.a[ei].u='_deleted_'+Date.now();}
d.a.push({u:un,nm:nm,pw:pw,av:1,bio:'',gifts:[],nk:{},prv:{},cr:Date.now(),customAv:null,deleted:false,profBg:null});
// Create saved messages key
if(!d.m[svKey(un)])d.m[svKey(un)]=[];
S(d);localStorage.setItem('supra_sid',un);
startApp();
// Confetti on registration!
doConfetti({colors:['#5288c1','#e17076','#7bc862','#f5a623','#9b59b6','#fff','#FBBF24']});
toast('🎉 Добро пожаловать в Супраграм!');
} else {
var un=(document.getElementById('lUn').value||'').trim().toLowerCase();
var pw=document.getElementById('lPw').value||'';
var acc=d.a.find(function(x){return x.u===un;});
if(!acc){err.textContent='Аккаунт не найден';return;}
if(acc.deleted){err.textContent='Этот аккаунт удалён';return;}
if(acc.pw!==pw){err.textContent='Неверный пароль';return;}
localStorage.setItem('supra_sid',un);
startApp();
}
}

function logout(){
var d=D(),curUser=me();
localStorage.removeItem('supra_sid');cur=null;
if(poll)clearInterval(poll);
var other=d.a.find(function(x){return !x.deleted && (!curUser || x.u!==curUser.u);});
if(other){localStorage.setItem('supra_sid',other.u);startApp();toast('Переключено на @'+other.u);}
else{document.getElementById('app').classList.add('hid');document.getElementById('authScreen').classList.remove('hid');authMode=0;document.getElementById('regB').classList.remove('hid');document.getElementById('logB').classList.add('hid');document.getElementById('authBtn').textContent='Создать аккаунт';document.getElementById('authSub').textContent='Создайте аккаунт';document.getElementById('authTog').textContent='Войти';document.getElementById('authErr').textContent='';}
}

function deleteAccount(){
if(!confirm('Вы уверены что хотите удалить аккаунт? Это действие нельзя отменить!\n\nВаше имя и аватарка будут удалены.'))return;
var u=me(),d=D();
var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai<0)return;
var oldUsername=d.a[ai].u;
d.a[ai].deleted=true;d.a[ai].nm='Аккаунт удалён';d.a[ai].customAv=null;d.a[ai].bio='';d.a[ai].gifts=[];
d.a[ai].u='_deleted_'+Date.now();
if(d.vf&&d.vf[oldUsername])delete d.vf[oldUsername];
S(d);localStorage.removeItem('supra_sid');clM();toast('Аккаунт удалён');logout();
}

function startApp(){
document.getElementById('authScreen').classList.add('hid');
document.getElementById('app').classList.remove('hid');
applyTheme();applyIface();updDr();renderList();showEmpty();
var u=me();
if(u&&u.u==='surpa')document.getElementById('adminBtn').classList.remove('hid');
else document.getElementById('adminBtn').classList.add('hid');
if(poll)clearInterval(poll);
poll=setInterval(function(){
localStorage.setItem('supra_on_'+(me()?me().u:''),Date.now());
smartRenderList();
if(cur)smartRenderMsgs();
},3000);
localStorage.setItem('supra_on_'+me().u,Date.now());
}

// Smart render — only update if content changed (prevents flicker)
function smartRenderList(){var el=document.getElementById('chatList');var h=buildListHTML();if(h!==lastListHTML){lastListHTML=h;el.innerHTML=h;}}
function smartRenderMsgs(){var h=buildMsgsHTML();if(h!==lastMsgHTML){/* don't re-render to avoid flicker during polling */}}

function opDr(){document.getElementById('drawer').classList.add('open');document.getElementById('drOv').classList.add('open');}
function clDr(){document.getElementById('drawer').classList.remove('open');document.getElementById('drOv').classList.remove('open');}
function updDr(){
var u=me();if(!u)return;
var nmHtml=esc(u.nm);
if(u.u==='surpa'||isVf(u.u))nmHtml+=' <span class="vf">✔</span>';
document.getElementById('drNm').innerHTML=nmHtml;
document.getElementById('drU').textContent='@'+u.u;
document.getElementById('drAv').innerHTML=avHTML(u,60);
var bgEl=document.getElementById('drBg');
if(u.profBg){
if(u.profBg.startsWith('data:')||u.profBg.startsWith('http'))bgEl.style.backgroundImage='url('+u.profBg+')';
else bgEl.style.background=u.profBg;
bgEl.style.opacity='.35';
} else {bgEl.style.background='';bgEl.style.backgroundImage='';bgEl.style.opacity='0';}
}

function buildListHTML(){
var u=me(),d=D();if(!u)return'';
var items=[];
// Saved messages
var svMsgs=d.m[svKey(u.u)]||[];
if(svMsgs.length>0||cur==='saved'){
var lastSv=svMsgs[svMsgs.length-1];
items.push({type:'saved',key:'saved',nm:'Избранное',last:lastSv,unread:0,ts:lastSv?lastSv.tm:0});
}
// DMs
Object.keys(d.m).forEach(function(k){
if(k.indexOf('|')<0||k.startsWith('sv|'))return;
if(k.indexOf(u.u)<0)return;
var pp=k.split('|'),oth=pp[0]===u.u?pp[1]:pp[0];
var msgs=d.m[k]||[];var last=msgs[msgs.length-1];
var unread=msgs.filter(function(m){return m.f!==u.u&&!m.rd;}).length;
var acc=d.a.find(function(x){return x.u===oth;});
items.push({type:'dm',key:oth,nm:getNick(oth,acc),acc:acc,last:last,unread:unread,ts:last?last.tm:0,on:isOn(oth)&&!(acc&&acc.deleted)});
});
// Channels
Object.keys(d.ch||{}).forEach(function(cid){
var c=d.ch[cid];if(c.ow!==u.u&&c.mb.indexOf(u.u)<0)return;
var last=c.ps&&c.ps.length?c.ps[c.ps.length-1]:null;
items.push({type:'ch',key:'ch:'+cid,cid:cid,nm:c.nm,last:last,unread:0,ts:last?last.tm:c.cr});
});
// Groups
Object.keys(d.gr||{}).forEach(function(gid){
var g=d.gr[gid];if(g.ow!==u.u&&g.mb.indexOf(u.u)<0)return;
var msgs=d.m['gr:'+gid]||[];var last=msgs[msgs.length-1];
var unread=msgs.filter(function(m){return m.f!==u.u&&!m.rd;}).length;
items.push({type:'gr',key:'gr:'+gid,gid:gid,nm:g.nm,last:last,unread:unread,ts:last?last.tm:g.cr});
});
items.sort(function(a,b){return(b.ts||0)-(a.ts||0);});
var h='';
items.forEach(function(it){
var act=cur===it.key?' act':'';
var avh;
if(it.type==='saved')avh='<div class="ci-av saved-icon" style="width:50px;height:50px">🔖</div>';
else if(it.type==='dm')avh=avHTML(it.acc,50);
else if(it.type==='ch')avh='<div class="ci-av" style="width:50px;height:50px;background:linear-gradient(135deg,#9b59b6,#c39bd3)">📢</div>';
else avh='<div class="ci-av" style="width:50px;height:50px;background:linear-gradient(135deg,#27ae60,#2ecc71)">👥</div>';
var lastTx=it.last?(it.last.tx||'').substring(0,35):'';
if(it.last&&it.last.stickerSvg)lastTx='🎨 Стикер';
if(it.last&&it.last.mediaType)lastTx=it.last.mediaType==='image'?'📷 Фото':it.last.mediaType==='video'?'🎬 Видео':it.last.mediaType==='audio'?'🎵 Аудио':'📎 Файл';
var timeStr=it.last?fmtTime(it.ts):'';
var nmDisplay=it.type==='dm'&&it.acc&&it.acc.deleted?'<span class="deleted-name">Аккаунт удалён</span>':esc(it.nm);
var vfMark='';
if(it.type==='dm'&&it.acc&&!it.acc.deleted&&(it.acc.u==='surpa'||isVf(it.acc.u)))vfMark=' <span class="vf">✔</span>';
h+='<div class="ci'+act+'" onclick="openChat(\''+it.key+'\')" oncontextmenu="chatCtx(event,\''+it.key+'\')">'+avh+'<div class="ci-nfo"><div class="ci-nm">'+nmDisplay+vfMark+'</div><div class="ci-last">'+esc(lastTx)+'</div></div><div class="ci-meta"><div class="ci-time">'+timeStr+'</div>'+(it.unread?'<div class="ci-badge">'+it.unread+'</div>':'')+'</div></div>';
});
return h;
}

function renderList(){var el=document.getElementById('chatList');var h=buildListHTML();lastListHTML=h;el.innerHTML=h;}

function openChat(key){
cur=key;editingMsg=null;forwardMsg=null;hideStickerPanel();
document.getElementById('emptyChat').classList.add('hid');
document.getElementById('chatView').classList.remove('hid');
document.getElementById('chatView').style.display='flex';
document.getElementById('editBar').classList.add('hid');
document.getElementById('fwdBar').classList.add('hid');
if(key.startsWith('ch:')){openCh(key.replace('ch:',''));return;}
var cha=document.getElementById('chatArea');cha.classList.add('open');
renderHead();renderMsgs();renderPinBar();
if(key!=='saved'&&!key.startsWith('gr:'))markRead();
if(key.startsWith('gr:'))markReadGr();
renderList();
var inp=document.getElementById('msgInp');if(inp)inp.focus();
}
function openCh(cid){cur='ch:'+cid;var cha=document.getElementById('chatArea');cha.classList.add('open');renderHead();renderMsgs();renderPinBar();renderList();}
function showEmpty(){document.getElementById('emptyChat').classList.remove('hid');document.getElementById('chatView').classList.add('hid');document.getElementById('chatArea').classList.remove('open');}
function goBack(){cur=null;editingMsg=null;forwardMsg=null;showEmpty();renderList();}

function renderPinBar(){
var u=me(),d=D(),bar=document.getElementById('pinBar');if(!cur){bar.classList.add('hid');return;}
var pinned=null;
if(cur==='saved'){bar.classList.add('hid');return;}
if(cur.startsWith('ch:')){
var cid=cur.replace('ch:',''),c=d.ch[cid];if(!c){bar.classList.add('hid');return;}
if(c.pinnedPost!==undefined&&c.pinnedPost!==null){var p=c.ps[c.pinnedPost];if(p)pinned={text:p.tx||'📷 Медиа',idx:c.pinnedPost,type:'channel'};}
} else if(cur.startsWith('gr:')){
var gid=cur.replace('gr:',''),msgs=d.m['gr:'+gid]||[];
var pi=msgs.findIndex(function(m){return m.pinned;});
if(pi>=0)pinned={text:msgs[pi].tx||'📷 Медиа',idx:pi,type:'group'};
} else {
var k=ck(u.u,cur),msgs=d.m[k]||[];
var pi=msgs.findIndex(function(m){return m.pinned;});
if(pi>=0)pinned={text:msgs[pi].tx||'📷 Медиа',idx:pi,type:'dm'};
}
if(pinned){
bar.classList.remove('hid');
bar.innerHTML='<span class="pin-icon">📌</span><span class="pin-text" onclick="scrollToMsg('+pinned.idx+')">'+esc((pinned.text||'').substring(0,60))+'</span><span class="pin-close" onclick="event.stopPropagation();unpinMsg()">✕</span>';
bar.onclick=function(){scrollToMsg(pinned.idx);};
} else {bar.classList.add('hid');}
}

function scrollToMsg(idx){
var el=document.getElementById('msgList');
var msgs=el.querySelectorAll('.m,.cpost');
if(msgs[idx]){
msgs[idx].scrollIntoView({behavior:'smooth',block:'center'});
msgs[idx].classList.add('highlight-msg');
setTimeout(function(){msgs[idx].classList.remove('highlight-msg');},2000);
}
}

function pinMsg(k,idx){var d=D();(d.m[k]||[]).forEach(function(m){m.pinned=false;});d.m[k][idx].pinned=true;S(d);renderMsgs();renderPinBar();toast('Закреплено 📌');}
function pinPost(cid,idx){var d=D();d.ch[cid].pinnedPost=idx;S(d);renderMsgs();renderPinBar();toast('Закреплено 📌');}
function unpinMsg(){
var u=me(),d=D();
if(cur.startsWith('ch:')){d.ch[cur.replace('ch:','')].pinnedPost=null;}
else if(cur.startsWith('gr:')){(d.m[cur]||[]).forEach(function(m){m.pinned=false;});}
else{var k=ck(u.u,cur);(d.m[k]||[]).forEach(function(m){m.pinned=false;});}
S(d);renderPinBar();renderMsgs();toast('Откреплено');
}

function startEdit(k,idx){
var d=D(),m=d.m[k][idx];if(!m||!m.tx)return;
editingMsg={key:k,idx:idx};
document.getElementById('msgInp').value=m.tx;document.getElementById('msgInp').focus();
var eb=document.getElementById('editBar');eb.classList.remove('hid');
eb.innerHTML='<span class="edit-label">✏️ Редактирование</span><span class="edit-text">'+esc(m.tx.substring(0,40))+'</span><span class="edit-close" onclick="cancelEdit()">✕</span>';
}
function cancelEdit(){editingMsg=null;document.getElementById('editBar').classList.add('hid');document.getElementById('msgInp').value='';}

function startForward(k,idx){
var d=D(),m,u=me();
if(k.startsWith('chpost:')){var parts=k.replace('chpost:','').split(',');var cid=parts[0];idx=parseInt(parts[1]);var c=d.ch[cid];if(!c)return;m=c.ps[idx];}
else{m=(d.m[k]||[])[idx];}
if(!m)return;
var contacts=[];
Object.keys(d.m).forEach(function(key){if(key.indexOf('|')<0||key.startsWith('sv|'))return;if(key.indexOf(u.u)>=0){var pp=key.split('|');var o=pp[0]===u.u?pp[1]:pp[0];if(o&&contacts.indexOf(o)<0)contacts.push(o);}});
var mc=document.getElementById('mdlB');
var text=m.tx||'';if(m.stickerSvg)text='🎨 Стикер';if(m.mediaType)text=m.mediaType==='image'?'📷 Фото':m.mediaType==='video'?'🎬 Видео':'📎 Файл';
var fwdData=JSON.stringify({tx:m.tx||'',mediaType:m.mediaType||null,mediaData:m.mediaData||null,mediaName:m.mediaName||null,mediaMime:m.mediaMime||null,mediaSize:m.mediaSize||0,stickerSvg:m.stickerSvg||null,fromUser:m.f||''}).replace(/'/g,"\\'");
var h='<h2>↩️ Переслать <span class="x" onclick="clM()">✕</span></h2><div style="padding:8px;background:var(--inp);border-radius:8px;margin-bottom:12px;font-size:13px;border-left:3px solid var(--ac)">'+esc(text.substring(0,80))+'</div><div style="font-size:13px;color:var(--tx2);margin-bottom:8px">Выберите получателя:</div><div class="fwd-list">';
// Saved
h+='<div class="fwd-item" onclick="doForwardSaved(\''+fwdData.replace(/"/g,'&quot;')+'\')"><div class="ci-av saved-icon" style="width:36px;height:36px">🔖</div><div style="font-weight:500">Избранное</div></div>';
contacts.forEach(function(c){var acc=d.a.find(function(x){return x.u===c;});if(acc&&acc.deleted)return;var nm=getNick(c,acc);h+='<div class="fwd-item" onclick="doForward(\''+c+'\',\''+fwdData.replace(/"/g,'&quot;')+'\')">'+avHTML(acc,36)+'<div style="font-weight:500">'+esc(nm)+'</div></div>';});
// Channels
Object.keys(d.ch||{}).forEach(function(cid){var c=d.ch[cid];if(c.ow!==u.u)return;h+='<div class="fwd-item" onclick="doForwardChannel(\''+cid+'\',\''+fwdData.replace(/"/g,'&quot;')+'\')"><div class="ci-av" style="width:36px;height:36px;background:linear-gradient(135deg,#9b59b6,#c39bd3);font-size:16px">📢</div><div style="font-weight:500">'+esc(c.nm)+'</div></div>';});
// Groups
Object.keys(d.gr||{}).forEach(function(gid){var g=d.gr[gid];if(g.ow!==u.u&&g.mb.indexOf(u.u)<0)return;h+='<div class="fwd-item" onclick="doForwardGroup(\''+gid+'\',\''+fwdData.replace(/"/g,'&quot;')+'\')"><div class="ci-av" style="width:36px;height:36px;background:linear-gradient(135deg,#27ae60,#2ecc71);font-size:16px">👥</div><div style="font-weight:500">'+esc(g.nm)+'</div></div>';});
h+='</div>';mc.innerHTML=W(h);
}

function doForward(to,fwdDataStr){
var u=me(),d=D(),fwd=JSON.parse(fwdDataStr);
var fromAcc=d.a.find(function(x){return x.u===fwd.fromUser;});var fromName=fromAcc?getDisplayName(fromAcc):fwd.fromUser;
var k=ck(u.u,to);if(!d.m[k])d.m[k]=[];
var msg={f:u.u,tx:fwd.tx||'',tm:Date.now(),rd:false,rx:{},fwd:{from:fromName,fromU:fwd.fromUser}};
if(fwd.mediaType){msg.mediaType=fwd.mediaType;msg.mediaData=fwd.mediaData;msg.mediaName=fwd.mediaName;msg.mediaMime=fwd.mediaMime;msg.mediaSize=fwd.mediaSize;}
if(fwd.stickerSvg)msg.stickerSvg=fwd.stickerSvg;
d.m[k].push(msg);
if(!d.sh[u.u])d.sh[u.u]=[];if(d.sh[u.u].indexOf(to)<0)d.sh[u.u].push(to);
if(!d.sh[to])d.sh[to]=[];if(d.sh[to].indexOf(u.u)<0)d.sh[to].push(u.u);
S(d);clM();openChat(to);toast('Переслано!');
}
function doForwardSaved(fwdDataStr){
var u=me(),d=D(),fwd=JSON.parse(fwdDataStr);
var fromAcc=d.a.find(function(x){return x.u===fwd.fromUser;});var fromName=fromAcc?getDisplayName(fromAcc):fwd.fromUser;
var k=svKey(u.u);if(!d.m[k])d.m[k]=[];
var msg={f:u.u,tx:fwd.tx||'',tm:Date.now(),rx:{},fwd:{from:fromName,fromU:fwd.fromUser}};
if(fwd.mediaType){msg.mediaType=fwd.mediaType;msg.mediaData=fwd.mediaData;msg.mediaName=fwd.mediaName;msg.mediaMime=fwd.mediaMime;msg.mediaSize=fwd.mediaSize;}
if(fwd.stickerSvg)msg.stickerSvg=fwd.stickerSvg;
d.m[k].push(msg);S(d);clM();openChat('saved');toast('Сохранено в Избранное!');
}
function doForwardChannel(cid,fwdDataStr){
var u=me(),d=D(),fwd=JSON.parse(fwdDataStr);
var fromAcc=d.a.find(function(x){return x.u===fwd.fromUser;});var fromName=fromAcc?getDisplayName(fromAcc):fwd.fromUser;
var c=d.ch[cid];if(!c)return;if(!c.ps)c.ps=[];
var post={f:u.u,tx:fwd.tx||'',tm:Date.now(),rx:{},views:[],fwd:{from:fromName,fromU:fwd.fromUser}};
if(fwd.mediaType){post.mediaType=fwd.mediaType;post.mediaData=fwd.mediaData;post.mediaName=fwd.mediaName;post.mediaMime=fwd.mediaMime;}
c.ps.push(post);S(d);clM();openChat('ch:'+cid);toast('Переслано в канал!');
}
function doForwardGroup(gid,fwdDataStr){
var u=me(),d=D(),fwd=JSON.parse(fwdDataStr);
var fromAcc=d.a.find(function(x){return x.u===fwd.fromUser;});var fromName=fromAcc?getDisplayName(fromAcc):fwd.fromUser;
var k='gr:'+gid;if(!d.m[k])d.m[k]=[];
var msg={f:u.u,tx:fwd.tx||'',tm:Date.now(),rd:false,rx:{},fwd:{from:fromName,fromU:fwd.fromUser}};
if(fwd.mediaType){msg.mediaType=fwd.mediaType;msg.mediaData=fwd.mediaData;msg.mediaName=fwd.mediaName;msg.mediaMime=fwd.mediaMime;msg.mediaSize=fwd.mediaSize;}
if(fwd.stickerSvg)msg.stickerSvg=fwd.stickerSvg;
d.m[k].push(msg);S(d);clM();openChat('gr:'+gid);toast('Переслано в группу!');
}

function renderHead(){
var u=me(),d=D(),el=document.getElementById('chatHead');if(!cur)return;
// Saved messages
if(cur==='saved'){
el.innerHTML='<button class="ch-back" onclick="goBack()"><svg viewBox="0 0 24 24"><path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z"/></svg></button><div class="ci-av saved-icon" style="width:42px;height:42px">🔖</div><div class="ch-nfo"><div class="ch-nm">Избранное</div><div class="ch-st">сохранённые сообщения</div></div>';
document.getElementById('inputArea').classList.remove('hid');document.getElementById('blockedArea').innerHTML='';return;
}
// Channel
if(cur.startsWith('ch:')){
var cid=cur.replace('ch:',''),c=d.ch[cid];if(!c)return;
var isOwner=c.ow===u.u;
el.innerHTML='<button class="ch-back" onclick="goBack()"><svg viewBox="0 0 24 24"><path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z"/></svg></button><div class="ch-nfo" onclick="modal(\'chinfo\',\''+cid+'\')"><div class="ch-nm">📢 '+esc(c.nm)+'</div><div class="ch-st">'+(c.mb.length+1)+' участников</div></div>'+(isOwner?'<button class="ch-btn" onclick="modal(\'chset\',\''+cid+'\')"><svg viewBox="0 0 24 24"><path d="M19.14 12.94c.04-.31.06-.63.06-.94 0-.31-.02-.63-.06-.94l2.03-1.58c.18-.14.23-.41.12-.61l-1.92-3.32c-.12-.22-.37-.29-.59-.22l-2.39.96c-.5-.38-1.03-.7-1.62-.94l-.36-2.54c-.04-.24-.24-.41-.48-.41h-3.84c-.24 0-.43.17-.47.41l-.36 2.54c-.59.24-1.13.57-1.62.94l-2.39-.96c-.22-.08-.47 0-.59.22L2.74 8.87c-.12.21-.08.47.12.61l2.03 1.58c-.04.31-.06.63-.06.94s.02.63.06.94l-2.03 1.58c-.18.14-.23.41-.12.61l1.92 3.32c.12.22.37.29.59.22l2.39-.96c.5.38 1.03.7 1.62.94l.36 2.54c.05.24.24.41.48.41h3.84c.24 0 .44-.17.47-.41l.36-2.54c.59-.24 1.13-.56 1.62-.94l2.39.96c.22.08.47 0 .59-.22l1.92-3.32c.12-.22.07-.47-.12-.61l-2.01-1.58zM12 15.6c-1.98 0-3.6-1.62-3.6-3.6s1.62-3.6 3.6-3.6 3.6 1.62 3.6 3.6-1.62 3.6-3.6 3.6z"/></svg></button><button class="ch-btn" onclick="modal(\'chadd\',\''+cid+'\')"><svg viewBox="0 0 24 24"><path d="M15 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm-9-2V7H4v3H1v2h3v3h2v-3h3v-2H6zm9 4c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg></button>':'');
if(isOwner)document.getElementById('inputArea').classList.remove('hid');
else document.getElementById('inputArea').classList.add('hid');
document.getElementById('blockedArea').innerHTML='';return;
}
// Group
if(cur.startsWith('gr:')){
var gid=cur.replace('gr:',''),g=d.gr[gid];if(!g)return;
var isOwner=g.ow===u.u;
el.innerHTML='<button class="ch-back" onclick="goBack()"><svg viewBox="0 0 24 24"><path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z"/></svg></button><div class="ci-av" style="width:42px;height:42px;background:linear-gradient(135deg,#27ae60,#2ecc71);font-size:18px">👥</div><div class="ch-nfo" onclick="modal(\'grinfo\',\''+gid+'\')"><div class="ch-nm">'+esc(g.nm)+'</div><div class="ch-st">'+(g.mb.length+1)+' участников</div></div>'+(isOwner?'<button class="ch-btn" onclick="modal(\'grset\',\''+gid+'\')"><svg viewBox="0 0 24 24"><path d="M19.14 12.94c.04-.31.06-.63.06-.94 0-.31-.02-.63-.06-.94l2.03-1.58c.18-.14.23-.41.12-.61l-1.92-3.32c-.12-.22-.37-.29-.59-.22l-2.39.96c-.5-.38-1.03-.7-1.62-.94l-.36-2.54c-.04-.24-.24-.41-.48-.41h-3.84c-.24 0-.43.17-.47.41l-.36 2.54c-.59.24-1.13.57-1.62.94l-2.39-.96c-.22-.08-.47 0-.59.22L2.74 8.87c-.12.21-.08.47.12.61l2.03 1.58c-.04.31-.06.63-.06.94s.02.63.06.94l-2.03 1.58c-.18.14-.23.41-.12.61l1.92 3.32c.12.22.37.29.59.22l2.39-.96c.5.38 1.03.7 1.62.94l.36 2.54c.05.24.24.41.48.41h3.84c.24 0 .44-.17.47-.41l.36-2.54c.59-.24 1.13-.56 1.62-.94l2.39.96c.22.08.47 0 .59-.22l1.92-3.32c.12-.22.07-.47-.12-.61l-2.01-1.58zM12 15.6c-1.98 0-3.6-1.62-3.6-3.6s1.62-3.6 3.6-3.6 3.6 1.62 3.6 3.6-1.62 3.6-3.6 3.6z"/></svg></button><button class="ch-btn" onclick="modal(\'gradd\',\''+gid+'\')"><svg viewBox="0 0 24 24"><path d="M15 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm-9-2V7H4v3H1v2h3v3h2v-3h3v-2H6zm9 4c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg></button>':'');
document.getElementById('inputArea').classList.remove('hid');document.getElementById('blockedArea').innerHTML='';return;
}
// DM
var acc=d.a.find(function(x){return x.u===cur;});
var nm=getNick(cur,acc);
var vfMark=(acc&&!acc.deleted&&(acc.u==='surpa'||isVf(acc.u)))?' <span class="vf">✔</span>':'';
var statusHtml=acc&&acc.deleted?'<span style="color:var(--rd)">аккаунт удалён</span>':(isOn(cur)?'<span style="color:var(--ac)">в сети</span>':'был(а) недавно');
el.innerHTML='<button class="ch-back" onclick="goBack()"><svg viewBox="0 0 24 24"><path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z"/></svg></button>'+avHTML(acc,42)+'<div class="ch-nfo" onclick="modal(\'vprof\',\''+cur+'\')"><div class="ch-nm">'+esc(nm)+vfMark+'</div><div class="ch-st">'+statusHtml+'</div></div>'+(acc&&!acc.deleted?'<button class="ch-btn" onclick="modal(\'gift\',\''+cur+'\')"><svg viewBox="0 0 24 24"><path d="M20 6h-2.18c.11-.31.18-.65.18-1 0-1.66-1.34-3-3-3-1.05 0-1.96.54-2.5 1.35l-.5.67-.5-.68C10.96 2.54 10.05 2 9 2 7.34 2 6 3.34 6 5c0 .35.07.69.18 1H4c-1.11 0-1.99.89-1.99 2L2 19c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V8c0-1.11-.89-2-2-2zm-5-2c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zM9 4c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zm11 15H4v-2h16v2zm0-5H4V8h5.08L7 10.83 8.62 12 11 8.76l1-1.36 1 1.36L15.38 12 17 10.83 14.92 8H20v6z"/></svg></button>':'');
if(acc&&acc.deleted){document.getElementById('inputArea').classList.add('hid');document.getElementById('blockedArea').innerHTML='<div class="blocked-msg">👻 Аккаунт удалён</div>';}
else{var blocked=!canMsg(u.u,cur);if(blocked){document.getElementById('inputArea').classList.add('hid');document.getElementById('blockedArea').innerHTML='<div class="blocked-msg">🚫 Запрет на сообщения</div>';}else{document.getElementById('inputArea').classList.remove('hid');document.getElementById('blockedArea').innerHTML='';}}
}

function buildMsgsHTML(){
var u=me(),d=D();if(!cur||!u)return'';
// Saved
if(cur==='saved'){var msgs=d.m[svKey(u.u)]||[];return buildDMHTML(msgs,u,d,svKey(u.u));}
// Channel
if(cur.startsWith('ch:')){return buildChannelHTML(u,d);}
// Group
if(cur.startsWith('gr:')){var msgs=d.m[cur]||[];return buildDMHTML(msgs,u,d,cur);}
// DM
var k=ck(u.u,cur);var msgs=d.m[k]||[];return buildDMHTML(msgs,u,d,k);
}

function buildChannelHTML(u,d){
var cid=cur.replace('ch:',''),c=d.ch[cid];if(!c)return'';
var h='';
(c.ps||[]).forEach(function(p,pIdx){
var acc=d.a.find(function(x){return x.u===p.f;});
if(!p.views)p.views=[];
if(p.views.indexOf(u.u)<0){p.views.push(u.u);d.ch[cid].ps[pIdx].views=p.views;S(d);}
var isPinned=c.pinnedPost===pIdx;
h+='<div class="cpost" id="msg-'+pIdx+'" oncontextmenu="postCtx(event,\''+cid+'\','+pIdx+')">';
if(isPinned)h+='<div class="cpost-pinned">📌 Закреплено</div>';
h+='<div style="display:flex;align-items:center;gap:8px;margin-bottom:6px">'+avHTML(acc,32)+'<span style="font-weight:600;font-size:13px">'+esc(getDisplayName(acc))+'</span></div>';
if(p.fwd)h+='<div class="m-fwd"><div class="m-fwd-from">↩ Переслано от '+esc(p.fwd.from)+'</div></div>';
if(p.tx)h+='<div class="cpost-t">'+esc(p.tx)+(p.edited?' <span style="font-size:10px;color:var(--tx2);font-style:italic">ред.</span>':'')+'</div>';
if(p.mediaType)h+=renderMediaHTML(p);
if(p.stickerSvg)h+='<div class="m-sticker">'+p.stickerSvg+'</div>';
h+='<div class="cpost-m"><span>'+fmtTime(p.tm)+'</span><span class="cpost-views"><svg viewBox="0 0 24 24"><path d="M12 4.5C7 4.5 2.73 7.61 1 12c1.73 4.39 6 7.5 11 7.5s9.27-3.11 11-7.5c-1.73-4.39-6-7.5-11-7.5zM12 17c-2.76 0-5-2.24-5-5s2.24-5 5-5 5 2.24 5 5-2.24 5-5 5zm0-8c-1.66 0-3 1.34-3 3s1.34 3 3 3 3-1.34 3-3-1.34-3-3-3z"/></svg>'+p.views.length+'</span></div>';
h+='<div class="cpost-rx">';var rx=p.rx||{};
Object.keys(rx).forEach(function(em){var cnt=rx[em]?rx[em].length:0;var my=rx[em]&&rx[em].indexOf(u.u)>=0;if(cnt)h+='<span class="rx'+(my?' my':'')+'" onclick="rxPost(\''+cid+'\','+pIdx+',\''+em+'\')">'+em+' '+cnt+'</span>';});
h+='</div></div>';});
return h;
}

function buildDMHTML(msgs,u,d,k){
var h='',lastDate='';
msgs.forEach(function(m,idx){
var dd=fmtDate(m.tm);
if(dd!==lastDate){h+='<div class="msg-date"><span>'+dd+'</span></div>';lastDate=dd;}
if(m.tp==='sys'){h+='<div class="m-sys"><span>'+esc(m.tx)+'</span></div>';return;}
var isMe=m.f===u.u;var isSticker=!!m.stickerSvg;
var cls=isMe?'m m-o':'m m-i';if(isSticker)cls+=' sticker-msg';
var rd=isMe&&cur!=='saved'?(m.rd?'✓✓':'✓'):'';
h+='<div class="'+cls+'" id="msg-'+idx+'" oncontextmenu="msgCtx(event,\''+k+'\','+idx+')">';
if(!isMe){var acc=d.a.find(function(x){return x.u===m.f;});h+='<div style="font-size:12px;color:var(--ac);margin-bottom:2px;font-weight:600">'+esc(getNick(m.f,acc))+'</div>';}
if(m.pinned)h+='<div style="font-size:10px;color:var(--ac);margin-bottom:2px">📌 Закреплено</div>';
if(m.fwd)h+='<div class="m-fwd"><div class="m-fwd-from">↩ Переслано от '+esc(m.fwd.from)+'</div></div>';
if(m.tp==='gift'){var gd=GIFTS.find(function(x){return x.id===m.gi;});h+='<div class="m-gift"><div class="m-gift-anim"><div class="m-gift-circle" style="background:radial-gradient(circle,'+(gd?gd.colors[0]:'#5288c1')+'22,'+(gd?gd.colors[1]:'#5288c1')+'11)"></div><div class="m-gift-circle2" style="background:radial-gradient(circle,'+(gd?gd.colors[0]:'#5288c1')+'18,'+(gd?gd.colors[1]:'#5288c1')+'08)"></div><div class="m-gift-svg">'+(gd?gd.svg:'🎁')+'</div><div class="m-gift-sparkles">';if(gd){for(var si=0;si<8;si++){var angle=si*45;var rad=angle*Math.PI/180;var sx=50+Math.cos(rad)*45;var sy=50+Math.sin(rad)*45;h+='<div class="m-gift-sparkle" style="left:'+sx+'%;top:'+sy+'%;background:'+gd.colors[si%gd.colors.length]+';animation-delay:'+(si*0.25)+'s"></div>';}}h+='</div></div><div class="m-gift-t">'+(gd?gd.name:'Подарок')+'</div>'+(m.gt?'<div class="m-gift-x">«'+esc(m.gt)+'»</div>':'')+'</div>';}
else if(isSticker){h+='<div class="m-sticker">'+m.stickerSvg+'</div>';}
else{if(m.tx)h+='<div class="m-tx">'+esc(m.tx)+(m.edited?'<span class="m-edited">ред.</span>':'')+'</div>';if(m.mediaType)h+=renderMediaHTML(m);}
var rx=m.rx||{};var hasRx=Object.keys(rx).some(function(em){return rx[em]&&rx[em].length>0;});
if(hasRx){h+='<div class="m-rx">';Object.keys(rx).forEach(function(em){var cnt=rx[em]?rx[em].length:0;var my=rx[em]&&rx[em].indexOf(u.u)>=0;if(cnt)h+='<span class="rx'+(my?' my':'')+'" onclick="rxMsg(\''+k+'\','+idx+',\''+em+'\')">'+em+' '+cnt+'</span>';});h+='</div>';}
h+='<div class="m-ft"><span>'+fmtTime(m.tm)+'</span>'+(rd?'<span class="m-ck">'+rd+'</span>':'')+'</div></div>';
});
return h;
}

function renderMsgs(){
var el=document.getElementById('msgList');var h=buildMsgsHTML();
var wasAtBottom=el.scrollHeight-el.scrollTop-el.clientHeight<50;
lastMsgHTML=h;el.innerHTML=h;
if(wasAtBottom)el.scrollTop=el.scrollHeight;
}

function renderMediaHTML(m){
var h='<div class="m-media">';
if(m.mediaType==='image')h+='<img src="'+m.mediaData+'" onclick="viewImage(this.src)" alt="photo">';
else if(m.mediaType==='video')h+='<video controls preload="metadata"><source src="'+m.mediaData+'" type="'+m.mediaMime+'">Видео</video>';
else if(m.mediaType==='audio')h+='<audio controls preload="metadata"><source src="'+m.mediaData+'" type="'+m.mediaMime+'"></audio>';
else h+='<a class="m-file" href="'+m.mediaData+'" download="'+esc(m.mediaName)+'"><span class="m-file-icon">📄</span><div class="m-file-info"><div class="m-file-name">'+esc(m.mediaName)+'</div><div class="m-file-size">'+formatSize(m.mediaSize||0)+'</div></div></a>';
h+='</div>';return h;
}
function formatSize(bytes){if(bytes<1024)return bytes+' Б';if(bytes<1024*1024)return(bytes/1024).toFixed(1)+' КБ';return(bytes/(1024*1024)).toFixed(1)+' МБ';}
function viewImage(src){document.getElementById('imgViewer').innerHTML='<div class="img-viewer" onclick="this.remove()"><img src="'+src+'"></div>';}
function attachFile(){document.getElementById('fileInp').click();}
function handleFileSelect(input){
var file=input.files[0];if(!file)return;
if(file.size>5*1024*1024){toast('Макс 5 МБ');input.value='';return;}
var reader=new FileReader();
reader.onload=function(e){var mediaType='file';if(file.type.startsWith('image/'))mediaType='image';else if(file.type.startsWith('video/'))mediaType='video';else if(file.type.startsWith('audio/'))mediaType='audio';sendMediaMsg(mediaType,e.target.result,file.name,file.type,file.size);};
reader.readAsDataURL(file);input.value='';
}
function sendMediaMsg(mediaType,mediaData,mediaName,mediaMime,mediaSize){
var u=me(),d=D();if(!u||!cur)return;
if(cur==='saved'){var k=svKey(u.u);if(!d.m[k])d.m[k]=[];d.m[k].push({f:u.u,mediaType:mediaType,mediaData:mediaData,mediaName:mediaName,mediaMime:mediaMime,mediaSize:mediaSize,tx:'',tm:Date.now(),rx:{}});S(d);renderMsgs();renderList();return;}
if(cur.startsWith('ch:')){var cid=cur.replace('ch:',''),c=d.ch[cid];if(!c||c.ow!==u.u){toast('Только создатель');return;}if(!c.ps)c.ps=[];c.ps.push({f:u.u,mediaType:mediaType,mediaData:mediaData,mediaName:mediaName,mediaMime:mediaMime,mediaSize:mediaSize,tm:Date.now(),rx:{},views:[]});S(d);renderMsgs();renderList();return;}
if(cur.startsWith('gr:')){var k=cur;if(!d.m[k])d.m[k]=[];d.m[k].push({f:u.u,mediaType:mediaType,mediaData:mediaData,mediaName:mediaName,mediaMime:mediaMime,mediaSize:mediaSize,tx:'',tm:Date.now(),rd:false,rx:{}});S(d);renderMsgs();renderList();return;}
var k=ck(u.u,cur);if(!d.m[k])d.m[k]=[];
d.m[k].push({f:u.u,mediaType:mediaType,mediaData:mediaData,mediaName:mediaName,mediaMime:mediaMime,mediaSize:mediaSize,tx:'',tm:Date.now(),rd:false,rx:{}});S(d);renderMsgs();renderList();
}

function toggleStickerPanel(){stickerOpen=!stickerOpen;var panel=document.getElementById('stickerPanel');if(stickerOpen){panel.classList.remove('hid');renderStickerPanel(0);}else{panel.classList.add('hid');}}
function hideStickerPanel(){stickerOpen=false;var panel=document.getElementById('stickerPanel');if(panel)panel.classList.add('hid');}
function renderStickerPanel(packIdx){
var panel=document.getElementById('stickerPanel');
var h='<div class="stk-tabs">';STICKER_PACKS.forEach(function(pack,i){h+='<div class="stk-tab'+(i===packIdx?' active':'')+'" onclick="renderStickerPanel('+i+')">'+esc(pack.name)+'</div>';});
h+='</div><div class="stk-grid">';STICKER_PACKS[packIdx].stickers.forEach(function(stk){h+='<div class="stk-item" onclick="sendSticker(\''+stk.id+'\')">'+stk.svg+'</div>';});
h+='</div>';panel.innerHTML=h;
}
function sendSticker(stickerId){
var u=me(),d=D();if(!u||!cur)return;
var svg='';STICKER_PACKS.forEach(function(pack){pack.stickers.forEach(function(stk){if(stk.id===stickerId)svg=stk.svg;});});if(!svg)return;
hideStickerPanel();
if(cur==='saved'){var k=svKey(u.u);if(!d.m[k])d.m[k]=[];d.m[k].push({f:u.u,stickerSvg:svg,tx:'',tm:Date.now(),rx:{}});S(d);renderMsgs();renderList();return;}
if(cur.startsWith('ch:')){var cid=cur.replace('ch:',''),c=d.ch[cid];if(!c||c.ow!==u.u){toast('Только создатель');return;}if(!c.ps)c.ps=[];c.ps.push({f:u.u,stickerSvg:svg,tx:'',tm:Date.now(),rx:{},views:[]});S(d);renderMsgs();renderList();return;}
if(cur.startsWith('gr:')){var k=cur;if(!d.m[k])d.m[k]=[];d.m[k].push({f:u.u,stickerSvg:svg,tx:'',tm:Date.now(),rd:false,rx:{}});S(d);renderMsgs();renderList();return;}
var k=ck(u.u,cur);if(!d.m[k])d.m[k]=[];
d.m[k].push({f:u.u,stickerSvg:svg,tx:'',tm:Date.now(),rd:false,rx:{}});
if(!d.sh[u.u])d.sh[u.u]=[];if(d.sh[u.u].indexOf(cur)<0)d.sh[u.u].push(cur);
if(!d.sh[cur])d.sh[cur]=[];if(d.sh[cur].indexOf(u.u)<0)d.sh[cur].push(u.u);
S(d);renderMsgs();renderList();
}

function sendMsg(){
var inp=document.getElementById('msgInp'),tx=inp.value.trim();if(!tx)return;
var u=me(),d=D();if(!u||!cur)return;
if(editingMsg){var em=d.m[editingMsg.key][editingMsg.idx];if(em){em.tx=tx;em.edited=true;S(d);}cancelEdit();renderMsgs();renderList();toast('Отредактировано');return;}
if(cur==='saved'){var k=svKey(u.u);if(!d.m[k])d.m[k]=[];d.m[k].push({f:u.u,tx:tx,tm:Date.now(),rx:{}});S(d);inp.value='';renderMsgs();renderList();return;}
if(cur.startsWith('ch:')){var cid=cur.replace('ch:',''),c=d.ch[cid];if(!c||c.ow!==u.u){toast('Только создатель');return;}if(!c.ps)c.ps=[];c.ps.push({f:u.u,tx:tx,tm:Date.now(),rx:{},views:[]});S(d);inp.value='';renderMsgs();renderList();return;}
if(cur.startsWith('gr:')){var k=cur;if(!d.m[k])d.m[k]=[];d.m[k].push({f:u.u,tx:tx,tm:Date.now(),rd:false,rx:{}});S(d);inp.value='';renderMsgs();renderList();return;}
var k=ck(u.u,cur);if(!d.m[k])d.m[k]=[];
d.m[k].push({f:u.u,tx:tx,tm:Date.now(),rd:false,rx:{}});
if(!d.sh[u.u])d.sh[u.u]=[];if(d.sh[u.u].indexOf(cur)<0)d.sh[u.u].push(cur);
if(!d.sh[cur])d.sh[cur]=[];if(d.sh[cur].indexOf(u.u)<0)d.sh[cur].push(u.u);
S(d);inp.value='';renderMsgs();renderList();
}

function markRead(){var u=me(),d=D();if(!u||!cur||cur.startsWith('ch:')||cur==='saved')return;var k=ck(u.u,cur);(d.m[k]||[]).forEach(function(m){if(m.f!==u.u)m.rd=true;});S(d);renderList();}
function markReadGr(){var u=me(),d=D();if(!u||!cur)return;(d.m[cur]||[]).forEach(function(m){if(m.f!==u.u)m.rd=true;});S(d);renderList();}

function rxMsg(k,idx,em){var u=me(),d=D();if(!u)return;var m=d.m[k][idx];if(!m.rx)m.rx={};if(!m.rx[em])m.rx[em]=[];var i=m.rx[em].indexOf(u.u);if(i>=0)m.rx[em].splice(i,1);else m.rx[em].push(u.u);S(d);renderMsgs();}
function rxPost(cid,idx,em){var u=me(),d=D();if(!u)return;var p=d.ch[cid].ps[idx];if(!p.rx)p.rx={};if(!p.rx[em])p.rx[em]=[];var i=p.rx[em].indexOf(u.u);if(i>=0)p.rx[em].splice(i,1);else p.rx[em].push(u.u);S(d);renderMsgs();}

function msgCtx(e,k,idx){
e.preventDefault();var u=me(),d=D(),m=(d.m[k]||[])[idx];if(!m)return;
var h='<div class="pop" style="left:'+Math.min(e.clientX,innerWidth-220)+'px;top:'+Math.min(e.clientY,innerHeight-300)+'px">';
h+='<div style="display:flex;gap:2px;padding:6px 10px;flex-wrap:wrap">';REACTIONS.forEach(function(em){h+='<span class="rbtn" onclick="rxMsg(\''+k+'\','+idx+',\''+em+'\');clPop()">'+em+'</span>';});h+='</div>';
h+='<div class="pop-i" onclick="startForward(\''+k+'\','+idx+');clPop()">↩️ Переслать</div>';
h+='<div class="pop-i" onclick="pinMsg(\''+k+'\','+idx+');clPop()">📌 Закрепить</div>';
if(m.f===u.u&&m.tx&&!m.stickerSvg)h+='<div class="pop-i" onclick="startEdit(\''+k+'\','+idx+');clPop()">✏️ Редактировать</div>';
if(m.f===u.u)h+='<div class="pop-i red" onclick="delMsg(\''+k+'\','+idx+');clPop()">🗑 Удалить</div>';
h+='<div class="pop-i" onclick="clPop()">✖ Закрыть</div></div>';
document.getElementById('popB').innerHTML=h;setTimeout(function(){document.addEventListener('click',clPop,{once:true});},10);
}

function postCtx(e,cid,idx){
e.preventDefault();var u=me(),d=D(),c=d.ch[cid];if(!c)return;var isOwner=c.ow===u.u;
var h='<div class="pop" style="left:'+Math.min(e.clientX,innerWidth-220)+'px;top:'+Math.min(e.clientY,innerHeight-250)+'px">';
h+='<div style="display:flex;gap:2px;padding:6px 10px;flex-wrap:wrap">';REACTIONS.forEach(function(em){h+='<span class="rbtn" onclick="rxPost(\''+cid+'\','+idx+',\''+em+'\');clPop()">'+em+'</span>';});h+='</div>';
h+='<div class="pop-i" onclick="startForward(\'chpost:'+cid+','+idx+'\','+idx+');clPop()">↩️ Переслать</div>';
if(isOwner){h+='<div class="pop-i" onclick="pinPost(\''+cid+'\','+idx+');clPop()">📌 Закрепить</div>';var p=c.ps[idx];if(p&&p.tx)h+='<div class="pop-i" onclick="editPost(\''+cid+'\','+idx+');clPop()">✏️ Редактировать</div>';h+='<div class="pop-i red" onclick="delPost(\''+cid+'\','+idx+');clPop()">🗑 Удалить</div>';}
h+='<div class="pop-i" onclick="clPop()">✖ Закрыть</div></div>';
document.getElementById('popB').innerHTML=h;setTimeout(function(){document.addEventListener('click',clPop,{once:true});},10);
}

function editPost(cid,idx){var d=D(),p=d.ch[cid].ps[idx];if(!p||!p.tx)return;var newText=prompt('Редактировать пост:',p.tx);if(newText!==null&&newText.trim()){d.ch[cid].ps[idx].tx=newText.trim();d.ch[cid].ps[idx].edited=true;S(d);renderMsgs();toast('Отредактировано');}}
function delPost(cid,idx){if(!confirm('Удалить пост?'))return;var d=D();d.ch[cid].ps.splice(idx,1);if(d.ch[cid].pinnedPost===idx)d.ch[cid].pinnedPost=null;else if(d.ch[cid].pinnedPost>idx)d.ch[cid].pinnedPost--;S(d);renderMsgs();renderPinBar();renderList();toast('Удалён');}
function chatCtx(e,key){
e.preventDefault();
var h='<div class="pop" style="left:'+Math.min(e.clientX,innerWidth-200)+'px;top:'+Math.min(e.clientY,innerHeight-200)+'px">';
if(!key.startsWith('ch:')&&!key.startsWith('gr:')&&key!=='saved'){h+='<div class="pop-i" onclick="modal(\'rename\',\''+key+'\');clPop()">✏️ Переименовать</div>';h+='<div class="pop-i" onclick="modal(\'gift\',\''+key+'\');clPop()">🎁 Подарить</div>';}
h+='<div class="pop-i red" onclick="delChat(\''+key+'\');clPop()">🗑 Удалить чат</div>';
h+='<div class="pop-i" onclick="clPop()">✖ Закрыть</div></div>';
document.getElementById('popB').innerHTML=h;setTimeout(function(){document.addEventListener('click',clPop,{once:true});},10);
}
function clPop(){document.getElementById('popB').innerHTML='';}
function delMsg(k,idx){var d=D();d.m[k].splice(idx,1);S(d);renderMsgs();renderPinBar();renderList();toast('Удалено');}
function delChat(key){
var d=D(),u=me();
if(key==='saved'){d.m[svKey(u.u)]=[];S(d);renderMsgs();renderList();toast('Избранное очищено');return;}
if(key.startsWith('ch:')){delete d.ch[key.replace('ch:','')];}
else if(key.startsWith('gr:')){delete d.gr[key.replace('gr:','')];delete d.m[key];}
else{var k=ck(u.u,key);delete d.m[k];}
S(d);if(cur===key){cur=null;showEmpty();}renderList();toast('Удалено');
}

function doSearch(q){
q=q.trim().toLowerCase();var d=D(),u=me(),el=document.getElementById('chatList');if(!q){renderList();return;}
var h='';
d.a.forEach(function(a){if(a.u===u.u||a.deleted)return;if(a.nm.toLowerCase().indexOf(q)>=0||a.u.indexOf(q)>=0){var vfMark=(a.u==='surpa'||isVf(a.u))?' <span class="vf">✔</span>':'';h+='<div class="sr" onclick="openChat(\''+a.u+'\')">'+avHTML(a,42)+'<div><div style="font-weight:500">'+esc(a.nm)+vfMark+'</div><div style="font-size:12px;color:var(--tx2)">@'+a.u+'</div></div></div>';}});
if(!h)h='<div style="padding:20px;text-align:center;color:var(--tx2)">Ничего не найдено</div>';
el.innerHTML='<div class="sec">Результаты</div>'+h;
}

// Modals
function modal(type,ex){
var u=me(),d=D(),mc=document.getElementById('mdlB');if(!u)return;

if(type==='profile'){
var gs=(u.gifts||[]).filter(function(g){return!g.sd;});
var gh=gs.length?'<div style="margin-top:12px"><div style="font-size:13px;color:var(--tx2);margin-bottom:6px">Подарки ('+gs.length+')</div><div style="display:flex;flex-wrap:wrap;gap:4px">'+gs.map(function(g,idx){var gd=GIFTS.find(function(x){return x.id===g.gi;});return'<div class="pg'+(g.hd?' dim':'')+'" onclick="modal(\'vgift\',\''+idx+'\')"><div class="pg-i" style="width:40px;height:40px">'+(gd?gd.svg:'🎁')+'</div>'+(g.hd?'<div class="pg-bd">🚫</div>':'')+'</div>';}).join('')+'</div></div>':'';
var vfMark=(u.u==='surpa'||isVf(u.u))?' <span class="vf">✔</span>':'';
mc.innerHTML=W('<h2>Мой профиль <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center"><div class="prof-av-wrap" onclick="triggerAvatarUpload()">'+avHTML(u,80)+'<div class="prof-av-edit"><svg viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg></div></div><input type="file" id="profAvInp" accept="image/*" style="display:none" onchange="uploadAvatar(this)"></div><div style="margin-top:8px;font-size:18px;font-weight:600">'+esc(u.nm)+vfMark+'</div><div style="color:var(--tx2);font-size:13px">@'+u.u+'</div>'+(u.bio?'<div style="margin-top:6px;font-size:13px">'+esc(u.bio)+'</div>':'')+(isVf(u.u)||u.u==='surpa'?'<div style="color:var(--ac);font-size:12px;margin-top:4px">✔ Верифицированный</div>':'')+'<div style="margin-top:4px;font-size:12px;color:var(--tx2)">Зарегистрирован '+new Date(u.cr).toLocaleDateString('ru-RU')+'</div>'+gh);return;
}

if(type==='vprof'){
var acc=d.a.find(function(x){return x.u===ex;});if(!acc)return;
if(acc.deleted){mc.innerHTML=W('<h2>Профиль <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center">'+avHTML(acc,80)+'<div style="margin-top:8px;font-size:18px;font-weight:600;color:var(--tx2);font-style:italic">Аккаунт удалён</div></div>');return;}
var gs=(acc.gifts||[]).filter(function(g){return!g.hd&&!g.sd;});
var gh=gs.length?'<div style="margin-top:12px"><div style="font-size:13px;color:var(--tx2);margin-bottom:6px">Подарки ('+gs.length+')</div><div style="display:flex;flex-wrap:wrap;gap:4px">'+gs.map(function(g){var gd=GIFTS.find(function(x){return x.id===g.gi;});return'<div class="pg"><div class="pg-i" style="width:40px;height:40px">'+(gd?gd.svg:'🎁')+'</div></div>';}).join('')+'</div></div>':'';
var vfMark=(acc.u==='surpa'||isVf(acc.u))?' <span class="vf">✔</span>':'';
mc.innerHTML=W('<h2>Профиль <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center">'+avHTML(acc,80)+'<div style="margin-top:8px;font-size:18px;font-weight:600">'+esc(acc.nm)+vfMark+'</div><div style="color:var(--tx2);font-size:13px">@'+acc.u+'</div>'+(acc.bio?'<div style="margin-top:6px;font-size:13px">'+esc(acc.bio)+'</div>':'')+'<div style="margin-top:8px;font-size:13px;color:var(--tx2)">'+(isOn(acc.u)?'<span style="color:var(--gn)">● в сети</span>':'был(а) недавно')+'</div>'+gh+'</div><button class="btn" style="width:100%;margin-top:12px" onclick="clM();openChat(\''+acc.u+'\')">Написать</button>');return;
}

if(type==='vgift'){var i=parseInt(ex),g=u.gifts[i];if(!g)return;var gd=GIFTS.find(function(x){return x.id===g.gi;});var from=d.a.find(function(x){return x.u===g.fr;});mc.innerHTML=W('<h2>Подарок <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center"><div style="width:100px;height:100px;margin:0 auto">'+(gd?gd.svg:'🎁')+'</div><div style="font-size:18px;font-weight:600;margin-top:8px">'+(gd?gd.name:'Подарок')+'</div><div style="color:var(--tx2);margin-top:8px">От: @'+esc(g.fr)+'</div>'+(g.tx?'<div style="margin-top:8px;font-style:italic">«'+esc(g.tx)+'»</div>':'')+'</div><div style="display:flex;gap:8px;margin-top:14px"><button class="btn outline" style="flex:1" onclick="togHide('+i+')">'+(g.hd?'Показать':'Скрыть')+'</button><button class="btn red" style="flex:1" onclick="sellG('+i+')">Продать</button></div>');return;}

if(type==='settings'){
tmpAv=null;
mc.innerHTML=W('<h2>⚙ Настройки <span class="x" onclick="clM()">✕</span></h2><label>Имя</label><input type="text" id="sNm" value="'+esc(u.nm)+'"><label>Username</label><input type="text" id="sUn" value="'+esc(u.u)+'"><label>Био</label><textarea id="sBio">'+esc(u.bio||'')+'</textarea><label>Аватар</label><div class="av-ops">'+
'<div class="av-upload-btn" onclick="document.getElementById(\'settAvInp\').click()">📷</div><input type="file" id="settAvInp" accept="image/*" style="display:none" onchange="uploadAvatarSettings(this)">'+
(u.customAv?'<div class="av-custom-wrap"><div class="av-o sel"><img src="'+u.customAv+'"></div><div class="av-custom-del" onclick="removeCustomAvatar()">✕</div></div>':'')+
AVATARS.map(function(av){var sel=(!u.customAv&&u.av===av.id)?' sel':'';return'<div class="av-o'+sel+'" style="background:'+av.bg+'" onclick="pickAv('+av.id+',this)">'+((u.nm||'?')[0].toUpperCase())+'</div>';}).join('')+'</div>'+
'<label>Фон профиля</label><div class="prof-bg-picker"><div class="prof-bg-upload" onclick="document.getElementById(\'profBgInp\').click()">📷</div><input type="file" id="profBgInp" accept="image/*" style="display:none" onchange="uploadProfBg(this)">'+
PROF_BG_COLORS.map(function(bg,i){var sel=(u.profBg===bg)?' sel':'';return'<div class="prof-bg-swatch'+sel+'" style="background:'+bg+'" onclick="pickProfBg(\''+bg+'\',this)"></div>';}).join('')+
(u.profBg?'<div class="prof-bg-swatch" style="background:var(--rd);display:flex;align-items:center;justify-content:center;color:#fff;font-size:14px" onclick="clearProfBg()">✕</div>':'')+'</div>'+
'<label>Тема</label><div class="theme-tog"><div class="theme-btn'+(theme==='dark'?' sel':'')+'" onclick="pickTheme(\'dark\',this)">🌙 Тёмная</div><div class="theme-btn'+(theme==='light'?' sel':'')+'" onclick="pickTheme(\'light\',this)">☀️ Светлая</div></div>'+
'<label>Интерфейс</label><div class="if-tog"><div class="if-btn'+(iface==='pc'?' sel':'')+'" onclick="pickIf(\'pc\',this)">💻 ПК</div><div class="if-btn'+(iface==='phone'?' sel':'')+'" onclick="pickIf(\'phone\',this)">📱 Телефон</div></div>'+
'<button class="btn" style="width:100%;margin-top:18px" onclick="saveSets()">Сохранить</button><button class="del-acc-btn" onclick="deleteAccount()">🗑 Удалить аккаунт</button>');return;
}

if(type==='privacy'){
if(!u.prv)u.prv={};var p=u.prv;var contacts=getContacts(u,d);
mc.innerHTML=W('<h2>🛡 Конфиденциальность <span class="x" onclick="clM()">✕</span></h2>'+
'<div class="prv-row"><div class="prv-label">Запрет на подарки</div><div class="prv-tog'+(p.noGift?' on':'')+'" onclick="togPrv(\'noGift\',this)"></div></div>'+
'<div class="prv-row"><div class="prv-label">Запрет на сообщения</div><div class="prv-tog'+(p.noMsg?' on':'')+'" onclick="togPrv(\'noMsg\',this)"></div></div>'+
'<div class="prv-row"><div class="prv-label">Запрет на каналы/группы</div><div class="prv-tog'+(p.noCh?' on':'')+'" onclick="togPrv(\'noCh\',this)"></div></div>'+
'<button class="btn" style="width:100%;margin-top:14px" onclick="savePrv()">Сохранить</button>');return;
}

if(type==='accounts'){
mc.innerHTML=W('<h2>👥 Аккаунты <span class="x" onclick="clM()">✕</span></h2>'+d.a.filter(function(a){return!a.deleted;}).map(function(a){var isCur=a.u===u.u;return'<div class="aci'+(isCur?' cur':'')+'" onclick="switchAcc(\''+a.u+'\')">'+avHTML(a,40)+'<div><div style="font-weight:500">'+esc(a.nm)+'</div><div style="font-size:12px;color:var(--tx2)">@'+a.u+(isCur?' · текущий':'')+'</div></div></div>';}).join('')+'<button class="btn outline" style="width:100%;margin-top:12px" onclick="addAcc()">+ Добавить аккаунт</button>');return;
}

if(type==='rename'){mc.innerHTML=W('<h2>Переименовать <span class="x" onclick="clM()">✕</span></h2><label>Имя для @'+esc(ex)+'</label><input type="text" id="rnNm"><div style="display:flex;gap:8px;margin-top:14px"><button class="btn" style="flex:1" onclick="doRename(\''+ex+'\')">Сохранить</button><button class="btn outline" style="flex:1" onclick="doRenameClear(\''+ex+'\')">Сбросить</button></div>');return;}

if(type==='gift'){
tmpGift=null;
var acc=d.a.find(function(x){return x.u===ex;});
if(acc&&acc.deleted){mc.innerHTML=W('<h2>Подарок <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center;padding:20px">👻 Аккаунт удалён</div>');return;}
if(!canGift(u.u,ex)&&u.u!==ex){mc.innerHTML=W('<h2>Подарок <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center;padding:20px">🚫 Запрет на подарки</div>');return;}
mc.innerHTML=W('<h2>🎁 Подарить <span class="x" onclick="clM()">✕</span></h2><div class="gc">'+GIFTS.map(function(g){return'<div class="gci" onclick="pickGift(\''+g.id+'\',this)"><div class="gci-svg">'+g.svg+'</div><div class="gci-n">'+g.name+'</div></div>';}).join('')+'</div><label>Сообщение</label><textarea id="gTx" rows="2" placeholder="Поздравляю!"></textarea><button class="btn" style="width:100%;margin-top:14px" onclick="sendGift(\''+ex+'\')">Отправить 🎁</button>');return;
}

if(type==='newch'){
var contacts=getContacts(u,d);
mc.innerHTML=W('<h2>📢 Создать канал <span class="x" onclick="clM()">✕</span></h2><label>Название</label><input type="text" id="chNm"><label>Описание</label><textarea id="chDs"></textarea><label>Участники</label><div id="chMb">'+contacts.map(function(c){var a=d.a.find(function(x){return x.u===c;});var blocked=!canAddCh(c)||(a&&a.deleted);return'<div style="padding:4px 0"><input type="checkbox" value="'+c+'"'+(blocked?' disabled':'')+' > '+(a?esc(a.deleted?'удалён':a.nm):c)+(blocked?' <span style="color:var(--rd);font-size:11px">запрет</span>':'')+'</div>';}).join('')+'</div><button class="btn" style="width:100%;margin-top:14px" onclick="mkCh()">Создать</button>');return;
}

// CREATE GROUP
if(type==='newgroup'){
var contacts=getContacts(u,d);
mc.innerHTML=W('<h2>👥 Создать группу <span class="x" onclick="clM()">✕</span></h2><label>Название</label><input type="text" id="grNm"><label>Описание</label><textarea id="grDs"></textarea><label>Участники</label><div id="grMb">'+contacts.map(function(c){var a=d.a.find(function(x){return x.u===c;});var blocked=!canAddCh(c)||(a&&a.deleted);return'<div style="padding:4px 0"><input type="checkbox" value="'+c+'"'+(blocked?' disabled':'')+' > '+(a?esc(a.deleted?'удалён':a.nm):c)+(blocked?' <span style="color:var(--rd);font-size:11px">запрет</span>':'')+'</div>';}).join('')+'</div><button class="btn" style="width:100%;margin-top:14px" onclick="mkGr()">Создать группу</button>');return;
}

if(type==='grinfo'){
var g=d.gr[ex];if(!g)return;
var members=[g.ow].concat(g.mb);
mc.innerHTML=W('<h2>👥 Информация <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center;font-size:18px;font-weight:600">'+esc(g.nm)+'</div>'+(g.ds?'<div style="text-align:center;color:var(--tx2);font-size:13px;margin-top:4px">'+esc(g.ds)+'</div>':'')+'<div style="margin-top:14px;font-size:14px;font-weight:600">Участники ('+members.length+')</div>'+members.map(function(m){var a=d.a.find(function(x){return x.u===m;});var vfMark=(!a||a.deleted)?'':(a.u==='surpa'||isVf(m))?' <span class="vf">✔</span>':'';var isOw=m===g.ow;return'<div class="aci" onclick="clM();openChat(\''+m+'\')">'+avHTML(a,36)+'<div><span style="font-weight:500">'+esc(getDisplayName(a))+vfMark+'</span><div style="font-size:11px;color:var(--tx2)">@'+m+(isOw?' · создатель':'')+'</div></div>'+(g.ow===u.u&&!isOw?'<button class="vfb" style="margin-left:auto" onclick="event.stopPropagation();kickFromGroup(\''+ex+'\',\''+m+'\')">✕</button>':'')+'</div>';}).join(''));return;
}

if(type==='grset'){
var g=d.gr[ex];if(!g)return;
mc.innerHTML=W('<h2>⚙ Настройки группы <span class="x" onclick="clM()">✕</span></h2><label>Название</label><input type="text" id="gsNm" value="'+esc(g.nm)+'"><label>Описание</label><textarea id="gsDs">'+esc(g.ds||'')+'</textarea><button class="btn" style="width:100%;margin-top:14px" onclick="saveGr(\''+ex+'\')">Сохранить</button><button class="btn red" style="width:100%;margin-top:8px" onclick="delGr(\''+ex+'\')">Удалить группу</button>');return;
}

if(type==='gradd'){
var g=d.gr[ex];if(!g)return;
var contacts=getContacts(u,d).filter(function(x){return g.mb.indexOf(x)<0&&x!==g.ow;});
mc.innerHTML=W('<h2>Добавить в группу <span class="x" onclick="clM()">✕</span></h2>'+(contacts.length?'<div id="addGrMb">'+contacts.map(function(cn){var a=d.a.find(function(x){return x.u===cn;});var blocked=!canAddCh(cn)||(a&&a.deleted);return'<div style="padding:4px 0"><input type="checkbox" value="'+cn+'"'+(blocked?' disabled':'')+' > '+(a?esc(a.deleted?'удалён':a.nm):cn)+'</div>';}).join('')+'</div><button class="btn" style="width:100%;margin-top:10px" onclick="addToGroup(\''+ex+'\')">Добавить</button>':'<div style="color:var(--tx2);text-align:center;padding:20px">Все уже в группе</div>'));return;
}

if(type==='chinfo'){
var c=d.ch[ex];if(!c)return;var members=[c.ow].concat(c.mb);
mc.innerHTML=W('<h2>📢 Информация <span class="x" onclick="clM()">✕</span></h2><div style="text-align:center;font-size:18px;font-weight:600">'+esc(c.nm)+'</div>'+(c.ds?'<div style="text-align:center;color:var(--tx2);font-size:13px;margin-top:4px">'+esc(c.ds)+'</div>':'')+'<div style="margin-top:14px;font-size:14px;font-weight:600">Участники ('+members.length+')</div>'+members.map(function(m){var a=d.a.find(function(x){return x.u===m;});var vfMark=(!a||a.deleted)?'':(a.u==='surpa'||isVf(m))?' <span class="vf">✔</span>':'';return'<div class="aci" onclick="clM();openChat(\''+m+'\')">'+avHTML(a,36)+'<div><span style="font-weight:500">'+esc(getDisplayName(a))+vfMark+'</span><div style="font-size:11px;color:var(--tx2)">@'+m+(m===c.ow?' · владелец':'')+'</div></div></div>';}).join(''));return;
}

if(type==='chadd'){var c=d.ch[ex];if(!c)return;var contacts=getContacts(u,d).filter(function(x){return c.mb.indexOf(x)<0&&x!==c.ow;});mc.innerHTML=W('<h2>Добавить <span class="x" onclick="clM()">✕</span></h2>'+(contacts.length?'<div id="addMb">'+contacts.map(function(cn){var a=d.a.find(function(x){return x.u===cn;});var blocked=!canAddCh(cn)||(a&&a.deleted);return'<div style="padding:4px 0"><input type="checkbox" value="'+cn+'"'+(blocked?' disabled':'')+' > '+(a?esc(a.deleted?'удалён':a.nm):cn)+'</div>';}).join('')+'</div><button class="btn" style="width:100%;margin-top:10px" onclick="addToChannel(\''+ex+'\')">Добавить</button>':'<div style="color:var(--tx2);text-align:center;padding:20px">Все уже в канале</div>'));return;}

if(type==='chset'){var c=d.ch[ex];if(!c)return;mc.innerHTML=W('<h2>⚙ Настройки канала <span class="x" onclick="clM()">✕</span></h2><label>Название</label><input type="text" id="csNm" value="'+esc(c.nm)+'"><label>Описание</label><textarea id="csDs">'+esc(c.ds||'')+'</textarea><button class="btn" style="width:100%;margin-top:14px" onclick="saveCh(\''+ex+'\')">Сохранить</button><button class="btn red" style="width:100%;margin-top:8px" onclick="delCh(\''+ex+'\')">Удалить канал</button>');return;}

if(type==='admin'){
if(u.u!=='surpa')return;
mc.innerHTML=W('<h2>⚡ Админ панель <span class="x" onclick="clM()">✕</span></h2><div style="font-size:13px;color:var(--tx2);margin-bottom:10px">Пользователи ('+d.a.length+')</div>'+d.a.map(function(a){var vf=isVf(a.u)||a.u==='surpa';return'<div class="adm-u">'+avHTML(a,38)+'<div style="flex:1"><div style="font-weight:500">'+esc(a.deleted?'Аккаунт удалён':a.nm)+(vf?' <span class="vf">✔</span>':'')+'</div><div style="font-size:11px;color:var(--tx2)">@'+a.u+'</div></div>'+(a.u!=='surpa'&&!a.deleted?'<button class="vfb" onclick="toggleVf(\''+a.u+'\')">'+(isVf(a.u)?'Убрать ✔':'Дать ✔')+'</button>':'')+'</div>';}).join(''));return;
}
}

function clM(){var el=document.getElementById('mdlB');var mo=el.querySelector('.mo');if(mo){mo.style.opacity='0';mo.style.transition='opacity .2s';var md=mo.querySelector('.md');if(md){md.style.transform='scale(.95)';md.style.transition='transform .2s';}setTimeout(function(){el.innerHTML='';},200);}else{el.innerHTML='';}}

function getContacts(u,d){
var contacts=[];
Object.keys(d.m).forEach(function(k){if(k.indexOf('|')<0||k.startsWith('sv|'))return;if(k.indexOf(u.u)>=0){var pp=k.split('|');var o=pp[0]===u.u?pp[1]:pp[0];if(o&&contacts.indexOf(o)<0)contacts.push(o);}});
(d.sh[u.u]||[]).forEach(function(x){if(contacts.indexOf(x)<0)contacts.push(x);});
return contacts;
}

function triggerAvatarUpload(){document.getElementById('profAvInp').click();}
function uploadAvatar(input){
var file=input.files[0];if(!file)return;if(!file.type.startsWith('image/')){toast('Выберите фото');return;}if(file.size>3*1024*1024){toast('Макс 3 МБ');return;}
var reader=new FileReader();reader.onload=function(e){var img=new Image();img.onload=function(){var canvas=document.createElement('canvas');var sz=200;canvas.width=sz;canvas.height=sz;var ctx=canvas.getContext('2d');var min=Math.min(img.width,img.height);var sx=(img.width-min)/2,sy=(img.height-min)/2;ctx.drawImage(img,sx,sy,min,min,0,0,sz,sz);var dataUrl=canvas.toDataURL('image/jpeg',0.85);var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].customAv=dataUrl;S(d);updDr();renderList();if(cur)renderHead();clM();toast('Аватарка обновлена!');setTimeout(function(){modal('profile');},300);}};img.src=e.target.result;};reader.readAsDataURL(file);input.value='';
}
function uploadAvatarSettings(input){
var file=input.files[0];if(!file)return;if(!file.type.startsWith('image/')){toast('Выберите фото');return;}if(file.size>3*1024*1024){toast('Макс 3 МБ');return;}
var reader=new FileReader();reader.onload=function(e){var img=new Image();img.onload=function(){var canvas=document.createElement('canvas');var sz=200;canvas.width=sz;canvas.height=sz;var ctx=canvas.getContext('2d');var min=Math.min(img.width,img.height);var sx=(img.width-min)/2,sy=(img.height-min)/2;ctx.drawImage(img,sx,sy,min,min,0,0,sz,sz);var dataUrl=canvas.toDataURL('image/jpeg',0.85);var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].customAv=dataUrl;S(d);updDr();renderList();if(cur)renderHead();toast('Аватарка обновлена!');clM();setTimeout(function(){modal('settings');},300);}};img.src=e.target.result;};reader.readAsDataURL(file);input.value='';
}
function removeCustomAvatar(){var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].customAv=null;S(d);updDr();renderList();if(cur)renderHead();toast('Аватарка удалена');clM();setTimeout(function(){modal('settings');},300);}}

function uploadProfBg(input){
var file=input.files[0];if(!file)return;if(!file.type.startsWith('image/')){toast('Выберите фото');return;}if(file.size>3*1024*1024){toast('Макс 3 МБ');return;}
var reader=new FileReader();reader.onload=function(e){var img=new Image();img.onload=function(){var canvas=document.createElement('canvas');canvas.width=300;canvas.height=200;var ctx=canvas.getContext('2d');ctx.drawImage(img,0,0,300,200);var dataUrl=canvas.toDataURL('image/jpeg',0.8);var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].profBg=dataUrl;S(d);updDr();toast('Фон обновлён!');clM();setTimeout(function(){modal('settings');},300);}};img.src=e.target.result;};reader.readAsDataURL(file);input.value='';
}
function pickProfBg(bg,el){var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].profBg=bg;S(d);updDr();document.querySelectorAll('.prof-bg-swatch').forEach(function(e){e.classList.remove('sel');});el.classList.add('sel');toast('Фон обновлён!');}}
function clearProfBg(){var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].profBg=null;S(d);updDr();toast('Фон сброшен');clM();setTimeout(function(){modal('settings');},300);}}

function togPrv(field,el){el.classList.toggle('on');}
function savePrv(){
var u=me(),d=D();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai<0)return;
if(!d.a[ai].prv)d.a[ai].prv={};
var rows=document.querySelectorAll('.prv-tog');
if(rows[0])d.a[ai].prv.noGift=rows[0].classList.contains('on');
if(rows[1])d.a[ai].prv.noMsg=rows[1].classList.contains('on');
if(rows[2])d.a[ai].prv.noCh=rows[2].classList.contains('on');
S(d);clM();toast('Сохранено');
}

function pickAv(id,el){tmpAv=id;var d=D(),u=me();var ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0){d.a[ai].customAv=null;S(d);}document.querySelectorAll('.av-o').forEach(function(e){e.classList.remove('sel');});el.classList.add('sel');}
function pickTheme(t,el){theme=t;localStorage.setItem('supra_theme',t);applyTheme();document.querySelectorAll('.theme-btn').forEach(function(e){e.classList.remove('sel');});el.classList.add('sel');}
function pickIf(v,el){iface=v;localStorage.setItem('supra_iface',v);applyIface();document.querySelectorAll('.if-btn').forEach(function(e){e.classList.remove('sel');});el.classList.add('sel');}

function saveSets(){
var nm=(document.getElementById('sNm').value||'').trim();
var un=(document.getElementById('sUn').value||'').trim().toLowerCase();
var bio=(document.getElementById('sBio').value||'').trim();
if(!nm){toast('Введите имя');return;}
if(!/^[a-z][a-z0-9_]{2,}$/.test(un)){toast('Username: англ, от 3 символов');return;}
var u=me(),d=D();
if(un!==u.u){
var existing=d.a.find(function(x){return x.u===un&&!x.deleted;});
if(existing){toast('Username занят');return;}
var oldU=u.u;var newM={};
Object.keys(d.m).forEach(function(k){var nk=k.replace(new RegExp(oldU.replace(/[.*+?^${}()|[\]\\]/g,'\\$&'),'g'),un);newM[nk]=d.m[k];});
d.m=newM;
Object.keys(d.m).forEach(function(k){(d.m[k]||[]).forEach(function(m){if(m.f===oldU)m.f=un;});});
Object.keys(d.ch||{}).forEach(function(cid){var c=d.ch[cid];if(c.ow===oldU)c.ow=un;var mi=c.mb.indexOf(oldU);if(mi>=0)c.mb[mi]=un;});
Object.keys(d.gr||{}).forEach(function(gid){var g=d.gr[gid];if(g.ow===oldU)g.ow=un;var mi=g.mb.indexOf(oldU);if(mi>=0)g.mb[mi]=un;});
if(d.sh[oldU]){d.sh[un]=d.sh[oldU];delete d.sh[oldU];}
d.a.forEach(function(a){if(a.gifts)a.gifts.forEach(function(g){if(g.fr===oldU)g.fr=un;});if(a.nk&&a.nk[oldU]){a.nk[un]=a.nk[oldU];delete a.nk[oldU];}});
if(d.vf&&d.vf[oldU]){d.vf[un]=true;delete d.vf[oldU];}
}
var o={nm:nm,u:un,bio:bio};if(tmpAv)o.av=tmpAv;
var i=d.a.findIndex(function(x){return x.u===u.u||x.u===un;});
if(i>=0)for(var k in o)d.a[i][k]=o[k];
S(d);localStorage.setItem('supra_sid',un);tmpAv=null;clM();updDr();renderList();if(cur&&!cur.startsWith('ch:')&&!cur.startsWith('gr:'))renderHead();toast('Сохранено');
}

function doRename(un){var nm=(document.getElementById('rnNm').value||'').trim();if(!nm)return;var d=D(),u=me(),i=d.a.findIndex(function(x){return x.u===u.u;});if(i>=0){if(!d.a[i].nk)d.a[i].nk={};d.a[i].nk[un]=nm;S(d);}clM();renderList();if(cur===un)renderHead();toast('Переименован');}
function doRenameClear(un){var d=D(),u=me(),i=d.a.findIndex(function(x){return x.u===u.u;});if(i>=0&&d.a[i].nk){delete d.a[i].nk[un];S(d);}clM();renderList();if(cur===un)renderHead();toast('Сброшено');}

function pickGift(id,el){tmpGift=id;document.querySelectorAll('.gci').forEach(function(e){e.classList.remove('sel');});el.classList.add('sel');}
function sendGift(to){
if(!tmpGift){toast('Выберите подарок');return;}
var u=me(),d=D(),tx=(document.getElementById('gTx').value||'').trim();
if(!canGift(u.u,to)&&u.u!==to){toast('Запрет');clM();return;}
var g=GIFTS.find(function(x){return x.id===tmpGift;});
var ri=d.a.findIndex(function(x){return x.u===to;});
if(ri>=0){if(!d.a[ri].gifts)d.a[ri].gifts=[];d.a[ri].gifts.push({gi:tmpGift,fr:u.u,tx:tx,tm:Date.now(),hd:false,sd:false});}
var k=ck(u.u,to);if(!d.m[k])d.m[k]=[];
d.m[k].push({f:u.u,tp:'gift',gi:tmpGift,gt:tx,tx:'🎁 Подарок: '+(g?g.name:''),tm:Date.now(),rd:false,rx:{}});
S(d);tmpGift=null;clM();renderMsgs();renderList();doConfetti(g);toast('Подарок отправлен! 🎁');
}
function togHide(i){var d=D(),u=me(),ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0&&d.a[ai].gifts[i]){d.a[ai].gifts[i].hd=!d.a[ai].gifts[i].hd;S(d);toast(d.a[ai].gifts[i].hd?'Скрыт':'Показан');}clM();modal('profile');}
function sellG(i){if(!confirm('Продать подарок?'))return;var d=D(),u=me(),ai=d.a.findIndex(function(x){return x.u===u.u;});if(ai>=0&&d.a[ai].gifts[i]){d.a[ai].gifts[i].sd=true;S(d);toast('Продан');}clM();modal('profile');}

function toggleVf(un){var d=D();if(!d.vf)d.vf={};if(d.vf[un]){delete d.vf[un];toast('Убрана ✔ @'+un);}else{d.vf[un]=true;toast('Выдана ✔ @'+un);}S(d);clM();modal('admin');}

function doConfetti(g){
var wrap=document.createElement('div');wrap.className='cfw';document.body.appendChild(wrap);
var cols=g&&g.colors?g.colors:['#5288c1','#e17076','#7bc862','#f5a623','#fff'];
for(var i=0;i<150;i++){var c=document.createElement('div');c.className='cf';c.style.background=cols[Math.floor(Math.random()*cols.length)];c.style.left=Math.random()*100+'vw';c.style.top='-14px';var s=4+Math.random()*12;c.style.width=s+'px';c.style.height=s+'px';c.style.borderRadius=Math.random()>.5?'50%':'2px';var dur=1200+Math.random()*3000,del=Math.random()*2000;c.animate([{transform:'translateY(0) rotate(0deg)',opacity:1},{transform:'translateY('+innerHeight+'px) rotate('+(300+Math.random()*600)+'deg)',opacity:0}],{duration:dur,delay:del,easing:'cubic-bezier(.25,.46,.45,.94)',fill:'forwards'});wrap.appendChild(c);}
setTimeout(function(){wrap.remove();},7000);
}

// Channel functions
function mkCh(){var nm=(document.getElementById('chNm').value||'').trim();if(!nm){toast('Введите название');return;}var ds=(document.getElementById('chDs').value||'').trim();var u=me(),d=D(),mb=[];document.querySelectorAll('#chMb input:checked').forEach(function(e){mb.push(e.value);});var cid='c'+Date.now();if(!d.ch)d.ch={};d.ch[cid]={nm:nm,ds:ds,ow:u.u,mb:mb,ps:[],cr:Date.now(),pinnedPost:null};S(d);clM();renderList();openCh(cid);toast('Канал создан');}
function addToChannel(cid){var d=D(),c=d.ch[cid];if(!c)return;var added=0;document.querySelectorAll('#addMb input:checked').forEach(function(e){if(c.mb.indexOf(e.value)<0){c.mb.push(e.value);added++;}});S(d);clM();renderHead();toast('Добавлено: '+added);}
function saveCh(cid){var d=D();d.ch[cid].nm=(document.getElementById('csNm').value||'').trim();d.ch[cid].ds=(document.getElementById('csDs').value||'').trim();S(d);clM();renderList();renderHead();toast('Сохранено');}
function delCh(cid){if(!confirm('Удалить канал?'))return;var d=D();delete d.ch[cid];S(d);cur=null;clM();showEmpty();renderList();toast('Удалён');}

// Group functions
function mkGr(){
var nm=(document.getElementById('grNm').value||'').trim();if(!nm){toast('Введите название');return;}
var ds=(document.getElementById('grDs').value||'').trim();var u=me(),d=D(),mb=[];
document.querySelectorAll('#grMb input:checked').forEach(function(e){mb.push(e.value);});
var gid='g'+Date.now();if(!d.gr)d.gr={};
d.gr[gid]={nm:nm,ds:ds,ow:u.u,mb:mb,cr:Date.now()};
if(!d.m['gr:'+gid])d.m['gr:'+gid]=[];
// System message
d.m['gr:'+gid].push({f:u.u,tp:'sys',tx:u.nm+' создал(а) группу «'+nm+'»',tm:Date.now()});
S(d);clM();renderList();openChat('gr:'+gid);toast('Группа создана');
}
function addToGroup(gid){var d=D(),g=d.gr[gid];if(!g)return;var added=0;document.querySelectorAll('#addGrMb input:checked').forEach(function(e){if(g.mb.indexOf(e.value)<0){g.mb.push(e.value);added++;}});S(d);clM();renderHead();toast('Добавлено: '+added);}
function saveGr(gid){var d=D();d.gr[gid].nm=(document.getElementById('gsNm').value||'').trim();d.gr[gid].ds=(document.getElementById('gsDs').value||'').trim();S(d);clM();renderList();renderHead();toast('Сохранено');}
function delGr(gid){if(!confirm('Удалить группу?'))return;var d=D();delete d.gr[gid];delete d.m['gr:'+gid];S(d);cur=null;clM();showEmpty();renderList();toast('Удалена');}
function kickFromGroup(gid,un){if(!confirm('Исключить @'+un+'?'))return;var d=D(),g=d.gr[gid];if(!g)return;var i=g.mb.indexOf(un);if(i>=0)g.mb.splice(i,1);d.m['gr:'+gid].push({f:me().u,tp:'sys',tx:un+' исключён(а) из группы',tm:Date.now()});S(d);clM();modal('grinfo',gid);renderHead();toast('Исключён');}

function switchAcc(un){var d=D(),acc=d.a.find(function(x){return x.u===un;});if(acc&&acc.deleted){toast('Удалён');return;}localStorage.setItem('supra_sid',un);cur=null;clM();showEmpty();updDr();renderList();if(un==='surpa')document.getElementById('adminBtn').classList.remove('hid');else document.getElementById('adminBtn').classList.add('hid');toast('Переключено на @'+un);}
function addAcc(){clM();cur=null;if(poll)clearInterval(poll);document.getElementById('app').classList.add('hid');document.getElementById('authScreen').classList.remove('hid');authMode=0;document.getElementById('regB').classList.remove('hid');document.getElementById('logB').classList.add('hid');document.getElementById('authBtn').textContent='Создать аккаунт';document.getElementById('authSub').textContent='Добавить аккаунт';document.getElementById('authTog').textContent='Войти';document.getElementById('authErr').textContent='';}

// Init
(function(){
applyTheme();
var sid=localStorage.getItem('supra_sid');
if(sid){var d=D();var acc=d.a.find(function(x){return x.u===sid;});if(acc&&!acc.deleted){startApp();return;}if(acc&&acc.deleted){var other=d.a.find(function(x){return!x.deleted;});if(other){localStorage.setItem('supra_sid',other.u);startApp();return;}}}
document.getElementById('authScreen').classList.remove('hid');
})();
</script>
</body>
</html>
