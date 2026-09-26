<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#090A18">
<title>PMS Bumper</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    -webkit-tap-highlight-color:transparent;
}

body{
    font-family:Arial,Helvetica,sans-serif;
    background:#070812;
    color:#fff;
    min-height:100vh;
}

button{
    font-family:inherit;
    border:0;
    cursor:pointer;
}

/* ================= SPLASH ================= */

#splash{
    position:fixed;
    inset:0;
    z-index:9999;
    background:
        radial-gradient(circle at 50% 35%,#4b20a8 0%,transparent 32%),
        radial-gradient(circle at 20% 80%,#172a8a 0%,transparent 30%),
        #070812;
    display:flex;
    align-items:center;
    justify-content:center;
    overflow:hidden;
}

.splash-content{
    width:90%;
    max-width:400px;
    text-align:center;
}

.logo-circle{
    width:115px;
    height:115px;
    margin:auto;
    border-radius:34px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:linear-gradient(145deg,#8b5cf6,#3b82f6);
    box-shadow:
        0 0 30px rgba(124,58,237,.65),
        0 0 80px rgba(59,130,246,.25);
    animation:logoPulse 2s infinite;
}

.logo-circle span{
    font-size:42px;
    font-weight:900;
    letter-spacing:-3px;
}

.brand{
    margin-top:25px;
    font-size:38px;
    font-weight:900;
    letter-spacing:-2px;
}

.brand span{
    background:linear-gradient(90deg,#a78bfa,#60a5fa);
    -webkit-background-clip:text;
    color:transparent;
}

.subtitle{
    margin-top:8px;
    color:#9ca3af;
    font-size:14px;
    letter-spacing:2px;
}

.loading-box{
    margin-top:45px;
}

.loading-text{
    display:flex;
    justify-content:space-between;
    font-size:12px;
    color:#9ca3af;
    margin-bottom:9px;
}

.progress{
    width:100%;
    height:7px;
    background:#1d2030;
    border-radius:20px;
    overflow:hidden;
}

.progress-bar{
    width:0%;
    height:100%;
    border-radius:20px;
    background:linear-gradient(90deg,#8b5cf6,#3b82f6);
    box-shadow:0 0 15px #6366f1;
    transition:width .08s linear;
}

.loading-status{
    margin-top:13px;
    font-size:12px;
    color:#777b91;
}

@keyframes logoPulse{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.06)}
}

/* ================= APP ================= */

#app{
    display:none;
    max-width:480px;
    margin:auto;
    min-height:100vh;
    background:
        radial-gradient(circle at 80% 0%,rgba(88,28,135,.25),transparent 28%),
        #080914;
    padding-bottom:90px;
}

/* HEADER */

.header{
    padding:20px 18px 12px;
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.header-logo{
    font-size:23px;
    font-weight:900;
}

.header-logo span{
    color:#8b5cf6;
}

.header-right{
    display:flex;
    gap:10px;
}

.icon-btn{
    width:42px;
    height:42px;
    border-radius:14px;
    background:#151727;
    border:1px solid #272a40;
    color:#fff;
    font-size:18px;
}

/* HERO */

.hero{
    margin:8px 16px 20px;
    padding:23px;
    min-height:190px;
    border-radius:25px;
    position:relative;
    overflow:hidden;
    background:
        radial-gradient(circle at 90% 10%,#5b21b6,transparent 35%),
        linear-gradient(135deg,#1d1645,#111a3b 55%,#10152d);
    border:1px solid #3b326b;
    box-shadow:0 15px 40px rgba(0,0,0,.3);
}

.hero:after{
    content:"";
    position:absolute;
    width:170px;
    height:170px;
    right:-60px;
    bottom:-70px;
    border-radius:50%;
    background:#6366f1;
    filter:blur(55px);
    opacity:.45;
}

.hero small{
    color:#c4b5fd;
    font-weight:bold;
}

.hero h1{
    margin-top:10px;
    font-size:29px;
    line-height:1.1;
}

.hero p{
    color:#b7b9c8;
    font-size:13px;
    margin-top:10px;
    line-height:1.5;
    max-width:280px;
}

.hero-btn{
    margin-top:17px;
    padding:11px 17px;
    border-radius:12px;
    color:#fff;
    font-weight:bold;
    background:linear-gradient(90deg,#7c3aed,#2563eb);
    box-shadow:0 8px 20px rgba(99,102,241,.25);
}

/* SECTION */

.section{
    padding:0 16px;
    margin-top:25px;
}

.section-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:13px;
}

.section-head h2{
    font-size:18px;
}

.section-head button{
    background:none;
    color:#9b7cf7;
    font-size:12px;
}

/* QUICK MENU */

.quick-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:10px;
}

.quick{
    padding:17px 8px;
    text-align:center;
    border-radius:17px;
    background:#121424;
    border:1px solid #24283c;
}

.quick-icon{
    width:42px;
    height:42px;
    margin:auto;
    border-radius:13px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:linear-gradient(145deg,#31206c,#18285e);
    font-size:20px;
}

.quick p{
    margin-top:9px;
    font-size:12px;
    color:#c7c9d5;
}

/* CARDS */

.card-row{
    display:flex;
    gap:13px;
    overflow-x:auto;
    padding-bottom:5px;
}

.card-row::-webkit-scrollbar{
    display:none;
}

.product{
    min-width:165px;
    background:#111321;
    border:1px solid #25283c;
    border-radius:19px;
    overflow:hidden;
}

.product-image{
    height:125px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:
        radial-gradient(circle,#5141a5,transparent 45%),
        linear-gradient(145deg,#191638,#111a35);
    font-size:43px;
}

.product-info{
    padding:12px;
}

.product-info h3{
    font-size:14px;
}

.product-info p{
    color:#85899d;
    font-size:11px;
    margin-top:5px;
}

.product-bottom{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-top:11px;
}

.price{
    font-size:14px;
    font-weight:bold;
    color:#a78bfa;
}

.buy-btn{
    padding:7px 10px;
    border-radius:9px;
    background:#27204c;
    color:#c4b5fd;
    font-size:11px;
    font-weight:bold;
}

/* CELEBRATION */

.celebrate{
    margin:25px 16px;
    padding:18px;
    border-radius:20px;
    background:linear-gradient(135deg,#17132f,#101c35);
    border:1px solid #302d59;
}

.celebrate-top{
    display:flex;
    align-items:center;
    gap:12px;
}

.celebrate-icon{
    width:48px;
    height:48px;
    border-radius:15px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:linear-gradient(145deg,#7c3aed,#2563eb);
    font-size:23px;
}

.celebrate h3{
    font-size:15px;
}

.celebrate p{
    margin-top:4px;
    color:#85899d;
    font-size:11px;
}

/* BOTTOM NAV */

.bottom-nav{
    position:fixed;
    bottom:0;
    left:50%;
    transform:translateX(-50%);
    width:100%;
    max-width:480px;
    height:76px;
    background:rgba(10,11,23,.94);
    backdrop-filter:blur(15px);
    border-top:1px solid #25283c;
    display:grid;
    grid-template-columns:repeat(4,1fr);
    z-index:100;
}

.nav-item{
    background:none;
    color:#696d82;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    gap:5px;
    font-size:11px;
}

.nav-item span{
    font-size:21px;
}

.nav-item.active{
    color:#a78bfa;
}

/* PAGE */

.page{
    display:none;
    padding-bottom:20px;
}

.page.active{
    display:block;
}

.page-title{
    padding:15px 18px 20px;
}

.page-title h1{
    font-size:25px;
}

.page-title p{
    color:#85899d;
    font-size:12px;
    margin-top:6px;
}

/* ORDERS */

.order{
    margin:0 16px 12px;
    padding:15px;
    background:#111321;
    border:1px solid #25283c;
    border-radius:17px;
}

.order-top{
    display:flex;
    justify-content:space-between;
}

.order h3{
    font-size:14px;
}

.status{
    color:#86efac;
    font-size:10px;
    background:#12301f;
    padding:5px 8px;
    border-radius:8px;
}

.order p{
    color:#85899d;
    font-size:11px;
    margin-top:8px;
}

/* PROFILE */

.profile{
    margin:0 16px;
    padding:25px 18px;
    text-align:center;
    background:#111321;
    border:1px solid #25283c;
    border-radius:22px;
}

.avatar{
    width:75px;
    height:75px;
    margin:auto;
    border-radius:25px;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:30px;
    font-weight:bold;
    background:linear-gradient(145deg,#8b5cf6,#2563eb);
}

.profile h2{
    margin-top:13px;
    font-size:19px;
}

.profile p{
    color:#85899d;
    font-size:12px;
    margin-top:5px;
}

.profile-menu{
    margin-top:20px;
    text-align:left;
}

.profile-menu div{
    padding:15px 5px;
    border-bottom:1px solid #24283c;
    font-size:13px;
    color:#c5c7d3;
}

/* TOAST */

#toast{
    position:fixed;
    left:50%;
    bottom:92px;
    transform:translateX(-50%) translateY(20px);
    background:#202235;
    border:1px solid #383c58;
    color:#fff;
    padding:12px 18px;
    border-radius:12px;
    font-size:12px;
    opacity:0;
    pointer-events:none;
    transition:.3s;
    z-index:500;
    white-space:nowrap;
}

#toast.show{
    opacity:1;
    transform:translateX(-50%) translateY(0);
}
</style>
</head>

<body>

<!-- SPLASH SCREEN -->

<div id="splash">
    <div class="splash-content">

        <div class="logo-circle">
            <span>PMS</span>
        </div>

        <div class="brand">
            PMS <span>BUMPER</span>
        </div>

        <div class="subtitle">
            PREMIUM DIGITAL EXPERIENCE
        </div>

        <div class="loading-box">
            <div class="loading-text">
                <span id="loadingStatus">Starting...</span>
                <span id="percent">0%</span>
            </div>

            <div class="progress">
                <div class="progress-bar" id="progressBar"></div>
            </div>

            <div class="loading-status">
                Preparing your experience...
            </div>
        </div>

    </div>
</div>


<!-- MAIN APP -->

<div id="app">

    <!-- HOME -->

    <section id="homePage" class="page active">

        <header class="header">
            <div class="header-logo">
                PMS <span>Bumper</span>
            </div>

            <div class="header-right">
                <button class="icon-btn" onclick="showToast('Notifications coming soon 🔔')">
                    🔔
                </button>

                <button class="icon-btn" onclick="openPage('profile')">
                    👤
                </button>
            </div>
        </header>


        <div class="hero">

            <small>🎉 PMS ARMY CELEBRATION</small>

            <h1>
                Welcome to<br>
                PMS Bumper
            </h1>

            <p>
                Discover premium digital rewards,
                collections and exclusive community offers.
            </p>

            <button class="hero-btn" onclick="openPage('collection')">
                Explore Now →
            </button>

        </div>


        <div class="section">

            <div class="section-head">
                <h2>Quick Access</h2>
            </div>

            <div class="quick-grid">

                <div class="quick" onclick="openPage('collection')">
                    <div class="quick-icon">🛍️</div>
                    <p>Collections</p>
                </div>

                <div class="quick" onclick="showToast('Rewards section opened 🎁')">
                    <div class="quick-icon">🎁</div>
                    <p>Rewards</p>
                </div>

                <div class="quick" onclick="openPage('orders')">
                    <div class="quick-icon">📦</div>
                    <p>Orders</p>
                </div>

            </div>

        </div>


        <div class="section">

            <div class="section-head">
                <h2>Featured</h2>
                <button onclick="openPage('collection')">
                    View All
                </button>
            </div>

            <div class="card-row">

                <div class="product">

                    <div class="product-image">
                        🎮
                    </div>

                    <div class="product-info">

                        <h3>Gaming Reward Pass</h3>

                        <p>Digital reward</p>

                        <div class="product-bottom">

                            <span class="price">
                                ₹49
                            </span>

                            <button class="buy-btn"
                            onclick="showToast('Product details coming soon')">
                                VIEW
                            </button>

                        </div>

                    </div>
                </div>


                <div class="product">

                    <div class="product-image">
                        ⚡
                    </div>

                    <div class="product-info">

                        <h3>PMS Digital Pack</h3>

                        <p>Premium pack</p>

                        <div class="product-bottom">

                            <span class="price">
                                ₹99
                            </span>

                            <button class="buy-btn"
                            onclick="showToast('Product details coming soon')">
                                VIEW
                            </button>

                        </div>

                    </div>
                </div>


                <div class="product">

                    <div class="product-image">
                        💎
                    </div>

                    <div class="product-info">

                        <h3>Premium Reward</h3>

                        <p>Digital benefit</p>

                        <div class="product-bottom">

                            <span class="price">
                                ₹149
                            </span>

                            <button class="buy-btn"
                            onclick="showToast('Product details coming soon')">
                                VIEW
                            </button>

                        </div>

                    </div>
                </div>

            </div>

        </div>


        <div class="celebrate">

            <div class="celebrate-top">

                <div class="celebrate-icon">
                    🏆
                </div>

                <div>
                    <h3>PMS Army Community</h3>

                    <p>
                        More features are coming soon.
                    </p>
                </div>

            </div>

        </div>

    </section>


    <!-- COLLECTION -->

    <section id="collectionPage" class="page">

        <div class="page-title">
            <h1>Collections 🛍️</h1>

            <p>
                Explore available digital products and rewards.
            </p>
        </div>

        <div class="section">

            <div class="card-row" style="flex-wrap:wrap;overflow:visible">

                <div class="product" style="width:calc(50% - 7px);min-width:0">
                    <div class="product-image">🎮</div>

                    <div class="product-info">
                        <h3>Gaming Pass</h3>
                        <p>Digital reward</p>

                        <div class="product-bottom">
                            <span class="price">₹49</span>
                            <button class="buy-btn"
                            onclick="showToast('Coming soon 🚀')">
                                VIEW
                            </button>
                        </div>
                    </div>
                </div>


                <div class="product" style="width:calc(50% - 7px);min-width:0">
                    <div class="product-image">⚡</div>

                    <div class="product-info">
                        <h3>Digital Pack</h3>
                        <p>Premium benefit</p>

                        <div class="product-bottom">
                            <span class="price">₹99</span>
                            <button class="buy-btn"
                            onclick="showToast('Coming soon 🚀')">
                                VIEW
                            </button>
                        </div>
                    </div>
                </div>


                <div class="product" style="width:calc(50% - 7px);min-width:0">
                    <div class="product-image">💎</div>

                    <div class="product-info">
                        <h3>Premium Pack</h3>
                        <p>Digital benefit</p>

                        <div class="product-bottom">
                            <span class="price">₹149</span>
                            <button class="buy-btn"
                            onclick="showToast('Coming soon 🚀')">
                                VIEW
                            </button>
                        </div>
                    </div>
                </div>


                <div class="product" style="width:calc(50% - 7px);min-width:0">
                    <div class="product-image">🔥</div>

                    <div class="product-info">
                        <h3>Special Pack</h3>
                        <p>Community reward</p>

                        <div class="product-bottom">
                            <span class="price">₹199</span>
                            <button class="buy-btn"
                            onclick="showToast('Coming soon 🚀')">
                                VIEW
                            </button>
                        </div>
                    </div>
                </div>

            </div>

        </div>

    </section>


    <!-- ORDERS -->

    <section id="ordersPage" class="page">

        <div class="page-title">
            <h1>My Orders 📦</h1>

            <p>
                Track your digital orders here.
            </p>
        </div>

        <div class="order">

            <div class="order-top">
                <h3>PMS Digital Pack</h3>
                <span class="status">DEMO</span>
            </div>

            <p>
                Order ID: PMS-0001
            </p>

            <p>
                Status: Prototype order
            </p>

        </div>


        <div class="order">

            <div class="order-top">
                <h3>Gaming Reward Pass</h3>
                <span class="status">READY</span>
            </div>

            <p>
                Order ID: PMS-0002
            </p>

            <p>
                Status: Demo
            </p>

        </div>

    </section>


    <!-- PROFILE -->

    <section id="profilePage" class="page">

        <div class="page-title">
            <h1>Profile 👤</h1>

            <p>
                Manage your PMS Bumper account.
            </p>
        </div>

        <div class="profile">

            <div class="avatar">
                PMS
            </div>

            <h2>PMS Army Member</h2>

            <p>
                Welcome to PMS Bumper
            </p>

            <div class="profile-menu">

                <div onclick="showToast('Account settings coming soon')">
                    ⚙️ Account Settings
                </div>

                <div onclick="showToast('Help Center coming soon')">
                    ❓ Help & Support
                </div>

                <div onclick="showToast('Terms page coming soon')">
                    📄 Terms & Conditions
                </div>

            </div>

        </div>

    </section>


    <!-- BOTTOM NAV -->

    <nav class="bottom-nav">

        <button class="nav-item active"
        id="navHome"
        onclick="openPage('home')">
            <span>⌂</span>
            Home
        </button>

        <button class="nav-item"
        id="navCollection"
        onclick="openPage('collection')">
            <span>◈</span>
            Collection
        </button>

        <button class="nav-item"
        id="navOrders"
        onclick="openPage('orders')">
            <span>▣</span>
            Orders
        </button>

        <button class="nav-item"
        id="navProfile"
        onclick="openPage('profile')">
            <span>●</span>
            Profile
        </button>

    </nav>

</div>


<div id="toast">
    Message
</div>


<script>

/* ================= LOADING ================= */

let progress = 0;

const progressBar =
    document.getElementById("progressBar");

const percent =
    document.getElementById("percent");

const loadingStatus =
    document.getElementById("loadingStatus");

const splash =
    document.getElementById("splash");

const app =
    document.getElementById("app");


const messages = [
    "Starting...",
    "Loading PMS...",
    "Preparing dashboard...",
    "Loading rewards...",
    "Almost ready..."
];


const loader = setInterval(() => {

    progress++;

    progressBar.style.width = progress + "%";
    percent.innerText = progress + "%";

    if(progress < 20){
        loadingStatus.innerText = messages[0];
    }
    else if(progress < 40){
        loadingStatus.innerText = messages[1];
    }
    else if(progress < 65){
        loadingStatus.innerText = messages[2];
    }
    else if(progress < 90){
        loadingStatus.innerText = messages[3];
    }
    else{
        loadingStatus.innerText = messages[4];
    }

    if(progress >= 100){

        clearInterval(loader);

        setTimeout(() => {

            splash.style.opacity = "0";
            splash.style.transition = "opacity .5s";

            setTimeout(() => {

                splash.style.display = "none";
                app.style.display = "block";

            },500);

        },400);
    }

},35);


/* ================= PAGE NAVIGATION ================= */

function openPage(page){

    document.querySelectorAll(".page")
        .forEach(p => p.classList.remove("active"));

    document.getElementById(page + "Page")
        .classList.add("active");


    document.querySelectorAll(".nav-item")
        .forEach(n => n.classList.remove("active"));


    if(page === "home"){
        document.getElementById("navHome")
            .classList.add("active");
    }

    if(page === "collection"){
        document.getElementById("navCollection")
            .classList.add("active");
    }

    if(page === "orders"){
        document.getElementById("navOrders")
            .classList.add("active");
    }

    if(page === "profile"){
        document.getElementById("navProfile")
            .classList.add("active");
    }

    window.scrollTo({
        top:0,
        behavior:"smooth"
    });
}


/* ================= TOAST ================= */

let toastTimer;

function showToast(message){

    const toast =
        document.getElementById("toast");

    toast.innerText = message;

    toast.classList.add("show");

    clearTimeout(toastTimer);

    toastTimer = setTimeout(() => {

        toast.classList.remove("show");

    },2200);
}

</script>

</body>
</html>
