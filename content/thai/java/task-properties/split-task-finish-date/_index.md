---
title: แยกวันที่เสร็จสิ้นงานใน Aspose.Tasks
linktitle: แยกวันที่เสร็จสิ้นงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีแบ่งวันที่เสร็จสิ้นงานได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงการจัดการโครงการด้วยไทม์ไลน์ที่แม่นยำ
type: docs
weight: 28
url: /th/java/task-properties/split-task-finish-date/
---
## การแนะนำ
ในการจัดการโครงการ การทำความเข้าใจลำดับเวลาของงานเป็นสิ่งสำคัญสำหรับการดำเนินโครงการให้สำเร็จ Aspose.Tasks สำหรับ Java มีคุณสมบัติอันทรงพลังเพื่อจัดการงานโปรเจ็กต์ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกการแยกวันที่เสร็จสิ้นของงานโดยใช้ Aspose.Tasks ซึ่งช่วยให้คุณจัดการไทม์ไลน์ของโปรเจ็กต์ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการรวมแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: ค้นหางานแยก
ค้นหางานที่คุณต้องการแบ่งภายในโครงการ:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// อ่านโครงการ
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## ขั้นตอนที่ 2: ค้นหาปฏิทินโครงการ
รับปฏิทินโครงการเพื่อการคำนวณวันที่ที่แม่นยำ:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## ขั้นตอนที่ 3: คำนวณวันที่เสร็จสิ้นงานด้วยระยะเวลาที่ต่างกัน
ตอนนี้ ให้คำนวณวันที่เสร็จสิ้นของงานตามระยะเวลาต่างๆ:
## ขั้นตอนที่ 3.1: ระยะเวลา 8 ชั่วโมง
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
ทำซ้ำโค้ดด้านบนตามระยะเวลาที่แตกต่างกัน โดยปรับชั่วโมงให้เหมาะสม
## บทสรุป
การเรียนรู้ศิลปะในการจัดการวันที่เสร็จสิ้นของงานเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ Aspose.Tasks สำหรับ Java ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณปรับปรุงไทม์ไลน์ของโปรเจ็กต์ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันจะดาวน์โหลด Aspose.Tasks สำหรับ Java ได้อย่างไร
 A1: คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
### คำถามที่ 2: ฉันจะหาเอกสารสำหรับ Aspose.Tasks ได้ที่ไหน
 A2: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/java/).
### คำถามที่ 3: ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 A3: รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### คำถามที่ 4: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 A4: เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/tasks/15).
### คำถามที่ 5: ฉันสามารถซื้อ Aspose.Tasks ได้หรือไม่
 A5: ใช่ คุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy).