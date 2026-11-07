
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#08080b">
<title>Riya — The Flower That Outshines the Day</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:wght@300;400;500&display=swap');

:root {
  --bg: #08080b;
  --white: #f2eee9;
  --muted: #aaa1a5;
  --rose: #a77c85;
  --gold: #c4a98b;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--white);
  font-family: 'DM Sans', sans-serif;
  overflow-x: hidden;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 10;
  opacity: .12;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.23'/%3E%3C/svg%3E");
}

button { font: inherit; }

.serif {
  font-family: 'Cormorant Garamond', serif;
}

/* PASSWORD SCREEN */

#gate {
  position: fixed;
  inset: 0;
  z-index: 100;
  background:
    radial-gradient(ellipse at 50% 40%, #21151c 0%, #0b090e 48%, #050507 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 24px;
  transition: opacity 1.2s ease, visibility 1.2s;
}

#gate.hidden {
  opacity: 0;
  visibility: hidden;
  pointer-events: none;
}

.gate-content {
  width: 100%;
  max-width: 400px;
  animation: appear 2s ease both;
}

.gate-flower {
  font-size: 43px;
  color: #eee5e7;
  margin-bottom: 35px;
  animation: glow 4s infinite alternate;
}

.eyebrow {
  font-size: 9px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: var(--rose);
}

.gate-title {
  font-size: clamp(48px, 12vw, 75px);
  font-weight: 400;
  letter-spacing: 7px;
  margin: 18px 0 8px;
}

.gate-subtitle {
  font-family: 'Cormorant Garamond', serif;
  font-size: 19px;
  font-style: italic;
  color: #c5b6bb;
}

.password-box {
  margin-top: 43px;
  display: flex;
  border-bottom: 1px solid #64515b;
  padding: 8px 0;
}

.password-box input {
  flex: 1;
  min-width: 0;
  background: transparent;
  color: white;
  border: none;
  outline: none;
  padding: 12px;
  text-align: center;
  letter-spacing: 4px;
  font-size: 13px;
}

.password-box button {
  background: transparent;
  border: none;
  color: var(--gold);
  letter-spacing: 2px;
  font-size: 10px;
  cursor: pointer;
  padding: 10px;
}

#error {
  color: #c58a91;
  font-size: 11px;
  margin-top: 16px;
  min-height: 16px;
}

.gate-bottom {
  margin-top: 50px;
  color: #71666c;
  font-size: 9px;
  letter-spacing: 3px;
}

/* MAIN WEBSITE */

#main {
  opacity: 0;
  transition: opacity 2s ease;
}

#main.visible { opacity: 1; }

nav {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  padding: 28px 7%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 20;
}

.nav-logo {
  letter-spacing: 5px;
  font-size: 11px;
}

.nav-right {
  display: flex;
  align-items: center;
  gap: 20px;
}

.sound-btn {
  color: #c8b8bd;
  background: transparent;
  border: 1px solid #55464d;
  padding: 9px 13px;
  font-size: 9px;
  letter-spacing: 2px;
  cursor: pointer;
}

.sound-btn:hover { border-color: var(--gold); }

/* HERO */

.hero {
  min-height: 100svh;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  overflow: hidden;
  padding: 100px 20px;
  background:
    radial-gradient(ellipse at 50% 53%, #21151d 0%, #100d13 35%, #08080b 75%);
}

.hero::after {
  content: "";
  position: absolute;
  width: 550px;
  height: 550px;
  border-radius: 50%;
  background: radial-gradient(circle, #79506020, transparent 70%);
  animation: breathe 8s infinite alternate;
}

.hero-content {
  position: relative;
  z-index: 2;
}

.hero-flower {
  font-size: 12px;
  letter-spacing: 9px;
  color: var(--rose);
  margin-bottom: 32px;
}

.hero h1 {
  font-size: clamp(65px, 14vw, 125px);
  font-weight: 400;
  letter-spacing: clamp(5px, 2vw, 15px);
  line-height: 1;
  text-shadow: 0 0 45px #e7cbd21c;
}

.hero-description {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(18px, 4vw, 26px);
  font-style: italic;
  color: #c8b8bd;
  margin-top: 22px;
}

.hero-line {
  width: 45px;
  height: 1px;
  background: var(--gold);
  margin: 35px auto;
}

.hero-note {
  font-size: 9px;
  letter-spacing: 4px;
  color: #92818a;
  text-transform: uppercase;
}

.scroll {
  position: absolute;
  bottom: 32px;
  font-size: 9px;
  letter-spacing: 4px;
  color: #82757b;
  animation: float 3s infinite ease-in-out;
}

/* FLOWER */

.flower-section {
  min-height: 90vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 100px 24px;
  background: linear-gradient(#08080b, #100d12, #08080b);
}

.flower-art {
  width: 180px;
  height: 180px;
  position: relative;
  margin-bottom: 65px;
  animation: flowerFloat 6s ease-in-out infinite;
}

.flower-art .petal {
  position: absolute;
  width: 48px;
  height: 85px;
  left: 66px;
  top: 12px;
  transform-origin: 50% 78px;
  border-radius: 55% 55% 45% 45%;
  background: linear-gradient(140deg, #fffefa, #d9cdd4 65%, #9e8795);
  box-shadow: 0 0 22px #fff6;
}

.petal:nth-child(1) { transform: rotate(0deg); }
.petal:nth-child(2) { transform: rotate(60deg); }
.petal:nth-child(3) { transform: rotate(120deg); }
.petal:nth-child(4) { transform: rotate(180deg); }
.petal:nth-child(5) { transform: rotate(240deg); }
.petal:nth-child(6) { transform: rotate(300deg); }

.flower-center {
  position: absolute;
  width: 25px;
  height: 25px;
  background: radial-gradient(circle, #f8e9ba, #b28b69);
  border-radius: 50%;
  top: 77px;
  left: 77px;
  box-shadow: 0 0 30px #f1d6a780;
}

.flower-stem {
  position: absolute;
  width: 3px;
  height: 65px;
  background: linear-gradient(#a2a98a, #3e5844);
  top: 125px;
  left: 89px;
}

.flower-leaf {
  position: absolute;
  width: 33px;
  height: 16px;
  border-radius: 100% 0 100% 0;
  background: #61755d;
  top: 150px;
  left: 91px;
  transform: rotate(-25deg);
}

.section-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(36px, 8vw, 57px);
  font-weight: 400;
  margin-bottom: 25px;
}

.section-text {
  max-width: 570px;
  color: #b7aab1;
  font-family: 'Cormorant Garamond', serif;
  font-size: 21px;
  line-height: 1.8;
}

.section-text em { color: #e5c9d0; }

/* POETRY */

.poetry {
  min-height: 90vh;
  padding: 120px 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: radial-gradient(ellipse at 50% 50%, #1b1119, #08080b 75%);
}

.poetry-content { max-width: 700px; }

.poetry-label {
  font-size: 9px;
  color: var(--rose);
  letter-spacing: 5px;
  margin-bottom: 45px;
}

.poetry h2 {
  font-family: 'Cormorant Garamond', serif;
  font-weight: 400;
  font-size: clamp(33px, 7vw, 54px);
  line-height: 1.35;
}

.poetry h2 span { color: #d2aab7; font-style: italic; }

.poetry p {
  margin-top: 35px;
  color: #a99ba2;
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  line-height: 1.9;
}

/* SMILE */

.smile {
  padding: 130px 25px;
  text-align: center;
  background: #09090c;
}

.smile h2 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(39px, 8vw, 62px);
  font-weight: 400;
  margin: 30px auto;
  max-width: 800px;
}

.smile h2 em { color: #d2abb4; }

.smile p {
  max-width: 540px;
  margin: auto;
  color: #aaa0a5;
  font-family: 'Cormorant Garamond', serif;
  font-size: 21px;
  line-height: 1.8;
}

/* LETTER */

.letter-section {
  padding: 110px 22px;
  background: linear-gradient(#09090c, #171017);
  display: flex;
  justify-content: center;
}

.letter {
  max-width: 650px;
  width: 100%;
  border: 1px solid #44343d;
  padding: clamp(30px, 7vw, 65px);
  background: #110e13;
  box-shadow: 0 20px 80px #0008;
}

.letter-top {
  font-size: 9px;
  letter-spacing: 4px;
  color: var(--gold);
}

.letter h2 {
  font-family: 'Cormorant Garamond', serif;
  font-size: 45px;
  font-weight: 400;
  margin: 32px 0;
}

.letter p {
  color: #bdb0b6;
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  line-height: 1.9;
  margin-bottom: 22px;
}

.signature {
  margin-top: 40px;
  text-align: right;
  color: #d5b5bd;
  font-family: 'Cormorant Garamond', serif;
  font-size: 27px;
  font-style: italic;
}

/* ENDING */

.ending {
  min-height: 90vh;
  padding: 100px 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  background:
    radial-gradient(ellipse at 50% 50%, #291823, #08080b 70%);
}

.ending .small {
  color: var(--rose);
  font-size: 9px;
  letter-spacing: 5px;
  margin-bottom: 40px;
}

.ending h2 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(42px, 9vw, 76px);
  font-weight: 400;
  line-height: 1.15;
}

.ending h2 em { color: #d4adb8; }

.ending p {
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  color: #b9aab1;
  margin-top: 35px;
  line-height: 1.8;
  max-width: 520px;
}

.ending .final-sign {
  margin-top: 70px;
  font-family: 'Cormorant Garamond', serif;
  font-size: 26px;
  font-style: italic;
  color: var(--gold);
}

footer {
  padding: 28px;
  background: #070709;
  text-align: center;
  color: #71666c;
  font-size: 9px;
  letter-spacing: 3px;
}

/* ANIMATIONS */

@keyframes appear {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes glow {
  from { text-shadow: 0 0 8px #fff4; }
  to { text-shadow: 0 0 35px #fff9; }
}

@keyframes breathe {
  from { transform: scale(.8); opacity: .4; }
  to { transform: scale(1.2); opacity: 1; }
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-9px); }
}

@keyframes flowerFloat {
  0%, 100% { transform: translateY(0) rotate(-2deg); }
  50% { transform: translateY(-13px) rotate(2deg); }
}

@media (max-width: 600px) {
  nav { padding: 22px 20px; }
  .nav-right { gap: 10px; }
  .sound-btn { padding: 8px; }
  .section-text { font-size: 19px; }
  .letter { padding: 30px 25px; }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: .01ms !important;
    scroll-behavior: auto !important;
  }
}
</style>
</head>

<body>

<!-- SECRET ENTRY -->

<div id="gate">
  <div class="gate-content">
    <div class="gate-flower">✿</div>
    <div class="eyebrow">A little world, made of words</div>
    <h1 class="gate-title serif">R I Y A</h1>
    <p class="gate-subtitle">Some things are meant to be discovered.</p>

    <div class="password-box">
      <input
        id="password"
        type="password"
        placeholder="Enter the secret"
        autocomplete="off"
        aria-label="Secret password"
      >
      <button onclick="unlock()">ENTER ↗</button>
    </div>

    <div id="error"></div>
    <div class="gate-bottom">ONLY FOR THE ONE WHO BLOOMS</div>
  </div>
</div>

<!-- WEBSITE -->

<div id="main">

<nav>
  <div class="nav-logo">R I Y A</div>
  <div class="nav-right">
    <button class="sound-btn" id="soundBtn" onclick="toggleSound()">
      ♫ SOUND OFF
    </button>
  </div>
</nav>

<!-- HERO -->

<section class="hero">
  <div class="hero-content">
    <div class="hero-flower">✳ &nbsp; ✳ &nbsp; ✳</div>
    <h1 class="serif">RIYA</h1>
    <p class="hero-description">
      The flower that outshines the day.
    </p>
    <div class="hero-line"></div>
    <div class="hero-note">
      A story written in the language of flowers
    </div>
  </div>
  <div class="scroll">SCROLL TO DISCOVER ↓</div>
</section>

<!-- FLOWER -->

<section class="flower-section">
  <div class="flower-art" aria-label="An illustrated white flower">
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="flower-center"></div>
    <div class="flower-stem"></div>
    <div class="flower-leaf"></div>
  </div>

  <div class="eyebrow">THE FIRST THOUGHT</div>
  <h2 class="section-title">A flower, perhaps.</h2>

  <p class="section-text">
    Some flowers bloom quietly, without asking the world to notice.
    They don't chase attention, nor do they compete with the beauty
    around them. They simply exist, and somehow, that is enough
    to make everything feel more beautiful.
    <br><br>
    <em>And then there is Riya.</em>
  </p>
</section>

<!-- POETRY -->

<section class="poetry">
  <div class="poetry-content">
    <div class="poetry-label">A THOUGHT ABOUT HER</div>

    <h2>
      Flowers wait for the sunlight
      to reveal their beauty.
      <br><br>
      <span>She smiles, and the sunlight
      seems to have found its purpose.</span>
    </h2>

    <p>
      Perhaps flowers were never meant to be compared.
      But if I had to find something that comes close
      to the quiet magic of her existence,
      I'd look at a garden in full bloom.
    </p>
  </div>
</section>

<!-- SMILE -->

<section class="smile">
  <div class="eyebrow">THE MOST BEAUTIFUL THING</div>

  <h2>
    The world has its flowers.
    <br>
    <em>But I wonder if the flowers
    have ever seen her smile.</em>
  </h2>

  <p>
    A flower makes a garden brighter.
    The morning makes the world brighter.
    Yet there is something about her smile
    that makes both seem a little less extraordinary.
    <br><br>
    Maybe that's why I chose a flower to describe her.
    Not because it is enough, but because I couldn't
    find anything better.
  </p>
</section>

<!-- LETTER -->

<section class="letter-section">
  <div class="letter">
    <div class="letter-top">A LETTER THAT FOUND ITS WAY HERE</div>

    <h2>Dear Riya,</h2>

    <p>
      I don't know if flowers understand how beautiful they are.
      Perhaps they simply bloom, unaware of the little worlds
      they brighten.
    </p>

    <p>
      I imagine you are a little like that.
      You probably don't realise how something as simple
      as your smile can change the atmosphere of an entire day.
    </p>

    <p>
      There are a thousand ways to describe beauty,
      and still, words seem to arrive a little late
      whenever I think of yours.
    </p>

    <p>
      So here's a little thought I wanted to leave behind:
      if the day ever forgets how to shine,
      perhaps it should just borrow a little light from you.
    </p>

    <div class="signature">— z</div>
  </div>
</section>

<!-- ENDING -->

<section class="ending">
  <div class="small">AND BEFORE YOU LEAVE...</div>

  <h2>
    If beauty had a name,
    <br>
    <em>perhaps it would be Riya.</em>
  </h2>

  <p>
    Some flowers outshine the garden.
    Some stars outshine the night.
    And some smiles...
    outshine the day itself.
  </p>

  <div class="final-sign">With a thought, - z</div>
</section>

<footer>
  MADE OF MIDNIGHT, FLOWERS & WORDS
  <br><br>
  RIYA © 2026
</footer>

</div>

<script>
/* CHANGE YOUR SECRET PASSWORD HERE */
const SECRET_PASSWORD = "bloom";

function unlock() {
  const input = document.getElementById("password");
  const error = document.getElementById("error");

  if (input.value.trim().toLowerCase() === SECRET_PASSWORD.toLowerCase()) {
    document.getElementById("gate").classList.add("hidden");
    document.getElementById("main").classList.add("visible");

    // Start the sound only after the visitor enters.
    startAmbient();
  } else {
    error.textContent = "Not every secret opens every door.";
    input.value = "";
    input.focus();
  }
}

document.getElementById("password").addEventListener("keydown", e => {
  if (e.key === "Enter") unlock();
});

/* ORIGINAL AMBIENT SOUND — NO EXTERNAL MUSIC FILE */

let audioContext = null;
let oscillators = [];
let soundOn = false;
let masterGain = null;

function startAmbient() {
  if (soundOn) return;

  try {
    const AudioContextClass =
      window.AudioContext || window.webkitAudioContext;

    if (!AudioContextClass) return;

    audioContext = audioContext || new AudioContextClass();

    if (audioContext.state === "suspended") {
      audioContext.resume();
    }

    masterGain = audioContext.createGain();
    masterGain.gain.value = 0;
    masterGain.connect(audioContext.destination);

    const notes = [110, 164.81, 220, 261.63];

    notes.forEach((frequency, index) => {
      const oscillator = audioContext.createOscillator();
      const gain = audioContext.createGain();

      oscillator.type = index === 0 ? "sine" : "triangle";
      oscillator.frequency.value = frequency;
      gain.gain.value = index === 0 ? 0.035 : 0.012;

      oscillator.connect(gain);
      gain.connect(masterGain);
      oscillator.start();

      oscillators.push(oscillator);
    });

    masterGain.gain.setTargetAtTime(
      0.8,
      audioContext.currentTime,
      3
    );

    soundOn = true;
    updateSoundButton();

  } catch (error) {
    console.log("Audio unavailable:", error);
  }
}

function toggleSound() {
  if (!audioContext || !soundOn) {
    startAmbient();
    return;
  }

  if (audioContext.state === "suspended") {
    audioContext.resume();
  }

  const target = masterGain.gain.value > 0.01 ? 0 : 0.8;

  masterGain.gain.setTargetAtTime(
    target,
    audioContext.currentTime,
    0.5
  );

  updateSoundButton(target > 0);
}

function updateSoundButton(active = soundOn) {
  const button = document.getElementById("soundBtn");
  button.textContent = active ? "♫ SOUND ON" : "♫ SOUND OFF";
}

/* REVEAL SECTIONS AS THEY ENTER VIEW */

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.animate(
        [
          { opacity: 0.3, transform: "translateY(18px)" },
          { opacity: 1, transform: "translateY(0)" }
        ],
        {
          duration: 1200,
          easing: "ease-out",
          fill: "forwards"
        }
      );

      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.15 });

document.querySelectorAll(
  ".flower-section, .poetry, .smile, .letter, .ending"
).forEach(section => observer.observe(section));

</script>

</body>
</html>
