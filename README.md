# Diary
My virtual diary
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Diary</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display&family=Cormorant+Garamond&display=swap');

body {
  margin: 0;
  background: #f6ece8;
  font-family: 'Cormorant Garamond', serif;
  color: #4a2f24;
}

.cover {
  height: 100vh;
  background: radial-gradient(circle at top, #f2d9d2, #e8c4bb);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  animation: fadeIn 2s;
}

.cover h1 {
  font-size: 42px;
  letter-spacing: 3px;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.book {
  display: none;
  padding: 40px 20px;
  animation: openBook 1.5s ease forwards;
}

@keyframes openBook {
  from { transform: scale(0.9); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}

.page {
  max-width: 700px;
  margin: 0 auto 80px;
  padding: 40px;
  background:
    repeating-linear-gradient(
      #f6ece8,
      #f6ece8 24px,
      #e9d2cc 25px
    );
  box-shadow: inset 0 0 40px rgba(0,0,0,0.08);
}

.text {
  font-size: 18px;
  line-height: 2;
}

.button {
  margin-top: 25px;
  padding: 10px 20px;
  border: none;
  background: #d9b2a9;
  color: #4a2f24;
  font-family: inherit;
  cursor: pointer;
  transition: transform 0.3s;
}

.button:hover {
  transform: scale(1.05);
}

.info {
  display: none;
  margin-top: 20px;
  padding: 20px;
  border-left: 2px solid #4a2f24;
  animation: slideDown 0.6s ease;
}

@keyframes slideDown {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>

<div class="cover" onclick="openDiary()">
  <h1>my diary</h1>
</div>

<div class="book" id="book">

  <div class="page">
    <div class="text">
      Aqui vai a primeira parte do texto do seu plot.
    </div>
    <button class="button" onclick="toggleInfo(this)">details</button>
    <div class="info">
      idade: <br>
      nome: <br>
      local de nascimento:
    </div>
  </div>

  <div class="page">
    <div class="text">
      Segunda parte do texto, como se fosse outra página do diário.
    </div>
    <button class="button" onclick="toggleInfo(this)">details</button>
    <div class="info">
      personalidade: <br>
      traços: <br>
      segredos:
    </div>
  </div>

  <div class="page">
    <div class="text">
      Terceira parte do diário, mais íntima e profunda.
    </div>
    <button class="button" onclick="toggleInfo(this)">details</button>
    <div class="info">
      relações: <br>
      medos: <br>
      desejos:
    </div>
  </div>

</div>

<script>
function openDiary() {
  document.querySelector('.cover').style.display = 'none';
  document.getElementById('book').style.display = 'block';
}

function toggleInfo(btn) {
  const info = btn.nextElementSibling;
  info.style.display = info.style.display === 'block' ? 'none' : 'block';
}
</script>

</body>
</html>
