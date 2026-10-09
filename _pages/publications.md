---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
classes: wide
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
  "Sudarshan Shyam": "https://sudarshanshy.github.io/"
  "Erik Waingarten": "https://sites.google.com/site/erikwaing/home"
  "David Woodruff": "https://www.cs.cmu.edu/~dwoodruf/"
  "Kunal Agrawal": "https://www.cse.wustl.edu/~kunal/"
  "Owen Druzgal": "https://www.linkedin.com/in/owen-druzgal-b00b872a8"
  "Jinhao Zhao": "https://www.moeheart.cn/"
---

<script>
  (function () {
    var savedTheme = localStorage.getItem("site-theme");
    var prefersLight = window.matchMedia && window.matchMedia("(prefers-color-scheme: light)").matches;
    document.documentElement.setAttribute("data-theme", savedTheme || (prefersLight ? "light" : "dark"));
  })();
</script>

<div class="publications-archive-page">
  <header class="publications-archive__topbar">
    <a href="{{ '/' | relative_url }}"><span aria-hidden="true">←</span> Home</a>
    <button class="theme-toggle publications-theme-toggle" type="button" aria-label="Switch to light mode" aria-pressed="false">
      <i class="fas fa-sun theme-toggle__icon" aria-hidden="true"></i>
    </button>
  </header>

  <header class="publications-archive__intro">
    <h1>All publications</h1>
    <p>Research papers and preprints, newest first.</p>
  </header>

  {% assign all_papers = site.publications | concat: site.preprints | sort: 'date' | reverse %}
  <ol class="publications-archive__list">
    {% for paper in all_papers %}
      <li class="publication-archive-card">
        <div class="publication-archive-card__header">
          {% if paper.paperurl %}
            <a class="publication-archive-card__title" href="{{ paper.paperurl }}">{{ paper.title }}</a>
          {% else %}
            <span class="publication-archive-card__title">{{ paper.title }}</span>
          {% endif %}
          <span class="publication-archive-card__venue">
            {% if paper.venue_display %}
              {{ paper.venue_display }}
            {% elsif paper.collection == 'preprints' %}
              Preprint {{ paper.date | date: "%Y" }}
            {% else %}
              {{ paper.venue }} {{ paper.date | date: "%Y" }}
            {% endif %}
          </span>
        </div>

        {% if paper.citation %}
          {% assign authors = paper.citation | split: ', ' %}
          <p class="publication-archive-card__authors">with
            {% for author in authors %}
              {% assign author_url = page.author_links[author] %}
              {% if author_url %}<a href="{{ author_url }}">{{ author }}</a>{% else %}{{ author }}{% endif %}{% unless forloop.last %}{% if forloop.length == 2 %} and {% elsif forloop.rindex == 2 %}, and {% else %}, {% endif %}{% endunless %}
            {% endfor %}
          </p>
        {% endif %}
      </li>
    {% endfor %}
  </ol>
</div>

<script>
  (function () {
    var button = document.querySelector(".publications-theme-toggle");
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
        icon.className = isLight ? "fas fa-moon theme-toggle__icon" : "fas fa-sun theme-toggle__icon";
      }
    }

    setTheme(document.documentElement.getAttribute("data-theme") || "dark");

    button.addEventListener("click", function () {
      setTheme(document.documentElement.getAttribute("data-theme") === "light" ? "dark" : "light");
    });
  })();
</script>
