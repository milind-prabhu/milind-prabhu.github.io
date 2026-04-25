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
  <button class="theme-toggle" type="button" aria-label="Switch to light mode" aria-pressed="false">
    <span class="theme-toggle__icon" aria-hidden="true">💡</span>
  </button>

  <header class="hero" id="top">
    <div class="hero__layout">
      <div class="hero__content">
        <h1>Milind Prabhu</h1>
        <p class="hero__subtitle">Ph.D. student in Computer Science</p>
        <p class="hero__email">"first name" + "pr@umich.edu"</p>
        <p class="hero__meta">Advised by Nikhil Bansal</p>
        <p class="hero__interests">Research interests: online algorithms, approximation algorithms</p>
        <nav class="hero__links" aria-label="Profile links">
          <a href="{{ '/files/resume.pdf' | relative_url }}">CV</a>
          <a href="{{ site.author.googlescholar }}">Google Scholar</a>
        </nav>
      </div>
      <img class="hero__photo" src="{{ '/images/milind.png' | relative_url }}" alt="Portrait of Milind Prabhu" loading="lazy">
    </div>
  </header>

  <main class="home-main">
    <section id="publications" class="home-section publications-section">
      <h2>Publications</h2>
      <div class="pub-list">
        {% assign pubs = site.publications | sort: 'date' | reverse %}
        {% for post in pubs %}
          <article class="pub-card">
            <p class="pub-card__meta">{{ post.venue }} · {{ post.date | date: "%Y" }}</p>
            <h3 class="pub-card__title">{{ post.title }}</h3>
            {% if post.citation %}
              <p class="pub-card__authors">{{ post.citation }}</p>
            {% endif %}
            <div class="pub-card__actions">
              {% if post.paperurl %}
                <a class="pub-link" href="{{ post.paperurl }}">Paper</a>
              {% endif %}
            </div>
          </article>
        {% endfor %}
      </div>
    </section>

    <aside id="collaborators" class="home-section collaborators-panel">
      <h2>Collaborators</h2>
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
        <li><a href="https://www.cs.cmu.edu/~dwoodruf/">David Woodruff</a></li>
      </ul>
    </aside>
  </main>
</div>

<script>
  (function () {
    var button = document.querySelector(".theme-toggle");

    if (!button) {
      return;
    }

    function setTheme(theme) {
      var isLight = theme === "light";
      document.documentElement.setAttribute("data-theme", theme);
      localStorage.setItem("site-theme", theme);
      button.setAttribute("aria-label", isLight ? "Switch to dark mode" : "Switch to light mode");
      button.setAttribute("aria-pressed", isLight ? "true" : "false");
    }

    setTheme(document.documentElement.getAttribute("data-theme") || "dark");

    button.addEventListener("click", function () {
      var currentTheme = document.documentElement.getAttribute("data-theme") || "dark";
      setTheme(currentTheme === "light" ? "dark" : "light");
    });
  })();
</script>
