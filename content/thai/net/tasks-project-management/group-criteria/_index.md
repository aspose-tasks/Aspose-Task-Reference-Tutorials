---
title: การจัดการเกณฑ์กลุ่มโครงการ MS ใน Aspose.Tasks
linktitle: เกณฑ์กลุ่มใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจวิธีจัดการไฟล์ MS Project โดยทางโปรแกรมใน .NET โดยใช้ Aspose.Tasks ดึงข้อมูลกลุ่มงานและข้อมูลเกณฑ์ตัวอย่างทีละขั้นตอน
type: docs
weight: 27
url: /th/net/tasks-project-management/group-criteria/
---
## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็น API ที่มีประสิทธิภาพซึ่งอำนวยความสะดวกในการทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน .NET ของคุณ ไม่ว่าคุณกำลังพัฒนาซอฟต์แวร์การจัดการโครงการหรือต้องการจัดการข้อมูลโครงการโดยทางโปรแกรม Aspose.Tasks ก็มีชุดคุณสมบัติที่ครอบคลุมเพื่อตอบสนองความต้องการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ความรู้เกี่ยวกับ C# และ .NET Framework
ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และ .NET Framework เป็นสิ่งสำคัญในการทำความเข้าใจและนำตัวอย่างที่ให้ไว้ในบทช่วยสอนนี้ไปใช้
### 2. การติดตั้ง Aspose.Tasks สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้
### 3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE)
ติดตั้ง IDE เช่น Visual Studio บนระบบของคุณเพื่อเขียนและรันโค้ด C#

## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ Microsoft
ขั้นแรก ให้ระบุเส้นทางไปยังไฟล์ Microsoft Project ของคุณ:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไฟล์โครงการของคุณ
## ขั้นตอนที่ 2: ดึงข้อมูลกลุ่มงาน
ถัดไป ดึงข้อมูลเกี่ยวกับกลุ่มงานในโครงการ:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
ส่วนย่อยโค้ดนี้จะพิมพ์จำนวนทั้งหมดของกลุ่มงาน ดึงข้อมูลกลุ่มงานที่สอง ชื่อของกลุ่มงาน และจำนวนเกณฑ์ที่มีอยู่
## ขั้นตอนที่ 3: ดึงข้อมูลเกณฑ์ของกลุ่มงาน
ตอนนี้ เรามาเจาะลึกรายละเอียดของเกณฑ์เฉพาะภายในกลุ่มงานกัน:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
ส่วนนี้แสดงคุณสมบัติต่างๆ ของเกณฑ์ เช่น ดัชนี ฟิลด์ ข้อมูลการจัดกลุ่ม สีของเซลล์ สีแบบอักษร ช่วงเวลาของกลุ่ม และจุดเริ่มต้น
## ขั้นตอนที่ 4: ดึงข้อมูลแบบอักษรของเกณฑ์
สุดท้าย รับรายละเอียดที่เกี่ยวข้องกับแบบอักษรของเกณฑ์:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
ขั้นตอนนี้จะพิมพ์ชื่อแบบอักษร ขนาด สไตล์ และดูว่าเกณฑ์จะเรียงลำดับจากน้อยไปหามากหรือจากมากไปหาน้อย

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ Aspose.Tasks สำหรับ .NET เพื่อดึงข้อมูลเกี่ยวกับกลุ่มงานและเกณฑ์จากไฟล์ Microsoft Project ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถทำงานกับข้อมูลโครงการโดยทางโปรแกรมในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการไฟล์ Microsoft Project ขนาดใหญ่ได้หรือไม่
Aspose.Tasks ได้รับการปรับให้เหมาะสมเพื่อจัดการไฟล์โปรเจ็กต์ขนาดใหญ่อย่างมีประสิทธิภาพ ทำให้มั่นใจได้ถึงประสิทธิภาพและความน่าเชื่อถือในระดับสูง
### Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่
ใช่ Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้กับไฟล์รูปแบบต่างๆ
### ฉันสามารถจัดการข้อมูลโปรเจ็กต์โดยใช้ Aspose.Tasks ได้หรือไม่
แน่นอนว่า Aspose.Tasks มีฟังก์ชันการทำงานที่ครอบคลุมเพื่อจัดการข้อมูลโครงการ รวมถึงงาน ทรัพยากร ปฏิทิน และอื่นๆ อีกมากมาย
### Aspose.Tasks ให้การสนับสนุนแพลตฟอร์ม .NET ที่แตกต่างกันหรือไม่
ใช่ Aspose.Tasks รองรับแพลตฟอร์ม .NET หลายแพลตฟอร์ม รวมถึง .NET Framework, .NET Core และ .NET Standard
### มีฟอรัมชุมชนสำหรับ Aspose.Tasks ที่ฉันสามารถขอความช่วยเหลือได้หรือไม่?
 ใช่ คุณสามารถเยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อถามคำถาม แบ่งปันความรู้ และทำงานร่วมกับผู้ใช้รายอื่น