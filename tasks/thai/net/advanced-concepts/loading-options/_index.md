---
date: 2026-03-08
description: เรียนรู้วิธีนำเข้าไฟล์โครงการโดยใช้ Aspose.Tasks สำหรับ .NET รวมถึงวิธีระบุการเข้ารหัสไฟล์และโหลดไฟล์
  Microsoft Project อย่างมีประสิทธิภาพ
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: นำเข้าไฟล์โครงการ – ตัวเลือกสำหรับการโหลดใน Aspose.Tasks
url: /th/net/advanced-concepts/loading-options/
weight: 16
---

 Import Project File – Options for Loading in Aspose.Tasks" becomes "# นำเข้าไฟล์โครงการ – ตัวเลือกการโหลดใน Aspose.Tasks". Keep dash.

Similarly others.

Make sure to keep code block placeholders unchanged.

Translate bullet points.

Be careful not to translate URLs, code names, etc.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# นำเข้าไฟล์โครงการ – ตัวเลือกการโหลดใน Aspose.Tasks

## บทนำ

Aspose.Tasks for .NET ทำให้การ **import project file** จาก Microsoft Project, Primavera และรูปแบบอื่น ๆ เป็นเรื่องง่าย ไม่ว่าคุณจะต้องการอ่านไฟล์ที่มีการป้องกันด้วยรหัสผ่าน, ตั้งค่าการเข้ารหัสแบบกำหนดเอง, หรือจัดการข้อผิดพลาดในการพาร์ส, ไลบรารีนี้ให้การควบคุมที่ละเอียดผ่านตัวเลือกการโหลด ในบทแนะนำนี้เราจะพาคุณผ่านสถานการณ์ที่พบบ่อยที่สุดเพื่อให้คุณสามารถ **load Microsoft Project file** ในแอปพลิเคชัน .NET ของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **วิธีหลักในการนำเข้าไฟล์โครงการคืออะไร?** ใช้คอนสตรัคเตอร์ `Project` พร้อมอินสแตนซ์ของ `LoadOptions`  
- **ฉันสามารถเปิดไฟล์ที่ป้องกันด้วยรหัสผ่านได้หรือไม่?** ได้—ตั้งค่า `Password` บน `LoadOptions`  
- **ฉันจะระบุการเข้ารหัสไฟล์อย่างไร?** กำหนดอ็อบเจ็กต์ `Encoding` ให้กับ `LoadOptions.Encoding`  
- **การจัดการข้อผิดพลาดสามารถปรับแต่งได้หรือไม่?** แน่นอน—ให้ delegate กับ `LoadOptions.ErrorHandler`  
- **ตัวเลือกเหล่านี้ทำงานกับไฟล์ Primavera หรือไม่?** ใช้ `PrimaveraReadOptions` ภายใน `LoadOptions`

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

1. **Visual Studio** (หรือ IDE .NET ที่คุณชื่นชอบ)  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดได้จาก [website](https://releases.aspose.com/tasks/net/)  
3. ความเข้าใจพื้นฐานเกี่ยวกับไวยากรณ์ **C#** และโครงสร้างโปรเจกต์

เมื่อพร้อมแล้ว ให้ทำการนำเข้า namespace ที่จำเป็น

## การนำเข้า Namespaces

ในโปรเจกต์ C# ของคุณ เพิ่ม `using` statements ด้านล่างเพื่อให้คลาส API พร้อมใช้งาน:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## วิธีนำเข้าไฟล์โครงการด้วยตัวเลือกการโหลด

ต่อไปนี้เป็นตัวอย่างสี่กรณีที่ครอบคลุมสถานการณ์การโหลดที่พบบ่อยที่สุด

### ขั้นตอน 1: โหลดโครงการที่ป้องกันด้วยรหัสผ่าน

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### ขั้นตอน 2: โหลดโครงการ Primavera ด้วยตัวเลือกกำหนดเอง

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### ขั้นตอน 3: **ระบุการเข้ารหัสไฟล์** เมื่อ Import XER File

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### ขั้นตอน 4: โหลดโครงการ Primavera ด้วยการจัดการข้อผิดพลาดแบบกำหนดเอง

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

โดยทำตามขั้นตอนเหล่านี้ คุณจะสามารถ **import project file** ได้อย่างแม่นยำ ปรับกระบวนการโหลดให้ตรงกับความต้องการของคุณ และทำให้แอปพลิเคชันของคุณมีความเสถียร

## ปัญหาที่พบบ่อย & เคล็ดลับ

- **รหัสผ่านไม่ถูกต้อง** – property `Password` จะโยนข้อยกเว้น; ตรวจสอบข้อมูลประจำตัวก่อนทำการโหลด  
- **การเข้ารหัสที่ไม่รองรับ** – ตรวจสอบให้แน่ใจว่า code page ที่ระบุมีอยู่บนเครื่องเป้าหมาย (`Encoding.GetEncoding(1251)` ใช้สำหรับ Cyrillic)  
- **ขาดตัวเลือก Primavera** – หากต้องการรักษา UID ของงาน, ตั้งค่า `PreserveUids = true`; มิฉะนั้นอาจมี ID ซ้ำเกิดขึ้น  
- **Error handler คืนค่า null** – การคืนค่า `null` จะบอก parser ให้ข้ามองค์ประกอบที่มีปัญหา; ปรับแต่งตามต้องการ

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for .NET รองรับทุกเวอร์ชันของ Microsoft Project หรือไม่?**  
A: รองรับหลายเวอร์ชันของ Microsoft Project, ดังนั้นคุณสามารถ **load Microsoft Project file** จากไฟล์ MPP เก่าไปจนถึงรูปแบบล่าสุดได้

**Q: ฉันสามารถรวม Aspose.Tasks for .NET กับไลบรารีของบุคคลที่สามอื่น ๆ ได้หรือไม่?**  
A: แน่นอน ไลบรารีทำงานร่วมกับแพคเกจ .NET อื่น ๆ ได้อย่างราบรื่น ทำให้คุณสามารถผสานกับระบบรายงาน, UI หรือเฟรมเวิร์กการเข้าถึงข้อมูลได้

**Q: Aspose.Tasks for .NET มีเอกสารและแหล่งสนับสนุนหรือไม่?**  
A: มี คุณสามารถอ้างอิงเอกสารที่ครอบคลุมได้ที่ [documentation](https://reference.aspose.com/tasks/net/) และรับการสนับสนุนผ่าน [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

**Q: มีตัวเลือกการให้ลิขสิทธิ์สำหรับ Aspose.Tasks for .NET หรือไม่?**  
A: มี คุณสามารถสำรวจตัวเลือกลิขสิทธิ์ต่าง ๆ รวมถึงการทดลองใช้ฟรีและลิขสิทธิ์ชั่วคราวได้ที่ [Aspose.Tasks website](https://purchase.aspose.com/buy)

**Q: การอัปเดตและฟีเจอร์ใหม่ ๆ ของ Aspose.Tasks for .NET ปล่อยบ่อยแค่ไหน?**  
A: Aspose.Tasks มีการอัปเดตเป็นประจำเพื่อเพิ่มฟีเจอร์, ปรับปรุงประสิทธิภาพ, และรักษาความเข้ากันได้กับการปล่อยเวอร์ชันใหม่ของ Microsoft Project

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}