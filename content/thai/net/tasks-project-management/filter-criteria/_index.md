---
title: การเรียนรู้เกณฑ์การกรองโครงการ MS ด้วย Aspose.Tasks
linktitle: เกณฑ์การกรองใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีใช้เกณฑ์ตัวกรองใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เพิ่มประสิทธิภาพการจัดการโครงการด้วยการวิเคราะห์ข้อมูลที่ตรงเป้าหมาย
type: docs
weight: 18
url: /th/net/tasks-project-management/filter-criteria/
---
## การแนะนำ
ในขอบเขตของการจัดการโครงการ Microsoft Project ถือเป็นเครื่องมือที่แข็งแกร่ง โดยนำเสนอฟีเจอร์มากมายเพื่อช่วยผู้วางแผนและผู้จัดการโครงการ ในบรรดาฟังก์ชันต่างๆ มากมายนั้น ความสามารถในการกรองข้อมูลโครงการ ช่วยให้ผู้ใช้สามารถมุ่งเน้นไปที่ลักษณะเฉพาะของงานโครงการของตนได้ อย่างไรก็ตาม การเรียนรู้ความสามารถในการกรองเหล่านี้จนเชี่ยวชาญอาจเป็นงานที่น่ากังวลหากไม่มีคำแนะนำที่ถูกต้อง บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อทำความเข้าใจกระบวนการโดยให้คำแนะนำทีละขั้นตอนเกี่ยวกับการนำเกณฑ์ตัวกรองไปใช้ใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นเพื่อเข้าใจแนวคิดที่กล่าวถึงในบทช่วยสอนนี้
2.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ไฟล์ Microsoft Project: เตรียมไฟล์ Microsoft Project (เช่น Project2003.mpp) ให้พร้อม ซึ่งคุณจะใช้สำหรับการนำเกณฑ์ตัวกรองไปใช้

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Tasks สำหรับ .NET ทำตามขั้นตอนเหล่านี้:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 คำอธิบาย: บรรทัดของโค้ดนี้เตรียมใช้งานอินสแตนซ์ใหม่ของ`Project` คลาสและโหลดไฟล์ Microsoft Project ที่ระบุโดยเส้นทาง
## ขั้นตอนที่ 2: ดึงข้อมูลตัวกรองงาน
```csharp
var filter = project.TaskFilters.ToList()[1];
```
คำอธิบาย: ที่นี่ เราดึงข้อมูลตัวกรองงานจากโครงการ ปรับดัชนี (`[1]`) ตามความต้องการของคุณเพื่อเลือกตัวกรองที่ต้องการ
## ขั้นตอนที่ 3: แสดงแถวเกณฑ์
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
คำอธิบาย: ส่วนนี้จะวนซ้ำแต่ละแถวเกณฑ์ของตัวกรอง และแสดงฟิลด์ การดำเนินการ การทดสอบ และค่า (ถ้ามี)
## ขั้นตอนที่ 4: พิมพ์เกณฑ์ตัวกรอง
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
คำอธิบาย: พิมพ์การทำงานของเกณฑ์ตัวกรอง
## ขั้นตอนที่ 5: แสดงรายละเอียดเกณฑ์
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
คำอธิบาย: ส่วนนี้จะดึงและแสดงข้อมูลโดยละเอียดเกี่ยวกับแถวเกณฑ์แต่ละแถว โดยให้ข้อมูลเชิงลึกเกี่ยวกับการกำหนดค่าของตัวกรอง

## บทสรุป
การเรียนรู้เกณฑ์การกรองใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เป็นทักษะอันทรงคุณค่าที่สามารถเพิ่มประสิทธิภาพการจัดการโครงการได้อย่างมาก ด้วยการทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดการเกณฑ์ตัวกรองโดยทางโปรแกรม ซึ่งช่วยให้คุณปรับแต่งมุมมองโครงการให้ตรงกับความต้องการเฉพาะของคุณได้
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ตัวกรองหลายตัวพร้อมกันใน MS Project ได้หรือไม่
ตอบ: ได้ คุณสามารถรวมตัวกรองหลายตัวเข้าด้วยกันเพื่อปรับแต่งข้อมูลโครงการของคุณเพิ่มเติมได้
### ถาม: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันเก่าหรือไม่
ตอบ: ได้ Aspose.Tasks มีความเข้ากันได้แบบย้อนหลัง ช่วยให้คุณสามารถทำงานกับไฟล์ Microsoft Project เวอร์ชันต่างๆ ได้
### ถาม: Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET อื่นๆ หรือไม่
ตอบ: Aspose.Tasks รองรับ .NET Framework, .NET Core และ .NET Standard ทำให้มั่นใจถึงความยืดหยุ่นในสภาพแวดล้อมการพัฒนาที่แตกต่างกัน
### ถาม: ฉันสามารถปรับแต่งเกณฑ์ตัวกรองตามเงื่อนไขไดนามิกได้หรือไม่
ตอบ: แน่นอน คุณสามารถปรับเกณฑ์ตัวกรองโดยทางโปรแกรมตามพารามิเตอร์ไดนามิก ซึ่งช่วยให้สามารถวิเคราะห์ข้อมูลโครงการแบบปรับเปลี่ยนได้
### ถาม: ฉันจะขอความช่วยเหลือได้ที่ไหนหากฉันประสบปัญหากับ Aspose.Tasks
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อขอการสนับสนุนจากชุมชนหรือติดต่อโดยตรงกับฝ่ายสนับสนุน Aspose.Tasks เพื่อขอความช่วยเหลือส่วนบุคคล