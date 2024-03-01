---
title: เซิร์ฟเวอร์บันทึกตัวเลือกโครงการ MS สำหรับ Aspose.Tasks
linktitle: ตัวเลือกการบันทึกเซิร์ฟเวอร์โครงการสำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีบันทึกตัวเลือก Microsoft Project สำหรับ Aspose.Tasks โดยใช้การรวม Project Server ปรับปรุงขั้นตอนการทำงานการจัดการโครงการของคุณ
type: docs
weight: 16
url: /th/net/saving-options/project-server-save-options/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการบันทึกตัวเลือก Microsoft Project สำหรับ Aspose.Tasks โดยใช้ Project Server Aspose.Tasks เป็น .NET API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรมได้ ด้วยการใช้ประโยชน์จากความสามารถของ Project Server ทำให้เราสามารถรวม Aspose.Tasks เข้ากับเวิร์กโฟลว์การจัดการโครงการของเราได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET: ติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
   
2. การเข้าถึง Project Server: คุณจะต้องมีข้อมูลรับรองการเข้าถึงและ URL ของอินสแตนซ์ Project Server ของคุณ หากคุณยังไม่มี คุณสามารถขอรับรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
3. ไฟล์ Microsoft Project: เตรียมไฟล์ Microsoft Project (.mpp) ที่คุณต้องการบันทึกโดยใช้ Aspose.Tasks

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## ขั้นตอนที่ 1: เริ่มต้นโครงการและข้อมูลประจำตัว
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 ให้แน่ใจว่าคุณเปลี่ยน`"Your Document Directory"`, `URL`, `Domain`, `UserName` , และ`Password` ด้วยคุณค่าที่แท้จริงของคุณ
## ขั้นตอนที่ 2: สร้างตัวจัดการเซิร์ฟเวอร์โครงการ
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## ขั้นตอนที่ 3: กำหนดตัวเลือกการบันทึก
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 ปรับ`ProjectGuid`, `ProjectName`, `Timeout` , และ`PollingInterval` ตามความต้องการของคุณ
## ขั้นตอนที่ 4: บันทึกโครงการไปยังเซิร์ฟเวอร์
```csharp
manager.CreateNewProject(project, options);
```
สิ่งนี้จะบันทึกโปรเจ็กต์ไปยัง Project Server ด้วยตัวเลือกที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกตัวเลือก Microsoft Project สำหรับ Aspose.Tasks โดยใช้การรวม Project Server เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถรวม Aspose.Tasks เข้ากับเวิร์กโฟลว์การจัดการโครงการของคุณได้อย่างราบรื่น ซึ่งช่วยเพิ่มประสิทธิภาพและประสิทธิผล
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับ Microsoft Project เวอร์ชันต่างๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถขอรับ Aspose.Tasks เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: Aspose.Tasks รองรับการทำงานแบบมัลติเธรดหรือไม่
ตอบ: ใช่ Aspose.Tasks ได้รับการออกแบบมาให้ปลอดภัยต่อเธรด ช่วยให้สามารถเข้าถึงข้อมูลโปรเจ็กต์ได้พร้อมกัน
### ถาม: ฉันสามารถปรับแต่งตัวเลือกการบันทึกเมื่อใช้การรวม Project Server ได้หรือไม่
ตอบ: ได้ คุณสามารถปรับแต่งตัวเลือกการบันทึก เช่น ชื่อโปรเจ็กต์ การหมดเวลา และช่วงเวลาการโพลให้เหมาะกับความต้องการของคุณได้
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).