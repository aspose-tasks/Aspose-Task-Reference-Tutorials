---
title: แถบจัดแต่งทรงผมใน Aspose.Tasks
linktitle: แถบจัดแต่งทรงผมใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดสไตล์แท่งใน Aspose.Tasks สำหรับ .NET เพื่อปรับปรุงการแสดงภาพโปรเจ็กต์
weight: 19
url: /th/net/advanced-features/styling-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แถบจัดแต่งทรงผมใน Aspose.Tasks

## การแนะนำ

แถบจัดแต่งทรงผมใน Aspose.Tasks เป็นส่วนสำคัญในการสร้างแผนโครงการที่ดึงดูดสายตา ด้วยความยืดหยุ่นที่นำเสนอโดย Aspose.Tasks API นักพัฒนาจึงสามารถปรับแต่งแถบต่างๆ ในแง่มุมต่างๆ ได้ เช่น สี รูปร่าง และสไตล์ข้อความ เพื่อปรับปรุงการแสดงภาพของโปรเจ็กต์ ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดสไตล์แท่งโดยใช้ Aspose.Tasks สำหรับ .NET โดยแจกแจงแต่ละตัวอย่างออกเป็นขั้นตอนที่สามารถจัดการได้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาด้วยการสนับสนุนกรอบงาน .NET
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการของ Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## ขั้นตอนที่ 1: โหลดโครงการ

ในการเริ่มต้น ให้โหลดไฟล์โปรเจ็กต์โดยใช้ Aspose.Tasks API:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการบันทึก

กำหนดตัวเลือกการบันทึก โดยระบุสไตล์แท่งที่จะใช้:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## ขั้นตอนที่ 3: กำหนดสไตล์บาร์

สร้างสไตล์แท่งใหม่และปรับแต่งคุณสมบัติ:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // ตั้งค่าประเภทรายการแถบ
style.BarColor = Color.Green; // ตั้งค่าสีแถบ
style.BarShape = BarShape.HalfHeight; // ตั้งรูปทรงแท่ง
style.StartShape = Shape.LeftBracket; // วางรูปทรงไว้ที่จุดเริ่มต้นของแถบ
style.StartShapeColor = Color.Aqua; // กำหนดสีของรูปร่างเริ่มต้น
style.EndShape = Shape.RightBracket; // วางรูปทรงไว้ที่ปลายแท่ง
style.EndShapeColor = Color.Aquamarine; // กำหนดสีของรูปทรงส่วนท้าย
style.TextStyle = new TextStyle(); // ตั้งค่ารูปแบบข้อความ
style.TextStyle.BackgroundColor = Color.Black; // กำหนดสีพื้นหลังให้กับข้อความ
```

## ขั้นตอนที่ 4: ปรับแต่งตัวแปลงข้อความ

หรือปรับแต่งตัวแปลงข้อความเพื่อแก้ไขการแสดงข้อความ:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## ขั้นตอนที่ 5: เพิ่มสไตล์บาร์ให้กับตัวเลือก

เพิ่มสไตล์แถบที่กำหนดค่าให้กับตัวเลือกการบันทึก:

```csharp
options.BarStyles.Add(style);
```

## ขั้นตอนที่ 6: บันทึกโครงการ

สุดท้าย ให้บันทึกโปรเจ็กต์ด้วยสไตล์แถบที่ใช้:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## บทสรุป

การปรับแต่งสไตล์แท่งใน Aspose.Tasks สำหรับ .NET ช่วยให้นักพัฒนาสามารถสร้างแผนโครงการที่ดึงดูดสายตาได้ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดสไตล์แถบได้อย่างมีประสิทธิภาพเพื่อให้ตรงตามข้อกำหนดการแสดงภาพโปรเจ็กต์เฉพาะ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้สไตล์แท่งหลายแบบกับโปรเจ็กต์เดียวได้หรือไม่

A1: ได้ คุณสามารถกำหนดและนำสไตล์แท่งหลายแบบไปใช้กับงานประเภทต่างๆ ภายในโปรเจ็กต์เดียวกันได้
   
### คำถามที่ 2: เป็นไปได้หรือไม่ที่จะเปลี่ยนสไตล์แถบแบบไดนามิกระหว่างรันไทม์

ตอบ 2: ได้ คุณสามารถปรับเปลี่ยนสไตล์แท่งแบบไดนามิกตามเงื่อนไขหรือการตั้งค่าของผู้ใช้ภายในแอปพลิเคชันของคุณได้
   
### คำถามที่ 3: Aspose.Tasks รองรับการส่งออกโปรเจ็กต์ที่มีแถบสไตล์ไปเป็นไฟล์รูปแบบต่างๆ หรือไม่

ตอบ 3: ใช่ Aspose.Tasks รองรับการส่งออกโปรเจ็กต์ที่มีแถบสไตล์เป็นรูปแบบต่างๆ เช่น PDF, XLSX และ HTML
   
### คำถามที่ 4: Aspose.Tasks มีรูปแบบแท่งที่กำหนดไว้ล่วงหน้าหรือไม่

ตอบ 4: แม้ว่า Aspose.Tasks จะมีสไตล์แถบเริ่มต้น แต่นักพัฒนาก็สามารถสร้างสไตล์แถบแบบกำหนดเองที่ปรับแต่งตามความต้องการของโปรเจ็กต์ของตนได้
   
### คำถามที่ 5: ฉันสามารถดึงข้อมูลและแก้ไขสไตล์แท่งที่มีอยู่ภายในโปรเจ็กต์โดยใช้ API ได้หรือไม่

A5: ได้ คุณสามารถดึงข้อมูลและแก้ไขสไตล์แท่งที่มีอยู่โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ .NET API
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
