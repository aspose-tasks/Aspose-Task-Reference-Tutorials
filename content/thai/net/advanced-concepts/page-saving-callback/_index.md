---
title: การใช้ Page Saving Callback ใน Aspose.Tasks
linktitle: การใช้ Page Saving Callback ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีใช้การโทรกลับการบันทึกเพจใน Aspose.Tasks สำหรับ .NET ช่วยให้สามารถจัดการสตรีมเอาท์พุตเอกสารหลายเพจแบบกำหนดเองได้
type: docs
weight: 12
url: /th/net/advanced-concepts/page-saving-callback/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการใช้การโทรกลับเพื่อบันทึกหน้าใน Aspose.Tasks สำหรับ .NET คุณลักษณะนี้ช่วยให้เราสามารถบันทึกเอกสารหลายหน้าลงในสตรีมที่ผู้ใช้จัดเตรียมไว้ ซึ่งให้ความยืดหยุ่นและการปรับแต่งในการจัดการเอาต์พุต

## ข้อกำหนดเบื้องต้น:

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ความรู้เกี่ยวกับภาษาการเขียนโปรแกรม C#: คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับไวยากรณ์และแนวคิดของ C#
   
2.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

3. การตั้งค่าสภาพแวดล้อมการพัฒนา: ตั้งค่า IDE ที่คุณต้องการสำหรับการพัฒนา .NET เช่น Visual Studio

## นำเข้าเนมสเปซ:

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;

```

## ขั้นตอนที่ 1: สร้างวัตถุโครงการ

 ยกตัวอย่าง`Project` วัตถุโดยการโหลดไฟล์โครงการที่มีอยู่:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการบันทึกรูปภาพ

 กำหนด`ImageSaveOptions`และปรับแต่งพฤติกรรมการบันทึกหน้าโดยการตั้งค่า`PageSavingCallback` คุณสมบัติ:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

## ขั้นตอนที่ 3: บันทึกโครงการด้วยการโทรกลับ

บันทึกโปรเจ็กต์โดยใช้ตัวเลือกการบันทึกรูปภาพที่กำหนดค่าไว้:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## ขั้นตอนที่ 4: ประมวลผลสตรีมเพจที่บันทึกไว้

วนซ้ำสตรีมเพจที่ได้รับจากการโทรกลับเพื่อประมวลผลแต่ละเพจแยกกัน:

```csharp
foreach (var stream in callback.PageStreams)
{
    // ประมวลผลสตรีมแต่ละหน้า
}
```

## ขั้นตอนที่ 5: ใช้การโทรกลับการบันทึกเพจแบบกำหนดเอง

 สร้างคลาสที่ใช้`IPageSavingCallback` อินเทอร์เฟซสำหรับจัดการการบันทึกหน้า:

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // ดำเนินการล้างข้อมูลหรือการสรุปผล
    }
}
```

## บทสรุป:

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้งานการโทรกลับเพื่อบันทึกหน้าใน Aspose.Tasks สำหรับ .NET ซึ่งช่วยให้เราสามารถบันทึกเอกสารหลายหน้าเพื่อแยกสตรีมได้ ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับปรุงฟังก์ชันการทำงานของแอปพลิเคชันของคุณและบรรลุการจัดการเอาต์พุตแบบกำหนดเองได้

## คำถามที่พบบ่อย

### คำถามที่ 1: การโทรกลับเพื่อบันทึกหน้าใน Aspose.Tasks คืออะไร

A1: การเรียกกลับการบันทึกหน้าเป็นคุณลักษณะใน Aspose.Tasks ที่ช่วยให้ผู้ใช้ปรับแต่งกระบวนการบันทึกของเอกสารหลายหน้าโดยการจัดเตรียมสตรีมสำหรับแต่ละหน้าแยกกัน

### คำถามที่ 2: ฉันสามารถใช้รูปแบบอื่นในการบันทึกเพจโดยใช้การโทรกลับนี้ได้หรือไม่

ตอบ 2: ได้ คุณสามารถใช้รูปแบบไฟล์ต่างๆ ที่ Aspose.Tasks รองรับ เช่น PNG, JPEG, PDF ฯลฯ เพื่อบันทึกเพจที่มีการติดต่อกลับ

### คำถามที่ 3: Aspose.Tasks เข้ากันได้กับ .NET Core หรือไม่

ตอบ 3: ใช่ Aspose.Tasks รองรับ .NET Core ซึ่งช่วยให้นักพัฒนาสามารถใช้คุณสมบัติต่างๆ ในแอปพลิเคชันข้ามแพลตฟอร์มได้

### คำถามที่ 4: ฉันจะจัดการกับข้อผิดพลาดระหว่างขั้นตอนการบันทึกหน้าได้อย่างไร

A4: คุณสามารถใช้กลไกการจัดการข้อผิดพลาดภายในวิธีการโทรกลับเพื่อจัดการข้อยกเว้นและรับรองความแข็งแกร่งในแอปพลิเคชันของคุณ

### คำถามที่ 5: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน

 A5: คุณสามารถเยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือเข้าถึงเอกสาร[ที่นี่](https://reference.aspose.com/tasks/net/) หรือสำรวจคุณสมบัติเพิ่มเติมและตัวเลือกสิทธิ์การใช้งานบน[เว็บไซต์ Aspose.Tasks](https://purchase.aspose.com/buy).