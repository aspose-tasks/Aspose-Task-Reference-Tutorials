---
title: คอลเลกชันของวัตถุ OLE ใน Aspose.Tasks
linktitle: คอลเลกชันของวัตถุ OLE ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการอ็อบเจ็กต์ OLE ใน Aspose.Tasks สำหรับ .NET ด้วยบทช่วยสอนที่ครอบคลุมนี้ เชี่ยวชาญการจัดการไฟล์ที่ฝังอยู่ภายในเอกสารโครงการได้อย่างง่ายดาย
type: docs
weight: 23
url: /th/net/advanced-concepts/ole-object-collection/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะเจาะลึกการจัดการออบเจ็กต์ OLE (การเชื่อมโยงและการฝังวัตถุ) ใน Aspose.Tasks สำหรับ .NET วัตถุ OLE ช่วยให้ผู้ใช้สามารถฝังหรือเชื่อมโยงไฟล์จากแอปพลิเคชันอื่นภายในไฟล์โครงการได้ เราจะอธิบายวิธีการทำงานกับคอลเลกชันของออบเจ็กต์เหล่านี้ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;


```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

ขั้นแรก โหลดไฟล์โครงการที่มีวัตถุ OLE:

```csharp
var project = new Project(DataDir + "Embedded.mpp");
```

## ขั้นตอนที่ 2: กำหนดนามสกุลไฟล์

ถัดไป กำหนดนามสกุลไฟล์ที่เกี่ยวข้องกับวัตถุ OLE:

```csharp
IDictionary<string, string> extensions = new Dictionary<string, string>
{
    { "RTF", "_rtfFile_out.rtf" },
    { "MSWordDoc", "_wordFile_out.docx" },
    { "ExcelML12", "_excelFile_out.xlsx" }
};
```

## ขั้นตอนที่ 3: วนซ้ำวัตถุ OLE

ตอนนี้ วนซ้ำวัตถุ OLE ภายในโครงการ:

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

## บทสรุป

โดยสรุป การจัดการอ็อบเจ็กต์ OLE ใน Aspose.Tasks สำหรับ .NET มีความสำคัญอย่างยิ่งต่อการจัดการไฟล์ที่ฝังหรือเชื่อมโยงภายในเอกสารโครงการ ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถทำงานกับคอลเลกชันอ็อบเจ็กต์ OLE ในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### Q1: วัตถุ OLE คืออะไร

A1: วัตถุ OLE (การเชื่อมโยงและการฝังวัตถุ) เป็นเทคโนโลยีที่ช่วยให้สามารถฝังหรือเชื่อมโยงไฟล์จากแอปพลิเคชันอื่นภายในเอกสารได้

### คำถามที่ 2: ฉันจะติดตั้ง Aspose.Tasks สำหรับ .NET ได้อย่างไร

 A2: คุณสามารถดาวน์โหลด Aspose.Tasks สำหรับ .NET ได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้

### คำถามที่ 3: ฉันสามารถทำงานกับวัตถุ OLE ใน Aspose.Tasks โดยไม่ต้องมีความรู้ C# มาก่อนได้หรือไม่

ตอบ 3: แม้ว่าเราจะแนะนำให้ใช้ความรู้พื้นฐานเกี่ยวกับ C# แต่ Aspose.Tasks ก็มีเอกสารและบทช่วยสอนที่ครอบคลุมเพื่อช่วยให้ผู้ใช้เริ่มต้นได้โดยไม่คำนึงถึงพื้นฐานการเขียนโปรแกรม

### คำถามที่ 4: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่

 A4: ได้ คุณสามารถทดลองใช้ Aspose.Tasks ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน

 A5: คุณสามารถขอรับการสนับสนุนและถามคำถามได้ที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).