---
date: 2026-08-29
description: เรียนรู้วิธีตั้งค่า baseline duration และติดตาม project progress ด้วย
  Aspose.Tasks for Java คู่มือขั้นตอนต่อขั้นตอนนี้ช่วยให้คุณจัดการ task baselines
  ได้อย่างมีประสิทธิภาพ
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: วิธีตั้งค่า Baseline Duration ใน Aspose.Tasks for Java
og_description: เรียนรู้วิธีตั้งค่า baseline duration และติดตาม project progress ด้วย
  Aspose.Tasks for Java ปฏิบัติตามคู่มือโดยละเอียดนี้เพื่อจัดการ task baselines อย่างมีประสิทธิภาพ
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: วิธีตั้งค่า baseline duration เพื่อการติดตาม project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: วิธีตั้งค่า baseline duration เพื่อการติดตาม project progress
url: /th/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งระยะเวลา baseline เพื่อการติดตามความคืบหน้าโครงการ

## บทนำ
การติดตามความคืบหน้าโครงการเริ่มต้นด้วย baseline ที่มั่นคง ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีตั้งระยะเวลา baseline** สำหรับงานในไฟล์ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java และเข้าใจว่าการตั้ง baseline ตั้งแต่ต้นช่วยให้คุณตรวจสอบการเบี่ยงเบนของกำหนดเวลา ความแปรผันของต้นทุน และการจัดสรรทรัพยากรเกินขนาดตลอดอายุโครงการ

## คำตอบด่วน
- **“set baseline” หมายถึงอะไร?** มันบันทึกวันเริ่มต้น, วันสิ้นสุด, และระยะเวลาต้นฉบับของงานเพื่อให้คุณเปรียบเทียบการเปลี่ยนแปลงในอนาคตได้  
- **คลาส Aspose.Tasks ใดที่สร้างโปรเจกต์?** `Project` class – คุณจะได้เรียนรู้วิธี **สร้างอินสแตนซ์ของโปรเจกต์** อย่างถูกต้อง  
- **ฉันต้องการไลเซนส์เพื่อรันโค้ดหรือไม่?** ไลเซนส์ทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ฉันสามารถดึง baseline ชั่วคราวได้หรือไม่?** ได้, Aspose.Tasks ให้คุณสอบถาม baseline ชั่วคราวและค่าใช้จ่ายคงที่ของมัน  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือใหม่กว่าแนะนำ  
- **วิธีนี้ช่วยให้ฉันติดตามความคืบหน้าโครงการได้อย่างไร?** เมื่อกำหนด baseline แล้ว คุณสามารถเปรียบเทียบวันที่จริงกับแผนต้นฉบับได้ทันทีโดยใช้คุณลักษณะการรายงานในตัว  

## Baseline งานคืออะไรและทำไมต้องตั้งมัน?
Baseline งานจับตารางเวลาที่วางแผนไว้ (วันเริ่มต้น, วันสิ้นสุด, และระยะเวลา) ณ จุดเวลาหนึ่ง การตั้ง baseline จะสร้างจุดอ้างอิงที่ทำให้ง่ายต่อการสังเกตการเบี่ยงเบนของกำหนดเวลา, ค่าใช้จ่ายเกินงบ, และการจัดสรรทรัพยากรเกินขนาดเมื่อโครงการพัฒนา

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดการ baseline?
Aspose.Tasks ให้ **ความเข้ากันได้เต็มรูปแบบกับ .mpp** – คุณสามารถอ่านและเขียนไฟล์ Microsoft Project แบบดั้งเดิมโดยไม่ต้องติดตั้ง Microsoft Office API ให้การเข้าถึงแบบโปรแกรมต่อ **รูปแบบการนำเข้าและส่งออกกว่า 50 แบบ**, รองรับ **baseline ชั่วคราว 1‑10**, และสามารถจัดการ **โครงการหลายร้อยหน้า** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ซึ่งเป็นสิ่งสำคัญสำหรับการประมวลผลแบบแบตช์ที่มีประสิทธิภาพสูง

## ข้อกำหนดเบื้องต้น
1. **Java Development Environment** – ติดตั้งและกำหนดค่า JDK 8+ แล้ว  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีจาก [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)  
3. **IDE or build tool** – Maven, Gradle, หรือ IDE ใดที่คุณชอบ  

## นำเข้าแพ็กเกจ
การนำเข้าต่อไปนี้นำเข้าคลาสหลักของ Aspose.Tasks ที่จำเป็นสำหรับการทำงานกับโปรเจกต์, งาน, baseline, และข้อมูลตามช่วงเวลา

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของโปรเจกต์
`Project` class แทนไฟล์ Microsoft Project ในหน่วยความจำและเป็นจุดเริ่มต้นสำหรับการดำเนินการทั้งหมด

```java
Project project = new Project();
```

## ขั้นตอนที่ 2: สร้าง baseline งาน
`TaskBaseline` เก็บข้อมูลวันเริ่มต้น, วันสิ้นสุด, และระยะเวลาที่วางแผนไว้สำหรับงานเฉพาะ

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## ขั้นตอนที่ 3: แสดงข้อมูล baseline ของงาน
เมธอด `getBaselines()` คืนค่าชุดของ baseline ที่เชื่อมโยงกับงาน

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## ขั้นตอนที่ 4: ตรวจสอบ baseline ชั่วคราวและค่าใช้จ่ายคงที่
`BaselineType` แสดงรายการ baseline หลักและชั่วคราว (Baseline, Baseline1‑Baseline10)

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## ขั้นตอนที่ 5: พิมพ์ข้อมูลตามช่วงเวลา
`TimephasedData` แสดงข้อมูลตารางเวลาชิ้นหนึ่งสำหรับช่วงเวลาที่กำหนด

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

โดยทำตามขั้นตอนเหล่านี้ คุณสามารถ **ตั้งระยะเวลา baseline** สำหรับงานใดก็ได้และดึงข้อมูล baseline อย่างละเอียดโดยใช้ Aspose.Tasks สำหรับ Java ทำให้คุณมีวิธีที่เชื่อถือได้ในการ **ติดตามความคืบหน้าโครงการ** ตลอดวงจรชีวิตของโครงการ

## ปัญหาทั่วไปและวิธีแก้
- **Baseline ไม่ปรากฏใน MS Project:** ตรวจสอบว่าคุณได้เรียก `project.setBaseline(BaselineType.Baseline)` **หลังจาก** เพิ่มงานแล้ว  
- **NullPointerException บน `getBaselines()`:** ตรวจสอบว่างานถูกเพิ่มเข้าไปในโปรเจกต์ก่อนตั้ง baseline  
- **ไม่ตรงกันของหน่วยเวลา:** ใช้ `TimeUnitType` เพื่อจัดรูปแบบระยะเวลาให้ถูกต้อง โดยเฉพาะเมื่อทำงานกับปฏิทินที่กำหนดเอง  

## คำถามที่พบบ่อย
### Baseline งานใน MS Project คืออะไร?
Baseline งานใน MS Project คือภาพถ่ายของตารางเวลาที่วางแผนไว้ตั้งแต่แรกสำหรับงานหนึ่ง รวมถึงวันเริ่มต้น, วันสิ้นสุด, และระยะเวลา

### ทำไมการจัดการ baseline งานจึงสำคัญ?
การจัดการ baseline งานช่วยเปรียบเทียบตารางเวลาที่วางแผนกับความคืบหน้าจริงของโครงการ ทำให้การติดตามและการตัดสินใจดีขึ้น

### ฉันสามารถแก้ไข baseline งานได้หลังจากตั้งแล้วหรือไม่?
ได้, คุณสามารถแก้ไข baseline งานใน MS Project เพื่อสะท้อนการเปลี่ยนแปลงในแผนโครงการ อย่างไรก็ตาม จำเป็นต้องบันทึกความแตกต่างใด ๆ จาก baseline ต้นฉบับ

### Aspose.Tasks รองรับฟังก์ชันการจัดการโครงการอื่น ๆ หรือไม่?
ได้, Aspose.Tasks มีฟีเจอร์หลากหลายสำหรับการจัดการโครงการ รวมถึงการกำหนดตารางงาน, การจัดสรรทรัพยากร, และการสร้างแผนภูมิ Gantt

### ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?
คุณสามารถหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) ซึ่งคุณสามารถถามคำถามและโต้ตอบกับผู้ใช้คนอื่น ๆ  

## คำถามที่พบบ่อยเพิ่มเติม
**Q: ฉันต้องเรียก `setBaseline` สำหรับแต่ละงานแยกกันหรือไม่?**  
A: ไม่. การเรียก `project.setBaseline(BaselineType.Baseline)` จะบันทึก baseline สำหรับงานทั้งหมดในโปรเจกต์พร้อมกัน  

**Q: ฉันจะตั้ง baseline ชั่วคราวสำหรับงานเฉพาะได้อย่างไร?**  
A: ใช้ `project.setBaseline(BaselineType.Baseline1)` (หรือ Baseline2‑Baseline10) หลังจากอัปเดตตารางเวลาของงาน  

**Q: สามารถส่งออกข้อมูล baseline ไปเป็น CSV ได้หรือไม่?**  
A: ได้. ทำการวนลูป `task.getBaselines()` แล้วเขียนฟิลด์ที่ต้องการลงในไฟล์ CSV โดยใช้ Java I/O มาตรฐาน  

**Q: ฉันสามารถอ่านไฟล์ .mpp ที่มี baseline อยู่แล้วได้หรือไม่?**  
A: แน่นอน. โหลดไฟล์ด้วย `new Project("myproject.mpp")` แล้วเข้าถึง baseline ของแต่ละงานตามที่แสดงข้างต้น  

**Q: Aspose.Tasks รองรับไฟล์หลายโครงการหรือไม่?**  
A: Aspose.Tasks ทำงานกับไฟล์ .mpp โครงการเดียว. สำหรับสถานการณ์หลายโครงการ ให้รวมโครงการเข้าด้วยกันโดยโปรแกรม  

---

**อัปเดตล่าสุด:** 2026-08-29  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

## บทเรียนที่เกี่ยวข้อง

- [สร้างรายการงาน Java – Baseline ของ MS Project ด้วย Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [สร้างโครงการ MPP Java – เปลี่ยนความคืบหน้าของงานด้วย Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Baseline การจัดการโครงการ – การกำหนดตารางงานด้วย Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}