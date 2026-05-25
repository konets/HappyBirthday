<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>С Днём Рождения, Мамочка! 💗</title>
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Nunito:wght@400;700;900;800&display=swap" rel="stylesheet">
<style>
:root {
  --pink: #FF9BBD;
  --pink-light: #FFE8F3;
  --pink-dark: #E75480;
  --red: #FF4D6D;
  --cream: #FFF8F5;
  --yellow: #FFE66D;
  --mint: #B8F0D0;
  --lavender: #D4B8F0;
  --peach: #FFCBA4;
  --white: #FFFFFF;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: linear-gradient(135deg, #FFF0F8 0%, #FFE8F3 40%, #FFF5E8 100%);
  font-family: 'Nunito', sans-serif;
  overflow-x: hidden;
  min-height: 100vh;
  cursor: default;
}

/* ===== AUDIO BUTTON ===== */
#audio-btn {
  position: fixed;
  top: 14px;
  right: 16px;
  z-index: 999;
  background: var(--pink-dark);
  border: 3px solid white;
  color: white;
  font-family: 'Press Start 2P', monospace;
  font-size: 7px;
  padding: 8px 10px;
  cursor: pointer;
  box-shadow: 3px 3px 0 #a03060;
  border-radius: 4px;
  transition: transform 0.1s;
}
#audio-btn:hover { transform: translate(-1px,-1px); box-shadow: 4px 4px 0 #a03060; }

/* ===== SCROLLING RIBBON ===== */
.ribbon {
  background: linear-gradient(90deg, var(--pink-dark), #c0306a, var(--pink-dark));
  color: white;
  font-family: 'Press Start 2P', monospace;
  font-size: 8px;
  padding: 10px 0;
  overflow: hidden;
  white-space: nowrap;
  position: relative;
}
.ribbon-inner {
  display: inline-block;
  animation: ribbonScroll 14s linear infinite;
}
@keyframes ribbonScroll {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); }
}

/* ===== CONFETTI CANVAS ===== */
#confetti-canvas {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  pointer-events: none;
  z-index: 500;
}

/* ===== CLICK BURST ===== */
.click-burst {
  position: fixed;
  pointer-events: none;
  z-index: 600;
  font-size: 22px;
  animation: burstAnim 1.1s ease-out forwards;
  transform-origin: center;
}
@keyframes burstAnim {
  0%   { transform: translate(-50%,-50%) scale(0) rotate(0deg); opacity: 1; }
  60%  { opacity: 1; }
  100% { transform: translate(-50%, calc(-50% - 80px)) scale(1.4) rotate(30deg); opacity: 0; }
}

/* ===== MAIN LAYOUT ===== */
main {
  max-width: 860px;
  margin: 0 auto;
  padding: 10px 16px 80px;
  position: relative;
  z-index: 2;
}

/* ===== HEADER ===== */
.header {
  text-align: center;
  padding: 30px 20px 10px;
}

.header-title {
  font-family: 'Press Start 2P', monospace;
  font-size: clamp(13px, 3.8vw, 24px);
  color: var(--pink-dark);
  text-shadow: 3px 3px 0 #fff, 6px 6px 0 rgba(231,84,128,0.25);
  line-height: 1.9;
  animation: titleBounce 1.2s ease-in-out infinite alternate;
}
@keyframes titleBounce {
  from { transform: translateY(0px) rotate(-0.5deg); }
  to   { transform: translateY(-7px) rotate(0.5deg); }
}

.deco-row {
  font-size: 30px;
  margin: 10px 0;
  display: block;
  letter-spacing: 4px;
  animation: heartPulse 1.4s ease-in-out infinite alternate;
}
@keyframes heartPulse {
  from { transform: scale(1); }
  to   { transform: scale(1.12); }
}

/* ===== PIXEL KITTENS ===== */
.scene {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  gap: 16px;
  margin: 18px 0;
  flex-wrap: wrap;
}
.float-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
  animation: floatAnim 3s ease-in-out infinite;
}
.float-item:nth-child(1) { animation-delay: 0s; }
.float-item:nth-child(2) { animation-delay: 0.7s; }
.float-item:nth-child(3) { animation-delay: 1.4s; }
.float-item:nth-child(4) { animation-delay: 0.3s; }
.float-item:nth-child(5) { animation-delay: 1.1s; }
@keyframes floatAnim {
  0%, 100% { transform: translateY(0px); }
  50%       { transform: translateY(-10px); }
}
.item-label {
  font-family: 'Press Start 2P', monospace;
  font-size: 7px;
  color: var(--pink-dark);
  background: white;
  padding: 3px 7px;
  border: 2px solid var(--pink);
  border-radius: 3px;
}
canvas.kitty {
  image-rendering: pixelated;
}

/* ===== FLOWERS ROW ===== */
.flowers-row {
  text-align: center;
  font-size: 32px;
  margin: 10px 0;
  letter-spacing: 6px;
  animation: swayRow 2s ease-in-out infinite alternate;
}
@keyframes swayRow {
  from { transform: rotate(-1deg); }
  to   { transform: rotate(1deg); }
}

/* ===== MESSAGE CARD ===== */
.message-card {
  background: white;
  border: 4px solid var(--pink);
  outline: 3px solid var(--pink-dark);
  outline-offset: 3px;
  padding: 30px 36px;
  margin: 28px 0;
  position: relative;
  box-shadow: 8px 8px 0 var(--pink);
}
.message-card::before {
  content: '✿ ✦ ✿';
  position: absolute;
  top: -14px; left: 50%;
  transform: translateX(-50%);
  background: var(--pink-light);
  padding: 0 10px;
  color: var(--pink-dark);
  font-size: 16px;
}
.message-text {
  font-size: clamp(15px, 2.8vw, 20px);
  color: #4a1030;
  line-height: 2;
  text-align: center;
  font-weight: 700;
}
.message-text em {
  color: var(--pink-dark);
  font-style: normal;
  font-weight: 900;
}

/* ===== GIFTS SECTION ===== */
.gifts-title {
  font-family: 'Press Start 2P', monospace;
  font-size: 10px;
  color: var(--pink-dark);
  text-align: center;
  margin: 36px 0 20px;
  text-shadow: 2px 2px 0 #fff;
}

.gifts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(155px, 1fr));
  gap: 16px;
  margin-bottom: 40px;
}

/* Each gift = a present box */
.gift-box {
  position: relative;
  cursor: pointer;
  user-select: none;
  transition: transform 0.15s, box-shadow 0.15s;
}
.gift-box:hover .box-body { transform: translate(-2px,-3px); }
.gift-box:hover .box-lid  { transform: translateY(-6px); }

.box-lid {
  background: var(--lid-color, #FF9BBD);
  border: 3px solid #333;
  border-bottom: none;
  height: 26px;
  position: relative;
  z-index: 2;
  transition: transform 0.25s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}
.box-lid::after {
  content: '';
  position: absolute;
  left: 50%; top: 50%;
  transform: translate(-50%,-50%);
  width: 100%; height: 6px;
  background: rgba(255,255,255,0.5);
}
/* ribbon on lid */
.lid-ribbon {
  position: absolute;
  left: 50%; top: -8px;
  transform: translateX(-50%);
  z-index: 3;
  font-size: 18px;
  pointer-events: none;
}

.box-body {
  background: var(--box-color, #FFD6E7);
  border: 3px solid #333;
  padding: 18px 14px 20px;
  text-align: center;
  position: relative;
  z-index: 1;
  box-shadow: 5px 5px 0 #333;
  transition: transform 0.15s, box-shadow 0.15s;
  min-height: 110px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
}
/* vertical ribbon stripe on body */
.box-body::before {
  content: '';
  position: absolute;
  left: 50%; top: 0; bottom: 0;
  transform: translateX(-50%);
  width: 12px;
  background: rgba(0,0,0,0.08);
  pointer-events: none;
}

.gift-emoji {
  font-size: 28px;
  display: block;
}
.gift-hint {
  font-family: 'Press Start 2P', monospace;
  font-size: 6px;
  color: #7a3050;
  opacity: 0.7;
}

/* Opened state */
.gift-box.opened .box-lid {
  transform: translateY(-14px) rotate(-8deg);
}
.wish-reveal {
  font-size: 13px;
  color: #4a1030;
  font-weight: 800;
  line-height: 1.5;
  display: none;
}
.gift-box.opened .wish-reveal { display: block; }
.gift-box.opened .gift-hint   { display: none; }
.gift-box.opened .gift-emoji  { font-size: 22px; }

/* ===== FOOTER ===== */
.footer {
  text-align: center;
  font-family: 'Press Start 2P', monospace;
  font-size: 8px;
  color: var(--pink-dark);
  padding: 20px;
  line-height: 2.2;
}
</style>
</head>
<body>

<!-- Audio (Happy Birthday MIDI-style via Web Audio API) -->
<canvas id="confetti-canvas"></canvas>
<button id="audio-btn" onclick="toggleAudio()">🎵 МУЗЫКА</button>

<!-- TOP RIBBON -->
<div class="ribbon">
  <div class="ribbon-inner">
    🎀 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 &nbsp;&nbsp;&nbsp;&nbsp;
    🎀 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 С ДНЁМ РОЖДЕНИЯ, МАМОЧКА! 🌸 ЛЮБЛЮ ТЕБЯ! 💗 &nbsp;&nbsp;&nbsp;&nbsp;
  </div>
</div>

<main>
  <!-- HEADER -->
  <div class="header">
    <span class="deco-row">💗 🌸 🎀 🌸 💗</span>
    <h1 class="header-title">С Днём<br>Рождения!<br>Мамочка!</h1>
    <span class="deco-row">✨ 🌺 ⭐ 🌺 ✨</span>
  </div>

  <!-- SCENE: kitty + cake -->
  <div class="scene">
    <div class="float-item">
      <canvas id="kitty1" class="kitty" width="84" height="96"></canvas>
    </div>

    <div class="float-item">
      <!-- Pixelated Cake SVG (fully pixel/rect based) -->
      <svg width="112" height="140" viewBox="0 0 112 140" style="image-rendering:pixelated;filter:drop-shadow(4px 4px 0 #c0306a)" xmlns="http://www.w3.org/2000/svg">
        <!-- candles (pixel rects only) -->
        <rect x="22" y="4"  width="8" height="4" fill="#FF9BBD"/>
        <rect x="22" y="8"  width="8" height="4" fill="#FFB8D0"/>
        <rect x="22" y="12" width="8" height="4" fill="#FF9BBD"/>
        <rect x="22" y="16" width="8" height="4" fill="#FFB8D0"/>
        <rect x="22" y="20" width="8" height="4" fill="#FF9BBD"/>

        <rect x="52" y="0"  width="8" height="4" fill="#B8F0D0"/>
        <rect x="52" y="4"  width="8" height="4" fill="#D0F8E4"/>
        <rect x="52" y="8"  width="8" height="4" fill="#B8F0D0"/>
        <rect x="52" y="12" width="8" height="4" fill="#D0F8E4"/>
        <rect x="52" y="16" width="8" height="4" fill="#B8F0D0"/>
        <rect x="52" y="20" width="8" height="4" fill="#D0F8E4"/>

        <rect x="82" y="4"  width="8" height="4" fill="#FFE66D"/>
        <rect x="82" y="8"  width="8" height="4" fill="#FFF0A0"/>
        <rect x="82" y="12" width="8" height="4" fill="#FFE66D"/>
        <rect x="82" y="16" width="8" height="4" fill="#FFF0A0"/>
        <rect x="82" y="20" width="8" height="4" fill="#FFE66D"/>

        <!-- pixel flames -->
        <rect x="24" y="0"  width="4" height="4" fill="#FFE66D"/>
        <rect x="22" y="2"  width="8" height="2" fill="#FF7043"/>
        <rect x="54" y="-4" width="4" height="4" fill="#FFE66D"/>
        <rect x="52" y="-2" width="8" height="2" fill="#FF7043"/>
        <rect x="84" y="0"  width="4" height="4" fill="#FFE66D"/>
        <rect x="82" y="2"  width="8" height="2" fill="#FF7043"/>

        <!-- top tier frosting band -->
        <rect x="16" y="24" width="80" height="8"  fill="#FF9BBD"/>
        <!-- top tier body rows -->
        <rect x="16" y="32" width="80" height="8"  fill="#FFFFFF"/>
        <rect x="16" y="40" width="80" height="8"  fill="#FFF0F8"/>
        <rect x="16" y="48" width="80" height="8"  fill="#FFFFFF"/>
        <!-- top tier bottom band -->
        <rect x="16" y="56" width="80" height="6"  fill="#FF9BBD"/>
        <!-- pixel dots top tier -->
        <rect x="28" y="38" width="8" height="8" fill="#FF4D6D"/>
        <rect x="48" y="36" width="8" height="8" fill="#FFE66D"/>
        <rect x="68" y="38" width="8" height="8" fill="#D4B8F0"/>
        <!-- star pixel style top tier -->
        <rect x="52" y="36" width="4" height="4" fill="#E75480"/>
        <rect x="50" y="38" width="8" height="2" fill="#E75480"/>

        <!-- middle frosting separator -->
        <rect x="8"  y="62" width="96" height="4"  fill="#E75480"/>

        <!-- bottom tier body rows -->
        <rect x="8"  y="66" width="96" height="8"  fill="#FFFFFF"/>
        <rect x="8"  y="74" width="96" height="8"  fill="#FFF0F8"/>
        <rect x="8"  y="82" width="96" height="8"  fill="#FFFFFF"/>
        <rect x="8"  y="90" width="96" height="8"  fill="#FFF0F8"/>
        <!-- bottom tier bottom band -->
        <rect x="8"  y="98" width="96" height="8"  fill="#E75480"/>
        <!-- pixel dots bottom tier -->
        <rect x="16" y="74" width="8" height="8"  fill="#FFE66D"/>
        <rect x="32" y="80" width="8" height="8"  fill="#B8F0D0"/>
        <rect x="48" y="72" width="10" height="10" fill="#FF9BBD"/>
        <rect x="64" y="78" width="8" height="8"  fill="#D4B8F0"/>
        <rect x="82" y="74" width="8" height="8"  fill="#FFCBA4"/>

        <!-- plate pixel rows -->
        <rect x="4"  y="106" width="104" height="4" fill="#FFD6E7"/>
        <rect x="2"  y="110" width="108" height="4" fill="#FFBBD8"/>
        <rect x="4"  y="114" width="104" height="4" fill="#FFD6E7"/>
      </svg>
      <span class="item-label">Тортик!</span>
    </div>
  </div>

  <!-- FLOWERS ROW -->
  <div class="flowers-row">🌹 🌷 🌸 🌺 💐 🌸 🌷 🌹</div>

  <!-- MESSAGE CARD -->
  <div class="message-card">
    <p class="message-text">
      Дорогая, любимая <em>мамочка!</em> 🌸<br><br>
      Сегодня особенный день, и я хочу сказать тебе то,<br>
      что иногда не успеваем говорить в суете каждого дня.<br><br>
      Ты самый важный человек в моей жизни.<br>
      Ты дала мне не просто жизнь, ты дала мне всё,<br>
      что в этой жизни ценно: тепло, заботу, опору и любовь. 💗<br><br>
      Я помню, как ты всегда находила слова, которые успокаивали.<br>
      Как твои объятия были самым безопасным местом на свете.<br>
      Как ты верила в меня, даже когда я сам сомневался.<br>
      Это не забывается никогда. ✨<br><br>
      Спасибо за твоё бесконечное терпение,<br>
      за каждую ночь, которую ты провела рядом,<br>
      за улыбку, которую ты дарила, пряча усталость,<br>
      за мудрость, которую ты передавала по капле, с любовью.<br><br>
      Я так благодарен тебе за всё, что ты делала<br>
      и продолжаешь делать. Ты моя гордость, моя опора<br>
      и моя самая большая любовь. 🌺<br><br>
      Пусть этот день будет наполнен радостью,<br>
      пусть каждое утро начинается легко и светло,<br>
      а каждый вечер приносит покой и уют.<br>
      Ты заслуживаешь всего самого лучшего на свете! 🌸<br><br>
      <em>С днём рождения, мамочка!</em><br>
      Я люблю тебя больше всех слов! 💗
    </p>
  </div>

  <!-- GIFTS / WISHES -->
  <p style="text-align:center;font-family:'Nunito',sans-serif;font-size:clamp(22px,4vw,34px);font-weight:900;color:var(--pink-dark);margin:32px 0 4px;text-shadow:2px 2px 0 #fff,4px 4px 0 rgba(231,84,128,0.2);">Я желаю тебе....</p>
  <p class="gifts-title">✦ Нажми на подарок ✦</p>
  <div class="gifts-grid">

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#FF9BBD;--box-color:#FFE8F3;">
      <div class="box-lid">
        <span class="lid-ribbon">🎀</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">💊</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Крепкого здоровья на долгие-долгие годы!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#B8F0D0;--box-color:#E8FFF4;">
      <div class="box-lid">
        <span class="lid-ribbon">🌿</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">🧘</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Терпения и внутреннего покоя в любой ситуации!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#FFE66D;--box-color:#FFFBE8;">
      <div class="box-lid">
        <span class="lid-ribbon">⭐</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">😊</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Счастья, которое живёт внутри и не гаснет!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#D4B8F0;--box-color:#F5EEFF;">
      <div class="box-lid">
        <span class="lid-ribbon">💜</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">🌍</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Путешествий и новых открытий в жизни!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#FFCBA4;--box-color:#FFF5EE;">
      <div class="box-lid">
        <span class="lid-ribbon">🌟</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">💰</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Финансового благополучия и исполнения желаний!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#FF9BBD;--box-color:#FFE8F3;">
      <div class="box-lid">
        <span class="lid-ribbon">🌸</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">💑</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Любви, тепла и заботы от близких каждый день!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#B8F0D0;--box-color:#E8FFF4;">
      <div class="box-lid">
        <span class="lid-ribbon">✨</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">🎨</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Времени на себя, свои мечты и увлечения!</p>
      </div>
    </div>

    <div class="gift-box" onclick="openGift(this)" style="--lid-color:#FFE66D;--box-color:#FFFBE8;">
      <div class="box-lid">
        <span class="lid-ribbon">🎂</span>
      </div>
      <div class="box-body">
        <span class="gift-emoji">🥂</span>
        <span class="gift-hint">Открой!</span>
        <p class="wish-reveal">Радости в каждом дне и поводов для праздника!</p>
      </div>
    </div>

  </div>

  <!-- FOOTER -->
  <div class="footer">
    Сделано с любовью 💗<br>
    Специально для тебя, мамочка!
  </div>
</main>

<!-- BOTTOM RIBBON -->
<div class="ribbon">
  <div class="ribbon-inner">
    💗 ТЫ ЛУЧШАЯ МАМА НА СВЕТЕ! 🌸 ЛЮБЛЮ ТЕБЯ БЕСКОНЕЧНО! ✨ ТЫ ЛУЧШАЯ МАМА НА СВЕТЕ! 🌸 ЛЮБЛЮ ТЕБЯ БЕСКОНЕЧНО! ✨ &nbsp;&nbsp;&nbsp;&nbsp;
    💗 ТЫ ЛУЧШАЯ МАМА НА СВЕТЕ! 🌸 ЛЮБЛЮ ТЕБЯ БЕСКОНЕЧНО! ✨ ТЫ ЛУЧШАЯ МАМА НА СВЕТЕ! 🌸 ЛЮБЛЮ ТЕБЯ БЕСКОНЕЧНО! ✨ &nbsp;&nbsp;&nbsp;&nbsp;
  </div>
</div>

<script>
// ===================================================
//  PIXEL KITTY DRAWING
// ===================================================
function drawKitty(canvasId, bodyColor, bellyColor, bowColor, eyeColor, earColor) {
  const canvas = document.getElementById(canvasId);
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  const S = 6; // pixel size

  const BK = '#2a1a1a';
  const W  = '#FFFFFF';
  const NO = '#FF9BBD'; // nose
  const B  = bodyColor;
  const BL = bellyColor;
  const EY = eyeColor;
  const EA = earColor;
  const RB = bowColor;

  // 14 cols x 16 rows
  const grid = [
    //0    1    2    3    4    5    6    7    8    9   10   11   12   13
    [ 0,   0,   BK,  BK,  0,   0,   0,   0,   0,   BK,  BK,  0,   0,   0  ], // row 0  ears top
    [ 0,   BK,  EA,  EA,  BK,  0,   0,   0,   BK,  EA,  EA,  BK,  0,   0  ], // row 1
    [ BK,  EA,  EA,  EA,  BK,  BK,  BK,  BK,  BK,  EA,  EA,  EA,  BK,  0  ], // row 2
    [ BK,  B,   B,   BK,  B,   B,   B,   B,   B,   BK,  B,   B,   B,   BK ], // row 3  head top
    [ BK,  B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   BK ], // row 4
    [ BK,  B,   BK,  BK,  B,   B,   B,   B,   B,   BK,  BK,  B,   B,   BK ], // row 5  eyes
    [ BK,  B,   BK,  EY,  BK,  B,   B,   B,   BK,  EY,  BK,  B,   B,   BK ], // row 6
    [ BK,  B,   BK,  BK,  B,   B,   B,   B,   B,   BK,  BK,  B,   B,   BK ], // row 7
    [ BK,  B,   B,   B,   B,   NO,  B,   B,   B,   B,   B,   B,   B,   BK ], // row 8  nose
    [ BK,  B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   BK ], // row 9
    [ BK,  BK,  B,   B,   B,   B,   B,   B,   B,   B,   B,   B,   BK,  BK ], // ro
