---
title: คู่มือการรวบรวมตารางการเรียนรู้ใน Aspose.Tasks
linktitle: คอลเลกชันของตารางใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master Aspose.Tasks สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนเกี่ยวกับการจัดการคอลเลกชันตาราง ปรับปรุงแอปพลิเคชันการจัดการโครงการได้อย่างง่ายดาย ดาวน์โหลดเดี๋ยวนี้!
type: docs
weight: 11
url: /th/net/task-table-management/table-collection/
---
## การแนะนำ
ปลดล็อกพลังของ Aspose.Tasks สำหรับ .NET โดยเจาะลึกขอบเขตอันน่าทึ่งของคอลเลกชันตาราง ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นการเดินทางกับ Aspose.Tasks คู่มือที่ครอบคลุมนี้จะแนะนำคุณเกี่ยวกับความแตกต่างของการจัดการตาราง ซึ่งจะช่วยให้คุณมีทักษะในการปรับปรุงแอปพลิเคชันการจัดการโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางครั้งนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
- Aspose.Tasks สำหรับ .NET ที่ติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ
- ไฟล์โครงการในรูปแบบ MPP เพื่อทดลองใช้
## นำเข้าเนมสเปซ
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. เริ่มต้นโครงการของคุณ
เริ่มต้นด้วยการตั้งค่าโปรเจ็กต์ของคุณและโหลดไฟล์ MPP:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
// โหลดไฟล์โครงการ
var project = new Project(DataDir + "Project1.mpp");
```
## 2. ตรวจสอบสถานะอ่านอย่างเดียว
ตรวจสอบว่าคอลเลกชันของตารางเป็นแบบอ่านอย่างเดียวหรือไม่:
```csharp
Console.WriteLine("Is the collection of tables read-only?: " + project.Tables.IsReadOnly);
```
## 3. ทำซ้ำตาราง
สำรวจตารางที่มีอยู่ในโครงการ:
```csharp
Console.WriteLine("Print tables of " + project.Get(Prj.Name) + " project.");
Console.WriteLine("Table count: " + project.Tables.Count);
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Index: " + tbl.Index);
    Console.WriteLine("Name: " + tbl.Name);
}
```
## 4. เพิ่มตารางใหม่
เรียนรู้วิธีเพิ่มตารางใหม่ให้กับคอลเลกชัน:
```csharp
var tableToAdd = new Table
{
    Name = "New Table",
    ShowInMenu = true
};
project.Tables.Add(tableToAdd);
Console.WriteLine("Does the collection contain the new table?: " + project.Tables.Contains(tableToAdd));
```
## 5. ล้างคอลเลกชัน
ค้นพบสองวิธีในการล้างคอลเลกชันตาราง:
- ลบตารางทีละรายการ:
```csharp
var tables = new Table[project.Tables.Count];
project.Tables.CopyTo(tables, 0);
foreach (var table in tables)
{
    project.Tables.Remove(table);
}
```
- ล้างคอลเลกชันทั้งหมด:
```csharp
project.Tables.Clear();
```
## 6. แปลงเป็นรายการ
แปลงคอลเลกชันให้เป็นรายการตารางธรรมดา:
```csharp
List<Table> list = project.Tables.ToList();
foreach (var table in list)
{
    Console.WriteLine("Index: " + table.Index);
    Console.WriteLine("Name: " + table.Name);
}
```
## บทสรุป
ยินดีด้วย! คุณได้สำรวจภูมิทัศน์ที่ซับซ้อนของคอลเลกชันตารางใน Aspose.Tasks สำหรับ .NET สำเร็จแล้ว ด้วยความรู้นี้ คุณสามารถเพิ่มประสิทธิภาพแอปพลิเคชันการจัดการโครงการของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถจัดการคุณสมบัติของตารางที่มีอยู่ในคอลเลกชันได้หรือไม่
ตอบ: แน่นอน! คุณสามารถแก้ไขคุณสมบัติ เช่น ชื่อ การเปิดเผย และอื่นๆ
### ถาม: สามารถสร้างตารางแบบกำหนดเองได้หรือไม่
ตอบ: ได้ คุณสามารถสร้างและเพิ่มตารางแบบกำหนดเองเพื่อปรับแต่งให้ตรงตามความต้องการเฉพาะของคุณได้
### ถาม: มีข้อจำกัดเกี่ยวกับจำนวนตารางในโปรเจ็กต์หรือไม่
ตอบ: ในเวอร์ชันล่าสุด ไม่มีข้อจำกัดเกี่ยวกับจำนวนตารางที่กำหนดไว้ล่วงหน้า
### ถาม: ฉันสามารถคืนค่าการเปลี่ยนแปลงที่ทำกับคอลเลกชันตารางได้หรือไม่
ตอบ: ได้ คุณสามารถใช้ project.Undo() เพื่อคืนค่าการเปลี่ยนแปลงที่ทำระหว่างเซสชันได้
### ถาม: มีข้อควรพิจารณาด้านประสิทธิภาพเมื่อทำงานกับโครงการขนาดใหญ่หรือไม่
ตอบ: เพื่อประสิทธิภาพสูงสุด ให้พิจารณาการดำเนินการเป็นชุดและหลีกเลี่ยงการทำซ้ำโดยไม่จำเป็น