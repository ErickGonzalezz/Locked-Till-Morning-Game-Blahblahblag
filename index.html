<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width,initial-scale=1.0,user-scalable=no" />
<title>Locked Till Morning — Christmas Update (No Flashlight)</title>
<style>
  :root{
    --bg:#0b1020;
    --panel:rgba(10,10,14,.94);
    --ui:rgba(10,10,14,.45);
    --btn:rgba(31,38,51,0.88);
    --btn2:#1f2633;
    --txt:#fff;
  }
  body{margin:0;overflow:hidden;background:var(--bg);font-family:Arial,sans-serif;color:var(--txt)}
  canvas{display:block;touch-action:none}

  .panel{
    position:fixed;inset:0;background:var(--panel);
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    gap:10px;padding:20px;text-align:center
  }
  .row{display:flex;gap:10px;flex-wrap:wrap;justify-content:center}
  button,select,input{
    background:var(--btn2);color:#fff;border:none;border-radius:12px;
    padding:10px 12px;font-size:14px;min-width:170px
  }
  input{min-width:230px;text-align:center}
  button{background:var(--btn)}

  /* ✅ iOS multi-touch friendliness */
  button{touch-action:manipulation;-webkit-tap-highlight-color:transparent}
  .pad button,.rightStack button{touch-action:none}

  #ui{
    position:fixed;top:8px;left:8px;font-size:12px;line-height:1.35;
    background:var(--ui);padding:8px 10px;border-radius:12px;display:none
  }
  #controls{position:fixed;inset:0;display:none;pointer-events:none}
  #toast{
    position:fixed;left:50%;transform:translateX(-50%);bottom:120px;
    background:rgba(10,10,14,.75);padding:10px 12px;border-radius:12px;font-size:13px;display:none
  }

  .pad{
    position:fixed;left:14px;bottom:14px;width:170px;height:170px;
    display:grid;grid-template-columns:repeat(3,1fr);grid-template-rows:repeat(3,1fr);
    gap:8px;pointer-events:auto
  }
  .pad button{
    min-width:auto;width:100%;height:100%;border-radius:14px;font-weight:700;font-size:14px;
    background:rgba(31,38,51,0.85);backdrop-filter:blur(2px)
  }
  .pad .empty{visibility:hidden}

  .rightStack{
    position:fixed;right:14px;bottom:14px;display:flex;flex-direction:column;gap:10px;
    pointer-events:auto
  }
  .rightStack button{
    min-width:170px;background:rgba(31,38,51,0.85);backdrop-filter:blur(2px)
  }

  .small{font-size:12px;opacity:.9;max-width:560px}
  .divider{height:1px;width:100%;max-width:560px;background:rgba(255,255,255,.12);margin:10px 0}
  .list{width:100%;max-width:560px;text-align:left;background:rgba(255,255,255,.06);border-radius:12px;padding:10px}
  .serverRow{display:flex;justify-content:space-between;align-items:center;gap:10px;padding:8px;border-radius:10px}
  .serverRow:nth-child(odd){background:rgba(255,255,255,.05)}
  .badge{font-size:12px;opacity:.88}

  #invOverlay{
    position:fixed;inset:0;background:rgba(10,10,14,.92);
    display:none;align-items:center;justify-content:center;padding:18px
  }
  #invCard{
    width:min(720px,100%);background:rgba(255,255,255,.06);
    border-radius:16px;padding:14px;box-shadow:0 20px 60px rgba(0,0,0,.35)
  }
  #invTop{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-bottom:10px}
  #invGrid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px}
  .invItem{
    background:rgba(31,38,51,0.85);border-radius:14px;padding:12px;
    display:flex;justify-content:space-between;align-items:center;gap:10px
  }
  .invItem .left{display:flex;flex-direction:column;gap:4px;text-align:left}
  .invItem .name{font-weight:800}
  .invItem .desc{font-size:12px;opacity:.86}
  .invItem .count{font-size:12px;opacity:.9}
  .invItem button{min-width:110px}

  .xmasTitle{
    font-weight:900;font-size:30px;letter-spacing:.5px;
    text-shadow:0 2px 0 rgba(0,0,0,.25), 0 0 18px rgba(120,200,255,.15)
  }
  .xmasSpark{font-size:14px;opacity:.95}
  .xmasLine{
    max-width:560px;width:100%;height:1px;
    background:linear-gradient(90deg, rgba(255,255,255,0), rgba(255,255,255,.20), rgba(255,255,255,0));
    margin:8px 0 6px 0
  }
</style>
</head>
<body>
<canvas id="c"></canvas>

<div id="ui">
  <div>
    <b>❤️</b> <span id="health">100</span> &nbsp;
    <b>🍗</b> <span id="hunger">100</span> &nbsp;
    <b>💧</b> <span id="thirst">100</span>
  </div>
  <div>
    <b>⚡</b> <span id="stamina">100</span>
  </div>
  <div>
    <b>⏰</b> <span id="time">12:00 AM</span> &nbsp;
    <span id="diffLabel">Easy</span>
  </div>
  <div id="extraHud" class="badge"></div>
  <div id="hideHint" class="badge"></div>
</div>

<div id="controls">
  <div class="pad">
    <button class="empty"></button>
    <button id="btnUp">▲</button>
    <button class="empty"></button>

    <button id="btnLeft">◀</button>
    <button class="empty"></button>
    <button id="btnRight">▶</button>

    <button class="empty"></button>
    <button id="btnDownReal">▼</button>
    <button class="empty"></button>
  </div>

  <div class="rightStack">
    <button id="sprintBtn">🏃 Sprint: OFF</button>
    <button id="invBtn">🎒 Inventory</button>
    <button id="hideBtn">🫥 Hide</button>
    <button id="pauseBtn">⏸ Menu</button>
  </div>
</div>

<div id="toast"></div>

<div id="invOverlay">
  <div id="invCard">
    <div id="invTop">
      <div style="text-align:left">
        <div style="font-weight:900;font-size:18px">Inventory</div>
        <div class="badge" id="invHint">Tap USE to eat/drink items.</div>
      </div>
      <button id="invCloseBtn" style="min-width:140px">Close</button>
    </div>
    <div id="invGrid"></div>
  </div>
</div>

<div id="menu" class="panel">
  <div class="xmasTitle">🎄 Locked Till Morning 🎄</div>
  <div class="xmasSpark" id="eventNoteTop">✨ Christmas Update is active ✨</div>
  <div class="xmasLine"></div>

  <div class="small" id="eventNote">
    Pixel-art mall survival. Start at <b>12:00 AM</b>. Survive until <b>8:00 AM</b>.<br>
    Clock speed: <b>1 real second = 1 in-game minute</b> (8 real minutes to win).
  </div>

  <div class="divider"></div>

  <div>
    <div class="small" style="margin-bottom:6px;">Your Name (saved):</div>
    <input id="nameInput" maxlength="16" />
  </div>

  <div class="divider"></div>

  <div class="row">
    <button id="playBtn">Play (Solo)</button>
    <button id="multiBtn">Multiplayer</button>
  </div>

  <div class="row">
    <button id="howBtn">How To Play</button>
    <button id="statsBtn">Stats</button>
    <button id="lbBtn">Leaderboard</button>
  </div>

  <div class="divider"></div>

  <div style="max-width:560px;width:100%;">
    <div class="small" style="margin-bottom:6px;">Difficulty:</div>
    <select id="diffSelect"></select>
    <div id="unlockText" class="small" style="margin-top:6px;"></div>
  </div>

  <div class="xmasLine"></div>
  <div class="small" id="eventNoteBottom">🎁 Tip: Meet-Santa area is the center atrium (no Santa).</div>
</div>

<div id="how" class="panel" style="display:none;">
  <h2 style="margin:0;">How To Play</h2>
  <div class="small" style="text-align:left;max-width:560px;">
    • Survive until <b>8:00 AM</b>.<br>
    • Employees chase and attack you (slower).<br>
    • Pickups go into your <b>Inventory</b>. Tap <b>USE</b> to eat/drink.<br>
    • Food refills hunger. Drinks refill thirst. Drinks also give stamina <b>except soda</b>.<br>
    • Use <b>Hide</b> at hiding spots (locker-door animation).<br>
    • Clock speed: <b>1 second = 1 minute</b>.<br>
    • Santa Difficulty: collect <b>5 ornaments</b> before <b>8:00 AM</b>.
  </div>
  <button onclick="showPanel('menu')">Back</button>
</div>

<div id="stats" class="panel" style="display:none;">
  <h2 style="margin:0;">Stats</h2>
  <div class="list" id="statsBox"></div>
  <button onclick="showPanel('menu')">Back</button>
</div>

<div id="leaderboard" class="panel" style="display:none;">
  <h2 style="margin:0;">Leaderboard</h2>
  <div class="small">Saved on your device.</div>
  <div class="list" id="lbBox"></div>
  <button onclick="showPanel('menu')">Back</button>
</div>

<div id="multiplayer" class="panel" style="display:none;">
  <h2 style="margin:0;">Multiplayer</h2>
  <div class="small">Same-device lobby using multiple Safari tabs/windows.</div>
  <div class="row">
    <button id="hostBtn">Host</button>
    <button id="joinBtn">Join</button>
  </div>
  <button onclick="leaveMultiplayer()">Back</button>
</div>

<div id="hostSetup" class="panel" style="display:none;">
  <h2 style="margin:0;">Host Server</h2>
  <div class="small">Choose max players (2–6).</div>
  <select id="maxPlayersSelect">
    <option>2</option><option>3</option><option>4</option><option>5</option><option>6</option>
  </select>
  <button id="createServerBtn">Create</button>
  <button onclick="showPanel('multiplayer')">Back</button>
</div>

<div id="lobby" class="panel" style="display:none;">
  <h2 style="margin:0;">Lobby</h2>
  <div class="small" id="lobbyInfo"></div>
  <div class="list" id="playerList"></div>
  <div class="row">
    <button id="startHostBtn">Start (Host)</button>
    <button id="leaveLobbyBtn">Leave</button>
  </div>
  <div class="small">Host can start only with <b>2+ players</b>.</div>
</div>

<div id="joinList" class="panel" style="display:none;">
  <h2 style="margin:0;">Join a Server</h2>
  <div class="list" id="serverList"></div>
  <button onclick="showPanel('multiplayer')">Back</button>
</div>

<script>
/* =========================
   SEASON / EVENT TIMER
========================= */
const EVENT_END = new Date(2026, 0, 11, 0, 0, 0).getTime();
const CHRISTMAS_ACTIVE = Date.now() < EVENT_END;

/* =========================
   STORAGE (NO DATA LOSS)
========================= */
const LS = { profile:"ltm_profile", stats:"ltm_stats", lb:"ltm_leaderboard", servers:"ltm_servers" };
const OLD_KEYS = {
  profile: ["ltm_px_profile_v3","ltm_px_profile_v4","ltm_px_profile_v5"],
  stats:   ["ltm_px_stats_v3","ltm_px_stats_v4","ltm_px_stats_v5"],
  lb:      ["ltm_px_lb_v3","ltm_px_lb_v4","ltm_px_lb_v5"],
  servers: ["ltm_px_servers_v3","ltm_px_servers_v4","ltm_px_servers_v5"]
};
function migrateKey(newKey, oldKeys){
  if(localStorage.getItem(newKey)!=null) return;
  for(const k of oldKeys){
    const v=localStorage.getItem(k);
    if(v!=null){ localStorage.setItem(newKey,v); return; }
  }
}
migrateKey(LS.profile, OLD_KEYS.profile);
migrateKey(LS.stats,   OLD_KEYS.stats);
migrateKey(LS.lb,      OLD_KEYS.lb);
migrateKey(LS.servers, OLD_KEYS.servers);

const rand4=()=>Math.floor(Math.random()*10000).toString().padStart(4,"0");
function safeParse(json,fallback){ try{return JSON.parse(json);}catch{return fallback;} }
function loadProfile(){
  let p=safeParse(localStorage.getItem(LS.profile),null);
  if(!p||typeof p!=="object") p={name:"Player"+rand4()};
  if(!p.name) p.name="Player"+rand4();
  localStorage.setItem(LS.profile,JSON.stringify(p));
  return p;
}
function saveProfile(p){ localStorage.setItem(LS.profile,JSON.stringify(p)); }
function loadStats(){
  let s=safeParse(localStorage.getItem(LS.stats),null);
  if(!s||typeof s!=="object") s={totalPlaySeconds:0,survives:0,deaths:0};
  s.totalPlaySeconds=Number(s.totalPlaySeconds||0);
  s.survives=Number(s.survives||0);
  s.deaths=Number(s.deaths||0);
  localStorage.setItem(LS.stats,JSON.stringify(s));
  return s;
}
function saveStats(s){ localStorage.setItem(LS.stats,JSON.stringify(s)); }
function loadLB(){
  let lb=safeParse(localStorage.getItem(LS.lb),[]);
  if(!Array.isArray(lb)) lb=[];
  return lb;
}
function saveLB(lb){ localStorage.setItem(LS.lb,JSON.stringify(lb)); }

/* =========================
   CHRISTMAS FEATURES
========================= */
const EVENT = { christmas: CHRISTMAS_ACTIVE, snowParticles: CHRISTMAS_ACTIVE };
let cheer = { active:false, t:0, dur:18 };
function startCheer(){ cheer.active=true; cheer.t=cheer.dur; }

/* =========================
   PANELS / TOAST
========================= */
const PANELS=["menu","how","stats","leaderboard","multiplayer","hostSetup","lobby","joinList"];
function showPanel(id){ PANELS.forEach(p=>document.getElementById(p).style.display="none"); document.getElementById(id).style.display="flex"; }
const toastEl=document.getElementById("toast");
function toast(msg){ toastEl.textContent=msg; toastEl.style.display="block"; clearTimeout(toast._t); toast._t=setTimeout(()=>toastEl.style.display="none",1400); }
const esc=s=>String(s).replace(/[&<>"']/g,m=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#039;"}[m]));
function jingle(){
  try{
    const a=new (window.AudioContext||window.webkitAudioContext)();
    const o=a.createOscillator();
    const g=a.createGain();
    o.type="triangle"; o.frequency.value=880;
    g.gain.value=0.06;
    o.connect(g); g.connect(a.destination);
    o.start();
    setTimeout(()=>{ o.frequency.value=1174; },90);
    setTimeout(()=>{ g.gain.value=0.0001; },220);
    setTimeout(()=>{ o.stop(); a.close(); },260);
  }catch{}
}

/* =========================
   DIFFICULTY
========================= */
function getDifficultyOptions(survives){
  const base = [
    {key:"easy",label:"Easy",unlocked:true},
    {key:"medium",label:"Medium",unlocked:survives>=5},
    {key:"hard",label:"Hard",unlocked:survives>=10},
  ];
  if(EVENT.christmas){
    base.push({key:"santa",label:"Santa 🎄 (Limited)",unlocked:true});
  }
  return base;
}
function diffParams(k){
  if(k==="easy")   return { empCount:3, empSpeed:78,  drainH:0.18, drainT:0.26, dmg:25, vis:230, atkCool:46 };
  if(k==="medium") return { empCount:5, empSpeed:92,  drainH:0.23, drainT:0.32, dmg:30, vis:260, atkCool:44 };
  if(k==="hard")   return { empCount:7, empSpeed:108, drainH:0.30, drainT:0.40, dmg:35, vis:290, atkCool:42 };
  return              { empCount:6, empSpeed:98,  drainH:0.26, drainT:0.34, dmg:30, vis:270, atkCool:44 };
}
const diffLabel=k=>{
  if(k==="easy") return "Easy";
  if(k==="medium") return "Medium";
  if(k==="hard") return "Hard";
  return "Santa 🎄";
};

/* =========================
   CANVAS + PIXEL BUFFER
========================= */
const canvas=document.getElementById("c");
const ctx=canvas.getContext("2d",{alpha:false});
const buf=document.createElement("canvas");
const bctx=buf.getContext("2d",{alpha:false});
function resize(){
  canvas.width=innerWidth; canvas.height=innerHeight;
  const scaleDown=4;
  buf.width=Math.max(240,Math.floor(canvas.width/scaleDown));
  buf.height=Math.max(180,Math.floor(canvas.height/scaleDown));
  ctx.imageSmoothingEnabled=false;
  bctx.imageSmoothingEnabled=false;
}
addEventListener("resize",resize);
resize();

/* =========================
   MALL MAP
========================= */
const TILE=16;
const MAP_W=80, MAP_H=60;
let map=new Array(MAP_W*MAP_H).fill(1);
const idx=(x,y)=>y*MAP_W+x;
const inMap=(x,y)=>x>=0&&y>=0&&x<MAP_W&&y<MAP_H;

function setRect(x,y,w,h,val){ for(let j=y;j<y+h;j++)for(let i=x;i<x+w;i++) if(inMap(i,j)) map[idx(i,j)]=val; }
function carveHall(x,y,w,h,t=0){ setRect(x,y,w,h,t); }
function storeBlock(x,y,w,h,doorSide,floorType=4){
  setRect(x,y,w,h,1);
  setRect(x+1,y+1,w-2,h-2,floorType);
  if(doorSide==="bottom"){ for(let i=x+1;i<x+w-1;i++) map[idx(i,y+h-1)]=2; map[idx(x+Math.floor(w/2), y+h-1)]=0; }
  if(doorSide==="top"){ for(let i=x+1;i<x+w-1;i++) map[idx(i,y)]=2; map[idx(x+Math.floor(w/2), y)]=0; }
  if(doorSide==="left"){ for(let j=y+1;j<y+h-1;j++) map[idx(x,j)]=2; map[idx(x, y+Math.floor(h/2))]=0; }
  if(doorSide==="right"){ for(let j=y+1;j<y+h-1;j++) map[idx(x+w-1,j)]=2; map[idx(x+w-1, y+Math.floor(h/2))]=0; }
}
let meetSantaArea=null;

function generateMall(){
  map.fill(1);
  setRect(2,2, MAP_W-4, MAP_H-4, 0);

  carveHall(6,6, MAP_W-12, 6, 0);
  carveHall(6,MAP_H-12, MAP_W-12, 6, 0);
  carveHall(6,12, 6, MAP_H-24, 0);
  carveHall(MAP_W-12,12, 6, MAP_H-24, 0);
  carveHall(22,18, MAP_W-44, MAP_H-36, 3);

  for(let sx=14; sx<MAP_W-20; sx+=12) storeBlock(sx,3,10,8,"bottom",4);
  for(let sx=14; sx<MAP_W-20; sx+=12) storeBlock(sx,MAP_H-11,10,8,"top",4);
  for(let sy=16; sy<MAP_H-20; sy+=11) storeBlock(3,sy,8,9,"right",4);
  for(let sy=16; sy<MAP_H-20; sy+=11) storeBlock(MAP_W-11,sy,8,9,"left",4);

  const cx = Math.floor(MAP_W/2);
  const cy = Math.floor(MAP_H/2);
  const w = 16, h = 12;
  const x0 = cx - Math.floor(w/2);
  const y0 = cy - Math.floor(h/2);
  setRect(x0, y0, w, h, EVENT.christmas ? 5 : 3);
  setRect(x0+2, y0+2, w-4, h-4, 3);
  for(let x=x0; x<x0+w; x++){ map[idx(x, y0)] = 1; map[idx(x, y0+h-1)] = 1; }
  for(let y=y0; y<y0+h; y++){ map[idx(x0, y)] = 1; map[idx(x0+w-1, y)] = 1; }
  map[idx(cx, y0)] = 0;
  map[idx(cx, y0+h-1)] = 0;
  meetSantaArea = { cx:cx*TILE+TILE/2, cy:cy*TILE+TILE/2, w:w*TILE, h:h*TILE };
}

function blocksMove(t){ return t===1 || t===2; }
function circleHitsWalls(x,y,r){
  const minTx=Math.floor((x-r)/TILE), maxTx=Math.floor((x+r)/TILE);
  const minTy=Math.floor((y-r)/TILE), maxTy=Math.floor((y+r)/TILE);
  for(let ty=minTy; ty<=maxTy; ty++){
    for(let tx=minTx; tx<=maxTx; tx++){
      if(!inMap(tx,ty)) return true;
      const t = map[idx(tx,ty)];
      if(!blocksMove(t)) continue;
      const rx=tx*TILE, ry=ty*TILE;
      const cx=Math.max(rx, Math.min(x, rx+TILE));
      const cy=Math.max(ry, Math.min(y, ry+TILE));
      if((x-cx)*(x-cx)+(y-cy)*(y-cy) < r*r) return true;
    }
  }
  return false;
}
function moveWithCollision(ent,nx,ny,r){
  const ox=ent.x, oy=ent.y;
  ent.x=nx; if(circleHitsWalls(ent.x,ent.y,r)) ent.x=ox;
  ent.y=ny; if(circleHitsWalls(ent.x,ent.y,r)) ent.y=oy;
}
function randomFloorSpot(){
  for(let tries=0; tries<5000; tries++){
    const tx=3+Math.floor(Math.random()*(MAP_W-6));
    const ty=3+Math.floor(Math.random()*(MAP_H-6));
    const t=map[idx(tx,ty)];
    if(t===0 || t===3 || t===4 || t===5){
      const x=tx*TILE+TILE/2, y=ty*TILE+TILE/2;
      if(!circleHitsWalls(x,y,6)) return {x,y};
    }
  }
  return {x:8*TILE,y:8*TILE};
}

/* =========================
   GAME STATE
========================= */
let profile=loadProfile();
let stats=loadStats();
const nameInput=document.getElementById("nameInput");
nameInput.value=profile.name;
nameInput.addEventListener("change",()=>{
  let v=nameInput.value.trim();
  if(!v) v="Player"+rand4();
  profile.name=v.slice(0,16);
  nameInput.value=profile.name;
  saveProfile(profile);
});

let game={
  playing:false,
  hidden:false,
  inHideSpot:false,
  sprint:false,
  invOpen:false,

  timeSeconds:0,
  gameSecondsPerTick:60,
  winAtSeconds:8*3600,

  tickPlaySec:0,
  difficultyKey:"easy",
  params:diffParams("easy"),

  ornamentsFound:0,
  ornamentsNeeded:5,

  mode:"solo",
  serverId:null,
  isHost:false
};

let hideAnim={active:false,t:0,dir:0,durClose:0.40,durOpen:0.35};

let player, employees, foods, drinks, hideSpots;
let holidayItems, ornaments;
let inventory;
let snow=[];
let cam={x:0,y:0};
const worldToScreen=(wx,wy)=>({x:wx-cam.x,y:wy-cam.y});

function resetInventory(){
  inventory = {
    burger:0, chips:0,
    water:0, juice:0, soda:0,
    cookie:0, cocoa:0, candy:0, milk:0
  };
  renderInventory();
}

function resetWorld(){
  generateMall();
  const sp=randomFloorSpot();
  player={ x:sp.x,y:sp.y,r:6,face:1, health:100,hunger:100,thirst:100,stamina:100, speed:76 };

  hideSpots=[
    {name:"Lockers",x:(16*TILE)+8,y:(6*TILE)+8,r:10},
    {name:"Storage",x:((MAP_W-20)*TILE)+8,y:(16*TILE)+8,r:10},
    {name:"Backroom",x:(14*TILE)+8,y:((MAP_H-12)*TILE)+8,r:11},
  ];

  employees=[];
  for(let i=0;i<game.params.empCount;i++){
    const p=randomFloorSpot();
    employees.push({x:p.x,y:p.y,r:6,face:1,cool:0,wander:Math.random()*Math.PI*2});
  }

  foods=[]; drinks=[];
  for(let i=0;i<9;i++){ const p=randomFloorSpot(); foods.push({x:p.x,y:p.y,taken:false,kind:Math.random()<0.5?"burger":"chips"}); }
  for(let i=0;i<9;i++){
    const p=randomFloorSpot(); const soda=Math.random()<0.4;
    drinks.push({x:p.x,y:p.y,taken:false,kind:soda?"soda":(Math.random()<0.5?"water":"juice")});
  }

  holidayItems=[];
  if(EVENT.christmas){
    for(let i=0;i<7;i++){ const p=randomFloorSpot(); holidayItems.push({x:p.x,y:p.y,taken:false,kind:"cookie"}); }
    for(let i=0;i<6;i++){ const p=randomFloorSpot(); holidayItems.push({x:p.x,y:p.y,taken:false,kind:"cocoa"}); }
    for(let i=0;i<6;i++){ const p=randomFloorSpot(); holidayItems.push({x:p.x,y:p.y,taken:false,kind:"candy"}); }
    if(meetSantaArea){
      const baseX=meetSantaArea.cx, baseY=meetSantaArea.cy;
      const drops=[
        {dx:-40,dy:-10,kind:"cookie"},
        {dx: 40,dy:-10,kind:"cookie"},
        {dx:-10,dy: 10,kind:"milk"},
        {dx: 10,dy: 10,kind:"cocoa"},
        {dx:  0,dy:-28,kind:"candy"},
      ];
      for(const d of drops){
        holidayItems.push({x:baseX+d.dx,y:baseY+d.dy,taken:false,kind:d.kind});
      }
    }
  }

  ornaments=[];
  game.ornamentsFound=0;
  if(game.difficultyKey==="santa" && EVENT.christmas){
    for(let i=0;i<game.ornamentsNeeded;i++){
      const p=randomFloorSpot();
      ornaments.push({x:p.x,y:p.y,taken:false});
    }
  }

  snow=[];
  if(EVENT.christmas && EVENT.snowParticles){
    for(let i=0;i<90;i++){
      snow.push({x:Math.random()*buf.width,y:Math.random()*buf.height,spd:12+Math.random()*24,sz:1+Math.random()*2});
    }
  }

  game.hidden=false;
  game.inHideSpot=false;
  game.sprint=false;
  game.invOpen=false;
  game.timeSeconds=0;
  game.tickPlaySec=0;

  hideAnim.active=false; hideAnim.t=0; hideAnim.dir=0;
  cheer.active=false; cheer.t=0;

  sprintBtn.textContent="🏃 Sprint: OFF";
  resetInventory();
  closeInventory();
  updateUI();
}

function startGame(){
  document.getElementById("menu").style.display="none";
  document.getElementById("ui").style.display="block";
  document.getElementById("controls").style.display="block";
  game.playing=true;
  resetWorld();
  startIntervals();
  lastFrame=performance.now();
  requestAnimationFrame(loop);
}

/* =========================
   TIMERS
========================= */
let statInterval=null;
function startIntervals(){
  stopIntervals();
  statInterval=setInterval(()=>{
    if(!game.playing) return;

    game.tickPlaySec++;
    stats.totalPlaySeconds++;

    game.timeSeconds += game.gameSecondsPerTick;

    if(game.timeSeconds >= game.winAtSeconds){
      if(game.difficultyKey==="santa"){
        if(game.ornamentsFound>=game.ornamentsNeeded) winGame();
        else loseSantaFail();
      }else{
        winGame();
      }
      return;
    }

    player.hunger -= game.params.drainH;
    player.thirst -= game.params.drainT;

    // Regen a bit slower while sprint toggle is ON, faster while walking/resting
    let regen = game.sprint ? 0.55 : 0.85;
    if(cheer.active) regen += 0.35;
    player.stamina = Math.min(100, player.stamina + regen);

    if(cheer.active){
      cheer.t -= 1;
      if(cheer.t <= 0){ cheer.active=false; cheer.t=0; }
    }

    if(player.hunger<=0 || player.thirst<=0) player.health -= 1;

    if(player.health<=0){ player.health=0; loseGame("You passed out…"); return; }

    saveStats(stats);
    updateUI();
  },1000);
}
function stopIntervals(){ if(statInterval) clearInterval(statInterval); statInterval=null; }

/* =========================
   UI
========================= */
const healthEl=document.getElementById("health");
const hungerEl=document.getElementById("hunger");
const thirstEl=document.getElementById("thirst");
const staminaEl=document.getElementById("stamina");
const timeEl=document.getElementById("time");
const diffEl=document.getElementById("diffLabel");
const hideHintEl=document.getElementById("hideHint");
const extraHudEl=document.getElementById("extraHud");

function formatGameTime12h(totalSeconds){
  const h24=Math.floor(totalSeconds/3600);
  const m=Math.floor((totalSeconds%3600)/60);
  let h12=h24%12; if(h12===0) h12=12;
  const ampm=(h24<12)?"AM":"PM";
  return `${h12}:${String(m).padStart(2,"0")} ${ampm}`;
}
function updateUI(){
  healthEl.textContent=Math.max(0,Math.floor(player?.health??100));
  hungerEl.textContent=Math.max(0,Math.floor(player?.hunger??100));
  thirstEl.textContent=Math.max(0,Math.floor(player?.thirst??100));
  staminaEl.textContent=Math.min(100,Math.max(0,Math.floor(player?.stamina??100)));

  timeEl.textContent=formatGameTime12h(game.timeSeconds);
  diffEl.textContent="• "+diffLabel(game.difficultyKey);

  if(game.difficultyKey==="santa"){
    extraHudEl.textContent = `🎄 Ornaments: ${game.ornamentsFound}/${game.ornamentsNeeded}`;
  }else{
    extraHudEl.textContent = "";
  }

  let hint="";
  if(game.invOpen) hint="Inventory open.";
  else if(game.inHideSpot && !game.hidden && !hideAnim.active) hint="You can hide here. Press HIDE.";
  else if(hideAnim.active && hideAnim.dir===1) hint="Hiding...";
  else if(hideAnim.active && hideAnim.dir===-1) hint="Leaving...";
  else if(game.hidden) hint="Hidden.";
  else if(cheer.active) hint=`Cheer buff active (${cheer.t}s)`;
  else if(game.sprint) hint="Sprint ON (stamina drains while moving)";
  hideHintEl.textContent=hint;
}

/* =========================
   INVENTORY
========================= */
const invOverlay=document.getElementById("invOverlay");
const invGrid=document.getElementById("invGrid");
const invBtn=document.getElementById("invBtn");
const invCloseBtn=document.getElementById("invCloseBtn");

function openInventory(){
  if(!game.playing) return;
  game.invOpen=true;
  invOverlay.style.display="flex";
  renderInventory();
  updateUI();
}
function closeInventory(){
  game.invOpen=false;
  invOverlay.style.display="none";
  updateUI();
}
invBtn.onclick=()=>{ if(game.invOpen) closeInventory(); else openInventory(); };
invCloseBtn.onclick=()=>closeInventory();

const INV_ITEMS = [
  { key:"burger", name:"Burger", desc:"+Hunger to 100",
    canUse:()=>inventory.burger>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.burger--; player.hunger=100; toast("Ate Burger (+Hunger)"); } },
  { key:"chips", name:"Chips", desc:"+Hunger to 100",
    canUse:()=>inventory.chips>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.chips--; player.hunger=100; toast("Ate Chips (+Hunger)"); } },
  { key:"water", name:"Water", desc:"+Thirst 100 +Stamina 100",
    canUse:()=>inventory.water>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.water--; player.thirst=100; player.stamina=100; toast("Drank Water (+Thirst +Stamina)"); } },
  { key:"juice", name:"Juice", desc:"+Thirst 100 +Stamina 100",
    canUse:()=>inventory.juice>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.juice--; player.thirst=100; player.stamina=100; toast("Drank Juice (+Thirst +Stamina)"); } },
  { key:"soda", name:"Soda", desc:"+Thirst 100 (NO stamina)",
    canUse:()=>inventory.soda>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.soda--; player.thirst=100; toast("Drank Soda (+Thirst)"); } },
  { key:"milk", name:"Milk", desc:"+Thirst 100 +Stamina 100 +Cheer buff",
    canUse:()=>inventory.milk>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.milk--; player.thirst=100; player.stamina=100; startCheer(); toast("Drank Milk (+Cheer)"); } },
  { key:"cookie", name:"Cookie", desc:"+Hunger 100 +Cheer buff",
    canUse:()=>inventory.cookie>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.cookie--; player.hunger=100; startCheer(); toast("Ate Cookie (+Cheer)"); } },
  { key:"cocoa", name:"Hot Cocoa", desc:"+Thirst 100 +Stamina 100 +Cheer buff",
    canUse:()=>inventory.cocoa>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.cocoa--; player.thirst=100; player.stamina=100; startCheer(); toast("Drank Cocoa (+Cheer)"); } },
  { key:"candy", name:"Candy Cane", desc:"+Stamina 100 +Cheer buff",
    canUse:()=>inventory.candy>0 && !game.hidden && !hideAnim.active,
    use:()=>{ inventory.candy--; player.stamina=100; startCheer(); toast("Candy Cane (+Cheer)"); } },
];

function renderInventory(){
  invGrid.innerHTML = INV_ITEMS.map(item=>{
    const count = inventory[item.key]||0;
    const disabled = !(item.canUse());
    return `
      <div class="invItem">
        <div class="left">
          <div class="name">${item.name}</div>
          <div class="desc">${item.desc}</div>
          <div class="count">Count: <b>${count}</b></div>
        </div>
        <button ${disabled?'disabled':''} onclick="useInv('${item.key}')">USE</button>
      </div>
    `;
  }).join("");
}
window.useInv=function(key){
  const item=INV_ITEMS.find(x=>x.key===key);
  if(!item) return;
  if(!item.canUse()) return toast("Can't use that right now.");
  item.use();
  renderInventory();
  updateUI();
};

/* =========================
   CONTROLS
========================= */
const sprintBtn=document.getElementById("sprintBtn");
const hideBtn=document.getElementById("hideBtn");
const pauseBtn=document.getElementById("pauseBtn");

/* ---- SPRINT FIX (works while moving on iOS) ---- */
function setSprint(on){
  game.sprint = !!on;
  sprintBtn.textContent = game.sprint ? "🏃 Sprint: ON" : "🏃 Sprint: OFF";
  updateUI();
}
function toggleSprintNow(e){
  if(e){ e.preventDefault(); e.stopPropagation(); }
  if(!game.playing) return;
  if(game.invOpen) return toast("Close inventory first.");
  if(game.hidden || hideAnim.active) return toast("Can't sprint while hiding.");

  if(game.sprint){
    setSprint(false);
    toast("Sprint OFF");
    return;
  }
  if(player.stamina <= 8) return toast("Too tired to sprint.");
  setSprint(true);
  toast("Sprint ON");
}
sprintBtn.addEventListener("pointerdown", toggleSprintNow, { passive:false });
sprintBtn.addEventListener("touchstart", toggleSprintNow, { passive:false });
sprintBtn.addEventListener("click", toggleSprintNow);
/* ---- END SPRINT FIX ---- */

hideBtn.onclick=()=>{
  if(!game.playing) return;
  if(game.invOpen) return toast("Close inventory first.");
  if(!game.inHideSpot) return toast("Not in a hiding spot.");
  if(hideAnim.active) return;
  if(!game.hidden){
    hideAnim.active=true; hideAnim.dir=1; hideAnim.t=0; toast("Hiding...");
    setSprint(false);
  }else{
    hideAnim.active=true; hideAnim.dir=-1; hideAnim.t=1; toast("Leaving...");
  }
};

pauseBtn.onclick=()=>{
  if(!game.playing) return;
  game.playing=false;
  stopIntervals();
  document.getElementById("ui").style.display="none";
  document.getElementById("controls").style.display="none";
  closeInventory();
  toast("Paused");
  showPanel("menu");
  refreshDifficultyUI();
};

const keys={up:false,down:false,left:false,right:false};
function bindHold(btn, key){
  const el=document.getElementById(btn);
  const on=()=>{ keys[key]=true; };
  const off=()=>{ keys[key]=false; };
  el.addEventListener("touchstart",(e)=>{ e.preventDefault(); on(); }, {passive:false});
  el.addEventListener("touchend",(e)=>{ e.preventDefault(); off(); }, {passive:false});
  el.addEventListener("touchcancel",(e)=>{ e.preventDefault(); off(); }, {passive:false});
  el.addEventListener("mousedown",(e)=>{ e.preventDefault(); on(); });
  addEventListener("mouseup",()=>off());
}
bindHold("btnUp","up");
bindHold("btnDownReal","down");
bindHold("btnLeft","left");
bindHold("btnRight","right");

/* =========================
   END STATES
========================= */
function formatTime(sec){ const m=Math.floor(sec/60), s=sec%60; return `${m}m ${s}s`; }
function winGame(){
  game.playing=false; stopIntervals(); closeInventory();
  stats.survives++; saveStats(stats);

  const lb=loadLB();
  lb.push({name:profile.name,difficulty:game.difficultyKey,seconds:game.tickPlaySec,date:new Date().toISOString()});
  lb.sort((a,b)=>a.seconds-b.seconds);
  saveLB(lb.slice(0,20));

  const extra = (game.difficultyKey==="santa") ? `\nOrnaments: ${game.ornamentsFound}/${game.ornamentsNeeded}` : "";
  alert(`You survived until 8:00 AM!\nReal Time Played: ${formatTime(game.tickPlaySec)}\nDifficulty: ${diffLabel(game.difficultyKey)}${extra}`);
  location.reload();
}
function loseSantaFail(){
  game.playing=false; stopIntervals(); closeInventory();
  stats.deaths++; saveStats(stats);
  alert(`Mall opened at 8:00 AM… but you only found ${game.ornamentsFound}/${game.ornamentsNeeded} ornaments.\nSanta Difficulty FAILED.`);
  location.reload();
}
function loseGame(msg){
  game.playing=false; stopIntervals(); closeInventory();
  stats.deaths++; saveStats(stats);
  alert(msg || "You got caught… Game Over.");
  location.reload();
}

/* =========================
   DRAW HELPERS
========================= */
function px(x,y,w,h,c){ bctx.fillStyle=c; bctx.fillRect(x|0,y|0,w|0,h|0); }
function drawTile(tx,ty,t){
  const x = tx*TILE - cam.x;
  const y = ty*TILE - cam.y;
  if(x<-TILE||y<-TILE||x>buf.width+TILE||y>buf.height+TILE) return;

  if(t===0){
    px(x,y,TILE,TILE,"#d7e2ee");
    px(x+1,y+1,TILE-2,TILE-2,"#c6d3e2");
    px(x+7,y,2,TILE,"#aab7c8");
    px(x,y+7,TILE,2,"#aab7c8");
  } else if(t===3){
    px(x,y,TILE,TILE,"#5a2aa6");
    px(x+1,y+1,TILE-2,TILE-2,"#7b43c9");
  } else if(t===4){
    px(x,y,TILE,TILE,"#d1c8b5");
    px(x+1,y+1,TILE-2,TILE-2,"#e8e2d2");
  } else if(t===5){
    px(x,y,TILE,TILE,"#b51f2e");
    px(x+1,y+1,TILE-2,TILE-2,"#d13a49");
    px(x+2,y+2,4,4,"#1a9c55");
    px(x+10,y+10,4,4,"#1a9c55");
    px(x+2,y+10,4,4,"#ffe869");
    px(x+10,y+2,4,4,"#ffe869");
  } else if(t===2){
    px(x,y,TILE,TILE,"#434a55");
    px(x+1,y+1,TILE-2,TILE-2,"rgba(120,184,255,0.55)");
  } else {
    px(x,y,TILE,TILE,"#59606a");
    px(x+1,y+1,TILE-2,TILE-2,"#434a55");
  }
}
function drawDecor(){
  if(EVENT.christmas){
    const y=6;
    for(let x=0; x<buf.width; x+=14){
      px(x,y,12,2,"rgba(26,156,85,0.55)");
      px(x+2,y-2,2,2,"rgba(255,112,112,0.85)");
      px(x+7,y-2,2,2,"rgba(255,232,105,0.85)");
    }
  }
}
function drawPlayer(wx,wy,facing,frame,hidden){
  const s=worldToScreen(wx,wy);
  const x=s.x|0, y=s.y|0;
  px(x-4,y+5,8,2,"rgba(0,0,0,0.25)");
  const alpha = hidden ? 0.45 : 1;
  bctx.globalAlpha=alpha;

  px(x-2,y+2,2,3,"#2f6dff"); px(x+1,y+2,2,3,"#2f6dff");
  px(x-4,y-2,8,6,"#d8e6ff"); px(x-3,y-1,6,4,"#b8d3ff");
  px(x-3,y-6,6,5,"#ffd6b8");
  px(x-3,y-6,6,2,"#3a2620");
  const fx=(facing===1)?1:-1;
  px(x-1+fx,y-4,1,1,"#111"); px(x+1+fx,y-4,1,1,"#111");

  bctx.globalAlpha=1;
}
function drawEmployee(wx,wy,facing,frame){
  const s=worldToScreen(wx,wy);
  const x=s.x|0, y=s.y|0;
  px(x-4,y+5,8,2,"rgba(0,0,0,0.25)");

  px(x-2,y+2,2,3,"#3d3d3d"); px(x+1,y+2,2,3,"#3d3d3d");
  px(x-4,y-2,8,6,"#ff7070"); px(x-3,y-1,6,4,"#d94b4b");
  px(x-3,y-6,6,5,"#ffd6b8");
  px(x-3,y-6,6,2,"#2a2a2a");
  const fx=(facing===1)?1:-1;
  px(x-1+fx,y-4,1,1,"#111"); px(x+1+fx,y-4,1,1,"#111");
}
function drawFood(wx,wy,kind){
  const s=worldToScreen(wx,wy); const x=s.x|0, y=s.y|0;
  if(kind==="burger"){
    px(x-5,y-4,10,2,"#d6a15f");
    px(x-5,y-2,10,1,"#44d07b");
    px(x-5,y-1,10,1,"#6b3f24");
    px(x-5,y+1,10,2,"#c98e52");
  } else {
    px(x-4,y-5,8,10,"#ff9f43");
    px(x-3,y-4,6,8,"#ffcc66");
  }
}
function drawDrink(wx,wy,kind){
  const s=worldToScreen(wx,wy); const x=s.x|0, y=s.y|0;
  if(kind==="water"){
    px(x-3,y-6,6,12,"#6ad7ff"); px(x-2,y-5,4,10,"#c4f2ff");
  } else if(kind==="juice"){
    px(x-4,y-5,8,10,"#ffd56a"); px(x-3,y-4,6,8,"#ff7cb5");
  } else {
    px(x-3,y-5,6,10,"#ff7070"); px(x-2,y-4,4,8,"#d94b4b");
  }
}
function drawHolidayItem(wx,wy,kind){
  const s=worldToScreen(wx,wy); const x=s.x|0, y=s.y|0;
  if(kind==="cookie"){
    px(x-4,y-4,8,8,"#c98e52"); px(x-3,y-3,6,6,"#d6a15f");
  } else if(kind==="cocoa"){
    px(x-4,y-3,8,7,"#cfd6dd"); px(x-3,y-2,6,5,"#6b3f24");
  } else if(kind==="milk"){
    px(x-3,y-6,6,12,"#cfd6dd"); px(x-2,y-5,4,10,"#ffffff");
  } else {
    px(x-1,y-6,2,12,"#cfd6dd"); px(x+1,y-6,2,2,"#ff7070");
  }
}
function drawOrnament(wx,wy){
  const s=worldToScreen(wx,wy); const x=s.x|0, y=s.y|0;
  px(x-3,y-3,6,6,"#ff3b3b");
  px(x-2,y-2,4,4,"#ff7a7a");
  px(x-1,y-5,2,2,"#cfd6dd");
  px(x-2,y-6,4,1,"#ffe869");
  px(x+1,y-2,1,1,"rgba(255,255,255,0.7)");
}
function tintSnowOverlay(){ px(0,0,buf.width,buf.height,"rgba(220,240,255,0.06)"); }
function drawNightOverlay(){ px(0,0,buf.width,buf.height,"rgba(14,18,28,0.56)"); }

function drawHideDoorOverlay(){
  if(hideAnim.t<=0) return;
  const t=hideAnim.t, w=buf.width, h=buf.height;
  const leftW=(w/2)*t, rightW=(w/2)*t;
  px(0,0,leftW,h,"rgba(8,8,10,0.92)");
  px(w-rightW,0,rightW,h,"rgba(8,8,10,0.92)");
  px((w/2)-1,0,2,h,`rgba(255,255,255,${0.10*t})`);
  bctx.fillStyle=`rgba(255,255,255,${0.75*t})`;
  bctx.font="10px Arial";
  bctx.textAlign="center";
  bctx.fillText("HIDING", w/2, 22);
  bctx.font="9px Arial";
  bctx.fillText("stay quiet...", w/2, 34);
  bctx.textAlign="left";
}

/* =========================
   LOOP
========================= */
let lastFrame=performance.now();
let frameCounter=0;

function loop(now){
  if(!game.playing) return;
  const dt=Math.min(0.05,(now-lastFrame)/1000);
  lastFrame=now;
  frameCounter++;

  cam.x = player.x - buf.width/2;
  cam.y = player.y - buf.height/2;

  if(!game.invOpen && !game.hidden && !hideAnim.active){
    let mx=0,my=0;
    if(keys.left) mx-=1;
    if(keys.right) mx+=1;
    if(keys.up) my-=1;
    if(keys.down) my+=1;

    const moving = (mx!==0 || my!==0);

    if(game.sprint && player.stamina<=0){
      setSprint(false);
      toast("Sprint ended (out of stamina).");
    }

    if(moving){
      const len=Math.hypot(mx,my);
      mx/=len; my/=len;

      const sprintMul=(game.sprint && player.stamina>0) ? 1.60 : 1.0;
      let speed=player.speed*sprintMul;
      if(cheer.active) speed*=1.08;

      player.face=(mx>=0)?1:-1;
      moveWithCollision(player, player.x + mx*speed*dt, player.y + my*speed*dt, player.r);

      if(game.sprint){
        player.stamina = Math.max(0, player.stamina - (24*dt)); // slower drain
      }
    }
  }

  game.inHideSpot = hideSpots.some(s=>Math.hypot(player.x-s.x,player.y-s.y) < (s.r+player.r));
  if(!game.inHideSpot && game.hidden && !hideAnim.active){
    game.hidden=false; hideAnim.t=0; toast("You left the hiding spot.");
  }

  if(hideAnim.active){
    if(hideAnim.dir===1){
      hideAnim.t += dt/hideAnim.durClose;
      if(hideAnim.t>=1){ hideAnim.t=1; hideAnim.active=false; game.hidden=true; toast("Hidden."); }
    } else {
      hideAnim.t -= dt/hideAnim.durOpen;
      if(hideAnim.t<=0){ hideAnim.t=0; hideAnim.active=false; game.hidden=false; toast("Visible."); }
    }
  }

  const trulyHidden = game.hidden || (hideAnim.t>0.92 && hideAnim.dir===1);
  for(const e of employees){
    const dx=player.x-e.x, dy=player.y-e.y;
    const d=Math.hypot(dx,dy);
    const sees = (!trulyHidden && d < (game.params.vis/(canvas.width/buf.width)));

    if(sees){
      const ux=dx/(d||1), uy=dy/(d||1);
      e.face=(ux>=0)?1:-1;
      moveWithCollision(e, e.x + ux*game.params.empSpeed*dt, e.y + uy*game.params.empSpeed*dt, e.r);
    } else {
      e.wander += (Math.random()-0.5)*0.65*dt;
      const ux=Math.cos(e.wander), uy=Math.sin(e.wander);
      e.face=(ux>=0)?1:-1;
      moveWithCollision(e, e.x + ux*(game.params.empSpeed*0.42)*dt, e.y + uy*(game.params.empSpeed*0.42)*dt, e.r);
      if(circleHitsWalls(e.x,e.y,e.r)) e.wander += Math.PI/2;
    }

    if(e.cool>0) e.cool--;

    if(!trulyHidden && d < (e.r+player.r+2) && e.cool<=0){
      player.health -= game.params.dmg;
      e.cool = game.params.atkCool;
      toast(`Attacked! (-${game.params.dmg})`);
      if(player.health<=0){ player.health=0; loseGame("You got caught… Game Over."); return; }
    }
  }

  if(!game.hidden && !hideAnim.active){
    for(const f of foods){
      if(!f.taken && Math.hypot(player.x-f.x,player.y-f.y) < 12){
        f.taken=true; inventory[f.kind]=(inventory[f.kind]||0)+1; jingle();
        toast(`Picked up ${f.kind==="burger"?"Burger":"Chips"} (Inventory)`);
        if(game.invOpen) renderInventory();
      }
    }
    for(const d of drinks){
      if(!d.taken && Math.hypot(player.x-d.x,player.y-d.y) < 12){
        d.taken=true; inventory[d.kind]=(inventory[d.kind]||0)+1; jingle();
        const nm=d.kind==="water"?"Water":(d.kind==="juice"?"Juice":"Soda");
        toast(`Picked up ${nm} (Inventory)`);
        if(game.invOpen) renderInventory();
      }
    }
    if(EVENT.christmas){
      for(const h of holidayItems){
        if(!h.taken && Math.hypot(player.x-h.x,player.y-h.y) < 12){
          h.taken=true; inventory[h.kind]=(inventory[h.kind]||0)+1; jingle();
          const nm=h.kind==="cookie"?"Cookie":(h.kind==="cocoa"?"Hot Cocoa":(h.kind==="milk"?"Milk":"Candy Cane"));
          toast(`Picked up ${nm} (Inventory)`);
          if(game.invOpen) renderInventory();
        }
      }
    }

    if(game.difficultyKey==="santa" && EVENT.christmas){
      for(const o of ornaments){
        if(!o.taken && Math.hypot(player.x-o.x,player.y-o.y) < 12){
          o.taken=true;
          game.ornamentsFound++;
          jingle();
          toast(`Ornament found! (${game.ornamentsFound}/${game.ornamentsNeeded})`);
          if(game.ornamentsFound>=game.ornamentsNeeded){
            toast("All ornaments found! Survive until 8:00 AM!");
          }
        }
      }
    }
  }

  px(0,0,buf.width,buf.height,"#e9eef3");

  const startX=Math.floor(cam.x/TILE)-2;
  const startY=Math.floor(cam.y/TILE)-2;
  const endX=startX+Math.ceil(buf.width/TILE)+4;
  const endY=startY+Math.ceil(buf.height/TILE)+4;

  for(let ty=startY; ty<=endY; ty++){
    for(let tx=startX; tx<=endX; tx++){
      if(!inMap(tx,ty)) continue;
      drawTile(tx,ty,map[idx(tx,ty)]);
    }
  }

  drawDecor();

  for(const f of foods) if(!f.taken) drawFood(f.x,f.y,f.kind);
  for(const d of drinks) if(!d.taken) drawDrink(d.x,d.y,d.kind);
  if(EVENT.christmas){
    for(const h of holidayItems) if(!h.taken) drawHolidayItem(h.x,h.y,h.kind);
    tintSnowOverlay();
  }

  if(game.difficultyKey==="santa" && EVENT.christmas){
    for(const o of ornaments) if(!o.taken) drawOrnament(o.x,o.y);
  }

  for(const e of employees) drawEmployee(e.x,e.y,e.face,frameCounter);
  drawPlayer(player.x,player.y,player.face,frameCounter,game.hidden);

  if(EVENT.christmas && EVENT.snowParticles){
    for(const p of snow){
      p.y += p.spd*dt;
      if(p.y > buf.height+4){ p.y=-4; p.x=Math.random()*buf.width; }
      px(p.x,p.y,p.sz,p.sz,"rgba(255,255,255,0.55)");
    }
  }

  drawNightOverlay();

  // hide door overlay
  if(hideAnim.t>0){
    const t=hideAnim.t, w=buf.width, h=buf.height;
    const leftW=(w/2)*t, rightW=(w/2)*t;
    px(0,0,leftW,h,"rgba(8,8,10,0.92)");
    px(w-rightW,0,rightW,h,"rgba(8,8,10,0.92)");
    px((w/2)-1,0,2,h,`rgba(255,255,255,${0.10*t})`);
    bctx.fillStyle=`rgba(255,255,255,${0.75*t})`;
    bctx.font="10px Arial";
    bctx.textAlign="center";
    bctx.fillText("HIDING", w/2, 22);
    bctx.font="9px Arial";
    bctx.fillText("stay quiet...", w/2, 34);
    bctx.textAlign="left";
  }

  ctx.imageSmoothingEnabled=false;
  ctx.clearRect(0,0,canvas.width,canvas.height);
  ctx.drawImage(buf,0,0,buf.width,buf.height,0,0,canvas.width,canvas.height);

  updateUI();
  requestAnimationFrame(loop);
}

/* =========================
   DIFFICULTY UI
========================= */
function refreshDifficultyUI(){
  stats=loadStats();
  const sel=document.getElementById("diffSelect");
  const unlockText=document.getElementById("unlockText");
  sel.innerHTML="";
  const opts=getDifficultyOptions(stats.survives);
  for(const o of opts){
    const op=document.createElement("option");
    op.value=o.key;
    op.textContent=o.unlocked?o.label:`${o.label} (Locked)`;
    if(!o.unlocked) op.disabled=true;
    sel.appendChild(op);
  }
  sel.value="easy";

  let msg =
    stats.survives<5 ? "Medium unlocks at 5 survives. Hard unlocks at 10." :
    stats.survives<10 ? "Hard unlocks at 10 survives." :
    "All main difficulties unlocked.";

  if(EVENT.christmas){
    msg += " Santa Difficulty is available (limited-time).";
  }else{
    msg += " Christmas event ended (Jan 11, 2026).";
  }
  unlockText.textContent = msg;
}

/* =========================
   MENU BUTTONS
========================= */
document.getElementById("howBtn").onclick=()=>showPanel("how");

document.getElementById("statsBtn").onclick=()=>{
  stats=loadStats();
  document.getElementById("statsBox").innerHTML=`
    <div><b>Name:</b> ${esc(profile.name)}</div>
    <div><b>Total Play Time:</b> ${Math.floor(stats.totalPlaySeconds/60)}m ${stats.totalPlaySeconds%60}s</div>
    <div><b>Total Survives:</b> ${stats.survives}</div>
    <div><b>Total Deaths:</b> ${stats.deaths}</div>
    <div class="divider"></div>
    <div><b>Unlocks:</b></div>
    <div>Medium: ${stats.survives>=5 ? "Unlocked" : "Locked (need 5 survives)"}</div>
    <div>Hard: ${stats.survives>=10 ? "Unlocked" : "Locked (need 10 survives)"}</div>
    <div>Santa 🎄: ${EVENT.christmas ? "Available (until Jan 11, 2026)" : "Not available (event ended)"}</div>
  `;
  showPanel("stats");
};

document.getElementById("lbBtn").onclick=()=>{
  const lb=loadLB();
  const box=document.getElementById("lbBox");
  if(!lb.length) box.innerHTML=`<div>No runs yet.</div>`;
  else box.innerHTML=lb.map((r,i)=>`
    <div style="padding:6px 0;">
      <b>#${i+1}</b> ${esc(r.name)} — <b>${Math.floor(r.seconds/60)}m ${r.seconds%60}s</b>
      <span class="badge">(${diffLabel(r.difficulty)})</span>
    </div>
  `).join("");
  showPanel("leaderboard");
};

document.getElementById("playBtn").onclick=()=>{
  profile.name=nameInput.value.trim()||("Player"+rand4());
  saveProfile(profile);

  stats=loadStats();
  const chosen=document.getElementById("diffSelect").value;
  const opts=getDifficultyOptions(stats.survives);
  const ok=opts.find(o=>o.key===chosen && o.unlocked);
  game.difficultyKey= ok ? chosen : "easy";

  if(game.difficultyKey==="santa" && !EVENT.christmas){
    game.difficultyKey="easy";
    toast("Santa event ended.");
  }

  game.params=diffParams(game.difficultyKey);
  startGame();
};

/* =========================
   MULTIPLAYER (LOCAL TABS)
========================= */
document.getElementById("multiBtn").onclick=()=>{
  profile.name=nameInput.value.trim()||("Player"+rand4());
  saveProfile(profile);
  showPanel("multiplayer");
};
document.getElementById("hostBtn").onclick=()=>showPanel("hostSetup");
document.getElementById("joinBtn").onclick=()=>{ renderServerList(); showPanel("joinList"); };

function loadServers(){
  let s=safeParse(localStorage.getItem(LS.servers),[]);
  if(!Array.isArray(s)) s=[];
  const now=Date.now();
  s=s.filter(x=>x && (now-(x.updatedAt||0))<10*60*1000);
  localStorage.setItem(LS.servers,JSON.stringify(s));
  return s;
}
function saveServers(s){ localStorage.setItem(LS.servers,JSON.stringify(s)); }
function makeServerId(){ return "srv_"+Math.random().toString(16).slice(2)+"_"+Date.now(); }
let lobbyPoll=null;

document.getElementById("createServerBtn").onclick=()=>{
  const maxP=parseInt(document.getElementById("maxPlayersSelect").value,10);
  const servers=loadServers();
  const id=makeServerId();
  const server={
    id, hostName:profile.name, maxPlayers:maxP,
    players:[profile.name], started:false,
    difficultyKey:document.getElementById("diffSelect").value||"easy",
    updatedAt:Date.now()
  };
  if(server.difficultyKey==="santa" && !EVENT.christmas) server.difficultyKey="easy";

  servers.push(server); saveServers(servers);
  game.mode="multi"; game.serverId=id; game.isHost=true;
  openLobby();
};

function renderServerList(){
  const box=document.getElementById("serverList");
  const servers=loadServers().filter(s=>!s.started);
  if(!servers.length){ box.innerHTML=`<div>No servers yet.</div>`; return; }
  box.innerHTML=servers.map(s=>`
    <div class="serverRow">
      <div>
        <div><b>${esc(s.hostName)}’s Server</b></div>
        <div class="badge">${s.players.length}/${s.maxPlayers} • ${diffLabel(s.difficultyKey)}</div>
      </div>
      <button onclick="joinServer('${s.id}')">Join</button>
    </div>
  `).join("");
}

function joinServer(id){
  const servers=loadServers();
  const s=servers.find(x=>x.id===id);
  if(!s) return toast("Server not found.");
  if(s.started) return toast("Already started.");
  if(s.players.includes(profile.name)) return toast("Already in server.");
  if(s.players.length>=s.maxPlayers) return toast("Server full.");
  s.players.push(profile.name); s.updatedAt=Date.now(); saveServers(servers);
  game.mode="multi"; game.serverId=id; game.isHost=false;
  openLobby();
}

function openLobby(){
  showPanel("lobby");
  if(lobbyPoll) clearInterval(lobbyPoll);
  lobbyPoll=setInterval(updateLobby,700);
  updateLobby();
}

function updateLobby(){
  const servers=loadServers();
  const s=servers.find(x=>x.id===game.serverId);
  if(!s){ toast("Lobby closed."); leaveLobby(); return; }
  s.updatedAt=Date.now(); saveServers(servers);

  document.getElementById("lobbyInfo").innerHTML =
    `<b>${esc(s.hostName)}’s Server</b> • ${s.players.length}/${s.maxPlayers} • ${diffLabel(s.difficultyKey)}`;

  document.getElementById("playerList").innerHTML =
    s.players.map((p,i)=>`<div style="padding:6px 0;"><b>${i+1}.</b> ${esc(p)}</div>`).join("");

  const startBtn=document.getElementById("startHostBtn");
  startBtn.style.display = game.isHost ? "inline-block" : "none";
  startBtn.disabled = !(s.players.length>=2);

  if(s.started){
    game.difficultyKey=s.difficultyKey;
    game.params=diffParams(game.difficultyKey);
    if(lobbyPoll) clearInterval(lobbyPoll);
    lobbyPoll=null;
    startGame();
    toast("Game started!");
  }
}

document.getElementById("startHostBtn").onclick=()=>{
  const servers=loadServers();
  const s=servers.find(x=>x.id===game.serverId);
  if(!s) return;
  if(s.players.length<2) return toast("Need at least 2 players.");
  s.started=true; s.updatedAt=Date.now(); saveServers(servers);
};

document.getElementById("leaveLobbyBtn").onclick=()=>leaveLobby();

function leaveLobby(){
  if(lobbyPoll) clearInterval(lobbyPoll);
  lobbyPoll=null;
  const servers=loadServers();
  const s=servers.find(x=>x.id===game.serverId);
  if(s){
    s.players=s.players.filter(p=>p!==profile.name);
    if(game.isHost || s.players.length===0) saveServers(servers.filter(x=>x.id!==game.serverId));
    else { s.updatedAt=Date.now(); saveServers(servers); }
  }
  game.serverId=null; game.isHost=false;
  showPanel("multiplayer");
}
function leaveMultiplayer(){
  if(game.serverId) leaveLobby();
  showPanel("menu");
}
setInterval(()=>{ if(document.getElementById("joinList").style.display==="flex") renderServerList(); },800);

/* =========================
   INIT
========================= */
(function init(){
  showPanel("menu");
  profile=loadProfile();
  stats=loadStats();
  nameInput.value=profile.name;
  refreshDifficultyUI();

  const top=document.getElementById("eventNoteTop");
  const bottom=document.getElementById("eventNoteBottom");
  if(CHRISTMAS_ACTIVE){
    top.textContent = "✨ Christmas Update is active — ends Jan 11, 2026 ✨";
    bottom.textContent = "🎁 Christmas + Santa Difficulty will leave on Jan 11, 2026.";
  }else{
    top.textContent = "Winter event has ended (Jan 11, 2026).";
    bottom.textContent = "No Christmas content right now.";
  }
})();
</script>
</body>
</html>
