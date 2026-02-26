---
date: 2026-02-26
description: เรียนรู้วิธีแยกงานด้วย Aspose.Tasks for Java – คู่มือที่ครอบคลุมเกี่ยวกับวิธีแยกงาน,
  ตั้งปฏิทินโครงการ, และสร้างการมอบหมายทรัพยากร.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีแยกงานใน Aspose.Tasks
url: /th/java/task-properties/split-tasks/
weight: 29
---

 "อัปเดตล่าสุด:"

"Tested With:" => "ทดสอบด้วย:"

"Author:" => "ผู้เขียน:"

Then closing shortcodes.

Make sure to keep markdown formatting: headings, bold, lists, links.

Also keep code block placeholders unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแยกงานใน Aspose.Tasks

## บทนำ
หากคุณกำลังมองหา **วิธีแยกงาน** ในโครงการที่ใช้ Java, คุณมาถูกที่แล้ว Aspose.Tasks for Java มอบวิธีการเชิงโปรแกรมที่สะอาดตาเพื่อแบ่งงานที่ใช้เวลานานออกเป็นส่วนย่อยที่จัดการได้ง่าย ซึ่งช่วยในการปรับระดับทรัพยากร, รายงานที่แม่นยำ, และกำหนดเวลาโครงการที่เข้มงวดมากขึ้น ในบทเรียนนี้เราจะเดินผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าปฏิทินโครงการจนถึงการสร้างการมอบหมายทรัพยากรและสุดท้ายการแยกงานออกเป็นหลายส่วน

## คำตอบสั้น
- **Task splitting คืออะไร?** การแบ่งงานเดียวเป็นหลายช่วงย่อยขณะยังคงรักษาระยะเวลารวมไว้  
- **ทำไมต้องแยกงานใน Java?** ช่วยให้การจัดสรรทรัพยากรแม่นยำและการติดตามความคืบหน้าได้ดียิ่งขึ้น  
- **ไลบรารีใดช่วยได้?** Aspose.Tasks for Java มีเมธอดในตัวสำหรับการแยกและการทำ Time‑phasing  
- **ต้องการไลเซนส์หรือไม่?** สามารถใช้เวอร์ชันทดลองฟรีสำหรับการพัฒนา; ต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** ไลบรารีทำงานกับ Java 8 และใหม่กว่า

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทเรียน, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:
- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Tasks for Java ดาวน์โหลดและเพิ่มเข้าในโปรเจกต์ของคุณ คุณสามารถดาวน์โหลดได้จาก [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## ขั้นตอนที่ 1: สร้างโปรเจกต์ใหม่
สร้างโปรเจกต์ใหม่โดยใช้ไลบรารี Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## ขั้นตอนที่ 2: ตั้งค่าปฏิทินโปรเจกต์
การตั้งค่า **project calendar** กำหนดวันทำงาน, วันหยุด, และไทม์ไลน์โดยรวมสำหรับตารางของคุณ ขั้นตอนนี้สำคัญสำหรับการคำนวณ Time‑phased ที่แม่นยำ

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## ขั้นตอนที่ 3: เพิ่มงานราก
ทุกโปรเจกต์ต้องมีคอนเทนเนอร์ราก การเพิ่มงานรากจะให้จุดเชื่อมต่อสำหรับงานทั้งหมดที่ตามมา

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## ขั้นตอนที่ 4: เพิ่มงานใหม่เพื่อแยก
สร้างงานที่คุณต้องการจะแยก ในตัวอย่างนี้เรากำหนดระยะเวลาเป็นสามวันเป็นตัวอย่าง

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## ขั้นตอนที่ 5: สร้างการมอบหมายทรัพยากร
**Resource assignment** เชื่อมทรัพยากร (หรือ placeholder) กับงาน ซึ่งจำเป็นก่อนการสร้างข้อมูล Time‑phased

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## ขั้นตอนที่ 6: สร้างข้อมูล Timephased
ข้อมูล Time‑phased แสดงว่าการทำงานกระจายอย่างไรตลอดระยะเวลาของงาน การสร้างข้อมูลนี้เตรียมงานให้พร้อมสำหรับการแยก

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## ขั้นตอนที่ 7: แยกงาน
ตอนนี้เราจะ **แยกงานออกเป็นส่วน** ในตัวอย่างนี้เราจะแบ่งงานสามวันเป็นสามส่วนวันละหนึ่งวัน

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## ทำไมต้องแยกงาน?
การแยกงานให้คุณควบคุมได้ละเอียดขึ้นในด้าน:
- **Resource leveling:** มอบหมายทรัพยากรที่แตกต่างให้กับแต่ละส่วน  
- **Progress tracking:** อัปเดตสถานะตามแต่ละส่วน  
- **Reporting:** สร้าง Gantt chart และรายงานที่ละเอียดมากขึ้น

## ปัญหาที่พบบ่อยและวิธีแก้
- **Missing calendar data:** ตรวจสอบให้แน่ใจว่าคุณเรียก `timephasedDataFromTaskDuration` ก่อนทำการแยก  
- **Zero‑duration segments:** ตรวจสอบว่าช่วงเวลาที่แยกแต่ละช่วงมีระยะเวลาไม่เป็นศูนย์; มิฉะนั้นไลบรารีจะละเลยมัน  
- **License exceptions:** การรันโดยไม่มีไลเซนส์ที่ถูกต้องอาจทำให้ไฟล์ที่ส่งออกมีลายน้ำ

## คำถามที่พบบ่อย
### ฉันสามารถแยกงานโดยมีระยะเวลาต่างกันได้หรือไม่?
ได้, คุณสามารถปรับระยะเวลาของแต่ละส่วนให้ตรงกับความต้องการของโครงการของคุณ

### Aspose.Tasks for Java เข้ากันได้กับเวอร์ชัน Java ทั้งหมดหรือไม่?
Aspose.Tasks for Java ถูกออกแบบให้ทำงานอย่างราบรื่นกับ Java 8 และใหม่กว่า, เพื่อความเข้ากันได้อย่างกว้างขวาง

### ฉันสามารถใช้ Aspose.Tasks for Java ได้ฟรีหรือไม่?
Aspose.Tasks for Java มีเวอร์ชันทดลองฟรี, ให้คุณสำรวจคุณสมบัติก่อนตัดสินใจซื้อ

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้อย่างไร?
เยี่ยมชม [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือและเชื่อมต่อกับชุมชน

### ฉันต้องการใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks for Java หรือไม่?
คุณสามารถรับใบอนุญาตชั่วคราวจาก [this link](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบและประเมินผล

---

**อัปเดตล่าสุด:** 2026-02-26  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}