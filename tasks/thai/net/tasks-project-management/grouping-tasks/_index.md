---
title: การจัดกลุ่มงานโครงการ MS ที่มีประสิทธิภาพด้วย Aspose.Tasks
linktitle: การจัดกลุ่มงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดกลุ่มงาน Microsoft Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET
weight: 25
url: /th/net/tasks-project-management/grouping-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดกลุ่มงานโครงการ MS ที่มีประสิทธิภาพด้วย Aspose.Tasks

## การแนะนำ
การจัดการงานใน Microsoft Project บางครั้งอาจเป็นเรื่องท้าทาย โดยเฉพาะอย่างยิ่งเมื่อต้องจัดระเบียบงานเหล่านั้นอย่างมีประสิทธิภาพ Aspose.Tasks สำหรับ .NET นำเสนอโซลูชันที่ครอบคลุมโดยมอบฟังก์ชันการทำงานเพื่อจัดกลุ่มงานอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดกลุ่มงาน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET แล้ว
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ประการแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ C# ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ MS
เริ่มต้นด้วยการโหลดไฟล์ MS Project ของคุณโดยใช้รหัสต่อไปนี้:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## ขั้นตอนที่ 2: เข้าถึงกลุ่มงาน
ต่อไป เรามาเข้าถึงกลุ่มงานภายในโครงการกันดีกว่า:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## ขั้นตอนที่ 3: ดึงข้อมูลกลุ่ม
ตอนนี้ รับข้อมูลเกี่ยวกับกลุ่มงาน:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## ขั้นตอนที่ 4: เกณฑ์กลุ่มการเข้าถึง
เข้าถึงเกณฑ์ที่กำหนดไว้สำหรับกลุ่มงาน:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## ขั้นตอนที่ 5: ดึงข้อมูลเกณฑ์
รับข้อมูลโดยละเอียดเกี่ยวกับแต่ละเกณฑ์:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดกลุ่มงาน MS Project ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET ซึ่งจะช่วยปรับปรุงองค์กรและการจัดการข้อมูลโครงการของคุณ

## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ .NET มอบความสามารถอันทรงพลังสำหรับการจัดกลุ่มงาน MS Project ช่วยให้สามารถจัดระเบียบและจัดการข้อมูลโครงการได้ดีขึ้น ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะสามารถใช้คุณสมบัติเหล่านี้ในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถจัดกลุ่มงานตามเกณฑ์ที่กำหนดเองได้หรือไม่
ได้ คุณสามารถกำหนดเกณฑ์ที่กำหนดเองสำหรับการจัดกลุ่มงานตามความต้องการเฉพาะของคุณได้โดยใช้ Aspose.Tasks for .NET
### Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และการผสานรวมที่ราบรื่น
### มีรุ่นทดลองใช้สำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถรับ Aspose.Tasks สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของงานที่จัดกลุ่มได้หรือไม่
แน่นอนว่า Aspose.Tasks มีตัวเลือกในการปรับแต่งรูปลักษณ์ของงานที่จัดกลุ่ม รวมถึงสีของเซลล์ แบบอักษร และสไตล์
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือสำหรับ Aspose.Tasks สำหรับ .NET ได้ใน[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
