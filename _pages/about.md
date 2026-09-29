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
