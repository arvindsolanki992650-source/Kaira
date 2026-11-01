# Kaira
 My All-in-One Social App

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KAIRA - Connect Your World</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#faf9fc;color:#292333;font-family:Arial,sans-serif}
header{background:white;padding:18px;display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid #eee;position:sticky;top:0}
.logo{font-size:28px;font-weight:bold;letter-spacing:3px;background:linear-gradient(90deg,#df579c,#7955d8);color:transparent;background-clip:text}
nav{display:flex;justify-content:center;gap:12px;padding:15px;flex-wrap:wrap}
nav button{border:0;padding:12px 20px;border-radius:12px;background:#eee8f7;color:#7148b5;font-weight:bold}
nav button:hover{background:#df579c;color:white}
main{max-width:850px;margin:20px auto;padding:15px}
.page{display:none}
.page.active{display:block}
.stories{display:flex;gap:18px;overflow:auto;background:white;padding:18px;border-radius:15px}
.story{text-align:center;min-width:65px;font-size:13px}
.circle{width:55px;height:55px;border-radius:50%;background:linear-gradient(135deg,#f5a4c8,#8058d8);margin:auto auto 7px;color:white;display:grid;place-items:center;font-size:20px}
.post,.movie,.music{background:white;padding:18px;border-radius:15px;margin:18px 0}
.post-image{height:260px;border-radius:12px;background:linear-gradient(135deg,#f6c4d8,#b7a9e9);display:grid;place-items:center;color:white;font-size:35px;font-weight:bold}
.actions{display:flex;gap:20px;margin:15px 0}
.actions button{border:0;background:none;font-size:23px}
input,textarea{padding:12px;border:1px solid #ddd;border-radius:10px;width:100%;margin:8px 0}
.primary{background:linear-gradient(90deg,#df579c,#7955d8);color:white;border:0;padding:12px 20px;border-radius:10px;font-weight:bold}
.movie-grid,.music-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:15px}
.poster{height:220px;border-radius:12px;display:grid;place-items:center;text-align:center;color:white;font-size:23px;font-weight:bold;padding:10px}
.p1{background:linear-gradient(140deg,#192d52,#d68a75)}
.p2{background:linear-gradient(140deg,#633b68,#e2a2a5)}
.p3{background:linear-gradient(140deg,#151d48,#8278ca)}
.album{height:150px;border-radius:12px;background:linear-gradient(135deg,#f4a6c5,#7958d6);display:grid;place-items:center;font-size:55px;color:white}
small{color:#888}
@media(max-width:500px){main{padding:10px}.post-image{height:220px}}
</style>
</head>
<body>

<header>
<div class="logo">KAIRA</div>
<div>♡ &nbsp; ✉</div>
</header>

<nav>
<button onclick="show('home')">⌂ Home</button>
<button onclick="show('movies')">🎬 Movies</button>
<button onclick="show('music')">♫ Music</button>
<button onclick="show('profile')">☺ Profile</button>
</nav>

<main>

<section id="home" class="page active">
<h2>Welcome to KAIRA ✨</h2>

<div class="stories">
<div class="story"><div class="circle">+</div>Your Story</div>
<div class="story"><div class="circle">A</div>Aarav</div>
<div class="story"><div class="circle">M</div>Meera</div>
<div class="story"><div class="circle">R</div>Riya</div>
<div class="story"><div class="circle">S</div>Sana</div>
</div>

<h3>Latest Posts</h3>
<div class="post">
<b>aarav.verma</b>
<div class="post-image">MAKE MEMORIES</div>
<div class="actions">
<button onclick="like(this)">♡</button>
<button onclick="alert('Comments section')">▢</button>
<button onclick="alert('Share coming soon')">↗</button>
</div>
<p>24 likes</p>
<p>Collect moments, not things. ✨</p>
</div>

<div class="post">
<b>meera.creates</b>
<div class="post-image">FIND YOUR OWN WAY</div>
<div class="actions">
<button onclick="like(this)">♡</button>
<button>▢</button>
<button>↗</button>
</div>
<p>108 likes</p>
<p>A little progress every day. 🌸</p>
</div>

<h3>Create a post</h3>
<textarea id="newPost" placeholder="What's on your mind?"></textarea>
<button class="primary" onclick="addPost()">Share Post</button>
<div id="newPosts"></div>
</section>

<section id="movies" class="page">
<h2>🎬 KAIRA Movies</h2>
<p>Discover movies and trailers.</p>
<div class="movie-grid">
<div class="movie">
<div class="poster p1">THE LAST HORIZON</div>
<h3>The Last Horizon</h3>
<small>Adventure · Demo title</small>
</div>
<div class="movie">
<div class="poster p2">MONSOON LETTERS</div>
<h3>Monsoon Letters</h3>
<small>Drama · Demo title</small>
</div>
<div class="movie">
<div class="poster p3">BEYOND THE STARS</div>
<h3>Beyond the Stars</h3>
<small>Sci-Fi · Demo title</small>
</div>
</div>
<p><small>Movies and trailers will need authorised video sources.</small></p>
</section>

<section id="music" class="page">
<h2>♫ KAIRA Music</h2>
<p>Discover music and playlists.</p>
<div class="music-grid">
<div class="music">
<div class="album">♫</div>
<h3>Late Night</h3>
<small>Calm music playlist</small>
</div>
<div class="music">
<div class="album">♪</div>
<h3>Good Vibes</h3>
<small>Feel good playlist</small>
</div>
<div class="music">
<div class="album">♥</div>
<h3>My Favourites</h3>
<small>Favourite songs</small>
</div>
</div>
<p><small>Music playback will require original or licensed audio.</small></p>
</section>

<section id="profile" class="page">
<h2>My Profile</h2>
<div class="circle">K</div>
<h3>KAIRA User</h3>
<p>Welcome to your KAIRA profile.</p>
</section>

</main>

<script>
function show(id){
document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
document.getElementById(id).classList.add('active');
window.scrollTo(0,0);
}

function like(button){
button.textContent=button.textContent==='♡'?'♥':'♡';
button.style.color=button.textContent==='♥'?'#df579c':'';
}

function addPost(){
let input=document.getElementById('newPost');
let value=input.value.trim();
if(!value)return;
let post=document.createElement('div');
post.className='post';
let name=document.createElement('b');
name.textContent='KAIRA User';
let caption=document.createElement('p');
caption.textContent=value;
post.append(name,caption);
document.getElementById('newPosts').prepend(post);
input.value='';
}
</script>

</body>
</html>
