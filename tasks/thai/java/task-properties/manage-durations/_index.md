---
date: 2026-02-20
description: สำรวจวิธีเพิ่มงานลงในโครงการและจัดการระยะเวลาโดยใช้ Aspose.Tasks สำหรับ
  Java เรียนรู้วิธีตั้งระยะเวลาและวิธีแปลงระยะเวลาได้อย่างง่ายดาย.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: เพิ่มงานลงในโครงการและจัดการระยะเวลาโดยใช้ Aspose.Tasks
url: /th/java/task-properties/manage-durations/
weight: 20
---

 any code block placeholders or URLs. Good.

Check any other text: "step-by-step" not needed.

Make sure we keep markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มงานลงในโครงการและจัดการระยะเวลาโดยใช้ Aspose.Tasks

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีเพิ่มงานลงในโครงการ** และควบคุมระยะเวลาของมันโดยใช้ Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะกำลังสร้างเครื่องมือวางแผนโครงการใหม่หรือขยายโซลูชันที่มีอยู่ การเชี่ยวชาญการจัดการระยะเวลาของงานเป็นสิ่งสำคัญสำหรับการกำหนดเวลาและการรายงานที่แม่นยำ

## คำตอบอย่างรวดเร็ว
- **“add task to project” หมายถึงอะไร?** มันสร้างอ็อบเจกต์งานใหม่ภายใต้รูทของโครงการหรือภายใต้งานสรุปเฉพาะ  
- **คลาสใดที่แสดงถึงระยะเวลา?** `com.aspose.tasks.Duration`.  
- **จะตั้งระยะเวลาอย่างไร?** ใช้ `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **ฉันสามารถแปลงระยะเวลาเป็นหน่วยอื่นได้หรือไม่?** ได้, เรียก `duration.convert(TimeUnitType.Hour)` หรือ `TimeUnitType` ใด ๆ  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์

## อะไรคือ “add task to project”?
การเพิ่มงานลงในโครงการหมายถึงการสร้างอ็อบเจกต์ `Task` และผูกมันเข้ากับโครงสร้างงานของโครงการ การดำเนินการนี้เป็นขั้นตอนแรกก่อนที่คุณจะสามารถกำหนดงาน, ทรัพยากร หรือระยะเวลาสำหรับงานนั้นได้

## ทำไมต้องจัดการระยะเวลาของงาน?
ระยะเวลาที่แม่นยำทำให้ได้ไทม์ไลน์ที่เป็นจริง การจัดสรรทรัพยากร และการวิเคราะห์เส้นทางวิกฤติ ด้วย Aspose.Tasks คุณสามารถตั้งค่า, อ่าน, แปลงและปรับระยะเวลาโดยโปรแกรมได้ ทำให้คุณมีการควบคุมเต็มที่ต่อกำหนดการของโครงการ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: ดาวน์โหลดและใส่ไลบรารี Aspose.Tasks ลงในโครงการของคุณ คุณสามารถหาไลบรารีได้จาก [here](https://releases.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ, นำเข้าแพ็กเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
```java
// Create a new project
Project project = new Project();
```

## ขั้นตอนที่ 2: เพิ่มงานใหม่ (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## วิธีตั้งระยะเวลา
เมื่อมีงานแล้ว, คุณสามารถกำหนดความยาวของมันได้ โดยค่าเริ่มต้น, ระยะเวลาจะแสดงเป็นวัน

## ขั้นตอนที่ 3: รับและแปลงระยะเวลาของงาน
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## วิธีแปลงระยะเวลา
เมธอด `convert` ช่วยให้คุณแปลง `Duration` จาก `TimeUnitType` หนึ่งเป็นอีกหน่วยหนึ่ง (เช่น วัน → ชั่วโมง, สัปดาห์ → วัน).

## ขั้นตอนที่ 4: ปรับระยะเวลาของงานเป็น 1 สัปดาห์
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## ขั้นตอนที่ 5: ลดระยะเวลาของงาน
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

โดยทำตามขั้นตอนเหล่านี้, คุณได้ **เพิ่มงานลงในโครงการ** และจัดการระยะเวลาของมันโดยใช้ Aspose.Tasks สำหรับ Java อย่างสำเร็จ

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาด:** ลืมแปลงระยะเวลาก่อนทำการคำนวณอาจทำให้ผลลัพธ์ไม่ถูกต้อง ตรวจสอบหน่วยเสมอด้วย `duration.getTimeUnit()`.
- **เคล็ดลับ:** ใช้ `project.getDuration(value, TimeUnitType)` เพื่อสร้างระยะเวลาในหน่วยที่ต้องการแทนการแปลงภายหลัง.
- **ข้อผิดพลาด:** การตั้งระยะเวลาเป็นค่าลบจะทำให้เกิดข้อยกเว้น ตรวจสอบค่าที่ป้อนให้ถูกต้อง.

## สรุป
ในคู่มือนี้เราได้อธิบายวิธี **เพิ่มงานลงในโครงการ**, อ่านระยะเวลาเริ่มต้นของมัน, **ตั้งระยะเวลา**, และ **แปลงระยะเวลา** ไปยังหน่วยเวลาอื่น ๆ คุณสามารถนำเทคนิคเหล่านี้ไปใช้ในแอปพลิเคชันการจัดตารางที่ใหญ่ขึ้นเพื่อการวางแผนโครงการที่แม่นยำ

## คำถามที่พบบ่อย
### Aspose.Tasks รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?
Aspose.Tasks รองรับ Java 6 และเวอร์ชันต่อ ๆ ไป

### ฉันสามารถใช้ Aspose.Tasks สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?
ได้, คุณสามารถใช้ Aspose.Tasks ทั้งสำหรับโครงการส่วนบุคคลและเชิงพาณิชย์ เยี่ยมชม [here](https://purchase.aspose.com/buy) สำหรับรายละเอียดไลเซนส์

### ฉันสามารถหาแหล่งสนับสนุนและทรัพยากรเพิ่มเติมได้ที่ไหน?
เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

### ฉันจะขอรับไลเซนส์ชั่วคราวเพื่อการทดสอบได้อย่างไร?
คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล

### มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks หรือไม่?
ได้, คุณสามารถเข้าถึงการทดลองใช้ฟรีได้จาก [here](https://releases.aspose.com/) เพื่อสำรวจ Aspose.Tasks ก่อนทำการซื้อ

## คำถามที่พบบ่อย

**Q: ฉันจะเปลี่ยนระยะเวลาของงานหลังจากที่ตั้งค่าแล้วได้อย่างไร?**  
A: ดึงระยะเวลาปัจจุบันด้วย `task.get(Tsk.DURATION)`, แก้ไข (เช่น `add`, `subtract`, หรือ `convert`), แล้วตั้งค่าใหม่ด้วย `task.set(Tsk.DURATION, newDuration)`.

**Q: ฉันสามารถตั้งระยะเวลาเป็นนาทีได้หรือไม่?**  
A: ได้, ใช้ `TimeUnitType.Minute` เมื่อเรียก `project.getDuration(value, TimeUnitType.Minute)`.

**Q: การเปลี่ยนระยะเวลาจะอัปเดตวันเริ่มต้นและสิ้นสุดของงานโดยอัตโนมัติหรือไม่?**  
A: จะทำได้เฉพาะเมื่อโหมดการกำหนดเวลาของโครงการตั้งเป็นอัตโนมัติ มิฉะนั้นคุณอาจต้องคำนวณตารางใหม่ด้วย `project.calculateCriticalPath()`.

**Q: สามารถดึงระยะเวลาเป็นค่าตัวเลขดิบได้หรือไม่?**  
A: เรียก `duration.getTimeSpan()` เพื่อรับค่าตัวเลขในหน่วยเวลาปัจจุบัน.

**Q: จะเกิดอะไรขึ้นหากฉันลบมากกว่าระยะเวลาปัจจุบัน?**  
A: API จะโยน `ArgumentOutOfRangeException` ตรวจสอบให้แน่ใจว่าระยะเวลาที่ได้ยังคงเป็นบวกเสมอ.

---

**อัปเดตล่าสุด:** 2026-02-20  
**ทดสอบด้วย:** Aspose.Tasks for Java (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}