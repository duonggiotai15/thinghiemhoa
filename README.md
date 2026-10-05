<!doctype html>
<html lang="vi"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Phòng thí nghiệm Hóa học ảo</title>
<link href="https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:wght@400;600;700&display=swap" rel="stylesheet">
<style>
:root{color-scheme:light;--ink:#1c2b3a;--mut:#6b7c8d;--ac:#1e88e5;--ln:#dde5ee;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:#f4f7fb;color:var(--ink);font:14px/1.45 'Be Vietnam Pro',system-ui,sans-serif;min-height:100%}
header{display:flex;flex-wrap:wrap;gap:10px;align-items:center;justify-content:space-between;padding:12px 18px;background:#fff;border-bottom:1px solid var(--ln)}
h1{font-size:18px;margin:0;letter-spacing:.06em}
button,select,input[type=search]{font:inherit}
button{background:#fff;border:1px solid var(--ln);border-radius:10px;padding:9px 14px;cursor:pointer;color:var(--ink);transition:.15s}
button:hover{border-color:var(--ac);transform:translateY(-1px)}
button.on{background:var(--ac);border-color:var(--ac);color:#fff}
main{display:grid;grid-template-columns:190px minmax(0,1fr) 250px;gap:14px;padding:14px 18px;max-width:1280px;margin:auto}
aside{background:#fff;border:1px solid var(--ln);border-radius:14px;padding:12px}
h4{margin:6px 0;font-size:11px;color:var(--mut);text-transform:uppercase;letter-spacing:.08em}
#liqs{display:grid;grid-template-columns:repeat(3,1fr);gap:6px}
.chip{touch-action:none;user-select:none;cursor:grab;text-align:center;font-size:10px;line-height:1.1;padding:4px 2px;border-radius:10px;border:1px solid transparent;transition:.15s}
.chip:hover{background:#eef4fb}.chip svg{width:30px;height:40px;display:block;margin:0 auto 2px}
.ghost{position:fixed;z-index:50;pointer-events:none;box-shadow:0 12px 24px #0003;background:#fff;transition:none}
.rackw{display:flex;gap:4px;align-items:center}.rackw button{padding:6px 8px}
#rack{display:flex;gap:6px;overflow-x:auto;scroll-behavior:smooth;padding:6px 2px;scrollbar-width:none;flex:1}
.mchip{flex:0 0 46px;height:46px;border-radius:9px;display:grid;place-items:center;font-weight:700;color:#2a3440;cursor:grab;touch-action:none;user-select:none;border:2px solid #fff;box-shadow:0 1px 4px #0003,inset 0 0 8px #fff8}
.mchip.sel{box-shadow:0 0 0 3px #1e88e544,0 0 14px #1e88e5}
#minfo{font-size:12px;min-height:70px;color:var(--mut)}#minfo b{color:var(--ink)}
#stage{display:flex;flex-direction:column;gap:10px;min-width:0}
#cvw{position:relative;background:linear-gradient(#fff,#eaf1f9);border:1px solid var(--ln);border-radius:16px;overflow:hidden;transition:box-shadow .2s}
#stage.drop #cvw{box-shadow:0 0 0 3px var(--ac),0 0 24px #1e88e566}
canvas{display:block;width:100%;max-height:64vh;margin:auto;aspect-ratio:520/560;touch-action:none}
#toast{position:absolute;left:10px;right:10px;top:10px;text-align:center;font-size:12px;background:#1c2b3add;color:#fff;border-radius:10px;padding:8px;opacity:0;transition:.3s;pointer-events:none}
#toast.show{opacity:1}
#ctl{display:flex;flex-wrap:wrap;gap:8px 12px;align-items:center;background:#fff;border:1px solid var(--ln);border-radius:14px;padding:10px 12px}
.seg{display:flex}.seg button{border-radius:0;padding:8px 11px}.seg button:first-child{border-radius:10px 0 0 10px}.seg button:last-child{border-radius:0 10px 10px 0}
label.t{display:flex;align-items:center;gap:6px;cursor:pointer}
input[type=range]{accent-color:var(--ac)}
#info{font-size:13px}#info h3{margin:0 0 6px;font-size:13px;letter-spacing:.08em}
#info .k{color:var(--mut);font-size:11px;text-transform:uppercase;margin-top:8px;letter-spacing:.06em}
.bar{height:8px;background:#e6edf5;border-radius:6px;overflow:hidden}.bar i{display:block;height:100%;background:var(--ac);transition:width .3s}
.ph{background:linear-gradient(90deg,#e53935,#fb8c00,#fdd835,#43a047,#1e88e5,#5e35b1);position:relative;height:8px;border-radius:6px}.ph i{position:absolute;top:-3px;width:4px;height:14px;background:#1c2b3a;border-radius:2px;transition:left .3s}
.eq{font-weight:700;color:#0b5cab}.warn{color:#b3261e;font-size:12px}
footer{text-align:center;padding:10px 0 16px;font-size:12px;color:#7a8a9a;letter-spacing:.03em}
.pop{position:fixed;inset:0;background:#1c2b3a66;display:grid;place-items:center;z-index:60;padding:14px}.pop[hidden]{display:none}
.pop>div{background:#fff;border-radius:16px;padding:16px;max-width:520px;width:100%;max-height:80vh;overflow:auto}
#mlist button{display:block;width:100%;text-align:left;margin:4px 0}#mlist small{color:var(--mut)}
@media(max-width:900px){main{grid-template-columns:1fr;padding:10px}#liqs{grid-template-columns:repeat(6,1fr)}}
</style></head><body>
<header><h1>PHÒNG THÍ NGHIỆM HÓA HỌC</h1>
<nav style="display:flex;gap:8px;flex-wrap:wrap"><button id="bMenu">🧫 Chọn thí nghiệm</button><button id="bGuide">❔ Hướng dẫn</button><button id="bReset">↺ Reset</button></nav></header>
<main>
<aside><h4>Hóa chất</h4><div id="liqs"></div><h4 style="margin-top:12px">Bệ kim loại</h4>
<div class="rackw"><button id="mL">‹</button><div id="rack"></div><button id="mR">›</button></div><div id="minfo">Chạm hoặc kéo một kim loại vào dụng cụ.</div></aside>
<section id="stage"><div id="cvw"><canvas id="cv" width="520" height="560"></canvas><div id="toast"></div></div>
<div id="ctl">
<div class="seg" id="vsel"><button data-v="tube" class="on">Ống nghiệm</button><button data-v="beaker">Cốc</button><button data-v="flask">Bình tam giác</button></div>
<div class="seg" id="lsel"><button data-l="0">Cơ bản</button><button data-l="1" class="on">Học tập</button><button data-l="2">Phân tử</button></div>
<label class="t">🌡 <input id="tmp" type="range" min="0" max="300" value="25"><b id="tv">25°C</b></label>
<button id="bLamp">🔥 Bật đèn cồn</button>
<label class="t">Cường độ <input id="int" type="range" min="1" max="3" value="2"></label>
<label class="t"><input id="cMol" type="checkbox">👁 Phân tử</label>
<label class="t"><input id="cGas" type="checkbox" checked>Khí</label>
<button id="bSnd" class="on">🔊 Âm thanh</button>
<button id="bFree" class="on">🧪 Phòng thí nghiệm tự do</button>
</div></section>
<aside id="info"></aside>
</main>
<footer>Made by Phạm Bá Dương</footer>
<div class="pop" id="menu" hidden><div><input id="q" type="search" placeholder="🔎 Tìm kiếm phản ứng..." style="width:100%;padding:9px;border:1px solid var(--ln);border-radius:10px"><select id="fc" style="width:100%;margin:8px 0;padding:8px"></select><div id="mlist"></div></div></div>
<div class="pop" id="guide" hidden><div><h3>Hướng dẫn</h3><p>1. Kéo (hoặc chạm) hóa chất / kim loại vào dụng cụ ở giữa.<br>2. Dùng thanh nhiệt độ hoặc đèn cồn để đun; xem hiện tượng, khí, kết tủa, đổi màu.<br>3. Xem phương trình và giải thích ở bảng bên phải (chế độ Học tập).<br>4. «Chọn thí nghiệm» để lấy bộ hóa chất gợi ý; «Phòng thí nghiệm tự do» để tự trộn — hệ thống tự nhận diện phản ứng.</p><p class="warn">Đây là mô phỏng giáo dục. Không tự thực hiện thí nghiệm nguy hiểm ngoài phòng thí nghiệm được giám sát.</p><button onclick="this.closest('.pop').hidden=true">Đóng</button></div></div>
<script>
const $=s=>document.querySelector(s);
/* ===== DỮ LIỆU (tách khỏi giao diện) ===== */
// k: a=axit b=bazơ i=chỉ thị o=lớp hữu cơ không tan | hz: cảnh báo
const L={
h2o:{n:'Nước',f:'H₂O',c:[140,195,235,.3]},
hcl:{n:'HCl',f:'HCl',c:[215,232,242,.25],k:'a',ion:['H⁺','Cl⁻'],hz:'Ăn mòn'},
h2so4:{n:'H₂SO₄',f:'H₂SO₄',c:[215,232,242,.25],k:'a',ion:['H⁺','SO₄²⁻'],hz:'Ăn mòn'},
hno3:{n:'HNO₃',f:'HNO₃',c:[215,232,242,.25],k:'a',ion:['H⁺','NO₃⁻'],hz:'Ăn mòn, oxi hóa'},
naoh:{n:'NaOH',f:'NaOH',c:[215,232,242,.25],k:'b',ion:['Na⁺','OH⁻'],hz:'Ăn mòn'},
nh3:{n:'NH₃',f:'NH₃',c:[215,232,242,.25],k:'b',hz:'Độc'},
ch3nh2:{n:'CH₃NH₂',f:'CH₃NH₂',c:[215,232,242,.25],k:'b',hz:'Độc, dễ cháy'},
agno3:{n:'AgNO₃',f:'AgNO₃',c:[215,232,242,.25],ion:['Ag⁺','NO₃⁻'],hz:'Oxi hóa'},
nacl:{n:'NaCl',f:'NaCl',c:[215,232,242,.25],ion:['Na⁺','Cl⁻']},
bacl2:{n:'BaCl₂',f:'BaCl₂',c:[215,232,242,.25],ion:['Ba²⁺','Cl⁻'],hz:'Độc'},
cuso4:{n:'CuSO₄',f:'CuSO₄',c:[40,130,225,.55],ion:['Cu²⁺','SO₄²⁻']},
fecl3:{n:'FeCl₃',f:'FeCl₃',c:[225,165,40,.6],ion:['Fe³⁺','Cl⁻']},
quy:{n:'Quỳ tím',f:'Quỳ',c:[150,80,190,.4],k:'i'},
phph:{n:'Phenolphtalein',f:'PP',c:[225,235,240,.2],k:'i'},
mo:{n:'Metyl da cam',f:'MO',c:[245,150,40,.6],k:'i'},
glucose:{n:'Glucozơ',f:'C₆H₁₂O₆',c:[225,235,240,.25]},
sacc:{n:'Saccarozơ',f:'C₁₂H₂₂O₁₁',c:[225,235,240,.25]},
starch:{n:'Hồ tinh bột',f:'(C₆H₁₀O₅)n',c:[238,236,225,.55]},
i2:{n:'Iot (I₂)',f:'I₂',c:[175,100,30,.55]},
tollens:{n:'Tollens',f:'[Ag(NH₃)₂]⁺',c:[225,230,236,.3],hz:'Độc'},
protein:{n:'Protein',f:'Lòng trắng',c:[245,240,205,.45]},
enzyme:{n:'Men',f:'Enzym',c:[230,205,150,.4]},
oil:{n:'Dầu ăn',f:'Chất béo',c:[240,200,45,.9],k:'o'},
ester:{n:'Etyl axetat',f:'CH₃COOC₂H₅',c:[235,235,215,.7],k:'o',hz:'Dễ cháy'}};
const M={
Li:{n:'Liti',act:'Mạnh',w:'Phản ứng êm, nổi trên nước',col:[205,208,214],fl:1,hz:'Dễ cháy'},
Na:{n:'Natri',act:'Rất mạnh',w:'Chạy trên mặt nước, có thể bắt lửa',col:[222,224,230],fl:1,hz:'Dễ cháy, ăn mòn'},
K:{n:'Kali',act:'Rất mạnh',w:'Phản ứng mãnh liệt, bốc cháy',col:[196,192,212],fl:1,hz:'Dễ cháy, ăn mòn'},
Mg:{n:'Magie',act:'Trung bình',w:'Rất chậm ở nhiệt độ thường, nhanh hơn khi đun',col:[210,214,220]},
Ca:{n:'Canxi',act:'Mạnh',w:'Chìm, sủi bọt, nước đục nhẹ',col:[185,187,190]},
Al:{n:'Nhôm',act:'Trung bình',w:'Lớp Al₂O₃ bảo vệ — gần như không phản ứng',col:[200,206,214]},
Zn:{n:'Kẽm',act:'Trung bình',w:'Không phản ứng đáng kể với nước',col:[150,156,162]},
Fe:{n:'Sắt',act:'Trung bình',w:'Không phản ứng đáng kể với nước lạnh',col:[110,114,122]},
Cu:{n:'Đồng',act:'Rất thấp',w:'Không phản ứng với nước',col:[205,115,70]},
Cr:{n:'Crom',act:'Thấp',w:'Không phản ứng đáng kể với nước',col:[170,180,190]}};
/* Cấu trúc phản ứng: r=chất tham gia, rate=tốc độ/giây ở 25°C, minT=cần đun, opt=[nhiệt tối ưu, độ rộng],
   gas, pre=[tên,màu], col=màu dung dịch sau, heat=tỏa nhiệt, fl=lửa, fadeT=mất màu khi nóng hơn, mirror, layer */
const RX=[];const add=o=>RX.push(o);
const MW=(m,o)=>add({id:m+'_h2o',cat:'Kim loại',type:'Oxi hóa – khử',name:m+' + nước',r:[m,'h2o'],...o});
MW('Li',{rate:.05,gas:'H₂',heat:1,eq:'2Li + 2H₂O → 2LiOH + H₂↑',ph:'Li nổi trên mặt nước, sủi bọt khí H₂ nhỏ, phản ứng êm.',ex:'Li khử H₂O tạo LiOH và khí H₂; phản ứng tỏa nhiệt.'});
MW('Na',{rate:.12,gas:'H₂',heat:1,fl:1,eq:'2Na + 2H₂O → 2NaOH + H₂↑',ph:'Na nổi, chạy trên mặt nước, nhiều bọt khí, nhỏ dần, có thể phát lửa nhỏ.',ex:'Na phản ứng mạnh với nước tạo NaOH và H₂. Phản ứng tỏa nhiều nhiệt nên có thể làm khí H₂ bốc cháy.',warn:'Kim loại kiềm rất nguy hiểm.'});
MW('K',{rate:.25,gas:'H₂',heat:1,fl:1,eq:'2K + 2H₂O → 2KOH + H₂↑',ph:'K chạy rất nhanh, sủi bọt mạnh, ngọn lửa xuất hiện, tan nhanh hơn Na.',ex:'K hoạt động mạnh hơn Na nên phản ứng mãnh liệt hơn.',warn:'Kim loại kiềm rất nguy hiểm.'});
MW('Mg',{rate:.004,ts:12,cap:80,gas:'H₂',heat:1,eq:'Mg + 2H₂O → Mg(OH)₂ + H₂↑',eqHot:[90,'Mg + H₂O(hơi) → MgO + H₂↑'],ph:'Rất ít bọt khí ở nhiệt độ thường; đun nóng thì bọt khí nhiều hơn.',ex:'Mg phản ứng chậm với nước lạnh; tăng nhiệt độ làm tăng tốc độ phản ứng.'});
MW('Ca',{rate:.035,gas:'H₂',heat:1,pre:['Ca(OH)₂',[245,245,245]],eq:'Ca + 2H₂O → Ca(OH)₂ + H₂↑',ph:'Ca chìm, sủi bọt khí; dung dịch đục nhẹ do Ca(OH)₂ ít tan.',ex:'Ca phản ứng với nước tạo Ca(OH)₂ ít tan và khí H₂.'});
[['Al','Lớp Al₂O₃ bảo vệ làm phản ứng bị hạn chế.'],['Fe','Không có hiện tượng rõ rệt ở điều kiện thường.'],['Cu','Cu không phản ứng đáng kể với nước ở điều kiện thường.'],['Zn','Zn không phản ứng đáng kể với nước ở điều kiện thường.'],['Cr','Cr không phản ứng đáng kể với nước ở điều kiện thường.']].forEach(([m,t])=>MW(m,{rate:0,none:t,eq:'Không phản ứng',ph:t,ex:t}));
[['Mg',.1,'Mg + 2HCl → MgCl₂ + H₂↑'],['Zn',.05,'Zn + 2HCl → ZnCl₂ + H₂↑'],['Fe',.025,'Fe + 2HCl → FeCl₂ + H₂↑'],['Al',.04,'2Al + 6HCl → 2AlCl₃ + 3H₂↑']].forEach(([m,rt,eq])=>add({id:m+'_hcl',cat:'Axit – Bazơ',type:'Oxi hóa – khử',name:m+' + HCl',r:[m,'hcl'],rate:rt,gas:'H₂',heat:1,eq,ph:'Kim loại tan dần, sủi bọt khí H₂.',ex:'Kim loại đứng trước H trong dãy hoạt động hóa học khử H⁺ của axit tạo khí H₂.'}));
add({id:'fe_hno3',cat:'Kim loại',type:'Oxi hóa – khử',name:'Fe + HNO₃',r:['Fe','hno3'],rate:.03,gas:'NO',col:[225,170,60,.5],heat:1,eq:'Fe + 4HNO₃ → Fe(NO₃)₃ + NO↑ + 2H₂O',ph:'Sắt tan dần, dung dịch vàng nâu, khí NO thoát ra (hóa nâu trong không khí).',ex:'HNO₃ loãng oxi hóa Fe lên Fe³⁺ và bị khử thành NO.',warn:'Axit nitric và khí NOx độc, ăn mòn.'});
const PRE=(id,name,r,pre,eq,ph,ex)=>add({id,cat:'Kết tủa',type:'Tạo kết tủa',name,r,rate:.3,pre,eq,ph,ex});
PRE('agcl','AgCl',['agno3','nacl'],['AgCl',[250,250,250]],'AgNO₃ + NaCl → AgCl↓ + NaNO₃','Dung dịch trong, thêm NaCl xuất hiện kết tủa trắng rồi lắng xuống đáy.','Ion Ag⁺ kết hợp Cl⁻ tạo AgCl không tan.');
PRE('cuoh2','Cu(OH)₂',['cuso4','naoh'],['Cu(OH)₂',[70,140,235]],'CuSO₄ + 2NaOH → Cu(OH)₂↓ + Na₂SO₄','Kết tủa xanh lam xuất hiện từ từ rồi lắng xuống.','Cu²⁺ + 2OH⁻ → Cu(OH)₂↓ (xanh lam).');
PRE('feoh3','Fe(OH)₃',['fecl3','naoh'],['Fe(OH)₃',[150,60,30]],'FeCl₃ + 3NaOH → Fe(OH)₃↓ + 3NaCl','Kết tủa nâu đỏ xuất hiện, kết tụ thành cụm rồi lắng.','Fe³⁺ + 3OH⁻ → Fe(OH)₃↓ (nâu đỏ).');
PRE('baso4','BaSO₄',['bacl2','h2so4'],['BaSO₄',[250,250,250]],'BaCl₂ + H₂SO₄ → BaSO₄↓ + 2HCl','Xuất hiện kết tủa trắng BaSO₄ không tan trong axit.','Ba²⁺ + SO₄²⁻ → BaSO₄↓.');
PRE('feoh3b','Fe(OH)₃ (amin)',['fecl3','ch3nh2'],['Fe(OH)₃',[150,60,30]],'3CH₃NH₂ + 3H₂O + FeCl₃ → Fe(OH)₃↓ + 3CH₃NH₃Cl','Xuất hiện kết tủa nâu đỏ Fe(OH)₃, lắng xuống.','Metylamin là bazơ, làm kết tủa hiđroxit của Fe³⁺.');
['hcl','h2so4','hno3'].forEach(a=>add({id:'neut_'+a,cat:'Axit – Bazơ',type:'Trung hòa',name:'Trung hòa '+L[a].n+' + NaOH',r:[a,'naoh'],rate:.4,heat:1,eq:a=='h2so4'?'H₂SO₄ + 2NaOH → Na₂SO₄ + 2H₂O':a=='hcl'?'HCl + NaOH → NaCl + H₂O':'HNO₃ + NaOH → NaNO₃ + H₂O',ph:'Hai dung dịch trộn lẫn, nhiệt độ tăng nhẹ; chỉ thị đổi màu theo pH.',ex:'H⁺ + OH⁻ → H₂O; phản ứng tỏa nhiệt, pH tiến về 7.'}));
add({id:'ch3nh2_hcl',cat:'Amin',type:'Axit – bazơ',name:'Metylamin + HCl',r:['ch3nh2','hcl'],rate:.4,heat:1,eq:'CH₃NH₂ + HCl → CH₃NH₃Cl',ph:'Dung dịch ấm lên, tạo muối metylamoni clorua tan.',ex:'Nhóm –NH₂ nhận proton H⁺ từ HCl tạo muối.'});
add({id:'starch_i2',cat:'Carbohydrate',type:'Nhận biết',name:'Tinh bột + I₂',r:['starch','i2'],rate:.12,col:[25,25,95,.85],fadeT:60,eq:'Tinh bột + I₂ → hợp chất xanh tím',ph:'Màu xanh tím/xanh đen xuất hiện dần. Đun nóng màu mất, để nguội màu hiện lại.',ex:'I₂ chui vào lòng xoắn của amilozơ tạo hợp chất màu xanh tím; nhiệt làm mở xoắn nên mất màu.'});
add({id:'glu_tollens',cat:'Carbohydrate',type:'Oxi hóa – khử',name:'Glucozơ + Tollens (tráng bạc)',r:['glucose','tollens'],rate:.08,minT:40,mirror:1,col:[190,195,200,.35],eq:'C₅H₁₁O₅CHO + 2[Ag(NH₃)₂]OH → C₅H₁₁O₅COONH₄ + 2Ag↓ + 3NH₃ + H₂O',ph:'Đun nhẹ (≥40°C): lớp bạc sáng bám lên thành ống nghiệm.',ex:'Glucozơ có nhóm –CHO nên khử Ag⁺ thành Ag (phản ứng tráng bạc).',note:'Cần đun nhẹ ≥ 40°C'});
add({id:'glu_cu',cat:'Carbohydrate',type:'Tạo phức',name:'Glucozơ + Cu(OH)₂',r:['cuso4','naoh','glucose'],rate:.15,col:[25,95,210,.75],eq:'2C₆H₁₂O₆ + Cu(OH)₂ → (C₆H₁₁O₆)₂Cu + 2H₂O',ph:'Cu(OH)₂ xanh lam tan, tạo dung dịch xanh lam đặc trưng.',ex:'Glucozơ có nhiều nhóm –OH kề nhau nên hòa tan Cu(OH)₂ tạo phức xanh lam.'});
add({id:'sac_cu',cat:'Carbohydrate',type:'Tạo phức',name:'Saccarozơ + Cu(OH)₂',r:['cuso4','naoh','sacc'],rate:.15,col:[25,95,210,.75],eq:'2C₁₂H₂₂O₁₁ + Cu(OH)₂ → (C₁₂H₂₁O₁₁)₂Cu + 2H₂O',ph:'Kết tủa xanh tan thành dung dịch xanh lam.',ex:'Saccarozơ có các nhóm –OH kề nhau tạo phức tan với Cu(OH)₂.'});
add({id:'sac_hyd',cat:'Carbohydrate',type:'Thủy phân',name:'Thủy phân saccarozơ',r:['sacc','h2so4'],rate:.04,minT:70,col:[250,235,190,.35],eq:'C₁₂H₂₂O₁₁ + H₂O → C₆H₁₂O₆ (glucozơ) + C₆H₁₂O₆ (fructozơ)',ph:'Đun nóng với axit, dung dịch chuyển nhẹ sang vàng nhạt.',ex:'Axit xúc tác thủy phân saccarozơ thành glucozơ và fructozơ.'});
add({id:'ferment',cat:'Carbohydrate',type:'Lên men',name:'Lên men glucozơ',r:['glucose','enzyme'],rate:.08,opt:[33,6],gas:'CO₂',eq:'C₆H₁₂O₆ → 2C₂H₅OH + 2CO₂↑',ph:'Bọt khí CO₂ tăng dần ở khoảng 30–35°C; quá lạnh hoặc quá nóng thì chậm lại.',ex:'Enzym hoạt động tốt nhất ở nhiệt độ thích hợp; nóng quá enzym bị biến tính.'});
add({id:'ester_hyd',cat:'Ester – Lipid',type:'Thủy phân',name:'Thủy phân ester (axit)',r:['ester','h2so4'],rate:.04,minT:60,layerFade:.5,eq:'CH₃COOC₂H₅ + H₂O ⇌ CH₃COOH + C₂H₅OH',ph:'Đun nóng: lớp ester mỏng dần nhưng không biến mất hoàn toàn (thuận nghịch).',ex:'Phản ứng thuận nghịch, cần H₂SO₄ đặc xúc tác và đun nóng.'});
add({id:'ester_sap',cat:'Ester – Lipid',type:'Xà phòng hóa',name:'Xà phòng hóa ester',r:['ester','naoh'],rate:.07,minT:50,layerFade:1,eq:'CH₃COOC₂H₅ + NaOH → CH₃COONa + C₂H₅OH',ph:'Lớp ester biến mất dần, dung dịch trở nên đồng nhất.',ex:'Phản ứng một chiều, tạo muối của axit và ancol tan trong nước.'});
add({id:'soap1',cat:'Ester – Lipid',type:'Xà phòng hóa',name:'Xà phòng hóa chất béo',r:['oil','naoh'],rate:.05,minT:60,layerFade:.8,eq:'(RCOO)₃C₃H₅ + 3NaOH → 3RCOONa + C₃H₅(OH)₃',ph:'Đun nóng và khuấy: giọt dầu nhỏ dần, hỗn hợp đồng nhất. Thêm NaCl bão hòa để tách xà phòng.',ex:'Sản phẩm: muối natri của axit béo + glixerol.'});
add({id:'soap2',cat:'Ester – Lipid',type:'Xà phòng hóa',name:'Xà phòng hóa + NaCl bão hòa',r:['oil','naoh','nacl'],rate:.07,minT:60,soap:1,eq:'(RCOO)₃C₃H₅ + 3NaOH → 3RCOONa + C₃H₅(OH)₃',ph:'Xà phòng trắng nổi lên thành lớp riêng; glixerol nằm trong pha dung dịch.',ex:'NaCl bão hòa làm giảm độ tan của xà phòng nên xà phòng tách ra.'});
add({id:'biuret',cat:'Protein',type:'Nhận biết',name:'Phản ứng Biuret',r:['protein','naoh','cuso4'],rate:.25,col:[135,55,170,.8],eq:'Protein + Cu(OH)₂ → phức màu tím',ph:'Phản ứng màu Biuret: màu tím đặc trưng.',ex:'Liên kết peptit tạo phức với Cu²⁺ trong môi trường kiềm cho màu tím.'});
RX.forEach(x=>x.hz=x.warn);
const ACID=['hcl','h2so4','hno3'];
/* ===== TRẠNG THÁI ===== */
const S={liqs:[],metal:null,T:25,lamp:false,inten:2,level:0,tlevel:0,p:0,rx:null,sp:0,sed:0,vessel:'tube',sound:true,lvl:1,free:true,kit:null,col:[0,0,0,0],pour:null,sel:null};
const P={b:[],f:[],s:[],p:[],m:[]};
let t=0,last=performance.now();
const cv=$('#cv'),ctx=cv.getContext('2d');
const V={
tube:{x1:222,x2:298,top:90,bot:360,cap:.8,p(c){c.beginPath();c.moveTo(215,90);c.lineTo(215,315);c.arc(260,315,45,Math.PI,0,true);c.lineTo(305,90)}},
beaker:{x1:178,x2:342,top:130,bot:360,cap:.8,p(c){c.beginPath();c.moveTo(170,130);c.lineTo(170,350);c.quadraticCurveTo(170,360,180,360);c.lineTo(340,360);c.quadraticCurveTo(350,360,350,350);c.lineTo(350,130)}},
flask:{x1:190,x2:330,top:90,bot:360,cap:.55,p(c){c.beginPath();c.moveTo(238,90);c.lineTo(238,200);c.lineTo(160,340);c.quadraticCurveTo(155,360,175,360);c.lineTo(345,360);c.quadraticCurveTo(365,360,360,340);c.lineTo(282,200);c.lineTo(282,90)}}};
const lc=(c,a)=>`rgba(${c[0]|0},${c[1]|0},${c[2]|0},${a??c[3]})`;
const mix=(a,b,m)=>a.map((v,i)=>v+(b[i]-v)*m);
const ySurf=()=>{const v=V[S.vessel];return v.bot-S.level*(v.bot-v.top)*v.cap};
/* ===== ÂM THANH ===== */
let AC;function snd(k){if(!S.sound)return;try{AC=AC||new AudioContext();const o=AC.createOscillator(),g=AC.createGain();o.connect(g);g.connect(AC.destination);o.frequency.value=({click:620,drop:300,warn:220,pour:180,bub:800+Math.random()*500})[k]||400;o.type=k=='warn'?'triangle':'sine';g.gain.setValueAtTime(.04,AC.currentTime);g.gain.exponentialRampToValueAtTime(.0001,AC.currentTime+.14);o.start();o.stop(AC.currentTime+.15)}catch(e){}}
/* ===== ĐỘNG CƠ PHẢN ỨNG ===== */
function contents(){const a=[...S.liqs];if(S.metal&&S.metal.touch)a.push(S.metal.id);return a}
function recompute(){
 const c=contents();let best=null;
 RX.forEach(x=>{if(x.r.every(i=>c.includes(i))&&(!best||x.r.length>best.r.length||(x.r.length==best.r.length&&x.rate>best.rate)))best=x});
 if(best!==S.rx){S.rx=best;S.p=0;S.sed=0;P.p=[]}
 buildMol()}
function spd(x){if(!x||x.rate==0||S.p>=1)return 0;if(x.minT&&S.T<x.minT)return 0;
 const f=x.opt?Math.exp(-(((S.T-x.opt[0])/x.opt[1])**2)):Math.min(Math.pow(2,(S.T-25)/(x.ts||30)),x.cap||4);return x.rate*f}
function pH(){let a=0,b=0;S.liqs.forEach(i=>{if(L[i].k=='a')a++;if(L[i].k=='b')b++});if(!a&&!b)return 7;return Math.max(0,Math.min(14,7-3.2*(a-b)))}
function indCol(h){const i=S.liqs.find(k=>L[k].k=='i');if(!i)return null;
 if(i=='quy')return h<5?[220,50,50,.55]:h>8?[50,90,220,.55]:[150,80,190,.5];
 if(i=='phph')return h>8.2?[235,60,150,.6]:[225,235,240,.2];
 return h<3.1?[225,50,40,.6]:h>4.4?[245,215,50,.6]:[245,150,40,.6]}
function target(){
 const aq=S.liqs.filter(i=>L[i].k!='o'&&L[i].k!='i'),src=aq.length?aq:S.liqs.filter(i=>L[i].k!='i');
 let c=[225,235,245,.12];if(src.length){c=src.map(i=>L[i].c).reduce((a,b)=>a.map((v,j)=>v+b[j]),[0,0,0,0]).map(v=>v/src.length)}
 const ic=indCol(pH());if(ic)c=mix(c,ic,.9);
 const x=S.rx;if(x&&x.col){const m=(x.fadeT&&S.T>x.fadeT)?0:Math.min(1,S.p*1.3);c=mix(c,x.col,m)}
 return c}
/* ===== THAO TÁC ===== */
const toast=(m,ms=2600)=>{const e=$('#toast');e.textContent=m;e.classList.add('show');clearTimeout(toast.h);toast.h=setTimeout(()=>e.classList.remove('show'),ms)};
function addItem(id){
 snd('drop');
 if(M[id]){if(S.metal)return toast('Dụng cụ đã có một kim loại. Hãy Reset để thử kim loại khác.');
  S.metal={id,x:260,y:20,vy:0,touch:false,rot:0};if(M[id].hz)toast('⚠️ '+M[id].hz+'. Đây là mô phỏng giáo dục. Không tự thực hiện thí nghiệm nguy hiểm ngoài phòng thí nghiệm được giám sát.',4200);return}
 if(!S.liqs.includes(id))S.liqs.push(id);
 S.tlevel=Math.min(.95,S.tlevel+(id=='h2o'?.3:.18));S.pour={c:L[id].c,t:0};snd('pour');
 if(L[id].hz){snd('warn');toast('⚠️ '+L[id].n+': '+L[id].hz+'. Đây là mô phỏng giáo dục. Không tự thực hiện thí nghiệm nguy hiểm ngoài phòng thí nghiệm được giám sát.',4200)}
 recompute()}
function reset(keep){S.liqs=[];S.metal=null;S.level=S.tlevel=0;S.p=0;S.rx=null;S.sed=0;S.T=25;S.lamp=false;S.col=[0,0,0,0];Object.keys(P).forEach(k=>P[k]=[]);
 $('#bLamp').textContent='🔥 Bật đèn cồn';$('#bLamp').classList.remove('on');if(!keep){S.kit=null;S.free=true;$('#bFree').classList.add('on');buildShelf()}}
/* ===== GIAO DIỆN KỆ + KÉO THẢ ===== */
function bottle(c,f){return `<svg viewBox="0 0 36 48"><path d="M13 2h10v8l7 9v24a3 3 0 0 1-3 3H9a3 3 0 0 1-3-3V19l7-9z" fill="#fff9" stroke="#9db3c6"/><path d="M8 28h20v15a2 2 0 0 1-2 2H10a2 2 0 0 1-2-2z" fill="${lc(c,Math.min(1,c[3]+.35))}"/></svg>`}
function buildShelf(){
 const kit=S.free?null:S.kit,lq=$('#liqs'),rk=$('#rack');lq.innerHTML='';rk.innerHTML='';
 Object.keys(L).filter(i=>!kit||kit.includes(i)).forEach(i=>{const d=document.createElement('div');d.className='chip';d.innerHTML=bottle(L[i].c)+L[i].n;d.title=L[i].f+(L[i].hz?' — ⚠️ '+L[i].hz:'');lq.appendChild(d);drag(d,i)});
 Object.keys(M).filter(i=>!kit||kit.includes(i)).forEach(i=>{const d=document.createElement('div');d.className='mchip'+(S.sel==i?' sel':'');d.textContent=i;const c=M[i].col;d.style.background=`linear-gradient(135deg,${lc(c,1)},${lc(c.map(v=>v*.7),1)})`;d.dataset.m=i;rk.appendChild(d);drag(d,i)})}
function selMetal(i){S.sel=i;document.querySelectorAll('.mchip').forEach(e=>e.classList.toggle('sel',e.dataset.m==i));const m=M[i];$('#minfo').innerHTML=`<b>${i} — ${m.n}</b><br>Mức độ hoạt động: <b>${m.act}</b><br>Với nước: ${m.w}`;snd('click')}
function over(e){const r=cv.getBoundingClientRect(),k=520/r.width,x=(e.clientX-r.left)*k,y=(e.clientY-r.top)*k;return x>120&&x<400&&y>0&&y<420}
function drag(el,id){el.addEventListener('pointerdown',e=>{e.preventDefault();if(M[id])selMetal(id);const sx=e.clientX,sy=e.clientY,r=el.getBoundingClientRect(),g=el.cloneNode(true);g.classList.add('ghost');g.style.cssText=`left:${r.left}px;top:${r.top}px;width:${r.width}px;height:${r.height}px`;document.body.appendChild(g);let mv=false;
 const m=ev=>{const dx=ev.clientX-sx,dy=ev.clientY-sy;if(Math.abs(dx)+Math.abs(dy)>6)mv=true;g.style.transform=`translate(${dx}px,${dy}px) scale(1.12)`;$('#stage').classList.toggle('drop',mv&&over(ev))};
 const u=ev=>{removeEventListener('pointermove',m);removeEventListener('pointerup',u);$('#stage').classList.remove('drop');
  if(!mv||over(ev)){g.remove();addItem(id)}else{g.style.transition='transform .3s';g.style.transform='';setTimeout(()=>g.remove(),300)}};
 addEventListener('pointermove',m);addEventListener('pointerup',u)})}
/* ===== PHÂN TỬ ===== */
function buildMol(){P.m=[];const v=V[S.vessel];const aq=S.liqs.length;if(!aq)return;
 const mk=(ty,lb)=>P.m.push({ty,lb,x:v.x1+Math.random()*(v.x2-v.x1),y:0,vx:(Math.random()-.5)*30,vy:(Math.random()-.5)*30});
 for(let i=0;i<12;i++)mk('w');
 S.liqs.forEach(i=>(L[i].ion||[]).forEach(l=>{for(let k=0;k<4;k++)mk('i',l)}));
 if(S.rx&&S.rx.gas)for(let k=0;k<4;k++)mk('g',S.rx.gas)}
/* ===== MÔ PHỎNG ===== */
function step(dt){
 const v=V[S.vessel];S.level+=(S.tlevel-S.level)*Math.min(1,dt*3);
 const aqueous=S.liqs.some(i=>L[i].k!='o')&&S.level>.02,cap=aqueous?100:300;
 if(S.lamp){const tg=[0,130,220,320][S.inten];S.T+=(Math.min(tg,cap)-S.T)*dt*.1*S.inten}else S.T+=(25-S.T)*dt*.03;
 S.T=Math.max(0,Math.min(S.T,cap));
 const ys=ySurf(),boil=aqueous&&S.T>98.5;
 // kim loại
 const m=S.metal;
 if(m){const fl=S.rx&&M[m.id].fl||['Li','Na','K'].includes(m.id),tgt=fl?ys-5:v.bot-10;m.vy=Math.min(m.vy+dt*400,m.y>ys?60:420);
  if(!(fl&&m.y>=tgt-1&&m.touch)){m.y=Math.min(tgt,m.y+m.vy*dt);if(m.y>=tgt-.5)m.vy=0}
  if(fl&&m.touch)m.y=ys-5+Math.sin(t*3)*1.2;
  const was=m.touch;m.touch=S.level>.02&&m.y>=ys-6;if(m.touch&&!was){for(let i=0;i<6;i++)P.b.push({x:m.x,y:ys,r:2+Math.random()*2,vy:-30,w:Math.random()*6});recompute()}
  if(m.touch&&S.sp>0&&fl){m.x=260+Math.sin(t*(1+S.sp*5))*Math.min(v.x2-v.x1-30,20+S.sp*180)/2}}
 const x=S.rx;S.sp=spd(x);
 if(x&&S.sp>0){S.p=Math.min(1,S.p+S.sp*dt);if(x.heat&&S.T<80)S.T+=S.sp*6*dt;
  if(x.gas){const n=Math.min(70,S.sp*400+(x.opt?0:0))*dt;for(let i=0,k=Math.floor(n)+(Math.random()<n%1?1:0);i<k;i++){const mt=m&&m.touch&&x.r.includes(m.id);P.b.push({x:mt?m.x+(Math.random()-.5)*14:v.x1+Math.random()*(v.x2-v.x1),y:mt?m.y+4:v.bot-14,r:1.5+Math.random()*3.5,vy:-(25+Math.random()*35),w:Math.random()*6})}}
  if(x.pre&&Math.random()<S.sp*40*dt*3)for(let i=0;i<2;i++)P.p.push({x:v.x1+Math.random()*(v.x2-v.x1),y:ys+4,vy:20+Math.random()*25,r:1.5+Math.random()*3});
  if(x.fl&&S.p<.97&&m&&m.touch)for(let i=0;i<2;i++)P.f.push({x:m.x+(Math.random()-.5)*8,y:m.y-4,vy:-(30+Math.random()*30),vx:(Math.random()-.5)*20,l:.5,ty:'fl'});
  if(Math.random()<S.sp*dt*3)snd('bub')}
 if(x&&x.pre)S.sed=S.p*28;
 if(boil&&Math.random()<dt*40)P.b.push({x:v.x1+Math.random()*(v.x2-v.x1),y:v.bot-12,r:2+Math.random()*3,vy:-60,w:Math.random()*6});
 if(S.T>80&&aqueous&&Math.random()<dt*((S.T-78)/20)*30)P.s.push({x:v.x1+Math.random()*(v.x2-v.x1),y:ys-4,vy:-(20+Math.random()*25),r:3,l:1.6});
 if(S.lamp&&Math.random()<dt*50)P.f.push({x:260+(Math.random()-.5)*8,y:405,vy:-(25+Math.random()*30)*S.inten/2,vx:0,l:.35,ty:'lamp'});
 // cập nhật hạt
 P.b=P.b.filter(b=>{b.y+=b.vy*dt;b.x+=Math.sin(t*6+b.w)*10*dt;b.r+=dt*.4;if(b.y<=ys){if(Math.random()<.7)P.f.push({x:b.x,y:ys,vx:0,vy:0,l:.2,ty:'pop',r:b.r});return false}return true});
 P.f=P.f.filter(f=>{f.l-=dt;f.x+=(f.vx||0)*dt;f.y+=f.vy*dt;return f.l>0});
 P.s=P.s.filter(s=>{s.l-=dt;s.y+=s.vy*dt;s.r+=dt*7;return s.l>0});
 P.p=P.p.filter(p=>{p.y+=p.vy*dt;p.x+=Math.sin(t*3+p.r*9)*6*dt;return p.y<v.bot-S.sed-2});
 P.m.forEach(q=>{q.x+=q.vx*dt*(1+S.T/80);q.y+=q.vy*dt*(1+S.T/80);if(q.y==0)q.y=ys+10+Math.random()*(v.bot-ys-20);q.vx+=(Math.random()-.5)*60*dt;q.vy+=(Math.random()-.5)*60*dt;
  if(q.x<v.x1+6||q.x>v.x2-6)q.vx*=-1;if(q.y<ys+8||q.y>v.bot-8)q.vy*=-1;q.x=Math.max(v.x1,Math.min(v.x2,q.x));q.y=Math.max(ys+6,Math.min(v.bot-6,q.y))});
 S.col=mix(S.col,target(),Math.min(1,dt*2.5));
 // layer
 S.hasOrg=S.liqs.some(i=>L[i].k=='o');
}
/* ===== VẼ ===== */
function drawLamp(){const x=260;ctx.save();
 ctx.fillStyle='#d9e2ec';ctx.fillRect(40,500,440,8);ctx.fillStyle='#0001';ctx.fillRect(60,508,400,5);
 if(S.lamp){const g=ctx.createRadialGradient(x,420,5,x,380,160);g.addColorStop(0,'rgba(255,170,60,.28)');g.addColorStop(1,'rgba(255,170,60,0)');ctx.fillStyle=g;ctx.fillRect(80,250,360,250)}
 const gr=ctx.createLinearGradient(x-34,0,x+34,0);gr.addColorStop(0,'#aecde4');gr.addColorStop(.35,'#eaf5fc');gr.addColorStop(1,'#9ebdd4');
 ctx.fillStyle=gr;ctx.strokeStyle='#7da0ba';ctx.beginPath();ctx.moveTo(x-12,425);ctx.lineTo(x-12,440);ctx.quadraticCurveTo(x-42,450,x-34,480);ctx.quadraticCurveTo(x-30,500,x,500);ctx.quadraticCurveTo(x+30,500,x+34,480);ctx.quadraticCurveTo(x+42,450,x+12,440);ctx.lineTo(x+12,425);ctx.closePath();ctx.fill();ctx.stroke();
 ctx.fillStyle='rgba(250,205,100,.8)';ctx.fillRect(x-30,468,60,26);ctx.fillStyle='#8a6a42';ctx.fillRect(x-14,412,28,14);
 ctx.restore()}
function flame(){const x=260,k=[0,.6,1,1.4][S.inten];ctx.save();ctx.globalCompositeOperation='source-over';
 const h=34*k+Math.sin(t*14)*3,w=11*k;
 let g=ctx.createLinearGradient(0,412,0,412-h);g.addColorStop(0,'rgba(60,110,255,.9)');g.addColorStop(.35,'rgba(255,190,60,.9)');g.addColorStop(1,'rgba(255,100,20,0)');
 ctx.fillStyle=g;ctx.beginPath();ctx.moveTo(x-w,412);ctx.quadraticCurveTo(x-w*1.2,412-h*.5,x+Math.sin(t*9)*3,412-h);ctx.quadraticCurveTo(x+w*1.2,412-h*.5,x+w,412);ctx.fill();ctx.restore()}
function thermo(){const x=440,T=S.T;ctx.save();ctx.strokeStyle='#8fa8be';ctx.fillStyle='#ffffffcc';ctx.lineWidth=2;
 ctx.beginPath();ctx.roundRect(x-7,100,14,300,7);ctx.fill();ctx.stroke();ctx.beginPath();ctx.arc(x,410,13,0,7);ctx.fill();ctx.stroke();
 const col=T>80?'#e53935':T>40?'#fb8c00':'#1e88e5';ctx.fillStyle=col;ctx.beginPath();ctx.arc(x,410,9,0,7);ctx.fill();const h=8+T/300*280;ctx.fillRect(x-3,405-h,6,h+5);
 ctx.fillStyle='#6b7c8d';ctx.font='10px sans-serif';ctx.textAlign='left';[0,100,200,300].forEach(v=>{const y=405-(8+v/300*280);ctx.fillRect(x+9,y,6,1);ctx.fillText(v,x+18,y+3)});ctx.restore()}
function metal(){const m=S.metal;if(!m)return;const x=S.rx&&S.rx.r.includes(m.id);const mass=x?1-S.p:1;if(mass<.03)return;const s=.4+.6*Math.sqrt(mass),c=M[m.id].col;
 ctx.save();ctx.translate(m.x,m.y);ctx.rotate(Math.sin(t*2)*.05*(S.sp>0?3:1));ctx.scale(s,s);
 const g=ctx.createLinearGradient(0,-8,0,8);g.addColorStop(0,lc([...c.map(v=>Math.min(255,v+45))],1));g.addColorStop(.5,lc(c,1));g.addColorStop(1,lc(c.map(v=>v*.65),1));
 ctx.fillStyle=g;ctx.strokeStyle=g;
 if(m.id=='Mg'){ctx.lineWidth=5;ctx.beginPath();for(let i=-24;i<=24;i+=2)ctx.lineTo(i,Math.sin(i*.25)*3);ctx.stroke()}
 else if(m.id=='Fe'){ctx.fillRect(-20,-2,40,4);ctx.beginPath();ctx.ellipse(-21,0,3,7,0,0,7);ctx.fill();ctx.beginPath();ctx.moveTo(20,-2);ctx.lineTo(27,0);ctx.lineTo(20,2);ctx.fill()}
 else if(m.id=='Cu'){ctx.lineWidth=3;ctx.beginPath();for(let i=-24;i<=24;i+=2)ctx.lineTo(i,Math.sin(i*.45)*5);ctx.stroke()}
 else{ctx.beginPath();ctx.roundRect(-11,-7,22,14,3);ctx.fill();ctx.fillStyle='rgba(255,255,255,.55)';ctx.fillRect(-8,-5,10,2)}
 ctx.restore()}
function draw(){
 const v=V[S.vessel],ys=ySurf(),c=ctx;c.clearRect(0,0,520,560);
 drawLamp();thermo();
 const boil=S.T>98.5&&S.level>.02,amp=1.2+Math.min(5,S.sp*30)+(boil?2:0);
 c.save();if(S.sp>.15||boil)c.translate(Math.sin(t*60)*.8,0);
 // chất lỏng
 c.save();v.p(c);c.clip();
 if(S.level>.01){const col=S.col,g=c.createLinearGradient(0,ys,0,v.bot);g.addColorStop(0,lc(col,Math.min(1,col[3]+.05)));g.addColorStop(1,lc(col.map(q=>q*.85),Math.min(1,col[3]+.2)));
  c.fillStyle=g;c.beginPath();c.moveTo(100,v.bot+20);for(let x=100;x<=420;x+=4)c.lineTo(x,ys+Math.sin(x*.06+t*3)*amp);c.lineTo(420,v.bot+20);c.fill();
  if(S.hasOrg){const o=S.liqs.find(i=>L[i].k=='o');let oc=L[o].c.slice(),th=22,al=1;const x=S.rx;if(x&&x.layerFade)al=1-x.layerFade*S.p;if(x&&x.soap){oc=mix(oc,[252,248,235,.95],Math.min(1,S.p*2));th=22+S.p*12}
   c.fillStyle=lc(oc,oc[3]*al);c.fillRect(100,ys-1,320,th);c.fillStyle='#fff6';c.fillRect(100,ys+th,320,1.5)}
  c.fillStyle='rgba(255,255,255,.5)';c.fillRect(100,ys-1+Math.sin(t*3)*amp*.4,320,1.5);
  // sediment
  const x=S.rx;if(x&&x.pre&&S.sed>0){c.fillStyle=lc(x.pre[1],.95);c.beginPath();c.moveTo(100,v.bot+20);for(let q=100;q<=420;q+=6)c.lineTo(q,v.bot-S.sed+Math.sin(q*.5)*2);c.lineTo(420,v.bot+20);c.fill()}
  // gương bạc
  if(x&&x.mirror){c.strokeStyle=`rgba(225,230,238,${.95*S.p})`;c.lineWidth=14;c.stroke();c.strokeStyle=`rgba(255,255,255,${.7*S.p})`;c.lineWidth=3;c.stroke()}
  // hạt kết tủa
  if(x&&x.pre){c.fillStyle=lc(x.pre[1],.9);P.p.forEach(p=>{c.beginPath();c.arc(p.x,p.y,p.r,0,7);c.fill()})}
  // phân tử
  if($('#cMol').checked||S.lvl==2)P.m.forEach(q=>{if(q.ty=='w'){c.fillStyle='#e53935';c.beginPath();c.arc(q.x,q.y,3.5,0,7);c.fill();c.fillStyle='#1e88e5';c.beginPath();c.arc(q.x-4,q.y+3,2.2,0,7);c.arc(q.x+4,q.y+3,2.2,0,7);c.fill()}
   else{c.fillStyle=q.ty=='g'?'#6a9e5b':/\+/.test(q.lb)?'#e8710a':'#2e7d32';c.beginPath();c.arc(q.x,q.y,7,0,7);c.fill();c.fillStyle='#fff';c.font='8px sans-serif';c.textAlign='center';c.fillText(q.lb,q.x,q.y+3)}})}
 // bong bóng (trong chất lỏng)
 if($('#cGas').checked||true){c.strokeStyle='rgba(255,255,255,.9)';c.fillStyle='rgba(255,255,255,.25)';P.b.forEach(b=>{if(!$('#cGas').checked)return;c.beginPath();c.arc(b.x,b.y,b.r,0,7);c.fill();c.lineWidth=1;c.stroke()})}
 c.restore();
 // kim loại
 metal();
 // kính
 const gl=c.createLinearGradient(160,0,360,0);gl.addColorStop(0,'rgba(120,160,190,.55)');gl.addColorStop(.5,'rgba(255,255,255,.5)');gl.addColorStop(1,'rgba(120,160,190,.55)');
 v.p(c);c.strokeStyle=gl;c.lineWidth=3;c.stroke();c.strokeStyle='rgba(255,255,255,.7)';c.lineWidth=2;c.beginPath();c.moveTo(v.x1+4,v.top+30);c.lineTo(v.x1+4,v.bot-70);c.stroke();
 c.fillStyle='rgba(180,210,235,.08)';v.p(c);c.fill();
 c.restore();
 // hơi, lửa, nổ bọt
 if($('#cGas').checked)P.s.forEach(s=>{c.fillStyle=`rgba(235,240,245,${Math.max(0,s.l/1.6)*.35})`;c.beginPath();c.arc(s.x,s.y,s.r,0,7);c.fill()});
 P.f.forEach(f=>{if(f.ty=='pop'){c.strokeStyle=`rgba(255,255,255,${f.l*4})`;c.beginPath();c.arc(f.x,f.y,f.r+(.2-f.l)*20,0,7);c.stroke()}else{const a=Math.max(0,f.l*2);c.fillStyle=f.ty=='fl'?`rgba(255,${120+Math.random()*80|0},30,${a})`:`rgba(255,200,80,${a*.5})`;c.beginPath();c.arc(f.x,f.y,f.ty=='fl'?4*f.l*2:3,0,7);c.fill()}});
 if(S.lamp)flame();
 // rót chất lỏng
 if(S.pour){S.pour.t+=.016;const p=S.pour;if(p.t>.9)S.pour=null;else{c.strokeStyle=lc(p.c,Math.min(1,p.c[3]+.4));c.lineWidth=5;c.lineCap='round';c.beginPath();c.moveTo(150,40);c.quadraticCurveTo(250,30,258,40);c.lineTo(258,ys);c.stroke();c.fillStyle=lc(p.c,.9);c.beginPath();c.ellipse(120,52,36,14,-.4,0,7);c.fill()}}
 // nhãn vật liệu
 c.fillStyle='#6b7c8d';c.font='11px "Be Vietnam Pro",sans-serif';c.textAlign='center';c.fillText({tube:'Ống nghiệm',beaker:'Cốc thủy tinh',flask:'Bình tam giác'}[S.vessel],260,545)}
/* ===== BẢNG THÔNG TIN ===== */
function info(){
 const x=S.rx,sp=S.sp,c=contents(),nm=c.map(i=>M[i]?i:L[i].f);
 const fx=S.liqs.filter(i=>L[i].k!='i'&&i!='h2o');
 let h='<h3>PHẢN ỨNG</h3>';
 h+=`<div class="k">Trong dụng cụ</div>${S.liqs.map(i=>L[i].f).concat(S.metal?[S.metal.id+(S.metal.touch?'':' (chưa chạm nước)')]:[]).join(', ')||'<span style="color:var(--mut)">Trống — hãy kéo hóa chất vào</span>'}`;
 if(x&&x.minT&&S.T<x.minT&&S.p<1)h+=`<div class="warn" style="margin-top:6px">Cần đun nóng ≥ ${x.minT}°C để phản ứng xảy ra.</div>`;
 if(x){
  if(x.none)h+=`<div class="k">Hiện tượng</div>${x.none}`;
  else if(S.p>.03){h+=`<div class="k">Hiện tượng</div>${x.ph}`;
   if(x.gas)h+=`<div class="k">Khí sinh ra</div>${x.gas}`;if(x.pre)h+=`<div class="k">Kết tủa</div>${x.pre[0]}`}
  if(S.p>.35||x.none){let eq=x.eq;if(x.eqHot&&S.T>=x.eqHot[0])eq=x.eqHot[1];h+=`<div class="k">Phương trình</div><div class="eq">${eq}</div>`}
  if(S.lvl>=1&&(S.p>.5||x.none)){h+=`<div class="k">Giải thích</div>${x.ex}<div class="k">Loại phản ứng</div>${x.type} · ${x.cat}`}
  if(x.warn)h+=`<div class="warn" style="margin-top:6px">⚠️ ${x.warn}</div>`;
  h+=`<div class="k">Tốc độ phản ứng</div><div class="bar"><i style="width:${Math.min(100,sp*300)|0}%"></i></div><small>Tiến trình: ${(S.p*100)|0}%</small>`;
 }else if(c.filter(i=>!L[i]||L[i].k!='i').length>=2&&S.liqs.filter(i=>i!='h2o').length+(S.metal?1:0)>=2)h+=`<div class="k">Hiện tượng</div>Không quan sát thấy phản ứng đáng kể trong điều kiện hiện tại.`;
 const ph=pH(),showPh=S.liqs.some(i=>L[i].k=='a'||L[i].k=='b'||L[i].k=='i');
 if(showPh)h+=`<div class="k">pH ≈ ${ph.toFixed(1)}</div><div class="ph"><i style="left:${ph/14*96}%"></i></div>`;
 h+=`<div class="k">Nhiệt độ</div><b>${S.T|0}°C</b>${S.T>98.5&&S.level>.02?' · nước sôi':S.T>80&&S.level>.02?' · bắt đầu bốc hơi':''}`;
 $('#info').innerHTML=h}
/* ===== VÒNG LẶP ===== */
let sliding=false;
function frame(now){const dt=Math.min(.05,(now-last)/1000);last=now;t+=dt;step(dt);draw();if(!sliding)$('#tmp').value=S.T;$('#tv').textContent=(S.T|0)+'°C';if((frame.n=(frame.n||0)+1)%8==0)info();requestAnimationFrame(frame)}
/* ===== ĐIỀU KHIỂN ===== */
$('#tmp').oninput=e=>{sliding=true;S.T=+e.target.value};$('#tmp').onchange=()=>sliding=false;
$('#bLamp').onclick=e=>{S.lamp=!S.lamp;e.target.textContent=S.lamp?'🔥 Tắt đèn cồn':'🔥 Bật đèn cồn';e.target.classList.toggle('on',S.lamp);snd('click')};
$('#int').oninput=e=>S.inten=+e.target.value;
$('#bSnd').onclick=e=>{S.sound=!S.sound;e.target.textContent=S.sound?'🔊 Âm thanh':'🔇 Âm thanh';e.target.classList.toggle('on',S.sound);snd('click')};
$('#bReset').onclick=()=>{reset(true);snd('click');toast('Đã reset thí nghiệm.')};
$('#bFree').onclick=()=>{S.free=!S.free;$('#bFree').classList.toggle('on',S.free);if(S.free)S.kit=null;buildShelf();snd('click')};
$('#vsel').onclick=e=>{const b=e.target.closest('button');if(!b)return;S.vessel=b.dataset.v;[...$('#vsel').children].forEach(x=>x.classList.toggle('on',x==b));buildMol();snd('click')};
$('#lsel').onclick=e=>{const b=e.target.closest('button');if(!b)return;S.lvl=+b.dataset.l;[...$('#lsel').children].forEach(x=>x.classList.toggle('on',x==b));snd('click')};
$('#mL').onclick=()=>$('#rack').scrollBy(-150,0);$('#mR').onclick=()=>$('#rack').scrollBy(150,0);
$('#bGuide').onclick=()=>$('#guide').hidden=false;
$('#bMenu').onclick=()=>{$('#menu').hidden=false;list()};
$('#menu').onclick=e=>{if(e.target==$('#menu'))$('#menu').hidden=true};
$('#guide').onclick=e=>{if(e.target==$('#guide'))$('#guide').hidden=true};
const cats=['Tất cả',...new Set(RX.map(x=>x.cat))];$('#fc').innerHTML=cats.map(c=>`<option>${c}</option>`).join('');
function list(){const q=$('#q').value.toLowerCase(),f=$('#fc').value;
 const items=[{id:'metals',name:'Kim loại + nước',cat:'Kim loại',r:[...Object.keys(M),'h2o'],eq:'Chọn kim loại, quan sát mức độ hoạt động'},...RX.filter(x=>!x.id.endsWith('_h2o'))];
 $('#mlist').innerHTML='';items.filter(x=>(f=='Tất cả'||x.cat==f)&&(!q||(x.name+x.eq+x.r.join(' ')+x.r.map(i=>L[i]?L[i].n:i).join(' ')).toLowerCase().includes(q))).forEach(x=>{const b=document.createElement('button');b.innerHTML=`${x.name}<br><small>${x.cat}</small>`;b.onclick=()=>{reset(true);S.free=false;S.kit=x.r.concat(x.cat=='Axit – Bazơ'||x.id.startsWith('neut')?['quy','phph','mo']:[]);$('#bFree').classList.remove('on');buildShelf();$('#menu').hidden=true;toast('Thí nghiệm «'+x.name+'»: kéo các chất trên kệ vào dụng cụ.',3600)};$('#mlist').appendChild(b)})}
$('#q').oninput=list;$('#fc').onchange=list;
buildShelf();recompute();requestAnimationFrame(frame);
</script></body></html>
