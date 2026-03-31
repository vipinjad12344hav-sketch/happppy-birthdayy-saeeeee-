# happppy-birthdayy-saeeeee-🍬🍭🎂🌻
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday ❤️</title>

<style>
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    overflow: hidden;
}

/* Reel container */
.container {
    height: 100vh;
    overflow-y: scroll;
    scroll-snap-type: y mandatory;
}

/* Each slide */
.slide {
    height: 100vh;
    scroll-snap-align: start;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: white;
    text-align: center;
    position: relative;
    padding: 20px;
}

/* Backgrounds */
.slide:nth-child(1){background: linear-gradient(#ff758c,#ff7eb3);}
.slide:nth-child(2){background: linear-gradient(#6a11cb,#2575fc);}
.slide:nth-child(3){background: linear-gradient(#ff9966,#ff5e62);}
.slide:nth-child(4){background: linear-gradient(#000000,#434343);}

/* Text */
h1 {
    font-size: 38px;
    animation: fadeUp 1.5s;
}
p {
    font-size: 18px;
    max-width: 300px;
    animation: fadeUp 2s;
}

/* Animation */
@keyframes fadeUp {
    from {opacity:0; transform: translateY(30px);}
    to {opacity:1; transform: translateY(0);}
}

/* Slideshow */
.slideshow {
    width: 220px;
    height: 280px;
    border-radius: 20px;
    overflow: hidden;
    margin-top: 15px;
}
.slideshow img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

/* Typing */
#typing {
    margin-top: 10px;
}

/* Button */
button {
    padding: 12px 25px;
    border-radius: 25px;
    border: none;
    background: white;
    color: black;
    cursor: pointer;
    margin-top: 20px;
}

/* Floating elements */
.float {
    position: fixed;
    bottom: -20px;
    animation: floatUp 6s linear infinite;
}
@keyframes floatUp {
    0% {transform: translateY(0); opacity:1;}
    100% {transform: translateY(-110vh); opacity:0;}
}

/* Sparkles */
.sparkle {
    position: fixed;
    width: 4px;
    height: 4px;
    background: white;
    border-radius: 50%;
    animation: sparkle 3s infinite;
}
@keyframes sparkle {
    0%,100%{opacity:0;}
    50%{opacity:1;}
}
</style>
</head>

<body>

<div class="container">

<!-- Slide 1 -->
<div class="slide">
    <h1>Happy Birthday My Love ❤️</h1>
    <p>Swipe up ⬆️</p>
</div>

<!-- Slide 2 -->
<div class="slide">
    <h1>You Are My Everything 💖</h1>
    <div id="typing"></div>
</div>

<!-- Slide 3 -->
<div class="slide">
    <h1>Our Memories 📸</h1>
    <div class="slideshow">
        <img id="slideImg" src="https://picsum.photos/300/400?1">
    </div>
</div>

<!-- Slide 4 -->
<div class="slide">
    <h1>Forever With You 💍</h1>
    <p>You are my today, tomorrow, and forever ❤️</p>
    <button onclick="showLove()">Tap ❤️</button>
    <p id="final" style="display:none;">I Love You Endlesssss 🥺💖</p>
</div>

</div>

<script>
// Typing effect
const text = "You are the most special part of my life... I love you endlessly ❤️";
let i = 0;
function type() {
    if(i < text.length){
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(type,50);
    }
}
type();

// Slideshow
let imgs = [
"https://picsum.photos/300/400?1",
"https://picsum.photos/300/400?2",
"https://picsum.photos/300/400?3"
];
let idx = 0;
setInterval(()=>{
    idx=(idx+1)%imgs.length;
    document.getElementById("slideImg").src=imgs[idx];
},3000);

// Floating hearts & roses
setInterval(()=>{
    let el=document.createElement("div");
    el.className="float";
    el.innerHTML=Math.random()>0.5?"❤️":"🌹";
    el.style.left=Math.random()*100+"vw";
    el.style.fontSize=(Math.random()*20+15)+"px";
    document.body.appendChild(el);
    setTimeout(()=>el.remove(),6000);
},300);

// Sparkles
setInterval(()=>{
    let sp=document.createElement("div");
    sp.className="sparkle";
    sp.style.left=Math.random()*100+"vw";
    sp.style.top=Math.random()*100+"vh";
    document.body.appendChild(sp);
    setTimeout(()=>sp.remove(),3000);
},200);

// Final message
function showLove(){
    document.getElementById("final").style.display="block";
}
</script>

</body>
</html>
