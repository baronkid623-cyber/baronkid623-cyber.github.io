---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* B.S. in Financial Technology (FinTech), Shenzhen University, 2025–present

Skills
======
* Programming Languages: C, C++, Python, JavaScript
* AI & Data: Machine Learning, Deep Learning, NLP, Pandas, NumPy
* Embedded Systems: STM32, Arduino, RTOS, Linux
* Financial Technology: Quantitative Finance, Risk Management, Blockchain
* Tools: Git, Docker, GitHub Actions, VS Code, Jupyter

Work experience
======
* 有运营自媒体软件的经验，最高播放量视频播放量为120w播放量
* (需根据实习和项目经验进行更新)

Projects
======
* 参与AI大模型驱动的金融科技项目
* 更多项目详见 Portfolio：{% for post in site.portfolio reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}
