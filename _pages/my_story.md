---
layout: page
permalink: /about/
title: about
description: The places, people and questions behind my research.
nav: true
nav_order: 1
---

<div class="story">

  <section class="story-chapter">
    <h2 class="story-chapter-title">🗺️ About my research</h2>

    <div class="scrolly">
      <div class="scrolly-figure" aria-hidden="true">
        <img class="active" data-step="1" src="{{ '/assets/img/about/research-river.jpg' | relative_url }}" alt="">
        <img data-step="2" src="{{ '/assets/img/about/research-depopulation-maps.jpg' | relative_url }}" alt="">
        <img data-step="3" src="{{ '/assets/img/about/research-madrid-rents.jpg' | relative_url }}" alt="">
      </div>

      <div class="scrolly-steps">
        <div class="scrolly-step" data-step="1">
          <img class="step-img" src="{{ '/assets/img/about/research-river.jpg' | relative_url }}" alt="The Tormes river near Encinas de Abajo, Salamanca" loading="lazy">
          <span class="step-kicker">Where it all starts</span>
          <h3>A village on the banks of the Tormes</h3>
          <p>
            I was born and raised in Encinas de Abajo, a small village on the banks of the Tormes river, in the province of Salamanca.
            Growing up there taught me to value the quality of life of the countryside, but also to notice the grievances that rural areas endure.
            Like anyone's, my socialisation was shaped by the place I come from.
          </p>
        </div>

        <div class="scrolly-step" data-step="2">
          <img class="step-img" src="{{ '/assets/img/about/research-depopulation-maps.jpg' | relative_url }}" alt="Maps of Spanish municipalities at risk of depopulation, 2011–2019" loading="lazy">
          <span class="step-kicker">2020 · The spark</span>
          <h3>Learning to read the world through maps</h3>
          <p>
            The academic spark came in 2020, during the Master's in Political and Electoral Analysis at UC3M.
            There, <a href="https://www.tonirodon.cat">Toni Rodon</a> taught me to read social life through maps, exogeneity and, above all, geography.
            That is when I found my path, right at the intersection between my personal background and what I truly wanted to research.
          </p>
          <p>
            My first project asked a question that had followed me since childhood: <strong>how does depopulation shape the way people vote?</strong>
          </p>
        </div>

        <div class="scrolly-step" data-step="3">
          <img class="step-img" src="{{ '/assets/img/about/research-madrid-rents.jpg' | relative_url }}" alt="Map of the change in rent prices across Madrid census tracts, 2015–2019" loading="lazy">
          <span class="step-kicker">Today · Place matters</span>
          <h3>From empty villages to crowded cities</h3>
          <p>
            Geography never let go of me. I soon moved on to other place-based phenomena that, again for personal reasons, I found compelling:
            how rising rents shape voting in big cities, the rural–urban divide, or the political behaviour of farmers.
          </p>
          <p>
            Linking <strong>political geography and place-based phenomena with electoral behaviour</strong> is what drives my research today.
            <a href="{{ '/publications/' | relative_url }}">See my publications →</a>
          </p>
        </div>
      </div>
    </div>
  </section>

  <section class="story-chapter">
    <h2 class="story-chapter-title">🏃 About me, beyond academia</h2>

    <div class="personal">
      <img class="personal-photo" src="{{ '/assets/img/about/personal-running.jpg' | relative_url }}" alt="Álvaro running a race in Madrid" loading="lazy">

      <div class="personal-facts">
        <div class="fact">
          <span class="fact-emoji">🌾</span>
          <p>A rural guy forced to live in the city.</p>
        </div>
        <div class="fact">
          <span class="fact-emoji">👟</span>
          <p>I spend my free time thinking about causality while running.</p>
        </div>
        <div class="fact">
          <span class="fact-emoji">🦇</span>
          <p>I also devote part of my life to surviving from one Valencia CF disappointment to the next.</p>
        </div>
        <div class="fact">
          <span class="fact-emoji">🎧</span>
          <p>According to my Spotify, the soundtrack of my life would be a remix of
            <span class="band">Coldplay</span> <span class="band">The Killers</span> <span class="band">Viva Suecia</span>
            <span class="band">Supersubmarina</span> <span class="band">Arde Bogotá</span></p>
        </div>
      </div>
    </div>
  </section>

</div>

<script>
  (function () {
    var steps = document.querySelectorAll(".scrolly-step");
    var imgs = document.querySelectorAll(".scrolly-figure img");
    if (!("IntersectionObserver" in window) || !steps.length) return;
    var io = new IntersectionObserver(
      function (entries) {
        entries.forEach(function (e) {
          if (!e.isIntersecting) return;
          var n = e.target.getAttribute("data-step");
          steps.forEach(function (s) { s.classList.toggle("is-active", s === e.target); });
          imgs.forEach(function (im) { im.classList.toggle("active", im.getAttribute("data-step") === n); });
        });
      },
      { rootMargin: "-45% 0px -45% 0px" }
    );
    steps.forEach(function (s) { io.observe(s); });
  })();
</script>
