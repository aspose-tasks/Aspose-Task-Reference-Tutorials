---
date: 2026-07-14
description: เรียนรู้วิธีหยุด resource assignment Java, จัดการ resource assignments,
  และดูตัวอย่างโดยใช้ Aspose.Tasks for Java ในคู่มือขั้นตอนนี้
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: หยุดและทำต่อ Resource Assignments ใน Aspose.Tasks
og_description: หยุด resource assignment Java ด้วย Aspose.Tasks. บทเรียนนี้แสดงวิธี
  pause และ resume assignments, จัดการ dates, และรวม API โดยไม่ต้องใช้ Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: หยุด Resource Assignment Java – คู่มือ Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: วิธีหยุด Resource Assignment Java – ทำต่อด้วย Aspose.Tasks
url: /th/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีหยุดการมอบหมายทรัพยากรใน Java – ทำการต่อเนื่องด้วย Aspose.Tasks

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้ **how to stop resource assignment java** และต่อภายหลังโดยใช้ Aspose.Tasks สำหรับ Java. Aspose.Tasks เป็น API ของ Java ที่แข็งแกร่งซึ่งช่วยให้คุณอ่านและเขียนไฟล์ Microsoft Project, ปรับตารางเวลา, และควบคุมการมอบหมายทรัพยากร—ทั้งหมดโดยไม่ต้องติดตั้ง Microsoft Project เราจะเดินผ่านแต่ละขั้นตอน, อธิบายว่าทำไมแต่ละบรรทัดจึงสำคัญ, และแชร์เคล็ดลับที่คุณสามารถนำไปใช้กับแผนโครงการจริง

## คำตอบอย่างรวดเร็ว
- **What does “stop assignment” mean?** มันทำเครื่องหมายการมอบหมายทรัพยากรว่าเป็นสถานะไม่ทำงานชั่วคราวตั้งแต่วันที่หยุดที่ระบุ.  
- **Can I resume the same assignment later?** ได้, โดยตั้งค่าวันที่ทำต่อบนการมอบหมายเดียวกัน.  
- **Do I need Microsoft Project to use this API?** ไม่จำเป็น, Aspose.Tasks ทำงานอย่างอิสระจาก Microsoft Project.  
- **Which Java version is required?** แนะนำให้ใช้ Java 8 หรือสูงกว่า.  
- **Where can I download the library?** จากหน้าดาวน์โหลดอย่างเป็นทางการของ Aspose.Tasks Java.

## วิธีหยุดการมอบหมายทรัพยากรใน Java?
โหลดโครงการของคุณ, ค้นหา `ResourceAssignment` ที่ต้องการ, ตั้งค่าวันที่ `STOP`, หากต้องการตั้งค่าวันที่ `RESUME`, แล้วบันทึกไฟล์ ลำดับนี้จะหยุดการทำงานในช่วงเวลาที่กำหนดและเปิดใช้งานใหม่โดยอัตโนมัติหลังจากวันที่ทำต่อ, ให้คุณควบคุมปฏิทินทรัพยากรได้อย่างแม่นยำโดยไม่ต้องแก้ไขไฟล์ด้วยตนเอง.

## “how to stop assignment” หมายถึงอะไรในบริบทของ Aspose.Tasks?
การหยุดการมอบหมายบอกให้ตัวจัดตารางเวลาละเว้นงานที่มอบหมายให้ทรัพยากรหลังจาก **stop date** จนถึง **resume date** (ถ้ามี) สิ่งนี้มีประโยชน์สำหรับการจัดการวันหยุด, เวลาไม่ทำงานของอุปกรณ์, หรือช่วงเวลาที่ทรัพยากรไม่ควรถือว่าใช้งาน.

## ทำไมต้องใช้ Aspose.Tasks เพื่อจัดการการมอบหมายทรัพยากร?
Aspose.Tasks ช่วยให้คุณควบคุมวันที่มอบหมายได้โดยโปรแกรม, ขจัดการแก้ไขด้วยมือและลดความเสี่ยงของข้อผิดพลาด มันรองรับ **50+ input and output formats** และสามารถประมวลผลโครงการที่มี **up to 10,000 tasks** ในขณะที่ใช้หน่วยความจำน้อยกว่า 200 MB เนื่องจากสตรีมข้อมูลแทนการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ API ทำงานบนระบบปฏิบัติการใด ๆ ที่รองรับ Java, ให้ความยืดหยุ่นแบบข้ามแพลตฟอร์ม.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) 8 หรือใหม่กว่า ติดตั้งแล้ว.  
- ไลบรารี Aspose.Tasks for Java ดาวน์โหลดแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).  
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java.

## นำเข้าแพ็กเกจ
คลาส `Project`, `ResourceAssignment`, และ `Asn` อยู่ในเนมสเปซ `com.aspose.tasks` ให้นำเข้าที่ส่วนหัวของไฟล์ซอร์สของคุณ:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
คลาส `Project` เป็นอ็อบเจกต์ระดับบนสุดของ Aspose.Tasks ที่แทนไฟล์ Microsoft Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอินสแตนซ์จะโหลดไฟล์และให้คุณเข้าถึงงาน, ทรัพยากร, และการมอบหมาย.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## ขั้นตอนที่ 2: วนลูปผ่านการมอบหมายทรัพยากร
อ็อบเจกต์ `ResourceAssignment` เปิดเผยฟิลด์ที่เกี่ยวข้องกับการมอบหมายทั้งหมด เราตั้งค่า **minimum date** เพื่อกรองวันที่เป็นตัวแทนแล้ววนลูปผ่านแต่ละการมอบหมาย รูปแบบนี้เป็น *resource assignment example* มาตรฐานสำหรับการตรวจสอบหรือการแก้ไข.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## ขั้นตอนที่ 3: ตรวจสอบวันที่ STOP และ RESUME
ในบล็อกนี้เราตรวจสอบฟิลด์ `STOP` และ `RESUME` ของแต่ละการมอบหมาย หากวันที่อยู่ก่อน `minDate` ของเรา เราจะถือว่าไม่ได้ตั้งค่า (`"NA"`); มิฉะนั้นจะแสดงวันที่จริง โลจิกนี้สำคัญสำหรับการ **manage resource assignments** อย่างถูกต้อง.

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

## ปัญหาที่พบบ่อยและวิธีแก้
- **Null dates** – `ra.get(Asn.STOP)` อาจคืนค่า `null`. ป้องกันโดยเพิ่มการตรวจสอบ null ก่อนเรียก `.before(minDate)`.  
- **Incorrect file path** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) ที่เหมาะสมกับ OS ของคุณ.  
- **Version mismatch** – ใช้เวอร์ชันล่าสุดของ Aspose.Tasks for Java เพื่อหลีกเลี่ยงค่าที่หายไปของ enum.

## คำถามที่พบบ่อย

**Q: How do I programmatically set a stop date for an assignment?**  
A: ใช้ `ra.set(Asn.STOP, yourDateObject);` โดยที่ `yourDateObject` เป็นอ็อบเจกต์ `java.util.Date`.

**Q: What happens if the resume date is earlier than the stop date?**  
A: API ไม่บังคับให้ลำดับเวลาเป็นไปตามลำดับ; อย่างไรก็ตาม ตัวจัดตารางเวลาจะถือว่าการมอบหมายเป็นสถานะใช้งานเฉพาะหลังจากวันที่ที่ช้ากว่าระหว่างสองวันที่, ดังนั้นคุณควรตรวจสอบความถูกต้องของวันที่ด้วยตนเอง.

**Q: Can I filter assignments to only those that have a stop date set?**  
A: ได้, วนลูปผ่าน `prj.getResourceAssignments()` และตรวจสอบว่า `ra.get(Asn.STOP) != null`.

**Q: Is it possible to remove a stop date once set?**  
A: ตั้งค่าวันที่หยุดเป็น `null` ด้วย `ra.set(Asn.STOP, null);` แล้วบันทึกโครงการ.

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: แน่นอน. Enum `Asn` มีค่าคงที่สำหรับฟิลด์การมอบหมายทั้งหมด เช่น `Asn.START`, `Asn.FINISH` เป็นต้น.

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **how to stop resource assignment java** แล้วตรวจสอบวันที่หยุด/ต่อ และทำการต่อการมอบหมายเมื่อจำเป็น ความสามารถนี้ทำให้คุณ **manage resource assignments** ได้อย่างแม่นยำยิ่งขึ้น, โดยเฉพาะในสถานการณ์เช่นวันหยุดของทรัพยากรหรือเวลาไม่ทำงานของอุปกรณ์ อย่าลังเลที่จะขยายตัวอย่างเพื่ออัปเดตวันที่, สร้างรายงาน, หรือรวมเข้ากับตรรกะการจัดตารางของคุณเอง.

---

**อัปเดตล่าสุด:** 2026-07-14  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [วิธีคำนวณส่วนต่างต้นทุนและจัดการค่าใช้จ่ายการมอบหมายด้วย Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [วิธีเพิ่มบันทึกย่อในการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}