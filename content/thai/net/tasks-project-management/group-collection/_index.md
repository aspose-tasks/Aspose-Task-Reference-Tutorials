---
title: การจัดการคอลเลกชันโครงการใน Aspose.Tasks
linktitle: การจัดการคอลเลกชันกลุ่มใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคอลเลกชัน MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเรา
type: docs
weight: 26
url: /th/net/tasks-project-management/group-collection/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการกลุ่มคอลเลกชัน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET การจัดการคอลเลกชันกลุ่มเป็นสิ่งสำคัญสำหรับการจัดระเบียบและจัดการงานและทรัพยากรอย่างมีประสิทธิภาพภายในโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานการเขียนโปรแกรม C# เนื่องจากบทช่วยสอนนี้เกี่ยวข้องกับการเขียนโค้ดใน C#
3. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา เช่น Visual Studio หรือ IDE อื่น ๆ ที่รองรับการพัฒนา .NET

## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับฟังก์ชัน Aspose.Tasks ในโค้ด C# ของเรา

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## ขั้นตอนที่ 1: โหลดโครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
ขั้นตอนนี้เกี่ยวข้องกับการโหลดไฟล์ MS Project ลงในวัตถุโครงการ Aspose.Tasks เพื่อให้เราสามารถดำเนินการกับมันได้
## ขั้นตอนที่ 2: ทำซ้ำกลุ่มงาน
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
ที่นี่ เราทำซ้ำกลุ่มงานภายในโปรเจ็กต์ โดยพิมพ์รายละเอียด เช่น ดัชนี ชื่อ และการมองเห็นในเมนูสำหรับแต่ละกลุ่ม
## ขั้นตอนที่ 3: ทำซ้ำกลุ่มทรัพยากร
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
ในทำนองเดียวกัน ขั้นตอนนี้จะวนซ้ำกลุ่มทรัพยากร โดยแสดงดัชนี ชื่อ และการมองเห็นในเมนู
## ขั้นตอนที่ 4: ล้างและคัดลอกกลุ่มไปยังโครงการอื่น
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// ล้างกลุ่มของโครงการอื่น
otherProject.TaskGroups.Clear();
// คัดลอกกลุ่มไปยังโครงการอื่น
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
ที่นี่ เราจะล้างกลุ่มของโปรเจ็กต์อื่น จากนั้นคัดลอกกลุ่มจากโปรเจ็กต์ดั้งเดิมไปยังโปรเจ็กต์นั้น
## ขั้นตอนที่ 5: เพิ่มกลุ่มงานแบบกำหนดเอง
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
ในขั้นตอนนี้ เราจะสร้างกลุ่มงานแบบกำหนดเองและเพิ่มลงในโครงการอื่นหากยังไม่มีอยู่
## ขั้นตอนที่ 6: ลบกลุ่มทั้งหมด
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
สุดท้าย เราจะลบกลุ่มทั้งหมดออกจากโปรเจ็กต์อื่น

## บทสรุป
การจัดการกลุ่มคอลเลกชัน MS Project ใน Aspose.Tasks สำหรับ .NET เป็นสิ่งจำเป็นสำหรับการจัดระเบียบและจัดการข้อมูลโครงการอย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการงานและกลุ่มทรัพยากรภายในโครงการของคุณได้อย่างมีประสิทธิภาพ ซึ่งจะช่วยปรับปรุงการจัดการโครงการโดยรวม
## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ .NET เข้ากันได้กับ MS Project ทุกเวอร์ชันหรือไม่
Aspose.Tasks สำหรับ .NET รองรับ Microsoft Project เวอร์ชันต่างๆ รวมถึง 2003, 2007, 2010, 2013, 2016 และ 2019
### ฉันสามารถปรับแต่งคุณสมบัติกลุ่มโดยใช้ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ได้ คุณสามารถปรับแต่งคุณสมบัติของกลุ่ม เช่น ชื่อและการมองเห็นได้โดยใช้ Aspose.Tasks for .NET
### Aspose.Tasks สำหรับ .NET มีความเข้ากันได้ข้ามแพลตฟอร์มหรือไม่
Aspose.Tasks สำหรับ .NET กำหนดเป้าหมายไปที่เฟรมเวิร์ก .NET เป็นหลัก แต่สามารถใช้ในสถานการณ์ข้ามแพลตฟอร์มด้วย .NET Core และ .NET Standard
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### มีรุ่นทดลองใช้สำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Tasks สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).