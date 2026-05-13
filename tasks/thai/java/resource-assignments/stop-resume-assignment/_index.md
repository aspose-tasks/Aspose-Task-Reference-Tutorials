---
date: 2026-01-10
description: เรียนรู้วิธีหยุดการมอบหมาย, จัดการการมอบหมายทรัพยากร, และดูตัวอย่างการมอบหมายทรัพยากรใน
  Aspose.Tasks สำหรับ Java ด้วยบทแนะนำแบบขั้นตอนต่อขั้นตอนนี้.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีหยุดการมอบหมายและทำการมอบหมายทรัพยากรต่อใน Aspose.Tasks
url: /th/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีหยุดการมอบหมายและดำเนินการมอบหมายทรัพยากรต่อใน Aspose.Tasks

## การแนะนำ
ในบทแนะนำนี้ **คุณจะได้หยุดการในส่วน** และเพื่อให้เคล็ดลับการดำเนินการต่อสิทธิพิเศษ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็น API ของ Java ซึ่งช่วยให้อ่านไฟล์รูปแบบโครงการ Java, จัดการข้อมูล Microsoft Project, และดำเนินการดำเนินการตามทรัพยากรเพื่อตรวจสอบการติดตั้ง Microsoft Project ในการดำเนินการแต่ละขั้นตอน, อธิบายว่าทำไมบรรทัดแต่ละบรรทัดจึงมีความสำคัญ, และให้ทราบถึงโครงการจริงได้

## คำตอบด่วน
- **“หยุดการส่วนใหญ่” ส่วนใหญ่คืออะไร?** มันถือเป็นการดำรงอยู่อย่างต่อเนื่องเป็นระยะเวลาหยุดที่กำหนด
- **ขั้นตอนการดำเนินการอื่นๆ ในเวลาเดียวกันสามารถติดตามได้?** โดยกำหนดวันที่บนการประสิทธิภาพเดียวกัน
- **ต้องใช้ Microsoft Project การตรวจสอบ API จำนวนมาก?** ไม่จำเป็น, Aspose.Tasks อย่างเป็นทางการจาก Microsoft Project
- **ต้องใช้ Java ใด ๆ?** ต้องใช้ Java8 หรือต้องการ
- **ดาวน์โหลดได้จากที่ไหน?** จากหน้าดาวน์โหลดอย่างเป็นทางการของ Aspose.Tasks Java

## “วิธีหยุดการมอบหมายงาน” ในบริบทของ Aspose.Tasks คืออะไร
การหยุดการอธิบายการทำงานของตัวจัดตารางเวลาละเว้นโดยขึ้นอยู่กับแหล่งที่มา **วันที่หยุด** วันที่ **วันที่** (หากคุณ) ที่เป็นประโยชน์สำหรับการจัดการวันหยุด, โครงสร้างการหยุดทำงาน, หรือแหล่งทรัพยากรที่ถือว่าใช้งานอยู่

## เหตุใดจึงต้องใช้ Aspose.Tasks เพื่อจัดการการมอบหมายทรัพยากร
- **ไม่ต้องใช้ Microsoft Project** – เรามีไฟล์ .mpp
- **ควบคุมวันที่ได้เต็มที่** – วันที่หยุด, วันที่ดังกล่าว, และวันที่ควบคุมโปรแกรม
- **ข้ามแพลตฟอร์ม** – รันบนระบบปฏิบัติการที่รองรับ Java
- **API ที่ครบถ้วน** – มี *ตัวอย่างการมอบหมายทรัพยากร* สามารถต่อยอดรายงานประจำปีได้

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, กรุณาตรวจสอบคุณ:

- Java Development Kit (JDK) ติดตั้งบนระบบของคุณ
- ไลบรารี Aspose.Tasks สำหรับ Java ดาวน์โหลดแล้วดาวน์โหลดดาวน์โหลด [ที่นี่](https://releases.aspose.com/tasks/java/)
- ความเข้าใจพื้นฐานเกี่ยวกับ Java

## แพคเกจนำเข้า
ก่อนอื่น, ให้เรานำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของเรา:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## ขั้นตอนที่ 1: โหลดไฟล์โปรเจ็กต์
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

ที่นี่เราจะ **อ่านไฟล์โครงการรูปแบบ Java** (`.mpp`) และสร้างอ็อบเจ็กต์ `Project` ที่ให้เราเข้าถึงข้อมูลโครงการทั้งหมด รวมถึงการมอบหมายทรัพยากร

## ขั้นตอนที่ 2: ดำเนินการจัดสรรทรัพยากร
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

เราตั้งค่า **minimum date** เพื่อกรองวันที่เป็นตัวแทนและจากนั้นวนลูปผ่านการมอบหมายแต่ละรายการ นี่คือรูปแบบ *resource assignment example* ที่ใช้บ่อยเมื่อคุณต้องการตรวจสอบหรือแก้ไขการมอบหมาย

## ขั้นตอนที่ 3: ตรวจสอบวันที่สิ้นสุดและวันที่เริ่มต้นใหม่
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

ในบล็อกนี้เราจะ **ตรวจสอบวันที่หยุด** และ **ตรวจสอบวันที่ดำเนินการต่อ** สำหรับการมอบหมายแต่ละรายการ หากวันที่อยู่ก่อน `minDate` เราจะถือว่าไม่ได้ตั้งค่า (`"NA"`); หากไม่ใช่เราจะแสดงวันที่จริง ตรรกะนี้สำคัญสำหรับการ **manage resource assignments** อย่างถูกต้อง

## ปัญหาทั่วไปและแนวทางแก้ไข
- **วันที่เป็นค่าว่าง** – `ra.get(Asn.STOP)` อาจจะเป็นเช่นนั้น `null` ตรวจสอบค่า null ก่อนที่จะเรียก `.before(minDate)`
- **Incorrect file path** – การควบคุมในโหมดนี้ `dataDir` สิ้นสุดด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) ที่ระบบควบคุมของคุณ
- **Version mismatch** – ใช้งานระบบต่างๆ ของ Aspose.Tasks for Java และค่าต่างๆ แจงนับที่หายไป

## คำถามที่พบบ่อย

**คำถาม: วิธีตั้งค่าขั้นตอนหยุดวันที่สำหรับการรักษาโรคโดยโปรแกรมทำอย่างไร?**
A: ใช้ `ra.set(Asn.STOP, yourDateObject);` โดยที่ `yourDateObject` คืออ็อบเจ็กต์ `java.util.Date`

**คำถาม: ถ้าหากวันที่ต้องอยู่ก่อนวันที่หยุด?**
ตอบ: API ไม่ได้เป็นไปตามเวลาต่อเนื่อง; อย่างไรก็ตาม พนักงานจัดตารางเวลาจะถือว่าการมีความสำคัญเป็นสถานะทำงานหลังจากวันที่ช้ากว่าระหว่างสองวันจึงควรตรวจสอบความถูกต้องของวันที่อื่นๆ

**คำถาม: สามารถกรองระบบส่วนใหญ่ให้แสดงเฉพาะที่มีวันที่หยุดได้หรือไม่**
ตอบ: ได้, วนยิ่งใหญ่ผ่าน `prj.getResourceAssignments()` แล้วหลังจากนั้น `ra.get(Asn.STOP) != null`

**Q: สามารถลบวันที่หยุดที่เอกสารไว้ได้หรือไม่?**
A: วันที่หยุดเป็น `null` ด้วย `ra.set(Asn.STOP, null);` จากนั้นบันทึกโครงการ

**ถาม: Aspose.Tasks แสดงข้อมูลวันที่อื่นๆ เช่น เริ่มต้น เสร็จสิ้น หรือเริ่มต้นจริง?**
A: หลักฐานที่เห็นได้ชัด. enum `Asn` มีนัยสำคัญสำหรับประสิทธิภาพของการกล่าวทั้งหมด แปลว่า `Asn.START`, `Asn.FINISH` เป็นต้น

## บทสรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **วิธีหยุดการมอบหมาย**, ตรวจสอบวันที่หยุด/ดำเนินการต่อ, และดำเนินการต่อการมอบหมายเมื่อจำเป็น ความสามารถนี้ช่วยให้คุณ **manage resource assignments** ได้อย่างแม่นยำยิ่งขึ้น โดยเฉพาะในสถานการณ์เช่น การลาพักร้อนของทรัพยากรหรือการหยุดทำงานของอุปกรณ์ อย่าลังเลที่จะต่อยอดตัวอย่างเพื่ออัปเดตวันที่, สร้างรายงาน, หรือรวมเข้ากับตรรกะการจัดตารางเวลาของคุณเอง

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}