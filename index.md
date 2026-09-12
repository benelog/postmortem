---
layout: default
---
<figure class="illustration cover">{% include illustrations/cover.svg %}</figure>
<section class="intro">
  <h1 class="series-title">포스트모템</h1>
  <p class="series-tagline">IT 회사의 장애를 둘러싼 연작 추리 단편</p>
  <p>새벽 두 시에 결제가 죽고, 감사 로그에는 그 자리에 없던 사람의 이름이 찍혀 있다. 로그를 끝까지 읽는 사람들과, 그들이 목요일 열한 시 반에 모이는 술집의 이야기.</p>
</section>
<ol class="episode-list">
{% assign eps = site.episodes | sort: "number" %}
{% for e in eps %}
  <li>
    <a href="{{ e.url | relative_url }}">
      <span class="num">{{ e.number }}화</span>
      <span class="title">{{ e.title }}</span>
      <span class="pov">{{ e.pov }} 시점</span>
      <span class="summary">{{ e.summary }}</span>
    </a>
  </li>
{% endfor %}
</ol>
