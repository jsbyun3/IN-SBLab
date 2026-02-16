---
layout: page
title: news
permalink: /news/
---

<div class="news-container">
  {% include news.liquid %}
</div>

<style>
  /* 리스트를 노션 같은 카드형으로 바꾸는 마법의 CSS */
  .news table { border: none !important; }
  .news tr { 
    display: inline-block;
    width: 300px;
    margin: 10px;
    padding: 20px;
    border: 1px solid #e0e0e0;
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    transition: 0.3s;
    vertical-align: top;
  }
  .news tr:hover { transform: translateY(-5px); box-shadow: 0 8px 15px rgba(0,0,0,0.1); }
  .news td { border: none !important; display: block !important; }
  th { display: none; } /* 표 헤더 숨기기 */
</style>
.news tr::before {
  content: "";
  display: block;
  width: 100%;
  height: 150px;
  background-color: #f5f5f5; /* 이미지가 없을 때 기본 배경색 */
  background-image: url('/assets/img/news_default.png'); /* 기본 썸네일 경로 */
  background-size: cover;
  background-position: center;
  margin-bottom: 15px;
  border-radius: 8px 8px 0 0;
}
