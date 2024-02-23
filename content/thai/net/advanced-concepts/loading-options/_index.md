---
title: ตัวเลือกสำหรับการโหลดใน Aspose.Tasks
linktitle: ตัวเลือกสำหรับการโหลดใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีควบคุมพลังของ Aspose.Tasks สำหรับ .NET เพื่อจัดการเอกสาร Microsoft Project อย่างมีประสิทธิภาพพร้อมคำแนะนำทีละขั้นตอน
type: docs
weight: 16
url: /th/net/advanced-concepts/loading-options/
---
## การแนะนำ

Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการเอกสาร Microsoft Project โดยทางโปรแกรมได้ ไม่ว่าคุณจะต้องการสร้าง อ่าน เขียน หรือแปลงไฟล์โปรเจ็กต์ Aspose.Tasks มีฟังก์ชันการทำงานที่หลากหลายเพื่อปรับปรุงงานของคุณ ในบทช่วยสอนนี้ เราจะเจาะลึกสิ่งสำคัญของการใช้ Aspose.Tasks สำหรับ .NET โดยแบ่งกระบวนการสำคัญออกเป็นขั้นตอนง่ายๆ ที่นำไปปฏิบัติได้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึก Aspose.Tasks สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio หรือ IDE อื่น ๆ ที่คุณเลือก
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว เรามาสำรวจเนมสเปซที่จำเป็นและเจาะลึกคำแนะนำทีละขั้นตอนกันดีกว่า

## การนำเข้าเนมสเปซ

ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:

1. Aspose.Tasks: เนมสเปซนี้มีคลาสหลักและอินเทอร์เฟซสำหรับการทำงานกับเอกสาร Project

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

ตอนนี้ เรามาแบ่งงานต่างๆ ออกเป็นคำแนะนำทีละขั้นตอน

## ขั้นตอนที่ 1: กำลังโหลดโปรเจ็กต์ที่ป้องกันด้วยรหัสผ่าน

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // เริ่มต้น FileStream เพื่อโหลดไฟล์โครงการ
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // สร้างอินสแตนซ์ LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // ตั้งรหัสผ่าน
        };

        // โหลดโปรเจ็กต์ด้วยตัวเลือกที่ระบุ
        var project = new Project(stream, options);

        // แสดงชื่อโครงการ
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## ขั้นตอนที่ 2: กำลังโหลดโปรเจ็กต์ Primavera ด้วยตัวเลือกแบบกำหนดเอง

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // สร้างอินสแตนซ์ LoadOptions
    var loadOptions = new LoadOptions();

    // กำหนดค่าตัวเลือกการอ่าน Primavera
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // ตั้งค่า UID ของโครงการ
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // ตั้งค่าตัวเลือกการอ่าน Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // โหลดโปรเจ็กต์ Primavera ด้วยตัวเลือกที่ระบุ
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // แสดงชื่อโครงการ
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // ดำเนินการเพิ่มเติมกับโปรเจ็กต์ที่โหลดแล้ว
}
```

## ขั้นตอนที่ 3: ระบุการเข้ารหัสไฟล์

```csharp
public void SpecifyFileEncoding()
{
    // สร้างอินสแตนซ์ LoadOptions
    LoadOptions lo = new LoadOptions();

    // ระบุการเข้ารหัสเมื่อเปิดโปรเจ็กต์จากไฟล์ Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // โหลดโปรเจ็กต์ด้วยการเข้ารหัสที่ระบุ
    var project = new Project("encoding1251.xer", lo);

    // ดำเนินการเพิ่มเติมกับโปรเจ็กต์ที่โหลดแล้ว
}
```

## ขั้นตอนที่ 4: กำลังโหลดโปรเจ็กต์ Primavera พร้อมการจัดการข้อผิดพลาด

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // สร้างอินสแตนซ์ LoadOptions
    var loadOptions = new LoadOptions();

    // กำหนดค่าตัวเลือกการอ่าน Primavera
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // ตั้งค่า UID ของโครงการ
    };

    // ตั้งค่าตัวเลือกการอ่าน Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //ตั้งค่าการจัดการข้อผิดพลาดแบบกำหนดเอง
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // โหลดโปรเจ็กต์ Primavera ด้วยตัวเลือกที่ระบุและการจัดการข้อผิดพลาด
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // ดำเนินการเพิ่มเติมกับโปรเจ็กต์ที่โหลดแล้ว
}

// วิธีจัดการข้อผิดพลาดแบบกำหนดเอง
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // ใช้ตรรกะการจัดการข้อผิดพลาดแบบกำหนดเอง
}
```

ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถใช้ตัวเลือกการโหลดใน Aspose.Tasks สำหรับ .NET เพื่อจัดการเอกสาร Project ตามความต้องการของคุณได้อย่างมีประสิทธิภาพ

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจพื้นฐานของการทำงานกับตัวเลือกการโหลดใน Aspose.Tasks สำหรับ .NET ตั้งแต่การโหลดโปรเจ็กต์ที่มีการป้องกันด้วยรหัสผ่านไปจนถึงการระบุการจัดการข้อผิดพลาดแบบกำหนดเอง การเรียนรู้เทคนิคเหล่านี้อย่างเชี่ยวชาญจะช่วยให้คุณสามารถจัดการไฟล์โปรเจ็กต์ภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่

ตอบ 1: ใช่ Aspose.Tasks สำหรับ .NET รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน

### คำถามที่ 2: ฉันสามารถรวม Aspose.Tasks สำหรับ .NET เข้ากับไลบรารีของบริษัทอื่นได้หรือไม่

ตอบ 2: แน่นอนว่า Aspose.Tasks สำหรับ .NET สามารถทำงานร่วมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น โดยนำเสนอฟังก์ชันการทำงานและความยืดหยุ่นที่ได้รับการปรับปรุง

### คำถามที่ 3: Aspose.Tasks สำหรับ .NET มีเอกสารประกอบและทรัพยากรสนับสนุนหรือไม่

 A3: ใช่ คุณสามารถอ้างอิงถึงเนื้อหาที่ครอบคลุมได้[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) และเข้าถึงการสนับสนุนผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### คำถามที่ 4: มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.Tasks สำหรับ .NET หรือไม่

 A4: ได้ คุณสามารถสำรวจตัวเลือกใบอนุญาตต่างๆ รวมถึงการทดลองใช้ฟรีและใบอนุญาตชั่วคราวได้ที่[เว็บไซต์ Aspose.Tasks](https://purchase.aspose.com/buy).

### คำถามที่ 5: มีการอัปเดตและฟีเจอร์ใหม่สำหรับ Aspose.Tasks สำหรับ .NET บ่อยเพียงใด

A5: Aspose.Tasks สำหรับ .NET ได้รับการอัพเดตและการปรับปรุงคุณสมบัติเป็นประจำเพื่อให้มั่นใจถึงประสิทธิภาพสูงสุดและความเข้ากันได้กับเทคโนโลยีที่พัฒนา