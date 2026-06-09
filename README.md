<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>💖 Secret Gift</title>

<style>
body {
  margin:0;
  font-family: Arial;
  background: linear-gradient(135deg,#ffdde1,#ee9ca7);
  text-align:center;
}

/* login */
#login {
  position:fixed;
  width:100%;
  height:100%;
  background:black;
  color:white;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
}

input, button {
  padding:10px;
  border-radius:10px;
  border:none;
  margin-top:10px;
}

/* content */
#content {
  display:none;
  padding:20px;
}

img {
  width:200px;
  border-radius:15px;
  margin:10px;
}

.heart {
  position:absolute;
  color:red;
  animation: float 6s linear infinite;
}

@keyframes float {
  0% {transform: translateY(100vh);}
  100% {transform: translateY(-10vh);}
}
</style>
</head>

<body>

<!-- 🔐 login -->
<div id="login">
  <h2>🔐 Password</h2>
  <input type="password" id="pass" placeholder="enter password">
  <button onclick="check()">Enter</button>
</div>

<!-- 💖 content -->
<div id="content">
  <h1>💖 Welcome 💖</h1>

  <p>💌 رسالة خاصة: أنتِ غالية برشا 💕</p>

  <img src="https://via.placeholder.com/200">
  <img src="https://via.placeholder.com/200">
</div>

<script>
function check(){
  let p = document.getElementById("pass").value;

  if(p === "1234"){
    document.getElementById("login").style.display="none";
    document.getElementById("content").style.display="block";
    startHearts();
  } else {
    alert("❌ Wrong password");
  }
}

function startHearts(){
  setInterval(()=>{
    let heart = document.createElement("div");
    heart.innerHTML = "❤️";
    heart.classList.add("heart");
    heart.style.left = Math.random()*100 + "vw";
    document.body.appendChild(heart);

    setTimeout(()=>{heart.remove()},6000);
  },300);
}
</script>

</body>
</html>
