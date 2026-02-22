# para-my-lover 
[index.html](https://github.com/user-attachments/files/25472525/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💕 Para Minha Maria</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
<style>
:root { --rose:#c0395a; --blush:#f7c5d2; --cream:#fff8f0; --gold:#d4a853; --deep:#1a0a10; }
* { box-sizing:border-box; margin:0; padding:0; }
html { scroll-behavior:smooth; }
body { background:var(--deep); font-family:'Lato',sans-serif; min-height:100vh; overflow-x:hidden; color:var(--cream); }

.petals { position:fixed; inset:0; pointer-events:none; z-index:0; overflow:hidden; }
.petal { position:absolute; background:radial-gradient(ellipse at 30% 30%,#f7c5d2,#c0395a88); border-radius:50% 0 50% 0; animation:fall linear infinite; opacity:0; }
@keyframes fall { 0%{transform:translateY(-20px) rotate(0deg);opacity:.8} 100%{transform:translateY(110vh) rotate(360deg);opacity:0} }

.app { position:relative; z-index:1; max-width:480px; margin:0 auto; padding:20px 14px 100px; display:flex; flex-direction:column; align-items:center; gap:20px; }

header { text-align:center; padding-top:16px; }
.app-name { font-family:'Playfair Display',serif; font-size:clamp(1.7rem,7vw,2.5rem); font-style:italic; background:linear-gradient(135deg,var(--gold),var(--blush)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
.app-subtitle { font-size:.72rem; letter-spacing:3px; text-transform:uppercase; color:var(--rose); margin-top:5px; opacity:.8; }
.heart-icon { font-size:2rem; animation:pulse 1.5s ease-in-out infinite; display:block; margin:8px auto 2px; }
@keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.25)} }

.counter-card { width:100%; background:linear-gradient(135deg,#3a0a20,#1f0a14); border:1px solid var(--gold); border-radius:20px; padding:20px; text-align:center; box-shadow:0 0 30px #d4a85322; }
.counter-label { font-size:.7rem; letter-spacing:3px; text-transform:uppercase; color:var(--gold); margin-bottom:10px; }
.counter-numbers { display:flex; justify-content:center; gap:14px; flex-wrap:wrap; }
.counter-unit { display:flex; flex-direction:column; align-items:center; gap:3px; }
.counter-num { font-family:'Playfair Display',serif; font-size:2.2rem; color:var(--blush); line-height:1; text-shadow:0 0 20px #c0395a88; }
.counter-name { font-size:.6rem; letter-spacing:2px; text-transform:uppercase; color:var(--rose); opacity:.8; }
.counter-sep { font-size:1.8rem; color:#c0395a44; align-self:center; }
.counter-since { margin-top:10px; font-size:.74rem; color:#c0395a88; font-style:italic; }

.card { width:100%; background:linear-gradient(145deg,#2a0f1a,#1f0d16); border:1px solid #c0395a44; border-radius:20px; padding:20px 18px; box-shadow:0 0 30px #c0395a0d,inset 0 1px 0 #ffffff08; }
.card-title { font-family:'Playfair Display',serif; font-size:.92rem; color:var(--gold); margin-bottom:12px; letter-spacing:1px; }

.love-btn { width:100%; padding:17px; background:linear-gradient(135deg,var(--rose),#8b1a34); border:none; border-radius:50px; font-family:'Playfair Display',serif; font-size:1.3rem; font-style:italic; color:#fff; cursor:pointer; box-shadow:0 4px 20px #c0395a55; transition:all .2s; letter-spacing:1px; }
.love-btn:hover { transform:translateY(-2px); box-shadow:0 8px 30px #c0395a88; }
.love-btn:active { transform:scale(.97); }

#message-box { width:100%; background:linear-gradient(135deg,#3a0a20,#1f0a14); border:1px solid var(--rose); border-radius:16px; padding:18px; text-align:center; font-family:'Playfair Display',serif; font-size:1rem; font-style:italic; color:var(--blush); line-height:1.8; display:none; box-shadow:0 0 30px #c0395a22; animation:fadeIn .4s ease; }
@keyframes fadeIn { from{opacity:0;transform:translateY(10px)} to{opacity:1;transform:translateY(0)} }

textarea,.text-input { width:100%; padding:12px 14px; background:#0f0508; border:1px solid #c0395a44; border-radius:12px; color:var(--cream); font-family:'Lato',sans-serif; font-size:.9rem; outline:none; transition:border-color .2s; line-height:1.6; }
textarea { min-height:100px; resize:vertical; }
textarea::placeholder,.text-input::placeholder { color:#c0395a55; font-style:italic; }
textarea:focus,.text-input:focus { border-color:var(--rose); box-shadow:0 0 0 3px #c0395a18; }

.send-btn { width:100%; padding:13px; background:transparent; border:1.5px solid var(--rose); border-radius:50px; color:var(--blush); font-size:.86rem; cursor:pointer; letter-spacing:1px; transition:all .2s; font-family:'Lato',sans-serif; margin-top:10px; }
.send-btn:hover { background:var(--rose); color:#fff; transform:translateY(-1px); }

.img-zone { width:100%; min-height:80px; border:2px dashed #c0395a44; border-radius:14px; display:flex; flex-direction:column; align-items:center; justify-content:center; gap:6px; padding:16px; cursor:pointer; position:relative; transition:border-color .2s,background .2s; }
.img-zone:hover { border-color:var(--rose); background:#c0395a08; }
.img-zone input { position:absolute; inset:0; opacity:0; cursor:pointer; width:100%; height:100%; }
.img-zone-text { font-size:.78rem; color:#c0395a88; text-align:center; font-style:italic; }
.img-zone-icon { font-size:1.6rem; }
#img-preview { width:100%; border-radius:12px; display:none; margin-top:10px; border:1px solid #c0395a44; max-height:260px; object-fit:cover; }

/* YouTube */
.yt-tip { font-size:.72rem; color:#c0395a88; font-style:italic; margin-bottom:10px; padding:8px 12px; background:#0f0508; border-radius:8px; border-left:2px solid var(--rose); line-height:1.5; }
.yt-row { display:flex; gap:8px; margin-bottom:10px; }
.yt-row .text-input { flex:1; height:44px; }
.yt-add-btn { padding:0 16px; height:44px; background:linear-gradient(135deg,var(--rose),#8b1a34); border:none; border-radius:12px; color:#fff; font-size:.95rem; cursor:pointer; transition:all .2s; white-space:nowrap; font-weight:700; }
.yt-add-btn:hover { transform:scale(1.05); }

.yt-player-card { width:100%; background:#0f0508; border:1px solid #c0395a33; border-radius:14px; overflow:hidden; display:none; margin-bottom:10px; }
.yt-thumb-wrap { position:relative; width:100%; aspect-ratio:16/9; cursor:pointer; overflow:hidden; }
.yt-thumb { width:100%; height:100%; object-fit:cover; display:block; }
.yt-thumb-overlay { position:absolute; inset:0; background:rgba(0,0,0,.45); display:flex; align-items:center; justify-content:center; transition:background .2s; }
.yt-thumb-overlay:hover { background:rgba(0,0,0,.25); }
.yt-play-circle { width:60px; height:60px; background:var(--rose); border-radius:50%; display:flex; align-items:center; justify-content:center; font-size:1.5rem; box-shadow:0 4px 20px #c0395a88; transition:transform .2s; }
.yt-thumb-wrap:hover .yt-play-circle { transform:scale(1.1); }
.yt-embed-wrap { width:100%; aspect-ratio:16/9; display:none; }
.yt-embed-wrap iframe { width:100%; height:100%; border:none; display:block; }
.yt-info { padding:10px 14px; display:flex; align-items:center; gap:8px; }
.yt-title { font-size:.8rem; color:var(--blush); flex:1; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; font-style:italic; }
.yt-open-btn { padding:6px 12px; background:transparent; border:1px solid #c0395a55; border-radius:8px; color:var(--rose); font-size:.7rem; cursor:pointer; transition:all .2s; white-space:nowrap; }
.yt-open-btn:hover { background:var(--rose); color:#fff; border-color:var(--rose); }

.yt-controls { display:none; gap:6px; margin-bottom:8px; }
.yt-ctrl-btn { flex:1; padding:9px; background:#0f0508; border:1px solid #c0395a33; border-radius:10px; color:var(--blush); font-size:.78rem; cursor:pointer; transition:all .2s; text-align:center; }
.yt-ctrl-btn:hover { border-color:var(--rose); background:#c0395a18; }

.playlist { display:flex; flex-direction:column; gap:6px; }
.pl-item { display:flex; align-items:center; gap:8px; padding:9px 12px; background:#0f0508; border:1px solid #c0395a22; border-radius:10px; cursor:pointer; transition:all .2s; }
.pl-item:hover { border-color:var(--rose); background:#c0395a12; }
.pl-item.active { border-color:var(--rose); background:#c0395a22; }
.pl-thumb { width:42px; height:28px; border-radius:5px; object-fit:cover; flex-shrink:0; background:#1a0610; }
.pl-name { font-size:.8rem; color:var(--blush); flex:1; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
.pl-del { font-size:.85rem; color:#c0395a44; cursor:pointer; padding:2px 6px; border-radius:6px; transition:color .2s; flex-shrink:0; }
.pl-del:hover { color:var(--rose); }
.pl-empty { font-size:.78rem; color:#c0395a44; font-style:italic; text-align:center; padding:10px 0; }

/* Chat */
.chat-wrap { width:100%; background:linear-gradient(145deg,#1a0609,#110408); border:1px solid #c0395a44; border-radius:20px; overflow:hidden; }
.chat-header { background:linear-gradient(90deg,#3a0a20,#2a0a18); padding:14px 16px; display:flex; align-items:center; gap:10px; border-bottom:1px solid #c0395a33; }
.chat-avatar { width:38px; height:38px; border-radius:50%; background:linear-gradient(135deg,var(--rose),#8b1a34); display:flex; align-items:center; justify-content:center; font-size:1.2rem; flex-shrink:0; }
.chat-name-h { font-family:'Playfair Display',serif; font-size:.95rem; font-style:italic; color:var(--blush); }
.chat-status { font-size:.66rem; color:#4ade8088; letter-spacing:1px; }
.chat-messages { height:340px; overflow-y:auto; padding:14px 12px; display:flex; flex-direction:column; gap:8px; scroll-behavior:smooth; }
.chat-messages::-webkit-scrollbar { width:3px; }
.chat-messages::-webkit-scrollbar-thumb { background:#c0395a44; border-radius:4px; }
.msg { display:flex; flex-direction:column; max-width:80%; animation:msgIn .22s ease; }
@keyframes msgIn { from{opacity:0;transform:translateY(6px)} to{opacity:1;transform:translateY(0)} }
.msg.me { align-self:flex-end; align-items:flex-end; }
.msg.her { align-self:flex-start; align-items:flex-start; }
.msg-bubble { padding:9px 13px; border-radius:16px; font-size:.88rem; line-height:1.55; word-break:break-word; }
.msg.me .msg-bubble { background:linear-gradient(135deg,#8b1a34,#5a0f22); border-bottom-right-radius:4px; color:var(--cream); box-shadow:0 2px 10px #c0395a33; }
.msg.her .msg-bubble { background:linear-gradient(135deg,#2a0f1a,#1f0a14); border:1px solid #c0395a33; border-bottom-left-radius:4px; color:var(--blush); }
.msg-time { font-size:.6rem; color:#c0395a66; margin-top:3px; padding:0 2px; }
.msg-sender { font-size:.63rem; color:var(--gold); margin-bottom:3px; font-style:italic; }
.who-bar { display:flex; gap:8px; padding:8px 12px; background:#110408; border-bottom:1px solid #c0395a1a; align-items:center; }
.who-btn { flex:1; padding:7px; background:transparent; border:1px solid #c0395a33; border-radius:20px; color:#c0395a88; font-size:.74rem; cursor:pointer; transition:all .2s; text-align:center; }
.who-btn.active { background:var(--rose); color:#fff; border-color:var(--rose); }
.who-label { font-size:.68rem; color:#c0395a66; white-space:nowrap; }
.chat-input-bar { display:flex; align-items:center; gap:8px; padding:10px 12px; background:#1a0609; border-top:1px solid #c0395a22; }
.chat-input-bar .text-input { flex:1; min-height:unset; height:42px; border-radius:21px; padding:10px 16px; font-size:.88rem; }
.chat-send { width:42px; height:42px; flex-shrink:0; background:linear-gradient(135deg,var(--rose),#8b1a34); border:none; border-radius:50%; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:1rem; transition:all .2s; box-shadow:0 2px 10px #c0395a44; }
.chat-send:hover { transform:scale(1.1); }
.conn-status { font-size:.65rem; padding:4px 10px; border-radius:10px; }
.conn-ok { color:#4ade80; background:#4ade8011; }
.conn-off { color:#f87171; background:#f8717111; }

.divider { width:60%; height:1px; background:linear-gradient(90deg,transparent,#c0395a44,transparent); }

.music-fab { position:fixed; bottom:24px; right:20px; width:52px; height:52px; background:linear-gradient(135deg,var(--rose),#8b1a34); border:none; border-radius:50%; font-size:1.3rem; cursor:pointer; box-shadow:0 4px 20px #c0395a66; z-index:100; display:flex; align-items:center; justify-content:center; transition:transform .2s; }
.music-fab:hover { transform:scale(1.1); }
.music-fab.spin { animation:spin 3s linear infinite; }
@keyframes spin { to{transform:rotate(360deg)} }

.burst { position:fixed; pointer-events:none; z-index:999; }
.burst-heart { position:absolute; font-size:1.3rem; animation:burstA 1s ease-out forwards; }
@keyframes burstA { 0%{transform:translate(0,0) scale(0);opacity:1} 100%{transform:translate(var(--dx),var(--dy)) scale(1.2);opacity:0} }
</style>
</head>
<body>

<div class="petals" id="petals"></div>

<div class="app">

  <header>
    <span class="heart-icon">❤️</span>
    <div class="app-name" id="app-name">Para Minha Maria</div>
    <div class="app-subtitle">com todo o meu amor</div>
  </header>

  <div class="counter-card">
    <div class="counter-label">💍 Juntos há</div>
    <div class="counter-numbers">
      <div class="counter-unit"><div class="counter-num" id="cnt-a">0</div><div class="counter-name">anos</div></div>
      <div class="counter-sep">·</div>
      <div class="counter-unit"><div class="counter-num" id="cnt-m">0</div><div class="counter-name">meses</div></div>
      <div class="counter-sep">·</div>
      <div class="counter-unit"><div class="counter-num" id="cnt-d">0</div><div class="counter-name">dias</div></div>
    </div>
    <div class="counter-since">desde 11 de novembro de 2025 🌹</div>
  </div>

  <div class="card" style="text-align:center">
    <button class="love-btn" onclick="sendLove(event)">💕 Eu te amo, Maria!</button>
  </div>
  <div id="message-box"></div>
  <div class="divider"></div>

  <!-- 🎵 YouTube -->
  <div class="card">
    <div class="card-title">🎵 Player de Música</div>
    <div class="yt-tip">
      💡 Cole o link do YouTube e clique <strong>＋ Add</strong>.<br>
      Clique na <strong>thumbnail</strong> para tocar. Se bloquear, use <strong>"Abrir no YouTube"</strong>.
    </div>
    <div class="yt-row">
      <input class="text-input" id="yt-url" placeholder="https://youtube.com/watch?v=...">
      <button class="yt-add-btn" onclick="addToPlaylist()">＋ Add</button>
    </div>

    <div class="yt-player-card" id="yt-player-card">
      <div class="yt-thumb-wrap" id="yt-thumb-wrap" onclick="toggleEmbed()">
        <img class="yt-thumb" id="yt-thumb" src="" alt="">
        <div class="yt-thumb-overlay">
          <div class="yt-play-circle">▶</div>
        </div>
      </div>
      <div class="yt-embed-wrap" id="yt-embed-wrap">
        <iframe id="yt-frame" allow="autoplay; encrypted-media; fullscreen" allowfullscreen></iframe>
      </div>
      <div class="yt-info">
        <div class="yt-title" id="yt-title">🎵 Tocando agora...</div>
        <button class="yt-open-btn" onclick="openInYt()">▶ Abrir no YouTube</button>
      </div>
    </div>

    <div class="yt-controls" id="yt-controls">
      <div class="yt-ctrl-btn" onclick="ytPrev()">⏮ Anterior</div>
      <div class="yt-ctrl-btn" onclick="ytNext()">Próxima ⏭</div>
      <div class="yt-ctrl-btn" onclick="ytShuffle()">🔀 Aleatório</div>
    </div>

    <div class="playlist" id="playlist">
      <div class="pl-empty" id="pl-empty">Nenhuma música ainda 🎶</div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="card">
    <div class="card-title">✍️ Escreva uma mensagem</div>
    <textarea id="msg-input" placeholder="Escreva algo especial para a Maria..."></textarea>
    <button class="send-btn" onclick="sendMsg()">Enviar mensagem ✉️</button>
  </div>

  <div class="card">
    <div class="card-title">🌹 Envie uma foto especial</div>
    <div class="img-zone">
      <input type="file" id="img-input" accept="image/*" onchange="loadImg(event)">
      <div class="img-zone-icon">📷</div>
      <div class="img-zone-text">Toque aqui para escolher uma foto</div>
    </div>
    <img id="img-preview" alt="Foto especial">
  </div>

  <div class="divider"></div>

  <!-- Chat -->
  <div style="width:100%">
    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:10px">
      <div class="card-title" style="color:var(--gold);font-family:'Playfair Display',serif;font-size:.92rem;letter-spacing:1px;margin:0">💬 Chat em Tempo Real</div>
      <div class="conn-status conn-off" id="conn-status">⚡ conectando...</div>
    </div>
    <div class="chat-wrap">
      <div class="chat-header">
        <div class="chat-avatar">🌹</div>
        <div style="flex:1">
          <div class="chat-name-h">Maria</div>
          <div class="chat-status" id="online-status">● online com amor</div>
        </div>
        <span style="font-size:1.1rem">❤️</span>
      </div>
      <div class="who-bar">
        <div class="who-label">Enviando como:</div>
        <button class="who-btn active" id="who-me" onclick="setWho('me')">💙 Eu (você)</button>
        <button class="who-btn" id="who-her" onclick="setWho('her')">🌹 Maria</button>
      </div>
      <div class="chat-messages" id="chat-messages">
        <div style="text-align:center;font-size:.75rem;color:#c0395a55;font-style:italic;padding:20px 0">Carregando mensagens... 💕</div>
      </div>
      <div class="chat-input-bar">
        <input class="text-input" id="chat-input" placeholder="Mensagem..." onkeydown="if(event.key==='Enter'&&!event.shiftKey){sendChat();event.preventDefault();}">
        <button class="chat-send" onclick="sendChat()">➤</button>
      </div>
    </div>
  </div>

  <div class="card">
    <div class="card-title">🏷️ Personalizar nome do app</div>
    <input class="text-input" id="name-input" placeholder="Ex: Para minha princesa...">
    <button class="send-btn" onclick="updateName()">Salvar nome 💾</button>
  </div>

</div>

<button class="music-fab" id="music-fab" onclick="toggleBgMusic()">🎵</button>
<audio id="bg-audio" loop src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"></audio>

<script type="module">
import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
import { getDatabase,ref,push,onChildAdded,serverTimestamp,onValue,set,onDisconnect }
  from "https://www.gstatic.com/firebasejs/10.12.0/firebase-database.js";
const app=initializeApp({databaseURL:"https://my-love-145ae-default-rtdb.firebaseio.com/"});
const db=getDatabase(app);
const msgRef=ref(db,'chat/messages');
const presRef=ref(db,'chat/presence/'+Date.now());
set(presRef,true); onDisconnect(presRef).remove();
onValue(ref(db,'chat/presence'),snap=>{
  const c=snap.exists()?Object.keys(snap.val()).length:0;
  document.getElementById('online-status').textContent=c>=2?'● vocês dois estão online 💕':c===1?'● você está online':'● offline';
});
onValue(ref(db,'.info/connected'),snap=>{
  const el=document.getElementById('conn-status');
  if(snap.val()){el.textContent='✅ conectado';el.className='conn-status conn-ok';}
  else{el.textContent='❌ sem conexão';el.className='conn-status conn-off';}
});
window._fbSend=function(text,who){push(msgRef,{text,who,name:who==='me'?'Você':'Maria',ts:serverTimestamp()});};
let first=true;
const box=document.getElementById('chat-messages');
onChildAdded(msgRef,snap=>{
  const d=snap.val();if(!d)return;
  if(first){box.innerHTML='';first=false;}
  const now=d.ts?new Date(d.ts):new Date();
  const time=now.getHours().toString().padStart(2,'0')+':'+now.getMinutes().toString().padStart(2,'0');
  const wrap=document.createElement('div');wrap.className='msg '+(d.who==='me'?'me':'her');
  const nm=d.who==='her'?`<div class="msg-sender">Maria</div>`:'';
  wrap.innerHTML=`${nm}<div class="msg-bubble">${esc(d.text)}</div><div class="msg-time">${time}</div>`;
  box.appendChild(wrap);box.scrollTop=box.scrollHeight;
});
function esc(t){return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');}
</script>

<script>
/* Petals */
const pc=document.getElementById('petals');
for(let i=0;i<32;i++){const p=document.createElement('div');p.className='petal';p.style.cssText=`left:${Math.random()*100}%;width:${6+Math.random()*9}px;height:${8+Math.random()*13}px;animation-duration:${5+Math.random()*7}s;animation-delay:${Math.random()*10}s;`;pc.appendChild(p);}

/* Counter */
(function tick(){
  const s=new Date(2025,10,11),n=new Date();
  let a=n.getFullYear()-s.getFullYear(),m=n.getMonth()-s.getMonth(),d=n.getDate()-s.getDate();
  if(d<0){m--;d+=new Date(n.getFullYear(),n.getMonth(),0).getDate();}
  if(m<0){a--;m+=12;}
  document.getElementById('cnt-a').textContent=a;
  document.getElementById('cnt-m').textContent=m;
  document.getElementById('cnt-d').textContent=d;
  setTimeout(tick,60000);
})();

/* Love */
const ll=['💕 Eu te amo, Maria!','🌹 Você é tudo pra mim!','💖 Meu coração é seu!','✨ Você ilumina minha vida!','💗 Te amo mais a cada dia!'];
let li=0;
function sendLove(e){burstHearts(e.clientX,e.clientY);showMsg(ll[li++%ll.length]);}
function sendMsg(){const t=document.getElementById('msg-input').value.trim();if(!t){showMsg('💬 Escreva algo primeiro!');return;}showMsg('✉️ '+t);document.getElementById('msg-input').value='';}
function showMsg(t){const b=document.getElementById('message-box');b.style.display='none';b.textContent=t;void b.offsetWidth;b.style.display='block';b.scrollIntoView({behavior:'smooth',block:'center'});}

/* Image */
function loadImg(e){const f=e.target.files[0];if(!f)return;const r=new FileReader();r.onload=ev=>{const i=document.getElementById('img-preview');i.src=ev.target.result;i.style.display='block';i.scrollIntoView({behavior:'smooth',block:'center'});};r.readAsDataURL(f);}

/* YouTube */
let playlist=[],curIdx=-1,embedOpen=false;
function extractId(url){const m=url.match(/(?:youtu\.be\/|[?&]v=|embed\/)([A-Za-z0-9_-]{11})/);return m?m[1]:null;}
function thumb(id){return`https://img.youtube.com/vi/${id}/hqdefault.jpg`;}

function addToPlaylist(){
  const raw=document.getElementById('yt-url').value.trim();if(!raw)return;
  const id=extractId(raw);
  if(!id){alert('❌ Link inválido!\nUse: https://youtube.com/watch?v=XXXXXXXXXXX\nou: https://youtu.be/XXXXXXXXXXX');return;}
  playlist.push({id,name:'🎵 Música '+(playlist.length+1)});
  document.getElementById('yt-url').value='';
  renderPL();
  if(playlist.length===1)playIdx(0);
}

function playIdx(i){
  if(i<0||i>=playlist.length)return;
  curIdx=i; embedOpen=false;
  const {id,name}=playlist[i];
  document.getElementById('yt-player-card').style.display='block';
  document.getElementById('yt-thumb').src=thumb(id);
  document.getElementById('yt-thumb-wrap').style.display='block';
  document.getElementById('yt-embed-wrap').style.display='none';
  document.getElementById('yt-frame').src='';
  document.getElementById('yt-title').textContent=name;
  renderPL();
  document.getElementById('yt-player-card').scrollIntoView({behavior:'smooth',block:'center'});
}

function toggleEmbed(){
  if(!playlist[curIdx])return;
  embedOpen=!embedOpen;
  document.getElementById('yt-thumb-wrap').style.display=embedOpen?'none':'block';
  document.getElementById('yt-embed-wrap').style.display=embedOpen?'block':'none';
  if(embedOpen){
    document.getElementById('yt-frame').src=
      `https://www.youtube-nocookie.com/embed/${playlist[curIdx].id}?autoplay=1&rel=0&modestbranding=1`;
  } else {
    document.getElementById('yt-frame').src='';
  }
}

function openInYt(){if(playlist[curIdx])window.open('https://www.youtube.com/watch?v='+playlist[curIdx].id,'_blank');}
function ytNext(){playIdx((curIdx+1)%playlist.length);}
function ytPrev(){playIdx((curIdx-1+playlist.length)%playlist.length);}
function ytShuffle(){let i;do{i=Math.floor(Math.random()*playlist.length);}while(i===curIdx&&playlist.length>1);playIdx(i);}
function removeTr(i,e){
  e.stopPropagation();playlist.splice(i,1);
  if(curIdx===i){curIdx=-1;document.getElementById('yt-player-card').style.display='none';document.getElementById('yt-frame').src='';}
  else if(curIdx>i){curIdx--;}
  renderPL();
}
function renderPL(){
  const el=document.getElementById('playlist');
  document.getElementById('pl-empty').style.display=playlist.length?'none':'block';
  el.querySelectorAll('.pl-item').forEach(i=>i.remove());
  playlist.forEach((s,i)=>{
    const d=document.createElement('div');d.className='pl-item'+(i===curIdx?' active':'');
    d.innerHTML=`<img class="pl-thumb" src="${thumb(s.id)}" onerror="this.style.display='none'"><div class="pl-name">${s.name}</div><div class="pl-del" onclick="removeTr(${i},event)">✕</div>`;
    d.onclick=()=>playIdx(i);el.appendChild(d);
  });
  document.getElementById('yt-controls').style.display=playlist.length>1?'flex':'none';
}

/* Chat */
let whoAmI='me';
function setWho(w){whoAmI=w;document.getElementById('who-me').classList.toggle('active',w==='me');document.getElementById('who-her').classList.toggle('active',w==='her');}
function sendChat(){const inp=document.getElementById('chat-input');const txt=inp.value.trim();if(!txt)return;inp.value='';if(window._fbSend)window._fbSend(txt,whoAmI);}

/* Name */
function updateName(){const v=document.getElementById('name-input').value.trim();if(!v)return;document.getElementById('app-name').textContent=v;document.title='💕 '+v;document.getElementById('name-input').value='';}

/* BG Music */
let bgOn=false;
function toggleBgMusic(){const a=document.getElementById('bg-audio'),b=document.getElementById('music-fab');if(bgOn){a.pause();b.textContent='🎵';b.classList.remove('spin');}else{a.play().catch(()=>{});b.textContent='🎶';b.classList.add('spin');}bgOn=!bgOn;}

/* Burst */
function burstHearts(cx,cy){const c=document.createElement('div');c.className='burst';c.style.left=cx+'px';c.style.top=cy+'px';const em=['❤️','💕','💖','💗','🌹','✨'];for(let i=0;i<14;i++){const h=document.createElement('div');h.className='burst-heart';h.textContent=em[Math.floor(Math.random()*em.length)];const a=Math.random()*Math.PI*2,dist=60+Math.random()*90;h.style.setProperty('--dx',Math.cos(a)*dist+'px');h.style.setProperty('--dy',Math.sin(a)*dist+'px');h.style.animationDelay=Math.random()*.15+'s';c.appendChild(h);}document.body.appendChild(c);setTimeout(()=>c.remove(),1300);}
</script>
</body>
</html>
