---
title: บันทึกไฟล์โครงการ MS ในรูปแบบต่าง ๆ ใน Aspose.Tasks
linktitle: การบันทึกไฟล์ในรูปแบบต่างๆ ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีบันทึกไฟล์ MS Project ในรูปแบบต่างๆ โดยใช้ Aspose.Tasks สำหรับ .NET ขั้นตอนง่ายๆ สำหรับการจัดการโครงการอย่างมีประสิทธิภาพ
type: docs
weight: 17
url: /th/net/rate-recurring-tasks/save-file-formats/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกไฟล์ Microsoft Project ในรูปแบบต่างๆ โดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาจัดการและจัดการไฟล์โปรเจ็กต์โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นที่จุดเริ่มต้นของไฟล์ C# ของคุณ:
```csharp

using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: สร้างวัตถุโครงการ
ขั้นแรก สร้างออบเจ็กต์ Project และโหลดไฟล์ Microsoft Project ของคุณ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## ขั้นตอนที่ 2: บันทึกโครงการในรูปแบบ CSV
ตอนนี้ มาบันทึกโครงการในรูปแบบ CSV กัน 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## ขั้นตอนที่ 3: สำรวจรูปแบบอื่น ๆ
 Aspose.Tasks รองรับรูปแบบต่างๆ สำหรับการบันทึกไฟล์โปรเจ็กต์ เช่น XML, PDF, XLSX และอื่นๆ คุณสามารถสำรวจรูปแบบเหล่านี้ได้โดยเพียงแค่เปลี่ยน`SaveFileFormat` พารามิเตอร์ใน`Save` วิธี.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถบันทึกไฟล์ Microsoft Project ในรูปแบบต่างๆ ได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ .NET

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกไฟล์ MS Project ในรูปแบบต่างๆ โดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks ลดความซับซ้อนของกระบวนการจัดการไฟล์โปรเจ็กต์โดยทางโปรแกรม ให้ความยืดหยุ่นและประสิทธิภาพแก่นักพัฒนา
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks รองรับรูปแบบ Microsoft Project 2003 XML, Microsoft Project 2007 MPP และ Microsoft Project 2010 MPP
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: Aspose.Tasks มีใบอนุญาตชั่วคราวหรือไม่
 ตอบ: ใช่ ใบอนุญาตชั่วคราวมีไว้เพื่อวัตถุประสงค์ในการประเมิน คุณสามารถได้รับอย่างใดอย่างหนึ่ง[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: Aspose.Tasks มีราคาเท่าใด
 ตอบ: สามารถดูข้อมูลราคาได้ที่หน้าการซื้อ Aspose.Tasks[ที่นี่](https://purchase.aspose.com/buy).