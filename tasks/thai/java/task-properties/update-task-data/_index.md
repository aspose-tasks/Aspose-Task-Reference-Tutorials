---
date: 2026-03-03
description: เรียนรู้วิธีอัปเดตข้อมูลงานเป็นรูปแบบ MPP ด้วย Aspose.Tasks Java. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการจัดการโครงการที่มีประสิทธิภาพ.
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – อัปเดตข้อมูลงานเป็นรูปแบบ MPP
url: /th/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อัปเดตข้อมูลงานเป็นรูปแบบ MPP ใน Aspose.Tasks

## คำแนะนำ
ยินดีต้อนรับสู่คู่มือแบบขั้นตอนของเราเกี่ยวกับ **การอัปเดตข้อมูลงานเป็นรูปแบบ MPP ด้วย Aspose.Tasks for Java** ในบทเรียนนี้คุณจะได้เรียนรู้วิธีการจัดการไฟล์โครงการโดยใช้โปรแกรม *aspose tasks java* ตั้งแต่การสร้างงานสรุปจนถึงการแปลงโครงการ XML เป็นไฟล์ MPP เมื่อเสร็จสิ้นคุณจะสามารถจัดการงานโครงการได้อย่างมีประสิทธิภาพและผสานโซลูชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไร?** การอัปเดตข้อมูลงานและบันทึกโครงการเป็นไฟล์ MPP ด้วย Aspose.Tasks for Java  
- **ต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต; มีการทดลองใช้ฟรีให้บริการ  
- **IDE ใดดีที่สุด?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, VS Code) จะทำงานได้  
- **สามารถแปลง XML เป็น MPP ได้หรือไม่?** ได้ – ตัวอย่างจะโหลดโครงการ XML แล้วบันทึกเป็นไฟล์ MPP  
- **สร้างงานกี่งาน?** ตัวอย่างสร้างงานหลักหนึ่งงาน, งานสรุปหนึ่งงาน, และงานเพิ่มเติมอีกสิบงาน

## Aspose.Tasks for Java คืออะไร?
Aspose.Tasks for Java เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถอ่าน, เขียน, และแก้ไขไฟล์ Microsoft Project (MPP, XML และอื่น ๆ) ได้โดยไม่ต้องติดตั้ง Microsoft Project รองรับการจัดการระดับโครงการเต็มรูปแบบ รวมถึงการสร้างงาน, การจัดการข้อจำกัด, และการแปลงรูปแบบไฟล์

## ทำไมต้องใช้ Aspose.Tasks Java สำหรับการจัดการโครงการ?
- **การควบคุมเต็มรูปแบบ** บนคุณสมบัติงาน เช่น วันที่เริ่มต้น, ระยะเวลา, และข้อจำกัด  
- **การแปลงอย่างไร้รอยต่อ** ระหว่าง XML และ MPP ทำให้สามารถผสานกับสายงานข้อมูลโครงการที่มีอยู่ได้  
- **ไม่มี COM interop** – เป็น Java แท้ ๆ เหมาะสำหรับสภาพแวดล้อมข้ามแพลตฟอร์ม  
- **ประสิทธิภาพสูง** สำหรับไฟล์โครงการขนาดใหญ่ ทำให้เหมาะกับโซลูชันระดับองค์กร

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มทำตามบทเรียน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- Aspose.Tasks for Java: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks แล้ว คุณสามารถดาวน์โหลดได้จาก [release page](https://releases.aspose.com/tasks/java/)  
- Java Development Kit (JDK): ตรวจสอบว่ามี Java ติดตั้งอยู่ในระบบของคุณ  
- Integrated Development Environment (IDE): ใช้ IDE ที่คุณชื่นชอบสำหรับการพัฒนา Java

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ ตัวอย่างโค้ดต่อไปนี้แสดงวิธีนำเข้าแพ็กเกจ:

```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```

## วิธีสร้างงานสรุป
งานสรุปเป็นการจัดกลุ่มงานย่อยที่เกี่ยวข้อง เพื่อให้คุณมองเห็นภาพรวมของแพคเกจงาน ในโค้ดด้านล่างเราจะสร้างงานสรุปและแนบงานแรกเป็นลูกของมัน

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## วิธีตั้งค่าวันเริ่มต้นสำหรับงาน
การตั้งค่าวันเริ่มต้นเป็นสิ่งสำคัญสำหรับการกำหนดตารางเวลาอย่างแม่นยำ ตัวอย่างใช้อินสแตนซ์ `Calendar` เพื่อกำหนดวันเริ่มต้นของโครงการและกำหนดให้กับงาน

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## วิธีแปลง XML เป็น MPP
API สามารถอ่านไฟล์โครงการ XML และบันทึกโดยตรงเป็นไฟล์ MPP ทำให้การย้ายข้อมูลจากรูปแบบเก่าเป็นเรื่องง่าย

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## วิธีตั้งกำหนดเวลาและเพิ่มบันทึกย่อของงาน
กำหนดเวลาช่วยให้งานดำเนินไปตามแผน ในขณะที่บันทึกย่อให้ข้อมูลบริบทแก่สมาชิกทีม

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## วิธีกำหนดข้อจำกัดของงานและอัปเดตระยะเวลาของงาน
ข้อจำกัดเช่น *Finish No Later Than* ช่วยกำหนดทิศทางให้กับตัวจัดตารางเวลา คุณยังสามารถเปลี่ยนรูปแบบระยะเวลาให้สอดคล้องกับจำนวนวันโดยประมาณได้

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## วิธีสร้างงานเพิ่มเติม (การจัดการงานในโครงการ)
ลูปด้านล่างแสดงวิธีการสร้างงานหลายงานโดยอัตโนมัติ ซึ่งเป็นความต้องการทั่วไปเมื่อทำการนำเข้าข้อมูลจำนวนมาก

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## วิธีบันทึกโครงการ (ส่งออกเป็น MPP)
สุดท้ายให้บันทึกการเปลี่ยนแปลงโดยการบันทึกโครงการเป็นไฟล์ MPP

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

โดยทำตามขั้นตอนเหล่านี้ คุณได้ **อัปเดตข้อมูลงานเป็นรูปแบบ MPP ด้วย aspose tasks java** อย่างสำเร็จแล้ว ตอนนี้คุณมีพื้นฐานที่มั่นคงสำหรับการจัดการงานโครงการ, การสร้างงานสรุป, การตั้งค่าวันเริ่มต้น, และการแปลงโครงการ XML เป็น MPP

## สรุป
ขอแสดงความยินดี! คุณได้ทำคู่มือฉบับครบถ้วนเกี่ยวกับการอัปเดตข้อมูลงานเป็นรูปแบบ MPP ด้วย Aspose.Tasks for Java ไลบรารีที่ทรงพลังนี้ทำให้การจัดการงานโครงการง่ายขึ้น เป็นเครื่องมือที่มีคุณค่าสำหรับนักพัฒนา Java ที่ต้อง **จัดการงานโครงการ** อย่างเป็นโปรแกรม

## คำถามที่พบบ่อย

### ถาม: ฉันสามารถหาเอกสาร Aspose.Tasks for Java ได้ที่ไหน?
ตอบ: เอกสารพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/tasks/java/)

### ถาม: ฉันจะดาวน์โหลด Aspose.Tasks for Java ได้อย่างไร?
ตอบ: คุณสามารถดาวน์โหลดได้จาก [release page](https://releases.aspose.com/tasks/java/)

### ถาม: มีการทดลองใช้ฟรีหรือไม่?
ตอบ: มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)

### ถาม: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
ตอบ: เยี่ยมชมฟอรั่มสนับสนุน [ที่นี่](https://forum.aspose.com/c/tasks/15)

### ถาม: คุณมีไลเซนส์ชั่วคราวสำหรับการทดสอบหรือไม่?
ตอบ: มี, คุณสามารถรับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-03  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11 (latest)  
**ผู้เขียน:** Aspose