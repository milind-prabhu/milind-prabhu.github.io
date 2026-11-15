---
layout: archive
title: "Contact"
permalink: /contact/
author_profile: false
classes: wide
---

<script>
  (function () {
    var savedTheme = localStorage.getItem("site-theme");
    var prefersLight = window.matchMedia && window.matchMedia("(prefers-color-scheme: light)").matches;
    document.documentElement.setAttribute("data-theme", savedTheme || (prefersLight ? "light" : "dark"));
  })();
</script>

<div class="contact-page">
  <header class="contact-page__topbar">
    <a href="{{ '/' | relative_url }}"><span aria-hidden="true">←</span> Home</a>
    <button class="theme-toggle contact-theme-toggle" type="button" aria-label="Switch to light mode" aria-pressed="false">
      <i class="fas fa-sun theme-toggle__icon" aria-hidden="true"></i>
    </button>
  </header>

  <main>
    <header class="contact-page__intro">
      <p class="contact-page__eyebrow">Contact</p>
      <h1>Get in touch</h1>
      <p>Open to research collaborations, industry conversations, or a quick chat.</p>
    </header>

    <div class="contact-page__grid">
      <section class="contact-card" aria-labelledby="contact-email-title">
        <span class="contact-card__icon" aria-hidden="true"><i class="fas fa-envelope"></i></span>
        <div>
          <h2 id="contact-email-title">Email</h2>
          <p>The best way to reach me is by email.</p>
          <a class="contact-card__email" href="mailto:milindpr@umich.edu">milindpr@umich.edu</a>
        </div>
      </section>

      <section class="availability-card" aria-labelledby="availability-title">
        <div class="availability-card__header">
          <div>
            <p class="availability-card__label">Weekly availability</p>
            <h2 id="availability-title">9:00 AM–12:00 PM EST</h2>
          </div>
          <span class="availability-card__status"><span aria-hidden="true"></span> Free</span>
        </div>

        <ul class="availability-list" aria-label="Available meeting times">
          <li><span>Monday</span><time>9:00 AM–12:00 PM</time></li>
          <li><span>Tuesday</span><time>9:00 AM–12:00 PM</time></li>
          <li><span>Wednesday</span><time>9:00 AM–12:00 PM</time></li>
          <li><span>Thursday</span><time>9:00 AM–12:00 PM</time></li>
          <li><span>Friday</span><time>9:00 AM–12:00 PM</time></li>
          <li><span>Saturday</span><time>9:00 AM–12:00 PM</time></li>
          <li><span>Sunday</span><time>9:00 AM–12:00 PM</time></li>
        </ul>

        <p class="availability-card__note">All times are in Eastern Standard Time.</p>
        <a class="availability-card__cta" href="mailto:milindpr@umich.edu?subject=Meeting%20request">Email me to schedule <span aria-hidden="true">→</span></a>
      </section>
    </div>
  </main>
</div>

<script>
  (function () {
    var button = document.querySelector(".contact-theme-toggle");
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
