---
title: คำจำกัดความการจัดการโค้ดโครงร่างโครงการ MS ใน Aspose.Tasks
linktitle: การจัดการคำจำกัดความโค้ดเค้าร่างใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคำจำกัดความโค้ดโครงร่างของ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เพื่อเพิ่มศักยภาพให้กับแอปพลิเคชันการจัดการโครงการของคุณ
type: docs
weight: 12
url: /th/net/outline-code-page-settings/outline-code-definitions/
---
## การแนะนำ
Microsoft Project เป็นเครื่องมือที่มีประสิทธิภาพสำหรับการจัดการโครงการ และ Aspose.Tasks สำหรับ .NET ให้การสนับสนุนที่ครอบคลุมสำหรับการจัดการไฟล์โครงการโดยทางโปรแกรม สิ่งสำคัญอย่างหนึ่งของการจัดการโครงการคือการจัดระเบียบงานโดยใช้โค้ดโครงร่าง ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการคำจำกัดความของโค้ดเค้าร่างของ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง Aspose.Tasks สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
### 2. ความเข้าใจพื้นฐานเกี่ยวกับ C# และ .NET Framework
ทำความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และเฟรมเวิร์ก .NET เนื่องจากบทช่วยสอนนี้ต้องใช้ความรู้ C# ระดับกลาง
### 3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE)
ติดตั้ง IDE เช่น Visual Studio บนระบบของคุณสำหรับการเขียนโค้ดและการดีบัก
## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มเขียนโค้ด เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Tasks สำหรับ .NET กันก่อน
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ชัดเจน
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก เราต้องโหลดไฟล์ MS Project ลงในแอปพลิเคชันของเรา
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## ขั้นตอนที่ 2: สร้างคำจำกัดความโค้ดโครงร่าง
ตอนนี้ เรามาสร้างคำจำกัดความโค้ดเค้าร่างใหม่กันดีกว่า
```csharp
var outline = new OutlineCodeDefinition();
```
## ขั้นตอนที่ 3: ตั้งค่าหมายเลขฟิลด์และชื่อ
ตั้งค่าหมายเลขฟิลด์และชื่อสำหรับโค้ดโครงร่าง
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## ขั้นตอนที่ 4: ตั้งค่า GUID และคุณสมบัติอื่น ๆ
ตั้งค่า GUID และคุณสมบัติอื่นๆ ของโค้ดโครงร่าง
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## ขั้นตอนที่ 5: เพิ่ม Outline Mask
เพิ่มมาสก์โครงร่างให้กับโค้ดโครงร่าง
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## ขั้นตอนที่ 6: ตั้งค่าคุณสมบัติอื่น ๆ
ตั้งค่าคุณสมบัติเพิ่มเติมของโค้ดโครงร่าง
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## ขั้นตอนที่ 7: เพิ่มมูลค่าเค้าร่าง
สุดท้ายนี้ ให้เพิ่มค่าโครงร่างให้กับโค้ดโครงร่าง
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการคำจำกัดความของโค้ดโครงร่างของ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถจัดการโค้ดเค้าร่างในไฟล์โปรเจ็กต์ของคุณโดยทางโปรแกรมได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับไฟล์ MS Project เวอร์ชันต่างๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับไฟล์ MS Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP และ XML
### คำถามที่ 2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core ทำให้คุณสามารถพัฒนาแอปพลิเคชันข้ามแพลตฟอร์มได้
### คำถามที่ 3: ฉันสามารถจัดการการกำหนดทรัพยากรโดยใช้ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET มีคุณสมบัติมากมายสำหรับการจัดการการมอบหมายทรัพยากร รวมถึงการเพิ่ม อัปเดต และการลบการมอบหมาย
### คำถามที่ 4: Aspose.Tasks สำหรับ .NET รองรับการอ่านฟิลด์แบบกำหนดเองจากไฟล์ MS Project หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ .NET รองรับการอ่านและเขียนฟิลด์แบบกำหนดเอง รวมถึงโค้ดโครงร่าง จากไฟล์ MS Project
### คำถามที่ 5: มีฟอรัมชุมชนสำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ตอบ: ได้ คุณสามารถเข้าร่วมฟอรัมชุมชนสำหรับ Aspose.Tasks สำหรับ .NET ได้[ที่นี่](https://forum.aspose.com/c/tasks/15) เพื่อถามคำถาม แบ่งปันความรู้ และทำงานร่วมกับนักพัฒนารายอื่น