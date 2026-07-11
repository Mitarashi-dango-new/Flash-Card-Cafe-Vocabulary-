<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>Cafe Vocabulary Review</title>

<link href="https://fonts.googleapis.com/css2?family=Kiwi+Maru:wght@400;500;700&display=swap" rel="stylesheet">

<style>

*{margin:0;padding:0;box-sizing:border-box;}

body{
    font-family:'Kiwi Maru',serif;
    background:#f6efe7;
    color:#5c4635;
}

/* ヘッダー */
.header{
    position:sticky;
    top:0;
    background:#f6efe7;
    padding:14px;
    border-bottom:1px solid #e7d7c9;
}

.header h1{
    font-size:20px;
    color:#6f4e37;
}

.tabs{
    display:flex;
    gap:10px;
    margin-top:10px;
}

.tab-btn{
    flex:1;
    padding:10px;
    border:none;
    border-radius:14px;
    background:#fff;
    font-weight:700;
}

.tab-btn.active{
    background:#6f4e37;
    color:white;
}

.container{
    padding:16px;
}

/* セクション */
.section{
    background:#fffaf5;
    padding:14px;
    border-radius:18px;
    margin-bottom:14px;
    box-shadow:0 5px 15px rgba(0,0,0,0.06);
}

/* 入力 */
input, select{
    width:100%;
    padding:12px;
    margin-bottom:10px;
    border-radius:12px;
    border:1px solid #e7d7c9;
}

/* ボタン */
.btn{
    width:100%;
    padding:12px;
    border:none;
    border-radius:12px;
    background:#a47148;
    color:white;
    font-weight:700;
}

/* カテゴリ */
.category-item{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:10px;
    border-radius:12px;
    background:#fff;
    margin-bottom:8px;
    border:1px solid #e7d7c9;
}

/* ×ボタン */
.x-btn{
    background:#b08968;
    color:#fffaf5;
    border:none;
    border-radius:6px;
    width:20px;
    height:20px;
    font-size:12px;
    font-weight:700;
    display:flex;
    align-items:center;
    justify-content:center;
    cursor:pointer;
    opacity:0.85;
}

/* 単語カード */
.list{
    display:flex;
    flex-direction:column;
    gap:12px;
}

.card{
    background:#fffaf5;
    padding:16px;
    border-radius:18px;
    position:relative;
}

.word{
    font-size:20px;
    font-weight:700;
}

.category{
    font-size:12px;
    color:#a47148;
}

.meaning{
    margin-top:10px;
    display:none;
}

.card.show .meaning{display:block;}

.buttons{
    margin-top:12px;
    display:none;
    gap:8px;
}

.card.show .buttons{display:flex;}

.ok{background:#6b8e23;}
.ng{background:#b45309;}

.miss{
    margin-top:10px;
    font-size:13px;
    color:#c2410c;
}

/* 単語削除 */
.delete-word{
    position:absolute;
    top:10px;
    right:10px;
}

/* ページ */
.page{display:none;}
.page.active{display:block;}

/* ★追加：モードボタン */
.mode-bar{
    display:flex;
    gap:10px;
    margin-bottom:10px;
}

.mode-btn{
    flex:1;
    padding:10px;
    border:none;
    border-radius:12px;
    background:#ddd;
    font-weight:700;
}

.mode-btn.active{
    background:#6f4e37;
    color:white;
}

</style>
</head>

<body>

<div class="header">
    <h1>☕ Cafe Vocabulary</h1>

    <div class="tabs">
        <button class="tab-btn active" onclick="show('manage')">管理</button>
        <button class="tab-btn" onclick="show('study')">学習</button>
    </div>
</div>

<div class="container">

<!-- 管理 -->
<div id="manage" class="page active">

    <div class="section">
        <h3>📂 カテゴリ</h3>

        <input id="newCategory" placeholder="カテゴリ追加">
        <button class="btn" onclick="addCategory()">追加</button>

        <div id="categoryList"></div>
    </div>

    <div class="section">
        <h3>📚 単語追加</h3>

        <select id="categorySelect"></select>

        <input id="word" placeholder="単語">
        <input id="meaning" placeholder="意味">

        <button class="btn" onclick="addWord()">追加</button>
    </div>

    <div id="manageList" class="list"></div>

</div>

<!-- 学習 -->
<div id="study" class="page">

    <!-- ★追加：復習モードUI -->
    <div class="section">

        <div class="mode-bar">
            <button id="allBtn" class="mode-btn active" onclick="setMode('all')">全単語</button>
            <button id="reviewBtn" class="mode-btn" onclick="setMode('review')">復習</button>
        </div>

    </div>

    <div class="section">
        <select id="studyFilter" onchange="renderStudy()"></select>
    </div>

    <div id="studyList" class="list"></div>

</div>

</div>

<script>

let words = JSON.parse(localStorage.getItem("words")) || [];
let categories = JSON.parse(localStorage.getItem("categories")) || ["未分類"];

/* ★追加：モード */
let mode = "all";

function save(){
    localStorage.setItem("words", JSON.stringify(words));
    localStorage.setItem("categories", JSON.stringify(categories));
}

function show(page){
    document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
    document.getElementById(page).classList.add("active");

    document.querySelectorAll(".tab-btn").forEach(b=>b.classList.remove("active"));
    event.target.classList.add("active");
}

/* ★追加：モード切替 */
function setMode(m){
    mode = m;

    document.getElementById("allBtn").classList.remove("active");
    document.getElementById("reviewBtn").classList.remove("active");

    if(m === "all"){
        document.getElementById("allBtn").classList.add("active");
    } else {
        document.getElementById("reviewBtn").classList.add("active");
    }

    renderStudy();
}

/* 追加 */
function addCategory(){
    const c = newCategory.value.trim();
    if(!c) return;
    if(!categories.includes(c)) categories.push(c);
    save();
    render();
    newCategory.value="";
}

function deleteCategory(name){
    if(!confirm("削除しますか？")) return;
    categories = categories.filter(c=>c!==name);
    words.forEach(w=>{if(w.category===name) w.category="未分類";});
    save();
    render();
}

function addWord(){
    const w=word.value.trim();
    const m=meaning.value.trim();
    const c=categorySelect.value;

    if(!w||!m){alert("入力してください");return;}

    words.push({word:w,meaning:m,category:c,miss:0});
    save();
    render();

    word.value="";
    meaning.value="";
}

function deleteWord(i){
    if(!confirm("削除しますか？")) return;
    words.splice(i,1);
    save();
    render();
}

function ok(e,i){
    e.stopPropagation();
    if(words[i].miss>0) words[i].miss--;
    save();
    render();
}

function ng(e,i){
    e.stopPropagation();
    words[i].miss++;
    save();
    render();
}

function openCard(i){
    document.getElementById("card-"+i).classList.add("show");
}

/* 描画 */
function renderCategories(){
    const el=document.getElementById("categoryList");
    el.innerHTML="";
    categories.forEach(c=>{
        el.innerHTML+=`
        <div class="category-item">
            <span>${c}</span>
            <button class="x-btn" onclick="deleteCategory('${c}')">×</button>
        </div>`;
    });
}

function renderSelects(){
    const sel=categorySelect;
    const filter=studyFilter;

    sel.innerHTML="";
    filter.innerHTML=`<option value="all">すべて</option>`;

    categories.forEach(c=>{
        sel.innerHTML+=`<option value="${c}">${c}</option>`;
        filter.innerHTML+=`<option value="${c}">${c}</option>`;
    });
}

function renderManage(){
    const el=document.getElementById("manageList");
    el.innerHTML="";
    words.forEach((v,i)=>{
        el.innerHTML+=`
        <div class="card">
            <div class="delete-word">
                <button class="x-btn" onclick="deleteWord(${i})">×</button>
            </div>
            <div class="word">${v.word}</div>
            <div class="category">📂 ${v.category}</div>
            <div class="meaning">${v.meaning}</div>
            <div class="miss">ミス: ${v.miss}</div>
        </div>`;
    });
}

/* ★修正：復習モード追加 */
function renderStudy(){

    const filter=studyFilter.value;
    const el=document.getElementById("studyList");

    el.innerHTML="";

    let list = filter === "all"
        ? words
        : words.filter(v=>v.category===filter);

    // ★ここが復習モード
    if(mode === "review"){
        list = list.filter(v=>v.miss > 0);
    }

    list.forEach(v=>{
        const i=words.indexOf(v);

        el.innerHTML+=`
        <div class="card" id="card-${i}" onclick="openCard(${i})">
            <div class="word">${v.word}</div>
            <div class="category">📂 ${v.category}</div>
            <div class="meaning">${v.meaning}</div>

            <div class="buttons">
                <button class="btn ok" onclick="ok(event,${i})">正解</button>
                <button class="btn ng" onclick="ng(event,${i})">不正解</button>
            </div>

            <div class="miss">ミス: ${v.miss}</div>
        </div>`;
    });
}

function render(){
    renderCategories();
    renderSelects();
    renderManage();
    renderStudy();
}

render();

</script>

</body>
</html>
