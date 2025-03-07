---
title: แยกข้อมูลโครงการ MS ใน Aspose.Tasks
linktitle: การแยกข้อมูลโครงการใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีดึงข้อมูล MS Project ได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ .NET เจาะลึกบทช่วยสอนที่ครอบคลุมของเรา
weight: 20
url: /th/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แยกข้อมูลโครงการ MS ใน Aspose.Tasks

## การแนะนำ
คุณกำลังมองหาวิธีดึงข้อมูลจากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET อยู่ใช่ไหม? ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน แต่ก่อนที่เราจะเจาะลึกรายละเอียดการใช้งาน ก่อนอื่นมาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการแล้ว
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
### 1. Aspose.Tasks สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET แล้ว หากคุณยังไม่ได้ดำเนินการ คุณสามารถดาวน์โหลดได้จาก[Aspose.Tasks สำหรับเว็บไซต์ .NET](https://releases.aspose.com/tasks/net/).
### 2. ข้อมูลประจำตัวสำหรับ SharePoint
คุณจะต้องมีข้อมูลประจำตัวเพื่อเข้าถึง SharePoint ที่เก็บไฟล์ MS Project ของคุณ ตรวจสอบให้แน่ใจว่าคุณมีข้อมูลต่อไปนี้:
- ที่อยู่โดเมน SharePoint
- ชื่อผู้ใช้
- รหัสผ่าน
## การนำเข้าเนมสเปซ
เมื่อคุณจัดการข้อกำหนดเบื้องต้นเรียบร้อยแล้ว ก็ถึงเวลานำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
ตอนนี้เรามาแบ่งกระบวนการแยกข้อมูล MS Project ออกเป็นหลายขั้นตอนกัน
## ขั้นตอนที่ 1: ระบุข้อมูลรับรอง
ขั้นแรก คุณต้องระบุข้อมูลประจำตัว SharePoint ของคุณเพื่อเข้าถึง Project Server
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## ขั้นตอนที่ 2: เตรียมใช้งาน Project Server Manager
 ถัดไป เริ่มต้น a`ProjectServerManager` อินสแตนซ์พร้อมข้อมูลประจำตัวที่ให้ไว้
```csharp
var reader = new ProjectServerManager(credentials);
```
## ขั้นตอนที่ 3: ดึงรายการโครงการ
ตอนนี้คุณสามารถดึงข้อมูลรายการโครงการจาก Project Server ได้
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## ขั้นตอนที่ 4: พิมพ์ข้อมูลโครงการ
สุดท้าย วนซ้ำรายการโครงการและพิมพ์ข้อมูล
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีดึงข้อมูล MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เรียบร้อยแล้ว ด้วยความรู้นี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับ Microsoft Project เวอร์ชันใดก็ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับ Microsoft Project เวอร์ชันต่างๆ รวมถึง 2003, 2007, 2010, 2013, 2016 และ 2019
### คำถามที่ 2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับทั้งแพลตฟอร์ม Windows และ Linux หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET เข้ากันได้กับทั้งแพลตฟอร์ม Windows และ Linux ทำให้มีความอเนกประสงค์สำหรับสภาพแวดล้อมการพัฒนาที่แตกต่างกัน
### คำถามที่ 3: ฉันสามารถแยกการพึ่งพางานโดยใช้ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks สำหรับ .NET มีฟังก์ชันการทำงานที่มีประสิทธิภาพเพื่อดึงข้อมูลไม่เพียงแต่ข้อมูลโครงการพื้นฐานเท่านั้น แต่ยังรวมไปถึงการขึ้นต่อกันของงานและรายละเอียดที่ซับซ้อนอื่นๆ ด้วย
### คำถามที่ 4: Aspose.Tasks สำหรับ .NET ให้การสนับสนุนทางเทคนิคหรือไม่
 ตอบ: ได้ คุณสามารถรับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks สำหรับ .NET ผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)โดยคุณสามารถถามคำถามและขอความช่วยเหลือจากผู้เชี่ยวชาญได้
### คำถามที่ 5: ฉันสามารถลองใช้ Aspose.Tasks สำหรับ .NET ก่อนที่จะซื้อได้หรือไม่
 ตอบ: แน่นอน! คุณสามารถทดลองใช้ Aspose.Tasks สำหรับ .NET ได้ฟรีจาก[หน้าเผยแพร่](https://releases.aspose.com/)ให้คุณสำรวจฟีเจอร์ต่างๆ ก่อนตัดสินใจซื้อ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
