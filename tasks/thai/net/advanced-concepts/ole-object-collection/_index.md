---
date: 2026-03-14
description: เรียนรู้วิธีสกัดไฟล์ที่ฝังอยู่และโหลดไฟล์โครงการด้วย Aspose.Tasks สำหรับ
  .NET บทเรียนนี้แสดงขั้นตอนการสกัดวัตถุ OLE อย่างละเอียด
linktitle: Collection of OLE Objects in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ดึงไฟล์ที่ฝังอยู่จากวัตถุ OLE ใน Aspose.Tasks
url: /th/net/advanced-concepts/ole-object-collection/
weight: 23
---

 translations.

Check for any missed items: Quick Answers list items bold phrase keep English, description translated. Ensure we keep markdown formatting.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงไฟล์ที่ฝังอยู่จากวัตถุ OLE ใน Aspose.Tasks

## บทนำ

ในบทแนะนำนี้คุณจะ **extract embedded files** ที่ถูกเก็บเป็นวัตถุ OLE ภายในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ไม่ว่าคุณจะต้องการดึงเอกสาร Word ที่เชื่อมโยง, ตาราง Excel, หรือไฟล์ rich‑text ขั้นตอนด้านล่างจะแสดงวิธี **load project file**, ค้นหาทุกรายการ OLE, และเขียนเนื้อหาไบนารีกลับไปยังดิสก์ เมื่อเสร็จคุณจะคุ้นเคยกับกระบวนการ **c# extract ole** ที่สมบูรณ์ซึ่งคุณสามารถนำกลับมาใช้ใหม่ในแอปพลิเคชันของคุณ

## คำตอบอย่างรวดเร็ว
- **What does “extract embedded files” mean?** หมายถึงการอ่านข้อมูลไบนารีของวัตถุ OLE และบันทึกเป็นไฟล์แยกต่างหากบนดิสก์.  
- **Which API method loads the project?** `new Project(filePath)` จากเนมสเปซ Aspose.Tasks.  
- **Can I export OLE objects of any type?** รองรับเฉพาะฟอร์แมตที่ Aspose.Tasks สามารถจดจำได้ (เช่น RTF, Word, Excel).  
- **Do I need a license for this?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “extract embedded files” คืออะไรในบริบทของวัตถุ OLE?

OLE (Object Linking and Embedding) ทำให้ไฟล์ Project สามารถบรรจุสำเนาครบของเอกสารภายนอกได้ การดึงไฟล์ที่ฝังอยู่เหล่านั้นทำให้คุณเข้าถึงเนื้อหาต้นฉบับโดยตรงโดยไม่ต้องเปิดไฟล์ Project ใน Microsoft Project.

## ทำไมต้องดึงไฟล์ที่ฝังอยู่จากวัตถุ OLE?

- **Preserve original data:** เก็บสำเนาสำรองของเอกสารที่แนบทุกไฟล์.  
- **Automate reporting:** ดึงรายงาน Word หรือ Excel จากหลายโครงการในชุดเดียว.  
- **Integrate with other systems:** ส่งไฟล์ที่ดึงออกไปยังระบบจัดการเอกสารหรือกระบวนการวิเคราะห์.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ตรวจสอบว่าคุณมี:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ (2019, 2022 หรือใหม่กว่า).  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดและติดตั้งจาก [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – คุณควรคุ้นเคยกับการวนลูป, คอลเลกชัน, และการทำ I/O ไฟล์.  

## นำเข้า Namespaces

To begin, import the necessary namespaces into your project:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;
```

## ขั้นตอนที่ 1: โหลดไฟล์ Project

แรก, โหลดไฟล์ Project ที่มีวัตถุ OLE ที่คุณต้องการดึงออก:

```csharp
var project = new Project(DataDir + "Embedded.mpp");
```

> **Tip:** `DataDir` ควรชี้ไปยังโฟลเดอร์ที่ไฟล์ `.mpp` ของคุณอยู่ ขั้นตอนนี้ทำให้ตรงตามข้อกำหนด **load project file**.

## ขั้นตอนที่ 2: กำหนดส่วนขยายไฟล์

สร้างตาราง lookup ที่แมปตัวระบุ `FileFormat` ของ OLE ไปยังชื่อไฟล์ผลลัพธ์ที่ต้องการ ทำให้การ **export ole objects** มีส่วนขยายที่ถูกต้องง่ายขึ้น:

```csharp
IDictionary<string, string> extensions = new Dictionary<string, string>
{
    { "RTF", "_rtfFile_out.rtf" },
    { "MSWordDoc", "_wordFile_out.docx" },
    { "ExcelML12", "_excelFile_out.xlsx" }
};
```

## ขั้นตอนที่ 3: วนลูปผ่านวัตถุ OLE และดึงไฟล์ที่ฝังอยู่

ตอนนี้ให้เดินผ่านแต่ละวัตถุ OLE ในโครงการ, ตรวจสอบว่าฟอร์แมตของมันเป็นฟอร์แมตที่เรารองรับ, แล้วเขียนเนื้อหาไบนารีไปยังไฟล์ใหม่:

```csharp
foreach (var oleObject in project.OleObjects)
{
    if (string.IsNullOrEmpty(oleObject.FileFormat) || !extensions.ContainsKey(oleObject.FileFormat))
    {
        continue;
    }

    var path = OutDir + "EmbeddedContent_" + extensions[oleObject.FileFormat];
    using (var stream = new FileStream(path, FileMode.Create))
    {
        stream.Write(oleObject.Content, 0, oleObject.Content.Length);
    }
}
```

> **Pro tip:** `OutDir` ควรเป็นไดเรกทอรีที่สามารถเขียนได้ โค้ดข้างต้นจะสร้างไฟล์เช่น `EmbeddedContent__wordFile_out.docx` ซึ่งทำให้ **extract ole objects** จากโครงการได้อย่างมีประสิทธิภาพ.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| ไม่มีไฟล์ถูกสร้าง | `OutDir` ไม่มีอยู่หรือไม่มีสิทธิ์การเขียน | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และแอปพลิเคชันมีสิทธิ์การเขียน. |
| รูปแบบไฟล์ที่ไม่คาดคิด | `FileFormat` ของวัตถุ OLE ไม่อยู่ในพจนานุกรม | เพิ่มฟอร์แมตที่ขาดหายไปลงในพจนานุกรม `extensions`. |
| วัตถุ OLE ขนาดใหญ่ทำให้เกิดความกดดันของหน่วยความจำ | โหลดวัตถุขนาดใหญ่หลายตัวพร้อมกัน | ประมวลผลวัตถุทีละหนึ่งตามที่แสดง หรือสตรีมโดยตรงไปยังดิสก์. |

## คำถามที่พบบ่อย

**Q: What is an OLE object?**  
A: OLE (Object Linking and Embedding) เป็นเทคโนโลยีที่ทำให้สามารถฝังหรือเชื่อมโยงไฟล์จากแอปพลิเคชันอื่นภายในเอกสารได้.

**Q: How do I install Aspose.Tasks for .NET?**  
A: คุณสามารถดาวน์โหลด Aspose.Tasks for .NET จาก [here](https://releases.aspose.com/tasks/net/) และทำตามคำแนะนำการติดตั้งที่ให้ไว้.

**Q: Can I work with OLE objects in Aspose.Tasks without prior knowledge of C#?**  
A: แม้ว่าความรู้พื้นฐานของ C# จะเป็นที่แนะนำ, Aspose.Tasks มีเอกสารและบทแนะนำที่ครอบคลุมเพื่อช่วยผู้ใช้เริ่มต้นไม่ว่าพื้นฐานการเขียนโปรแกรมของพวกเขาจะเป็นอย่างไร.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: ใช่, คุณสามารถใช้การทดลองฟรีของ Aspose.Tasks ได้จาก [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: คุณสามารถขอรับการสนับสนุนและถามคำถามได้ในฟอรั่ม Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**อัปเดตล่าสุด:** 2026-03-14  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}