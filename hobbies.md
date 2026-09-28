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
.gate input {
  font: inherit;
  padding: 6px 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
.gate button {
  font: inherit;
  padding: 6px 14px;
  margin-left: 6px;
  border: 1px solid #ccc;
  border-radius: 4px;
  background: none;
  cursor: pointer;
}
.gate-error {
  color: #D21515;
  visibility: hidden;
}

.osrs-model {
  width: 100%;
  height: 420px;
  margin: 20px 0;
  cursor: grab;
}

.goal {
  margin: 10px 0 20px;
}
.goal-label {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  font-size: 0.9em;
  margin-bottom: 4px;
}
.goal-bar {
  height: 10px;
  border-radius: 5px;
  background: #eee;
  overflow: hidden;
}
.goal-fill {
  height: 100%;
  background: #D21515;
}

.skills {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 6px;
  font-size: 0.85em;
}
.skill {
  display: flex;
  justify-content: space-between;
  padding: 4px 8px;
  border: 1px solid #eee;
  border-radius: 4px;
}
.updated {
  font-size: 0.8em;
  color: #999;
}

.favs {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
  gap: 12px;
  margin: 20px 0;
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
  <p>You found the secret page. What's the password?</p>
  <form id="gate-form">
    <input type="password" id="gate-input" autocomplete="off" autofocus>
    <button type="submit">Enter</button>
  </form>
  <p class="gate-error" id="gate-error">Not quite – try again.</p>
</div>

<div id="secret" hidden markdown="1">

### Video Games

<p align="justify"><b>Old School RuneScape</b> – [Text to come.] My current goal is <b>200m Mining</b> experience.</p>

<div id="osrs-model" class="osrs-model" title="Drag to rotate"></div>

<div class="goal">
  <div class="goal-label">
    <span>Mining</span>
    <span><span id="mining-xp">31,374,069</span> / 200,000,000 XP (<span id="mining-pct">15.7</span>%)</span>
  </div>
  <div class="goal-bar"><div class="goal-fill" id="mining-fill" style="width: 15.7%"></div></div>
</div>

<div class="skills" id="skills"></div>
<p class="updated" id="osrs-updated"></p>

### Manga

<p align="justify">My favourite manga and how I rated them on <a href="https://myanimelist.net/profile/Yagamifyed">MyAnimeList</a>:</p>

<div class="favs">
  <a class="fav" href="https://myanimelist.net/manga/1517/JoJo_no_Kimyou_na_Bouken_Part_1__Phantom_Blood">
    <img src="/assets/img/hobbies/manga-jojo-phantom-blood.jpg" alt="JoJo no Kimyou na Bouken Part 1: Phantom Blood">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">JoJo Part 1: Phantom Blood<small>Manga · 1986</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/656/Vagabond">
    <img src="/assets/img/hobbies/manga-vagabond.jpg" alt="Vagabond">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Vagabond<small>Manga · 1998</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/2/Berserk">
    <img src="/assets/img/hobbies/manga-berserk.jpg" alt="Berserk">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">Berserk<small>Manga · 1989</small></span>
  </a>
  <a class="fav" href="https://myanimelist.net/manga/13/One_Piece">
    <img src="/assets/img/hobbies/manga-one-piece.jpg" alt="One Piece">
    <span class="fav-score">★ 10</span>
    <span class="fav-title">One Piece<small>Manga · 1997</small></span>
  </a>
</div>

### Exercise

<p align="justify">[Lifting weights and running – text to come.]</p>

### Chess

<p align="justify">[Text to come.]</p>

</div>

<script>
  (function () {
    // SHA-256 of the password. To change it, run: printf 'newpassword' | shasum -a 256
    var HASH = "3338a5fdfc10e11cebdef7ffa6662e03257106eb43345c4436898c2370a92dc8";
    var gate = document.getElementById("gate");
    var secret = document.getElementById("secret");

    function unlock() {
      gate.hidden = true;
      secret.hidden = false;
      try { sessionStorage.setItem("hobbies-unlocked", "1"); } catch (e) {}
    }

    try {
      if (sessionStorage.getItem("hobbies-unlocked") === "1") unlock();
    } catch (e) {}

    document.getElementById("gate-form").addEventListener("submit", function (e) {
      e.preventDefault();
      var value = document.getElementById("gate-input").value;
      crypto.subtle.digest("SHA-256", new TextEncoder().encode(value)).then(function (buf) {
        var hex = Array.from(new Uint8Array(buf)).map(function (b) {
          return b.toString(16).padStart(2, "0");
        }).join("");
        if (hex === HASH) {
          unlock();
        } else {
          document.getElementById("gate-error").style.visibility = "visible";
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

        var grid = document.getElementById("skills");
        Object.keys(skills).forEach(function (key) {
          var name = key === "overall" ? "Total" : key.charAt(0).toUpperCase() + key.slice(1);
          var cell = document.createElement("div");
          cell.className = "skill";
          cell.title = skills[key].experience.toLocaleString("en-US") + " XP";
          cell.innerHTML = "<span></span><span></span>";
          cell.children[0].textContent = name;
          cell.children[1].textContent = skills[key].level;
          grid.appendChild(cell);
        });

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
    renderer.setSize(w, h);
    camera.aspect = w / h;
    camera.updateProjectionMatrix();
  }).observe(container);

  renderer.setAnimationLoop(() => {
    for (const pivot of pivots) pivot.rotation.y += 0.01;
    controls.update();
    renderer.render(scene, camera);
  });
</script>
