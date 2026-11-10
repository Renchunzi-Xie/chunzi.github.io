---
permalink: /publications/
title: "Publications"
slug: publications
author_profile: true
---

{% assign pubs = site.data.publications %}
{% assign published = pubs | where_exp: "p", "p.type != 'preprint'" %}
{% assign lead = published | where: "lead", true %}
{% assign confs = published | where: "type", "conference" %}
{% assign journals = published | where: "type", "journal" %}

<header class="page-head reveal">
  <p class="hero__eyebrow">02 · Research output</p>
  <h1 class="page-head__title">Publications</h1>
  <p class="muted"><span class="me-mark">Renchunzi Xie</span> = me &nbsp;·&nbsp; <sup>*</sup> corresponding author.
    Full list on <a href="{{ site.author.googlescholar }}">Google Scholar</a>.</p>
</header>

<div class="stats reveal">
  <div class="stat"><span class="stat__num">{{ published | size }}</span><span class="stat__label">Peer-reviewed papers</span></div>
  <div class="stat"><span class="stat__num">{{ lead | size }}</span><span class="stat__label">First / corresponding author</span></div>
  <div class="stat"><span class="stat__num">{{ confs | size }}</span><span class="stat__label">Conference papers</span></div>
  <div class="stat"><span class="stat__num">{{ journals | size }}</span><span class="stat__label">Journal papers</span></div>
</div>

<div class="filters reveal" role="group" aria-label="Filter publications">
  <button class="filter is-active" data-filter="all">All</button>
  <button class="filter" data-filter="lead">First / Corresponding</button>
  <button class="filter" data-filter="conference">Conference</button>
  <button class="filter" data-filter="journal">Journal</button>
</div>

{% assign groups = pubs | group_by: "year" %}
{% for g in groups %}
<section class="pub-year reveal">
  <h2 class="pub-year__label">{{ g.name }}</h2>
  <div class="pub-list">
  {% for p in g.items %}
    {% assign authors = p.authors | replace: "Renchunzi Xie*", "@@MEC@@" | replace: "Renchunzi Xie", "@@ME@@" %}
    {% assign authors = authors | replace: "@@MEC@@", "<span class='me-mark'>Renchunzi Xie</span><sup>*</sup>" | replace: "@@ME@@", "<span class='me-mark'>Renchunzi Xie</span>" %}
    {% assign venue_key = p.short | downcase %}
    <article class="pub" data-type="{{ p.type }}" data-lead="{% if p.lead %}1{% else %}0{% endif %}">
      <div class="pub__badge venue--{{ venue_key }}">
        <span class="pub__venue">{{ p.short }}</span>
        {% if p.type != "preprint" %}<span class="pub__year">{{ p.year }}</span>{% endif %}
      </div>
      <div class="pub__body">
        <h3 class="pub__title">{{ p.title }}</h3>
        <p class="pub__authors">{{ authors }}</p>
        <p class="pub__venue-full"><em>{{ p.venue }}</em>{% if p.type != "preprint" %}, {{ p.year }}{% endif %}</p>
        <div class="pub__links">
          {% if p.paper %}<a class="pill" href="{{ p.paper }}"><i class="fas fa-file-pdf"></i> Paper</a>{% endif %}
          {% if p.code %}<a class="pill" href="{{ p.code }}"><i class="fab fa-github"></i> Code</a>{% endif %}
          {% if p.lead %}<span class="pill pill--soft"><i class="fas fa-star"></i> {% if p.authors contains "Renchunzi Xie*" %}Corresponding{% else %}First author{% endif %}</span>{% endif %}
        </div>
      </div>
    </article>
  {% endfor %}
  </div>
</section>
{% endfor %}

<p class="pub-empty muted" hidden>No publications match this filter.</p>

<script>
  (function () {
    var buttons = document.querySelectorAll('.filter');
    var pubs = document.querySelectorAll('.pub');
    var years = document.querySelectorAll('.pub-year');
    var empty = document.querySelector('.pub-empty');
    buttons.forEach(function (b) {
      b.addEventListener('click', function () {
        var f = b.getAttribute('data-filter');
        buttons.forEach(function (x) { x.classList.toggle('is-active', x === b); });
        var shown = 0;
        pubs.forEach(function (p) {
          var ok = f === 'all' || (f === 'lead' ? p.dataset.lead === '1' : p.dataset.type === f);
          p.hidden = !ok;
          if (ok) shown++;
        });
        years.forEach(function (y) {
          y.hidden = !y.querySelector('.pub:not([hidden])');
        });
        empty.hidden = shown > 0;
      });
    });
  })();
</script>
