---
title: การใช้ Tree Algorithm ใน Aspose.Tasks
linktitle: การใช้ Tree Algorithm ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการลำดับชั้นของงานในโครงการ .NET ของคุณอย่างมีประสิทธิภาพโดยใช้อัลกอริทึมแผนผังของ Aspose.Tasks
type: docs
weight: 13
url: /th/net/advanced-concepts/tree-algorithm/
---
## การแนะนำ

Aspose.Tasks สำหรับ .NET มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการทำงานกับงานการจัดการโครงการ ทรัพยากร และกำหนดการ คุณสมบัติอย่างหนึ่งคือ Tree Algorithm ซึ่งช่วยให้ผู้ใช้สามารถจัดการลำดับชั้นของงานได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้อัลกอริทึมแบบทรีใน Aspose.Tasks สำหรับ .NET เพื่อรวบรวมงานทั่วไปและอัปเดตค่างานภายในโปรเจ็กต์

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของ C#: ต้องมีความคุ้นเคยกับภาษาการเขียนโปรแกรม C# ควบคู่ไปกับตัวอย่าง

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับฟังก์ชัน Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 โหลดไฟล์โครงการลงในหน่วยความจำโดยใช้ไฟล์`Project` ระดับ.

## ขั้นตอนที่ 2: กำหนดลำดับชั้นของงาน

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

กำหนดลำดับชั้นของงานโดยการเพิ่มงานหลักและงานรอง

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติของงาน

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

ตั้งค่าคุณสมบัติ เช่น วันที่เริ่มต้น ระยะเวลา และวันที่เสร็จสิ้นสำหรับงาน

## ขั้นตอนที่ 4: เพิ่มทรัพยากร

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

เพิ่มทรัพยากรให้กับโครงการและมอบหมายงานตามความจำเป็น

## ขั้นตอนที่ 5: ใช้อัลกอริทึมแบบต้นไม้

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 เริ่มต้น`WorkAccumulator` และใช้ Tree Algorithm เพื่อรวบรวมงานทั่วไป

## ขั้นตอนที่ 6: อัปเดตงาน

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

อัพเดตค่างานสำหรับงานตามข้อมูลที่รวบรวม

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Tree Algorithm ใน Aspose.Tasks สำหรับ .NET เพื่อจัดการลำดับชั้นของงานอย่างมีประสิทธิภาพ ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถจัดการงานและทรัพยากรภายในโครงการของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สำหรับ .NET คืออะไร

คำตอบ 1: Aspose.Tasks สำหรับ .NET เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรมโดยใช้ C#

### คำถามที่ 2: ฉันสามารถดาวน์โหลด Aspose.Tasks สำหรับ .NET รุ่นทดลองใช้ฟรีได้หรือไม่

 ตอบ 2: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks for .NET รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ไหน

 A3: คุณสามารถค้นหาเอกสารประกอบสำหรับ Aspose.Tasks สำหรับ .NET ได้[ที่นี่](https://reference.aspose.com/tasks/net/).

### คำถามที่ 4: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร

 A4: สำหรับการสนับสนุนที่เกี่ยวข้องกับ Aspose.Tasks สำหรับ .NET คุณสามารถไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### คำถามที่ 5: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่

 A5: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).