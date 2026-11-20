---
layout: default
---
<figure class="illustration cover"><img src="{{ '/assets/illustrations/cover.webp' | relative_url }}" alt="비 내리는 밤 골목, 불 켜진 술집 유리문 너머 마주 앉은 민아와 도경" width="1672" height="941" decoding="async" fetchpriority="high"></figure>
<section class="intro">
  <h1 class="series-title">포스트모템</h1>
  <p class="series-tagline">IT 회사의 장애를 둘러싼 연작 추리 단편</p>
  <p>새벽 두 시에 결제 서버가 죽고, 감사 로그에는 그 자리에 없던 사람의 이름이 찍혀 있다. 로그를 끝까지 읽는 사람들과, 그들이 목요일 열한 시 반에 모이는 술집의 이야기.</p>
</section>
<h2 class="part-title">1부 · 소설</h2>
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
<h2 class="part-title">2부 · 해설</h2>
<p class="part-desc">소설을 읽은 뒤에 보는 글입니다. 화마다 그 화에 나온 개념과 교훈, 비슷한 일을 겪은 실제 회사들의 사례를 정리했습니다. 각 글은 해당 화의 결말을 다룹니다.</p>
<ol class="episode-list note-list">
{% assign nts = site.notes | sort: "number" %}
{% for n in nts %}
  <li>
    <a href="{{ n.url | relative_url }}">
      <span class="num">{{ n.number }}화</span>
      <span class="title">{{ n.title }}</span>
      <span class="summary">{{ n.summary }}</span>
    </a>
  </li>
{% endfor %}
</ol>
<a class="appendix-card" href="{{ '/appendix/' | relative_url }}">
  <span class="appendix-kicker">부록</span>
  <span class="appendix-title">참고 자료</span>
  <span class="appendix-desc">각 화의 장애가 참고한 문서. 인시던트 지휘, 블레임리스 포스트모템, 온콜, 감사 로그, 그리고 국내 회사들의 장애 대응 사례. 각 화로 바로 가는 링크도 함께.</span>
  <span class="appendix-go">보러 가기 →</span>
</a>
