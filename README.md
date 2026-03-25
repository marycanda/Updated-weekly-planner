# Updated-weekly-planner
<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Week Plan">
<meta name="theme-color" content="#c68642">
<link rel="apple-touch-icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 180 180'%3E%3Crect width='180' height='180' rx='40' fill='%23c68642'/%3E%3Ctext x='90' y='115' font-size='90' text-anchor='middle' font-family='system-ui'%3E📅%3C/text%3E%3C/svg%3E">
<title>Week Plan</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#12100e;--bg3:#1e1a16;--surface:#252018;--surface2:#2e2720;
  --border:rgba(255,220,180,0.08);--border2:rgba(255,220,180,0.16);
  --text:#f0e8dc;--text2:#a89880;--text3:#6b5a47;
  --work:#1a2a1e;--work-b:#5aac6e;--work-t:#a8e0b4;
  --pilates:#2a1a3e;--pilates-b:#b87ef0;--pilates-t:#e8d0ff;
  --strength:#2e1800;--strength-b:#f07828;--strength-t:#ffd4a8;
  --run:#1e1a0a;--run-b:#c8a832;--run-t:#f0e090;
  --yoga:#2a2200;--yoga-b:#e8c832;--yoga-t:#fff0a0;
  --climb:#2a1a08;--climb-b:#c87a20;--climb-t:#f0c080;
  --surf:#0e1e2a;--surf-b:#3a9ec8;--surf-t:#a0d8f0;
  --appt:#2e0e0e;--appt-b:#e05050;--appt-t:#fac0c0;
  --sleep:#100e0c;--sleep-t:#3a2e24;
  --commute:#1a1610;--commute-t:#5a4a38;
  --free-t:#4a3828;
  --accent:#e8673a;--accent2:#d4882a;
}
*{box-sizing:border-box;margin:0;padding:0;}
body{background:var(--bg);color:var(--text);font-family:'DM Mono',monospace;min-height:100vh;}
body::before{content:'';position:fixed;inset:0;pointer-events:none;z-index:0;opacity:0.4;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");}
.app{position:relative;z-index:1;max-width:1140px;margin:0 auto;padding:env(safe-area-inset-top, 1rem) max(1.25rem, env(safe-area-inset-right)) 5rem max(1.25rem, env(safe-area-inset-left));}

@media(max-width:480px){
.toggle{width:36px;height:20px;}
.toggle::after{width:14px;height:14px;}
.toggle.on::after{transform:translateX(16px);}
.wk-cell,.yoga-cell,.surf-cell,.opt-cell{height:46px;font-size:11px;}
.act-lbl{height:46px;font-size:10px;}
.cell{height:32px;font-size:9px;}
.time-lbl{height:32px;font-size:9px;}
}

header{display:flex;align-items:flex-end;justify-content:space-between;margin-bottom:2rem;padding-bottom:1.25rem;border-bottom:1px solid var(–border2);flex-wrap:wrap;gap:1rem;}
.header-left h1{font-family:‘Syne’,sans-serif;font-size:clamp(1.5rem,4vw,2.4rem);font-weight:700;letter-spacing:-0.03em;line-height:1;}
.header-left h1 span{color:var(–accent);}
.header-left .sub{font-size:11px;color:var(–text3);margin-top:5px;letter-spacing:0.08em;text-transform:uppercase;}
.week-nav{display:flex;align-items:center;gap:10px;}
.week-nav button{width:30px;height:30px;background:var(–surface);border:1px solid var(–border2);border-radius:50%;color:var(–text2);cursor:pointer;font-size:13px;display:flex;align-items:center;justify-content:center;transition:all .15s;}
.week-nav button:hover{background:var(–surface2);color:var(–text);}
.week-label{font-family:‘Syne’,sans-serif;font-size:12px;font-weight:600;color:var(–text2);min-width:150px;text-align:center;}

.summary-row{display:flex;gap:7px;margin-bottom:1.5rem;flex-wrap:wrap;}
.pill{display:flex;align-items:center;gap:5px;padding:4px 11px;border-radius:20px;font-size:11px;font-family:‘DM Mono’,monospace;border:1px solid;letter-spacing:.02em;}
.pill.work-pill   {background:var(–work);   border-color:var(–work-b);   color:var(–work-t);}
.pill.workout-pill{background:var(–pilates);border-color:var(–pilates-b);color:var(–pilates-t);}
.pill.yoga-pill   {background:var(–yoga);   border-color:var(–yoga-b);   color:var(–yoga-t);}
.pill.climb-pill  {background:var(–climb);  border-color:var(–climb-b);  color:var(–climb-t);}
.pill.surf-pill   {background:var(–surf);   border-color:var(–surf-b);   color:var(–surf-t);}

.legend{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:1.1rem;align-items:center;}
.leg-item{display:flex;align-items:center;gap:5px;font-size:11px;color:var(–text3);}
.leg-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0;}
.reset-btn{margin-left:auto;padding:4px 12px;background:transparent;border:1px solid var(–border2);border-radius:6px;color:var(–text3);font-family:‘DM Mono’,monospace;font-size:11px;cursor:pointer;transition:all .15s;}
.reset-btn:hover{border-color:var(–accent);color:var(–accent);}

.day-controls{display:grid;grid-template-columns:54px repeat(7,minmax(0,1fr));gap:3px;margin-bottom:3px;}
.day-head{background:var(–surface);border:1px solid var(–border);border-radius:8px;padding:7px 4px;display:flex;flex-direction:column;align-items:center;gap:4px;transition:background .2s;}
.day-head.is-work{background:rgba(26,42,30,.7);border-color:rgba(90,172,110,.3);}
.day-name{font-family:‘Syne’,sans-serif;font-size:11px;font-weight:600;color:var(–text2);letter-spacing:.07em;text-transform:uppercase;}
.day-head.is-work .day-name{color:var(–work-t);}
.toggle{width:30px;height:16px;border-radius:8px;border:1px solid var(–border2);background:var(–bg3);cursor:pointer;position:relative;transition:background .2s,border-color .2s;flex-shrink:0;}
.toggle.on{background:var(–work-b);border-color:var(–work-b);}
.toggle::after{content:’’;position:absolute;top:2px;left:2px;width:10px;height:10px;border-radius:50%;background:rgba(255,255,255,.45);transition:transform .2s,background .2s;}
.toggle.on::after{transform:translateX(14px);background:white;}
.day-badge{font-size:9px;letter-spacing:.05em;text-transform:uppercase;padding:2px 5px;border-radius:3px;}
.day-badge.work{background:rgba(90,172,110,.15);color:var(–work-b);}
.day-badge.off{background:var(–bg3);color:var(–text3);}

.planner-grid{display:grid;grid-template-columns:54px repeat(7,minmax(0,1fr));gap:3px;}
.time-lbl{display:flex;align-items:flex-start;justify-content:flex-end;padding-right:7px;padding-top:3px;font-size:10px;color:var(–text3);height:36px;letter-spacing:.03em;}
.cell{height:36px;border-radius:5px;display:flex;align-items:center;justify-content:center;font-size:11px;text-align:center;line-height:1.2;padding:2px 3px;border:1px solid transparent;transition:filter .15s;letter-spacing:.02em;overflow:hidden;font-family:‘DM Mono’,monospace;}
.cell:hover{filter:brightness(1.18);}
.cell.work    {background:var(–work);    border-color:rgba(90,172,110,.25);  color:var(–work-t);}
.cell.work.s  {border-color:rgba(90,172,110,.65);}
.cell.work.e  {border-color:rgba(90,172,110,.5);}
.cell.pilates {background:var(–pilates); border-color:rgba(184,126,240,.45); color:var(–pilates-t);}
.cell.strength{background:var(–strength);border-color:rgba(240,120,40,.45);  color:var(–strength-t);}
.cell.pilates.run  {background:var(–pilates); border-color:rgba(184,126,240,.6);  color:var(–pilates-t);opacity:.85;}
.cell.strength.run {background:var(–strength);border-color:rgba(240,120,40,.6);   color:var(–strength-t);opacity:.85;}
.cell.run     {background:var(–run);     border-color:rgba(200,168,50,.4);   color:var(–run-t);}
.cell.yoga    {background:var(–yoga);    border-color:rgba(232,200,50,.45);  color:var(–yoga-t);}
.cell.climb   {background:var(–climb);   border-color:rgba(200,122,32,.45);  color:var(–climb-t);}
.cell.surf    {background:var(–surf);    border-color:rgba(58,158,200,.4);   color:var(–surf-t);}
.cell.appt    {background:var(–appt);    border-color:rgba(224,80,80,.45);   color:var(–appt-t);}
.cell.sleep   {background:var(–sleep);   color:var(–sleep-t);}
.cell.commute {background:var(–commute); border-color:rgba(255,220,180,.04); color:var(–commute-t);}
.cell.free    {background:transparent;   border-color:var(–border);          color:var(–free-t);}

.limit-note{font-size:11px;color:var(–text3);margin-top:4px;text-align:center;display:none;}
.limit-note.show{display:block;}

.act-panel{margin-top:1.5rem;background:var(–surface);border:1px solid var(–border2);border-radius:12px;padding:1rem 1.25rem;}
.act-panel-title{font-family:‘Syne’,sans-serif;font-size:12px;font-weight:600;color:var(–text3);letter-spacing:.08em;text-transform:uppercase;margin-bottom:3px;}
.act-panel-hint{font-size:11px;color:var(–text3);margin-bottom:12px;line-height:1.6;}
.act-grid{display:grid;grid-template-columns:54px repeat(7,minmax(0,1fr));gap:3px;}
.act-lbl{display:flex;align-items:center;justify-content:flex-end;padding-right:7px;font-size:10px;color:var(–text3);height:42px;white-space:nowrap;letter-spacing:.02em;}
.opt-gap{grid-column:1 / -1;height:5px;}

.wk-cell{height:42px;border-radius:5px;display:flex;align-items:center;justify-content:center;font-size:10px;text-align:center;padding:2px 3px;cursor:pointer;border:1px solid;transition:all .15s;letter-spacing:.02em;user-select:none;font-family:‘DM Mono’,monospace;}
.wk-cell.pilates-mode {background:var(–pilates); border-color:rgba(184,126,240,.55); color:var(–pilates-t);}
.wk-cell.strength-mode{background:var(–strength);border-color:rgba(240,120,40,.55);  color:var(–strength-t);}
.wk-cell.inactive{background:var(–bg3);border:1px dashed rgba(255,220,180,.1);color:var(–text3);}

.yoga-cell{height:42px;border-radius:5px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px;font-size:10px;text-align:center;padding:4px 3px;cursor:pointer;border:1px dashed rgba(255,220,180,.1);background:var(–bg3);color:var(–text3);transition:border-color .15s;letter-spacing:.02em;user-select:none;font-family:‘DM Mono’,monospace;}
.yoga-cell:hover:not(.yoga-on){border-color:rgba(232,200,50,.4);color:var(–yoga-t);}
.yoga-cell.yoga-on:hover{filter:brightness(1.12);}
.yoga-cell.yoga-on{background:var(–yoga);border:1px solid rgba(232,200,50,.55);color:var(–yoga-t);cursor:default;}
.yoga-cell .yc-label{font-size:10px;line-height:1;}
.yoga-cell select{background:#0a0d14;border:1px solid rgba(255,255,255,.15);border-radius:3px;color:var(–text2);font-family:‘DM Mono’,monospace;font-size:10px;cursor:pointer;outline:none;-webkit-appearance:none;text-align:center;padding:1px 3px;width:100%;max-width:62px;}

.surf-cell{height:42px;border-radius:5px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px;font-size:10px;text-align:center;padding:4px 3px;cursor:pointer;border:1px dashed rgba(255,220,180,.1);background:var(–bg3);color:var(–text3);transition:border-color .15s;letter-spacing:.02em;user-select:none;font-family:‘DM Mono’,monospace;}
.surf-cell:hover:not(.surf-on):not(.surf-locked):not(.surf-disabled){border-color:rgba(58,158,200,.4);color:var(–surf-t);}
.surf-cell.surf-on:hover{filter:brightness(1.12);}
.surf-cell.surf-on{background:var(–surf);border:1px solid rgba(58,158,200,.55);color:var(–surf-t);cursor:default;}
.surf-cell.surf-locked{opacity:.32;cursor:not-allowed;}
.surf-cell.surf-disabled{opacity:.18;cursor:default;}
.surf-cell .sc-label{font-size:10px;line-height:1;}
.surf-cell select{background:#0a0d14;border:1px solid rgba(255,255,255,.15);border-radius:3px;color:var(–text2);font-family:‘DM Mono’,monospace;font-size:10px;cursor:pointer;outline:none;-webkit-appearance:none;text-align:center;padding:1px 3px;width:100%;max-width:62px;}

.opt-cell{height:42px;border-radius:5px;display:flex;align-items:center;justify-content:center;font-size:10px;cursor:pointer;border:1px dashed rgba(255,220,180,.1);background:var(–bg3);color:var(–text3);transition:all .15s;text-align:center;padding:2px 3px;user-select:none;letter-spacing:.02em;font-family:‘DM Mono’,monospace;}
.opt-cell:hover:not(.opt-disabled):not(.opt-locked){border-color:rgba(255,220,180,.3);color:var(–text2);}
.opt-cell.opt-disabled{opacity:.18;cursor:default;}
.opt-cell.opt-locked{opacity:.32;cursor:not-allowed;}

.forecast-bar{margin-top:1.25rem;background:var(–surface);border:1px solid var(–border2);border-radius:12px;padding:1rem 1.25rem;}
.forecast-bar h3{font-family:‘Syne’,sans-serif;font-size:12px;font-weight:600;color:var(–text3);letter-spacing:.08em;text-transform:uppercase;margin-bottom:10px;}
.forecast-days{display:grid;grid-template-columns:repeat(7,1fr);gap:6px;}
.fday{background:var(–bg3);border-radius:8px;padding:9px 5px;display:flex;flex-direction:column;align-items:center;gap:4px;border:1px solid var(–border);}
.fday .fd-name{font-size:10px;color:var(–text3);letter-spacing:.06em;text-transform:uppercase;font-family:‘DM Mono’,monospace;}
.fday .fd-wave{font-size:17px;line-height:1;}
.fday .fd-size{font-size:11px;font-weight:500;color:var(–text);font-family:‘Syne’,sans-serif;}
.fday .fd-tag{font-size:9px;padding:2px 6px;border-radius:3px;letter-spacing:.04em;font-family:‘DM Mono’,monospace;}
.fday.surfable{border-color:rgba(58,158,200,.55);background:rgba(10,30,42,.85);}
.fday.surfable .fd-name,.fday.surfable .fd-size{color:var(–surf-t);}
.fday.surfable .fd-tag{background:rgba(58,158,200,.2);color:var(–surf-t);}
.fday.flat{opacity:.38;}
.fday.flat .fd-tag{background:var(–bg3);color:var(–text3);}
.fday.ok-surf .fd-tag{background:rgba(232,200,50,.15);color:var(–yoga-t);}
.fday select{background:transparent;border:none;color:var(–text2);font-family:‘DM Mono’,monospace;font-size:10px;cursor:pointer;width:100%;outline:none;-webkit-appearance:none;text-align:center;}

.bottom-row{margin-top:1.25rem;display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.card{background:var(–surface);border:1px solid var(–border);border-radius:12px;padding:1rem 1.25rem;}
.card h3{font-family:‘Syne’,sans-serif;font-size:12px;font-weight:600;color:var(–text3);letter-spacing:.08em;text-transform:uppercase;margin-bottom:10px;}
.stat-row{display:flex;justify-content:space-between;align-items:center;padding:5px 0;border-bottom:1px solid var(–border);}
.stat-row:last-child{border-bottom:none;}
.stat-label{font-size:12px;color:var(–text2);}
.stat-val{font-size:13px;font-weight:500;color:var(–accent);font-family:‘Syne’,sans-serif;}
.stat-val.warn{color:var(–accent2);}

.appt-list{display:flex;flex-direction:column;gap:6px;margin-bottom:10px;}
.appt-item{display:flex;align-items:center;gap:6px;background:var(–bg3);border-radius:6px;padding:6px 8px;border:1px solid rgba(224,80,80,.25);}
.appt-item .appt-day{font-size:10px;color:var(–appt-t);min-width:28px;font-weight:500;}
.appt-item .appt-time{font-size:10px;color:var(–text3);min-width:44px;}
.appt-item .appt-desc{font-size:11px;color:var(–text2);flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
.appt-item .appt-del{background:transparent;border:none;color:var(–text3);cursor:pointer;font-size:13px;padding:0 2px;line-height:1;transition:color .15s;flex-shrink:0;}
.appt-item .appt-del:hover{color:var(–appt-b);}
.appt-add-row{display:grid;grid-template-columns:80px 70px 1fr auto;gap:5px;align-items:center;}
.appt-add-row select,.appt-add-row input{background:var(–bg3);border:1px solid var(–border2);border-radius:5px;color:var(–text2);font-family:‘DM Mono’,monospace;font-size:11px;padding:5px 7px;outline:none;transition:border-color .15s;width:100%;}
.appt-add-row select{-webkit-appearance:none;cursor:pointer;}
.appt-add-row input::placeholder{color:var(–text3);}
.appt-add-row select:focus,.appt-add-row input:focus{border-color:rgba(224,80,80,.5);}
.appt-add-btn{padding:5px 10px;background:transparent;border:1px solid rgba(224,80,80,.4);border-radius:5px;color:var(–appt-t);font-family:‘DM Mono’,monospace;font-size:11px;cursor:pointer;transition:all .15s;white-space:nowrap;}
.appt-add-btn:hover{background:rgba(224,80,80,.15);}

.notes-textarea{width:100%;background:var(–bg3);border:1px solid var(–border);border-radius:8px;color:var(–text2);font-family:‘DM Mono’,monospace;font-size:12px;padding:10px;resize:none;height:88px;outline:none;transition:border-color .15s;line-height:1.6;}
.notes-textarea:focus{border-color:var(–border2);}
.notes-textarea::placeholder{color:var(–text3);}
.horizon{height:1px;background:linear-gradient(90deg,transparent,var(–accent),transparent);opacity:.2;margin:1.75rem 0 1.25rem;}

@media(max-width:620px){
.bottom-row{grid-template-columns:1fr;}
.forecast-days{grid-template-columns:repeat(4,1fr);}
.appt-add-row{grid-template-columns:1fr 1fr;}
}
</style>

</head>
<body>
<div class="app">

<header>
  <div class="header-left">
    <h1>week<span>.</span>plan</h1>
    <p class="sub">4 × 10h shifts · 7 AM–5 PM · active lifestyle</p>
  </div>
  <div class="week-nav">
    <button id="prev-week">&#8592;</button>
    <div class="week-label" id="week-label">—</div>
    <button id="next-week">&#8594;</button>
  </div>
</header>

<div class="summary-row" id="summary-row"></div>

<div class="legend">
  <div class="leg-item"><div class="leg-dot" style="background:var(--work-b)"></div>Work</div>
  <div class="leg-item"><div class="leg-dot" style="background:var(--pilates-b)"></div>Pilates 45m</div>
  <div class="leg-item"><div class="leg-dot" style="background:var(--strength-b)"></div>Strength 40m</div>
  <div class="leg-item"><div class="leg-dot" style="background:var(--yoga-b)"></div>Hot yoga 1h</div>
  <div class="leg-item"><div class="leg-dot" style="background:var(--climb-b)"></div>Climbing</div>
  <div class="leg-item"><div class="leg-dot" style="background:var(--surf-b);opacity:.8"></div>Surf 3–4h</div>
  <div class="leg-item"><div class="leg-dot" style="background:var(--appt-b)"></div>Appointment</div>
  <button class="reset-btn" id="reset-btn">Reset week</button>
</div>

<div class="day-controls" id="day-controls"></div>
<div class="limit-note" id="limit-note">max 4 work days reached</div>
<div class="planner-grid" id="planner-grid"></div>

<div class="act-panel">
  <div class="act-panel-title">Daily activity options</div>
  <div class="act-panel-hint">
    Tap to add · tap again to remove · booked cells show ✕
  </div>
  <div class="act-grid" id="act-grid"></div>
</div>

<div class="horizon"></div>

<div class="forecast-bar">
  <h3>Surf forecast — fair to good 2–3 ft · pumping 3–4 ft · ≤3 kt wind</h3>
  <div class="forecast-days" id="forecast-days"></div>
</div>

<div class="bottom-row">
  <div class="card"><h3>This week</h3><div id="stats"></div></div>
  <div class="card">
    <h3>Appointments &amp; notes</h3>
    <div class="appt-list" id="appt-list"></div>
    <div class="appt-add-row">
      <select id="appt-day"></select>
      <input type="time" id="appt-time" value="09:00">
      <input type="text" id="appt-desc" placeholder="e.g. Dr. Smith checkup">
      <button class="appt-add-btn" id="appt-add-btn">+ add</button>
    </div>
    <div style="margin-top:10px;">
      <textarea class="notes-textarea" id="notes-area" placeholder="general notes, surf links, gym hours..."></textarea>
    </div>
  </div>
</div>

</div>
<script>
const DAYS=['Mon','Tue','Wed','Thu','Fri','Sat','Sun'];
const HOURS=['5 AM','6 AM','7 AM','8 AM','9 AM','10 AM','11 AM','12 PM','1 PM','2 PM','3 PM','4 PM','5 PM','6 PM','7 PM','8 PM','9 PM','10 PM','11 PM'];
const HI={};HOURS.forEach((h,i)=>HI[h]=i);
const YOGA_TIMES=['6 AM','7 AM','8 AM','9 AM','10 AM','11 AM','12 PM','1 PM','2 PM','3 PM','4 PM','5 PM','6 PM'];
const SURF_STARTS=['5 AM','6 AM','7 AM','8 AM','9 AM','10 AM','11 AM','12 PM'];
const CLIMB_TIMES=['6 AM','7 AM','8 AM','9 AM','10 AM','11 AM','12 PM','1 PM','2 PM','3 PM','4 PM','5 PM','6 PM','7 PM','8 PM','9 PM'];

let workDays=[true,true,true,true,false,false,false];
let workoutType=[‘pilates’,‘pilates’,‘pilates’,‘none’,null,null,null];
let offWorkout=[null,null,null,null,‘none’,‘none’,‘none’];
let yogaDays=Array(7).fill(false);
let yogaTime=Array(7).fill(‘7 AM’);
let climbDays=Array(7).fill(false);
let climbTime=Array(7).fill(‘10 AM’);
let surfDays=Array(7).fill(false);
let surfWorkDay=Array(7).fill(false);
let surfStart=Array(7).fill(‘7 AM’);
let surfFcast=Array(7).fill(‘ok’);
let appointments=[];
let notes=’’;
let weekOff=0;

const isSurfable=i=>surfFcast[i]===‘good’||surfFcast[i]===‘ok’;
function hoursFrom(start,count){const idx=HI[start];if(idx===undefined)return[];return HOURS.slice(idx,Math.min(idx+count,HOURS.length));}
function timeToHour(t){const[h,m]=t.split(’:’).map(Number);const total=h*60+m;let best=HOURS[0],bestD=Infinity;HOURS.forEach(hr=>{const[hh]=parseHr(hr);const d=Math.abs(hh*60-total);if(d<bestD){bestD=d;best=hr;}});return best;}
function parseHr(hr){const[t,ap]=hr.split(’ ’);let h=parseInt(t);if(ap===‘PM’&&h!==12)h+=12;if(ap===‘AM’&&h===12)h=0;return[h,0];}
function countWk(){let n=0;DAYS.forEach((_,i)=>{if(workDays[i]){if(workoutType[i]===‘pilates’||workoutType[i]===‘strength’)n++;}else{if(offWorkout[i]===‘pilates’||offWorkout[i]===‘strength’)n++;}});return n;}

function workSched(d){
const wt=workoutType[d],hasYoga=yogaDays[d],hasClimb=climbDays[d],hasPreSurf=surfWorkDay[d]&&isSurfable(d);
const s={};HOURS.forEach(h=>s[h]={cls:‘free’,lb:’’});
Object.assign(s,{‘5 AM’:{cls:‘sleep’,lb:‘sleep’},‘6 AM’:{cls:‘sleep’,lb:‘sleep’},‘7 AM’:{cls:‘work s’,lb:‘work’},‘8 AM’:{cls:‘work’,lb:‘work’},‘9 AM’:{cls:‘work’,lb:‘work’},‘10 AM’:{cls:‘work’,lb:‘work’},‘11 AM’:{cls:‘work’,lb:‘work’},‘12 PM’:{cls:‘work’,lb:‘work’},‘1 PM’:{cls:‘work’,lb:‘work’},‘2 PM’:{cls:‘work’,lb:‘work’},‘3 PM’:{cls:‘work’,lb:‘work’},‘4 PM’:{cls:‘work e’,lb:‘work’},‘5 PM’:{cls:‘commute’,lb:‘🚗’},‘9 PM’:{cls:‘sleep’,lb:‘sleep’},‘10 PM’:{cls:‘sleep’,lb:‘sleep’},‘11 PM’:{cls:‘sleep’,lb:‘sleep’}});
if(hasPreSurf){s[‘5 AM’]={cls:‘surf’,lb:‘🏄’};s[‘6 AM’]={cls:‘surf’,lb:‘🏄’};}
appointments.filter(a=>a.day===d).forEach(a=>{s[timeToHour(a.time)]={cls:‘appt’,lb:a.desc||‘📅’};});
if(hasClimb){s[‘5 PM’]={cls:‘climb’,lb:‘🧗’};s[‘6 PM’]={cls:‘climb’,lb:‘🧗’};s[‘7 PM’]={cls:‘free’,lb:’’};s[‘8 PM’]={cls:‘free’,lb:’’};}
else if(hasYoga){const yt=(HI[yogaTime[d]]>=HI[‘6 PM’])?yogaTime[d]:‘6 PM’;s[yt]={cls:‘yoga’,lb:‘🧘’};const nx=HOURS[HI[yt]+1];if(nx)s[nx]={cls:‘free’,lb:’’};s[‘8 PM’]={cls:‘free’,lb:’’};}
else if(wt===‘pilates’){s[‘6 PM’]={cls:‘pilates’,lb:‘🤸’};s[‘7 PM’]={cls:‘pilates run’,lb:‘🏃’};}
else if(wt===‘strength’){s[‘6 PM’]={cls:‘strength’,lb:‘🏋️’};s[‘7 PM’]={cls:‘strength run’,lb:‘🏃’};}
else{s[‘6 PM’]={cls:‘free’,lb:’’};s[‘7 PM’]={cls:‘free’,lb:’’};s[‘8 PM’]={cls:‘free’,lb:’’};}
return s;
}

function offSched(d){
const hasYoga=yogaDays[d],hasClimb=climbDays[d],hasSurf=surfDays[d]&&isSurfable(d),ow=offWorkout[d];
const s={};HOURS.forEach(h=>s[h]={cls:‘free’,lb:’’});
s[‘5 AM’]={cls:‘free’,lb:’’};s[‘9 PM’]={cls:‘free’,lb:’’};s[‘10 PM’]={cls:‘free’,lb:’’};s[‘11 PM’]={cls:‘free’,lb:’’};
if(hasSurf){const ss=surfStart[d]||‘7 AM’;hoursFrom(ss,4).forEach((h,i,arr)=>{s[h]={cls:‘surf’,lb:‘🏄’};});}
if(hasYoga){const yt=yogaTime[d]||‘9 AM’;s[yt]={cls:‘yoga’,lb:‘🧘’};}
if(hasClimb){const cs=climbTime[d]||‘10 AM’;s[cs]={cls:‘climb’,lb:‘🧗’};const nx=HOURS[HI[cs]+1];if(nx)s[nx]={cls:‘climb’,lb:‘🧗’};}
if(ow===‘pilates’){s[‘9 AM’]={cls:‘pilates’,lb:‘🤸’};s[‘10 AM’]={cls:‘pilates run’,lb:‘🏃’};}
else if(ow===‘strength’){s[‘9 AM’]={cls:‘strength’,lb:‘🏋️’};s[‘10 AM’]={cls:‘strength run’,lb:‘🏃’};}
appointments.filter(a=>a.day===d).forEach(a=>{s[timeToHour(a.time)]={cls:‘appt’,lb:a.desc||‘📅’};});
return s;
}

function buildHeader(){document.getElementById(‘week-label’).textContent=getWeekLabel(weekOff);}

function buildSummary(){
const row=document.getElementById(‘summary-row’);row.innerHTML=’’;
const wc=workDays.filter(Boolean).length;let pC=0,sC=0;
DAYS.forEach((_,i)=>{if(workDays[i]){if(yogaDays[i]||climbDays[i])return;if(workoutType[i]===‘pilates’)pC++;if(workoutType[i]===‘strength’)sC++;}else{if(offWorkout[i]===‘pilates’)pC++;if(offWorkout[i]===‘strength’)sC++;}});
const yC=yogaDays.filter(Boolean).length,cC=climbDays.filter(Boolean).length,sfC=surfDays.filter(Boolean).length+surfWorkDay.filter(Boolean).length;
const wL=pC>0&&sC>0?`pilates ${pC}× · strength ${sC}×`:pC>0?`pilates · ${pC}×`:sC>0?`strength · ${sC}×`:‘no workout’;
[{cls:‘work-pill’,pip:‘var(–work-b)’,lb:`${wc} work days · ${wc*10}h`},{cls:‘workout-pill’,pip:‘var(–pilates-b)’,lb:wL},{cls:‘yoga-pill’,pip:‘var(–yoga-b)’,lb:`hot yoga · ${yC}×`},{cls:‘climb-pill’,pip:‘var(–climb-b)’,lb:`climbing · ${cC}×`},{cls:‘surf-pill’,pip:‘var(–surf-b)’,lb:`surf · ${sfC}×`}].forEach(p=>{const el=document.createElement(‘div’);el.className=’pill ’+p.cls;el.innerHTML=`<div style="width:6px;height:6px;border-radius:50%;background:${p.pip};flex-shrink:0"></div>${p.lb}`;row.appendChild(el);});
}

function buildDayControls(){
const c=document.getElementById(‘day-controls’);c.innerHTML=’’;c.appendChild(document.createElement(‘div’));
DAYS.forEach((day,i)=>{
const head=document.createElement(‘div’);head.className=‘day-head’+(workDays[i]?’ is-work’:’’);
head.innerHTML=`<div class="day-name">${day}</div><div class="toggle${workDays[i]?' on':''}" data-i="${i}"></div><div class="day-badge ${workDays[i]?'work':'off'}">${workDays[i]?'work':'off'}</div>`;
head.querySelector(’.toggle’).addEventListener(‘click’,function(){
const idx=+this.dataset.i,count=workDays.filter(Boolean).length;
if(!workDays[idx]&&count>=4){const n=document.getElementById(‘limit-note’);n.classList.add(‘show’);setTimeout(()=>n.classList.remove(‘show’),2000);return;}
workDays[idx]=!workDays[idx];
if(workDays[idx]){surfDays[idx]=false;workoutType[idx]=‘pilates’;offWorkout[idx]=null;}
else{workoutType[idx]=null;surfWorkDay[idx]=false;offWorkout[idx]=‘none’;}
save();render();
});
c.appendChild(head);
});
}

function buildGrid(){
const grid=document.getElementById(‘planner-grid’);grid.innerHTML=’’;
const scheds=DAYS.map((*,i)=>workDays[i]?workSched(i):offSched(i));
HOURS.forEach(h=>{
const tl=document.createElement(‘div’);tl.className=‘time-lbl’;tl.textContent=h;grid.appendChild(tl);
DAYS.forEach((*,i)=>{const s=scheds[i][h]||{cls:‘free’,lb:’’};const cell=document.createElement(‘div’);cell.className=’cell ’+s.cls;if(s.lb)cell.textContent=s.lb;grid.appendChild(cell);});
});
}

function buildActPanel(){
const grid=document.getElementById(‘act-grid’);grid.innerHTML=’’;
// workout row
addL(grid,‘workout’);
DAYS.forEach((_,i)=>{
const cell=document.createElement(‘div’);
if(workDays[i]){
const wt=workoutType[i];
if(wt===‘pilates’){cell.className=‘wk-cell pilates-mode’;cell.textContent=‘P’;}
else if(wt===‘strength’){cell.className=‘wk-cell strength-mode’;cell.textContent=‘S’;}
else{const atCap=countWk()>=4;cell.className=‘wk-cell inactive’;cell.style.cursor=atCap?‘not-allowed’:‘pointer’;cell.style.opacity=‘0.5’;cell.textContent=atCap?’–’:’+’;}
cell.addEventListener(‘click’,()=>{const cur=workoutType[i],next=cur===‘pilates’?‘strength’:cur===‘strength’?‘none’:‘pilates’;if(next!==‘none’&&cur===‘none’&&countWk()>=4)return;workoutType[i]=next;save();render();});
}else{
const ow=offWorkout[i];
if(ow===‘pilates’){cell.className=‘wk-cell pilates-mode’;cell.textContent=‘P’;}
else if(ow===‘strength’){cell.className=‘wk-cell strength-mode’;cell.textContent=‘S’;}
else{const atCap=countWk()>=4;cell.className=‘wk-cell inactive’;cell.style.cursor=atCap?‘not-allowed’:‘pointer’;cell.style.opacity=‘0.4’;cell.textContent=atCap?’–’:’+’;}
cell.addEventListener(‘click’,()=>{const cur=offWorkout[i],next=cur===‘none’?‘pilates’:cur===‘pilates’?‘strength’:‘none’;if(next!==‘none’&&cur===‘none’&&countWk()>=4)return;offWorkout[i]=next;save();render();});
}
grid.appendChild(cell);
});
addGap(grid);

// hot yoga row
addL(grid,‘hot yoga’);
DAYS.forEach((_,i)=>{
const isOn=yogaDays[i],yCount=yogaDays.filter(Boolean).length;
const cell=document.createElement(‘div’);cell.className=‘yoga-cell’+(isOn?’ yoga-on’:’’);
if(isOn){
const lbl=document.createElement(‘div’);lbl.className=‘yc-label’;lbl.textContent=‘✓ ✕’;
const sel=document.createElement(‘select’);
const opts=workDays[i]?YOGA_TIMES.filter(t=>HI[t]>=HI[‘6 PM’]):YOGA_TIMES;
opts.forEach(t=>{const o=document.createElement(‘option’);o.value=t;o.textContent=t;if(t===yogaTime[i])o.selected=true;sel.appendChild(o);});
sel.addEventListener(‘change’,e=>{e.stopPropagation();yogaTime[i]=e.target.value;save();render();});
sel.addEventListener(‘click’,e=>e.stopPropagation());
cell.style.cursor=‘pointer’;cell.addEventListener(‘click’,()=>{yogaDays[i]=false;save();render();});
cell.appendChild(lbl);cell.appendChild(sel);
}else if(!isOn&&yCount>=2){cell.style.opacity=’.32’;cell.style.cursor=‘not-allowed’;cell.textContent=‘max 2×’;}
else{cell.textContent=’+ add’;cell.addEventListener(‘click’,()=>{yogaDays[i]=true;save();render();});}
grid.appendChild(cell);
});
addGap(grid);

// climbing row
addL(grid,‘climbing’);
DAYS.forEach((_,i)=>{
const isOn=climbDays[i],count=climbDays.filter(Boolean).length;
const cell=document.createElement(‘div’);
if(!isOn&&count>=2){cell.className=‘opt-cell opt-locked’;cell.textContent=’–’;}
else if(isOn){
cell.style.cssText=‘height:42px;border-radius:5px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px;font-size:10px;padding:4px 3px;background:var(–climb);border:1px solid rgba(200,122,32,.55);color:var(–climb-t);cursor:pointer;font-family:'DM Mono',monospace;letter-spacing:.02em;’;
const lbl=document.createElement(‘div’);lbl.style.cssText=‘font-size:12px;line-height:1;’;lbl.textContent=‘✓ ✕’;
cell.addEventListener(‘click’,()=>{climbDays[i]=false;save();render();});
if(workDays[i]){cell.appendChild(lbl);}
else{
const sel=document.createElement(‘select’);
sel.style.cssText=‘background:#0a0d14;border:1px solid rgba(255,255,255,.15);border-radius:3px;color:var(–text2);font-family:'DM Mono',monospace;font-size:10px;cursor:pointer;outline:none;-webkit-appearance:none;text-align:center;padding:1px 3px;width:100%;max-width:62px;’;
CLIMB_TIMES.forEach(t=>{const o=document.createElement(‘option’);o.value=t;o.textContent=t;if(t===climbTime[i])o.selected=true;sel.appendChild(o);});
sel.addEventListener(‘change’,e=>{e.stopPropagation();climbTime[i]=e.target.value;save();render();});
sel.addEventListener(‘click’,e=>e.stopPropagation());
cell.appendChild(lbl);cell.appendChild(sel);
}
}else{
cell.className=‘opt-cell’;cell.textContent=’+’;
cell.addEventListener(‘click’,()=>{climbDays[i]=true;save();render();});
}
grid.appendChild(cell);
});
addGap(grid);

// surf row
addL(grid,‘surf’);
DAYS.forEach((_,i)=>{
const isWork=workDays[i],isOn=surfDays[i],isWorkSurf=surfWorkDay[i],surfable=isSurfable(i);
const totalSurf=surfDays.filter(Boolean).length+surfWorkDay.filter(Boolean).length;
const cell=document.createElement(‘div’);
if(isWork){
if(!surfable){cell.className=‘surf-cell surf-locked’;cell.textContent=’–’;}
else if(!isWorkSurf&&totalSurf>=2){cell.className=‘surf-cell surf-locked’;cell.textContent=’–’;}
else if(isWorkSurf){
cell.className=‘surf-cell surf-on’;
const lbl=document.createElement(‘div’);lbl.className=‘sc-label’;lbl.textContent=‘🤙 ✕’;
cell.style.cursor=‘pointer’;cell.addEventListener(‘click’,()=>{surfWorkDay[i]=false;save();render();});
cell.appendChild(lbl);
}else{cell.className=‘surf-cell’;cell.textContent=’+ early’;cell.addEventListener(‘click’,()=>{surfWorkDay[i]=true;save();render();});}
}else if(!surfable){cell.className=‘surf-cell surf-locked’;cell.textContent=’–’;}
else if(!isOn&&totalSurf>=2){cell.className=‘surf-cell surf-locked’;cell.textContent=’–’;}
else if(isOn){
cell.className=‘surf-cell surf-on’;
const lbl=document.createElement(‘div’);lbl.className=‘sc-label’;lbl.textContent=‘🤙 ✕’;
const sel=document.createElement(‘select’);
SURF_STARTS.forEach(t=>{const o=document.createElement(‘option’);o.value=t;o.textContent=t;if(t===surfStart[i])o.selected=true;sel.appendChild(o);});
sel.addEventListener(‘change’,e=>{e.stopPropagation();surfStart[i]=e.target.value;save();render();});
sel.addEventListener(‘click’,e=>e.stopPropagation());
cell.style.cursor=‘pointer’;cell.addEventListener(‘click’,()=>{surfDays[i]=false;save();render();});
cell.appendChild(lbl);cell.appendChild(sel);
}else{cell.className=‘surf-cell’;cell.textContent=’+’;cell.addEventListener(‘click’,()=>{surfDays[i]=true;save();render();});}
grid.appendChild(cell);
});
}

function addL(p,t){const l=document.createElement(‘div’);l.className=‘act-lbl’;l.textContent=t;p.appendChild(l);}
function addGap(p){const g=document.createElement(‘div’);g.className=‘opt-gap’;p.appendChild(g);}

function buildForecast(){
const c=document.getElementById(‘forecast-days’);c.innerHTML=’’;
const INFO={good:{wave:‘🌊’,size:‘3–4 ft’,tag:‘pumping · ≤3kt’,cls:‘surfable’},ok:{wave:’〰’,size:‘2–3 ft’,tag:‘fair to good’,cls:‘surfable ok-surf’},poor:{wave:’—’,size:‘flat / blown’,tag:‘no go’,cls:‘flat’}};
DAYS.forEach((day,i)=>{
const cond=surfFcast[i],info=INFO[cond];
const card=document.createElement(‘div’);card.className=’fday ’+info.cls;
card.innerHTML=`<div class="fd-name">${day}</div><div class="fd-wave">${info.wave}</div><div class="fd-size">${info.size}</div><div class="fd-tag">${info.tag}</div><select><option value="good" ${cond==='good'?'selected':''}>pumping</option><option value="ok" ${cond==='ok'?'selected':''}>fair to good</option><option value="poor" ${cond==='poor'?'selected':''}>no go</option></select>`;
card.querySelector(‘select’).addEventListener(‘change’,e=>{surfFcast[i]=e.target.value;if(!isSurfable(i)){surfDays[i]=false;surfWorkDay[i]=false;}save();render();});
c.appendChild(card);
});
}

function buildStats(){
const el=document.getElementById(‘stats’);el.innerHTML=’’;
const wc=workDays.filter(Boolean).length;let pilates=0,strength=0;
DAYS.forEach((*,i)=>{if(workDays[i]){if(yogaDays[i]||climbDays[i])return;if(workoutType[i]===‘pilates’)pilates++;if(workoutType[i]===‘strength’)strength++;}else{if(offWorkout[i]===‘pilates’)pilates++;if(offWorkout[i]===‘strength’)strength++;}});
const totalWk=pilates+strength,yoga=yogaDays.filter(Boolean).length;
const climbW=DAYS.filter((*,i)=>workDays[i]&&climbDays[i]).length;
const climbO=DAYS.filter((*,i)=>!workDays[i]&&climbDays[i]).length;
const surf=surfDays.filter(Boolean).length+surfWorkDay.filter(Boolean).length;
const surfGd=DAYS.filter((*,i)=>isSurfable(i)&&!workDays[i]).length;
[{l:‘Work hours’,v:`${wc*10}h`},{l:‘Days off’,v:`${7-wc}`},{l:‘Pilates sessions’,v:`${pilates}×`},{l:‘Strength sessions’,v:`${strength}×`},{l:‘Workout days’,v:`${totalWk} / 4`,warn:totalWk<3},{l:‘Hot yoga’,v:`${yoga} / 2`},{l:‘Climbing’,v:`${climbW+climbO}× (${climbW} post-work, ${climbO} off)`},{l:‘Surf sessions’,v:`${surf}×`},{l:‘Surfable days off’,v:`${surfGd}`},{l:‘Appointments’,v:`${appointments.length}`}].forEach(r=>{el.innerHTML+=`<div class="stat-row"><span class="stat-label">${r.l}</span><span class="stat-val${r.warn?' warn':''}">${r.v}</span></div>`;});
}

function buildAppointments(){
const daySel=document.getElementById(‘appt-day’);daySel.innerHTML=’’;
DAYS.forEach((d,i)=>{const o=document.createElement(‘option’);o.value=i;o.textContent=d;daySel.appendChild(o);});
const list=document.getElementById(‘appt-list’);list.innerHTML=’’;
if(appointments.length===0){const e=document.createElement(‘div’);e.style.cssText=‘font-size:11px;color:var(–text3);padding:4px 0;’;e.textContent=‘no appointments yet’;list.appendChild(e);}
else appointments.forEach((a,idx)=>{
const item=document.createElement(‘div’);item.className=‘appt-item’;
const[hh,mm]=a.time.split(’:’);const h=parseInt(hh),ampm=h>=12?‘PM’:‘AM’,h12=h%12||12;
item.innerHTML=`<span class="appt-day">${DAYS[a.day]}</span><span class="appt-time">${h12}:${mm} ${ampm}</span><span class="appt-desc" title="${a.desc}">${a.desc}</span><button class="appt-del" data-idx="${idx}">&#x2715;</button>`;
item.querySelector(’.appt-del’).addEventListener(‘click’,()=>{appointments.splice(idx,1);save();buildAppointments();buildGrid();buildStats();});
list.appendChild(item);
});
}

function getWeekLabel(off){
const now=new Date(),d=now.getDay(),diff=now.getDate()-d+(d===0?-6:1);
const mon=new Date(now);mon.setDate(diff+off*7);const sun=new Date(mon);sun.setDate(mon.getDate()+6);
const fmt=x=>x.toLocaleDateString(‘en-US’,{month:‘short’,day:‘numeric’});return fmt(mon)+’ – ’+fmt(sun);
}

function save(){
try{
localStorage.setItem(‘wp7_work’,JSON.stringify(workDays));localStorage.setItem(‘wp7_wtype’,JSON.stringify(workoutType));
localStorage.setItem(‘wp7_owt’,JSON.stringify(offWorkout));localStorage.setItem(‘wp7_yoga’,JSON.stringify(yogaDays));
localStorage.setItem(‘wp7_ytime’,JSON.stringify(yogaTime));localStorage.setItem(‘wp7_climb’,JSON.stringify(climbDays));
localStorage.setItem(‘wp7_ctime’,JSON.stringify(climbTime));localStorage.setItem(‘wp7_surf’,JSON.stringify(surfDays));
localStorage.setItem(‘wp7_swd’,JSON.stringify(surfWorkDay));localStorage.setItem(‘wp7_ss’,JSON.stringify(surfStart));
localStorage.setItem(‘wp7_fcast’,JSON.stringify(surfFcast));localStorage.setItem(‘wp7_appts’,JSON.stringify(appointments));
localStorage.setItem(‘wp7_notes’,notes);
}catch(e){}
}

function load(){
try{
const p=k=>{const v=localStorage.getItem(k);return v?JSON.parse(v):null;};
workDays=p(‘wp7_work’)||workDays;workoutType=p(‘wp7_wtype’)||workoutType;offWorkout=p(‘wp7_owt’)||offWorkout;
yogaDays=p(‘wp7_yoga’)||yogaDays;yogaTime=p(‘wp7_ytime’)||yogaTime;climbDays=p(‘wp7_climb’)||climbDays;
climbTime=p(‘wp7_ctime’)||climbTime;surfDays=p(‘wp7_surf’)||surfDays;surfWorkDay=p(‘wp7_swd’)||surfWorkDay;
surfStart=p(‘wp7_ss’)||surfStart;surfFcast=p(‘wp7_fcast’)||surfFcast;appointments=p(‘wp7_appts’)||appointments;
notes=localStorage.getItem(‘wp7_notes’)||’’;
}catch(e){}
}

function render(){buildHeader();buildSummary();buildDayControls();buildGrid();buildActPanel();buildForecast();buildStats();buildAppointments();document.getElementById(‘notes-area’).value=notes;}

document.getElementById(‘prev-week’).addEventListener(‘click’,()=>{weekOff–;render();});
document.getElementById(‘next-week’).addEventListener(‘click’,()=>{weekOff++;render();});
document.getElementById(‘reset-btn’).addEventListener(‘click’,()=>{
workDays=[true,true,true,true,false,false,false];workoutType=[‘pilates’,‘pilates’,‘pilates’,‘none’,null,null,null];
offWorkout=[null,null,null,null,‘none’,‘none’,‘none’];yogaDays=Array(7).fill(false);yogaTime=Array(7).fill(‘7 AM’);
climbDays=Array(7).fill(false);climbTime=Array(7).fill(‘10 AM’);surfDays=Array(7).fill(false);surfWorkDay=Array(7).fill(false);
surfStart=Array(7).fill(‘7 AM’);surfFcast=Array(7).fill(‘ok’);appointments=[];notes=’’;save();render();
});
document.getElementById(‘appt-add-btn’).addEventListener(‘click’,()=>{
const day=+document.getElementById(‘appt-day’).value,time=document.getElementById(‘appt-time’).value,desc=document.getElementById(‘appt-desc’).value.trim();
if(!desc)return;appointments.push({day,time,desc});appointments.sort((a,b)=>a.day-b.day||a.time.localeCompare(b.time));
document.getElementById(‘appt-desc’).value=’’;save();buildAppointments();buildGrid();buildStats();
});
document.getElementById(‘notes-area’).addEventListener(‘input’,e=>{notes=e.target.value;save();});
load();render();

// register inline service worker for offline support
if(‘serviceWorker’ in navigator){
const swCode=`const CACHE='weekplan-v1'; const ASSETS=[ 'https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;500;600;700&display=swap' ]; self.addEventListener('install',e=>{e.waitUntil(caches.open(CACHE).then(c=>c.addAll(ASSETS).catch(()=>{})));self.skipWaiting();}); self.addEventListener('activate',e=>{e.waitUntil(caches.keys().then(keys=>Promise.all(keys.filter(k=>k!==CACHE).map(k=>caches.delete(k)))));}); self.addEventListener('fetch',e=>{e.respondWith(caches.match(e.request).then(r=>r||fetch(e.request).catch(()=>new Response('',{status:408}))));});`;
const blob=new Blob([swCode],{type:‘application/javascript’});
const url=URL.createObjectURL(blob);
navigator.serviceWorker.register(url).catch(()=>{});
}
</script>

</body>
</html>
