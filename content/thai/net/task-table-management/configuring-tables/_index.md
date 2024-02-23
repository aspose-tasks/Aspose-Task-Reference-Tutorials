---
title: การกำหนดค่าตารางหลักใน Aspose.Tasks สำหรับ .NET
linktitle: กำหนดค่าตารางใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่าตารางใน Aspose.Tasks สำหรับ .NET ด้วยคำแนะนำทีละขั้นตอนนี้ ยกระดับประสบการณ์การจัดการโครงการของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/task-table-management/configuring-tables/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการกำหนดค่าตารางใน Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการกำหนดค่าตารางโดยใช้ Aspose.Tasks โดยแจกแจงแต่ละขั้นตอนเพื่อความเข้าใจที่ชัดเจน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks แล้ว คุณสามารถดาวน์โหลดได้จาก[เอกสาร Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Visual Studio หรือเครื่องมือพัฒนา .NET ที่ต้องการอื่นๆ
- ไฟล์โครงการตัวอย่าง: เตรียมไฟล์ Microsoft Project (MPP) ตัวอย่างให้พร้อมสำหรับการทดสอบ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Tasks เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของโค้ดของคุณ:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
    using System;
    using System.Collections.Generic;
    
    using Aspose.Tasks.Saving;
```
ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนกัน
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## ขั้นตอนที่ 3: เข้าถึงตารางสำหรับการแก้ไข
```csharp
var table = project.Tables.ToList()[0];
Console.WriteLine("Uid of the table: " + table.Uid);
Console.WriteLine("Index of the table: " + table.Index);
Console.WriteLine("Name of the table: " + table.Name);
Console.WriteLine("Type of the table: " + table.TableType);
```
## ขั้นตอนที่ 4: ปรับแต่งคุณสมบัติของตาราง
```csharp
table.AdjustHeaderRowHeight = true;
table.DateFormat = DateFormat.DateDdMmYyyy;
table.LockFirstColumn = true;
table.RowHeight = 10;
table.ShowAddNewColumn = true;
table.ShowInMenu = true;
```
## ขั้นตอนที่ 5: บันทึกตารางที่อัปเดต
```csharp
project.Save(DataDir + "WorkWithTable_out.mpp", SaveFileFormat.Mpp);
```
## บทสรุป
ยินดีด้วย! คุณได้กำหนดค่าตารางใน Aspose.Tasks for .NET เรียบร้อยแล้ว บทช่วยสอนนี้ครอบคลุมขั้นตอนสำคัญในการแก้ไขคุณสมบัติของตารางและบันทึกการเปลี่ยนแปลงในไฟล์โปรเจ็กต์ใหม่
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks โดยไม่มีใบอนุญาตได้หรือไม่
 ตอบ: ได้ แต่คุณสมบัติบางอย่างจำเป็นต้องมี Aspose License ที่ถูกต้อง คุณสามารถรับใบอนุญาตชั่วคราว 30 วัน[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ
### ถาม: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 ตอบ: โปรดดูที่[เอกสาร Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/) สำหรับข้อมูลโดยละเอียด
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ตอบ: ได้ คุณสามารถสำรวจเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะซื้อ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถซื้อใบอนุญาตแบบเต็มได้[ที่นี่](https://purchase.aspose.com/buy).