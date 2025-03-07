---
title: การเรียนรู้คอลเลกชันฟิลด์ตารางใน Aspose.Tasks สำหรับ .NET
linktitle: การรวบรวมเขตข้อมูลตารางใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจโลกแบบไดนามิกของการจัดการโครงการด้วย Aspose.Tasks สำหรับ .NET เรียนรู้วิธีจัดการคอลเลกชันฟิลด์ตารางสำหรับประสบการณ์โปรเจ็กต์แบบกำหนดเอง
weight: 13
url: /th/net/task-table-management/table-field-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้คอลเลกชันฟิลด์ตารางใน Aspose.Tasks สำหรับ .NET

## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งอำนวยความสะดวกในการจัดการโครงการโดยมอบฟังก์ชันการทำงานที่ครอบคลุมสำหรับการทำงานกับไฟล์ Microsoft Project ในบทช่วยสอนนี้ เราจะเจาะลึกคอลเลกชันของเขตข้อมูลตารางใน Aspose.Tasks สำรวจวิธีจัดการและจัดการเขตข้อมูลอย่างมีประสิทธิภาพโดยใช้ C#
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าดังต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio
## นำเข้าเนมสเปซ
ประการแรก ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นที่จุดเริ่มต้นของไฟล์ C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
```
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีไฟล์โครงการของคุณอยู่
```csharp
String DataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
โหลดไฟล์โครงการโดยใช้ไลบรารี Aspose.Tasks
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## ขั้นตอนที่ 3: วนซ้ำเขตข้อมูลตาราง
วนซ้ำเขตข้อมูลตารางภายในโครงการ
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    //วนซ้ำเขตข้อมูลตาราง
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## ขั้นตอนที่ 4: เพิ่มฟิลด์ตารางใหม่
เพิ่มเขตข้อมูลตารางใหม่ลงในตารางที่มีอยู่
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## ขั้นตอนที่ 5: แทรกฟิลด์ใหม่
แทรกฟิลด์ใหม่ในตำแหน่งเฉพาะภายในตาราง
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## ขั้นตอนที่ 6: แก้ไขฟิลด์ตารางใหม่
แก้ไขฟิลด์ตารางที่เพิ่มใหม่โดยใช้การเข้าถึงดัชนี
```csharp
table.TableFields[idx].WrapHeader = true;
```
## ขั้นตอนที่ 7: ลบฟิลด์
ลบฟิลด์ตารางทีละรายการหรือล้างคอลเลกชันทั้งหมด
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// ลบฟิลด์
table.TableFields.RemoveAt(idx);
```
## ขั้นตอนที่ 8: ล้างคอลเลกชัน
ล้างคอลเลกชันเขตข้อมูลตารางทีละรายการหรือทั้งหมด
```csharp
if (deleteOneByOne)
{
    // ถอดทีละอัน
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // ล้างคอลเลกชันให้สมบูรณ์
    table.TableFields.Clear();
}
```
ตอนนี้ คุณได้สำรวจคอลเลกชันของฟิลด์ตารางใน Aspose.Tasks สำหรับ .NET เรียบร้อยแล้ว ซึ่งช่วยให้คุณสามารถจัดการและจัดการฟิลด์เหล่านี้ตามความต้องการของโปรเจ็กต์ของคุณได้
## บทสรุป
โดยสรุป การทำความเข้าใจวิธีทำงานกับคอลเลกชันฟิลด์ตารางใน Aspose.Tasks สำหรับ .NET จะเปิดโอกาสสำหรับการจัดการโครงการและการปรับแต่งที่มีประสิทธิภาพ ด้วยความยืดหยุ่นจาก Aspose.Tasks นักพัฒนาจึงสามารถปรับแต่งแอปพลิเคชันของตนให้ตรงตามความต้องการเฉพาะของโครงการได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับไฟล์ Microsoft Project เวอร์ชันใดก็ได้หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และความยืดหยุ่น
### เป็นไปได้ไหมที่จะสร้างและแก้ไขฟิลด์ตารางแบบไดนามิกระหว่างรันไทม์?
อย่างแน่นอน! ดังที่แสดงในบทช่วยสอน คุณสามารถเพิ่ม แทรก แก้ไข และลบฟิลด์ตารางแบบไดนามิกได้ตามต้องการ
### มีข้อควรพิจารณาในการอนุญาตให้ใช้สิทธิ์สำหรับการใช้ Aspose.Tasks สำหรับ .NET ในโครงการเชิงพาณิชย์หรือไม่
 ใช่ คุณต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ Aspose.Tasks สำหรับ .NET ในโครงการเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).
### ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือเกี่ยวกับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)เพื่อรับการสนับสนุน ถามคำถาม และร่วมมือกับชุมชน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.Tasks สำหรับ .NET ได้ด้วยการทดลองใช้ฟรี ดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
