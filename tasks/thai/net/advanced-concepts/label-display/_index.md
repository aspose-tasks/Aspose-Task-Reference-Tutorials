---
date: 2026-03-08
description: Learn how to set label display and customize day label in project management
  using Aspose.Tasks for .NET, improving readability and clarity.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: How to Set Label Display in Aspose.Tasks for .NET
url: /th/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าการแสดงป้ายใน Aspose.Tasks สำหรับ .NET

## Introduction

เมื่อคุณกำลังสร้างโซลูชันการจัดการโครงการด้วย **Aspose.Tasks for .NET** การสามารถ **how to set label** ตัวเลือกเป็นสิ่งสำคัญสำหรับทำให้กำหนดการอ่านง่าย ไม่ว่าคุณจะต้องการความแม่นยำระดับนาทีหรือมุมมองระดับปี การปรับแต่งการแสดงป้ายช่วยให้คุณนำเสนอไทม์ไลน์ได้ตามที่ผู้มีส่วนได้ส่วนเสียคาดหวัง ในบทแนะนำนี้เราจะเดินผ่านกระบวนการตั้งค่าการแสดงป้ายสำหรับนาที ชั่วโมง วัน สัปดาห์ เดือน และปี และเราจะยังแสดงวิธี **customize day label** รูปแบบเพื่อความชัดเจนสูงสุด.

## Quick Answers
- **What does “how to set label” mean?** หมายถึงการกำหนดค่าคุณสมบัติ `DisplayOptions` ที่ควบคุมว่าหน่วยเวลาแสดงอย่างไรในไฟล์โครงการ  
- **Which label can I change?** นาที ชั่วโมง วัน สัปดาห์ เดือน และปี ทั้งหมดสามารถกำหนดค่าได้  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต; เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ  
- **Is this supported on .NET Core?** ใช่, API ทำงานกับ .NET Core, .NET 5/6, และ .NET Framework เต็มรูปแบบ  
- **Can I change the label at runtime?** แน่นอน – คุณสามารถแก้ไขตัวเลือกการแสดงได้ทุกเมื่อก่อนบันทึกโครงการ

## What is label display in Aspose.Tasks?

การแสดงป้ายกำหนดเป็นการกำหนดการแสดงผลเป็นข้อความของหน่วยเวลา (นาที, ชั่วโมง, วัน ฯลฯ) บนแผนภูมิ Gantt และสเกลเวลา โดยการตั้งค่าคุณสมบัติ `DisplayOptions` ที่เหมาะสม คุณจะสั่งให้ Aspose.Tasks เรนเดอร์หน่วยเหล่านั้น ซึ่งสามารถปรับปรุงความอ่านง่ายของโครงการได้อย่างมาก

## Why customize label displays?

- **Improved readability:** ผู้มีส่วนได้ส่วนเสียสามารถเข้าใจระดับความละเอียดของกำหนดการได้ทันที  
- **Consistent reporting:** ทำให้ผลลัพธ์ภาพสอดคล้องกับมาตรฐานองค์กร (เช่น ใช้ “Mo” สำหรับเดือน)  
- **Flexibility:** สลับระหว่างมุมมองละเอียดและระดับสูงโดยไม่ต้องเปลี่ยนแปลงข้อมูลกำหนดการพื้นฐาน

## Prerequisites

1. **C# knowledge** – ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และโครงสร้างโครงการ .NET  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดและติดตั้งไลบรารีจาก [here](https://releases.aspose.com/tasks/net/)  
3. **Development environment** – Visual Studio, VS Code, หรือ IDE ใด ๆ ที่รองรับการพัฒนา .NET

## Import Namespaces

ก่อนเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## How to set label display for minutes

### 1. Displaying Minute Labels

เพื่อกำหนดป้ายนาที ให้ใช้คุณสมบัติ `MinuteLabel` :

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## How to set label display for hours

### 2. Displaying Hour Labels

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Customize day label display

### 3. Displaying Day Labels

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## How to set label display for weeks

### 4. Displaying Week Labels

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## How to set label display for months

### 5. Displaying Month Labels

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## How to set label display for years

### 6. Displaying Year Labels

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Common Pitfalls & Tips

- **Tip:** ควรตั้งค่าการแสดงป้าย *ก่อน* บันทึกโครงการ; การเปลี่ยนแปลงหลังจากบันทึกจะไม่แสดงในไฟล์  
- **Pitfall:** การใช้ค่า enum ที่ไม่รองรับจะทำให้เกิด `ArgumentException`. ให้ใช้ enum `*LabelDisplay` ที่จัดเตรียมไว้เท่านั้น  
- **Tip:** หากต้องการสไตล์ป้ายที่แตกต่างสำหรับมุมมองแยกกัน ให้สร้างอินสแตนซ์ `Project` แยกหรือคัดลอกอ็อบเจ็กต์ `DisplayOptions`

## Conclusion

โดยการเชี่ยวชาญการตั้งค่า **how to set label** ใน Aspose.Tasks คุณจะได้การควบคุมระดับละเอียดต่อการนำเสนอภาพของกำหนดการโครงการ ไม่ว่าคุณจะปรับแต่งป้ายวันสำหรับบอร์ดสครัมประจำวันหรือปรับป้ายปีสำหรับแผนงานหลายปี การตั้งค่าเหล่านี้ช่วยให้คุณส่งมอบเอกสารโครงการที่ชัดเจนและเป็นมืออาชีพมากขึ้น

## FAQ's

### Q1: ฉันสามารถปรับแต่งการแสดงป้ายสำหรับส่วนเฉพาะของโครงการได้หรือไม่?

A1: ได้, Aspose.Tasks for .NET อนุญาตให้ควบคุมการแสดงป้ายอย่างละเอียด สามารถปรับแต่งสำหรับส่วนเฉพาะของโครงการตามความต้องการ

### Q2: Aspose.Tasks รองรับเฟรมเวิร์ก .NET ยอดนิยมหรือไม่?

A2: ใช่, Aspose.Tasks for .NET รองรับเฟรมเวิร์ก .NET ต่าง ๆ รวมถึง .NET Core และ .NET Framework

### Q3: ฉันสามารถเปลี่ยนการแสดงป้ายแบบไดนามิกตามความต้องการของโครงการได้หรือไม่?

A3: แน่นอน, ความยืดหยุ่นของ Aspose.Tasks for .NET อนุญาตให้ปรับการแสดงป้ายแบบไดนามิกตามความต้องการของโครงการที่เปลี่ยนแปลงไป

### Q4: มีข้อจำกัดใดในการปรับแต่งการแสดงป้ายหรือไม่?

A4: Aspose.Tasks for .NET มีตัวเลือกการปรับแต่งการแสดงป้ายอย่างกว้างขวาง โดยมีข้อจำกัดเพียงเล็กน้อย ให้ผู้ใช้มีความยืดหยุ่นเพียงพอ

### Q5: Aspose.Tasks รองรับการรวมกับเครื่องมือการจัดการโครงการอื่นหรือไม่?

A5: ใช่, Aspose.Tasks มีความสามารถในการรวมอย่างราบรื่น ช่วยให้ทำงานร่วมกับเครื่องมือและแพลตฟอร์มการจัดการโครงการอื่น ๆ ได้

---

**อัปเดตล่าสุด:** 2026-03-08  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}