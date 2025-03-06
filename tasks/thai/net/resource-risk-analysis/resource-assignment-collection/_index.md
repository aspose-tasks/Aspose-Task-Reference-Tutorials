---
title: การรวบรวมการมอบหมายทรัพยากรใน Aspose.Tasks
linktitle: การรวบรวมการมอบหมายทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการการกำหนดทรัพยากรใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนทีละขั้นตอนพร้อมตัวอย่างโค้ด
type: docs
weight: 12
url: /th/net/resource-risk-analysis/resource-assignment-collection/
---
## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการจัดการการกำหนดทรัพยากรใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการทีละขั้นตอน เพื่อให้แน่ใจว่าคุณมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการจัดการการมอบหมายทรัพยากรอย่างมีประสิทธิภาพ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะอธิบายทุกสิ่งที่คุณจำเป็นต้องรู้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าต่อไปนี้:
1.  ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากไม่ใช่คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ความรู้พื้นฐานของ C#: บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
3. ไฟล์โครงการ Microsoft: เตรียมไฟล์โครงการ Microsoft ให้พร้อมสำหรับการทดสอบ หากคุณไม่มี คุณสามารถสร้างไฟล์ตัวอย่างได้

## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็น:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
เริ่มต้นด้วยการโหลดไฟล์ Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## ขั้นตอนที่ 2: เพิ่มงานและทรัพยากร
ตอนนี้ เรามาเพิ่มงานและทรัพยากรให้กับโครงการกันดีกว่า:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## ขั้นตอนที่ 3: กำหนดทรัพยากรให้กับงาน
ต่อไป เราจะกำหนดทรัพยากรให้กับงาน:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## ขั้นตอนที่ 4: การทำงานกับประเภทการมอบหมายที่แตกต่างกัน
คุณยังสามารถทำงานกับการมอบหมายที่เกี่ยวข้องกับหน่วยหรือต้นทุน:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// ตั้งค่าคุณสมบัติสำหรับการมอบหมายด้วยหน่วยและต้นทุนในทำนองเดียวกันดังที่แสดงในขั้นตอนที่ 3
```
## ขั้นตอนที่ 5: พิมพ์งานที่ได้รับมอบหมาย
พิมพ์งานสำหรับโครงการ:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // พิมพ์รายละเอียดงาน
}
```
## ขั้นตอนที่ 6: ดึงข้อมูลการมอบหมายโดย UID
คุณสามารถดึงข้อมูลการมอบหมายโดย UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## ขั้นตอนที่ 7: ตรวจสอบสถานะอ่านอย่างเดียว
ตรวจสอบว่าคอลเลกชันการกำหนดทรัพยากรเป็นแบบอ่านอย่างเดียวหรือไม่:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## ขั้นตอนที่ 8: แปลงคอลเลกชันเป็นรายการและวนซ้ำ
แปลงคอลเลกชันเป็นรายการและทำซ้ำ:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีจัดการการกำหนดทรัพยากรใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการงานและทรัพยากรได้อย่างมีประสิทธิภาพ ทำให้การจัดการโครงการเป็นเรื่องง่าย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับไฟล์ Microsoft Project เวอร์ชันต่างๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### ถาม: มีเวอร์ชันทดลองใช้ก่อนที่จะซื้อ Aspose.Tasks สำหรับ .NET หรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ Aspose.Tasks for .NET ได้ฟรีจาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะได้รับการสนับสนุนได้อย่างไร หากฉันพบปัญหาใดๆ ในขณะที่ใช้ Aspose.Tasks สำหรับ .NET
 ตอบ: คุณสามารถขอการสนับสนุนจากฟอรัม Aspose.Tasks ได้[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันสามารถใช้สิทธิ์ใช้งานชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET ได้หรือไม่
 ตอบ: ใช่ ใบอนุญาตชั่วคราวมีไว้เพื่อวัตถุประสงค์ในการประเมิน คุณสามารถรับได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะซื้อใบอนุญาตแบบเต็มสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถซื้อใบอนุญาตฉบับสมบูรณ์ได้จากร้านค้าออนไลน์ของ Aspose[ที่นี่](https://purchase.aspose.com/buy).