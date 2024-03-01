---
title: การกำหนดค่ามุมมองการใช้งานใน Aspose.Tasks
linktitle: การกำหนดค่ามุมมองการใช้งานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่ามุมมองการใช้งานใน Aspose.Tasks สำหรับ .NET ปรับปรุงการแสดงภาพโครงการด้วยขั้นตอนโดยละเอียด ดาวน์โหลดห้องสมุดทันที!
type: docs
weight: 17
url: /th/net/text-view-configuration/usage-views/
---
## การแนะนำ
หากคุณเป็นนักพัฒนา .NET ที่ต้องการปรับปรุงความสามารถในการจัดการโครงการของคุณ Aspose.Tasks เป็นเครื่องมืออันทรงพลังที่ช่วยให้คุณจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเน้นที่การกำหนดค่ามุมมองการใช้งานโดยใช้ Aspose.Tasks สำหรับ .NET ปฏิบัติตามเพื่อรับข้อมูลเชิงลึกเกี่ยวกับการเรนเดอร์มุมมองการใช้งานพร้อมรายละเอียดเพื่อให้เห็นภาพโครงการได้ดีขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  ไลบรารี Aspose.Tasks: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Tasks ที่รวมอยู่ในโปรเจ็กต์ .NET ของคุณ ถ้าไม่คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/) และปฏิบัติตามคำแนะนำในการติดตั้ง
- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีที่เก็บเอกสารโครงการของคุณ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ในข้อมูลโค้ดด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ
## นำเข้าเนมสเปซ
ในข้อมูลโค้ดที่ให้มา คุณจะสังเกตเห็นการใช้เนมสเปซบางตัว อย่าลืมรวมสิ่งเหล่านี้ไว้ในโปรเจ็กต์ของคุณเพื่อการบูรณาการที่ราบรื่น:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: แสดงผลมุมมองการใช้งานพร้อมรายละเอียด
เริ่มต้นด้วยการแสดงมุมมองการใช้งานพร้อมรายละเอียด ทำตามขั้นตอนเหล่านี้:
## ขั้นตอนที่ 1.1: โหลดโปรเจ็กต์
```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## ขั้นตอนที่ 1.2: รับมุมมอง
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## ขั้นตอนที่ 1.3: ปรับแต่งการตั้งค่ามุมมอง
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## ขั้นตอนที่ 1.4: บันทึกโครงการเป็น PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## ขั้นตอนที่ 2: แสดงคอลัมน์ส่วนหัวรายละเอียด
ในขั้นตอนนี้ เราจะแก้ไขการตั้งค่ามุมมองเพื่อแสดงคอลัมน์ส่วนหัวรายละเอียดและบันทึกโครงการเป็น PDF:
## ขั้นตอนที่ 2.1: แสดงคอลัมน์ส่วนหัวรายละเอียด
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## ขั้นตอนที่ 2.2: ทำซ้ำส่วนหัวรายละเอียดในทุกแถว
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## ขั้นตอนที่ 2.3: บันทึกโครงการเป็น PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## บทสรุป
ยินดีด้วย! คุณได้กำหนดค่ามุมมองการใช้งานใน Aspose.Tasks เรียบร้อยแล้ว บทช่วยสอนนี้เป็นรากฐานสำหรับการจัดการโครงการและการแสดงภาพอย่างมีประสิทธิภาพโดยใช้ไลบรารี Aspose.Tasks

### คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารประกอบ Aspose.Tasks ได้ที่ไหน
 มีเอกสารประกอบครบถ้วน[ที่นี่](https://reference.aspose.com/tasks/net/).
### ถาม: ฉันจะดาวน์โหลด Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ดาวน์โหลดห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/net/).
### ถาม: ฉันจะซื้อ Aspose.Tasks ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Tasks[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ใช่ สำรวจการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ถาม: ต้องการความช่วยเหลือหรือมีคำถาม?
 เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/tasks/15).