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
    Light
  </button>

  <header class="hero" id="top">
    <div class="hero__layout">
      <div class="hero__content">
        <h1>Milind B. Prabhu</h1>
        <p class="hero__subtitle">Ph.D. student in Computer Science</p>
        <p class="hero__email">"first name" + "pr@umich.edu"</p>
        <p class="hero__meta">Advised by Nikhil Bansal</p>
        <p class="hero__interests">Research interests: online algorithms, approximation algorithms</p>
        <nav class="hero__links" aria-label="Profile links">
          <a href="{{ '/files/resume.pdf' | relative_url }}">CV</a>
          <a href="{{ site.author.googlescholar }}">Google Scholar</a>
        </nav>
      </div>
      <img class="hero__photo" src="{{ '/images/milind.png' | relative_url }}" alt="Portrait of Milind B. Prabhu" loading="lazy">
    </div>
  </header>

  <section id="publications" class="home-section">
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
      button.textContent = isLight ? "Dark" : "Light";
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
