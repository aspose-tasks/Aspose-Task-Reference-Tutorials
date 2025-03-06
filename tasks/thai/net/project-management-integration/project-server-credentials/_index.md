---
title: การจัดการข้อมูลประจำตัวเซิร์ฟเวอร์โครงการ MS ใน Aspose.Tasks
linktitle: การจัดการข้อมูลรับรองเซิร์ฟเวอร์โครงการใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการข้อมูลรับรอง MS Project Server ได้อย่างราบรื่นด้วย Aspose.Tasks สำหรับ .NET เพิ่มประสิทธิภาพการบริหารจัดการโครงการ
weight: 22
url: /th/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการข้อมูลประจำตัวเซิร์ฟเวอร์โครงการ MS ใน Aspose.Tasks

## การแนะนำ
ในขอบเขตของการจัดการโครงการ การประสานงานที่มีประสิทธิภาพและการสื่อสารที่ราบรื่นเป็นสิ่งสำคัญสำหรับการดำเนินโครงการที่ประสบความสำเร็จ Aspose.Tasks สำหรับ .NET มอบโซลูชันที่ครอบคลุมสำหรับการจัดการข้อมูลประจำตัวของ Microsoft Project Server ทำให้ผู้ใช้สามารถเข้าถึงและจัดการข้อมูลโครงการได้อย่างปลอดภัย บทช่วยสอนนี้จะเจาะลึกกระบวนการจัดการข้อมูลรับรอง MS Project Server โดยใช้ Aspose.Tasks สำหรับ .NET ซึ่งจะแนะนำผู้ใช้ในแต่ละขั้นตอนเพื่อให้แน่ใจว่าได้รับประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้นการเดินทางของการจัดการข้อมูลประจำตัว MS Project Server ด้วย Aspose.Tasks สำหรับ .NET ตรวจสอบให้แน่ใจว่ามีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง Aspose.Tasks สำหรับ .NET
 ในการเริ่มต้น ให้ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จากที่ให้มา[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/). ปฏิบัติตามคำแนะนำในการติดตั้งเพื่อรวมไลบรารีเข้ากับสภาพแวดล้อม .NET ของคุณได้อย่างราบรื่น
### 2. ข้อมูลรับรองการเข้าถึง
รวบรวมข้อมูลประจำตัวที่จำเป็นสำหรับการเข้าถึง MS Project Server ซึ่งรวมถึงที่อยู่โดเมน SharePoint ชื่อผู้ใช้ และรหัสผ่านที่เกี่ยวข้องกับ Project Server

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชันการทำงานที่ Aspose.Tasks สำหรับ .NET มอบให้อย่างมีประสิทธิภาพ

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีเอกสาร
```csharp
String DataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: ตั้งค่าที่อยู่โดเมน SharePoint ชื่อผู้ใช้ และรหัสผ่าน
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## ขั้นตอนที่ 3: สร้างข้อมูลรับรองเซิร์ฟเวอร์โครงการ
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## ขั้นตอนที่ 4: โหลดไฟล์โครงการ
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## ขั้นตอนที่ 5: เตรียมใช้งาน Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## ขั้นตอนที่ 6: สร้างโครงการใหม่
```csharp
manager.CreateNewProject(newProject);
```
## ขั้นตอนที่ 7: ดึงรายการโครงการ
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## ขั้นตอนที่ 8: วนซ้ำรายการโครงการ
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## บทสรุป
การจัดการข้อมูลรับรอง MS Project Server อย่างมีประสิทธิภาพเป็นสิ่งสำคัญยิ่งสำหรับการจัดการโครงการที่มีประสิทธิภาพ Aspose.Tasks สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นโดยจัดเตรียมชุดฟังก์ชันที่มีประสิทธิภาพ ด้วยการทำตามคำแนะนำทีละขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ ผู้ใช้สามารถผสานรวม Aspose.Tasks สำหรับ .NET เข้ากับโปรเจ็กต์ของตนได้อย่างราบรื่น ทำให้มั่นใจได้ถึงการเข้าถึงและการจัดการข้อมูลโปรเจ็กต์อย่างปลอดภัย
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ Microsoft Project Server ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks สำหรับ .NET ได้รับการออกแบบมาให้เข้ากันได้กับ Microsoft Project Server เวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความคล่องตัวและความยืดหยุ่นสำหรับผู้ใช้
### ถาม: ฉันสามารถรวม Aspose.Tasks สำหรับ .NET เข้ากับโปรเจ็กต์ .NET ที่มีอยู่ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET สามารถรวมเข้ากับโปรเจ็กต์ .NET ที่มีอยู่ได้อย่างราบรื่น ช่วยอำนวยความสะดวกในการจัดการโปรเจ็กต์ที่มีประสิทธิภาพ
### ถาม: Aspose.Tasks for .NET ให้การสนับสนุนการเข้าถึงทรัพยากรของโปรเจ็กต์หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ .NET ให้การสนับสนุนที่ครอบคลุมสำหรับการเข้าถึงและจัดการทรัพยากรของโปรเจ็กต์ ซึ่งช่วยเพิ่มประสิทธิภาพการจัดการโปรเจ็กต์
### ถาม: มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET มีตัวเลือกการให้สิทธิ์การใช้งานที่ยืดหยุ่น รวมถึงสิทธิ์การใช้งานชั่วคราวสำหรับการทดลองและสิทธิ์การใช้งานเต็มรูปแบบสำหรับการใช้งานเชิงพาณิชย์
### ถาม: ฉันจะขอความช่วยเหลือหรือสนับสนุน Aspose.Tasks for .NET ได้ที่ไหน
 ตอบ: หากมีข้อสงสัยหรือความช่วยเหลือเกี่ยวกับ Aspose.Tasks สำหรับ .NET คุณสามารถไปที่ฟอรัมสนับสนุนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## ซอร์สโค้ดที่สมบูรณ์
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
