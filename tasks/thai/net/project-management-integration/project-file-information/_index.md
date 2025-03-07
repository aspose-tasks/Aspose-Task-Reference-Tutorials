---
title: ดึงข้อมูลไฟล์โครงการ MS ใน Aspose.Tasks
linktitle: การดึงข้อมูลไฟล์โครงการใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีดึงข้อมูลไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
weight: 19
url: /th/net/project-management-integration/project-file-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงข้อมูลไฟล์โครงการ MS ใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการดึงข้อมูลไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนา .NET สามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม ช่วยให้สามารถทำงานต่างๆ เช่น การอ่าน การเขียน และการจัดการข้อมูลโครงการ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET: บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และกรอบงาน .NET
2. Visual Studio: ติดตั้ง Visual Studio หรือ IDE อื่น ๆ ที่เข้ากันได้กับการพัฒนา .NET
3.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET Library คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/net/).
4. ไฟล์โครงการ Microsoft: เตรียมไฟล์โครงการ Microsoft (รูปแบบ XML ในตัวอย่างนี้) ให้พร้อมสำหรับการทดสอบ

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณเพื่อทำงานกับ Aspose.Tasks:
## ขั้นตอนที่ 1: นำเข้าเนมสเปซ Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
## การดึงข้อมูลไฟล์โครงการ MS
ตอนนี้ เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 2: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางไปยังไดเร็กทอรีของคุณที่มีไฟล์ MS Project
## ขั้นตอนที่ 3: ดึงข้อมูลไฟล์โครงการ
```csharp
var info = Project.GetProjectFileInfo(dataDir + "Project.xml");
```
 บรรทัดโค้ดนี้ดึงข้อมูลเกี่ยวกับไฟล์โครงการที่ระบุ แทนที่`"Project.xml"` ด้วยชื่อไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 4: แสดงข้อมูลโครงการ
```csharp
Console.WriteLine("CanRead: " + info.CanRead);
Console.WriteLine("ProjectApplicationInfo: " + info.ProjectApplicationInfo);
Console.WriteLine("ProjectFileFormat: " + info.ProjectFileFormat);
```
บรรทัดโค้ดเหล่านี้แสดงข้อมูลต่างๆ เกี่ยวกับไฟล์ MS Project เช่น ความสามารถในการอ่าน ข้อมูลแอปพลิเคชัน และรูปแบบไฟล์

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดึงข้อมูลไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ช่วยให้คุณสามารถทำงานกับไฟล์ MS Project ได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการไฟล์ Microsoft Project เวอร์ชันต่างๆ ได้หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP และ XML
### Aspose.Tasks เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Tasks เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถจัดการข้อมูลโปรเจ็กต์โดยใช้ Aspose.Tasks ได้หรือไม่
แน่นอนว่า Aspose.Tasks มอบความสามารถที่ครอบคลุมสำหรับการอ่าน เขียน และจัดการข้อมูลโปรเจ็กต์โดยทางโปรแกรม
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึง Aspose.Tasks รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Tasks ผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## ซอร์สโค้ดที่สมบูรณ์
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
