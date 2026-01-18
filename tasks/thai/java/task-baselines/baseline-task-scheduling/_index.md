---
date: 2026-01-18
description: เรียนรู้วิธีกำหนดเวลา baseline การจัดการโครงการด้วย Aspose.Tasks สำหรับ
  Java เพื่อให้คุณสามารถจัดการ baseline ของโครงการและเปรียบเทียบความคืบหน้าที่วางแผนกับความคืบหน้าจริงได้
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: พื้นฐานการจัดการโครงการ – การกำหนดเวลางานด้วย Aspose.Tasks
url: /th/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baseline การจัดการโครงการ – การกำหนดเวลางานด้วย Aspose.Tasks

## บทนำสู่ Baseline การจัดการโครงการ
การจัดการ **baseline การจัดการโครงการ** เป็นหัวใจสำคัญของการจัดการโครงการที่มีประสิทธิภาพ มันช่วยให้คุณบันทึกแผนต้นฉบับและเปรียบเทียบ **แผนที่วางไว้กับความคืบหน้าจริง** ในภายหลัง เพื่อให้คุณสามารถตรวจจับความแตกต่างได้ตั้งแต่เนิ่นๆ ในบทเรียนนี้ เราจะอธิบายขั้นตอนการกำหนดเวลา baseline ของงานโดยใช้ Aspose.Tasks for Java ให้คุณมีเครื่องมือในการ **จัดการ baseline ของโครงการ** อย่างมั่นใจและทำให้โครงการของคุณเดินหน้าได้อย่างราบรื่น

## คำตอบสั้น
- **Baseline การจัดการโครงการหมายถึงอะไร?**  
  Baseline จะบันทึกกำหนดการต้นฉบับ, ค่าใช้จ่าย, และขอบเขตเพื่อการวิเคราะห์ความแตกต่างในภายหลัง.  
- **ไลบรารีใดจัดการการกำหนดเวลา baseline ใน Java?**  
  Aspose.Tasks for Java มี API ที่แข็งแกร่งสำหรับการสร้างและจัดการ baseline.  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?**  
  เวอร์ชันทดลองฟรีใช้สำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ข้อกำหนดเบื้องต้นหลักคืออะไร?**  
  Java Development Kit (JDK) และไลบรารี Aspose.Tasks for Java.  
- **ฉันสามารถดูวันที่ของ baseline หลังจากตั้งค่าได้หรือไม่?**  
  ได้—ใช้วัตถุ `TaskBaseline` เพื่ออ่านค่า start, finish, และ duration.

## Baseline การจัดการโครงการคืออะไร?
Baseline การจัดการโครงการบันทึกเวอร์ชันที่ได้รับการอนุมัติของกำหนดการโครงการ, งบประมาณ, และขอบเขตเมื่อเริ่มดำเนินการ มันทำหน้าที่เป็นจุดอ้างอิงสำหรับการวัดผลการดำเนินงานและการระบุความเบี่ยงเบนตลอดวงจรชีวิตของโครงการ

## ทำไมต้องใช้ Aspose.Tasks สำหรับการกำหนดเวลา Baseline?
Aspose.Tasks มี API แบบ pure‑Java ที่ทำงานได้โดยไม่ต้องติดตั้ง Microsoft Project มันช่วยให้คุณ **สร้างอินสแตนซ์โปรเจกต์**, กำหนดงาน, ตั้ง baseline, และดึงข้อมูล baseline อย่างโปรแกรมเมติก—เหมาะอย่างยิ่งสำหรับการรายงานอัตโนมัติหรือการผสานรวมกับเครื่องมือ PM ที่กำหนดเอง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อม:

### สภาพแวดล้อมการพัฒนา Java
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### ไลบรารี Aspose.Tasks for Java
ดาวน์โหลดไลบรารี Aspose.Tasks for Java จาก [download page](https://releases.aspose.com/tasks/java/) แล้วใส่เข้าไปในโปรเจกต์ Java ของคุณ

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

ตอนนี้เราจะทำการแยกตัวอย่างที่ให้มาออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project ใหม่
```java
Project project = new Project();
```

## ขั้นตอนที่ 2: กำหนดงานและตั้ง Baseline
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## ขั้นตอนที่ 3: เข้าถึงข้อมูล Baseline
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## ขั้นตอนที่ 4: แสดงระยะเวลา Baseline
```java
System.out.println(baseline.getDuration().toString());
```

## ขั้นตอนที่ 5: แสดงวันที่เริ่มต้น Baseline
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## ขั้นตอนที่ 6: แสดงวันที่สิ้นสุด Baseline
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

โดยการทำตามขั้นตอนเหล่านี้ คุณสามารถใช้ Aspose.Tasks for Java เพื่อ **จัดการ baseline ของโครงการ** ได้อย่างมีประสิทธิภาพในโครงการของคุณ

## ปัญหาทั่วไปและวิธีแก้
- **Baseline ไม่ได้ตั้งค่า:** ตรวจสอบให้แน่ใจว่าคุณเรียก `project.setBaseline(BaselineType.Baseline)` **หลังจาก** เพิ่มงาน; มิฉะนั้นคอลเลกชัน baseline จะว่างเปล่า.  
- **ค่า Null:** หาก `task.getBaselines()` คืนรายการว่าง, ให้ตรวจสอบว่าตัวงานได้ถูกเพิ่มเข้าไปในโครงสร้างโครงการก่อนตั้ง baseline.  
- **รูปแบบวันที่:** เมธอด `getStart()` และ `getFinish()` คืนค่าเป็นอ็อบเจกต์ `Date`. ใช้ตัวจัดรูปแบบหากคุณต้องการแสดงผลในรูปแบบที่กำหนดเอง.

## คำถามที่พบบ่อย

### Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?
ใช่, Aspose.Tasks for Java มีความสามารถที่แข็งแกร่งในการจัดการโครงการที่มีความซับซ้อนในระดับต่างๆ อย่างมีประสิทธิภาพ.

### Aspose.Tasks for Java เข้ากันได้กับไลบรารี Java อื่นหรือไม่?
แน่นอน, Aspose.Tasks for Java สามารถผสานรวมอย่างราบรื่นกับไลบรารี Java อื่น, เพิ่มศักยภาพการจัดการโครงการของคุณ.

### ฉันสามารถปรับแต่ง baseline ของงานโดยใช้ Aspose.Tasks for Java ได้หรือไม่?
ได้เลย, Aspose.Tasks for Java มีฟังก์ชันการทำงานที่ครอบคลุมเพื่อปรับแต่งและจัดการ baseline ของงานตามความต้องการของโครงการของคุณ.

### มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for Java หรือไม่?
มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.Tasks for Java จาก [release page](https://releases.aspose.com/).

### จะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
สำหรับคำถามหรือความช่วยเหลือใด ๆ คุณสามารถเยี่ยมชมฟอรั่ม Aspose.Tasks ได้ที่ [here](https://forum.aspose.com/c/tasks/15).

## Frequently Asked Questions

**Q: ฉันจะสร้างอินสแตนซ์ Project ใหม่ใน Aspose.Tasks อย่างไร?**  
A: สร้างอ็อบเจกต์ `Project` (`Project project = new Project();`). วิธีนี้จะสร้างไฟล์โปรเจกต์ใหม่พร้อมสำหรับงานและ baseline.

**Q: ความแตกต่างระหว่าง `BaselineType.Baseline` กับประเภท baseline อื่นคืออะไร?**  
A: `BaselineType.Baseline` หมายถึง baseline หลัก (Baseline 1). Aspose.Tasks ยังรองรับ Baseline 2‑10 สำหรับการบันทึกสแนปช็อตเพิ่มเติม.

**Q: ฉันสามารถส่งออกข้อมูล baseline ไปเป็น Excel หรือ CSV ได้หรือไม่?**  
A: ได้, คุณสามารถวนลูปผ่านอ็อบเจกต์ `TaskBaseline` แล้วเขียนค่าลงไฟล์ CSV ด้วย I/O ของ Java มาตรฐาน.

**Q: การตั้ง baseline มีผลต่อวันที่ของงานที่มีอยู่หรือไม่?**  
A: การตั้ง baseline จะบันทึกวันที่ปัจจุบันแต่ไม่เปลี่ยนแปลงกำหนดการทำงานที่ใช้งานอยู่ คุณยังสามารถปรับวันที่เริ่มต้น/สิ้นสุดหลังจากตั้ง baseline ได้.

**Q: สามารถเปรียบเทียบหลาย baseline ได้โดยโปรแกรมหรือไม่?**  
A: ได้เลย. ดึงแต่ละ baseline ผ่าน `task.getBaselines().get(index)` แล้วเปรียบเทียบคุณสมบัติ `Start`, `Finish`, และ `Duration`.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-18  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose