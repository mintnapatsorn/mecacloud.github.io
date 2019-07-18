---
layout: tutorial
title: Basic Deploy MECAs Website Application(TH)2
---

# 2. Web application with database
## Deploy Application 2 deployment และ 2 service


- **Joomla และ Mysql**

- **`Joomla`** คือ ระบบที่ช่วยในการจัดการเนื้อหา(Content Management System: CMS) บนเว็บไซต์ ที่เป็น open source โดย Joomla เขียนใน PHP ใช้เทคนิคการเขียนโปรแกรมเชิงวัตถุ (OOP) และรูปแบบการออกแบบซอฟต์แวร์จัดเก็บข้อมูลในฐานข้อมูล MySQL, MS SQL หรือ PostgreSQL

- **`MySQL`** คือ open source database ที่เป็นที่นิยมที่สุดในโลก. ด้วยประสิทธิภาพที่พิสูจน์ได้ความน่าเชื่อถือและความสะดวกในการใช้งาน MySQL กลายเป็นตัวเลือกฐานข้อมูลชั้นนำสำหรับแอปพลิเคชันบนเว็บ

## Prerequisite

- เข้าใจเกี่ยวกับ web application ที่ต้องการใช้
- เรียนรู้ basic web application in MECA 1
- เป็นสามาชิกของ docker hub

1. คลิกที่เมนู **Workload** ที่แถบเมนูด้านบน โดยหน้า Workload นี้จะแสดงชื่องานทั้งหมดที่อยู่ใน namespace นั้น คุณสามารถตรวจสอบสถานะงานของคุณได้ที่นี่

    ![Workloadpage](/assets/workloadpage.jpg)

2. คลิกที่ปุ่ม **+ NEW workload** ทางด้านบนขวา เพื่อทำการสร้าง workload ของตัวเอง

    ![New workload](/assets/Newworkload.jpg)

3. ตั้ง workload name ที่ด้านบนซ้าย โดย workload name จะเป็นชื่อที่แสดงอยู่ในหน้า workload

    ![workloadname](/assets/workloadname.png)

4. ทำในส่วน Deployment ให้เรียบร้อย โดยเริ่มจากส่วนของ **`Joomla`** ก่อน 

    ![Joomlahub](/assets/joomlahub.jpg)

    กรอกข้อมูลลงไปในแบบฟอร์มส่วนหัวของ Deployment

    ![Deployname](/assets/joomladeploy.jpg)

    ในส่วนของ container กรอกชื่อ container และ docker image ที่มาจาก repository ของ docker hub หรือ image ของคุณ 

    ![Joomlacontainer](/assets/joomlacontainer.jpg)

    ในส่วนของ Environment ค้นหา web application ที่คุณต้องการ แล้วเลื่อนลงเพื่อดูวิธีใช้ image และคุณจะเห็นรายละเอียดเกี่ยวกับ environment config

    ![Joomlaenv](/assets/joomlaenvconfig.jpg)

    - นำข้อมูล environment config มาเติมในส่วนของ environment variable

    ![Joomlaenv](/assets/joomlaenv.jpg)

    พอร์ตของเว็บไซต์ ชื่อของพอร์ตสามารถตั้งได้อย่างอิสระ แต่เลขพอร์ตต้องใช้เลขที่คุณ run เว็บไซต์ เช่น คุณ run เว็บไซต์ บน
    `https://localhost:4000` คุณต้องใช้เลขพอร์ต 4000 default http:80 

    - Joomla สามารถใช้เลขพอร์ต 4000 หรือเลข 80 ที่เป็น default port ของ HTTP
    ![Joomlacontainer](/assets/joomlacontainer.jpg)

5. เมื่อทำในส่วนของ deployment เสร็จแล้ว ถัดมาจะเป็นส่วนของ service โดยเริ่มจาก

    ![AddService](/assets/addservice.jpg)

    ถ้าเว็บไซต์ใช้ http หรือ https ให้คลิกที่ checkbox ของ service

    ![JoomlaCheckservice](/assets/joomlacheckservice.jpg)

    เลือก deployment ที่ต้องการเพิ่ม service และตั้งชื่อ service

    ![Joomlaselectdeploy](/assets/joomlaadddeploy.jpg)

    ใส่ชื่อและเลขพอร์ต เลขพอร์ตต้องเป็นเลขของ images ใน container เช่น http:80 ,https:443 or mysql:3306

    ![Joomlaserviceport](/assets/joomlaserviceport.jpg)

6. จากนั้น กลับมาเริ่มทำในส่วน Deployment ของ **`MySQL`** 

    ![MysqlDeploy](/assets/mysqldeploy.jpg)

    ในส่วนของ **Containers** 

    ![Mysqlhub](/assets/mysqlhub.jpg)

    ในส่วนของ container กรอกชื่อ container และ docker image ที่มาจาก repository ของ docker hub หรือ image ของคุณ
    - ถ้า MySQL error คุณต้องเปลี่ยน MySQL เป็นเวอร์ชันที่ 5
    - จาก mysql->mysql:5

    ![Mysqlcontainers](/assets/mysqlport.jpg)

    พอร์ตของเว็บไซต์ ชื่อของพอร์ตสามารถตั้งได้อย่างอิสระ แต่เลขพอร์ตต้องใช้เลขที่คุณ run เว็บไซต์ เช่น คุณ run เว็บไซต์ บน
    `https://localhost:4000` คุณต้องใช้เลขพอร์ต 4000 default http:80

    - MySQL ต้องใช้พอร์ตชื่อ **`mysql`** เพราะ database ไม่ใช่เว็บไซต์ที่จะใช้  **`http`**

    ![Mysqlcontainers](/assets/mysqlport.jpg)

    ในส่วนของ Environment ค้นหา web application ที่คุณต้องการ แล้วเลื่อนลงเพื่อดูวิธีใช้ image และคุณจะเห็นรายละเอียดเกี่ยวกับ environment config

    ![Mysqlenv](/assets/mysqlenvconfig.jpg)

    นำข้อมูล environment config มาเติมในส่วนของ environment variable

    ![Mysqlenv](/assets/mysqlenv.jpg)

7. เมื่อทำในส่วนของ deployment เสร็จแล้ว ถัดมาจะเป็นส่วนของ service โดยเริ่มจาก

    ![Add2Service](/assets/addservice2nd.jpg)

    checkbox เนื่องจากเว็บไซต์ไม่ได้ใช้ http หรือ https จึงไม้ต้องคลิกที่ checkbox ของ service

    ![MysqlCheckservice](/assets/mysqlcheckservice.jpg)

    เลือก deployment ที่ต้องการเพิ่ม service และตั้งชื่อ service

    ![Mysqlselectdeploy](/assets/mysqlselectdeploy.jpg)

    ใส่ชื่อและเลขพอร์ต เลขพอร์ตต้องเป็นเลขของ images ใน container โดย mysql ต้องใช้เลข 3306

    ![Mysqlserviceport](/assets/mysqlserviceport.jpg)

8. เมื่อเสร็จแล้วให้คลิก **`Deploy`** งานนี้ ชื่องานของคุณจะแสดงอยู่ในหน้า namespace workload portal

    คลิก **`Deploy`**

    ![Deployclick](/assets/deployclick.jpg)

    เมื่อคลิกแล้วกลับไปหน้า workload ชื่องานจะแสดงขึ้น

    ![WorkloadPageUpdate](/assets/workloadpageupdate.jpg)


9. จากนั้นรอความคืบหน้าขณะหนึ่ง เมื่อคุณคลิกชื่องานของคุณ สถานะงานจะเป็นสีเขียว แสดงให้เห็นว่า service พร้อมแล้ว

    ![Joomla](/assets/joomlasuccess.jpg)
    ![mysqlsuccess](/assets/mysqlsuccess.jpg)

10. คุณสามารถเข้าเป็นยังเว็บไซต์โดยไปที่ url  **Service Name.Name space.web.meca.in.th** หรือ คลิกที่ชื่อโปรเจคและเลื่อนลงไปยังส่วน service
    - ในส่วนนี้ **`MySQL`** ไม่สามารถเข้าถึงได้เนื่องจากไม่ใช่  ้HTTP service

    ![ServicetoWeb](/assets/serviceweb.jpg)

    ถ้าเว็บไซต์ไม่สามารถเข้าถึงได้จะแสดงเป็น

    ![502badgateway](/assets/502gateway.png)

    คุณสามารถเช็ค error โดยคลิกที่ **`LOG`** รายละเอียดของ error จะแสดงขึ้น

    ![Logerror](/assets/serviceerror.jpg)

    - ปัญญหาที่พบบ่อยคือ error ใน MySQL deployment เนื่องจาก resource ไม่พอ ดังนั้นคุณต้อง request resouce และ limit ที่มากขึ้น ในส่วนของ **`Environment`** 

    ![SQLError](/assets/envmemory.jpg)

    - **CAUTION**: resource มีอย่างจำกัด ถ้าคุณ request มากไปจะเกิดการ overload

### นี่คือ Joomla & MySQL website ของคุณ 
คุณสามารถสร้าง account, web url และ ข้อมูลเกี่ยวกับ website ของคุณได้ที่นี่

![Joomlawebsite](/assets/joomlafullyweb.jpg)
