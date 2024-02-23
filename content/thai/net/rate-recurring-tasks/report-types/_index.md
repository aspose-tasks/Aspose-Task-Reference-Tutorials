---
title: การรายงานโครงการ MS หลักด้วย Aspose.Tasks
linktitle: การทำงานกับประเภทรายงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีทำงานกับไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET สร้างรายงานประเภทต่างๆ ได้อย่างง่ายดาย
type: docs
weight: 16
url: /th/net/rate-recurring-tasks/report-types/
---
## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ไม่ว่าคุณจะทำงานเกี่ยวกับการจัดการโครงการ การกำหนดเวลา หรือการรายงานงาน Aspose.Tasks มีชุดคุณสมบัติที่ครอบคลุมเพื่อปรับปรุงขั้นตอนการทำงานของคุณ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับไฟล์ MS Project และสร้างรายงานประเภทต่างๆ โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
### 2. รับใบอนุญาต (ไม่บังคับ)
 หากคุณใช้ Aspose.Tasks ในโครงการเชิงพาณิชย์ คุณจะต้องมีใบอนุญาต คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy) หรือคุณสามารถขอใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### 3. ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มใช้ Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System.IO;

using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ MS
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + @"Homemoveplan.mpp");
```
## ขั้นตอนที่ 2: บันทึกรายงาน
```csharp
using Aspose.Tasks;
using (var stream = new FileStream(OutDir + "Burndown_out.pdf", FileMode.Create))
{
    project.SaveReport(stream, ReportType.Burndown);
}
```

## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ .NET เป็นไลบรารีอเนกประสงค์สำหรับการทำงานกับไฟล์ MS Project ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถโหลดไฟล์ MS Project และสร้างรายงานประเภทต่างๆ ได้อย่างง่ายดายโดยใช้ความพยายามเพียงเล็กน้อย ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นด้วยการพัฒนา .NET Aspose.Tasks ช่วยให้คุณสามารถจัดการงานการจัดการโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET ในโครงการเชิงพาณิชย์ได้หรือไม่
ตอบ: ได้ คุณสามารถใช้ Aspose.Tasks สำหรับ .NET ในโครงการเชิงพาณิชย์ได้ แต่คุณจะต้องซื้อใบอนุญาต
### คำถามที่ 2: มีการทดลองใช้ฟรีหรือไม่?
 ตอบ: ได้ คุณสามารถขอใบอนุญาตทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/tasks/net/).
### คำถามที่ 3: ฉันจะหาเอกสารสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/net/).
### คำถามที่ 4: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: คุณสามารถรับการสนับสนุนจากชุมชนได้[ที่นี่](https://forum.aspose.com/c/tasks/15).
### คำถามที่ 5: ฉันจะดาวน์โหลด Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: คุณสามารถดาวน์โหลด Aspose.Tasks สำหรับ .NET ได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).