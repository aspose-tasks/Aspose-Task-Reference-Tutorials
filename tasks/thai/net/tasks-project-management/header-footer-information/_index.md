---
title: แยกข้อมูลส่วนหัวและส่วนท้ายด้วย Aspose.Tasks
linktitle: ข้อมูลส่วนหัวและส่วนท้ายใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้การแยกข้อมูลส่วนหัวและส่วนท้ายจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET โซลูชันที่ง่าย มีประสิทธิภาพ และเป็นมิตรกับนักพัฒนา
weight: 29
url: /th/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แยกข้อมูลส่วนหัวและส่วนท้ายด้วย Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีดึงข้อมูลส่วนหัวและส่วนท้ายจากไฟล์ MS Project โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Visual Studio: ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ สิ่งนี้จะช่วยให้คุณสามารถเข้าถึงคลาสและวิธีการที่มีให้โดยไลบรารี Aspose.Tasks
```csharp
    using Aspose.Tasks;
    using System;
    
```
## ขั้นตอนที่ 1: เริ่มต้นวัตถุโครงการ
 ในการเริ่มต้น คุณจะต้องเริ่มต้น a`Project` วัตถุโดยการโหลดไฟล์ MS Project ที่มีอยู่
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## ขั้นตอนที่ 2: ดึงข้อมูลส่วนหัวและส่วนท้าย
 เมื่อคุณโหลดไฟล์โครงการแล้ว คุณสามารถดึงข้อมูลส่วนหัวและส่วนท้ายได้โดยใช้`PageInfo` คุณสมบัติ.
```csharp
var info = project.DefaultView.PageInfo;
// ข้อมูลส่วนหัว
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// ข้อมูลส่วนท้าย
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถดึงข้อมูลส่วนหัวและส่วนท้ายจากไฟล์ MS Project ได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ .NET

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีแยกข้อมูลส่วนหัวและส่วนท้ายจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ไลบรารีอันทรงพลังนี้ช่วยลดความยุ่งยากในการทำงานกับไฟล์ Project ในแอปพลิเคชัน C# ทำให้นักพัฒนามีเครื่องมือที่มีประสิทธิภาพสำหรับการจัดการ
### คำถามที่พบบ่อย
### ฉันสามารถแก้ไขข้อมูลส่วนหัวและส่วนท้ายโดยใช้ Aspose.Tasks ได้หรือไม่
ได้ คุณสามารถแก้ไขข้อมูลส่วนหัวและส่วนท้ายได้โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ .NET
### Aspose.Tasks รองรับรูปแบบไฟล์โครงการอื่นนอกเหนือจาก MS Project หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP, XML และ MPX
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Tasks ได้ที่ไหน
 คุณสามารถค้นหาเอกสารประกอบสำหรับ Aspose.Tasks[ที่นี่](https://reference.aspose.com/tasks/net/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Tasks ได้โดยไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
