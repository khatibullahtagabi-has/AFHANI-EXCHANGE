<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="USD and AFN exchange-rate converter">
<title>Afghani Exchange | Sarai Shahzada</title>
<style>
:root{--bg:#08111f;--panel:#101d30;--panel2:#14243a;--text:#f2f6ff;--muted:#9fb0c8;--accent:#52e0b1;--line:#263951;--gold:#ffd166}
*{box-sizing:border-box}body{margin:0;min-height:100vh;font-family:Arial,"Noto Sans Arabic",sans-serif;background:radial-gradient(ellipse at top,#163354 0%,var(--bg) 58%);color:var(--text);display:flex;justify-content:center;align-items:center;padding:22px}main{width:min(100%,780px)}header{text-align:center;margin-bottom:22px}.logo{width:64px;height:64px;margin:0 auto 12px;border-radius:20px;display:grid;place-items:center;background:linear-gradient(135deg,var(--accent),#39a6ff);color:#061321;font-size:24px;font-weight:800;direction:ltr}h1{font-size:clamp(27px,5vw,40px);margin:0 0 8px}.subtitle{color:var(--muted);margin:0;font-size:15px}.card{background:rgba(16,29,48,.96);border:1px solid var(--line);border-radius:24px;padding:clamp(18px,4vw,32px);box-shadow:0 24px 80px #0005}.source{text-align:center;color:var(--muted);font-size:13px;margin-bottom:15px}.source a{color:var(--accent)}.rates{display:grid;grid-template-columns:1fr 1fr;gap:12px}.ratebox{background:var(--panel2);border:1px solid var(--line);border-radius:16px;padding:18px;text-align:center}.ratebox span{display:block;color:var(--muted);font-size:14px}.ratebox strong{display:block;font-size:clamp(28px,6vw,42px);direction:ltr;margin-top:8px}.buy strong{color:var(--accent)}.sell strong{color:var(--gold)}.status{text-align:center;font-size:13px;color:var(--muted);min-height:38px;margin:14px 0 10px;line-height:1.7}hr{border:0;border-top:1px solid var(--line);margin:20px 0}label{display:block;color:var(--muted);font-size:14px;margin-bottom:8px}select,input{width:100%;padding:14px;border:1px solid #36506e;border-radius:12px;background:#091525;color:var(--text);font-size:18px;outline:none;direction:ltr}select{direction:rtl}input:focus,select:focus{border-color:var(--accent)}.formgrid{display:grid;grid-template-columns:1fr 1fr;gap:14px}.output{min-height:54px;border:1px solid var(--line);border-radius:12px;background:var(--panel2);padding:14px;display:flex;align-items:center;justify-content:space-between;gap:8px;font-size:22px;font-weight:700;direction:ltr}.output span{font-size:13px;color:var(--muted)}button{margin-top:16px;width:100%;padding:14px;border:0;border-radius:12px;background:var(--accent);color:#061321;font-size:16px;font-weight:800;cursor:pointer}button:disabled{opacity:.65;cursor:wait}.note{margin:16px 0 0;color:var(--muted);font-size:12px;line-height:1.9;text-align:center}footer{text-align:center;color:#778ba6;font-size:12px;margin-top:16px;line-height:1.8}.smalllink{color:var(--muted)}@media(max-width:560px){body{padding:12px}.rates,.formgrid{grid-template-columns:1fr}.card{border-radius:18px}}
</style></head>
<body><main>
<header><div class="logo">$ ⇄ ؋</div><h1>Afghani Exchange</h1><p class="subtitle">US Dollar and Afghan Afghani Market Rates</p></header>
<section class="card">

<div class="rates"><div class="ratebox buy"><span>USD Buy Rate (exchange buys from you)</span><strong id="buyRate">—</strong><span>AFN / 1 USD</span></div><div class="ratebox sell"><span>USD Sell Rate (exchange sells to you)</span><strong id="sellRate">—</strong><span>AFN / 1 USD</span></div></div>
<hr>
<div class="formgrid"><div><label for="direction">Conversion direction</label><select id="direction"><option value="usd-afn">USD → AFN</option><option value="afn-usd">AFN → USD</option></select></div><div><label for="amount">Enter amount</label><input id="amount" type="number" min="0" step="any" value="1" inputmode="decimal"></div></div>
<div style="margin-top:14px"><label>Result</label><div class="output"><strong id="result">—</strong><span id="unit">AFN</span></div></div>
<button id="refresh" type="button">↻ Refresh rates now</button>

</section>
</main>
<script>
const SARAFI_URL='https://sarafi.af/fa/exchange-rates/sarai-shahzada';
const PROXY_URL='https://api.allorigins.win/raw?url='+encodeURIComponent(SARAFI_URL);
const buyEl=document.getElementById('buyRate'), sellEl=document.getElementById('sellRate');
const amountEl=document.getElementById('amount'), directionEl=document.getElementById('direction'), resultEl=document.getElementById('result'), unitEl=document.getElementById('unit'), refreshBtn=document.getElementById('refresh');
let buy=null,sell=null,loading=false;
const numberFmt=new Intl.NumberFormat('en-US',{minimumFractionDigits:2,maximumFractionDigits:4});
function parseNumber(s){if(!s)return NaN;const normalized=String(s).replace(/[۰-۹]/g,d=>'۰۱۲۳۴۵۶۷۸۹'.indexOf(d)).replace(/[٠-٩]/g,d=>'٠١٢٣٤٥٦٧٨٩'.indexOf(d)).replace(/[٬،]/g,'').replace(/٫/g,'.').replace(/,/g,'');return Number(normalized.replace(/[^0-9.\-]/g,''));}
function convert(){const n=Number(amountEl.value);if(!Number.isFinite(n)||n<0||buy===null||sell===null){resultEl.textContent='—';return;}if(directionEl.value==='usd-afn'){resultEl.textContent=numberFmt.format(n*buy);unitEl.textContent='AFN ؋';}else{resultEl.textContent=numberFmt.format(n/sell);unitEl.textContent='USD $';}}
function getRates(doc){
 let rows=[...doc.querySelectorAll('tr')];
 for(const row of rows){const cells=[...row.querySelectorAll('th,td')].map(x=>x.textContent.trim());const first=(cells[0]||'').toUpperCase();if((first.includes('USD')||first.includes('دالر آمریکا')||first.includes('دالر امريکا'))&&cells.length>=3){const b=parseNumber(cells[1]),s=parseNumber(cells[2]);if(Number.isFinite(b)&&Number.isFinite(s)&&b>0&&s>0)return {buy:b,sell:s};}}
 const text=doc.body?doc.body.innerText:doc.documentElement.innerText;
 const m=text.match(/USD\s*[-–]\s*دالر آمریکا\s*([0-9]+(?:\.[0-9]+)?)\s*([0-9]+(?:\.[0-9]+)?)/i);
 if(m)return {buy:Number(m[1]),sell:Number(m[2])};
 throw new Error('USD buy/sell row not found');
}
async function loadRates(){if(loading)return;loading=true;refreshBtn.disabled=true;refreshBtn.textContent='Refreshing rates…';
 try{const r=await fetch(PROXY_URL,{cache:'no-store'});if(!r.ok)throw new Error('HTTP '+r.status);const html=await r.text();const doc=new DOMParser().parseFromString(html,'text/html');const rates=getRates(doc);buy=rates.buy;sell=rates.sell;buyEl.textContent=numberFmt.format(buy);sellEl.textContent=numberFmt.format(sell);convert();}
 catch(e){if(buy===null){buyEl.textContent='Unavailable';sellEl.textContent='Unavailable';}}
 finally{loading=false;refreshBtn.disabled=false;refreshBtn.textContent='↻ Refresh rates now';}}
amountEl.addEventListener('input',convert);directionEl.addEventListener('change',convert);refreshBtn.addEventListener('click',loadRates);loadRates();setInterval(loadRates,10000);
</script></body></html>
