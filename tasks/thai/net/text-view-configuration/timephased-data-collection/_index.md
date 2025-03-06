---
title: การเรียนรู้การรวบรวมข้อมูลตามช่วงเวลาใน Aspose.Tasks
linktitle: การรวบรวมข้อมูลตามช่วงเวลาใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจการรวบรวมข้อมูลตามช่วงเวลาใน Aspose.Tasks สำหรับ .NET คำแนะนำทีละขั้นตอน คำถามที่พบบ่อย และอื่นๆ อีกมากมาย เพิ่มความสามารถในการจัดการโครงการของคุณวันนี้!
weight: 15
url: /th/net/text-view-configuration/timephased-data-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้การรวบรวมข้อมูลตามช่วงเวลาใน Aspose.Tasks

## การแนะนำ
คุณต้องการควบคุมพลังของข้อมูลตามช่วงเวลาในแอปพลิเคชัน .NET ของคุณโดยใช้ Aspose.Tasks หรือไม่? ไม่ต้องมองอีกต่อไป! คู่มือที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการรวบรวมข้อมูลตามช่วงเวลาด้วย Aspose.Tasks สำหรับ .NET เพื่อให้มั่นใจว่าคุณจะได้รับประโยชน์สูงสุดจากไลบรารีอันทรงพลังนี้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[เอกสาร Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้
3. Your Document Directory: แทนที่ตัวยึดตำแหน่ง "Your Document Directory" ในโค้ดขนาดสั้นด้วยเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชัน Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. สร้างโครงการและทรัพยากร
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. เพิ่มงานในโครงการ
```csharp
var task = project.RootTask.Children.Add("Task 1");
// ตั้งค่าคุณสมบัติของงาน...
var task2 = project.RootTask.Children.Add("Task 2");
// ตั้งค่าคุณสมบัติ Task2...
```
## 3. กำหนดทรัพยากรให้กับงาน
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// ตั้งค่าคุณสมบัติการมอบหมาย...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//ตั้งค่าคุณสมบัติการมอบหมาย 2...
```
## 4. ทำงานกับข้อมูลตามช่วงเวลา
```csharp
// กำหนดโครงร่างการทำงานที่โค้งมน
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// ตรวจสอบว่าการรวบรวมข้อมูลตามช่วงเวลาเป็นแบบอ่านอย่างเดียวหรือไม่
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// ล้างข้อมูลตามระยะเวลาที่สร้างขึ้น
assignment.TimephasedData.Clear();
// สร้างและเพิ่มข้อมูลตามช่วงเวลา
var td = new TimephasedData
{
    // ตั้งค่าคุณสมบัติข้อมูลตามช่วงเวลา...
};
assignment.TimephasedData.Add(td);
// เพิ่มรายการข้อมูลตามช่วงเวลา
var list = new List<TimephasedData>();
// เพิ่มรายการข้อมูลตามช่วงเวลาเพิ่มเติมลงในรายการ...
assignment.TimephasedData.AddRange(list);
// กรองข้อมูลตามช่วงเวลาตามประเภทและช่วงวันที่
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// พิมพ์ข้อมูลตามระยะเวลาที่กรองแล้ว...
```
## 5. จัดการข้อมูลตามช่วงเวลา
```csharp
// เพิ่มรายการข้อมูลแบ่งเวลาผิดแล้วลบออก
var td4 = new TimephasedData
{
    // ตั้งค่าคุณสมบัติข้อมูลแบ่งตามช่วงเวลาไม่ถูกต้อง...
};
assignment.TimephasedData.Add(td4);
// ลบรายการข้อมูลตามเฟสที่ไม่ถูกต้อง
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// วนซ้ำรายการตามช่วงเวลาทั้งหมด
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // พิมพ์รายละเอียดรายการตามช่วงเวลา...
}
```
## 6. คัดลอกข้อมูลตามระยะเวลาไปยังงานมอบหมายอื่น
```csharp
// คัดลอกข้อมูลตามช่วงเวลาไปยังงานอื่น
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// แปลงคอลเลกชันเป็นรายการธรรมดา
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// ลบรายการข้อมูลตามช่วงเวลาออกทีละรายการ
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## บทสรุป
โดยสรุป บทช่วยสอนนี้ได้ให้คำแนะนำโดยละเอียดเกี่ยวกับการรวบรวมข้อมูลตามช่วงเวลาโดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น ช่วยให้สามารถติดตามเวลาและการจัดการทรัพยากรได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับเครื่องมือการจัดการโครงการอื่นๆ ได้หรือไม่
ใช่ Aspose.Tasks สำหรับ .NET ได้รับการออกแบบมาเพื่อทำงานร่วมกับเครื่องมือการจัดการโครงการยอดนิยม และรองรับไฟล์รูปแบบต่างๆ
### มีการจำกัดจำนวนทรัพยากรและงานที่ฉันสามารถจัดการด้วย Aspose.Tasks ได้หรือไม่
Aspose.Tasks จัดการโปรเจ็กต์ที่มีขนาดแตกต่างกัน และไม่มีการจำกัดจำนวนทรัพยากรและงานที่เข้มงวด
### ฉันจะรับการสนับสนุนสำหรับปัญหาหรือข้อสงสัยที่เกี่ยวข้องกับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 สำหรับการสนับสนุนโปรดไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือ
### ฉันสามารถลองใช้ Aspose.Tasks สำหรับ .NET ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.Tasks สำหรับ .NET ได้โดยเข้าไปที่[ทดลองฟรี](https://releases.aspose.com/).
### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
คุณสามารถซื้อใบอนุญาตสำหรับ Aspose.Tasks สำหรับ .NET[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
