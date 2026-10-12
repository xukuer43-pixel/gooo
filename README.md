<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>集美中学高二期中冲刺站</title>
<style>
:root{
 --bg:#f4f7fb;--card:#fff;--text:#202b3c;
 --muted:#69778b;--blue:#3569e8;--green:#138a67;
 --border:#e4eaf2;--orange:#ed8a29;
}
*{box-sizing:border-box}
body{
 margin:0;background:var(--bg);color:var(--text);
 font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",
 "PingFang SC","Microsoft YaHei",sans-serif;line-height:1.7
}
header{
 padding:28px 18px 25px;color:white;
 background:linear-gradient(135deg,#2445a8,#438cf2)
}
header h1{font-size:25px;margin:0 0 8px}
header p{margin:4px 0;opacity:.92;font-size:14px}
.container{max-width:900px;margin:auto;padding:15px}
nav{
 display:flex;gap:8px;overflow-x:auto;padding:10px 0;
 position:sticky;top:0;background:var(--bg);z-index:5
}
nav button{
 flex-shrink:0;border:0;border-radius:12px;padding:10px 14px;
 background:#e6edfc;color:#294b9c;font-weight:bold
}
nav button.active{background:var(--blue);color:white}
section{display:none}
section.active{display:block}
.card{
 background:var(--card);padding:18px;margin:12px 0;
 border:1px solid var(--border);border-radius:17px;
 box-shadow:0 3px 12px #1e365008
}
h2{font-size:21px;margin:0 0 12px}
h3{font-size:17px;margin:15px 0 8px}
p{margin:8px 0}
.small{font-size:13px;color:var(--muted)}
.tag{
 display:inline-block;background:#eaf0ff;color:#3459b7;
 padding:3px 9px;border-radius:8px;font-size:12px;margin:3px
}
.notice{
 background:#fff5df;border-left:4px solid #e9a331;
 border-radius:8px;padding:12px;font-size:14px
}
input,select,textarea{
 width:100%;padding:11px;border:1px solid #ccd5e3;
 border-radius:10px;background:white;font:inherit;margin:5px 0
}
button.action{
 border:0;background:var(--blue);color:white;
 padding:10px 15px;border-radius:10px;font:inherit;
 font-weight:bold;margin:5px 3px 5px 0
}
button.secondary{background:#e7edf8;color:#304c84}
.result{
 background:#edf7f3;padding:12px;border-radius:10px;
 margin-top:10px;overflow-wrap:anywhere
}
.formula{
 background:#f0f4ff;padding:12px;border-radius:10px;
 font-weight:bold;overflow-wrap:anywhere
}
.progress{
 height:10px;background:#e0e7f2;border-radius:10px;overflow:hidden
}
.progress div{height:100%;width:0;background:#2baf83}
.grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px}
.tile{padding:15px;border-radius:13px;background:#edf2ff}
.tile strong{display:block;font-size:20px;color:#315fce}
canvas{
 width:100%;height:auto;border:1px solid var(--border);
 border-radius:12px;background:#fbfcff
}
footer{text-align:center;color:var(--muted);padding:25px;font-size:12px}
li{margin:6px 0}
@media(max-width:520px){
 header h1{font-size:22px}
 .grid{grid-template-columns:1fr 1fr}
 .card{padding:15px}
}
</style>
</head>
<body>

<header>
 <h1>🎯 集美中学 · 高二期中冲刺站</h1>
 <p>高二上学期｜物理 · 化学 · 地理 · 数学 · 语文 · 英语</p>
 <p>把原理弄懂，把题目做会，把错题变成分数。</p>
</header>

<div class="container">
<nav>
 <button class="active" onclick="showTab('home',this)">🏠 首页</button>
 <button onclick="showTab('geo',this)">🌍 地理</button>
 <button onclick="showTab('phy',this)">⚡ 物理</button>
 <button onclick="showTab('chem',this)">🧪 化学</button>
 <button onclick="showTab('math',this)">📐 数学</button>
 <button onclick="showTab('chinese',this)">📚 语文</button>
 <button onclick="showTab('english',this)">🇬🇧 英语</button>
 <button onclick="showTab('mistakes',this)">📝 错题本</button>
</nav>

<!-- 首页 -->
<section id="home" class="active">
 <div class="card">
  <h2>📅 我的期中复习计划</h2>
  <p class="notice">考试日期暂按你提供的 11 月 20 日设置。
  目前没有核实到集美中学本次考试的官方范围，以下内容是复习框架，
  请以学校老师公布的范围为准。</p>
  <div class="grid">
   <div class="tile"><strong>物理</strong>电场与带电粒子</div>
   <div class="tile"><strong>化学</strong>原电池与电解池</div>
   <div class="tile"><strong>地理</strong>自然地理原理</div>
   <div class="tile"><strong>数学</strong>公式、模型、综合题</div>
  </div>
 </div>
 <div class="card">
  <h2>✅ 今日学习打卡</h2>
  <p>完成一个专题，就勾选一项。</p>
  <label><input type="checkbox" class="task" onchange="saveTasks()"> 物理：弄懂电场方向和电势</label>
  <label><input type="checkbox" class="task" onchange="saveTasks()"> 化学：独立写出电极反应式</label>
  <label><input type="checkbox" class="task" onchange="saveTasks()"> 地理：掌握正午太阳高度计算</label>
  <label><input type="checkbox" class="task" onchange="saveTasks()"> 数学：完成一道典型题</label>
  <label><input type="checkbox" class="task" onchange="saveTasks()"> 语文：分析一篇信息类文本</label>
  <label><input type="checkbox" class="task" onchange="saveTasks()"> 英语：完成一篇阅读理解</label>
  <p id="taskText">完成度：0%</p>
  <div class="progress"><div id="taskBar"></div></div>
 </div>
 <div class="card">
  <h2>📌 使用方法</h2>
  <ol>
   <li>点击顶部科目，进入对应的复习页面。</li>
   <li>先理解原理，再观察模型，最后独立做题。</li>
   <li>答错的题目可以加入错题本。</li>
   <li>学习进度和错题记录保存在当前浏览器中。</li>
  </ol>
  <p class="small">提示：清除浏览器网站数据后，本地保存的记录可能丢失。</p>
 </div>
</section>

<!-- 地理 -->
<section id="geo">
 <div class="card">
  <h2>🌍 地理：正午太阳高度计算器</h2>
  <p>核心模型：太阳直射点纬度与当地纬度的关系。</p>
  <div class="formula">H = 90° − |φ − δ|</div>
  <p class="small">H 为正午太阳高度，φ 为当地纬度，δ 为太阳直射点纬度。
  北纬取正、南纬取负。</p>
  <label>当地纬度（北纬为正，南纬为负）</label>
  <input id="latitude" type="number" value="25" min="-90" max="90">
  <label>太阳直射点纬度（北纬为正，南纬为负）</label>
  <input id="declination" type="number" value="0" min="-23.44" max="23.44">
  <button class="action" onclick="calcSun()">计算太阳高度</button>
  <div id="sunResult" class="result">输入数据后点击计算。</div>
 </div>
 <div class="card">
  <h2>🧠 地理自测</h2>
  <p>某地纬度为北纬 30°，太阳直射北纬 10°。
  该地正午太阳高度是多少？</p>
  <button class="action secondary" onclick="check('geoquiz','A')">A. 50°</button>
  <button class="action secondary" onclick="check('geoquiz','B')">B. 70°</button>
  <button class="action secondary" onclick="check('geoquiz','C')">C. 80°</button>
  <div id="geoquiz" class="result">请选择答案。</div>
 </div>
 <div class="card">
  <h2>📖 自然地理核心思路</h2>
  <h3>1. 太阳高度与昼夜长短</h3>
  <p>地球是球体，太阳光近似平行。纬度、季节和昼夜变化会影响太阳高度及昼长。</p>
  <h3>2. 大气运动</h3>
  <p>受热不均造成气压差异，空气由高压区流向低压区；实际风向还受到地转偏向力和摩擦力影响。</p>
  <h3>3. 水循环</h3>
  <p>蒸发、植物蒸腾、水汽输送、降水、下渗和地表径流等环节共同构成水循环。</p>
  <h3>4. 地貌形成</h3>
  <p>内力作用塑造地表基本形态，风化、侵蚀、搬运、沉积等外力作用持续改造地貌。</p>
 </div>
</section>

<!-- 物理 -->
<section id="phy">
 <div class="card">
  <h2>⚡ 物理：电场方向互动模型</h2>
  <p>选择电荷，观察电场方向和试探电荷的受力方向。</p>
  <label>场源电荷</label>
  <select id="source" onchange="drawField()">
   <option value="1">正电荷（+）</option>
   <option value="-1">负电荷（−）</option>
  </select>
  <label>试探电荷</label>
  <select id="testCharge" onchange="drawField()">
   <option value="1">正电荷（+）</option>
   <option value="-1">负电荷（−）</option>
  </select>
  <canvas id="fieldCanvas" width="600" height="300"></canvas>
  <div id="fieldResult" class="result"></div>
  <div class="formula">F = qE　　E = F/q</div>
  <p>电场方向规定为正试探电荷受力的方向。
  正电荷受力与电场同向，负电荷受力与电场反向。</p>
 </div>
 <div class="card">
  <h2>🧠 物理自测</h2>
  <p>负电荷在电场中受到向左的电场力，电场方向如何？</p>
  <button class="action secondary" onclick="check('phyquiz','A')">A. 向左</button>
  <button class="action secondary" onclick="check('phyquiz','B')">B. 向右</button>
  <div id="phyquiz" class="result">请选择答案。</div>
 </div>
 <div class="card">
  <h2>📌 带电粒子偏转解题步骤</h2>
  <ol>
   <li>先分析电场方向，再判断粒子受力方向。</li>
   <li>由 F = qE 求电场力；若电场匀强，E 为常量。</li>
   <li>由牛顿第二定律求加速度：a = F/m。</li>
   <li>若粒子初速度垂直于电场，分解为两个方向：
    水平方向通常做匀速运动，电场方向做匀加速运动。</li>
   <li>分别列位移、速度公式，再结合几何关系求解。</li>
  </ol>
  <div class="formula">x = v₀t　　y = ½at²　　vᵧ = at</div>
  <p class="small">上述偏转模型适用于忽略重力、匀强电场等相应条件下的情况。</p>
 </div>
</section>

<!-- 化学 -->
<section id="chem">
 <div class="card">
  <h2>🧪 原电池与电解池</h2>
  <p>选择装置类型，查看两极反应规律。</p>
  <label>装置类型</label>
  <select id="cellType" onchange="showCell()">
   <option value="galvanic">原电池（自发反应提供电能）</option>
   <option value="electrolytic">电解池（外部电源提供电能）</option>
  </select>
  <div id="cellResult" class="result"></div>
  <h3>最关键的规律</h3>
  <div class="formula">阳极：氧化　　阴极：还原</div>
  <p>原电池：负极发生氧化，正极发生还原。</p>
  <p>电解池：阳极接电源正极，阴极接电源负极。</p>
  <p>电子经外电路移动；溶液内部主要由离子迁移传递电荷。</p>
 </div>
 <div class="card">
  <h2>✍️ 电极反应式怎么写？</h2>
  <ol>
   <li>确定装置类型及电极。</li>
   <li>判断该电极发生氧化还是还原。</li>
   <li>根据反应物、生成物写出初步方程式。</li>
   <li>在酸性或碱性环境中配平 O、H 和电荷。</li>
   <li>检查原子守恒、电荷守恒和电子数守恒。</li>
  </ol>
  <h3>电子转移量计算</h3>
  <div class="formula">n(e⁻) = Q/F　　Q = It</div>
  <p>F ≈ 96500 C/mol。I 为电流，t 为通电时间，Q 为电量。</p>
  <p>若已知反应物物质的量，需先根据配平后的反应式求电子与物质的比例。</p>
 </div>
 <div class="card">
  <h2>🧠 化学自测</h2>
  <p>电解池中，阴极发生什么反应？</p>
  <button class="action secondary" onclick="check('chemquiz','A')">A. 氧化</button>
  <button class="action secondary" onclick="check('chemquiz','B')">B. 还原</button>
  <div id="chemquiz" class="result">请选择答案。</div>
 </div>
</section>

<!-- 数学 -->
<section id="math">
 <div class="card">
  <h2>📐 数学：综合题通用流程</h2>
  <h3>第一步：读条件</h3>
  <p>把已知量、未知量、取值范围和特殊条件分别标出来。</p>
  <h3>第二步：找关系</h3>
  <p>思考题目属于函数、数列、三角函数、向量还是其他模块。</p>
  <h3>第三步：建立模型</h3>
  <p>把文字条件转换成方程、函数关系、向量等式或不等式。</p>
  <h3>第四步：计算与检查</h3>
  <p>检查定义域、符号、单位、特殊值和最终答案是否满足原条件。</p>
  <h3>第五步：总结</h3>
  <p>做完一道题，记录它考查的知识点、关键突破口和容易出错的步骤。</p>
 </div>
 <div class="card">
  <h2>🧠 数学自测</h2>
  <p>若函数 f(x)=2x+1，则 f(3) 等于多少？</p>
  <button class="action secondary" onclick="check('mathquiz','A')">A. 5</button>
  <button class="action secondary" onclick="check('mathquiz','B')">B. 7</button>
  <button class="action secondary" onclick="check('mathquiz','C')">C. 8</button>
  <div id="mathquiz" class="result">请选择答案。</div>
 </div>
 <div class="card">
  <h2>📌 错题复盘模板</h2>
  <p>每道错题至少写清楚三个问题：</p>
  <ul>
   <li>我原来错在哪里？</li>
   <li>正确解法的突破口是什么？</li>
   <li>下次看到什么条件，我应该想到这个模型？</li>
  </ul>
 </div>
</section>

<!-- 语文 -->
<section id="chinese">
 <div class="card">
  <h2>📚 语文：信息类文本阅读</h2>
  <h3>1. 先读题目，再读原文</h3>
  <p>先圈出题目中的主体、范围、程度词和因果词，再回到原文定位。</p>
  <h3>2. 特别留意这些词</h3>
  <p>全部、部分、一定、可能、主要、唯一、直接、间接、因此、然而。</p>
  <h3>3. 常见错误选项</h3>
  <ul>
   <li>偷换概念：把 A 换成与它相关但不同的 B。</li>
   <li>扩大范围：把“部分”说成“全部”。</li>
   <li>强加因果：原文只说两件事同时发生，选项却说存在因果。</li>
   <li>颠倒关系：把条件和结果、原因和结果颠倒。</li>
   <li>无中生有：原文没有提供足够依据。</li>
  </ul>
 </div>
 <div class="card">
  <h2>📖 文言文阅读</h2>
  <h3>实词</h3>
  <p>结合上下文判断词义，注意古今异义、一词多义、通假字和词类活用。</p>
  <h3>虚词</h3>
  <p>重点分析“之、其、而、以、于、为、乃”等词在句中的作用。</p>
  <h3>翻译句子</h3>
  <p>先找人物和谓语，再判断省略、倒装等句式，最后补足语意并检查通顺。</p>
  <h3>内容概括</h3>
  <p>把人物、事件、原因、做法和结果对应起来，避免把评价当作事实。</p>
 </div>
 <div class="card">
  <h2>🧠 语文自测</h2>
  <p>原文说“多数学生完成了任务”，选项说“所有学生都完成了任务”。主要问题是什么？</p>
  <button class="action secondary" onclick="check('cnquiz','A')">A. 扩大范围</button>
  <button class="action secondary" onclick="check('cnquiz','B')">B. 语序不当</button>
  <div id="cnquiz" class="result">请选择答案。</div>
 </div>
</section>

<!-- 英语 -->
<section id="english">
 <div class="card">
  <h2>🇬🇧 英语：阅读理解</h2>
  <h3>推荐步骤</h3>
  <ol>
   <li>先看题目，判断题目问的是细节、主旨、推断还是词义。</li>
   <li>回到文章定位相关段落。</li>
   <li>理解原句和上下文，不只依赖单个词。</li>
   <li>排除与原文相反、过度推断和偷换概念的选项。</li>
  </ol>
  <h3>常见题型</h3>
  <p>细节题：找原文依据。</p>
  <p>主旨题：关注文章反复出现的核心信息。</p>
  <p>推断题：必须能从原文合理推出，不能靠个人想象。</p>
  <p>词义猜测：结合上下文、转折词和解释性内容。</p>
 </div>
 <div class="card">
  <h2>✍️ 英语写作框架</h2>
  <div class="formula">
   Dear ...,<br><br>
   I am writing to ...<br>
   First, ...<br>
   In addition, ...<br>
   Finally, ...<br><br>
   I would appreciate it if ...<br>
   Yours sincerely,<br>
   ...
  </div>
  <p class="small">这是通用框架。考试时要根据题目要求、文体和具体内容调整，不能机械套用。</p>
 </div>
 <div class="card">
  <h2>🧠 英语自测</h2>
  <p>“Although it was raining, we went out.” 中 although 表示什么关系？</p>
  <button class="action secondary" onclick="check('enquiz','A')">A. 转折 / 让步</button>
  <button class="action secondary" onclick="check('enquiz','B')">B. 因果</button>
  <div id="enquiz" class="result">请选择答案。</div>
 </div>
</section>

<!-- 错题本 -->
<section id="mistakes">
 <div class="card">
  <h2>📝 我的错题本</h2>
  <label>科目</label>
  <select id="mistakeSubject">
   <option>物理</option><option>化学</option><option>地理</option>
   <option>数学</option><option>语文</option><option>英语</option>
  </select>
  <label>题目 / 错误原因</label>
  <textarea id="mistakeText" rows="3" placeholder="写下题目、错误原因或正确解法……"></textarea>
  <button class="action" onclick="addMistake()">保存错题</button>
  <button class="action secondary" onclick="exportMistakes()">导出错题</button>
  <div id="mistakeList"></div>
 </div>
</section>

<footer>
 集美中学高二期中冲刺站 · 自主复习工具<br>
 请以学校实际教学进度和老师公布的考试范围为准。
</footer>
</div>

<script>
function showTab(id,btn){
 document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
 document.getElementById(id).classList.add('active');
 document.querySelectorAll('nav button').forEach(b=>b.classList.remove('active'));
 btn.classList.add('active');
 window.scrollTo({top:0,behavior:'smooth'});
}
function calcSun(){
 const lat=Number(document.getElementById('latitude').value);
 const dec=Number(document.getElementById('declination').value);
 const out=document.getElementById('sunResult');
 if(!Number.isFinite(lat)||!Number.isFinite(dec)||Math.abs(lat)>90||Math.abs(dec)>23.44){
  out.textContent='请检查输入：纬度应在 −90° 到 90°，直射点纬度约在 ±23.44° 内。';
  return;
 }
 const h=90-Math.abs(lat-dec);
 out.innerHTML='当地纬度：'+lat+'°<br>太阳直射点纬度：'+dec+'°<br>'+
 '纬度差：'+Math.abs(lat-dec)+'°<br><strong>正午太阳高度：'+h.toFixed(2)+'°</strong>'+
 '<br>计算：90° − |'+lat+'° − ('+dec+'°)| = '+h.toFixed(2)+'°';
}
function check(id,choice){
 const answers={
  geoquiz:['B','正确！H=90°−|30°−10°|=70°。'],
  phyquiz:['B','正确！负电荷受力方向与电场方向相反。'],
  chemquiz:['B','正确！阴极发生还原反应。'],
  mathquiz:['B','正确！f(3)=2×3+1=7。'],
  cnquiz:['A','正确！“多数”被改成“所有”，扩大了范围。'],
  enquiz:['A','正确！although 表示让步关系。']
 };
 const a=answers[id];
 const el=document.getElementById(id);
 if(choice===a[0]){
  el.textContent=a[1];
 }else{
  el.textContent='再想一想，回顾相关知识点后重试。';
 }
}
function drawField(){
 const c=document.getElementById('fieldCanvas');
 const ctx=c.getContext('2d');
 const source=Number(document.getElementById('source').value);
 const test=Number(document.getElementById('testCharge').value);
 ctx.clearRect(0,0,c.width,c.height);
 const cx=300,cy=150;
 ctx.strokeStyle='#d9e2f1';ctx.lineWidth=1;
 for(let x=20;x<600;x+=40){
  ctx.beginPath();ctx.moveTo(x,10);ctx.lineTo(x,290);ctx.stroke();
 }
 for(let y=30;y<300;y+=40){
  ctx.beginPath();ctx.moveTo(10,y);ctx.lineTo(590,y);ctx.stroke();
 }
 ctx.strokeStyle='#3570e8';ctx.fillStyle='#3570e8';ctx.lineWidth=2;
 for(let a=0;a<Math.PI*2;a+=Math.PI/4){
  for(let r=45;r<=125;r+=40){
   let x=cx+Math.cos(a)*r,y=cy+Math.sin(a)*r;
   let d=source===1?1:-1;
   let dx=Math.cos(a)*d,dy=Math.sin(a)*d;
   ctx.beginPath();ctx.moveTo(x-dx*12,y-dy*12);
   ctx.lineTo(x+dx*12,y+dy*12);ctx.stroke();
   ctx.beginPath();
   ctx.moveTo(x+dx*12,y+dy*12);
   ctx.lineTo(x+dx*4-dy*5,y+dy*4+dx*5);
   ctx.lineTo(x+dx*4+dy*5,y+dy*4-dx*5);
   ctx.closePath();ctx.fill();
  }
 }
 ctx.beginPath();ctx.arc(cx,cy,19,0,Math.PI*2);
 ctx.fillStyle=source===1?'#e84a5f':'#3478ed';ctx.fill();
 ctx.fillStyle='white';ctx.font='bold 23px sans-serif';
 ctx.textAlign='center';ctx.textBaseline='middle';
 ctx.fillText(source===1?'+':'−',cx,cy);
 const forceDirection=source*test;
 document.getElementById('fieldResult').innerHTML=
 '场源电荷：'+(source===1?'正电荷':'负电荷')+'；试探电荷：'+
 (test===1?'正电荷':'负电荷')+'。<br>电场方向：'+
 (source===1?'由场源电荷向外':'指向场源电荷')+'。<br>试探电荷受力：'+
 (forceDirection===1?'与电场方向相同':'与电场方向相反')+'。';
}
function showCell(){
 const type=document.getElementById('cellType').value;
 const el=document.getElementById('cellResult');
 if(type==='galvanic'){
  el.innerHTML='<strong>原电池：</strong><br>负极：氧化，失去电子。<br>'+
  '正极：还原，得到电子。<br>电子从负极经外电路流向正极。'+
  '<br>口诀：原电池，负氧正还。';
 }else{
  el.innerHTML='<strong>电解池：</strong><br>阳极：氧化，接电源正极。<br>'+
  '阴极：还原，接电源负极。<br>电子经电源和外电路传递，不能把电子说成在电解质溶液中自由移动。'+
  '<br>口诀：电解池，阳氧阴还。';
 }
}
function saveTasks(){
 const tasks=[...document.querySelectorAll('.task')].map(x=>x.checked);
 localStorage.setItem('studyTasks',JSON.stringify(tasks));
 updateTasks();
}
function updateTasks(){
 const saved=JSON.parse(localStorage.getItem('studyTasks')||'[]');
 document.querySelectorAll('.task').forEach((x,i)=>x.checked=!!saved[i]);
 const tasks=[...document.querySelectorAll('.task')];
 const done=tasks.filter(x=>x.checked).length;
 const percent=Math.round(done/tasks.length*100);
 document.getElementById('taskText').textContent='完成度：'+percent+'%（'+done+'/'+tasks.length+'）';
 document.getElementById('taskBar').style.width=percent+'%';
}
function getMistakes(){
 try{return JSON.parse(localStorage.getItem('studyMistakes')||'[]')}
 catch(e){return []}
}
function addMistake(){
 const subject=document.getElementById('mistakeSubject').value;
 const textValue=document.getElementById('mistakeText').value.trim();
 if(!textValue){alert('请先填写错题内容。');return}
 const list=getMistakes();
 list.unshift({subject:subject,text:textValue,date:new Date().toLocaleDateString()});
 localStorage.setItem('studyMistakes',JSON.stringify(list));
 document.getElementById('mistakeText').value='';
 renderMistakes();
}
function renderMistakes(){
 const list=getMistakes();
 const el=document.getElementById('mistakeList');
 if(!list.length){el.innerHTML='<p class="small">还没有保存错题。</p>';return}
 el.innerHTML=list.map((m,i)=>
 '<div class="card"><span class="tag">'+escapeHTML(m.subject)+'</span>'+
 '<span class="small">'+escapeHTML(m.date)+'</span><p>'+
 escapeHTML(m.text)+'</p><button class="action secondary" onclick="deleteMistake('+i+')">删除</button></div>'
 ).join('');
}
function deleteMistake(i){
 const list=getMistakes();list.splice(i,1);
 localStorage.setItem('studyMistakes',JSON.stringify(list));renderMistakes();
}
function escapeHTML(s){
 return String(s).replace(/[&<>"']/g,c=>({
 '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'
 })[c]);
}
function exportMistakes(){
 const data=JSON.stringify(getMistakes(),null,2);
 const blob=new Blob([data],{type:'application/json;charset=utf-8'});
 const url=URL.createObjectURL(blob);
 const a=document.createElement('a');a.href=url;a.download='我的错题本.json';
 a.click();URL.revokeObjectURL(url);
}
updateTasks();
renderMistakes();
calcSun();
drawField();
showCell();
</script>
</body>
</html>
