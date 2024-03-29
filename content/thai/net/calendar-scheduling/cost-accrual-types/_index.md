---
title: ประเภทการรับรู้ต้นทุนใน Aspose.Tasks
linktitle: ประเภทการรับรู้ต้นทุนใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการต้นทุนโครงการอย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ .NET กำหนดประเภทการรับรู้ต้นทุนเพื่อการติดตามงบประมาณที่แม่นยำ
type: docs
weight: 19
url: /th/net/calendar-scheduling/cost-accrual-types/
---
## การแนะนำ

ในการจัดการโครงการ การติดตามต้นทุนอย่างแม่นยำถือเป็นสิ่งสำคัญในการรักษาการควบคุมงบประมาณและรับรองความสำเร็จของโครงการ Aspose.Tasks for .NET นำเสนอชุดเครื่องมือที่มีประสิทธิภาพสำหรับการจัดการต้นทุนโครงการ รวมถึงความสามารถในการกำหนดประเภทการรับรู้ต้นทุนที่แตกต่างกัน บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทำความเข้าใจและการใช้งานประเภทการรับรู้ต้นทุนโดยใช้ Aspose.Tasks สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET

 ในการเริ่มต้น คุณต้องติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/net/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้

### 2. ความคุ้นเคยกับ .NET Framework

จำเป็นต้องปฏิบัติตามความรู้พื้นฐานของกรอบงาน .NET และภาษาการเขียนโปรแกรม C# พร้อมด้วยตัวอย่างในบทช่วยสอนนี้

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Tasks ในโปรเจ็กต์ .NET ของเรา:

```csharp

```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นและนำเข้าเนมสเปซที่จำเป็นแล้ว เรามาดูรายละเอียดแต่ละตัวอย่างออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project("Project2.mpp");
```

 ก่อนอื่น เราต้องโหลดไฟล์โปรเจ็กต์ลงในแอปพลิเคชันของเรา เราสร้างใหม่`Project` object และเริ่มต้นด้วยเส้นทางไปยังไฟล์โครงการของเรา

## ขั้นตอนที่ 2: เข้าถึงทรัพยากร

```csharp
var resource = project.Resources.GetById(1);
```

 ต่อไป เราเข้าถึงทรัพยากรที่เราต้องการใช้ประเภทการรับรู้ต้นทุน เราใช้`GetById` วิธีการของ`Resources` รวบรวมและส่งรหัสทรัพยากรเป็นอาร์กิวเมนต์

## ขั้นตอนที่ 3: ตั้งค่าประเภทการรับรู้ต้นทุน

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

ที่นี่ เราตั้งค่าประเภทการรับรู้ต้นทุนสำหรับทรัพยากร ในตัวอย่างนี้ เรากำลังตั้งค่าเป็น`CostAccrualType.End`ซึ่งหมายความว่าต้นทุนจะไม่เกิดขึ้นจนกว่างานที่เหลืออยู่จะเป็นศูนย์

## ขั้นตอนที่ 4: ทำงานกับโครงการ

หลังจากตั้งค่าชนิดการรับรู้ต้นทุน คุณสามารถทำงานกับโครงการต่อไปได้ตามต้องการ โดยดำเนินการหรือการคำนวณเพิ่มเติม

## บทสรุป

การทำความเข้าใจและการนำประเภทการรับรู้ต้นทุนไปใช้เป็นสิ่งจำเป็นสำหรับการจัดการต้นทุนโครงการอย่างมีประสิทธิภาพ ด้วย Aspose.Tasks สำหรับ .NET คุณสามารถกำหนดและปรับแต่งประเภทการคงค้างต้นทุนตามความต้องการของโปรเจ็กต์ของคุณได้อย่างง่ายดาย ช่วยให้มั่นใจในการติดตามต้นทุนและการควบคุมงบประมาณที่แม่นยำตลอดวงจรชีวิตของโปรเจ็กต์

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถเปลี่ยนประเภทการรับรู้ต้นทุนสำหรับทรัพยากรหลายรายการพร้อมกันได้หรือไม่

A1: ใช่ คุณสามารถวนซ้ำการรวบรวมทรัพยากรและตั้งค่าชนิดการรับรู้ต้นทุนสำหรับแต่ละทรัพยากรทีละรายการได้

### Q2: ประเภทการรับรู้ต้นทุนอื่นๆ ที่พร้อมใช้งานนอกเหนือจาก 'สิ้นสุด' คืออะไร

A2: Aspose.Tasks สำหรับ .NET มีประเภทการรับรู้ต้นทุนอื่นๆ หลายประเภท เช่น`Start`, `Prorated` , และ`Duration`.

### คำถามที่ 3: ฉันจะกำหนดประเภทการรับรู้ต้นทุนปัจจุบันสำหรับทรัพยากรได้อย่างไร

 A3: คุณสามารถดึงข้อมูลชนิดการรับรู้ต้นทุนปัจจุบันได้โดยใช้`Get` วิธีการบนวัตถุทรัพยากร

### คำถามที่ 4: ฉันสามารถใช้ประเภทการรับรู้ต้นทุนที่แตกต่างกันกับงานที่แตกต่างกันภายในโครงการเดียวกันได้หรือไม่

A4: ได้ คุณสามารถตั้งค่าประเภทการรับรู้ต้นทุนได้อย่างอิสระสำหรับแต่ละงานและทรัพยากรในโครงการของคุณ

### คำถามที่ 5: Aspose.Tasks สำหรับ .NET รองรับประเภทการคงค้างต้นทุนแบบกำหนดเองหรือไม่

A5: ในเวอร์ชันล่าสุด Aspose.Tasks สำหรับ .NET ไม่สนับสนุนการกำหนดประเภทการรับรู้ต้นทุนแบบกำหนดเอง