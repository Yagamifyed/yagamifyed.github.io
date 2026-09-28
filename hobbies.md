---
layout: work
title: Hobbies
permalink: /hobbies/
---

<style>
p {
  line-height: 25px;
}

h3 {
  font-family: Charter, Georgia, Helvetica, Arial, sans-serif;
}

b, strong {
  font-weight: inherit;
  text-decoration: underline;
}

.gate {
  text-align: center;
  margin: 60px 0;
}
.gate form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 18px;
}

/* Password field on a parchment scroll with rolled ends */
.scroll {
  position: relative;
  padding: 16px 34px;
  background: linear-gradient(#f4e4b8, #e3c98f);
  border-top: 2px solid #9a7440;
  border-bottom: 2px solid #9a7440;
  box-shadow: 0 3px 6px rgba(80, 50, 10, 0.25);
}
.scroll::before,
.scroll::after {
  content: "";
  position: absolute;
  top: -8px;
  bottom: -8px;
  width: 20px;
  border-radius: 10px;
  background: linear-gradient(90deg, #8a6331, #f0dca8 45%, #b08850);
  box-shadow: 0 2px 4px rgba(80, 50, 10, 0.35);
}
.scroll::before {
  left: -10px;
}
.scroll::after {
  right: -10px;
}
/* The real input is invisible; .scroll-mask draws a dot per character with its own underline */
.scroll-field {
  position: relative;
  width: 180px;
  max-width: 50vw;
  height: 32px;
}
.scroll-field input {
  position: absolute;
  inset: 0;
  width: 100%;
  padding: 0;
  font: inherit;
  font-size: 16px; /* below 16px, iOS Safari zooms in on focus and stays zoomed */
  color: transparent;
  caret-color: transparent;
  background: transparent;
  border: none;
  outline: none;
}
.scroll-mask {
  position: absolute;
  inset: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 5px;
  overflow: hidden;
  pointer-events: none;
  color: #3b2a14;
  font-size: 1.1em;
}
.scroll-mask span {
  width: 11px;
  line-height: 1.2;
  text-align: center;
  border-bottom: 2px solid #8a6331;
}
.scroll-mask .caret {
  width: 2px;
  height: 20px;
  border: none;
  background: #3b2a14;
  animation: blink 1s steps(1) infinite;
}
@keyframes blink {
  50% { opacity: 0; }
}

/* The casket is the submit button */
.casket {
  padding: 0;
  border: none;
  background: none;
  cursor: pointer;
}
.casket img {
  display: block;
  width: 72px;
  image-rendering: pixelated;
  transition: transform 0.15s;
}
.casket:hover img,
.casket:focus-visible img {
  transform: translateY(-3px) scale(1.05);
}
.casket.shake img {
  animation: shake 0.4s;
}
@keyframes shake {
  25% { transform: translateX(-6px) rotate(-6deg); }
  50% { transform: translateX(6px) rotate(6deg); }
  75% { transform: translateX(-3px) rotate(-3deg); }
}
.gate-error {
  color: #D21515;
  visibility: hidden;
}

.osrs-model {
  width: 100%;
  height: 420px;
  margin: 20px 0;
  overflow: hidden;
  cursor: grab;
}
.osrs-model canvas {
  display: block;
  width: 100% !important;
  height: 100% !important;
}

/* Mining goal: progress track with ore milestones and a little miner */
.goal {
  max-width: 384px;
  margin: 20px auto 0;
}
.goal-label {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-size: 0.9em;
}
.goal-name {
  display: inline-flex;
  align-items: center;
  gap: 4px;
}
.goal-name img {
  height: 16px;
}
.goal-track {
  position: relative;
  margin: 0 18px;
  padding-top: 94px;
  padding-bottom: 48px;
}
.goal-bar {
  height: 12px;
  border-radius: 6px;
  background: #eee;
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.15);
  overflow: hidden;
}
.goal-fill {
  height: 100%;
  border-radius: 6px;
  background: linear-gradient(#e0413f, #b31010);
}
.goal-miner {
  position: absolute;
  top: -12px;
  width: 80px;
  height: 104px;
  transform: translateX(-50%);
  pointer-events: none;
}
.goal-miner canvas {
  width: 80px;
  height: 104px;
  image-rendering: pixelated;
}
.goal-chip {
  position: absolute;
  width: 4px;
  height: 4px;
  background: #6b5a45;
  animation: chip 0.5s ease-out forwards;
}
@keyframes chip {
  to {
    transform: translate(var(--dx), var(--dy));
    opacity: 0;
  }
}
.goal-milestone {
  position: absolute;
  top: 110px; /* just below the bar (padding-top 94px + bar 12px + gap) */
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 0.7em;
  line-height: 1.2;
  color: #999;
  filter: grayscale(1);
  opacity: 0.45;
}
.goal-milestone::before {
  content: "";
  position: absolute;
  bottom: 100%;
  left: 50%;
  width: 2px;
  height: 17px;
  margin-left: -1px;
  background: rgba(0, 0, 0, 0.25);
}
.goal-milestone img {
  width: 26px;
  image-rendering: pixelated;
}
.goal-milestone.special img {
  filter: drop-shadow(0 0 4px #f5c400);
}
.goal-milestone.reached {
  color: #333;
  filter: none;
  opacity: 1;
}

@font-face {
  font-family: "RuneScape Small";
  src: url("/assets/fonts/RuneScape-Plain-11.ttf") format("truetype");
}
@font-face {
  font-family: "RuneScape Plain";
  src: url("/assets/fonts/RuneScape-Plain-12.ttf") format("truetype");
}

/* Skills panel styled after the in-game skill tab */
.osrs-panel {
  max-width: 372px;
  margin: 20px auto 6px;
  padding: 4px;
  background: #1f1f1f;
  border: 2px solid #050505;
  border-radius: 4px;
}
.osrs-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 3px;
}
.osrs-cell {
  position: relative;
  height: 54px;
  background: #343434;
  border: 2px solid;
  border-color: #464646 #161616 #161616 #464646;
  border-radius: 3px;
  box-shadow: 0 0 0 1px #0c0c0c;
  overflow: hidden;
}
.osrs-cell img {
  position: absolute;
  left: 4px;
  top: 50%;
  transform: translateY(-50%);
  max-width: 48%;
  max-height: 46px;
}
.osrs-lvl {
  position: absolute;
  font-family: "RuneScape Small", monospace;
  font-size: 30px;
  line-height: 1;
  color: #ffff00;
  text-shadow: 2px 2px 0 #000;
  -webkit-font-smoothing: none;
}
.osrs-lvl-top {
  left: 52%;
  top: 4px;
}
.osrs-lvl-bot {
  right: 6px;
  bottom: 4px;
}
.osrs-slash {
  position: absolute;
  left: 71%;
  top: -8px;
  width: 2px;
  height: 70px;
  background: #000;
  transform: rotate(40deg);
}
@media (max-width: 500px) {
  .osrs-model {
    height: 320px;
  }
  .osrs-cell {
    height: 62px;
  }
  .osrs-cell img {
    left: 3px;
    max-width: 40%;
    max-height: 40px;
  }
  .osrs-lvl {
    font-size: 24px;
    text-shadow: 1px 1px 0 #000;
  }
  .osrs-lvl-top {
    left: 46%;
    top: 7px;
  }
  .osrs-lvl-bot {
    right: 6px;
    bottom: 7px;
  }
  .osrs-slash {
    left: 70%;
    top: -6px;
    height: 74px;
    transform: rotate(35deg);
  }
  .osrs-total {
    font-size: 30px;
  }
}
.osrs-total {
  margin-top: 4px;
  padding: 4px 0;
  background: #000;
  border: 2px solid #2a2a2a;
  border-radius: 3px;
  text-align: center;
  font-family: "RuneScape Plain", monospace;
  font-size: 36px;
  line-height: 1;
  color: #ffff00;
  text-shadow: 2px 2px 0 #000;
  -webkit-font-smoothing: none;
}
.updated {
  text-align: center;
  font-size: 0.8em;
  color: #999;
}

.favs {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
  margin: 20px 0;
}
@media (max-width: 600px) {
  .favs {
    grid-template-columns: repeat(2, 1fr);
  }
}
.fav {
  position: relative;
  display: block;
  aspect-ratio: 70 / 110;
  border-radius: 4px;
  overflow: hidden;
  text-decoration: none;
  border: none;
}
.fav img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.fav-title {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 24px 8px 6px;
  color: #fff;
  font-size: 0.8em;
  line-height: 1.3;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
}
.fav-title small {
  display: block;
  opacity: 0.8;
}
.fav-score {
  position: absolute;
  top: 6px;
  right: 6px;
  padding: 2px 6px;
  border-radius: 3px;
  color: #fff;
  font-size: 0.8em;
  background: rgba(210, 21, 21, 0.9);
}

.hobby-img {
  display: block;
  max-width: 100%;
  max-height: 400px;
  margin: 20px auto;
}
</style>

<div class="gate" id="gate">
  <p>Nice find. What now?</p>
  <form id="gate-form">
    <div class="scroll">
      <div class="scroll-field">
        <input type="password" id="gate-input" autocomplete="off" aria-label="Password" autofocus>
        <div class="scroll-mask" id="gate-mask" aria-hidden="true"></div>
      </div>
    </div>
    <button type="submit" class="casket" id="gate-casket" title="Open" aria-label="Open">
      <img src="/assets/img/hobbies/casket.png" alt="">
    </button>
  </form>
  <p class="gate-error" id="gate-error">Not quite – try again.</p>
</div>

<div id="secret" hidden markdown="1">

<div id="osrs-model" class="osrs-model" title="Drag to rotate"></div>

<div class="osrs-panel">
  <div class="osrs-grid">
    <div class="osrs-cell" data-skill="attack" title="Attack">
      <img src="/assets/img/hobbies/skills/attack.png" alt="Attack">
      <span class="osrs-lvl osrs-lvl-top">99</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">99</span>
    </div>
    <div class="osrs-cell" data-skill="hitpoints" title="Hitpoints">
      <img src="/assets/img/hobbies/skills/hitpoints.png" alt="Hitpoints">
      <span class="osrs-lvl osrs-lvl-top">99</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">99</span>
    </div>
    <div class="osrs-cell" data-skill="mining" title="Mining">
      <img src="/assets/img/hobbies/skills/mining.png?v=2" alt="Mining">
      <span class="osrs-lvl osrs-lvl-top">99</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">99</span>
    </div>
    <div class="osrs-cell" data-skill="strength" title="Strength">
      <img src="/assets/img/hobbies/skills/strength.png" alt="Strength">
      <span class="osrs-lvl osrs-lvl-top">99</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">99</span>
    </div>
    <div class="osrs-cell" data-skill="agility" title="Agility">
      <img src="/assets/img/hobbies/skills/agility.png" alt="Agility">
      <span class="osrs-lvl osrs-lvl-top">76</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">76</span>
    </div>
    <div class="osrs-cell" data-skill="smithing" title="Smithing">
      <img src="/assets/img/hobbies/skills/smithing.png" alt="Smithing">
      <span class="osrs-lvl osrs-lvl-top">72</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">72</span>
    </div>
    <div class="osrs-cell" data-skill="defence" title="Defence">
      <img src="/assets/img/hobbies/skills/defence.png" alt="Defence">
      <span class="osrs-lvl osrs-lvl-top">94</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">94</span>
    </div>
    <div class="osrs-cell" data-skill="herblore" title="Herblore">
      <img src="/assets/img/hobbies/skills/herblore.png" alt="Herblore">
      <span class="osrs-lvl osrs-lvl-top">76</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">76</span>
    </div>
    <div class="osrs-cell" data-skill="fishing" title="Fishing">
      <img src="/assets/img/hobbies/skills/fishing.png" alt="Fishing">
      <span class="osrs-lvl osrs-lvl-top">71</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">71</span>
    </div>
    <div class="osrs-cell" data-skill="ranged" title="Ranged">
      <img src="/assets/img/hobbies/skills/ranged.png" alt="Ranged">
      <span class="osrs-lvl osrs-lvl-top">97</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">97</span>
    </div>
    <div class="osrs-cell" data-skill="thieving" title="Thieving">
      <img src="/assets/img/hobbies/skills/thieving.png?v=2" alt="Thieving">
      <span class="osrs-lvl osrs-lvl-top">82</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">82</span>
    </div>
    <div class="osrs-cell" data-skill="cooking" title="Cooking">
      <img src="/assets/img/hobbies/skills/cooking.png" alt="Cooking">
      <span class="osrs-lvl osrs-lvl-top">71</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">71</span>
    </div>
    <div class="osrs-cell" data-skill="prayer" title="Prayer">
      <img src="/assets/img/hobbies/skills/prayer.png" alt="Prayer">
      <span class="osrs-lvl osrs-lvl-top">81</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">81</span>
    </div>
    <div class="osrs-cell" data-skill="crafting" title="Crafting">
      <img src="/assets/img/hobbies/skills/crafting.png" alt="Crafting">
      <span class="osrs-lvl osrs-lvl-top">73</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">73</span>
    </div>
    <div class="osrs-cell" data-skill="firemaking" title="Firemaking">
      <img src="/assets/img/hobbies/skills/firemaking.png" alt="Firemaking">
      <span class="osrs-lvl osrs-lvl-top">78</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">78</span>
    </div>
    <div class="osrs-cell" data-skill="magic" title="Magic">
      <img src="/assets/img/hobbies/skills/magic.png" alt="Magic">
      <span class="osrs-lvl osrs-lvl-top">98</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">98</span>
    </div>
    <div class="osrs-cell" data-skill="fletching" title="Fletching">
      <img src="/assets/img/hobbies/skills/fletching.png" alt="Fletching">
      <span class="osrs-lvl osrs-lvl-top">71</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">71</span>
    </div>
    <div class="osrs-cell" data-skill="woodcutting" title="Woodcutting">
      <img src="/assets/img/hobbies/skills/woodcutting.png" alt="Woodcutting">
      <span class="osrs-lvl osrs-lvl-top">87</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">87</span>
    </div>
    <div class="osrs-cell" data-skill="runecrafting" title="Runecrafting">
      <img src="/assets/img/hobbies/skills/runecraft.png" alt="Runecrafting">
      <span class="osrs-lvl osrs-lvl-top">71</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">71</span>
    </div>
    <div class="osrs-cell" data-skill="slayer" title="Slayer">
      <img src="/assets/img/hobbies/skills/slayer.png" alt="Slayer">
      <span class="osrs-lvl osrs-lvl-top">81</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">81</span>
    </div>
    <div class="osrs-cell" data-skill="farming" title="Farming">
      <img src="/assets/img/hobbies/skills/farming.png" alt="Farming">
      <span class="osrs-lvl osrs-lvl-top">94</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">94</span>
    </div>
    <div class="osrs-cell" data-skill="construction" title="Construction">
      <img src="/assets/img/hobbies/skills/construction.png" alt="Construction">
      <span class="osrs-lvl osrs-lvl-top">86</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">86</span>
    </div>
    <div class="osrs-cell" data-skill="hunter" title="Hunter">
      <img src="/assets/img/hobbies/skills/hunter.png" alt="Hunter">
      <span class="osrs-lvl osrs-lvl-top">70</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">70</span>
    </div>
    <div class="osrs-cell" data-skill="sailing" title="Sailing">
      <img src="/assets/img/hobbies/skills/sailing.png" alt="Sailing">
      <span class="osrs-lvl osrs-lvl-top">76</span><span class="osrs-slash"></span><span class="osrs-lvl osrs-lvl-bot">76</span>
    </div>
  </div>
  <div class="osrs-total">Total level: <span id="osrs-total">2001</span></div>
</div>
<div class="goal">
  <div class="goal-label">
    <span class="goal-name"><img src="/assets/img/hobbies/skills/mining.png?v=2" alt="Mining"></span>
    <span><span id="mining-xp">31,395,445</span> / 200,000,000 XP (<span id="mining-pct">15.7</span>%)</span>
  </div>
  <div class="goal-track">
    <div class="goal-miner" id="goal-miner" style="left: 15.7%">
      <canvas id="miner-canvas"></canvas>
    </div>
    <div class="goal-bar"><div class="goal-fill" id="mining-fill" style="width: 15.7%"></div></div>
    <div class="goal-milestone cape reached" data-xp="13034431" style="left: 6.51722%" title="Mining cape – 13,034,431 XP">
      <img src="/assets/img/hobbies/ores/cape.png" alt="Mining cape"><span>13m</span>
    </div>
    <div class="goal-milestone reached" data-xp="25000000" style="left: 12.5%" title="25,000,000 XP">
      <span>25m</span>
    </div>
    <div class="goal-milestone" data-xp="50000000" style="left: 25%" title="50,000,000 XP">
      <span>50m</span>
    </div>
    <div class="goal-milestone" data-xp="75000000" style="left: 37.5%" title="75,000,000 XP">
      <span>75m</span>
    </div>
    <div class="goal-milestone" data-xp="100000000" style="left: 50%" title="100,000,000 XP">
      <span>100m</span>
    </div>
    <div class="goal-milestone" data-xp="125000000" style="left: 62.5%" title="125,000,000 XP">
      <span>125m</span>
    </div>
    <div class="goal-milestone" data-xp="150000000" style="left: 75%" title="150,000,000 XP">
      <span>150m</span>
    </div>
    <div class="goal-milestone" data-xp="175000000" style="left: 87.5%" title="175,000,000 XP">
      <span>175m</span>
    </div>
    <div class="goal-milestone special" data-xp="200000000" style="left: 100%" title="3rd age pickaxe – 200,000,000 XP">
      <img src="/assets/img/hobbies/ores/third-age-pickaxe.png" alt="3rd age pickaxe"><span>200m</span>
    </div>
  </div>
</div>
<p class="updated" id="osrs-updated"></p>

<div class="favs">
  <a class="fav" href="https://myanimelist.net/manga/1517/JoJo_no_Kimyou_na_Bouken_Part_1__Phantom_Blood">
    <img src="/assets/img/hobbies/manga/1517.jpg" alt="JoJo Part 1: Phantom Blood" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">JoJo Part 1: Phantom Blood<small>Manga · 1986</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/656/Vagabond">
    <img src="/assets/img/hobbies/manga/656.jpg" alt="Vagabond" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Vagabond<small>Manga · 1998</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/2/Berserk">
    <img src="/assets/img/hobbies/manga/2.jpg" alt="Berserk" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Berserk<small>Manga · 1989</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/13/One_Piece">
    <img src="/assets/img/hobbies/manga/13.jpg" alt="One Piece" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">One Piece<small>Manga · 1997</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/664/Akira">
    <img src="/assets/img/hobbies/manga/664.jpg" alt="Akira" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Akira<small>Manga · 1982</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/25/Fullmetal_Alchemist">
    <img src="/assets/img/hobbies/manga/25.jpg" alt="Fullmetal Alchemist" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Fullmetal Alchemist<small>Manga · 2001</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/564/Gantz">
    <img src="/assets/img/hobbies/manga/564.jpg" alt="Gantz" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Gantz<small>Manga · 2000</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/61027/Giganto_Makhia">
    <img src="/assets/img/hobbies/manga/61027.jpg" alt="Giganto Maxia" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Giganto Maxia<small>Manga · 2013</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/1706/JoJo_no_Kimyou_na_Bouken_Part_7__Steel_Ball_Run">
    <img src="/assets/img/hobbies/manga/1706.jpg" alt="JoJo Part 7: Steel Ball Run" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">JoJo Part 7: Steel Ball Run<small>Manga · 2004</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/1/Monster">
    <img src="/assets/img/hobbies/manga/1.jpg" alt="Monster" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Monster<small>Manga · 1994</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/7887/Toriko">
    <img src="/assets/img/hobbies/manga/7887.jpg" alt="Toriko" loading="lazy">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Toriko<small>Manga · 2008</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/23390/Shingeki_no_Kyojin">
    <img src="/assets/img/hobbies/manga/23390.jpg" alt="Attack on Titan" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">Attack on Titan<small>Manga · 2009</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/42/Dragon_Ball">
    <img src="/assets/img/hobbies/manga/42.jpg" alt="Dragon Ball" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">Dragon Ball<small>Manga · 1984</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/1630/JoJo_no_Kimyou_na_Bouken_Part_2__Sentou_Chouryuu">
    <img src="/assets/img/hobbies/manga/1630.jpg" alt="JoJo Part 2: Battle Tendency" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">JoJo Part 2: Battle Tendency<small>Manga · 1987</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/3008/JoJo_no_Kimyou_na_Bouken_Part_5__Ougon_no_Kaze">
    <img src="/assets/img/hobbies/manga/3008.jpg" alt="JoJo Part 5: Golden Wind" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">JoJo Part 5: Golden Wind<small>Manga · 1995</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/3009/JoJo_no_Kimyou_na_Bouken_Part_6__Stone_Ocean">
    <img src="/assets/img/hobbies/manga/3009.jpg" alt="JoJo Part 6: Stone Ocean" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">JoJo Part 6: Stone Ocean<small>Manga · 1999</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/25515/JoJo_no_Kimyou_na_Bouken_Part_8__JoJolion">
    <img src="/assets/img/hobbies/manga/25515.jpg" alt="JoJo Part 8: JoJolion" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">JoJo Part 8: JoJolion<small>Manga · 2011</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/139629/JoJo_no_Kimyou_na_Bouken_Part_9__The_JoJoLands">
    <img src="/assets/img/hobbies/manga/139629.jpg" alt="JoJo Part 9: The JoJoLands" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">JoJo Part 9: The JoJoLands<small>Manga · 2023</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/11/Naruto">
    <img src="/assets/img/hobbies/manga/11.jpg" alt="Naruto" loading="lazy">
    <span class="fav-score">★ 9</span>
    <span class="fav-title">Naruto<small>Manga · 1999</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/12/Bleach">
    <img src="/assets/img/hobbies/manga/12.jpg" alt="Bleach" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Bleach<small>Manga · 2001</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/116778/Chainsaw_Man">
    <img src="/assets/img/hobbies/manga/116778.jpg" alt="Chainsaw Man" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Chainsaw Man<small>Manga · 2018</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/21/Death_Note">
    <img src="/assets/img/hobbies/manga/21.jpg" alt="Death Note" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Death Note<small>Manga · 2003</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/132335/Death_Note_Tanpenshuu">
    <img src="/assets/img/hobbies/manga/132335.jpg" alt="Death Note Short Stories" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Death Note Short Stories<small>Manga · 2003</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/121329/Duranki">
    <img src="/assets/img/hobbies/manga/121329.jpg" alt="Dur-an-ki" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Dur-an-ki<small>Manga · 2019</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/909/Gyo__Ugomeku_Bukimi">
    <img src="/assets/img/hobbies/manga/909.jpg" alt="Gyo: The Death-Stench Creeps" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Gyo: The Death-Stench Creeps<small>Manga · 2001</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/872/JoJo_no_Kimyou_na_Bouken_Part_3__Stardust_Crusaders">
    <img src="/assets/img/hobbies/manga/872.jpg" alt="JoJo Part 3: Stardust Crusaders" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">JoJo Part 3: Stardust Crusaders<small>Manga · 1989</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/3006/JoJo_no_Kimyou_na_Bouken_Part_4__Diamond_wa_Kudakenai">
    <img src="/assets/img/hobbies/manga/3006.jpg" alt="JoJo Part 4: Diamond Is Unbreakable" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">JoJo Part 4: Diamond Is Unbreakable<small>Manga · 1992</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/698/Shinseiki_Evangelion">
    <img src="/assets/img/hobbies/manga/698.jpg" alt="Neon Genesis Evangelion" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Neon Genesis Evangelion<small>Manga · 1994</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/122305/One_Piece_Gakuen">
    <img src="/assets/img/hobbies/manga/122305.jpg" alt="One Piece Gakuen" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">One Piece Gakuen<small>Manga · 2019</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/3992/Jigokusei_Remina">
    <img src="/assets/img/hobbies/manga/3992.jpg" alt="Remina" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Remina<small>Manga · 2004</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/136793/Itou_Junji_Jisen_Kessakushuu">
    <img src="/assets/img/hobbies/manga/136793.jpg" alt="Shiver: Junji Ito Selected Stories" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Shiver: Junji Ito Selected Stories<small>Manga · 1990</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/642/Vinland_Saga">
    <img src="/assets/img/hobbies/manga/642.jpg" alt="Vinland Saga" loading="lazy">
    <span class="fav-score">★ 8</span>
    <span class="fav-title">Vinland Saga<small>Manga · 2005</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/142552/Fujiko_no_Kimyou_na_Shoseijutsu__Whitesnake_no_Gosan">
    <img src="/assets/img/hobbies/manga/142552.jpg" alt="Fujiko no Kimyou na Shoseijutsu: Whitesnake no Gosan" loading="lazy">
    <span class="fav-score">★ 7</span>
    <span class="fav-title">Fujiko no Kimyou na Shoseijutsu: Whitesnake no Gosan<small>One-shot · 2021</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/936/Homunculus">
    <img src="/assets/img/hobbies/manga/936.jpg" alt="Homunculus" loading="lazy">
    <span class="fav-score">★ 7</span>
    <span class="fav-title">Homunculus<small>Manga · 2003</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/14440/I_Am_a_Hero">
    <img src="/assets/img/hobbies/manga/14440.jpg" alt="I Am a Hero" loading="lazy">
    <span class="fav-score">★ 7</span>
    <span class="fav-title">I Am a Hero<small>Manga · 2009</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/91941/Made_in_Abyss">
    <img src="/assets/img/hobbies/manga/91941.jpg" alt="Made in Abyss" loading="lazy">
    <span class="fav-score">★ 7</span>
    <span class="fav-title">Made in Abyss<small>Manga · 2012</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/120865/One_Piece__Roronoa_Zoro_Umi_ni_Chiru">
    <img src="/assets/img/hobbies/manga/120865.jpg" alt="One Piece: Boichi Covers Zolo vs. Mihawk" loading="lazy">
    <span class="fav-score">★ 7</span>
    <span class="fav-title">One Piece: Boichi Covers Zolo vs. Mihawk<small>One-shot · 2019</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/145980/One_Piece__Nami_vs_Kalifa">
    <img src="/assets/img/hobbies/manga/145980.jpg" alt="One Piece: Nami vs. Kalifa" loading="lazy">
    <span class="fav-score">★ 7</span>
    <span class="fav-title">One Piece: Nami vs. Kalifa<small>One-shot · 2022</small></span>
  </a>
</div>

</div>

<script>
  (function () {
    // SHA-256 of the password. To change it, run: printf 'newpassword' | shasum -a 256
    var HASH = "3338a5fdfc10e11cebdef7ffa6662e03257106eb43345c4436898c2370a92dc8";
    var gate = document.getElementById("gate");
    var secret = document.getElementById("secret");

    function unlock() {
      document.getElementById("gate-input").blur();
      gate.hidden = true;
      secret.hidden = false;
    }

    // Lock again when the page is restored via the back/forward buttons.
    window.addEventListener("pageshow", function (e) {
      if (e.persisted) {
        secret.hidden = true;
        gate.hidden = false;
        document.getElementById("gate-input").value = "";
        drawMask();
      }
    });

    // Draw one dot per typed character, each with its own underline, plus a blinking caret.
    var input = document.getElementById("gate-input");
    var mask = document.getElementById("gate-mask");
    function drawMask() {
      var html = "";
      for (var i = 0; i < input.value.length; i++) html += "<span>•</span>";
      if (document.activeElement === input) html += '<span class="caret"></span>';
      mask.innerHTML = html;
    }
    ["input", "focus", "blur"].forEach(function (ev) { input.addEventListener(ev, drawMask); });
    drawMask();

    var casket = document.getElementById("gate-casket");
    document.getElementById("gate-form").addEventListener("submit", function (e) {
      e.preventDefault();
      crypto.subtle.digest("SHA-256", new TextEncoder().encode(input.value)).then(function (buf) {
        var hex = Array.from(new Uint8Array(buf)).map(function (b) {
          return b.toString(16).padStart(2, "0");
        }).join("");
        if (hex === HASH) {
          unlock();
        } else {
          document.getElementById("gate-error").style.visibility = "visible";
          casket.classList.remove("shake");
          void casket.offsetWidth; // restart the animation
          casket.classList.add("shake");
        }
      });
    });
  })();
</script>

<script>
  // Live OSRS stats from Wise Old Man (mirrors the official hiscores). The numbers in the HTML are the fallback.
  (function () {
    var GOAL = 200000000;
    fetch("https://api.wiseoldman.net/v2/players/levinlevin")
      .then(function (r) { return r.json(); })
      .then(function (player) {
        var skills = player.latestSnapshot.data.skills;

        var xp = skills.mining.experience;
        var pct = (xp / GOAL * 100).toFixed(1);
        document.getElementById("mining-xp").textContent = xp.toLocaleString("en-US");
        document.getElementById("mining-pct").textContent = pct;
        document.getElementById("mining-fill").style.width = pct + "%";
        document.getElementById("goal-miner").style.left = pct + "%";
        document.querySelectorAll(".goal-milestone").forEach(function (m) {
          m.classList.toggle("reached", xp >= Number(m.dataset.xp));
        });

        document.querySelectorAll(".osrs-cell").forEach(function (cell) {
          var skill = skills[cell.dataset.skill];
          if (!skill) return;
          cell.querySelector(".osrs-lvl-top").textContent = skill.level;
          cell.querySelector(".osrs-lvl-bot").textContent = skill.level;
          cell.title = cell.title.split(":")[0] + ": " + skill.experience.toLocaleString("en-US") + " XP";
        });
        document.getElementById("osrs-total").textContent = skills.overall.level;

        document.getElementById("osrs-updated").textContent =
          "Stats last updated " + new Date(player.updatedAt).toLocaleDateString("en-GB", { day: "numeric", month: "long", year: "numeric" }) + ".";
      })
      .catch(function () {});
  })();
</script>

<script type="importmap">
  {
    "imports": {
      "three": "https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.module.js",
      "three/addons/": "https://cdn.jsdelivr.net/npm/three@0.160.0/examples/jsm/"
    }
  }
</script>

<script type="module">
  // Rotating 3D model of my OSRS character and pet (exported from RuneProfile).
  import * as THREE from "three";
  import { GLTFLoader } from "three/addons/loaders/GLTFLoader.js";
  import { OrbitControls } from "three/addons/controls/OrbitControls.js";

  const container = document.getElementById("osrs-model");
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(35, 1, 0.1, 100);
  camera.position.set(0, 1.0, 3.6);

  const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
  renderer.setPixelRatio(window.devicePixelRatio);
  container.appendChild(renderer.domElement);

  const controls = new OrbitControls(camera, renderer.domElement);
  controls.target.set(0, 0.75, 0);
  controls.enableZoom = false;
  controls.enablePan = false;
  controls.minPolarAngle = Math.PI / 4;
  controls.maxPolarAngle = Math.PI / 2;

  // Stand each model on the ground at the given x, inside a pivot so it can spin in place.
  const loader = new GLTFLoader();
  const pivots = [];
  function place(url, x) {
    const pivot = new THREE.Group();
    pivot.position.x = x;
    scene.add(pivot);
    pivots.push(pivot);
    loader.load(url, (gltf) => {
      const model = gltf.scene;
      const box = new THREE.Box3().setFromObject(model);
      const center = box.getCenter(new THREE.Vector3());
      model.position.set(-center.x, -box.min.y, -center.z);
      pivot.add(model);
    });
  }
  place("/assets/img/hobbies/osrs-character.glb", -0.3);
  place("/assets/img/hobbies/osrs-pet.glb", 0.6);

  // The page starts hidden behind the password, so size the canvas whenever it becomes visible.
  new ResizeObserver(() => {
    const w = container.clientWidth, h = container.clientHeight;
    if (!w || !h) return;
    renderer.setSize(w, h, false); // CSS controls the displayed size
    camera.aspect = w / h;
    camera.updateProjectionMatrix();
  }).observe(container);

  renderer.setAnimationLoop(() => {
    for (const pivot of pivots) pivot.rotation.y += 0.01;
    controls.update();
    renderer.render(scene, camera);
  });

  // Little miner on the goal bar: the same character, rendered at low resolution for a pixel-art look.
  // The model is a single static mesh, so both arms are cut out by position and swung about the shoulders.
  const miner = document.getElementById("goal-miner");
  const minerRenderer = new THREE.WebGLRenderer({ canvas: document.getElementById("miner-canvas"), antialias: false, alpha: true });
  minerRenderer.setPixelRatio(1);
  minerRenderer.setSize(40, 52, false); // drawn at 2x via CSS
  const minerScene = new THREE.Scene();
  const minerCamera = new THREE.PerspectiveCamera(30, 40 / 52, 0.1, 50);
  minerCamera.position.set(0, 0.98, 4.6);
  minerCamera.lookAt(0, 0.98, 0);
  const minerPivot = new THREE.Group();
  minerPivot.position.x = -0.3;
  minerScene.add(minerPivot);
  // Rig, in model units. The body hinges at the hips: the bend fades in smoothly over the waist (no seam),
  // the legs stay straight, and the hips shift back and drop a little as the chest goes forward, the way a
  // person keeps their balance. The feet stay planted.
  // The pickaxe is split from the right arm and held by its handle; both arms turn at the shoulders so the
  // hands stay on it. Arms and pickaxe ride on the fully bent chest. The shield on the left side is dropped.
  const X_AXIS = new THREE.Vector3(1, 0, 0);
  const BEND_PIVOT = new THREE.Vector3(0, 88, 0); // hips
  const BEND_FROM = 72, BEND_TO = 112; // heights over which the bend fades in (the waist)
  const HIP_BACK = 16, HIP_DROP = 7; // how far the hips move back / down at a 45 degree bend
  const RIGHT_SHOULDER = new THREE.Vector3(-30, 140, 0);
  const LEFT_SHOULDER = new THREE.Vector3(30, 140, 0);
  const GRIP = new THREE.Vector3(-22, 106, 18); // right hand at the end of the handle in the model's pose
  const HAND_REST = -62; // direction shoulder -> hand in the model's pose, degrees above forward
  const HANDLE_REST = 41; // direction grip -> pickaxe head end in the model's pose, degrees above forward
  const LEFT_INWARD = -40 * Math.PI / 180; // bring the left arm across the body to the handle
  const LEFT_OFFSET = -28 * Math.PI / 180; // the left arm hangs lower than the right in the model's pose
  const isPickaxe = (c) => c.x < -4 && c.z > 19 && c.y > 92;
  const isRightArm = (c) => c.x < -21 && c.y > 88 && c.y < 150;
  const isShield = (c) => c.x > 34 && (c.z > 16 || c.z < -16 || c.y < 115);
  const isLeftArm = (c) => c.x > 21 && c.y > 88 && c.y < 150;
  const uppers = [], bodies = [], rightArms = [], leftArms = [], pickaxes = [];
  function part(mesh, index, parent, pivotPoint, parentOrigin, list) {
    const geometry = mesh.geometry.clone();
    geometry.setIndex(index);
    const piece = new THREE.Mesh(geometry, mesh.material);
    piece.position.copy(pivotPoint).negate();
    const pivot = new THREE.Group();
    pivot.position.copy(pivotPoint).sub(parentOrigin);
    pivot.add(piece);
    parent.add(pivot);
    list.push(pivot);
  }
  loader.load("/assets/img/hobbies/osrs-character.glb", (gltf) => {
    const body = gltf.scene;
    const meshes = [];
    body.traverse((o) => { if (o.isMesh) meshes.push(o); });
    const a = new THREE.Vector3(), b = new THREE.Vector3(), c = new THREE.Vector3();
    meshes.forEach((mesh, i) => {
      const pos = mesh.geometry.attributes.position;
      const idx = mesh.geometry.index.array;
      const pickIdx = [], rightIdx = [], leftIdx = [], bodyIdx = [];
      for (let t = 0; t < idx.length; t += 3) {
        a.fromBufferAttribute(pos, idx[t]);
        b.fromBufferAttribute(pos, idx[t + 1]);
        c.fromBufferAttribute(pos, idx[t + 2]);
        const centre = a.add(b).add(c).divideScalar(3);
        if (isShield(centre)) continue;
        const target = isPickaxe(centre) ? pickIdx : isRightArm(centre) ? rightIdx : isLeftArm(centre) ? leftIdx : bodyIdx;
        target.push(idx[t], idx[t + 1], idx[t + 2]);
      }
      // the chest frame that the arms and pickaxe hang from
      const upper = new THREE.Group();
      upper.position.copy(BEND_PIVOT);
      mesh.add(upper);
      uppers.push(upper);
      part(mesh, rightIdx, upper, RIGHT_SHOULDER, BEND_PIVOT, rightArms);
      part(mesh, leftIdx, upper, LEFT_SHOULDER, BEND_PIVOT, leftArms);
      part(mesh, pickIdx, upper, GRIP, BEND_PIVOT, pickaxes);
      mesh.geometry = mesh.geometry.clone();
      mesh.geometry.setIndex(bodyIdx);
      mesh.frustumCulled = false;
      bodies.push({ mesh, rest: Float32Array.from(mesh.geometry.attributes.position.array) });
      if (i === 0) {
        // Headless head: the model's neck stump is too small to survive pixelation, so draw a bolder one.
        const stump = new THREE.Mesh(new THREE.CylinderGeometry(11, 12, 10, 8), new THREE.MeshBasicMaterial({ color: 0xa3201a }));
        stump.position.set(0, 167, 3).sub(BEND_PIVOT);
        const wound = new THREE.Mesh(new THREE.CylinderGeometry(8, 8, 2, 8), new THREE.MeshBasicMaterial({ color: 0xf0782a }));
        wound.position.y = 5.5;
        stump.add(wound);
        upper.add(stump);
      }
    });
    const box = new THREE.Box3().setFromObject(body);
    const center = box.getCenter(new THREE.Vector3());
    body.position.set(-center.x, -box.min.y, -center.z);
    const facing = new THREE.Group();
    facing.rotation.y = Math.PI / 2; // face right, towards the next milestone
    facing.add(body);
    minerPivot.add(facing);
  });
  const hipOffset = new THREE.Vector3();
  function bendBody(bend) {
    const amount = bend / (Math.PI / 4); // 1 at a 45 degree bend
    hipOffset.set(0, -HIP_DROP * Math.abs(amount), -HIP_BACK * amount);
    for (const { mesh, rest } of bodies) {
      const arr = mesh.geometry.attributes.position.array;
      for (let v = 0; v < arr.length; v += 3) {
        const y = rest[v + 1], z = rest[v + 2];
        const k = Math.min(1, Math.max(0, (y - BEND_FROM) / (BEND_TO - BEND_FROM)));
        const ang = bend * k * k * (3 - 2 * k); // smoothstep across the waist
        const cy = y - BEND_PIVOT.y, cz = z - BEND_PIVOT.z;
        const cos = Math.cos(ang), sin = Math.sin(ang);
        // legs lean with the hips (0 at the feet, 1 at the hips); everything above moves with the hips
        const lean = Math.min(1, Math.max(0, y / BEND_PIVOT.y));
        arr[v + 1] = BEND_PIVOT.y + cy * cos - cz * sin + hipOffset.y * lean;
        arr[v + 2] = BEND_PIVOT.z + cy * sin + cz * cos + hipOffset.z * lean;
      }
      mesh.geometry.attributes.position.needsUpdate = true;
    }
  }

  // Keyframes measured from the OSRS wiki's mining animation (File:Mining.gif), times in ms of an 800 ms cycle.
  // Angles in degrees relative to the ground: hand = shoulder -> hands, handle = hands -> pickaxe head end
  // (0 = straight ahead, 90 = straight up), bend = forward bend at the hips.
  // Nothing is frozen: the strike sinks a little further into the rock and the wind-up keeps rising slowly.
  const KEYS = [
    { t: 0, hand: -66, handle: -49, bend: 40, stop: true }, // strike: pickaxe bites the rock
    { t: 110, hand: -70, handle: -54, bend: 44 }, // follow-through into the rock
    { t: 170, hand: -67, handle: -7, bend: 14 }, // pulled out, handle level
    { t: 230, hand: -25, handle: 118, bend: 5 }, // pickaxe flips up
    { t: 290, hand: 2, handle: 131, bend: 1 }, // hands rise in front
    { t: 340, hand: 45, handle: 137, bend: -2 },
    { t: 420, hand: 75, handle: 165, bend: -4 },
    { t: 470, hand: 86, handle: 174, bend: -5 }, // wound up: arms straight up, pickaxe level behind
    { t: 710, hand: 92, handle: 184, bend: -7, stop: true }, // still drawing back, then...
    { t: 770, hand: -21, handle: 87, bend: 10 }, // arms thrown forward, handle upright
    { t: 800, hand: -66, handle: -49, bend: 40, impact: true }, // into the rock
  ];
  const CYCLE = 800, SWING_MS = 900; // the GIF's timing, played slightly slower
  const CHANNELS = ["hand", "handle", "bend"];
  // tangents for cubic Hermite interpolation: zero at stops, carried through at impact, smooth elsewhere
  KEYS.forEach((k, i) => {
    k.m = {};
    for (const ch of CHANNELS) {
      if (k.stop) k.m[ch] = 0;
      else if (k.impact) k.m[ch] = (k[ch] - KEYS[i - 1][ch]) / (k.t - KEYS[i - 1].t) * 1.5;
      else k.m[ch] = (KEYS[i + 1][ch] - KEYS[i - 1][ch]) / (KEYS[i + 1].t - KEYS[i - 1].t);
    }
  });
  function pose(ms) {
    let i = 1;
    while (i < KEYS.length - 1 && KEYS[i].t <= ms) i++;
    const k0 = KEYS[i - 1], k1 = KEYS[i];
    const dt = k1.t - k0.t, x = (ms - k0.t) / dt;
    const h00 = 2 * x ** 3 - 3 * x ** 2 + 1, h10 = x ** 3 - 2 * x ** 2 + x, h01 = -2 * x ** 3 + 3 * x ** 2, h11 = x ** 3 - x ** 2;
    const out = {};
    for (const ch of CHANNELS) out[ch] = h00 * k0[ch] + h10 * dt * k0.m[ch] + h01 * k1[ch] + h11 * dt * k1.m[ch];
    return out;
  }
  function chips() {
    for (let i = 0; i < 3; i++) {
      const chip = document.createElement("span");
      chip.className = "goal-chip";
      chip.style.left = "66px";
      chip.style.top = "88px";
      chip.style.setProperty("--dx", 2 + Math.random() * 10 + "px");
      chip.style.setProperty("--dy", -6 - Math.random() * 14 + "px");
      miner.appendChild(chip);
      setTimeout(() => chip.remove(), 500);
    }
  }

  const still = window.matchMedia("(prefers-reduced-motion: reduce)").matches;
  const DEG = Math.PI / 180;
  const handOffset = GRIP.clone().sub(RIGHT_SHOULDER);
  const grip = new THREE.Vector3();
  let lastMs = 0;
  minerRenderer.setAnimationLoop((t) => {
    const ms = still ? 600 : ((t % SWING_MS) / SWING_MS) * CYCLE;
    const { hand, handle, bend } = pose(ms);
    // hand/handle are measured against the ground; the arms ride on the bent chest, so add the bend back
    const arm = (HAND_REST - hand - bend) * DEG; // rotation about the sideways axis; positive tips forward-down
    const pick = (HANDLE_REST - handle - bend) * DEG;
    bendBody(bend * DEG);
    grip.copy(handOffset).applyAxisAngle(X_AXIS, arm).add(RIGHT_SHOULDER).sub(BEND_PIVOT);
    for (const upper of uppers) {
      upper.position.copy(BEND_PIVOT).add(hipOffset);
      upper.rotation.x = bend * DEG;
    }
    for (const pivot of rightArms) pivot.rotation.x = arm;
    for (const pivot of leftArms) pivot.rotation.set(arm + LEFT_OFFSET, 0, LEFT_INWARD);
    for (const pivot of pickaxes) {
      pivot.position.copy(grip);
      pivot.rotation.x = pick;
    }
    if (ms < lastMs) chips(); // the cycle starts on the strike
    lastMs = ms;
    minerRenderer.render(minerScene, minerCamera);
  });
</script>
