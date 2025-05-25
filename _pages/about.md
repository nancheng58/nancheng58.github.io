---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>
Hi there! I'm a PhD student of [Information Retrieval Lab](https://ir.sdu.edu.cn/index_en.htm) at Shandong University, supervised by Prof. [Jun Ma](https://ir.sdu.edu.cn/~junma/~junma_en.htm), Prof. [Pengjie Ren](https://pengjieren.github.io/) and Prof. [Xin Xin](https://xinxin-me.github.io/). I also work closely with Prof. [Zhaochun Ren](https://renzhaochun.github.io/) and Prof. [Mengqi Zhang](https://zm7.github.io/).
My research interest is mainly recommender system and large language model. 

Email address: jiyuan.yang at mail.sdu.edu.cn

Please feel free to contact me if you have any questions.

# 📝 Papers

<!-- <div class='paper-box'> -->

<div class='paper-box-text' markdown="1">

[1] **[On the User Behavior Leakage from Recommender System Exposure](https://dl.acm.org/doi/full/10.1145/3568954) - TOIS 2023 (CCF A)** \| [![](https://img.shields.io/github/stars/nancheng58/On-the-User-Behavior-Leakage-from-Recommender-System-Exposure?style=social&label=Code+Stars)](https://github.com/nancheng58/On-the-User-Behavior-Leakage-from-Recommender-System-Exposure)
*Xin Xin\*, **Jiyuan Yang\* (co-first author)**, Hanbing Wang, Jun Ma, Pengjie Ren, Hengliang Luo, Xinlei Shi, Zhumin Chen, Zhaochun Ren*

[2] **基于自监督的预训练在推荐系统中的研究综述 - CCIR 2023** \| [![](https://img.shields.io/github/stars/nancheng58/Self-supervised-learning-for-Sequential-Recommender-Systems?style=social&label=Code+Stars)](https://github.com/nancheng58/Self-supervised-learning-for-Sequential-Recommender-Systems)

***Jiyuan Yang**, Muyang Ma, Pengjie Ren, Zhumin Chen, Zhaochun Ren, Xin Xin, Fei Cai, Jun Ma*

[3] **[Debiasing Sequential Recommenders through Distributionally Robust Optimization over System Exposure](https://arxiv.org/pdf/2312.07036) - WSDM 2024 (CCF B, Best paper honorable mention)** \| [![](https://img.shields.io/github/stars/nancheng58/DebiasedSR_DRO?style=social&label=Code+Stars)](https://github.com/nancheng58/DebiasedSR_DRO)

***Jiyuan Yang**, Yue Ding, Yidan Wang, Pengjie Ren, Zhumin Chen, Fei Cai, Jun Ma, Rui Zhang, Zhaochun Ren, Xin Xin*

[4] **[Uncovering Selective State Space Model's Capabilities in Lifelong Sequential Recommendation
](https://arxiv.org/pdf/2403.16371) - preprint** \| [![](https://img.shields.io/github/stars/nancheng58/RecMamba?style=social&label=Code+Stars)](https://github.com/nancheng58/RecMamba)

***Jiyuan Yang**, Yuanzi Li, Jingyu Zhao, Hanbing Wang, Muyang Ma, Jun Ma, Zhaochun Ren, Mengqi Zhang, Xin Xin, Zhumin Chen, Pengjie Ren*

[5] **[Enhanced generative recommendation via content and collaboration integration](https://arxiv.org/pdf/2403.18480) -  CIKM 2024 (CCF B)** 

*Yidan Wang, Zhaochun Ren, Weiwei Sun, **Jiyuan Yang**, Zhixiang Liang, Xin Chen, Ruobing Xie, Su Yan, Xu Zhang, Pengjie Ren, Zhumin Chen, Xin Xin*

[6] **Enhanced generative recommendation via content and collaboration integration -  SIGIR 2025 (CCF A)** 

*Shiguang Wu, Zhaochun Ren, Xin Xin, **Jiyuan Yang**, Mengqi Zhang, Zhumin Chen, Maarten de Rijke, Pengjie Ren*

[7] **Improving Sequential Recommenders through Counterfactual Augmentation of System Exposure -  SIGIR 2025 (CCF A)** 

*Ziqi Zhao, Zhaochun Ren, **Jiyuan Yang**, Zuming Yan, Zihan Wang, Liu Yang, Pengjie Ren, Zhumin Chen, Maarten de Rijke, Xin Xin*

<!-- <span class='anchor' id='project-experience'></span> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Aizoo</div><img src='images/projects/aizoo.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">
[Aizoo - A visual deep learning model building and cloud computing platform]

Pengjie Ren, **Hanbing Wang**, Hongtao Tian, Guojun Yan, Chaoyu Shi, Min Wei, Jiyuan Yang, et al.

[**Project information**]
- Develop and test some operators, collect information about these operators(including formulas, backgrounds, source papers, etc) and implement a pedestrian detection task based on Aizoo. 
</div>
</div> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Electronic perpetual calendar</div><img src='images/projects/calendar.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Electronic perpetual calendar]

**Hanbing Wang**

[**Project information**]
- Invented an electronic perpetual calendar from scratch. 
- Circuit design and printing, MCU programming, application of various chips such as HC-05, DHT11, DS1302, LCD1602, MQ-2, etc. 
- Functions include time display, solar terms display, conversion of lunar calendar and Gregorian calendar, alarm clock with customized music, smoke alarm, measurements of temperature and humidity, remote Bluetooth control. 
</div>
</div> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Driverless Assistant Aystem</div><img src='images/projects/Ascend.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[A full stack driverless assistant system based on Huawei Ascend]

Haiqiao Hong, **Hanbing Wang**, Qitao Zhao

[**Project information**]
- Invented a road information detection system which can transmit the detection results to the terminal(eg. screen. a website in our project) in real time. 
- Hardware includes the use of Raspberry Pi, Zynq, Atlas 200DK, 3D-printing, Wireless video signal transmission.
- Software includes improving the effciency of real time object detection algorithm, design a webpage to display all the information. 
</div>
</div> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Style Transfer</div><img src='images/projects/transfer.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[A real time image style transfer system]

Haiqiao Hong, **Hanbing Wang**, Qitao Zhao

[**Project information**]
- Invented a real time style transfer framework which can transfer the image/video style captured by a camera and display it on a webpage. 
- Developed a computer application which can achieve style transfer as long as you download our app. 
- Software includes real time style transfer algorithm, webpage design, video streaming and application development. 
</div>
</div> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Equipment Management System</div><img src='images/projects/deviceManagement.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Laboratory instrument and equipment management system]

**Hanbing Wang**

[**Project information**]
- Developed an online equipment Management System including React based front-end, Springboot based back-end and MySQL Database. 
- Functions includes data addition, deletion, modification query, system login, fuzzy search, paging display, data statistics(according to price or quantity) and statistics display(line chart).
</div>
</div> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Interdisciplinary Project</div><img src='images/projects/law.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Research on copyright protection obligations and technical regulation of cloud storage service providers based on deep learning ——Take Baidu online disk as an example]

**Hanbing Wang**, Cheng Zhang, Zihao Xiao, Chengzhuo Li, Hankang Sun, Xinyu Shen

[**Project information**]
- This is an interdisciplinary project between computer science and law. 
- Knowledge includes fast video/image/text detection and comparison algorithm in various situations. 
</div>
</div> -->

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">Interdisciplinary Project</div><img src='images/projects/biology.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[An online website for querying the signal pathways of hematopoietic cells in human body]

**Hanbing Wang**, Xiaoyu Ji, Bingyang Cui, Baoxun Du, Zihan Liu

[**Project information**]
- This is an interdisciplinary project between computer science and biology.
- Mapped the complete signal pathway of hematopoietic cells in human body, and made a web page for display. The webpage supports addition, deletion, modification, search of genes, fisheye magnification and freely adjusting gene arrangement. 
</div>
</div> -->

<!-- - **Aizoo - A visual deep learning model building and cloud computing platform** I'm in charge of writing some operators and collect information about common operators.  -->

<!-- - **Laboratory instrument and equipment management system** includes: React based front-end framework, Springboot based back-end and MySQL Database.  -->

<!--                -->

# 🎖 Honors and Awards

- *2024.02* **WSDM 2024 Best paper honorable mention award** (3/112).
- *2023.10* Dean's Award, School of Computer Science and Technology at Shandong University.
- *2021.05* Third Prize of National College Student Software Innovation Competition (top 2%).
- *2016.10* First Prize in NOIP, China Computer Federation.

<!-- - *2019.10* Bronze Medal in CCF‑CCSP Final, China Computer Federation. -->

# 📖 Educations

- *2024.09 - Now*, PhD, Shandong University, Qingdao. (Co-Supervised by Prof. Pengjie Ren and Prof. Xin Xin.)
- *2022.09 - 2024.08*, MSc, Shandong University, Qingdao. (Supervised by Prof. Jun Ma, co-advised by Prof. Pengjie Ren and Prof. Xin Xin.)
- *2018.09 - 2022.06*, Bachelor, Shandong University, Qingdao. (*2018.09 - 2019.07*, Software Engineering, Shandong University, Jinan).

# 💻 Internships

- *2021.10 - 2022.08*, Research Assistant, Information Retrieval Lab, Shandong University.

# 💬 Others

- Teaching Assistant: Machine Learning course (2023 Fall, 2023 Spring, 2022 Fall, 2022 Spring),  Software Engineering course (2023 Spring).
- Academic Service: Reviewer (Program Committee Member) of IP&M, TKDE, TOIS, SIGIR 2024, SIGIR 2025, SIGIR-AP 2025.