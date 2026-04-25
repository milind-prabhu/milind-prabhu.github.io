---
permalink: /
excerpt:
author_profile: false
classes: wide
redirect_from:
  - /about/
  - /about.html
---

<div class="single-page-home">
  <header class="hero" id="top">
    <div class="hero__layout">
      <div class="hero__content">
        <h1>Milind B. Prabhu</h1>
        <p class="hero__subtitle">Ph.D. student in Computer Science</p>
        <p class="hero__meta">Advised by Nikhil Bansal</p>
        <p class="hero__interests">Research interests: online algorithms, approximation algorithms</p>
      </div>
      <img class="hero__photo" src="{{ '/images/profile.jpg' | relative_url }}" alt="Portrait of Milind B. Prabhu" loading="lazy">
    </div>

    <nav class="hero__nav" aria-label="Section navigation">
      <a href="#publications">Publications</a>
      <a href="#teaching">Teaching</a>
      <a href="#cv">CV</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section id="publications" class="home-section">
    <h2>Publications</h2>
    <div class="pub-grid">
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
              <a class="card-btn" href="{{ post.paperurl }}">Read Paper</a>
            {% endif %}
            {% if post.url %}
              <a class="card-btn card-btn--secondary" href="{{ post.url | relative_url }}">More Details</a>
            {% endif %}
          </div>
        </article>
      {% endfor %}
    </div>
  </section>

  <section id="teaching" class="home-section">
    <h2>Teaching</h2>
    {% if site.teaching and site.teaching.size > 0 %}
      <p class="section-note">Teaching content exists and will be consolidated into this section soon.</p>
    {% endif %}
  </section>

  <section id="cv" class="home-section">
    <h2>CV</h2>
    <p><a class="inline-link" href="{{ '/files/resume.pdf' | relative_url }}">View CV (PDF)</a></p>
  </section>

  <section id="contact" class="home-section">
    <h2>Contact</h2>
    <p>Email: {{ site.author.email }}</p>
    <ul class="contact-links">
      {% if site.author.googlescholar %}
        <li><a href="{{ site.author.googlescholar }}">Google Scholar</a></li>
      {% endif %}
      {% if site.author.linkedin %}
        <li><a href="{{ site.author.linkedin }}">LinkedIn</a></li>
      {% endif %}
      {% if site.author.github %}
        <li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>
      {% endif %}
      {% if site.author.orcid %}
        <li><a href="{{ site.author.orcid }}">ORCID</a></li>
      {% endif %}
    </ul>
  </section>
</div>
