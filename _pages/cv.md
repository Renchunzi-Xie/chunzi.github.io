---
permalink: /cv/
title: "CV"
slug: cv
author_profile: true
---

{% assign cv_url = '/files/resume.pdf' | relative_url %}

<header class="page-head reveal">
  <p class="hero__eyebrow">03 · Curriculum Vitae</p>
  <h1 class="page-head__title">Curriculum Vitae</h1>
  <div class="hero__actions">
    <a class="btn-fancy" href="{{ cv_url }}" download><i class="fas fa-download"></i> Download PDF</a>
    <a class="btn-fancy btn-fancy--ghost" href="{{ cv_url }}" target="_blank" rel="noopener"><i class="fas fa-external-link-alt"></i> Open in new tab</a>
  </div>
</header>

<div class="grid-2 grid-2--cv">
  <section class="section reveal">
    <h2 class="section__title"><span class="section__icon">💼</span> Appointments</h2>
    <ul class="timeline">
      <li class="timeline__item">
        <span class="timeline__date">2025.12 – Present</span>
        <div class="timeline__body"><strong>Assistant Professor</strong><br>Great Bay University <span class="muted">· Dongguan, China</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2025.04 – 2025.11</span>
        <div class="timeline__body"><strong>Postdoctoral Researcher</strong> <span class="muted">(Supervisor: Prof. Bo An)</span><br>Nanyang Technological University <span class="muted">· Singapore</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2024.02 – 2025.02</span>
        <div class="timeline__body"><strong>Visiting Scholar</strong> <span class="muted">(Supervisor: Prof. Bingyi Jing)</span><br>Southern University of Science and Technology <span class="muted">· Shenzhen, China</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2023.06 – 2024.01</span>
        <div class="timeline__body"><strong>Research Intern</strong> <span class="muted">(Mentor: Jianfeng Zhang)</span><br>Huawei Noah's Ark Lab <span class="muted">· Shenzhen, China</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2020.02 – 2025.02</span>
        <div class="timeline__body"><strong>Research Associate</strong> <span class="muted">(Supervisor: Prof. Bo An)</span><br>Nanyang Technological University <span class="muted">· Singapore</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2019.02 – 2020.02</span>
        <div class="timeline__body"><strong>Research Associate</strong> <span class="muted">(Supervisor: Asst. Prof. Mahardhika Pratama)</span><br>Nanyang Technological University <span class="muted">· Singapore</span></div>
      </li>
    </ul>
  </section>

  <section class="section reveal">
    <h2 class="section__title"><span class="section__icon">🎓</span> Education</h2>
    <ul class="timeline">
      <li class="timeline__item">
        <span class="timeline__date">2021.08 – 2025.03</span>
        <div class="timeline__body"><strong>Ph.D.</strong> <span class="muted">(Supervisor: Prof. Bo An)</span><br>Nanyang Technological University, College of Computing and Data Science <span class="muted">· Singapore</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2017.09 – 2018.06</span>
        <div class="timeline__body"><strong>M.Sc. in Data Science</strong> <span class="muted">(Statistics)</span><br>University College London, Department of Statistical Science <span class="muted">· London, UK</span></div>
      </li>
      <li class="timeline__item">
        <span class="timeline__date">2013.09 – 2017.06</span>
        <div class="timeline__body"><strong>B.Econ. in Statistics</strong><br>Southwestern University of Finance and Economics, School of Statistics <span class="muted">· Chengdu, China</span></div>
      </li>
    </ul>
  </section>
</div>

<section class="section reveal">
  <h2 class="section__title"><span class="section__icon">📄</span> Full CV</h2>
  <div class="pdf-frame">
    <object data="{{ cv_url }}#view=FitH" type="application/pdf" width="100%" height="100%">
      <p class="pdf-frame__fallback">Your browser can't display the PDF inline.
        <a href="{{ cv_url }}">Download the CV</a> instead.</p>
    </object>
  </div>
</section>
