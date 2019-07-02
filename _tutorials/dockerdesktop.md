---
title: Install Docker Desktop for Windows
layout: tutorial
---

Docker Desktop for Windows คือ Docker Community Edition (CE) สำหรับ Microsoft Windows. โดย Community Edition (CE) เป็นชื่อรุ่นใช้งานฟรีของ Docker.

ดาวน์โหลด Docker Desktop for Windows ได้ที่ [Docker for Windows from Docker Hub](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

## สิ่งที่ควรรู้ก่อนติดตั้ง Docker Desktop

- Docker Desktop for Windows ใช้ Hyper-V เป็น VM engine ทำให้ VirtualBox ทำงานไม่ได้ Docker Desktop จะเปิดการใช้งาน Hyper-V สำหรับคุณหากมีความจำเป็นและทำการเริ่มต้นอุปกรณ์ของคุณใหม่/รีสตาร์ทเครื่อง
- ความต้องการของระบบ
  - สำหรับ Window 10 Pro หรือ Education ขึ้นไป และมี account docker hub
    Windows 10 64bit: Pro, Enterprise or Education (Build 15063 or later)
  - CPU SLAT-capable feature.
  - At least 4GB of RAM

Note: หากระบบของคุณไม่ตรงตามข้อกำหนดในการเรียกใช้ Docker Desktop สำหรับ Windows คุณสามารถติดตั้ง [Docker Toolbox]() ซึ่งใช้ Oracle Virtual Box แทน Hyper-V

![docker-enable-hyper-v](/assets/docker-enable-hyper-v.png)

รูปที่ 1 ใช้งาน docker ในโหมดของ Hyper-V แต่จะทำให้ VirtualBox ทำงานไม่ได้ หลังจากนั้นเครื่องจะ Restart และ Docker จะถูกใช้งาน อัตโนมัติ

เมื่อกด OK จะเปิดใช้งาน Feature Hyper-V อัตโนมัติ แต่หากไม่สำเร็จ  xศึกษาวิธีการเปิด Feature Hyper-V ได้ที่ [ลิ้งนี้](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)

## Install Docker Desktop for Windows desktop app

1. Double-click ที่ Docker Desktop for Windows Installer.exe เพื่อ run the installer
2. ทำตามตัวช่วยการติดตั้งเพื่อยอมรับ license อนุญาตและดำเนินการติดตั้งโปรแกรม
3. Click ปุ่ม Finish บน the setup complete dialog เพื่อเริ่มใช้ Docker

## เริ่มต้นการใช้งาน Docker Desktop for Windows

ถ้า Docker ไม่ได้เริ่มต้นอัตโนมัติภายหลังการติดตั้ง ในการจะเริ่มใช้งาน ค้นหา Docker ที่ช่องค้นหา เลือก Docker Desktop for Windows จากผลลัพท์และคลิกเปิด (หรือ กด Enter)

![docker-app-search](/assets/docker-app-search.png)
เมื่อมีไอคอนรูปวาฬอยู่บนแถบสถานะ แสดงว่า Docker กำลังทำงานอยู่ ทำให้สามารถใช้คำสั่งบนหน้าต่าง terminal ใดๆก็ได้

![whale-icon-systray](/assets/whale-icon-systray.png)

 ถ้าไอคอนหายไปจากแถบบาร์ ให้ลองคลิกไปดูที่ลูกศรขึ้นบนแถบ เพื่อแสดงไอค่อนเพิ่มเติม

ถ้าเพิ่งติดตั้งโปรแกรมเสร็จ จะเห็น ป๊อปอัพข้องความแสดงการติดตั้งสำเร็จพร้อมกับการแนะนำ step ถัดไป และลิ้งที่ไปยัง documentation

![dockerdesktop](/assets/dockerdesktop.png)

รูปที่ 2 หน้าต่างล็อกอินเข้าสู่ Docker ซึ่งผู้ใช้งานจะต้องทำการสมัครสมาชิกก่อนถึงจะสามารถใช้งานได้

เมื่อติดตั้งเสร็จสมบูรณ์ให้เลือก About Docker จากการคลิกขวาบนไอคอนรูปวาฬเพื่อตรวจสอบว่าเป็น Docker เวอร์ชันล่าสุด

### ยินดีด้วย ! Docker Desktop for Windows พร้อมใช้งานแล้ว