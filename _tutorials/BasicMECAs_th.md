---
layout: tutorial
title: Basic Deploy MECAs Website Application(TH)1
---

# 1. Static Website
## Deploy Application 1 deployment และ 1 service

>หลังจากที่มีการเตรียม Docker Image เรียบร้อยแล้ว เราสามารถนำ Docker Image นั้น ไป Deploy บน MECAs ซึ่งเป็น บริการ Container as a Service ได้ โดยทุกครั้ง จะต้องมีการวางแผนการ Deploy Application ก่อน ซึ่งในที่นี้รูปแบบของ Application จะเป็น 1 deployment และ 1 service ดังตัวอย่าง

**ex.**

![deploy1](/assets/deploy1.png)

### เริ่มสร้าง Deployment และ Service

1. คลิกที่เมนู **Workload** ที่แถบเมนูด้านบน

    ![workloadpage](/assets/workloadpage.png)

    โดยหน้า Workload นี้จะแสดงชื่องานทั้งหมดที่อยู่ใน namespace นั้น คุณสามารถตรวจสอบสถานะงานของคุณได้ที่นี่

2. คลิกที่ปุ่ม **+ New workload** ทางด้านบนขวา เพื่อทำการสร้าง workload ของตัวเอง

    ![newworkload](/assets/newworkload.png)

3. กรอกข้อมูลลงไปในแบบฟอร์ม ในส่วนของ Deployment

    - Deployment

        **Deployment Name**|my-awesome-site

    ![unnamed](/assets/unnamed.png)

4. ในส่วนของ container กรอกชื่อ container และ docker image ที่มาจาก repository ของ docker hub โดยสามารถเป็น image ของคุณ หรือ image อื่น ๆ ที่แบ่งปันอยู่บน docker hub ก็ได้

    - Container

        |**Container**|my-awesome-site|
        |**Image Name**|ridnarong/my-awesome-site:v1|
        |*Ports*
        |**Name**|**Port**|
        |http|80|

    ![containerform](/assets/containerform.png)

5. เริ่มต้นกรอกข้อมูลของ Service  สำหรับ mysite โดยคลิกเพิ่ม service ที่เมนูด้านซ้าย

    ![addservice](/assets/addservice.png)

    >กรอกข้อมูลลงไปในแบบฟอร์ม ในส่วนของ Service โดยบริการของ MECAs มีบริการสร้าง subdomain
    >
    >**< servicename >.< namespace >.web.meca.in.th**
    >
    >พร้อมทั้ง SSL Certificate (Let’s encrypt) ให้อัตโนมัติ สำหรับการใช้งาน Protocol HTTP/HTTPS ผ่าน port 80/443 เพียงเลือก Label service:http ซึ่งผู้ใช้ จะต้องระบุ Service Port  เป็น 80 ด้วย เพื่อการทำงานอย่างถูกต้อง

    - Service

        |**Service Name**| my-site
        |**Selector**|my-awesome-site
        |Port|
        |**Name**|**Service Port**
        |web|80


    ![service](/assets/service.png)

6. เมื่อกรอกข้อมูลเสร็จแล้ว อย่าลืมตั้ง workload name ที่ด้านบนซ้าย และคลิกปุ่ม **Deploy** ทางด้านบนขวา

    ![workloadnamedeploybutton](/assets/workloadnamedeploybutton.png)

7. จากนั้นจะกลับเข้าสู้หน้า workload ซึ่งมี workload name ที่ตั้งไว้ปรากฏขึ้น

    ![namewllist](/assets/namewllist.png)

8. เมื่อคลิกที่ workload name จะเข้าไปยังหน้ารายละเอียดของ workload นั้น และสามารถแก้ไข deployment และ service ได้ที่ปุ่ม **edit** ด้านบนขวา

    ![deploydone](/assets/deploydone.png)

9. สามารถคลิกไอคอนที่อยู่หลังชื่อ service เพื่อไปยังเว็บไซต์

    ![iconsite](/assets/iconsite.png)

    ตัวอย่างเช่น basic jekyll site

    ![myawesomesite](/assets/myawesomesite.png)

**หมายเหตุ**
>รองรับ WS และ WSS สำหรับ Websocket เช่นเดียวกัน การใช้งาน subdomain อาจจะใช้เวลา 1 - 2 นาที ในการพร้อมใช้งาน 
>
>การให้บริการ Protocol HTTP/HTTPS จะไม่ได้มีการ redirect HTTP ไปยัง HTTPS อัตโนมัติ 
>
>ผู้ใช้สามารถใช้ Custom Domain ได้ โดยมีการตั้งค่า DNS มายังระบบ สามารถใช้งานได้เช่นเดียวกัน แต่ในขณะนี้ ยังไม่มีบริการ Custom Certificate สำหรับผู้ใช้ที่ต้องการใช้ SSL Certificate ของตัวเอง ระบบจะสร้าง SSL Certificate ผ่าน Let’s encrypt ให้สำหรับ Custom domain


### คุณสร้าง Web Application สำเร็จแล้ว ! 
