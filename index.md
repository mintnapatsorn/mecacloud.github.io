---
layout: default
---
# Documentations

## Installation
{% for install in site.installs %}
  * [{{ install.title }}]({{ install.url }})
{% endfor %}

## Tutorial
{% for tutorial in site.tutorials %}
  * [{{ tutorial.title }}]({{ tutorial.url }})
{% endfor %}

## Concept
{% for concept in site.concepts %}
  * [{{ concept.title }}]({{ concept.url }})
{% endfor %}

## Presentation
รวบรวม การนำเสนอ และอบรม ที่เกี่ยวข้องกับ MECAs

| ชื่อการอบรม        | วัน เวลา         | สถานที่ | ดาวน์โหลด |
|:-------------|:------------------|:------|:------|
| สัมมนาและแลกเปลี่ยนเรียนรู้ Special Talks หัวข้อ “Cloud Computing”  | วันอังคารที่ 9 กรกฎาคม 2562 เวลา 09.00 - 12.00 น.  |  ห้องบุษกร อาคารเนคเทค  | <ul><li>[Presentation](/assets/pdf/2019-07-09-MECAs-Update.pdf)</li></ul> |
| การใช้บริการ MECAs (Cloud Container Service Platform)  | วันอังคารที่ 2 เมษายน 2562 เวลา 08.30 - 16.30 น.  |  ห้องบุษกร อาคารเนคเทค  | <ul><li>[Presentation](/assets/pdf/2019-04-02-MECAs-Intro.pdf)</li><li>[Hand on](/assets/pdf/2019-04-02-MECAs-Application-Workshop.pdf)</li></ul> |
| ทำความรู้จัก Micro Service, Container Technology และการใช้ Docker | วันพฤหัสบดีที่ 7 มีนาคม 2562 เวลา 08.30 - 16.30 น.  |  ห้อง CC306 อาคารศูนย์ประชุมอุทยานวิทยาศาสตร์ประเทศไทย  | <ul><li>[Presentation](/assets/pdf/2019-03-07-Microservices-Basic-Docker.pdf)</li><li>[Windows Setup](/assets/pdf/2019-03-07-Prepare-Windows.pdf)</li><li>[Ubuntu Setup](/assets/pdf/2019-03-07-Prepare-Ubuntu.pdf)</li><li>[Hand on#1](/assets/pdf/2019-03-07-Hand-on-Create-new-Django-application.pdf)</li><li>[Hand on#2](/assets/pdf/2019-03-07-Hand-on-Docker-build.pdf)</li><li>[Example YAML](/assets/pdf/2019-03-07--example-yaml.zip)</li></ul> |
