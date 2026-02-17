---
layout: about
title: Home
permalink: /
#subtitle: <a href='#'>Affiliations</a>. Address. Contacts. Motto. Etc.

profile:
  align: right
  # image: prof_pic.jpg
  # image_circular: false # crops the image to make it circular
  # more_info: >
  #   <p>555 your office number</p>
  #   <p>123 your address street</p>
  #   <p>Your City, State 12345</p>

selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

### **Integrative Neuro-Systems Biology Group at Keimyung University**

We study the principles of olfaction, from sensory dynamics to olfactory perception and decision-making.

Using the ***Drosophila* olfactory system** as a model, we explore how the brain transforms complex sensory inputs into optimal behavioral choices. Our research traces the olfactory information processing pipeline across scales: from the physical dynamics of **ligand-receptor binding** to the high-level **neural algorithms** that drive navigation.

We integrate **computational modeling**, **artificial intelligence**, and **quantitative experiments** to understand how biological systems—from signaling pathways to the *Drosophila* brain—process information and respond to their environment.

---

👋 We are recruiting! If you are interested in joining, press [here](https://jsbyun3.github.io/IN-SBLab/people/).

---

### **🔬 What we study**

**1. Chemosensory Receptor Dynamics**
We investigate how cells robustly encode external stimuli by studying the dynamics of chemosensory receptors. We aim to understand the fundamental limits of sensory encoding at the molecular interface.

**2. Olfactory Perception & Decision-Making**
We investigate how animals make decisions in complex environments. We integrate behavioral experiments and Artificial Intelligence to decode the algorithms of olfactory processing in *Drosophila*.

**3. Information Processing in Biological Systems**
We use olfaction as a model to uncover universal principles of biological computation. We investigate how biological networks—from biochemical signaling pathways to neural circuits—process information to ensure robust function.

**4. Biological Algorithm Development**
We develop novel computational methods for network inference, optimization, and clustering to interpret high-dimensional biological data.

[👉 Click here to read more about our research](https://www.notion.so/Research-2e6aef7eb716803cb918f4dbbe59da30?pvs=21)

---

### **📢 News**

[제목 없음](https://www.notion.so/2e6aef7eb71680b7bf12ddb74ae41fb7?pvs=21)

👉 [Click here to view previous lab news](https://www.notion.so/News-2e6aef7eb71680739767d93511490529?pvs=21)

---

화살표가 두 개 뜨는 이유는 HTML의 기본 화살표와 우리가 직접 추가한 ▶ 텍스트가 겹쳐서 보이기 때문입니다.

이 현상을 해결하고, 클릭했을 때 모양이 깔끔하게 변하도록 코드를 최종 수정했습니다. 70번 줄부터 103번 줄까지 아래 코드로 다시 교체해 보세요.

🛠️ 화살표 중복 해결 + 하단 스크롤 확보 코드 (70~103번 교체)
HTML
<div style="display: flex; align-items: center; justify-content: flex-start; gap: 40px; padding: 20px 0;">
  
  <img src="{{ '/assets/img/kmu_type30.png' | relative_url }}" style="width: 140px; height: auto; flex-shrink: 0;" alt="kmu logo">
  
  <div style="font-size: 0.9rem; line-height: 1.5; border-right: 1px solid #eee; padding-right: 20px; flex-shrink: 0;">
    <a href="https://bioscience.kmu.ac.kr/" style="text-decoration: none; color: inherit;">Department of Biological Sciences</a> |<br>
    <a href="https://www.kmu.ac.kr/" style="text-decoration: none; color: inherit;">Keimyung University</a>
  </div>

  <div style="flex-shrink: 0;">
    <details class="final-sitemap" style="cursor: pointer;">
      <summary style="list-style: none; font-weight: bold; display: flex; align-items: center; gap: 8px;">
        <span class="arrow-box"></span>
        <span>⚙️ Site Map</span>
      </summary>
      <ul style="list-style: none; padding-left: 15px; margin: 10px 0 0 0; line-height: 2; border-left: 2px solid #f0f0f0; font-size: 0.85rem;">
        <li><a href="https://www.notion.so/People-2e6aef7eb71680b9815bfaeb20ed8351?pvs=21">People</a></li>
        <li><a href="https://www.notion.so/Research-2e6aef7eb716803cb918f4dbbe59da30?pvs=21">Research</a></li>
        <li><a href="https://www.notion.so/Publications-2e6aef7eb71680e28871fdc36e8ab5f0?pvs=21">Publications</a></li>
        <li><a href="https://www.notion.so/Teaching-2e6aef7eb7168015885cfc1aa190aa11?pvs=21">Teaching</a></li>
        <li><a href="https://www.notion.so/Software-2e6aef7eb71680e3a10dc2aeee03ac0b?pvs=21">Software</a></li>
        <li><a href="https://www.notion.so/News-2e6aef7eb71680739767d93511490529?pvs=21">News</a></li>
        <li><a href="https://www.notion.so/Contact-2e6aef7eb71680d48b06d68c4559d76d?pvs=21">Contact</a></li>
      </ul>
    </details>
  </div>

  <div style="flex-shrink: 0;">
    <a href="https://www.notion.so/People-2e6aef7eb71680b9815bfaeb20ed8351?pvs=21" style="color: #666; text-decoration: none; font-size: 0.9rem;">Join us</a>
  </div>

  <div style="color: #888; font-size: 0.8rem; margin-left: auto; flex-shrink: 0; text-align: right;">
    © 2026 Kiri Choi. All rights reserved.
  </div>
</div>

<div style="height: 200px;"></div>

<style>
  /* 1. 브라우저 기본 화살표 완전히 제거 */
  .final-sitemap summary::-webkit-details-marker { display: none !important; }
  .final-sitemap summary { list-style: none !important; }

  /* 2. 가짜 화살표 박스에 모양 넣기 */
  .final-sitemap:not([open]) .arrow-box::before { content: "▶"; }
  .final-sitemap[open] .arrow-box::before { content: "▼"; }
  
  .arrow-box { 
    font-size: 0.75rem; 
    width: 15px; 
    display: inline-block; 
    color: #999;
    user-select: none;
  }
</style>