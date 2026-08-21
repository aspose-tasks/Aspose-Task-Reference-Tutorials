---
date: 2026-03-16
description: เรียนรู้วิธีการรวมหลายเงื่อนไขและกรองงานโครงการโดยใช้การดำเนินการ AND
  ขั้นสูงใน Aspose.Tasks สำหรับ .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีรวมหลายเงื่อนไขด้วยการดำเนินการ AND ขั้นสูงใน Aspose.Tasks
url: /th/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การดำเนินการ AND ขั้นสูงใน Aspose.Tasks

## คำแนะนำ

ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีการรวมหลายเงื่อนไข** ด้วย *การดำเนินการ AND ขั้นสูง* ใน Aspose.Tasks สำหรับ .NET. เมื่อจบคู่มือคุณจะสามารถ **กรองงานของโครงการ** ตามหลายเกณฑ์—สิ่งที่จำเป็นเมื่อคุณต้อง **กรองงาน** เช่น รายการสรุป, รายการที่ไม่เป็นค่า null, หรือแฟล็กที่กำหนดเองในหนึ่งครั้ง.

## คำตอบอย่างรวดเร็ว
- **การดำเนินการ AND ขั้นสูงทำอะไร?** มันรวมเงื่อนไขการกรองสองหรือมากกว่าด้วยกันเพื่อให้คืนค่าเฉพาะงานที่ตรงกับ *ทั้งหมด* ของเกณฑ์.  
- **คลาสใดที่รวมเงื่อนไข?** `Util.And<T>` (แสดงเป็น `And<T>` ใน API).  
- **ฉันต้องการใบอนุญาตพิเศษหรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ปกติสำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีให้ใช้.  
- **ฉันสามารถเชื่อมต่อมากก่าสองเงื่อนไขได้หรือไม่?** ได้—`And<T>` ยอมรับจำนวนเงื่อนไขใด ๆ  
- **เวอร์ชันของ .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## “การรวมหลายเงื่อนไข” ใน Aspose.Tasks คืออะไร?

การรวมหลายเงื่อนไขหมายถึงการสร้างตัวกรองเชิงประกอบที่ประเมินงานแต่ละรายการตามหลายกฎพร้อมกัน วิธีนี้มีประสิทธิภาพมากกว่าการวนลูปผ่านรายการงานหลายครั้ง เนื่องจากไลบรารีทำการประมวลผลตรรกะในหนึ่งรอบ.

## ทำไมต้องใช้การดำเนินการ AND ขั้นสูง?

- **ประสิทธิภาพ:** ลดจำนวนรอบการวนผ่านคอลเลกชันของงาน.  
- **ความอ่านง่าย:** ทำให้ตรรกะการกรองเป็นแบบ declarative และง่ายต่อการบำรุงรักษา.  
- **ความยืดหยุ่น:** คุณสามารถผสมเงื่อนไขในตัว (เช่น `SummaryCondition`) กับพรีดิเกตที่กำหนดเอง.  

## ข้อกำหนดเบื้องต้น

1. ความรู้พื้นฐานของการเขียนโปรแกรม C#.  
2. ติดตั้ง Aspose.Tasks for .NET หากคุณยังไม่ได้ดาวน์โหลด ให้รับได้จาก **[here](https://releases.aspose.com/tasks/net/)**.  
3. IDE เช่น Visual Studio (ทุกเวอร์ชันทำงานได้).  

## นำเข้า Namespaces

ก่อนอื่นให้นำเข้า namespaces ที่ให้โมเดลงานและคลาสยูทิลิตี้:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## ขั้นตอนที่ 1: เริ่มต้น Project และเก็บรวบรวมงาน

เราจะสร้างอินสแตนซ์ `Project` และใช้ `ChildTasksCollector` เพื่อรวบรวมงานทุกรายการในไฟล์ นี่เป็นการสาธิต **วิธีการใช้ collector** เพื่อดึงรายการงานแบบแบน.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## ขั้นตอนที่ 2: กำหนดเงื่อนไขการกรอง

ที่นี่เรากำหนดเงื่อนไขแต่ละรายการที่ต้องการใช้ ในตัวอย่างนี้เราจะ **กรองงานสรุป** และยังตรวจสอบให้แน่ใจว่าอ็อบเจ็กต์งานไม่เป็น null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## ขั้นตอนที่ 3: รวมเงื่อนไขด้วยการดำเนินการ AND

ตอนนี้เราจะ **รวมหลายเงื่อนไข** ด้วยคลาส `And<T>` นี่คือหัวใจของ **การดำเนินการ AND ขั้นสูง**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## ขั้นตอนที่ 4: ใช้เงื่อนไขและกรองงาน

เมื่อเงื่อนไขเชิงประกอบพร้อมแล้ว เราจะเรียก `Filter` เพื่อ **กรองงานของโครงการ** ตามตรรกะที่รวมกัน.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## ขั้นตอนที่ 5: แสดงผลงานที่กรองแล้ว

สุดท้าย เราจะแสดงงานที่ตรงกับ **ทั้งหมด** ของเงื่อนไข คุณสามารถแทนที่การเรียก `Console.WriteLine` ด้วยการประมวลผลแบบกำหนดเองที่คุณต้องการ.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้เร็ว |
|-------|----------------|-----------|
| `Filter` method not found | ขาด `using Aspose.Tasks.Util;` | ตรวจสอบให้แน่ใจว่าได้นำเข้า namespace Util (ดูที่นำเข้า Namespaces). |
| ไม่มีงานที่คืนค่า | เงื่อนไขเข้มงวดเกินไป (เช่น กรองงานสรุปเมื่อไม่มีอยู่จริง) | ตรวจสอบว่าโครงการมีงานสรุปจริงหรือปรับเงื่อนไขให้เหมาะสม. |
| NullReferenceException | `coll.Tasks` มีรายการที่เป็น null | `NotNullCondition` ได้ป้องกันกรณีนี้แล้ว; คงไว้ในโซ่ AND. |

## คำถามที่พบบ่อย

### Q1: Aspose.Tasks for .NET คืออะไร?

A: Aspose.Tasks for .NET เป็น API ที่แข็งแกร่งที่ช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project อย่างโปรแกรมมิ่งในแอปพลิเคชัน .NET.

### Q2: ฉันสามารถใช้เงื่อนไขมากกว่าสองอย่างด้วย Util.And ได้หรือไม่?

A: ใช่, Util.And สามารถใช้รวมเงื่อนไขจำนวนใดก็ได้เพื่อสร้างเกณฑ์การกรองที่ซับซ้อน.

### Q3: มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks for .NET หรือไม่?

A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก **[here](https://releases.aspose.com/)**.

### Q4: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้จากที่ไหน?

A: คุณสามารถค้นหาเอกสารได้ที่ **[here](https://reference.aspose.com/tasks/net/)**.

### Q5: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for .NET ได้อย่างไร?

A: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.Tasks **[here](https://forum.aspose.com/c/tasks/15)**.

**คำถามและคำตอบเพิ่มเติม**

**Q: ฉันจะกรองงานตามค่าฟิลด์ที่กำหนดเองได้อย่างไร?**  
A: สร้าง `CustomFieldCondition` (หรือทำการ implement `ICondition<Task>`) แล้วเพิ่มเข้าไปในโซ่ `And<T>`.

**Q: ฉันสามารถใช้วิธีเดียวกันนี้เพื่อกรองทรัพยากรได้หรือไม่?**  
A: ได้—แทนที่ `Task` ด้วย `Resource` และใช้คลาสเงื่อนไขที่สอดคล้องกัน.

## สรุป

โดยทำตามขั้นตอนข้างต้น คุณจะรู้ **วิธีการรวมหลายเงื่อนไข** ด้วย **การดำเนินการ AND ขั้นสูง** ใน Aspose.Tasks for .NET เทคนิคนี้ช่วยให้คุณ **กรองงานของโครงการ** อย่างมีประสิทธิภาพ ไม่ว่าจะเป็นการมุ่งเป้าไปที่รายการสรุป, รายการที่ไม่เป็น null, หรือเกณฑ์ที่กำหนดเองใด ๆ ที่คุณระบุ.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}