<!DOCTYPE html>
<html lang="tk"><head><meta charset="utf-8"><title>Futbol</title>
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<style>
:root{--bg:#0b0f17;--card:#161c28;--nav:#111827;--tx:#f3f4f6;--mu:#8b95a7;--ac:#38bdf8;--bad:#ef4444;color-scheme:dark;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
*{box-sizing:border-box}html,body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,-apple-system,Segoe UI,Roboto,sans-serif}
#app{max-width:520px;margin:0 auto;padding:16px 14px 100px}
h2{margin:6px 0 12px;font-size:20px}.card{background:var(--card);border-radius:16px;padding:14px;margin-bottom:10px}
.mu{color:var(--mu);font-size:13px}.row{display:flex;gap:8px;align-items:center}.sp{justify-content:space-between}
input,select,textarea{width:100%;background:#0f1520;border:1px solid #243047;color:var(--tx);border-radius:12px;padding:11px 12px;font-size:15px;margin:4px 0}
button{background:var(--ac);color:#06202e;border:0;border-radius:12px;padding:10px 14px;font-weight:600;font-size:14px}
button.g{background:#243047;color:var(--tx)}button.r{background:var(--bad);color:#fff}
nav{position:fixed;left:10px;right:10px;bottom:calc(10px + env(safe-area-inset-bottom,0px));max-width:500px;margin:0 auto;background:var(--nav);border-radius:24px;display:flex;justify-content:space-around;padding:10px 4px;border:1px solid #1f2937}
nav div{text-align:center;font-size:12px;color:#fff;flex:1}nav div.on{color:var(--ac)}nav b{display:block;font-size:20px;font-weight:400}
.sc{font-size:22px;font-weight:700}.tag{background:#243047;border-radius:8px;padding:2px 8px;font-size:12px}
.msg{padding:8px 12px;border-radius:14px;margin:6px 0;background:#1d2636;max-width:85%}.msg.me{background:#0e4a63;margin-left:auto}.msg.adm{border:1px solid var(--ac)}
.ava{width:84px;height:84px;border-radius:50%;background:#243047;object-fit:cover;display:block;margin:0 auto 8px}
.seg{display:flex;gap:6px;margin-bottom:8px}.seg button{flex:1}
table{width:100%;font-size:12px;border-collapse:collapse}td,th{padding:6px 4px;text-align:left;border-bottom:1px solid #243047;word-break:break-all}
</style>
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2.58.0/dist/umd/supabase.js"></script>
</head><body><div id="app"></div>
<script>
/* === ŞULARY ÖZÜŇKI BILEN ALMAŞDYR === */
const SUPA_URL='https://tbpftwruspfrcwrfcnxc.supabase.co';
const SUPA_KEY='sb_publishable_DCkYHwq3qnMgeYD-hjW4Ug_Eng57PgB';
/* ==================================== */
const sb=supabase.createClient(SUPA_URL,SUPA_KEY);
const $=s=>document.querySelector(s);
const esc=s=>String(s??'').replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const err=r=>{if(r.error){alert(r.error.message);return true}return false};
let S={me:null,tab:'home',mt:'next',q:'',adm:false,dmu:null,news:[],matches:[],chat:[],dm:[],bets:[],users:[]};
let sub;
async function load(){
 if(!S.me)return render();
 const q=(t,o)=>sb.from(t).select('*').order(o,{ascending:false});
 const [p,n,m,c,b,d]=await Promise.all([sb.from('profiles').select('*'),q('news','created'),q('matches','created'),q('chat','ts').limit(100),q('bets','created'),q('dm','ts')]);
 S.users=p.data||[];S.me=S.users.find(x=>x.id===S.me.id)||S.me;
 S.news=n.data||[];S.matches=m.data||[];S.chat=(c.data||[]).reverse();S.bets=b.data||[];S.dm=(d.data||[]).reverse();render()}
function subscribe(){if(sub)return;let t;sub=sb.channel('all').on('postgres_changes',{event:'*',schema:'public'},()=>{clearTimeout(t);t=setTimeout(load,300)}).subscribe()}
async function start(u){S.me={id:u.id};await load();subscribe()}
async function auth(reg){const m=$('#m').value.trim().toLowerCase(),k=$('#k').value;
 if(!m||k.length<6)return alert('Gmail we iň az 6 belgili kod ýaz');
 const r=reg?await sb.auth.signUp({email:m,password:k,options:{data:{ady:$('#n').value.trim(),nomer:$('#p').value.trim()}}}):await sb.auth.signInWithPassword({email:m,password:k});
 if(err(r))return;if(!r.data.session)return alert('Hasap açyldy. Indi "Gir" bas.');start(r.data.session.user)}
async function out(){await sb.auth.signOut();S.me=null;S.tab='home';S.adm=false;render()}
function go(t){S.tab=t;S.adm=false;S.dmu=null;render()}
function dmList(D,side){return D.map(m=>`<div class="msg ${m.frm===side?'me':''}">${esc(m.t)}</div>`).join('')}
async function sendDm(uid,frm){const t=$('#dt').value.trim();if(!t)return;$('#dt').value='';err(await sb.from('dm').insert({uid,frm,t}));load()}
async function sendMsg(){const t=$('#ct').value.trim();if(!t)return;$('#ct').value='';err(await sb.from('chat').insert({u:S.me.id,name:S.me.ady||S.me.mail,adm:S.me.is_admin,t}));load()}
async function bet(id){err(await sb.rpc('place_bet',{mid:id,pick:$('#bp'+id).value,stake:parseInt($('#bs'+id).value)||0}));load()}
async function saveProfile(){err(await sb.from('profiles').update({ady:$('#pn').value.trim()}).eq('id',S.me.id));load()}
function shrink(f,w){return new Promise(ok=>{const r=new FileReader();r.onload=()=>{const i=new Image();i.onload=()=>{const k=Math.min(1,w/i.width),c=document.createElement('canvas');c.width=i.width*k;c.height=i.height*k;c.getContext('2d').drawImage(i,0,0,c.width,c.height);ok(c.toDataURL('image/jpeg',.7))};i.src=r.result};r.readAsDataURL(f)})}
async function setAva(e){const f=e.target.files[0];if(!f)return;const c=await shrinkSq(f);err(await sb.from('profiles').update({ava:c}).eq('id',S.me.id));load()}
function shrinkSq(f){return new Promise(ok=>{const r=new FileReader();r.onload=()=>{const i=new Image();i.onload=()=>{const c=document.createElement('canvas');c.width=c.height=160;const z=Math.min(i.width,i.height);c.getContext('2d').drawImage(i,(i.width-z)/2,(i.height-z)/2,z,z,0,0,160,160);ok(c.toDataURL('image/jpeg',.8))};i.src=r.result};r.readAsDataURL(f)})}
async function addBal(id,s){const v=parseInt($('#ab'+id).value);if(!v)return;err(await sb.rpc('admin_add_bal',{uid:id,amt:s*v}));load()}
async function addNews(){const t=$('#nt').value.trim();if(!t)return;const F=[...$('#ni').files].slice(0,3);const imgs=await Promise.all(F.map(f=>shrink(f,800)));err(await sb.from('news').insert({t,d:$('#nd').value.trim(),imgs}));load()}
async function addMatch(){const a=$('#ma').value.trim(),b=$('#mb').value.trim();if(!a||!b)return;err(await sb.from('matches').insert({a,b,dt:$('#md').value.trim()}));load()}
async function setRes(id){const r=$('#r'+id).value.trim();if(!/^\d+:\d+$/.test(r))return alert('Mysal: 2:1');err(await sb.rpc('set_result',{mid:id,res:r}));load()}
async function del(t,id){if(!confirm('Pozmalymy?'))return;err(await sb.from(t).delete().eq('id',id));load()}
function matchCard(m){const past=m.r!==null;
return `<div class="card"><div class="row sp mu"><span>${esc(m.dt)}</span><span class="tag">${past?'Gutardy':'Geljek'}</span></div>
<div class="row sp" style="margin:8px 0"><b>${esc(m.a)}</b><span class="sc">${past?esc(m.r):'–'}</span><b>${esc(m.b)}</b></div>
${past?'':`<div class="row"><select id="bp${m.id}" style="flex:1"><option value="1">1 (${esc(m.a)})</option><option value="X">X (deň)</option><option value="2">2 (${esc(m.b)})</option></select><input id="bs${m.id}" type="number" placeholder="Bal" style="width:90px"><button onclick="bet(${m.id})">Çakla</button></div>`}</div>`}
function render(){const ae=document.activeElement,id=ae&&ae.id,val=ae&&ae.value;draw();if(id){const e=document.getElementById(id);if(e&&e.tagName!=='BUTTON'){if(e.type!=='file')e.value=val;e.focus()}}}
function draw(){const A=$('#app'),u=S.me&&S.me.mail!==undefined?S.me:null;
if(!u){A.innerHTML=`<h2>⚽ Futbol</h2><div class="card"><p class="mu">Hasap aç ýa-da gir</p><input id="n" placeholder="Ady"><input id="m" placeholder="Gmail" type="email"><input id="p" placeholder="Telefon belgi" type="tel"><input id="k" placeholder="Kod (iň az 6 belgi)" type="password"><div class="row" style="margin-top:8px"><button style="flex:1" onclick="auth(false)">Gir</button><button class="g" style="flex:1" onclick="auth(true)">Hasap aç</button></div></div>`;return}
let h='';if(S.adm&&u.is_admin&&S.dmu){const x=S.users.find(y=>y.id===S.dmu)||{ady:'?',bal:0,id:0};const D=S.dm.filter(m=>m.uid===x.id);
h=`<div class="row sp"><h2>${esc(x.ady||x.mail)}</h2><button class="g" onclick="S.dmu=null;render()">Yza</button></div><div class="card row sp"><span>Bal: <b>${x.bal}</b></span><span class="row"><input id="ab${x.id}" type="number" placeholder="Bal" style="width:80px"><button onclick="addBal('${x.id}',1)">+</button><button class="r" onclick="addBal('${x.id}',-1)">−</button></span></div><div>${dmList(D,1)||'<p class="mu">Habar ýok</p>'}</div><div class="row" style="margin-top:10px"><input id="dt" placeholder="Jogap ýaz..." onkeydown="if(event.key==='Enter')sendDm('${x.id}',1)"><button onclick="sendDm('${x.id}',1)">➤</button></div>`}
else if(S.adm&&u.is_admin){h=`<div class="row sp"><h2>Admin sahypasy</h2><button class="g" onclick="S.adm=false;render()">Yza</button></div>
<div class="card"><b>Ulanyjylar</b><div style="overflow-x:auto"><table><tr><th>Ady</th><th>Gmail</th><th>Nomer</th><th>ID kod</th><th>Bal</th><th></th></tr>
${S.users.filter(x=>!x.is_admin).map(x=>`<tr><td>${esc(x.ady)}</td><td>${esc(x.mail)}</td><td>${esc(x.nomer)}</td><td>${esc(x.kod)}</td><td>${x.bal}</td><td><input id="ab${x.id}" type="number" style="width:64px"><button onclick="addBal('${x.id}',1)">+</button> <button class="r" onclick="addBal('${x.id}',-1)">−</button> <button class="g" onclick="S.dmu='${x.id}';render()">💬${S.dm.filter(m=>m.uid===x.id).length}</button></td></tr>`).join('')||'<tr><td colspan=6 class="mu">Ulanyjy ýok</td></tr>'}</table></div></div>
<div class="card"><b>Habar goş</b><input id="nt" placeholder="Sözbaşy"><textarea id="nd" rows="3" placeholder="Habar barada maglumat"></textarea><div class="mu">Surat (iň köp 3)</div><input id="ni" type="file" accept="image/*" multiple><button onclick="addNews()">Goş</button>
${S.news.map(n=>`<div class="row sp mu" style="margin-top:6px"><span>${esc(n.t)}</span><button class="r" onclick="del('news',${n.id})">×</button></div>`).join('')}</div>
<div class="card"><b>Oýun goş</b><input id="ma" placeholder="1-nji topar"><input id="mb" placeholder="2-nji topar"><input id="md" placeholder="Sene we wagt: 2026-11-10 20:00"><button onclick="addMatch()">Goş</button>
${S.matches.map(m=>`<div class="row sp mu" style="margin-top:6px"><span>${esc(m.a)} – ${esc(m.b)}</span><button class="r" onclick="del('matches',${m.id})">×</button></div>`).join('')}</div>
<div class="card"><b>Netije ýaz</b>${S.matches.filter(m=>m.r===null).map(m=>`<div class="row" style="margin-top:6px"><span style="flex:1">${esc(m.a)} – ${esc(m.b)}</span><input id="r${m.id}" placeholder="2:1" style="width:70px"><button onclick="setRes(${m.id})">OK</button></div>`).join('')||'<span class="mu">Geljek oýun ýok</span>'}</div>`}
else if(S.tab==='home'){h=`<h2>Habarlar</h2>${S.news.map(n=>`<div class="card">${(n.imgs||[]).map(s=>`<img src="${s}" style="width:100%;border-radius:12px;margin-bottom:8px;display:block">`).join('')}<b>${esc(n.t)}</b><p class="mu" style="margin:6px 0 0;white-space:pre-wrap">${esc(n.d)}</p></div>`).join('')||'<p class="mu">Heniz habar ýok</p>'}`}
else if(S.tab==='games'){const q=S.q.toLowerCase();const L=S.matches.filter(m=>(S.mt==='next'?m.r===null:m.r!==null)&&(m.a+' '+m.b).toLowerCase().includes(q));
h=`<h2>Oýunlar</h2><input id="sq" placeholder="🔍 Topar gözle..." value="${esc(S.q)}" oninput="S.q=this.value;render()"><div class="seg"><button class="${S.mt==='next'?'':'g'}" onclick="S.mt='next';render()">Geljek</button><button class="${S.mt==='past'?'':'g'}" onclick="S.mt='past';render()">Geçen</button></div>${L.map(matchCard).join('')||'<p class="mu">Tapylmady</p>'}`}
else if(S.tab==='chat'){h=`<h2>Umumy chat</h2><div>${S.chat.map(c=>`<div class="msg ${c.u===u.id?'me':''} ${c.adm?'adm':''}"><div class="mu">${esc(c.name)}${c.adm?' · admin':''}</div>${esc(c.t)}</div>`).join('')||'<p class="mu">Heniz habar ýok</p>'}</div><div class="row" style="margin-top:10px"><input id="ct" placeholder="Habar ýaz..." onkeydown="if(event.key==='Enter')sendMsg()"><button onclick="sendMsg()">➤</button></div>`}
else if(S.tab==='dm'){const D=S.dm.filter(m=>m.uid===u.id);h=`<div class="row sp"><h2>Admin bilen chat</h2><button class="g" onclick="go('bal')">Yza</button></div><p class="mu">Bal doldurmak üçin diňe admine ýaz. Bu chaty diňe sen we admin görýär.</p><div>${dmList(D,0)||'<p class="mu">Heniz habar ýok</p>'}</div><div class="row" style="margin-top:10px"><input id="dt" placeholder="Admine ýaz..." onkeydown="if(event.key==='Enter')sendDm('${u.id}',0)"><button onclick="sendDm('${u.id}',0)">➤</button></div>`}
else if(S.tab==='bal'){const B=S.bets.filter(b=>b.u===u.id);h=`<h2>Balans</h2><div class="card" style="text-align:center"><div class="mu">Bal</div><div class="sc" style="font-size:36px">${u.bal}</div><button style="margin-top:10px" onclick="go('dm')">Bal almak üçin admine ýaz</button></div><b>Çaklamalarym</b>${B.map(b=>{const m=S.matches.find(x=>x.id===b.m)||{a:'?',b:'?'};return `<div class="card row sp"><span>${esc(m.a)} – ${esc(m.b)}<br><span class="mu">Saýlaw: ${b.p} · ${b.s} bal</span></span><span class="tag">${b.done?'Hasaplandy':'Garaşylýar'}</span></div>`}).join('')||'<p class="mu">Heniz ýok</p>'}`}
else{h=`<h2>Profil</h2><div class="card">${u.ava?`<img class="ava" src="${u.ava}">`:`<div class="ava"></div>`}<label class="mu" style="display:block;text-align:center"><input type="file" accept="image/*" onchange="setAva(event)" style="display:none"><u>Surat üýtget</u></label><input id="pn" value="${esc(u.ady)}"><div class="mu">${esc(u.mail)}</div><button style="width:100%;margin-top:8px" onclick="saveProfile()">Ýatda sakla</button></div>${u.is_admin?`<button style="width:100%;margin-bottom:8px" onclick="S.adm=true;render()">Admin sahypasy</button>`:''}<button class="g" style="width:100%" onclick="out()">Çyk</button>`}
const T=[['home','⌂','Baş sahypa'],['games','🏆','Oýunlar'],['chat','💬','Chat'],['bal','👛','Balans'],['pro','👤','Profil']];
A.innerHTML=(u.is_admin?'':`<div class="card row sp"><span class="mu">Balans</span><b style="font-size:20px;color:var(--ac)">${u.bal} bal</b></div>`)+h+`<nav>${T.map(t=>`<div class="${S.tab===t[0]&&!S.adm?'on':''}" onclick="go('${t[0]}')"><b>${t[1]}</b>${t[2]}</div>`).join('')}</nav>`}
(async()=>{const {data}=await sb.auth.getSession();if(data.session)start(data.session.user);else render()})();
</script></body></html>
