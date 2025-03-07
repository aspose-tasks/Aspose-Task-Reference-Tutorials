---
title: การเรียนรู้ค่าโครงร่างโครงการ MS ด้วย Aspose.Tasks
linktitle: การจัดการค่าเค้าร่างใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการค่าเค้าร่างของ MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET ปรับแต่งโครงร่างโครงการได้อย่างง่ายดาย
weight: 16
url: /th/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้ค่าโครงร่างโครงการ MS ด้วย Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการค่าโครงร่างของ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ .NET ด้วย Aspose.Tasks คุณสามารถจัดการโค้ดโครงร่าง สร้างค่าโครงร่างใหม่ และปรับแต่งโครงร่างโปรเจ็กต์ตามความต้องการของคุณได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา เช่น Visual Studio ที่เข้ากันได้กับเฟรมเวิร์ก .NET
3. ความเข้าใจพื้นฐานของการเขียนโปรแกรม C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C# เนื่องจากเราจะใช้ C# เพื่อทำงานกับไลบรารี Aspose.Tasks

## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
ขั้นตอนนี้จะเริ่มต้นวัตถุโครงการใหม่และโหลดไฟล์โครงการ Microsoft จากไดเรกทอรีที่ระบุ
## ขั้นตอนที่ 2: กำหนดคำจำกัดความของโค้ดโครงร่าง
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
ที่นี่ เรากำหนดออบเจ็กต์ OutlineCodeDefinition สองรายการ และเพิ่มลงในคอลเลกชัน OutlineCodes ของโปรเจ็กต์
## ขั้นตอนที่ 3: กำหนด Outline Mask
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
ขั้นตอนนี้ตั้งค่า OutlineMask สำหรับคำจำกัดความของโค้ดโครงร่าง
## ขั้นตอนที่ 4: สร้างค่าเค้าร่าง
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
ในขั้นตอนนี้ เราสร้างออบเจ็กต์ OutlineValue สองรายการ และตั้งค่าคุณสมบัติ เช่น ค่า รหัสค่า ประเภท คำอธิบาย และสถานะการล่มสลาย

## บทสรุป
การจัดการค่าเค้าร่างของ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET นั้นตรงไปตรงมาด้วยฟังก์ชันที่ให้มา ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการโค้ดและค่าโครงร่างได้อย่างมีประสิทธิภาพ เพื่อปรับแต่งโครงร่างโปรเจ็กต์ตามความต้องการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ตอบ: ได้ Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET ที่หลากหลาย จึงรับประกันความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ
### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึง Aspose.Tasks เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: สำหรับการสนับสนุนและความช่วยเหลือ คุณสามารถไปที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้หรือไม่
ตอบ: ได้ คุณสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถดูเอกสารประกอบที่มีอยู่ได้[ที่นี่](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
