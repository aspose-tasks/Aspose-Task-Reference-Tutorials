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

## Introduction
ในบทแนะนำนี้ **คุณจะได้เรียนรู้วิธีหยุดการมอบหมาย** และต่อมาจะทำการดำเนินการต่อโดยใช้ Aspose.Tasks for Java Aspose.Tasks เป็น API ของ Java ที่ทรงพลังซึ่งช่วยให้คุณอ่านไฟล์โครงการรูปแบบ Java, จัดการข้อมูล Microsoft Project, และจัดการการมอบหมายทรัพยากรโดยไม่ต้องติดตั้ง Microsoft Project เราจะเดินผ่านแต่ละขั้นตอน, อธิบายว่าทำไมบรรทัดแต่ละบรรทัดจึงสำคัญ, และให้เคล็ดลับที่คุณสามารถนำไปใช้กับโครงการจริงได้

## Quick Answers
- **“หยุดการมอบหมาย” หมายถึงอะไร?** มันทำเครื่องหมายการมอบหมายทรัพยากรว่าเป็นสถานะไม่ทำงานชั่วคราวตั้งแต่วันที่หยุดที่กำหนด  
- **ฉันสามารถดำเนินการมอบหมายเดียวกันต่อในภายหลังได้หรือไม่?** ได้, โดยกำหนดวันที่ดำเนินการต่อบนการมอบหมายเดียวกัน  
- **ต้องใช้ Microsoft Project เพื่อใช้ API นี้หรือไม่?** ไม่จำเป็น, Aspose.Tasks ทำงานอิสระจาก Microsoft Project  
- **ต้องใช้เวอร์ชัน Java ใด?** แนะนำให้ใช้ Java 8 หรือสูงกว่า  
- **สามารถดาวน์โหลดไลบรารีได้จากที่ไหน?** จากหน้าดาวน์โหลดอย่างเป็นทางการของ Aspose.Tasks Java  

## What is “how to stop assignment” in the context of Aspose.Tasks?
การหยุดการมอบหมายบอกให้ตัวจัดตารางเวลาละเว้นงานที่จัดสรรให้กับทรัพยากรหลังจาก **วันที่หยุด** จนถึง **วันที่ดำเนินการต่อ** (ถ้ามี) ซึ่งเป็นประโยชน์สำหรับการจัดการวันหยุด, เวลาเครื่องจักรหยุดทำงาน, หรือช่วงเวลาที่ทรัพยากรไม่ควรถือว่าใช้งานอยู่

## Why use Aspose.Tasks to manage resource assignments?
- **ไม่ต้องใช้ Microsoft Project** – ทำงานโดยตรงกับไฟล์ .mpp  
- **ควบคุมวันที่ได้เต็มที่** – สามารถตรวจสอบวันที่หยุด, วันที่ดำเนินการต่อ, และปรับเปลี่ยนได้โดยโปรแกรม  
- **ข้ามแพลตฟอร์ม** – รันบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java  
- **API ที่ครบถ้วน** – มี *resource assignment example* ที่คุณสามารถต่อยอดเพื่อสร้างรายงานแบบกำหนดเอง  

## Prerequisites
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) ติดตั้งบนระบบของคุณ  
- ไลบรารี Aspose.Tasks for Java ดาวน์โหลดแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/)  
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  

## Import Packages
ก่อนอื่น, ให้เรานำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของเรา:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Step 1: Load the Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

ที่นี่เราจะ **อ่านไฟล์โครงการรูปแบบ Java** (`.mpp`) และสร้างอ็อบเจ็กต์ `Project` ที่ให้เราเข้าถึงข้อมูลโครงการทั้งหมด รวมถึงการมอบหมายทรัพยากร

## Step 2: Iterate Through Resource Assignments
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

เราตั้งค่า **minimum date** เพื่อกรองวันที่เป็นตัวแทนและจากนั้นวนลูปผ่านการมอบหมายแต่ละรายการ นี่คือรูปแบบ *resource assignment example* ที่ใช้บ่อยเมื่อคุณต้องการตรวจสอบหรือแก้ไขการมอบหมาย

## Step 3: Check Stop and Resume Dates
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

## Common Issues and Solutions
- **Null dates** – `ra.get(Asn.STOP)` อาจคืนค่า `null`. ควรตรวจสอบค่า null ก่อนเรียก `.before(minDate)`  
- **Incorrect file path** – ตรวจสอบให้แน่ใจว่า `dataDir` สิ้นสุดด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) ที่เหมาะสมกับระบบปฏิบัติการของคุณ  
- **Version mismatch** – ใช้เวอร์ชันล่าสุดของ Aspose.Tasks for Java เพื่อหลีกเลี่ยงค่าคงที่ enum ที่หายไป  

## FAQ's
### สามารถใช้ Aspose.Tasks ได้โดยไม่ติดตั้ง Microsoft Project หรือไม่?
ได้, Aspose.Tasks ช่วยให้คุณทำงานกับไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project บนระบบของคุณ

### จะหาเอกสารเพิ่มเติมได้จากที่ไหน?
คุณสามารถดูเอกสารโดยละเอียดได้ที่ [here](https://reference.aspose.com/tasks/java/)

### มีรุ่นทดลองฟรีหรือไม่?
มี, คุณสามารถรับรุ่นทดลองฟรีได้ที่ [here](https://releases.aspose.com/)

### จะขอรับการสนับสนุนหากเจอปัญหาได้อย่างไร?
คุณสามารถรับการสนับสนุนจากชุมชนได้ที่ [here](https://forum.aspose.com/c/tasks/15)

### สามารถซื้อใบอนุญาตชั่วคราวได้หรือไม่?
ได้, คุณสามารถซื้อใบอนุญาตชั่วคราวได้ที่ [here](https://purchase.aspose.com/temporary-license/)

## Frequently Asked Questions

**Q: วิธีตั้งค่าขั้นตอนหยุดวันที่สำหรับการมอบหมายโดยโปรแกรมทำอย่างไร?**  
A: ใช้ `ra.set(Asn.STOP, yourDateObject);` โดยที่ `yourDateObject` คืออ็อบเจ็กต์ `java.util.Date`

**Q: จะเกิดอะไรขึ้นหากวันที่ดำเนินการต่ออยู่ก่อนวันที่หยุด?**  
A: API ไม่บังคับให้ลำดับเวลาเป็นไปตามลำดับเหตุการณ์; อย่างไรก็ตาม ตัวจัดตารางเวลาจะถือว่าการมอบหมายเป็นสถานะทำงานเฉพาะหลังจากวันที่ที่ช้ากว่าระหว่างสองวัน ดังนั้นคุณควรตรวจสอบความถูกต้องของวันที่ด้วยตนเอง

**Q: สามารถกรองการมอบหมายให้แสดงเฉพาะที่มีการตั้งค่าวันที่หยุดหรือไม่?**  
A: ได้, วนลูปผ่าน `prj.getResourceAssignments()` แล้วตรวจสอบว่า `ra.get(Asn.STOP) != null`

**Q: สามารถลบวันที่หยุดที่ตั้งค่าไว้ได้หรือไม่?**  
A: ตั้งค่าวันที่หยุดเป็น `null` ด้วย `ra.set(Asn.STOP, null);` แล้วบันทึกโครงการ

**Q: Aspose.Tasks รองรับฟิลด์ที่เกี่ยวกับวันที่อื่น ๆ เช่น start, finish หรือ actual start หรือไม่?**  
A: รองรับอย่างเต็มที่. enum `Asn` มีค่าคงที่สำหรับฟิลด์การมอบหมายทั้งหมด เช่น `Asn.START`, `Asn.FINISH` เป็นต้น

## Conclusion
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **วิธีหยุดการมอบหมาย**, ตรวจสอบวันที่หยุด/ดำเนินการต่อ, และดำเนินการต่อการมอบหมายเมื่อจำเป็น ความสามารถนี้ช่วยให้คุณ **manage resource assignments** ได้อย่างแม่นยำยิ่งขึ้น โดยเฉพาะในสถานการณ์เช่น การลาพักร้อนของทรัพยากรหรือการหยุดทำงานของอุปกรณ์ อย่าลังเลที่จะต่อยอดตัวอย่างเพื่ออัปเดตวันที่, สร้างรายงาน, หรือรวมเข้ากับตรรกะการจัดตารางเวลาของคุณเอง

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}