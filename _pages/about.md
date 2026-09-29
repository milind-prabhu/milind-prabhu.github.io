---
permalink: /
excerpt:
author_profile: false
classes: wide
redirect_from:
  - /about/
  - /about.html
author_links:
  "Sepehr Assadi": "https://sepehr.assadi.info/"
  "Nikhil Ayyadevara": "https://scholar.google.com/citations?user=7ZqLL2YAAAAJ&hl=en"
  "Nikhil Bansal": "https://bansal.engin.umich.edu/"
  "Vincent Cohen-Addad": "https://www.di.ens.fr/~vcohen/"
  "Nirmit Joshi": "https://nirmitj6.github.io/static-webpage/"
  "David Saulpic": "https://www.normalesup.org/~saulpic/"
  "Chris Schwiegelshohn": "https://cs.au.dk/~schwiegelshohn/"
  "Vihan Shah": "https://vihanshah72.github.io/"
  "Sahil Singla": "https://faculty.cc.gatech.edu/~ssingla7/"
  "Siddharth M. Sundaram": "https://aco.gatech.edu/users/siddharth-sundaram"
  "Sudarshan Shyam": "https://sudarshansiitkgp.github.io/"
  "Erik Waingarten": "https://sites.google.com/site/erikwaing/home"
  "David Woodruff": "https://www.cs.cmu.edu/~dwoodruf/"
---

<script>
  (function () {
    var savedTheme = localStorage.getItem("site-theme");
    var prefersLight = window.matchMedia && window.matchMedia("(prefers-color-scheme: light)").matches;
    document.documentElement.setAttribute("data-theme", savedTheme || (prefersLight ? "light" : "dark"));
  })();
</script>

<div class="single-page-home">
  <button class="theme-toggle" type="button" aria-label="Switch to light mode" aria-pressed="false">
    <i class="fas fa-sun theme-toggle__icon" aria-hidden="true"></i>
  </button>

  <header class="hero" id="top">
    <div class="hero__layout">
      <div class="hero__content">
        <h1>Milind Prabhu</h1>
        <p class="hero__subtitle">PhD student @ <a class="plain-link" href="https://theory.engin.umich.edu/">UMich Theory Lab</a></p>
        <p class="hero__interests">I like thinking about online and approximation algorithms.</p>
        <p class="hero__meta">I am fortunate to be advised by <a href="https://bansal.engin.umich.edu/">Nikhil Bansal</a>.</p>
        <p class="hero__meta hero__contact">Feel free to reach out to me if you would like to chat!</p>
        <p class="hero__email">"first name" + "pr@umich.edu"</p>
      </div>
      <div class="hero__media">
        <img class="hero__photo" src="{{ '/images/milind.png' | relative_url }}" alt="Portrait of Milind Prabhu" loading="lazy">
        <nav class="hero__icon-links" aria-label="Profile links">
          <a href="{{ '/files/resume.pdf' | relative_url }}" aria-label="CV">
            <i class="fas fa-file-alt" aria-hidden="true"></i>
            <span class="visually-hidden">CV</span>
          </a>
          <a href="{{ site.author.googlescholar }}" aria-label="Google Scholar">
            <i class="ai ai-google-scholar" aria-hidden="true"></i>
            <span class="visually-hidden">Google Scholar</span>
          </a>
        </nav>
      </div>
    </div>
  </header>

  <main class="home-main" style="grid-template-columns:minmax(0,1fr);gap:0">
    <div class="research-sections" style="display:flex;flex-direction:column;gap:2rem;min-width:0">
      <section id="preprints" class="home-section preprints-section">
        <h2>Preprints</h2>
        <div class="pub-list">
          {% assign preprints = site.preprints | sort: 'date' | reverse %}
          {% for post in preprints %}
            <article class="pub-card">
              <p class="pub-card__meta">{% if post.venue_display %}{{ post.venue_display }}{% else %}Preprint · {{ post.date | date: "%Y" }}{% endif %}</p>
              <h3 class="pub-card__title">{{ post.title }}</h3>
              {% if post.citation %}
                {% assign authors = post.citation | split: ', ' %}
                <p class="pub-card__authors">with {% for author in authors %}{% assign author_url = page.author_links[author] %}{% if author_url %}<a href="{{ author_url }}">{{ author }}</a>{% else %}{{ author }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}</p>
              {% endif %}
              <div class="pub-card__actions">
                {% if post.paperurl %}
                  <a class="pub-link" href="{{ post.paperurl }}">Link</a>
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
        <h2>Publications</h2>
        <div class="pub-list">
          {% assign pubs = site.publications | sort: 'date' | reverse %}
          {% for post in pubs %}
            <article class="pub-card">
              <p class="pub-card__meta">{% if post.venue_display %}{{ post.venue_display }}{% else %}{{ post.venue }} · {{ post.date | date: "%Y" }}{% endif %}</p>
              <h3 class="pub-card__title">{{ post.title }}</h3>
              {% if post.citation %}
                {% assign authors = post.citation | split: ', ' %}
                <p class="pub-card__authors">with {% for author in authors %}{% assign author_url = page.author_links[author] %}{% if author_url %}<a href="{{ author_url }}">{{ author }}</a>{% else %}{{ author }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}</p>
              {% endif %}
              <div class="pub-card__actions">
                {% if post.paperurl %}
                  <a class="pub-link" href="{{ post.paperurl }}">Link</a>
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
