---
title: การปรับแต่งสไตล์ Gantt Bar ด้วย Aspose.Tasks
linktitle: สไตล์แกนต์บาร์ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีปรับแต่งสไตล์แท่งแกนต์ใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ปรับปรุงการแสดงภาพโครงการได้อย่างง่ายดาย
type: docs
weight: 20
url: /th/net/tasks-project-management/gantt-bar-styles/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับสไตล์แท่งแกนต์ใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET สไตล์แท่งแกนต์ช่วยให้คุณปรับแต่งลักษณะของแท่งในแผนภูมิแกนต์ได้ ซึ่งช่วยปรับปรุงการแสดงภาพข้อมูลโปรเจ็กต์ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Visual Studio: ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.Linq;
using Aspose.Tasks.Saving;

using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
 เริ่มต้นด้วยการโหลดไฟล์โครงการโดยใช้นามสกุล`Project` ระดับ:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CustomBarStyle.mpp");
```
## ขั้นตอนที่ 2: เข้าถึงมุมมองแผนภูมิแกนต์
จากนั้น เข้าถึงมุมมองแผนภูมิแกนต์ของโปรเจ็กต์:
```csharp
var view = (GanttChartView)project.DefaultView;
```
## ขั้นตอนที่ 3: เข้าถึงสไตล์แถบที่กำหนดเอง
ตอนนี้ เรามาเรียกสไตล์แท่งแบบกำหนดเองจากมุมมองแผนภูมิแกนต์กันดีกว่า:
```csharp
Console.WriteLine("Custom bar styles count: {0}", view.CustomBarStyles.Count);
```
## ขั้นตอนที่ 4: สำรวจสไตล์บาร์
วนซ้ำสไตล์แถบแบบกำหนดเองและดึงคุณสมบัติ:
```csharp
var style1 = view.CustomBarStyles[0];
Console.WriteLine("Style1.ParentStyle Name: {0}", style1.ParentStyle.Name);
Console.WriteLine("Style1.LeftField: {0}", style1.LeftField);
Console.WriteLine("Style1.RightField: {0}", style1.RightField);
// ดำเนินการต่อคุณสมบัติอื่น ๆ ...
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการสไตล์แถบ Gantt ใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการปรับแต่งสไตล์เหล่านี้ คุณสามารถสื่อสารไทม์ไลน์และเหตุการณ์สำคัญของโครงการได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้สไตล์แถบแบบกำหนดเองหลายแบบกับงานต่างๆ ในโปรเจ็กต์ของฉันได้หรือไม่
ตอบ: ได้ คุณสามารถใช้สไตล์แท่งแบบกำหนดเองที่แตกต่างกันกับงานแต่ละงานหรือกลุ่มงานได้ตามความต้องการของโปรเจ็กต์ของคุณ
### ถาม: การเปลี่ยนแปลงสไตล์แท่งจะสะท้อนให้เห็นในไฟล์ MS Project ต้นฉบับหรือไม่
ตอบ: ไม่ การเปลี่ยนแปลงที่ทำโดยทางโปรแกรมโดยใช้ Aspose.Task จะไม่สะท้อนให้เห็นโดยตรงในไฟล์ MS Project ดั้งเดิม เว้นแต่จะได้รับการบันทึกอย่างชัดเจน
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks นำเสนอความเข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงการผสานรวมและฟังก์ชันการทำงานที่ราบรื่น
### ถาม: ฉันสามารถสร้างสไตล์แถบแบบกำหนดเองใหม่โดยใช้โปรแกรม Aspose.Tasks ได้หรือไม่
ตอบ: ได้ คุณสามารถสร้างสไตล์แท่งแบบกำหนดเองใหม่และปรับแต่งคุณสมบัติตามความต้องการของโปรเจ็กต์ของคุณได้โดยใช้ Aspose.Tasks API
### ถาม: Aspose.Tasks รองรับฟังก์ชันการจัดการโครงการอื่นๆ นอกเหนือจากแผนภูมิแกนต์หรือไม่
ตอบ: ใช่ Aspose.Tasks มีชุดคุณสมบัติที่ครอบคลุมสำหรับการทำงานกับข้อมูลการจัดการโครงการ รวมถึงการกำหนดเวลางาน การจัดการทรัพยากร และการวิเคราะห์โครงการ