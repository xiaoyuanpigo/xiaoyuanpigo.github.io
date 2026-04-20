---
permalink: /
title: "Yuan Xiao"
layout: homepage
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

{% include base_path %}

{% assign pubs_sorted = site.publications | sort: "date" | reverse | sort: "weight" %}
{% assign pub_topics = pubs_sorted | map: "topic" | uniq %}

<div class="home-shell">
  <section class="home-section hero" id="about">
    <div class="hero-grid">
      <div class="hero-copy">
        <span class="hero-kicker">Trustworthy AI · Verification · Security</span>
        <h1 class="hero-title">Yuan <span>Xiao</span></h1>
        <p class="hero-subtitle">
          I am currently a Ph.D. student at the Software Institute, Nanjing University, under the supervision of Professor <a href="https://software.nju.edu.cn/zychen/">Zhenyu Chen</a> and Associate Professor <a href="https://chunrong.github.io">Chunrong Fang</a>, with academic collaboration and guidance from Assistant Professor <a href="https://people.cs.umass.edu/~shiqingma/">Shiqing Ma</a> at the University of Massachusetts Amherst. I was also a joint Ph.D. student at the School of Computing, National University of Singapore, from November 2024 to November 2025, under the supervision of Professor <a href="https://www.comp.nus.edu.sg/~dongjs/">Jinsong Dong</a>, with collaboration and guidance from Professor <a href="https://sunjun.site/">Jun Sun</a>. I received my bachelor's degree in Mathematics from Sun Yat-sen University in 2021, advised by Professor <a href="https://math.sysu.edu.cn/teacher/428">Xianping Guo</a>.
        </p>
        <div class="hero-tags">
          <span class="hero-tag">Nanjing University</span>
          <span class="hero-tag">Software Security</span>
          <span class="hero-tag">Neural Verification</span>
          <span class="hero-tag">Postdoc 2026</span>
        </div>
        <div class="hero-actions">
          <a class="hero-button primary" href="#publications">View Publications</a>
          <a class="hero-button secondary" href="{{ base_path }}/files/resume.pdf">Open CV</a>
          <a class="hero-button secondary" href="mailto:{{ site.author.email }}">Email Me</a>
        </div>
      </div>
      <aside class="hero-panel">
        <div class="portrait-wrap">
          <img src="{{ base_path }}/images/custom/portrait-yuan.jpg" alt="Portrait of Yuan Xiao">
        </div>
        <p class="panel-note">
          My research focuses on building robust and trustworthy AI systems, especially neural network verification, code dataset watermarking, backdoor defense, and security analysis for modern learning systems. I am actively looking for postdoctoral opportunities in trustworthy AI and security.
        </p>
        <div class="stat-grid">
          <div class="info-chip">
            <strong>{{ site.publications | size }}</strong>
            <span>publications listed on this site</span>
          </div>
          <div class="info-chip">
            <strong>{{ site.talks | size }}</strong>
            <span>talks and posters</span>
          </div>
          <div class="info-chip">
            <strong>2026</strong>
            <span>expected Ph.D. completion</span>
          </div>
        </div>
      </aside>
    </div>
  </section>

  <section class="home-section" id="research">
    <div class="home-section-title">
      <span class="eyebrow">Research</span>
      <h2>Current focus</h2>
    </div>
    <div class="feature-grid">
      <article class="feature-card">
        <h3>Neural Network Verification</h3>
        <p>I study certified robustness for deep neural networks, with a particular emphasis on MaxPool-based architectures and tighter linear approximation methods.</p>
      </article>
      <article class="feature-card">
        <h3>Code Dataset Watermarking</h3>
        <p>I analyze how watermarks are embedded, detected, removed, and strengthened in code datasets and neural code models.</p>
      </article>
      <article class="feature-card">
        <h3>AI Security</h3>
        <p>I work on practical attack and defense problems around backdoors, unauthorized model usage, and trustworthy deployment of learning systems.</p>
      </article>
    </div>
  </section>

  <section class="home-section" id="education">
    <div class="home-section-title">
      <span class="eyebrow">Education</span>
      <h2>Academic background</h2>
    </div>
    <div class="timeline-grid" style="margin-top: 1rem;">
      <article class="timeline-card">
        <span class="timeline-date">2021 - 2026</span>
        <h3>Ph.D., Nanjing University</h3>
        <p>Software Institute. Research on trustworthy AI, verification, and security.</p>
      </article>
      <article class="timeline-card">
        <span class="timeline-date">Nov 2024 - Nov 2025</span>
        <h3>Joint Ph.D., NUS</h3>
        <p>School of Computing. Collaboration with Professor Jinsong Dong and Professor Jun Sun.</p>
      </article>
      <article class="timeline-card">
        <span class="timeline-date">2017 - 2021</span>
        <h3>B.S., Sun Yat-sen University</h3>
        <p>Mathematics. Advised by Professor Xianping Guo.</p>
      </article>
    </div>
  </section>

  <section class="home-section" id="publications">
    <div class="home-section-title">
      <span class="eyebrow">Publications</span>
      <h2>Selected papers across verification, watermarking, and security</h2>
    </div>
    <p class="fineprint">
      <sup>†</sup> co-first authors. <sup>*</sup> corresponding authors. For <em>Findings of ACL</em>, the CCF list does not count it as a regular ranked conference, so it is marked as <code>N/A</code>.
    </p>
    {% for topic in pub_topics %}
      {% assign pubs_in_topic = pubs_sorted | where: "topic", topic %}
      <div class="publication-group">
        <h3>{{ topic }}</h3>
        <div class="publication-list">
          {% for post in pubs_in_topic %}
            <article class="publication-card">
              <h3>{{ post.title }}</h3>
              <p class="publication-authors">{{ post.authors | join: ", " }}</p>
              <p class="publication-venue">{{ post.venue }}, {{ post.date | date: "%Y" }}{% if post.location %} · {{ post.location }}{% endif %}</p>
              <div class="publication-meta">
                <span class="rank-badge">CCF {{ post.ccf_rank | default: "N/A" }}</span>
                <span class="rank-badge">CORE {{ post.core_rank | default: "N/A" }}</span>
              </div>
              <div class="publication-links">
                {% if post.paperurl %}
                  <a class="link-pill" href="{{ post.paperurl }}">Paper</a>
                {% endif %}
                {% if post.githuburl %}
                  <a class="link-pill" href="{{ post.githuburl }}">Code</a>
                {% endif %}
                {% if post.slidesurl %}
                  <a class="link-pill" href="{{ post.slidesurl }}">Slides</a>
                {% endif %}
              </div>
            </article>
          {% endfor %}
        </div>
      </div>
    {% endfor %}
  </section>

  <section class="home-section" id="talks">
    <div class="home-section-title">
      <span class="eyebrow">Talks</span>
      <h2>Recent presentations</h2>
    </div>
    <div class="stack-grid">
      <div class="mini-card">
        <h3>Talks and posters</h3>
        <div class="mini-list">
          {% for post in site.talks reversed %}
            <div class="mini-item">
              <a class="mini-item-title" href="{{ base_path }}{{ post.url }}">{{ post.title }}</a>
              <div class="mini-meta">{{ post.type }} · {{ post.venue }} · {{ post.date | date: "%B %Y" }}{% if post.location %} · {{ post.location }}{% endif %}</div>
            </div>
          {% endfor %}
        </div>
      </div>
      <div class="mini-card">
        <h3>Highlights</h3>
        <p>Poster presentation at CVPR, plus an active publication pipeline across top AI and software engineering venues.</p>
        <div class="mini-list">
          <div class="mini-item">
            <div class="mini-item-title">Service</div>
            <div class="mini-meta">Reviewer: AAAI 2023, NeurIPS 2024/2025/2026, ICLR 2025/2026, ICML 2025, TSE 2026.</div>
          </div>
          <div class="mini-item">
            <div class="mini-item-title">External Review</div>
            <div class="mini-meta">TASE 2025, AAAI 2025, USENIX 2026, CVPR 2026.</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="home-section" id="gallery">
    <div class="home-section-title">
      <span class="eyebrow">Gallery</span>
      <h2>Snapshots from research and presentation</h2>
    </div>
    <div class="feature-grid">
      <article class="feature-card">
        <div class="home-media">
          <img src="{{ base_path }}/images/custom/issta2025-2.jpg" alt="ISSTA 2025 photo">
        </div>
        <h3>ISSTA 2025 Oral Presentation</h3>
        <p>A snapshot from my oral presentation at ISSTA 2025, highlighting active engagement with the software engineering research community.</p>
      </article>
      <article class="feature-card">
        <div class="home-media">
          <img src="{{ base_path }}/images/custom/issta2025.jpg" alt="ISSTA 2025 group scene">
        </div>
        <h3>ISSTA 2025 Attendance</h3>
        <p>A photo from my trip to ISSTA 2025.</p>
      </article>
      <article class="feature-card">
        <div class="home-media">
          <img src="{{ base_path }}/images/cvpr24-1.jpg" alt="CVPR poster snapshot">
        </div>
        <h3>CVPR 2024 Poster</h3>
        <p>A poster presentation snapshot from CVPR 2024, representing my work on robustness verification for neural networks.</p>
      </article>
    </div>
  </section>

  <section class="home-section" id="teaching">
    <div class="home-section-title">
      <span class="eyebrow">Teaching</span>
      <h2>Teaching and academic activity</h2>
    </div>
    <div class="stack-grid">
      <div class="mini-card">
        <h3>Teaching</h3>
        <div class="mini-list">
          {% for post in site.teaching reversed %}
            <div class="mini-item">
              <div class="mini-item-title">{{ post.title }}</div>
              <div class="mini-meta">{{ post.type }} · {{ post.venue }} · {{ post.location }}</div>
            </div>
          {% endfor %}
        </div>
      </div>
      <div class="mini-card">
        <h3>Awards and projects</h3>
        <div class="mini-list">
          <div class="mini-item">
            <div class="mini-item-title">Awards</div>
            <div class="mini-meta">Huawei Scholarship (2025), Model Graduate Student (2025), Nanjing University Graduate Scholarship (2021-2025), Outstanding Graduate Student (2022).</div>
          </div>
          <div class="mini-item">
            <div class="mini-item-title">Projects</div>
            <div class="mini-meta">Safety-critical software quality assurance, Internet of Vehicles load analysis, and population measurement projects.</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="home-section" id="contact">
    <div class="mini-card contact-panel">
      <div>
        <div class="home-section-title" style="margin-bottom: 0.5rem;">
          <span class="eyebrow">Contact</span>
          <h2>Open to postdoc and collaboration opportunities</h2>
        </div>
        <p>
          If you are working on trustworthy AI, neural verification, or security for learning systems, feel free to reach out by email or check my full academic record in the CV page.
        </p>
      </div>
      <div class="hero-actions">
        <a class="hero-button primary" href="mailto:{{ site.author.email }}">yuan.xiao@smail.nju.edu.cn</a>
        <a class="hero-button secondary" href="{{ site.author.googlescholar }}">Google Scholar</a>
      </div>
    </div>
  </section>
</div>
