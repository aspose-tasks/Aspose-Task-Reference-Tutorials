---
date: 2026-06-10
description: เรียนรู้วิธีอ่านอัตราและวิธีเขียนอัตราสเกลสำหรับการมอบหมายทรัพยากรโดยใช้
  Aspose.Tasks for Java รองรับทรัพยากรวัสดุหลายรูปแบบและโครงการขนาดใหญ่
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: อ่านและเขียนอัตราสเกลสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีอ่านอัตราสเกลและเขียนอัตราสเกลสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
url: /th/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านอัตราสเกลและเขียนอัตราสเกลสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks

## คำตอบอย่างรวดเร็ว
`ResourceAssignment` เชื่อมโยงงานกับทรัพยากรและเก็บข้อมูลเฉพาะการมอบหมาย.  
`Asn` มีค่าคงที่สำหรับฟิลด์การมอบหมาย รวมถึง `RATE_SCALE`.  
`RateScaleType` enum แสดงรายการหน่วยเวลาที่เป็นไปได้สำหรับการสเกลอัตรา.  

- **คลาสหลักสำหรับการจัดการอัตรา?** `ResourceAssignment` กับคุณสมบัติ `Asn.RATE_SCALE`.  
- **enum ใดกำหนดตัวเลือกสเกล?** `RateScaleType` (Day, Week, Month, ฯลฯ).  
- **ต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** ไลเซนส์ทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **สามารถเปลี่ยนสเกลหลังจากบันทึกได้หรือไม่?** ได้ – โหลดโปรเจกต์ใหม่และแก้ไข `Asn.RATE_SCALE` ตามที่แสดง.  
- **IDE ที่รองรับ?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, NetBeans) สามารถคอมไพล์โค้ดได้.

## วิธีอ่านอัตราสเกลสำหรับการมอบหมายทรัพยากร?
โหลดโปรเจกต์, ค้นหา `ResourceAssignment` ที่ต้องการ, แล้วเรียก `getRateScale()` – คำสั่งนี้จะคืนค่า `RateScaleType` ที่บอกว่าระดับอัตราถูกนำไปใช้ต่อวัน, สัปดาห์, เดือน หรือหน่วยอื่น คำตอบได้ทันทีและต้องการเพียงสองการเรียก API ทำให้เหมาะสำหรับสคริปต์ตรวจสอบหรือการแสดงผล UI.

## วิธีเขียนอัตราสเกลสำหรับการมอบหมายทรัพยากร?
สร้างหรือดึงอ็อบเจกต์ `ResourceAssignment`, ตั้งค่าคุณสมบัติ `Asn.RATE_SCALE` ให้เป็น `RateScaleType` ที่ต้องการ (เช่น `RateScaleType.Week`), แล้วบันทึกโปรเจกต์ การเปลี่ยนแปลงคุณสมบัติเพียงรายการเดียวนี้จะอัปเดตการคำนวณค่าใช้จ่ายโดยอัตโนมัติและคงอยู่ในทุกรูปแบบไฟล์ที่รองรับ หลังจากตั้งค่าสเกลแล้วอาจต้องปรับอัตรามาตรฐานหรืออัตราโอเวอร์ไทม์ของทรัพยากรให้สอดคล้องกับหน่วยเวลาใหม่ เพื่อให้การคำนวณค่าใช้จ่ายแม่นยำ.

## อัตราสเกลคืออะไร?
อัตราสเกลกำหนดหน่วยเวลา (วัน, สัปดาห์, เดือน ฯลฯ) ที่อัตราค่าใช้จ่ายของทรัพยากรถูกนำไปใช้ การปรับสเกลช่วยให้คุณจำลองการใช้วัสดุหรือแรงงานได้อย่างแม่นยำ ตัวอย่างเช่น การตั้งสเกลเป็น Week หมายความว่าอัตราค่าใช้จ่ายจะถูกตีความเป็นค่าใช้จ่ายต่อสัปดาห์ และค่าใช้จ่ายรวมของงานจะคำนวณตามจำนวนสัปดาห์ที่ทรัพยากรถูกมอบหมาย.

## ทำไมต้องอ่านและเขียนอัตราสเกล?
การอ่านสเกลปัจจุบันช่วยให้คุณตรวจสอบตารางเวลาที่มีอยู่ได้ ในขณะที่การเขียนสเกลใหม่ทำให้คุณสามารถปรับทรัพยากรให้สอดคล้องกับนโยบายการเรียกเก็บเงินหรือการใช้ของโครงการได้ สิ่งนี้มีประโยชน์อย่างยิ่งเมื่อ **กำหนดค่าใช้จ่ายของทรัพยากรวัสดุ** หรือเมื่อคุณต้อง **ตั้งสเกล** สำหรับปฏิทินงานที่ไม่เป็นมาตรฐาน.

## ข้อกำหนดเบื้องต้น
1. **Java Development Environment** – ติดตั้ง JDK 8 หรือสูงกว่า.  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดและติดตั้งไลบรารีจาก [here](https://releases.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
`ResourceAssignment` class แสดงลิงก์ระหว่างงานและทรัพยากร, ส่วน `RateScaleType` enum แสดงหน่วยเวลาที่เป็นไปได้สำหรับอัตรา. ให้นำเข้าคลาส Aspose.Tasks ที่จำเป็นก่อนเริ่มเขียนโค้ด.

`Project` คืออ็อบเจกต์หลักที่โหลดและบันทึกไฟล์ Microsoft Project.  
`Resource` กำหนดทรัพยากรของโปรเจกต์ เช่น งานหรือวัสดุ.  
`ResourceType` enum ระบุว่าทรัพยากรเป็นงานหรือวัสดุ.  
`Task` แทนรายการงานในตารางเวลาโปรเจกต์.  
`SaveFileFormat` enum กำหนดรูปแบบการบันทึกโปรเจกต์.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ Java ของคุณ
สร้างโปรเจกต์ Maven หรือ Gradle และเพิ่ม Aspose.Tasks JAR ไปยัง classpath ขั้นตอนนี้ทำให้คอมไพเลอร์สามารถค้นหาคลาสที่นำเข้าได้.

## ขั้นตอนที่ 2: โหลดไฟล์โปรเจกต์
โหลดไฟล์ Microsoft Project ที่มีอยู่ที่คุณต้องการทำงานด้วย.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## ขั้นตอนที่ 3: เพิ่มงาน
สร้างงานใหม่ที่จะรับการมอบหมายทรัพยากรในภายหลัง.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## ขั้นตอนที่ 4: กำหนดทรัพยากร
ที่นี่เราจะ **กำหนดทรัพยากรวัสดุ** และทรัพยากรงานปกติ โปรดสังเกตการใช้ `ResourceType.Material` สำหรับทรัพยากรประเภทวัสดุ.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## ขั้นตอนที่ 5: มอบหมายทรัพยากรให้กับงาน
ตอนนี้เราจะ **มอบหมายทรัพยากรให้กับงาน** และระบุ **วิธีตั้งสเกล** โดยใช้ `RateScaleType.Week` ตัวอย่างนี้แสดงการอ่านและเขียนอัตราสเกลพร้อมกัน.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## ขั้นตอนที่ 6: บันทึกโปรเจกต์
บันทึกการเปลี่ยนแปลงลงในไฟล์ใหม่เพื่อให้เราสามารถตรวจสอบอัตราสเกลที่บันทึกไว้ได้ในภายหลัง.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## ขั้นตอนที่ 7: ดึงการมอบหมายทรัพยากร
โหลดโปรเจกต์ที่บันทึกไว้ใหม่และ **อ่านอัตราสเกล** เพื่อยืนยันว่ามันถูกเขียนอย่างถูกต้อง.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **UID Mismatch** – เมื่อดึงการมอบหมายโดย UID ให้ตรวจสอบว่า UID ตรงกับที่กำหนดในระหว่างการสร้าง.  
- **Incorrect Resource Type** – การใช้ `ResourceType.Material` สำหรับทรัพยากรงานจะทำให้การคำนวณอัตราแสดงผลไม่คาดคิด.  
- **Saving Format** – ควรบันทึกโดยใช้ `SaveFileFormat.Mpp` (หรือรูปแบบที่รองรับอื่น) เพื่อรักษาฟิลด์กำหนดเองเช่นอัตราสเกล.  
- **Large Projects** – Aspose.Tasks สามารถประมวลผลไฟล์ที่มี **500+ หน้า** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ เนื่องจากสถาปัตยกรรมสตรีมมิ่งของมัน.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks for Java กับ IDE Java ใดก็ได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java รองรับ IDE Java หลักทั้งหมด รวมถึง IntelliJ IDEA, Eclipse, และ NetBeans.

**Q: Aspose.Tasks รองรับรูปแบบไฟล์อื่นนอกจาก MPP หรือไม่?**  
A: ใช่, Aspose.Tasks รองรับรูปแบบไฟล์หลายประเภท รวมถึง MPP, XML, และ HTML.

**Q: Aspose.Tasks เหมาะสำหรับการจัดการโครงการระดับองค์กรหรือไม่?**  
A: แน่นอน, Aspose.Tasks มีคุณลักษณะครบถ้วนสำหรับการจัดการโครงการทุกขนาด ทำให้เหมาะกับการจัดการโครงการระดับองค์กร.

**Q: ฉันสามารถปรับแต่งการมอบหมายทรัพยากรเพิ่มเติมนอกเหนือจากอัตราสเกลได้หรือไม่?**  
A: ใช่, Aspose.Tasks มีความสามารถกว้างขวางในการปรับแต่งการมอบหมายทรัพยากร รวมถึงการปรับค่าใช้จ่าย งาน และระยะเวลา.

**Q: มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่?**  
A: ใช่, คุณสามารถหาการสนับสนุนและโต้ตอบกับผู้ใช้คนอื่นได้ในฟอรั่ม Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**อัปเดตล่าสุด:** 2026-06-10  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [วิธีแก้ไขการมอบหมาย – อ่านทรัพยากรที่แชร์ด้วย Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [วิธีเพิ่มบันทึกลงในการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}