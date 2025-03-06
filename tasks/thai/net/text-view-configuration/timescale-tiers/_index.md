---
title: การกำหนดค่าระดับไทม์สเกลแผนภูมิแกนต์ใน Aspose.Tasks
linktitle: การกำหนดค่าระดับไทม์สเกลใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจ Aspose.Tasks สำหรับ .NET เพื่อกำหนดค่าระดับมาตราส่วนเวลาในมุมมองแผนภูมิ Gantt ของคุณเพื่อการแสดงภาพไทม์ไลน์ของโปรเจ็กต์ที่แม่นยำ #Aspose.Tasks #โครงการ MS
type: docs
weight: 16
url: /th/net/text-view-configuration/timescale-tiers/
---
## การแนะนำ
ในภูมิทัศน์แบบไดนามิกของการจัดการโครงการ การแสดงภาพที่มีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับการทำความเข้าใจลำดับเวลาและกำหนดเวลา Aspose.Tasks สำหรับ .NET มีชุดเครื่องมือที่มีประสิทธิภาพ และในบทช่วยสอนนี้ เราจะสำรวจวิธีกำหนดค่าระดับมาตราส่วนเวลาเพื่อการนำเสนอที่ดีที่สุดในมุมมองแผนภูมิแกนต์ ทำตามคำแนะนำทีละขั้นตอนเหล่านี้เพื่อปรับปรุงการแสดงภาพโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับ C# และ .NET
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าไว้สำหรับการพัฒนาแอปพลิเคชัน .NET
## นำเข้าเนมสเปซ
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
ตอนนี้ เรามาดูรายละเอียดแต่ละขั้นตอนของตัวอย่างที่ให้ไว้กัน
## ขั้นตอนที่ 1: เริ่มต้นโครงการและเพิ่มลิงค์งาน
```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
ที่นี่ เราสร้างโครงการและสร้างการเชื่อมโยงงานระหว่าง "งาน 1" และ "งาน 2"
## ขั้นตอนที่ 2: กำหนดค่ามุมมองแผนภูมิแกนต์
```csharp
var view = (GanttChartView)project.DefaultView;
```
เข้าถึงมุมมองแผนภูมิแกนต์เพื่อปรับแต่ง
## ขั้นตอนที่ 3: ปรับแต่ง Middle Timescale Tier
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
ปรับแต่งระดับมาตราส่วนเวลากลางเพื่อแสดงสัปดาห์ด้วยป้ายกำกับและการจัดตำแหน่งที่เฉพาะเจาะจง
## ขั้นตอนที่ 4: เพิ่มระดับไทม์สเกลสูงสุด
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
เพิ่มระดับมาตราส่วนเวลาสูงสุดเพื่อแสดงเดือน
## ขั้นตอนที่ 5: ปรับแต่งวันที่ระดับกลาง
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
ปรับแต่งป้ายกำกับเดือนเพื่อให้เห็นภาพได้ดีขึ้น
## ขั้นตอนที่ 6: กำหนดมาตราส่วนเวลาของโครงการ
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
กำหนดมาตราส่วนเวลาของโครงการเพื่อควบคุมไทม์ไลน์โดยรวม
## ขั้นตอนที่ 7: บันทึกโครงการด้วยมาตราส่วนเวลาที่กำหนดเอง
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
บันทึกโครงการด้วยการตั้งค่ามาตราส่วนเวลาที่กำหนด
## บทสรุป
โดยสรุป การกำหนดค่าระดับมาตราส่วนเวลาใน Aspose.Tasks สำหรับ .NET ช่วยให้นำเสนอไทม์ไลน์ของโครงการที่มีการปรับแต่งและดึงดูดสายตาได้มากขึ้น ขั้นตอนเหล่านี้ช่วยให้คุณสร้างมุมมองแผนภูมิแกนต์ที่ตรงกับความต้องการในการจัดการโครงการของคุณได้อย่างแม่นยำ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks กับไลบรารี .NET อื่นได้หรือไม่
ใช่ Aspose.Tasks ทำงานร่วมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น โดยให้ความยืดหยุ่นในสแต็กการพัฒนาของคุณ
### มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล
### มีตัวเลือกการปรับแต่งเพิ่มเติมสำหรับมุมมองแผนภูมิแกนต์หรือไม่
แน่นอน Aspose.Tasks มีตัวเลือกการปรับแต่งที่ครอบคลุมสำหรับมุมมองแผนภูมิแกนต์เพื่อให้เหมาะกับความต้องการของโครงการที่หลากหลาย
### ฉันสามารถแสดงมาตราส่วนเวลาในรูปแบบที่แตกต่างกันได้หรือไม่
แน่นอน คุณสามารถสำรวจรูปแบบและสไตล์ที่หลากหลายสำหรับการแสดงมาตราส่วนเวลาเพื่อให้เหมาะกับบริบทของโปรเจ็กต์ของคุณมากที่สุด
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ใช่แล้ว แวะมาที่.[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน