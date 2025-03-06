---
title: การจัดการเซิร์ฟเวอร์โครงการ MS ด้วย Aspose.Tasks
linktitle: การจัดการเซิร์ฟเวอร์โครงการด้วย Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ปลดล็อกการจัดการ MS Project Server ได้อย่างราบรื่นด้วย Aspose.Tasks สำหรับ .NET ทำให้งานโครงการเป็นอัตโนมัติได้อย่างง่ายดาย
weight: 23
url: /th/net/project-management-integration/project-server-management/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการเซิร์ฟเวอร์โครงการ MS ด้วย Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการจัดการ MS Project Server โดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม ช่วยให้สามารถผสานรวมและจัดการข้อมูลโปรเจ็กต์ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกในการจัดการ MS Project Server ด้วย Aspose.Tasks ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Microsoft Project Server: คุณต้องเข้าถึงอินสแตนซ์ Microsoft Project Server ที่คุณมีสิทธิ์ระดับผู้ดูแลระบบหรืออย่างน้อยสิทธิ์ในการสร้างและจัดการโครงการ
2.  Aspose.Tasks สำหรับไลบรารี .NET: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).
3. ข้อมูลรับรอง: รับข้อมูลรับรองที่จำเป็นในการตรวจสอบสิทธิ์กับอินสแตนซ์ MS Project Server ของคุณ โดยทั่วไปจะประกอบด้วยชื่อผู้ใช้และรหัสผ่าน
## นำเข้าเนมสเปซ
ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## ขั้นตอนที่ 1: ตั้งค่าข้อมูลรับรองการตรวจสอบสิทธิ์
ขั้นแรก คุณต้องตั้งค่าข้อมูลรับรองความถูกต้องเพื่อเชื่อมต่อกับอินสแตนซ์ MS Project Server ของคุณ ซึ่งรวมถึงที่อยู่โดเมน ชื่อผู้ใช้ และรหัสผ่าน
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## ขั้นตอนที่ 2: โหลดโครงการ
จากนั้น โหลดไฟล์ MS Project ที่คุณต้องการจัดการโดยใช้ Aspose.Tasks
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## ขั้นตอนที่ 3: สร้างตัวจัดการเซิร์ฟเวอร์โครงการ
 ยกตัวอย่าง`ProjectServerManager` วัตถุโดยใช้ข้อมูลประจำตัวที่กำหนดไว้ก่อนหน้านี้
```csharp
var manager = new ProjectServerManager(credentials);
```
## ขั้นตอนที่ 4: กำหนดตัวเลือกการบันทึก
กำหนดตัวเลือกการบันทึกเฉพาะสำหรับโครงการของคุณ ตัวอย่างเช่น คุณสามารถตั้งค่าการหมดเวลาสำหรับการดำเนินการได้
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## ขั้นตอนที่ 5: สร้างหรืออัปเดตโครงการ
สุดท้าย ให้สร้างหรืออัปเดตโครงการบน MS Project Server
```csharp
manager.CreateNewProject(project, options);
```
ยินดีด้วย! คุณจัดการ MS Project Server ได้สำเร็จโดยใช้ Aspose.Tasks สำหรับ .NET

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีจัดการ MS Project Server โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ .NET ด้วยขั้นตอนที่ให้มา คุณสามารถรวม Aspose.Tasks เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น เพื่อทำให้งานการจัดการโครงการบน MS Project Server เป็นแบบอัตโนมัติ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project Server ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks รองรับการทำงานร่วมกับ Microsoft Project Server เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ถาม: ฉันสามารถดำเนินการจำนวนมากกับโปรเจ็กต์โดยใช้ Aspose.Tasks ได้หรือไม่
ตอบ: ได้ Aspose.Tasks ช่วยให้คุณสามารถดำเนินการจำนวนมาก เช่น การสร้าง การอัปเดต และการลบโปรเจ็กต์บน MS Project Server
### ถาม: Aspose.Tasks ให้การสนับสนุนการจัดกำหนดการโครงการและการจัดการทรัพยากรหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ให้การสนับสนุนที่ครอบคลุมสำหรับการจัดกำหนดการโครงการ การจัดสรรทรัพยากร และฟังก์ชันการจัดการงาน
### ถาม: เป็นไปได้หรือไม่ที่จะสร้างรายงานงานอัตโนมัติด้วย Aspose.Tasks
ตอบ: ได้ Aspose.Tasks ช่วยให้คุณสามารถสร้างรายงานแบบกำหนดเองโดยอัตโนมัติตามข้อมูลโปรเจ็กต์ อำนวยความสะดวกในการติดตามและวิเคราะห์โปรเจ็กต์ที่มีประสิทธิภาพ
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถสำรวจความสามารถของ Aspose.Tasks ได้ด้วยการเข้าถึงรุ่นทดลองใช้ฟรีจาก[เว็บไซต์](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
