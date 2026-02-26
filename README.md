# Fit4Liffe
Moderna Fitness aplikacija za Hrvatske stanovnike
<!DOCTYPE html>
<html lang="hr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fitness Life Simulacija</title>

<link rel="stylesheet" href="css/style.css">
<link rel="stylesheet" href="css/animations.css">

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>

<body>

<nav class="navbar">
    <div class="logo">FITNESS PRO</div>
    <ul class="nav-links">
        <li><a href="#home">Početna</a></li>
        <li><a href="#programi">Programi</a></li>
        <li><a href="#vjezbe">Vježbe</a></li>
        <li><a href="#prehrana">Prehrana</a></li>
        <li><a href="#kalkulator">Kalkulator</a></li>
        <li><a href="#napredak">Napredak</a></li>
    </ul>
</nav>

<section id="home" class="hero">
    <video autoplay muted loop class="hero-video">
        <source src="assets/video/fitness-bg.mp4" type="video/mp4">
    </video>
    <div class="hero-overlay"></div>
    <div class="hero-content">
        <h1 class="fade-in">Transformiraj svoje tijelo</h1>
        <p class="fade-in-delay">Plan. Disciplina. Rezultat.</p>
        <a href="#programi" class="btn-primary">Kreni odmah</a>
    </div>
</section>

<section id="programi" class="section section-dark">
    <h2 class="section-title">Odaberi cilj</h2>
    <div class="cards">
        <div class="card">
            <h3>Masa</h3>
            <p>Specifične vježbe i kalorijski suficit.</p>
        </div>
        <div class="card">
            <h3>Definicija</h3>
            <p>Smanjenje masti uz očuvanje mišića.</p>
        </div>
        <div class="card">
            <h3>Snaga</h3>
            <p>Powerlifting pristup i progresivno opterećenje.</p>
        </div>
    </div>
</section>

<section id="vjezbe" class="section section-image">
    <h2 class="section-title">Vježbe</h2>
    <div class="placeholder-large">
        Ovdje će u FAZI 2 doći detaljne vježbe sa slikama.
    </div>
</section>

<section id="prehrana" class="section section-dark">
    <h2 class="section-title">Prehrana</h2>
    <div class="placeholder-large">
        FAZA 3 – detaljna prehrana + cijene + budžet.
    </div>
</section>

<section id="kalkulator" class="section section-image">
    <h2 class="section-title">Kalorijski Kalkulator</h2>
    <div class="calculator-box">
        <input type="number" id="tezina" placeholder="Težina (kg)">
        <input type="number" id="visina" placeholder="Visina (cm)">
        <input type="number" id="godine" placeholder="Godine">
        <select id="spol">
            <option value="musko">Muško</option>
            <option value="zensko">Žensko</option>
        </select>
        <button onclick="izracunaj()">Izračunaj</button>
        <h3 id="rezultat"></h3>
    </div>
</section>

<section id="napredak" class="section section-dark">
    <h2 class="section-title">Graf Napretka</h2>
    <canvas id="progressChart"></canvas>
</section>

<footer>
    <p>© 2026 Fitness Pro | Sva prava pridržana</p>
</footer>

<script src="js/main.js"></script>
</body>
</html>
* {
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins', sans-serif;
}

body {
    background:#0f0f0f;
    color:white;
    scroll-behavior:smooth;
}

.navbar {
    position:fixed;
    width:100%;
    top:0;
    display:flex;
    justify-content:space-between;
    padding:20px 60px;
    background:rgba(0,0,0,0.7);
    backdrop-filter:blur(10px);
    z-index:1000;
}

.nav-links {
    list-style:none;
    display:flex;
    gap:30px;
}

.nav-links a {
    color:white;
    text-decoration:none;
    transition:0.3s;
}

.nav-links a:hover {
    color:#00ffae;
}

.hero {
    position:relative;
    height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
}

.hero-video {
    position:absolute;
    width:100%;
    height:100%;
    object-fit:cover;
}

.hero-overlay {
    position:absolute;
    width:100%;
    height:100%;
    background:rgba(0,0,0,0.6);
}

.hero-content {
    position:relative;
    z-index:2;
}

.btn-primary {
    padding:15px 40px;
    background:#00ffae;
    border:none;
    border-radius:30px;
    color:black;
    font-weight:600;
    text-decoration:none;
}

.section {
    padding:120px 10%;
    text-align:center;
}

.section-dark {
    background:linear-gradient(135deg,#141414,#1f1f1f);
}

.section-image {
    background:url('../assets/images/bg-section.jpg') center/cover no-repeat;
}

.section-title {
    font-size:36px;
    margin-bottom:40px;
}

.cards {
    display:flex;
    justify-content:center;
    gap:40px;
}

.card {
    background:rgba(255,255,255,0.05);
    padding:30px;
    border-radius:20px;
    width:300px;
    backdrop-filter:blur(10px);
    transition:0.3s;
}

.card:hover {
    transform:translateY(-10px);
}

.calculator-box {
    display:flex;
    flex-direction:column;
    gap:15px;
    max-width:400px;
    margin:0 auto;
}

input, select {
    padding:10px;
    border-radius:10px;
    border:none;
}

button {
    padding:10px;
    border:none;
    border-radius:10px;
    background:#00ffae;
}

footer {
    padding:40px;
    text-align:center;
    background:#111;
}
.fade-in {
    animation:fadeIn 1.5s ease-in-out;
}

.fade-in-delay {
    animation:fadeIn 2.5s ease-in-out;
}

@keyframes fadeIn {
    from { opacity:0; transform:translateY(30px); }
    to { opacity:1; transform:translateY(0); }
}
function izracunaj() {
    let tezina = document.getElementById("tezina").value;
    let visina = document.getElementById("visina").value;
    let godine = document.getElementById("godine").value;
    let spol = document.getElementById("spol").value;

    let bmr;

    if(spol === "musko") {
        bmr = 10*tezina + 6.25*visina - 5*godine + 5;
    } else {
        bmr = 10*tezina + 6.25*visina - 5*godine - 161;
    }

    document.getElementById("rezultat").innerText = 
    "Tvoj dnevni kalorijski unos: " + Math.round(bmr) + " kcal";
}

const ctx = document.getElementById('progressChart').getContext('2d');

new Chart(ctx, {
    type: 'line',
    data: {
        labels: ['Tjedan 1','Tjedan 2','Tjedan 3','Tjedan 4'],
        datasets: [{
            label: 'Napredak (kg)',
            data: [80,78,77,75],
            borderColor: '#00ffae',
            borderWidth: 3
        }]
    }
});
<section id="vjezbe" class="section section-image">
    <h2 class="section-title">Vježbe po cilj</h2>
    <div class="workout-tabs">
        <button class="tab-btn active" onclick="showGoal('masa')">Masa</button>
        <button class="tab-btn" onclick="showGoal('definicija')">Definicija</button>
        <button class="tab-btn" onclick="showGoal('snaga')">Snaga</button>
    </div>

    <div id="workoutContainer" class="workout-grid">
        <!-- Vježbe se učitavaju ovdje preko JS -->
    </div>
</section>
.workout-tabs {
    display:flex;
    justify-content:center;
    gap:20px;
    margin-bottom:40px;
}

.tab-btn {
    padding:10px 30px;
    border:none;
    border-radius:20px;
    background:rgba(255,255,255,0.1);
    color:white;
    font-weight:600;
    cursor:pointer;
    transition:0.3s;
}

.tab-btn.active,
.tab-btn:hover {
    background:#00ffae;
    color:black;
}

.workout-card {
    background:rgba(0,0,0,0.6);
    border-radius:15px;
    padding:20px;
    text-align:center;
    transition:0.3s;
}

.workout-card:hover {
    transform:translateY(-10px);
}

.workout-card img {
    width:100%;
    border-radius:10px;
    margin-bottom:10px;
}

.workout-name {
    font-size:20px;
    margin-bottom:5px;
    font-weight:600;
}

.workout-desc {
    font-size:14px;
    color:#ddd;
}
// FAZA 2 – Baza vježbi
const vjezbe = {
    masa: [
        {name:"Bench Press", img:"assets/images/vjezbe/bench.jpg", desc:"3-4 serije, 8-12 ponavljanja. Fokus na prsa i triceps."},
        {name:"Deadlift", img:"assets/images/vjezbe/deadlift.jpg", desc:"3 serije, 5-8 ponavljanja. Fokus na leđa i noge."},
        {name:"Squat", img:"assets/images/vjezbe/squat.jpg", desc:"4 serije, 6-10 ponavljanja. Fokus na kvadricepse i gluteus."},
        {name:"Shoulder Press", img:"assets/images/vjezbe/shoulder.jpg", desc:"3-4 serije, 8-12 ponavljanja. Ramena i triceps."},
        {name:"Barbell Row", img:"assets/images/vjezbe/barbell-row.jpg", desc:"3 serije, 8-12 ponavljanja. Leđa i biceps."}
    ],
    definicija: [
        {name:"Push-Ups", img:"assets/images/vjezbe/pushup.jpg", desc:"4 serije do otkaza. Prsa, ramena, core."},
        {name:"Pull-Ups", img:"assets/images/vjezbe/pullup.jpg", desc:"3-4 serije, max ponavljanja. Leđa i biceps."},
        {name:"Lunges", img:"assets/images/vjezbe/lunge.jpg", desc:"3 serije, 12-15 ponavljanja po nozi. Noge i gluteus."},
        {name:"Plank", img:"assets/images/vjezbe/plank.jpg", desc:"3 serije po 60 sekundi. Core i stabilnost."},
        {name:"Mountain Climber", img:"assets/images/vjezbe/mountain.jpg", desc:"4 serije po 30 sekundi. Cardio i core."}
    ],
    snaga: [
        {name:"Power Clean", img:"assets/images/vjezbe/powerclean.jpg", desc:"4 serije, 3-5 ponavljanja. Full body power."},
        {name:"Front Squat", img:"assets/images/vjezbe/frontsquat.jpg", desc:"3-4 serije, 4-6 ponavljanja. Noge i core."},
        {name:"Overhead Press", img:"assets/images/vjezbe/ohp.jpg", desc:"4 serije, 3-6 ponavljanja. Ramena i triceps."},
        {name:"Weighted Pull-Up", img:"assets/images/vjezbe/weightedpullup.jpg", desc:"3 serije, 4-6 ponavljanja. Leđa i biceps."},
        {name:"Deadlift", img:"assets/images/vjezbe/deadlift.jpg", desc:"3 serije, 3-5 ponavljanja. Leđa i noge."}
    ]
};

let currentGoal = "masa";

function showGoal(goal){
    currentGoal = goal;
    document.querySelectorAll(".tab-btn").forEach(btn => btn.classList.remove("active"));
    document.querySelector(`.tab-btn[onclick="showGoal('${goal}')"]`).classList.add("active");
    renderWorkouts();
}

function renderWorkouts(){
    const container = document.getElementById("workoutContainer");
    container.innerHTML = "";
    vjezbe[currentGoal].forEach(v => {
        const card = document.createElement("div");
        card.classList.add("workout-card","fade-in");
        card.innerHTML = `
            <img src="${v.img}" alt="${v.name}">
            <div class="workout-name">${v.name}</div>
            <div class="workout-desc">${v.desc}</div>
        `;
        container.appendChild(card);
    });
}

// inicijalno učitavanje
renderWorkouts();
<section id="prehrana" class="section section-dark">
    <h2 class="section-title">Detaljna Prehrana</h2>

    <div class="meal-grid">
        <div class="meal-card">
            <h3>Doručak</h3>
            <div id="breakfastContainer"></div>
        </div>
        <div class="meal-card">
            <h3>Ručak</h3>
            <div id="lunchContainer"></div>
        </div>
        <div class="meal-card">
            <h3>Večera</h3>
            <div id="dinnerContainer"></div>
        </div>
        <div class="meal-card">
            <h3>Snack</h3>
            <div id="snackContainer"></div>
        </div>
    </div>

    <div class="budget-calculator">
        <h3>Kalkulator Budžeta</h3>
        <select id="foodSelect"></select>
        <input type="number" id="foodQuantity" placeholder="Količina (g)">
        <button onclick="calculateBudget()">Izračunaj trošak</button>
        <p id="budgetResult"></p>
    </div>
</section>
.meal-grid {
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:30px;
    margin-top:40px;
}

.meal-card {
    background:rgba(255,255,255,0.05);
    padding:20px;
    border-radius:20px;
    backdrop-filter:blur(10px);
}

.meal-card img {
    width:100%;
    border-radius:10px;
    margin-bottom:10px;
}

.budget-calculator {
    margin-top:50px;
    max-width:400px;
    margin-left:auto;
    margin-right:auto;
    display:flex;
    flex-direction:column;
    gap:15px;
    text-align:center;
}

.budget-calculator input,
.budget-calculator select,
.budget-calculator button {
    padding:10px;
    border:none;
    border-radius:10px;
}

.budget-calculator button {
    background:#00ffae;
    color:black;
    font-weight:600;
    cursor:pointer;
}
// FAZA 3 – baza hrane sa slikama, kalorijama i cijenama po 100g
const foodData = [
    {name:"Jaja", img:"assets/images/hrana/eggs.jpg", calories:155, price:2.5},
    {name:"Piletina", img:"assets/images/hrana/chicken.jpg", calories:165, price:1.8},
    {name:"Riža", img:"assets/images/hrana/rice.jpg", calories:130, price:0.8},
    {name:"Zeleno povrće", img:"assets/images/hrana/veggies.jpg", calories:25, price:1.2},
    {name:"Banana", img:"assets/images/hrana/banana.jpg", calories:89, price:0.9},
    {name:"Orašasti plodovi", img:"assets/images/hrana/nuts.jpg", calories:600, price:3.5},
    {name:"Losos", img:"assets/images/hrana/salmon.jpg", calories:208, price:4.0},
    {name:"Quinoa", img:"assets/images/hrana/quinoa.jpg", calories:120, price:1.5}
];

// plan obroka
const mealPlan = {
    breakfast:["Jaja","Banana"],
    lunch:["Piletina","Riža","Zeleno povrće"],
    dinner:["Losos","Quinoa","Zeleno povrće"],
    snack:["Orašasti plodovi","Banana"]
};

// funkcija za render obroka
function renderMeals(){
    const mapMeal = {
        breakfast:"breakfastContainer",
        lunch:"lunchContainer",
        dinner:"dinnerContainer",
        snack:"snackContainer"
    };
    for(let meal in mealPlan){
        const container = document.getElementById(mapMeal[meal]);
        container.innerHTML = "";
        mealPlan[meal].forEach(foodName => {
            const food = foodData.find(f => f.name === foodName);
            const div = document.createElement("div");
            div.classList.add("meal-item","fade-in");
            div.innerHTML = `
                <img src="${food.img}" alt="${food.name}">
                <strong>${food.name}</strong>
                <p>${food.calories} kcal | Cijena: ${food.price} HRK / 100g</p>
            `;
            container.appendChild(div);
        });
    }

    // popuni select za kalkulator
    const foodSelect = document.getElementById("foodSelect");
    foodSelect.innerHTML = "";
    foodData.forEach(f => {
        const option = document.createElement("option");
        option.value = f.name;
        option.text = f.name;
        foodSelect.appendChild(option);
    });
}

// kalkulator budžeta
function calculateBudget(){
    const selectedFood = document.getElementById("foodSelect").value;
    const quantity = parseFloat(document.getElementById("foodQuantity").value);
    if(!quantity || quantity<=0){ alert("Unesi količinu"); return; }
    const food = foodData.find(f => f.name === selectedFood);
    const cost = (food.price * quantity / 100).toFixed(2);
    document.getElementById("budgetResult").innerText = 
        `Trošak ${quantity}g ${food.name}: ${cost} HRK`;
}

// inicijalno učitavanje
renderMeals();
<section id="napredak" class="section section-dark">
    <h2 class="section-title">Praćenje Napretka</h2>
    
    <div class="progress-inputs">
        <input type="number" id="weightInput" placeholder="Unesi težinu (kg)">
        <button onclick="addWeight()">Spremi težinu</button>
    </div>

    <canvas id="progressChart"></canvas>
</section>
.progress-inputs {
    display:flex;
    justify-content:center;
    gap:15px;
    margin-bottom:30px;
}

.progress-inputs input {
    padding:10px;
    border-radius:10px;
    border:none;
    width:150px;
}

.progress-inputs button {
    padding:10px 20px;
    border:none;
    border-radius:10px;
    background:#00ffae;
    font-weight:600;
    cursor:pointer;
}
// FAZA 4 – Praćenje težine + Chart.js
let weights = JSON.parse(localStorage.getItem("weights")) || [];

const ctx = document.getElementById('progressChart').getContext('2d');

const chart = new Chart(ctx, {
    type: 'line',
    data: {
        labels: weights.map((w,i)=>`Tjedan ${i+1}`),
        datasets: [{
            label: 'Težina (kg)',
            data: weights,
            borderColor: '#00ffae',
            borderWidth: 3,
            fill:false,
            tension:0.2
        }]
    },
    options:{
        responsive:true,
        plugins:{legend:{display:true}},
        scales:{
            y:{beginAtZero:false}
        }
    }
});

function addWeight(){
    const w = parseFloat(document.getElementById("weightInput").value);
    if(!w || w<=0){ alert("Unesi ispravnu težinu"); return; }
    weights.push(w);
    localStorage.setItem("weights", JSON.stringify(weights));
    updateChart();
    document.getElementById("weightInput").value="";
}

function updateChart(){
    chart.data.labels = weights.map((w,i)=>`Tjedan ${i+1}`);
    chart.data.datasets[0].data = weights;
    chart.update();
}
