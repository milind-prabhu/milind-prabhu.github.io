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
  <nav class="home-nav" aria-label="Primary navigation">
    <a class="home-nav__brand" href="#top" aria-label="Milind Prabhu, back to top">MP</a>
    <div class="home-nav__links">
      <a href="#research">Research</a>
      <a href="#publications">Publications</a>
      <a href="{{ '/files/resume.pdf' | relative_url }}">CV</a>
      <button class="theme-toggle" type="button" aria-label="Switch to light mode" aria-pressed="false">
        <i class="fas fa-sun theme-toggle__icon" aria-hidden="true"></i>
      </button>
    </div>
  </nav>

  <header class="hero" id="top">
    <div class="hero__layout">
      <div class="hero__content">
        <p class="hero__eyebrow">Theoretical computer science · Algorithms</p>
        <h1>Milind Prabhu</h1>
        <p class="hero__subtitle">PhD student at <a class="plain-link" href="https://theory.engin.umich.edu/">UMich Theory Lab</a></p>
        <p class="hero__lede">I design algorithms for making good decisions with limited information—especially in online, approximation, and clustering problems.</p>
        <div class="focus-tags" aria-label="Research areas">
          <span>Online algorithms</span>
          <span>Approximation</span>
          <span>Coresets</span>
          <span>Discrepancy</span>
        </div>
        <div class="hero__actions">
          <a class="button-link button-link--primary" href="{{ '/files/resume.pdf' | relative_url }}">
            <i class="fas fa-file-alt" aria-hidden="true"></i>
            View CV
          </a>
          <a class="button-link" href="{{ site.author.googlescholar }}">
            <i class="ai ai-google-scholar" aria-hidden="true"></i>
            Google Scholar
          </a>
        </div>
        <p class="hero__meta">Advised by <a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a>. Always happy to talk about algorithms and their applications.</p>
        <p class="hero__email">"first name" + "pr@umich.edu"</p>
      </div>
      <div class="hero__media">
        <img class="hero__photo" src="{{ '/images/milind.png' | relative_url }}" alt="Portrait of Milind Prabhu" loading="lazy">
        <span class="hero__media-label">Algorithms · Theory · Impact</span>
      </div>
    </div>
  </header>

  <section class="research-overview" id="research" aria-labelledby="research-heading">
    <div class="section-heading section-heading--overview">
      <p class="section-kicker">Research focus</p>
      <h2 id="research-heading">Theory for decisions under constraints</h2>
    </div>
    <div class="research-grid">
      <article class="research-card">
        <span class="research-card__number">01</span>
        <h3>Online decisions</h3>
        <p>Algorithms that act before the future is known, with guarantees that hold even in difficult inputs.</p>
      </article>
      <article class="research-card">
        <span class="research-card__number">02</span>
        <h3>Approximation</h3>
        <p>Provable solutions for optimization problems where exact computation is too costly or impossible.</p>
      </article>
      <article class="research-card">
        <span class="research-card__number">03</span>
        <h3>Data reduction</h3>
        <p>Small representations that preserve the structure needed for reliable downstream decisions.</p>
      </article>
    </div>
  </section>

  <main class="home-main">
    <div class="research-sections">
      <section id="preprints" class="home-section preprints-section">
        <div class="section-heading">
          <div>
            <p class="section-kicker">Latest work</p>
            <h2>Preprints</h2>
          </div>
          <p class="section-intro">Recent results and work in progress.</p>
        </div>
        <div class="pub-list">
          {% assign preprints = site.preprints | sort: 'date' | reverse %}
          {% for post in preprints %}
            <article class="pub-card pub-card--featured">
              <p class="pub-card__meta"><span>{% if post.venue_display %}{{ post.venue_display }}{% else %}Preprint{% endif %}</span><span>{{ post.date | date: "%Y" }}</span></p>
              <h3 class="pub-card__title">{{ post.title }}</h3>
              {% if post.citation %}
                <p class="pub-card__authors">with {{ post.citation }}</p>
              {% endif %}
              <div class="pub-card__actions">
                {% if post.paperurl %}
                  <a class="pub-link" href="{{ post.paperurl }}">Read paper <span aria-hidden="true">↗</span></a>
                {% endif %}
                {% if post.summary %}
                  <button class="pub-summary-toggle" type="button" aria-expanded="false" aria-controls="preprint-summary-{{ forloop.index }}">Summary</button>
                {% endif %}
              </div>
              {% if post.summary %}
                <div class="pub-summary" id="preprint-summary-{{ forloop.index }}" hidden>
                  {{ post.summary | markdownify }}
                </div>
              {% endif %}
            </article>
          {% endfor %}
        </div>
      </section>

      <section id="publications" class="home-section publications-section">
        <div class="section-heading">
          <div>
            <p class="section-kicker">Selected research</p>
            <h2>Publications</h2>
          </div>
          <p class="section-intro">Peer-reviewed work in algorithms, optimization, and learning.</p>
        </div>
        <div class="pub-list">
          {% assign pubs = site.publications | sort: 'date' | reverse %}
          {% for post in pubs %}
            <article class="pub-card">
              <p class="pub-card__meta"><span>{% if post.venue_display %}{{ post.venue_display }}{% else %}{{ post.venue }}{% endif %}</span><span>{{ post.date | date: "%Y" }}</span></p>
              <h3 class="pub-card__title">{{ post.title }}</h3>
              {% if post.citation %}
                <p class="pub-card__authors">with {{ post.citation }}</p>
              {% endif %}
              <div class="pub-card__actions">
                {% if post.paperurl %}
                  <a class="pub-link" href="{{ post.paperurl }}">Read paper <span aria-hidden="true">↗</span></a>
                {% endif %}
                {% if post.summary %}
                  <button class="pub-summary-toggle" type="button" aria-expanded="false" aria-controls="publication-summary-{{ forloop.index }}">Summary</button>
                {% endif %}
              </div>
              {% if post.summary %}
                <div class="pub-summary" id="publication-summary-{{ forloop.index }}" hidden>
                  {{ post.summary | markdownify }}
                </div>
              {% endif %}
            </article>
          {% endfor %}
        </div>
      </section>
    </div>

    <section id="collaborators" class="home-section collaborators-panel">
      <div class="section-heading">
        <div>
          <p class="section-kicker">Research network</p>
          <h2>Collaborators</h2>
        </div>
      </div>
      <div class="collaborators-box">
        <ul class="collaborators-list">
          <li><a href="https://sepehr.assadi.info/">Sepehr Assadi</a></li>
          <li><a href="https://dblp.org/pid/286/1893.html">Nikhil Ayyadevara</a></li>
          <li><a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a></li>
          <li><a href="https://www.di.ens.fr/~vcohen/">Vincent Cohen-Addad</a></li>
          <li><a href="https://nirmitj6.github.io/static-webpage/">Nirmit Joshi</a></li>
          <li><a href="https://www.normalesup.org/~saulpic/">David Saulpic</a></li>
          <li><a href="https://cs.au.dk/~schwiegelshohn/">Chris Schwiegelshohn</a></li>
          <li><a href="https://vihanshah72.github.io/">Vihan Shah</a></li>
          <li><a href="https://faculty.cc.gatech.edu/~ssingla7/">Sahil Singla</a></li>
          <li><a href="https://aco.gatech.edu/users/siddharth-sundaram">Siddharth M. Sundaram</a></li>
          <li><a href="https://sudarshansiitkgp.github.io/">Sudarshan Shyam</a></li>
          <li><a href="https://www.cs.cmu.edu/~dwoodruf/">David Woodruff</a></li>
        </ul>
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

<script>
  (function () {
    document.querySelectorAll(".pub-summary-toggle").forEach(function (button) {
      var summary = document.getElementById(button.getAttribute("aria-controls"));

      if (!summary) {
        return;
      }

      button.addEventListener("click", function () {
        var isOpen = button.getAttribute("aria-expanded") === "true";
        button.setAttribute("aria-expanded", isOpen ? "false" : "true");
        summary.hidden = isOpen;

        if (!isOpen && window.MathJax && window.MathJax.typesetPromise) {
          window.MathJax.typesetPromise([summary]);
        }
      });
    });
  })();
</script>
