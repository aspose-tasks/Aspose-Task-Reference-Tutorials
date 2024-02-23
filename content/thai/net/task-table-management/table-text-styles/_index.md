---
title: การปรับแต่งคำแนะนำสไตล์ข้อความตารางใน Aspose.Tasks
linktitle: กำหนดค่าลักษณะข้อความตารางใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ปรับปรุงการแสดงภาพโครงการด้วย Aspose.Tasks สำหรับ .NET เรียนรู้วิธีกำหนดค่ารูปแบบข้อความตารางทีละขั้นตอน เพิ่มประสิทธิภาพและการนำเสนอ
type: docs
weight: 14
url: /th/net/task-table-management/table-text-styles/
---
## การแนะนำ
ในโลกของการจัดการโครงการ การแสดงภาพงานอย่างมีประสิทธิผลถือเป็นสิ่งสำคัญต่อความสำเร็จ Aspose.Tasks for .NET มอบโซลูชันอันทรงพลังในการปรับแต่งสไตล์ข้อความตาราง ซึ่งช่วยให้คุณปรับแต่งรูปลักษณ์ของรายการข้อความในโครงการของคุณได้ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการกำหนดค่าลักษณะข้อความตารางโดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
-  Aspose.Tasks for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks for .NET เวอร์ชันล่าสุดแล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณ แทนที่ "Your Document Directory" ในโค้ดด้วยเส้นทางจริง
-  ใบอนุญาต Aspose ที่ถูกต้อง: ตัวอย่างนี้ต้องการใบอนุญาต Aspose ที่ถูกต้อง คุณสามารถซื้อใบอนุญาตแบบเต็มได้[ที่นี่](https://purchase.aspose.com/buy) หรือได้รับใบอนุญาตชั่วคราว 30 วัน[ที่นี่](https://purchase.aspose.com/temporary-license/).
## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มเขียนโค้ด ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: โหลดโปรเจ็กต์และตั้งค่าคุณสมบัติของโปรเจ็กต์
```csharp
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.NewTasksAreManual, false);
```
## ขั้นตอนที่ 2: เข้าถึงมุมมองแผนภูมิแกนต์
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
## ขั้นตอนที่ 3: ปรับแต่งสไตล์ข้อความชื่องาน
```csharp
var style1 = new TableTextStyle(1);
style1.Field = Field.TaskName;
style1.Font = new FontDescriptor("Impact", 12F, FontStyles.Bold | FontStyles.Italic);
view.TableTextStyles.Add(style1);
```
## ขั้นตอนที่ 4: ปรับแต่งลักษณะข้อความระยะเวลางาน
```csharp
var style2 = new TableTextStyle(2);
style2.Field = Field.TaskDurationText;
style2.Font = new FontDescriptor("Impact", 16F, FontStyles.Underline);
view.TableTextStyles.Add(style2);
```
## ขั้นตอนที่ 5: บันทึกโครงการด้วยสไตล์ที่กำหนดเอง
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(DataDir + "WorkWithTableTextStyle_out.mpp", options);
```
## ขั้นตอนที่ 6: จัดการข้อยกเว้นใบอนุญาต
```csharp
catch (NotSupportedException ex)
{
    Console.WriteLine(
        ex.Message
        + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [Aspose](http://www.aspose.com/purchase/default.aspx");
}
```
## บทสรุป
การปรับแต่งสไตล์ข้อความตารางใน Aspose.Tasks สำหรับ .NET มอบวิธีที่ยืดหยุ่นและมีประสิทธิภาพในการปรับปรุงการแสดงภาพโครงการของคุณ ด้วยขั้นตอนง่ายๆ ไม่กี่ขั้นตอน คุณสามารถสร้างประสบการณ์การจัดการโครงการที่ตรงตามความต้องการและมีประสิทธิภาพมากขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET โดยไม่มีใบอนุญาตได้หรือไม่
 ไม่ จำเป็นต้องมีใบอนุญาต Aspose ที่ถูกต้องสำหรับฟังก์ชันนี้ คุณสามารถขอรับใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy) หรือได้รับใบอนุญาตชั่วคราว 30 วัน[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะอัปเดตลักษณะแบบอักษรสำหรับคุณลักษณะงานอื่น ๆ ได้อย่างไร
 เพียงสร้างเพิ่มเติม`TableTextStyle` อินสแตนซ์โดยระบุฟิลด์และการตั้งค่าแบบอักษรที่ต้องการ
### มีรุ่นทดลองใช้สำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองได้[ที่นี่](https://releases.aspose.com/).
### มีตัวเลือกการแสดงภาพอื่น ๆ จาก Aspose.Tasks หรือไม่
ใช่ Aspose.Tasks นำเสนอฟีเจอร์การแสดงภาพที่หลากหลายเพื่อตอบสนองความต้องการการจัดการโครงการที่แตกต่างกัน
### ฉันสามารถปรับแต่งสไตล์สำหรับประเภทงานเฉพาะได้หรือไม่?
แน่นอน คุณสามารถขยายการปรับแต่งไปยังงานประเภทต่างๆ ได้โดยการปรับการตั้งค่าฟิลด์และแบบอักษรให้สอดคล้องกัน