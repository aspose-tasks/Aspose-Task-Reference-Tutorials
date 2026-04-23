---
date: 2026-01-23
description: เรียนรู้วิธีตั้งระยะเวลา baseline และสร้างอินสแตนซ์ของโครงการโดยใช้ Aspose.Tasks
  สำหรับ Java คู่มือขั้นตอนนี้ช่วยให้คุณจัดการ baseline ของงานได้อย่างมีประสิทธิภาพ
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: วิธีตั้งระยะเวลาเบสไลน์ใน Aspose.Tasks สำหรับ Java
url: /th/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งระยะเวลา Baseline ใน Aspose.Tasks สำหรับ Java

## บทนำ
การตั้ง baseline เป็นขั้นตอนพื้นฐานในการติดตามความคืบหน้าของโครงการเทียบกับแผนเดิม ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีตั้ง baseline** ระยะเวลา สำหรับงานใน Microsoft Project ด้วยไลบรารี Aspose.Tasks สำหรับ Java และเห็นว่าการสร้าง baseline ตั้งแต่แรกจะช่วยประหยัดเวลาและปัญหาในภายหลังอย่างไร

## คำตอบอย่างรวดเร็ว
- **“set baseline” หมายถึงอะไร?** มันบันทึกค่าเริ่มต้น วันที่เริ่มต้น วันที่สิ้นสุด และระยะเวลาของงานต้นฉบับ เพื่อให้คุณสามารถเปรียบเทียบการเปลี่ยนแปลงในอนาคตได้.  
- **คลาส Aspose.Tasks ใดที่สร้างโปรเจกต์?** คลาส `Project` – คุณจะได้เรียนรู้วิธี **สร้างอินสแตนซ์โปรเจกต์** อย่างถูกต้องด้วย.  
- **ฉันต้องมีไลเซนส์เพื่อรันโค้ดหรือไม่?** ไลเซนส์ทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถดึง Baseline ชั่วคราวได้หรือไม่?** ได้, Aspose.Tasks ให้คุณสอบถาม Baseline ชั่วคราวและค่าใช้จ่ายคงที่ของมัน.  
- **ต้องการเวอร์ชัน Java ใด?** แนะนำให้ใช้ Java 8 หรือใหม่กว่า.

## Baseline ของงานคืออะไรและทำไมต้องตั้งมัน?
Baseline ของงานบันทึกตารางเวลาที่วางแผนไว้ (วันที่เริ่มต้น วันที่สิ้นสุด และระยะเวลา) ณ จุดเวลาเฉพาะ การตั้ง baseline จะสร้างจุดอ้างอิงที่ทำให้คุณสามารถตรวจจับการเบี่ยงเบนของตารางเวลา การเกินงบประมาณ และการจัดสรรทรัพยากรเกินพิกัดได้ง่ายเมื่อโครงการดำเนินไป

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดการ baseline?
- **รองรับไฟล์ .mpp อย่างเต็มรูปแบบ** – อ่านและเขียนไฟล์ Microsoft Project แบบดั้งเดิมโดยไม่ต้องติดตั้ง Office.  
- **API ครบครัน** – เข้าถึงข้อมูล baseline, baseline ชั่วคราว, และข้อมูลตามช่วงเวลาโดยโปรแกรม.  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS กับ JDK มาตรฐานใดก็ได้.

## ข้อกำหนดเบื้องต้น
1. **สภาพแวดล้อมการพัฒนา Java** – ติดตั้งและกำหนดค่า JDK 8+.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีจาก [here](https://releases.aspose.com/tasks/java/).  
3. **IDE หรือเครื่องมือสร้าง** – Maven, Gradle หรือ IDE ใดก็ได้ที่คุณชอบ.

## นำเข้าแพ็กเกจ
ก่อนแรก ให้นำเข้าคลาสที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project
การสร้างอินสแตนซ์โปรเจกต์เป็นพื้นฐานสำหรับการจัดการต่อไป ขั้นตอนนี้จะแสดงวิธี **สร้างอินสแตนซ์โปรเจกต์** ด้วย Aspose.Tasks:

```java
Project project = new Project();
```

## ขั้นตอนที่ 2: สร้าง Baseline ของงาน
เพิ่มงานใหม่ลงในโหนดรากของโปรเจกต์และตั้ง Baseline ของมัน ซึ่งจะบันทึกตารางเวลาต้นฉบับของงาน:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## ขั้นตอนที่ 3: แสดงข้อมูล Baseline ของงาน
ดึง Baseline ที่คุณสร้างขึ้นมาและพิมพ์คุณสมบัติหลักของมัน ช่วยให้คุณตรวจสอบว่า Baseline ถูกตั้งอย่างถูกต้อง:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## ขั้นตอนที่ 4: ตรวจสอบ Baseline ชั่วคราวและค่าใช้จ่ายคงที่
หากคุณทำงานกับ Baseline ชั่วคราว คุณสามารถสอบถามได้ว่า Baseline ปัจจุบันเป็นชั่วคราวหรือไม่และค่าใช้จ่ายคงที่ที่เกี่ยวข้อง:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## ขั้นตอนที่ 5: พิมพ์ข้อมูล Time‑phased
ข้อมูล Time‑phased แสดงว่าการกระจาย Baseline เป็นอย่างไรตามช่วงเวลา วนลูปผ่านคอลเลกชันเพื่อตรวจสอบแต่ละรายการ:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

โดยทำตามขั้นตอนเหล่านี้ คุณสามารถ **วิธีตั้ง baseline** ระยะเวลาให้กับงานใด ๆ และดึงข้อมูลรายละเอียดของ baseline ด้วย Aspose.Tasks สำหรับ Java

## ปัญหาทั่วไปและวิธีแก้
- **Baseline ไม่แสดงใน MS Project:** ตรวจสอบว่าคุณเรียก `project.setBaseline(BaselineType.Baseline)` **หลังจาก** เพิ่มงานแล้ว.  
- **NullPointerException ที่ `getBaselines()`:** ยืนยันว่ามีการเพิ่มงานเข้าสู่โปรเจกต์ก่อนตั้ง Baseline.  
- **หน่วยเวลาไม่ตรงกัน:** ใช้ `TimeUnitType` เพื่อจัดรูปแบบระยะเวลาให้ถูกต้อง โดยเฉพาะเมื่อทำงานกับปฏิทินที่กำหนดเอง.

## คำถามที่พบบ่อย
### Baseline ของงานใน MS Project คืออะไร?
Baseline ของงานใน MS Project คือภาพสแนปช็อตของตารางเวลาที่วางแผนไว้เริ่มแรกของงาน รวมถึงวันที่เริ่มต้น วันที่สิ้นสุด และระยะเวลา.

### ทำไมการจัดการ Baseline ของงานจึงสำคัญ?
การจัดการ Baseline ของงานช่วยให้เปรียบเทียบตารางเวลาที่วางแผนกับความคืบหน้าจริงของโครงการ ทำให้การติดตามและการตัดสินใจดีขึ้น.

### ฉันสามารถแก้ไข Baseline ของงานได้หลังจากตั้งแล้วหรือไม่?
ได้, คุณสามารถแก้ไข Baseline ของงานใน MS Project เพื่อสะท้อนการเปลี่ยนแปลงในแผนโครงการ อย่างไรก็ตาม จำเป็นต้องบันทึกความแตกต่างใด ๆ จาก Baseline ดั้งเดิม.

### Aspose.Tasks รองรับฟังก์ชันการจัดการโครงการอื่น ๆ หรือไม่?
ใช่, Aspose.Tasks มีฟีเจอร์หลากหลายสำหรับการจัดการโครงการ รวมถึงการกำหนดเวลา งาน การจัดสรรทรัพยากร และการสร้างแผนภูมิ Gantt.

### ฉันสามารถหาการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน?
คุณสามารถหาการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) ซึ่งคุณสามารถถามคำถามและโต้ตอบกับผู้ใช้คนอื่นได้.

## คำถามที่พบบ่อยเพิ่มเติม
**Q: ฉันต้องเรียก `setBaseline` สำหรับแต่ละงานแยกกันหรือไม่?**  
A: ไม่จำเป็น. การเรียก `project.setBaseline(BaselineType.Baseline)` จะบันทึก Baseline สำหรับงานทั้งหมดในโปรเจกต์พร้อมกัน.

**Q: ฉันจะตั้ง Baseline ชั่วคราวสำหรับงานเฉพาะได้อย่างไร?**  
A: ใช้ `project.setBaseline(BaselineType.Baseline1)` (หรือ Baseline2‑Baseline10) หลังจากอัปเดตตารางเวลาของงานนั้น.

**Q: สามารถส่งออกข้อมูล Baseline เป็น CSV ได้หรือไม่?**  
A: ได้. ทำการวนซ้ำ `task.getBaselines()` แล้วเขียนฟิลด์ที่ต้องการลงไฟล์ CSV ด้วย Java I/O มาตรฐาน.

**Q: ฉันสามารถอ่านไฟล์ .mpp ที่มี Baseline อยู่แล้วได้หรือไม่?**  
A: แน่นอน. โหลดไฟล์ด้วย `new Project("myproject.mpp")` แล้วเข้าถึง Baseline ของแต่ละงานตามที่แสดงข้างต้น.

**Q: Aspose.Tasks รองรับไฟล์หลายโปรเจกต์หรือไม่?**  
A: Aspose.Tasks ทำงานกับไฟล์ .mpp แบบโปรเจกต์เดียว สำหรับสถานการณ์หลายโปรเจกต์ ให้รวมโปรเจกต์เข้าด้วยกันโดยโปรแกรม.

---

**อัปเดตล่าสุด:** 2026-01-23  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}