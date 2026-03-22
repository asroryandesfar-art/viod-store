Use this shared code block as the starting point. When you respond with code, return the full updated code block, not just a diff or excerpt.

```html
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>VOID Studio</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>

/* ================= BASE ================= */
*{margin:0;padding:0;box-sizing:border-box;}

body{
    font-family:'Poppins',sans-serif;
    color:#fff;
    overflow-x:hidden;
}

/* ================= BACKGROUND IMAGE ================= */
/* GANTI LINK INI SESUAI STYLE KAMU */
body::before{
    content:"";
    position:fixed;
    inset:0;
    background:url('https://images.unsplash.com/photo-1492724441997-5dc865305da7?q=80&w=1920') center/cover no-repeat;
    z-index:-2;
}

/* overlay gelap biar elegan */
body::after{
    content:"";
    position:fixed;
    inset:0;
    background:rgba(0,0,0,0.6);
    z-index:-1;
}

/* dark mode lebih dalam */
body.dark::after{
    background:rgba(0,0,0,0.8);
}

.container{
    width:90%;
    max-width:1200px;
    margin:auto;
}

/* ================= NAV ================= */
nav{
    display:flex;
    justify-content:space-between;
    padding:25px 0;
}

.logo{
    font-weight:700;
    letter-spacing:2px;
}

.toggle{
    border:none;
    padding:8px 14px;
    border-radius:20px;
    background:#fff;
    color:#000;
    cursor:pointer;
}

/* ================= HERO ================= */
.hero{
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
}

.hero h1{
    font-size:clamp(40px,7vw,90px);
    line-height:1;
}

/* gradient elegan */
.gradient{
    background:linear-gradient(90deg,#fff,#aaa,#fff);
    -webkit-background-clip:text;
    color:transparent;
}

/* stroke */
.stroke{
    color:transparent;
    -webkit-text-stroke:1px #fff;
}

.hero p{
    margin-top:20px;
    max-width:500px;
    opacity:0.7;
}

/* ================= BUTTON ================= */
.btn{
    margin-top:30px;
    display:inline-block;
    padding:14px 30px;
    border-radius:40px;
    text-decoration:none;
    background:#fff;
    color:#000;
    transition:0.3s;
}

.btn:hover{
    transform:scale(1.05);
}

/* ================= SECTION ================= */
.section{
    margin-top:120px;
}

/* ================= PORTFOLIO ================= */
.portfolio{
    display:grid;
    gap:30px;
}

.work{
    padding:40px;
    border-radius:20px;
    backdrop-filter:blur(10px);
    background:rgba(255,255,255,0.1);
    transition:0.4s;
}

.work:hover{
    transform:scale(1.03);
}

.work h3{
    font-size:24px;
}

.work p{
    opacity:0.7;
}

/* ================= BIG TEXT ================= */
.big-text{
    font-size:clamp(60px,10vw,140px);
    font-weight:700;
    opacity:0.05;
}

/* ================= CTA ================= */
.cta{
    margin:150px 0;
}

/* ================= MOBILE ================= */
@media(max-width:600px){
    .hero{
        height:auto;
        padding:100px 0;
    }
}

</style>
</head>

<body>

<div class="container">

<!-- NAV -->
<nav>
    <div class="logo">VOID</div>
    <button class="toggle" onclick="toggleDark()">Mode</button>
</nav>

<!-- HERO -->
<section class="hero">
    <h1>
        We Build<br>
        <span class="gradient">Perception</span><br>
        <span class="stroke">Not Just Design</span>
    </h1>

    <p>
        Studio kreatif yang fokus pada bagaimana brand kamu dirasakan,
        bukan hanya dilihat.
    </p>

    <a href="#" class="btn">Start Project</a>
</section>

<div class="big-text">WORK</div>

<!-- PORTFOLIO -->
<section class="section portfolio">

    <div class="work">
        <h3>Luxury Website</h3>
        <p>Visual premium kelas atas</p>
    </div>

    <div class="work">
        <h3>Startup UI</h3>
        <p>Modern & scalable design</p>
    </div>

    <div class="work">
        <h3>Brand Identity</h3>
        <p>Karakter brand yang kuat</p>
    </div>

</section>

<!-- CTA -->
<section class="cta">
    <h2>Let’s Create Something Powerful</h2>
    <a href="#" class="btn">Contact Us</a>
</section>

</div>

<script>

// DARK MODE
function toggleDark(){
    document.body.classList.toggle("dark");
    localStorage.setItem("theme",
        document.body.classList.contains("dark") ? "dark" : "light"
    );
}

if(localStorage.getItem("theme")==="dark"){
    document.body.classList.add("dark");
}

</script>

</body>
</html>
