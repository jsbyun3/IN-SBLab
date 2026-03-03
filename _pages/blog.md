---
layout: default
permalink: /news/
title: news
nav: true
nav_order: 6
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 5 
  sort_field: date
  sort_reverse: true
  trail:
    before: 1 # The number of links before the current page
    after: 3 # The number of links after the current page
---


{% assign blog_name_size = site.blog_name | size %}
{% assign blog_description_size = site.blog_description | size %}

{% if blog_name_size > 0 or blog_description_size > 0 %}

  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>
  {% endif %}

{% if site.display_tags and site.display_tags.size > 0 or site.display_categories and site.display_categories.size > 0 %} 
<!-- site.display_tags and site.display_tags.size 변수에 값이 있거나, site.display_categories and site.display_categories.size 변수에 값이 있다면 -->
  <div class="tag-category-list"> <!-- 웹 페이지의 특정 구역의 디자인 템플릿이 tag-category-list. -->
    <ul class="p-0 m-0"> <!-- <ul>은 정렬되지 않은 목록. 순서가 중요하지 않을 때 사용함. 직계 자식 요소로는 오직 <li> 요소만 올 수 있고, 최소 하나 이상의 <li>요소를 자식으로 가져야 한다. tag간 순서가 중요하지 않기 때문에 ul을 사용해도 되는 것.  -->
      {% for tag in site.display_tags %}
        <li> <!-- <li>는 목록 안의 아이템을 나타낸다. 목록을 나타내는 <ul> 혹은 <ol> 요소 안에 항목으로서 <li>요소가 위치해야 함. -->
          <i class="fa-solid fa-hashtag fa-sm"></i> <a href="{{ tag | slugify | prepend: '/blog/tag/' | relative_url }}">{{ tag }}</a>
          <!-- {% for tag in site.display_tags %}은 설정된 태그 리스트를 하나씩 꺼내어 반복적으로 HTML을 생성하는 코드.  -->
          <!-- <i class="fa-solid fa-hashtag fa-sm"></i> 중 <i>는 폰트 어썸 아이콘을 삽입하기 위한 태그. fa-solid fa-hashtag fa-sm는 아이콘의 종류와 크기를 지정하는 CSS 클래스. -->
          <!-- <a> 클릭하면 해당 태그로 이동하는 하이퍼링크를 만듦. tag | slugify 태그 이름을 URL에 적합한 형태로 소문자화하고 공백을 하이픈으로 바꿈. (ex. "AI Lab" -> "ai-lab"), prepend: '/blog/tag/' -> 가공된 이름 앞에 특정 경로를 붙여줌, relative_url -> 완성된 경로를 홈페이지의 상대 주소로 변환하여 링크가 깨지지 않게 함. -->
          <!-- {{tag}}는 실제 태그명(ex. formatting 등)을 불러옴. -->
        </li>
        {% unless forloop.last %} 
        <!-- unless는 if와 반대되는 개념으로 "~하지 않는다면"이라는 의미를 가짐. 따라서 특정 조건이 거짓일 때만 내부 코드를 실행함. 즉, {% unless forloop.last %}는 "마지막 항목이 아니라면"을 의미함. -->
          <p>&bull;</p>
          <!-- <p>&bull;</p> -> '•' 을 나타내는 특수 문자. -->
        {% endunless %}
        <!-- unless로 시작된 조건문이 여기서 끝남을 명시함. -->
      {% endfor %}
      <!-- for로 시작된 조건문이 여기서 끝남을 명시함. -->
      {% if site.display_categories.size > 0 and site.display_tags.size > 0 %}
      <!-- site.display_categories.size 변수에 값이 있고 site.display_tags.size 변수에 값이 있다면 -->
        <p>&bull;</p>
        <!-- <p>&bull;</p> -> '•' 을 나타내는 특수 문자. -->
      {% endif %}
      <!-- if({% if site.display_categories.size > 0 and site.display_tags.size > 0 %})로 시작된 조건문이 여기서 끝남을 명시함. -->
      {% for category in site.display_categories %}
        <li>
          <i class="fa-solid fa-tag fa-sm"></i> <a href="{{ category | slugify | prepend: '/blog/category/' | relative_url }}">{{ category }}</a>
        </li>
        {% unless forloop.last %}
          <p>&bull;</p>
        {% endunless %}
      {% endfor %}
    </ul>
  </div>
  {% endif %}
  <!-- if로 시작된 조건문이 여기서 끝남을 명시함. -->

{% assign featured_posts = site.posts | where: "featured", "true" %}
<!-- site.posts 중 파일 상단 YMAL에 featured: true라고 명시된 글들만 골라내어 featured_posts라는 변수에 할당함. -->
{% if featured_posts.size > 0 %}
<!-- "만약 주요 게시물로 지정된 글이 하나라도 있다면" -->
<br>
<!-- 줄바꿈 태그 -->

<div class="container featured-posts">
{% assign is_even = featured_posts.size | modulo: 2 %}
<!-- featured_posts의 개수(featured_posts.size)가 짝수인지 홀수인지 판별함(modulo 연산으로). 레이아웃을 결정하는 기준. -->
<div class="row row-cols-{% if featured_posts.size <= 2 or is_even == 0 %}2{% else %}3{% endif %}">
<!-- 게시물이 2개 이하이거나 전체 개수가 짝수이면 2, 아니면 3이라는 숫자를 HTML클래스명에 삽입함. 화면에 카드를 한 줄에 2개씩 보여줄지, 3개씩 보여줄지 동적으로 결정함. --> 
{% for post in featured_posts %}
<!-- 추출된 주요 게시물 리스트에서 글을 하나씩 꺼내어 반복함. 글의 개수만큼 동일한 디자인의 '카드'를 자동으로 생성함. -->
<div class="col mb-4">
<!-- col : 그리드 시스템에서 하나의 '칸', mb-4 : margin-bottom : 1.5rem 정도의 하단 여백을 줌.(md : Medium 이상의 화면(ex. 태블릿, PC 등)에서의 설정을 의미.) -->
<a href="{{ post.url | relative_url }}">
<!-- 해당 게시물의 주소를 가져와서, 현재 사이트의 기본 경로를 고려한 링크로 변환.  -->
<div class="card hoverable">
<!-- card : 테두리가 있고, 깔끔하게 정렬된 '카드' 형태의 박스를 만듭니다. hoverable : 선택자를 사용해서 마우스를 요소 위에 올렸을 때 적용되는 스타일을 정의함. 이 홈페이지에서는 마우스를 올렸을 때 그림자가 생기고, 살짝 떠오르는 애니메이션 효과를 주는 식으로 적용됨. -->
<div class="row g-0">
<!-- 카드 내부에서 또 다시 행을 나눔, g-0 : 내부 여백을 제거하여 카드 내용이 꽉 차 보이게 함. -->
<div class="col-md-12">
<!-- 화면 가로를 총 12칸으로 나눔. 즉, 12는 전체 폭을 의미. 만약 이 숫자를 6으로 바꾸면 내용이 카드의 절반만 차지하게 됨. -->
<div class="card-body">
<!-- 사방에 적절한 안쪽 여백을 제공함으로써, 카드 안에 들어가는 제목(h3), 본문(p), 메타데이터 정보들이 깔끔하게 세로로 나열될 수 있는 바탕이 됨. -->
<div class="float-right">
<!-- 내용물을 오른쪽 끝으로 정렬함. 이 홈페이지에서는 '압정 아이콘'을 우측 상단에 두는 식으로 적용됨. -->
<i class="fa-solid fa-thumbtack fa-xs"></i>
<!-- Font Awesome 아이콘 문법. 이 홈페이지에서는 실물 압정 모양의 아이콘을 아주 작은 크기로 삽입하는 식으로 적용됨. -->
</div>
<h3 class="card-title text-lowercase">{{ post.title }}</h3>
<!-- 제목에 대문자가 섞여 있어도 모두 소문자로 바꿈. -->
<p class="card-text">{{ post.description }}</p>
<!-- {{ post.description }}글의 요약 문구를 출력함. 이 홈페이지에서는 카드 본문(card-text) 자리에 들어감. -->

                    {% if post.external_source == blank %}
                      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
                    {% else %}
                      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
                    {% endif %}
                    {% assign year = post.date | date: "%Y" %}

                    <p class="post-meta">
                      {{ read_time }} min read &nbsp; &middot; &nbsp;
                      <a href="{{ year | prepend: '/blog/' | relative_url }}">
                        <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </a>
        </div>
      {% endfor %}
      </div>
    </div>
    <hr>

{% endif %}

  <ul class="post-list">

    {% if page.pagination.enabled %}
      {% assign postlist = paginator.posts %}
    {% else %}
      {% assign postlist = site.posts %}
    {% endif %}

    {% for post in postlist %}

    {% if post.external_source == blank %}
      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    {% else %}
      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
    {% endif %}
    {% assign year = post.date | date: "%Y" %}
    {% assign tags = post.tags | join: "" %}
    {% assign categories = post.categories | join: "" %}

    <li>

{% if post.thumbnail %}

<div class="row">
          <div class="col-sm-9">
{% endif %}
        <h3>
        {% if post.redirect == blank %}
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {% elsif post.redirect contains '://' %}
          <a class="post-title" href="{{ post.redirect }}" target="_blank">{{ post.title }}</a>
          <svg width="2rem" height="2rem" viewBox="0 0 40 40" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 13.5v6H5v-12h6m3-3h6v6m0-6-9 9" class="icon_svg-stroke" stroke="#999" stroke-width="1.5" fill="none" fill-rule="evenodd" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        {% else %}
          <a class="post-title" href="{{ post.redirect | relative_url }}">{{ post.title }}</a>
        {% endif %}
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: '%B %d, %Y' }}
        {% if post.external_source %}
        &nbsp; &middot; &nbsp; {{ post.external_source }}
        {% endif %}
      </p>
      <p class="post-tags">
        <a href="{{ year | prepend: '/blog/' | relative_url }}">
          <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>

          {% if tags != "" %}
          &nbsp; &middot; &nbsp;
            {% for tag in post.tags %}
            <a href="{{ tag | slugify | prepend: '/blog/tag/' | relative_url }}">
              <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}</a>
              {% unless forloop.last %}
                &nbsp;
              {% endunless %}
              {% endfor %}
          {% endif %}

          {% if categories != "" %}
          &nbsp; &middot; &nbsp;
            {% for category in post.categories %}
            <a href="{{ category | slugify | prepend: '/blog/category/' | relative_url }}">
              <i class="fa-solid fa-tag fa-sm"></i> {{ category }}</a>
              {% unless forloop.last %}
                &nbsp;
              {% endunless %}
              {% endfor %}
          {% endif %}
    </p>

{% if post.thumbnail %}

</div>

  <div class="col-sm-3">
    <img class="card-img" src="{{ post.thumbnail | relative_url }}" style="object-fit: cover; height: 90%" alt="image">
  </div>
</div>
{% endif %}
    </li>

    {% endfor %}

  </ul>

{% if page.pagination.enabled %}
{% include pagination.liquid %}
{% endif %}

</div>
