---
title: อัปเดตและกำหนดเวลาโครงการ MS ใน Aspose.Tasks
linktitle: อัปเดตโครงการและกำหนดเวลางานที่ยังไม่เสร็จใหม่ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอัปเดตและกำหนดเวลาไฟล์ MS Project ใหม่โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ Java
weight: 23
url: /th/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อัปเดตและกำหนดเวลาโครงการ MS ใน Aspose.Tasks

## การแนะนำ
Microsoft Project เป็นซอฟต์แวร์การจัดการโครงการที่ใช้กันอย่างแพร่หลายซึ่งช่วยให้ผู้ใช้สามารถจัดการงาน ทรัพยากร และไทม์ไลน์ได้อย่างมีประสิทธิภาพ Aspose.Tasks สำหรับ Java มีชุด API ที่มีประสิทธิภาพเพื่อจัดการไฟล์ Microsoft Project โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีอัปเดตไฟล์ MS Project และกำหนดเวลางานที่ยังไม่เสร็จสมบูรณ์ใหม่โดยใช้ Aspose.Tasks สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
เริ่มต้นวัตถุ Project ใหม่และกำหนดงานภายในวัตถุนั้นพร้อมกับระยะเวลาและการขึ้นต่อกัน
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// กำหนดงานและระยะเวลา
// ...
// กำหนดการพึ่งพางาน
// ...
// บันทึกสถานะโปรเจ็กต์เริ่มต้น
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## ขั้นตอนที่ 2: อัปเดตงานโครงการ
อัปเดตงานโครงการเพื่อทำเครื่องหมายว่าเสร็จสมบูรณ์จนถึงวันที่กำหนด
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// บันทึกโครงการที่อัปเดต
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## ขั้นตอนที่ 3: กำหนดเวลางานที่ยังไม่เสร็จใหม่
กำหนดเวลางานที่ยังไม่เสร็จสิ้นใหม่ให้เริ่มหลังจากวันที่ระบุ
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// บันทึกโครงการที่กำหนดเวลาใหม่
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอัปเดตไฟล์ MS Project และกำหนดเวลางานที่ยังไม่เสร็จสมบูรณ์ใหม่โดยใช้ Aspose.Tasks สำหรับ Java สิ่งนี้มีประโยชน์อย่างยิ่งในสถานการณ์ที่ไทม์ไลน์ของโครงการจำเป็นต้องมีการปรับเปลี่ยนตามความคืบหน้าหรือลำดับความสำคัญที่เปลี่ยนแปลง

## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: ใช่ Aspose.Tasks for Java มี API ที่มีประสิทธิภาพเพื่อจัดการงาน การขึ้นต่อกัน ทรัพยากร และองค์ประกอบโปรเจ็กต์อื่นๆ ได้อย่างมีประสิทธิภาพ
### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ได้ มีใบอนุญาตชั่วคราวให้ซื้อได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: คุณสามารถดูเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/java/) สำหรับคำแนะนำที่ครอบคลุมและการอ้างอิง API
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
