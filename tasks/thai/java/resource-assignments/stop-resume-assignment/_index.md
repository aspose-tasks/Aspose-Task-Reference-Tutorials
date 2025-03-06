---
title: หยุดและดำเนินการมอบหมายทรัพยากรต่อใน Aspose.Tasks
linktitle: หยุดและดำเนินการมอบหมายทรัพยากรต่อใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการการมอบหมายทรัพยากรอย่างมีประสิทธิภาพใน Aspose.Tasks for Java ด้วยบทช่วยสอนทีละขั้นตอนนี้
weight: 23
url: /th/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# หยุดและดำเนินการมอบหมายทรัพยากรต่อใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีหยุดและดำเนินการมอบหมายทรัพยากรต่อโดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็น Java API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่จำเป็นต้องติดตั้ง Microsoft Project บนระบบของพวกเขา เราจะแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้เพื่อให้ง่ายต่อการปฏิบัติตาม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  ดาวน์โหลด Aspose.Tasks สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเข้าสู่โปรเจ็กต์ Java ของเรา:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
// โหลดไฟล์โครงการ
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 ในขั้นตอนนี้ เราจะโหลดไฟล์โครงการลงในไฟล์`Project` วัตถุโดยใช้เส้นทางไฟล์
## ขั้นตอนที่ 2: ทำซ้ำผ่านการกำหนดทรัพยากร
```java
// กำหนดวันที่ขั้นต่ำ
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// ทำซ้ำผ่านการมอบหมายทรัพยากร
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
ที่นี่ เรากำหนดวันที่ขั้นต่ำและเริ่มวนซ้ำตามการกำหนดทรัพยากรแต่ละรายการในโปรเจ็กต์
## ขั้นตอนที่ 3: ตรวจสอบวันที่หยุดและดำเนินการต่อ
```java
    // ตรวจสอบวันที่หยุด
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // ตรวจสอบวันที่ประวัติการทำงาน
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
ในขั้นตอนนี้ เราจะตรวจสอบว่าวันที่หยุดและดำเนินการต่อของการมอบหมายทรัพยากรแต่ละรายการอยู่ก่อนวันที่ขั้นต่ำหรือไม่ หากเป็นเช่นนั้น เราจะพิมพ์ "NA" ไม่เช่นนั้นเราจะพิมพ์วันที่ตามลำดับ
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีหยุดและดำเนินการมอบหมายทรัพยากรต่อใน Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถนำฟังก์ชันนี้ไปใช้ในโปรเจ็กต์ Java ของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks โดยไม่ต้องติดตั้ง Microsoft Project ได้หรือไม่
ใช่ Aspose.Tasks ช่วยให้คุณสามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่จำเป็นต้องติดตั้ง Microsoft Project บนระบบของคุณ
### ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?
 คุณสามารถค้นหาเอกสารรายละเอียดได้[ที่นี่](https://reference.aspose.com/tasks/java/).
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนได้อย่างไรหากฉันประสบปัญหาใดๆ
คุณสามารถรับการสนับสนุนจากชุมชน[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ฉันสามารถซื้อใบอนุญาตชั่วคราวได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
