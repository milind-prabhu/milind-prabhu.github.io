---
permalink: /
excerpt:
author_profile: false
classes: wide
redirect_from:
  - /about/
  - /about.html
---

<script>
  (function () {
    var savedTheme = localStorage.getItem("site-theme");
    var prefersLight = window.matchMedia && window.matchMedia("(prefers-color-scheme: light)").matches;
    document.documentElement.setAttribute("data-theme", savedTheme || (prefersLight ? "light" : "dark"));
  })();
</script>

<div class="single-page-home">
  <header class="home-topbar">
    <nav class="home-nav" aria-label="Primary navigation">
      <button class="theme-toggle" type="button" aria-label="Switch to light mode" aria-pressed="false">
        <i class="fas fa-sun theme-toggle__icon" aria-hidden="true"></i>
      </button>
    </nav>
  </header>

  <main>
    <section class="hero" id="top">
      <div class="hero__content">
        <h1>Milind Prabhu</h1>
        <p class="hero__meta">PhD Candidate <a href="https://theory.engin.umich.edu/">@UMich</a>, advised by <a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a>.</p>
        <p class="hero__copy">I design algorithms for big data.</p>
      </div>
      <div class="hero__portrait">
        <img class="hero__photo" src="{{ '/images/milind-green.webp' | relative_url }}" alt="Portrait of Milind Prabhu">
        <nav class="hero__quick-links" aria-label="Profile links">
          <a href="{{ '/files/resume.pdf' | relative_url }}" aria-label="Résumé" title="Résumé"><i class="fas fa-file-alt" aria-hidden="true"></i></a>
          <a href="https://scholar.google.com/citations?user=vu73GNIAAAAJ&amp;hl=en&amp;oi=ao" aria-label="Google Scholar" title="Google Scholar"><i class="ai ai-google-scholar" aria-hidden="true"></i></a>
          <a href="mailto:milindpr@umich.edu" aria-label="Email" title="Email"><i class="fas fa-envelope" aria-hidden="true"></i></a>
        </nav>
      </div>
    </section>

    <section class="focus-overview" id="focus" aria-labelledby="focus-title">
      <h2 id="focus-title">What I work on</h2>
      <div class="focus-list">
        <article class="focus-item">
          <h3>Data Compression</h3>
          <p>Compress large datasets to speed up computation</p>
          <div class="concept-graphic" aria-hidden="true">
            <svg viewBox="0 0 320 100" focusable="false">
              <g class="dataset-cluster">
                <circle class="dataset-point" cx="40" cy="22" r="3"/><circle class="dataset-point" cx="50" cy="30" r="3"/><circle class="dataset-point" cx="60" cy="18" r="3"/><circle class="dataset-point" cx="68" cy="27" r="3"/><circle class="dataset-point" cx="78" cy="20" r="3"/>
                <circle class="dataset-point dataset-selected" cx="85" cy="32" r="3"/><circle class="dataset-point" cx="45" cy="42" r="3"/><circle class="dataset-point dataset-selected" cx="58" cy="45" r="3"/><circle class="dataset-point" cx="72" cy="39" r="3"/><circle class="dataset-point" cx="88" cy="48" r="3"/>
                <circle class="dataset-point" cx="35" cy="36" r="3"/><circle class="dataset-point" cx="65" cy="55" r="3"/><circle class="dataset-point" cx="78" cy="52" r="3"/><circle class="dataset-point" cx="95" cy="38" r="3"/><circle class="dataset-point" cx="54" cy="58" r="3"/>
              </g>
              <g class="dataset-cluster">
                <circle class="dataset-point" cx="132" cy="58" r="3"/><circle class="dataset-point" cx="145" cy="52" r="3"/><circle class="dataset-point" cx="158" cy="57" r="3"/><circle class="dataset-point" cx="171" cy="53" r="3"/><circle class="dataset-point dataset-selected" cx="184" cy="60" r="3"/>
                <circle class="dataset-point" cx="138" cy="70" r="3"/><circle class="dataset-point dataset-selected" cx="151" cy="68" r="3"/><circle class="dataset-point" cx="164" cy="72" r="3"/><circle class="dataset-point" cx="177" cy="69" r="3"/><circle class="dataset-point" cx="190" cy="74" r="3"/>
                <circle class="dataset-point" cx="145" cy="82" r="3"/><circle class="dataset-point" cx="159" cy="84" r="3"/><circle class="dataset-point dataset-selected" cx="173" cy="82" r="3"/><circle class="dataset-point" cx="184" cy="88" r="3"/><circle class="dataset-point" cx="128" cy="76" r="3"/>
              </g>
              <g class="dataset-cluster">
                <circle class="dataset-point" cx="232" cy="18" r="3"/><circle class="dataset-point" cx="244" cy="14" r="3"/><circle class="dataset-point" cx="257" cy="20" r="3"/><circle class="dataset-point" cx="270" cy="15" r="3"/><circle class="dataset-point" cx="282" cy="24" r="3"/>
                <circle class="dataset-point" cx="235" cy="32" r="3"/><circle class="dataset-point" cx="248" cy="29" r="3"/><circle class="dataset-point dataset-selected" cx="262" cy="34" r="3"/><circle class="dataset-point" cx="276" cy="32" r="3"/><circle class="dataset-point" cx="291" cy="38" r="3"/>
                <circle class="dataset-point" cx="240" cy="46" r="3"/><circle class="dataset-point" cx="254" cy="44" r="3"/><circle class="dataset-point" cx="268" cy="48" r="3"/><circle class="dataset-point dataset-selected" cx="282" cy="50" r="3"/><circle class="dataset-point" cx="298" cy="25" r="3"/>
              </g>
            </svg>
          </div>
        </article>

        <article class="focus-item focus-item--balancing">
          <h3>Load Balancing</h3>
          <p>Use parallel processors to speed up computation</p>
          <div class="concept-graphic" aria-hidden="true">
            <svg viewBox="0 0 320 100" focusable="false">
              <g class="crowd-back">
                <circle cx="16" cy="14" r="3"/><rect x="11" y="18" width="10" height="7" rx="4"/>
                <circle cx="36" cy="12" r="3"/><rect x="31" y="16" width="10" height="7" rx="4"/>
                <circle cx="56" cy="15" r="3"/><rect x="51" y="19" width="10" height="7" rx="4"/>
                <circle cx="76" cy="12" r="3"/><rect x="71" y="16" width="10" height="7" rx="4"/>
                <circle cx="96" cy="15" r="3"/><rect x="91" y="19" width="10" height="7" rx="4"/>
              </g>
              <g class="crowd-middle">
                <circle cx="10" cy="42" r="3.5"/><rect x="4" y="47" width="12" height="8" rx="4"/>
                <circle cx="32" cy="39" r="3.5"/><rect x="26" y="44" width="12" height="8" rx="4"/>
                <circle cx="54" cy="43" r="3.5"/><rect x="48" y="48" width="12" height="8" rx="4"/>
                <circle cx="76" cy="39" r="3.5"/><rect x="70" y="44" width="12" height="8" rx="4"/>
                <circle cx="98" cy="43" r="3.5"/><rect x="92" y="48" width="12" height="8" rx="4"/>
              </g>
              <g class="crowd-front">
                <circle cx="21" cy="72" r="4"/><rect x="14" y="78" width="14" height="9" rx="5"/>
                <circle cx="46" cy="68" r="4"/><rect x="39" y="74" width="14" height="9" rx="5"/>
                <circle cx="71" cy="72" r="4"/><rect x="64" y="78" width="14" height="9" rx="5"/>
                <circle cx="96" cy="68" r="4"/><rect x="89" y="74" width="14" height="9" rx="5"/>
              </g>

              <circle class="graphic-soft dispatcher-halo" cx="157" cy="50" r="19"/>
              <circle class="graphic-node" cx="157" cy="50" r="10"/>
              <circle class="graphic-solid" cx="157" cy="50" r="4"/>

              <g>
                <rect class="work-packet packet-source-1" x="-5" y="-5" width="10" height="10" rx="3"/>
                <rect class="work-packet packet-source-2 packet-delay-1" x="-5" y="-5" width="10" height="10" rx="3"/>
                <rect class="work-packet packet-source-3 packet-delay-2" x="-5" y="-5" width="10" height="10" rx="3"/>
                <rect class="work-packet packet-source-4 packet-delay-3" x="-5" y="-5" width="10" height="10" rx="3"/>
                <rect class="work-packet packet-source-5 packet-delay-4" x="-5" y="-5" width="10" height="10" rx="3"/>
                <rect class="work-packet packet-source-6 packet-delay-5" x="-5" y="-5" width="10" height="10" rx="3"/>
              </g>

              <g transform="translate(0 -3)">
                <rect class="graphic-node" x="231" y="3" width="52" height="23" rx="5"/>
                <rect class="graphic-soft" x="236" y="8" width="42" height="13" rx="2"/>
                <rect class="graphic-solid" x="255" y="26" width="4" height="5" rx="2"/>
                <rect class="graphic-solid" x="247" y="31" width="20" height="3" rx="1.5"/>
              </g>
              <g>
                <rect class="graphic-node" x="259" y="34" width="52" height="23" rx="5"/>
                <rect class="graphic-soft" x="264" y="39" width="42" height="13" rx="2"/>
                <rect class="graphic-solid" x="283" y="57" width="4" height="5" rx="2"/>
                <rect class="graphic-solid" x="275" y="62" width="20" height="3" rx="1.5"/>
              </g>
              <g transform="translate(0 3)">
                <rect class="graphic-node" x="231" y="65" width="52" height="23" rx="5"/>
                <rect class="graphic-soft" x="236" y="70" width="42" height="13" rx="2"/>
                <rect class="graphic-solid" x="255" y="88" width="4" height="5" rx="2"/>
                <rect class="graphic-solid" x="247" y="93" width="20" height="3" rx="1.5"/>
              </g>
            </svg>
          </div>
        </article>
      </div>
    </section>

    <section class="selected-research" id="selected" aria-labelledby="selected-title">
      <div class="selected-research__header">
        <h2 id="selected-title">Selected research</h2>
        <a href="{{ '/publications/' | relative_url }}">View all publications <span aria-hidden="true">→</span></a>
      </div>
      <div class="research-columns">
        <section aria-labelledby="compression-papers-title">
          <h3 class="column-label" id="compression-papers-title">Data compression</h3>
          <ol class="paper-list">
            <li>
              <span class="paper-title">Coresets for Capacitated Clustering via Dual Concentration</span>
              <span class="paper-meta">SODA 2027</span>
              <span class="paper-authors">with <a href="https://cs.au.dk/~schwiegelshohn/">Chris Schwiegelshohn</a>, <a href="https://sudarshanshy.github.io/">Sudarshan Shyam</a>, and <a href="https://sites.google.com/site/erikwaing/home">Erik Waingarten</a></span>
            </li>
            <li>
              <span class="paper-title">Fault Tolerant Coresets</span>
              <span class="paper-meta">NeurIPS 2026</span>
              <span class="paper-authors">with <a href="https://cs.au.dk/~schwiegelshohn/">Chris Schwiegelshohn</a> and <a href="https://sudarshanshy.github.io/">Sudarshan Shyam</a></span>
            </li>
            <li>
              <a class="paper-title" href="https://arxiv.org/pdf/2405.01339">Sensitivity Sampling for k-Means: Worst Case and Stability Optimal Coreset Bounds</a>
              <span class="paper-meta">FOCS 2024</span>
              <span class="paper-authors">with <a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a>, <a href="https://www.di.ens.fr/~vcohen/">Vincent Cohen-Addad</a>, <a href="https://www.normalesup.org/~saulpic/">David Saulpic</a>, and <a href="https://cs.au.dk/~schwiegelshohn/">Chris Schwiegelshohn</a></span>
            </li>
          </ol>
        </section>

        <section aria-labelledby="balancing-papers-title">
          <h3 class="column-label" id="balancing-papers-title">Load balancing</h3>
          <ol class="paper-list">
            <li>
              <a class="paper-title" href="https://arxiv.org/pdf/2604.04159">Online Graph Balancing and the Power of Two Choices</a>
              <span class="paper-meta">FOCS 2026</span>
              <span class="paper-authors">with <a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a>, <a href="https://faculty.cc.gatech.edu/~ssingla7/">Sahil Singla</a>, and <a href="https://aco.gatech.edu/users/siddharth-sundaram">Siddharth M. Sundaram</a></span>
            </li>
            <li>
              <a class="paper-title" href="https://arxiv.org/pdf/2609.21348">The Cube-Root Phenomenon in Online Carpooling</a>
              <span class="paper-meta">Preprint 2026</span>
              <span class="paper-authors">with <a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a>, <a href="https://faculty.cc.gatech.edu/~ssingla7/">Sahil Singla</a>, and <a href="https://aco.gatech.edu/users/siddharth-sundaram">Siddharth M. Sundaram</a></span>
            </li>
            <li>
              <a class="paper-title" href="https://arxiv.org/abs/2610.11006">Non-Clairvoyant Scheduling is Hard Even for Trees</a>
              <span class="paper-meta">Preprint 2026</span>
              <span class="paper-authors">with <a href="https://www.cse.wustl.edu/~kunal/">Kunal Agrawal</a>, <a href="https://www.linkedin.com/in/owen-druzgal-b00b872a8">Owen Druzgal</a>, and <a href="https://www.moeheart.cn/">Jinhao Zhao</a></span>
            </li>
          </ol>
        </section>
      </div>
    </section>
  </main>

</div>

<script>
  (function () {
    var button = document.querySelector(".theme-toggle");
    var icon = button ? button.querySelector(".theme-toggle__icon") : null;

    if (!button) {
      return;
    }

    function setTheme(theme) {
      var isLight = theme === "light";
      document.documentElement.setAttribute("data-theme", theme);
      localStorage.setItem("site-theme", theme);
      button.setAttribute("aria-label", isLight ? "Switch to dark mode" : "Switch to light mode");
      button.setAttribute("aria-pressed", isLight ? "true" : "false");

      if (icon) {
        icon.classList.toggle("fa-moon", isLight);
        icon.classList.toggle("fa-sun", !isLight);
      }
    }

    setTheme(document.documentElement.getAttribute("data-theme") || "dark");

    button.addEventListener("click", function () {
      var currentTheme = document.documentElement.getAttribute("data-theme") || "dark";
      setTheme(currentTheme === "light" ? "dark" : "light");
    });
  })();
</script>
