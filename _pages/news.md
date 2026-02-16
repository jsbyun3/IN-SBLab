---
layout: page
title: news
permalink: /news/
---

<div class="news-container">
  {% include news.liquid %}
</div>

<style>
  /* 1. 테이블 구조를 카드 나열 구조로 변경 */
  .news table, 
  .news table tbody, 
  .news-container table {
    border: none !important;
    display: flex !important;
    flex-wrap: wrap !important;
    gap: 20px !important;
    justify-content: flex-start !important;
    background: none !important;
  }

  /* 2. 각 뉴스 행(tr)을 개별 카드로 만들기 */
  .news table tr, 
  .news-container table tr {
    display: flex !important;
    flex-direction: column !important;
    width: 300px !important;
    height: 400px !important;
    margin: 0 !important;
    padding: 0 !important;
    border: 1px solid #e0e0e0 !important;
    border-radius: 12px !important;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08) !important;
    overflow: hidden !important;
    background: #ffffff !important;
    transition: transform 0.3s ease !important;
  }

  .news table tr:hover {
    transform: translateY(-5px) !important;
  }

  /* 3. 카드 상단에 노션 느낌의 이미지 영역 추가 */
  .news table tr::before {
    content: "" !important;
    display: block !important;
    width: 100% !important;
    min-height: 160px !important;
    background-color: #f8f9fa !important;
    /* 실제 이미지가 있다면 아래 경로를 수정하세요 */
    background-image: url('/assets/img/news_default.png') !important;
    background-size: cover !important;
    background-position: center !important;
    border-bottom: 1px solid #eee !important;
  }

  /* 4. 날짜와 제목이 들어가는 칸(td) 정리 */
  .news table td, 
  .news-container table td {
    display: block !important;
    border: none !important;
    padding: 10px 15px !important;
    text-align: left !important;
  }

  /* 첫 번째 td(보통 날짜) 스타일 */
  .news table td:first-child {
    color: #888 !important;
    font-size: 0.85rem !important;
    order: 2 !important; /* 제목 아래로 보냄 */
  }

  /* 두 번째 td(제목 및 내용) 스타일 */
  .news table td:nth-child(2) {
    font-weight: bold !important;
    font-size: 1.1rem !important;
    color: #333 !important;
    order: 1 !important;
  }

  /* 5. 불필요한 요소(표 헤더 등) 숨기기 */
  .news thead, 
  .news th, 
  .news-container thead {
    display: none !important;
  }
</style>