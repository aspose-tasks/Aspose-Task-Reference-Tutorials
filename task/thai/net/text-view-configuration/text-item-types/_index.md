---
title: คู่มือการปรับแต่งประเภทรายการข้อความใน Aspose.Tasks
linktitle: การจัดการประเภทรายการข้อความใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: การปรับแต่งประเภทรายการข้อความหลักใน Aspose.Tasks สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้ ยกระดับเกมการจัดการโครงการของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/text-view-configuration/text-item-types/
---
## การแนะนำ
หากคุณเป็นนักพัฒนา .NET ที่เจาะลึกเรื่องการจัดการโครงการโดยใช้ Aspose.Tasks คุณมาถูกที่แล้ว! ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจความซับซ้อนของการจัดการประเภทรายการข้อความใน Aspose.Tasks โดยเน้นที่การปรับแต่งโดยใช้ไลบรารี .NET อันทรงพลัง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks แล้ว ถ้าไม่คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีสำหรับเอกสารโครงการของคุณ
ตอนนี้ เรามาเจาะลึกสาระสำคัญของการจัดการประเภทรายการข้อความกันดีกว่า
## นำเข้าเนมสเปซ
ก่อนอื่น ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มต้นโปรเจ็กต์ของคุณ:
```csharp
    using Aspose.Tasks;
    using System.Collections.Generic;
    using System.Drawing;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
```csharp
String DataDir = "Your Document Directory";
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังเอกสารโครงการของคุณ
## ขั้นตอนที่ 2: โหลดโปรเจ็กต์และปรับแต่ง
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
โหลดไฟล์โครงการของคุณ (ในกรณีนี้คือ "CreateProject2.mpp") โดยใช้ไลบรารี Aspose.Tasks
## ขั้นตอนที่ 3: บันทึกตัวเลือกและรูปแบบการนำเสนอ
```csharp
SaveOptions options = new PdfSaveOptions
{
    PresentationFormat = PresentationFormat.ResourceSheet
};
```
กำหนดตัวเลือกการบันทึก และตั้งค่ารูปแบบการนำเสนอเป็นแผ่นทรัพยากรเพื่อการปรับแต่ง
## ขั้นตอนที่ 4: ปรับแต่งสไตล์ข้อความ
```csharp
var style = new TextStyle(FontStyles.Italic | FontStyles.Bold)
{
    Color = Color.OrangeRed
};
style.ItemType = TextItemType.OverallocatedResources;
```
สร้างสไตล์ข้อความด้วยสไตล์ฟอนต์ สี และตั้งค่าประเภทรายการเป็นทรัพยากรที่จัดสรรไว้โดยรวม
## ขั้นตอนที่ 5: ใช้สไตล์ข้อความและบันทึก
```csharp
options.TextStyles = new List<TextStyle>
{
    style
};
project.Save(DataDir + "CustomizeTextStyle_out.pdf", options);
```
ใช้สไตล์ข้อความที่กำหนดกับโปรเจ็กต์ของคุณและบันทึกโปรเจ็กต์ที่ปรับแต่งเป็นไฟล์ PDF
ทำซ้ำขั้นตอนเหล่านี้สำหรับความต้องการในการปรับแต่งอื่นๆ โดยทดลองใช้ประเภทรายการข้อความ สไตล์แบบอักษร และสีต่างๆ
## บทสรุป
ยินดีด้วย! คุณเพิ่งเริ่มต้นการจัดการประเภทรายการข้อความใน Aspose.Tasks สำหรับ .NET ขณะที่คุณสำรวจต่อ โปรดดูที่[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) เพื่อข้อมูลเชิงลึก
### คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks ได้ฟรีหรือไม่
 ตอบ: Aspose.Tasks ให้ทดลองใช้ฟรี คว้ามัน[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: เยี่ยมชม Aspose.Tasks[ฟอรั่ม](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือจากผู้เชี่ยวชาญ
### ถาม: ฉันจะได้รับใบอนุญาตชั่วคราวได้อย่างไร
 ตอบ: ขอรับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: มีบทช่วยสอนแบบทีละขั้นตอนสำหรับคุณสมบัติอื่นๆ หรือไม่
ตอบ: สำรวจบทช่วยสอนเพิ่มเติมในเอกสารประกอบของ Aspose.Tasks
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 ตอบ: ซื้อห้องสมุด[ที่นี่](https://purchase.aspose.com/buy).