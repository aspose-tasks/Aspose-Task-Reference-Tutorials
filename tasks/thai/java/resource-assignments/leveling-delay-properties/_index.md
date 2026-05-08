---
date: 2026-01-07
description: เรียนรู้วิธีเพิ่มทรัพยากรลงในโครงการและจัดการคุณสมบัติการหน่วงระดับสำหรับการมอบหมายทรัพยากรโดยใช้
  Aspose.Tasks สำหรับ Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีเพิ่มทรัพยากรลงในโครงการและจัดการคุณสมบัติการหน่วงเวลาเลเวลใน Aspose.Tasks
url: /th/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มทรัพยากรลงในโครงการและจัดการคุณสมบัติการหน่วงเวลาการปรับระดับใน Aspose.Tasks

## บทนำ
ในบทเรียนนี้ คุณจะได้เรียนรู้ **วิธีเพิ่มทรัพยากรลงในโครงการ** พร้อมกับการจัดการคุณสมบัติการหน่วงเวลาการปรับระดับสำหรับการมอบหมายทรัพยากรด้วย Aspose.Tasks for Java ไม่ว่าคุณจะกำลังสร้างเครื่องมือจัดตารางเวลา หรือทำอัตโนมัติการอัปเดตโครงการ การเข้าใจขั้นตอนเหล่านี้จะช่วยให้คุณรักษาข้อมูลโครงการให้แม่นยำโดยไม่ต้องติดตั้ง Microsoft Project

## คำตอบสั้น
- **“เพิ่มทรัพยากรลงในโครงการ” หมายถึงอะไร?** มันสร้างรายการทรัพยากรใหม่ที่สามารถมอบหมายให้กับงานได้  
- **ฉันสามารถตั้งค่าการหน่วงเวลาการปรับระดับหลังการมอบหมายได้หรือไม่?** ได้ โดยใช้ฟิลด์ `Asn.DELAY` หรือ `Asn.LEVELING_DELAY`  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันโค้ดนี้หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์แบบชำระเงินสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือใหม่กว่า  
- **เข้ากันได้กับรูปแบบไฟล์ MS Project ทั้งหมดหรือไม่?** Aspose.Tasks รองรับ .MPP, .XML, .XER และอื่น ๆ  

## “เพิ่มทรัพยากรลงในโครงการ” ใน Aspose.Tasks คืออะไร?
การเพิ่มทรัพยากรลงในโครงการหมายถึงการสร้างอ็อบเจ็กต์ `Resource` ภายในโมเดล `Project` ซึ่งอ็อบเจ็กต์นี้สามารถเชื่อมโยงกับงานผ่าน `ResourceAssignment` เพื่อให้คุณติดตามงาน, ค่าใช้จ่าย, และการตั้งค่าการปรับระดับได้

## ทำไมต้องจัดการคุณสมบัติการหน่วงเวลาการปรับระดับ?
การหน่วงเวลาการปรับระดับช่วยให้ตัวจัดตารางกระจายงานเมื่อทรัพยากรถูกจัดสรรเกินกำลัง โดยการตั้งค่าหน่วงเวลา คุณบอกให้เครื่องมือเลื่อนการเริ่มต้นของการมอบหมายออกไป เพื่อหลีกเลี่ยงความขัดแย้งและทำให้โครงการเป็นจริงมากขึ้น

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
1. **Java Development Kit (JDK):** ตรวจสอบว่าคุณได้ติดตั้ง Java JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งได้จาก [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html)  
2. **Aspose.Tasks for Java Library:** ดาวน์โหลดไลบรารี Aspose.Tasks for Java จาก [download page](https://releases.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
ก่อนอื่น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณเพื่อใช้ฟังก์ชันของ Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Project
สร้างอ็อบเจ็กต์ `Project` ซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับงาน, ทรัพยากร, และการมอบหมายทั้งหมด:
```java
Project prj = new Project();
```

## ขั้นตอนที่ 2: สร้างงาน
เพิ่มงานลงในโครงการ ซึ่งจะแสดง **วิธีเพิ่มงาน** อย่างโปรแกรมเมติก:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## ขั้นตอนที่ 3: กำหนดวันที่เริ่มต้นและระยะเวลาของงาน
ระบุเวลาที่งานจะเริ่มต้นและระยะเวลาที่งานจะดำเนินการ:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## ขั้นตอนที่ 4: เพิ่มทรัพยากร
ตอนนี้เราจะ **เพิ่มทรัพยากรลงในโครงการ** โดยการสร้างรายการ `Resource` ใหม่:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## ขั้นตอนที่ 5: สร้างการมอบหมายทรัพยากร
เชื่อมโยงงานกับทรัพยากรที่เพิ่งเพิ่มเข้ามา:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## ขั้นตอนที่ 6: ตั้งค่าการหน่วงเวลาการปรับระดับ
กำหนดการหน่วงเวลาการปรับระดับสำหรับการมอบหมาย การตั้งค่าเป็นศูนย์หมายถึงไม่มีการหน่วงเวลาเพิ่มเติม แต่คุณสามารถปรับค่าได้ตามต้องการ:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## ขั้นตอนที่ 7: แสดงผลลัพธ์
พิมพ์คุณสมบัติสำคัญเพื่อยืนยันว่าทุกอย่างถูกตั้งค่าอย่างถูกต้อง:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาด:** ลืมกำหนดวันที่เริ่มต้นของงานอาจทำให้การมอบหมายเริ่มต้นที่วันเริ่มต้นของโครงการโดยอัตโนมัติ  
- **เคล็ดลับ:** ใช้ `prj.getDuration(value, TimeUnitType.Day)` เพื่อควบคุมความละเอียดของการหน่วงเวลา  
- **เคล็ดลับ:** หลังจากเพิ่มทรัพยากรหลายรายการ ให้เรียก `prj.updateResourceAssignments()` เพื่อให้ตัวจัดตารางคำนวณการปรับระดับใหม่  

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้ **วิธีเพิ่มทรัพยากรลงในโครงการ**, มอบหมายให้กับงาน, และจัดการคุณสมบัติการหน่วงเวลาการปรับระดับด้วย Aspose.Tasks for Java ความรู้นี้จะช่วยให้คุณสร้างโซลูชันอัตโนมัติโครงการที่แข็งแรงและสอดคล้องกับข้อจำกัดของทรัพยากรในโลกจริง

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.Tasks ร่วมกับไลบรารี Java อื่นได้หรือไม่?
A: ได้, Aspose.Tasks สามารถผสานรวมกับไลบรารี Java อื่นเพื่อเพิ่มความสามารถในการจัดการโครงการได้

### Q: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่าง ๆ หรือไม่?
A: รองรับ, Aspose.Tasks รองรับไฟล์ Microsoft Project หลายเวอร์ชัน ทำให้เข้ากันได้กับสภาพแวดล้อมที่หลากหลาย

### Q: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้จากที่ไหน?
A: คุณสามารถค้นหาแหล่งสนับสนุนและทรัพยากรได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

### Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?
A: ได้, คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Tasks จาก [releases page](https://releases.aspose.com/)

### Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?
A: คุณสามารถขอรับลิขสิทธิ์ชั่วคราวจาก [temporary license page](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินผล

## คำถามที่พบบ่อยเพิ่มเติม

**Q: จะเกิดอะไรขึ้นหากฉันตั้งค่าการหน่วงเวลาการปรับระดับเป็นค่าที่ไม่เป็นศูนย์?**  
A: ตัวจัดตารางจะเลื่อนการเริ่มต้นของการมอบหมายตามระยะเวลาที่ระบุ ช่วยแก้ไขการจัดสรรเกินกำลัง

**Q: ฉันสามารถดึงค่าการหน่วงเวลาการปรับระดับหลังจากบันทึกโครงการได้หรือไม่?**  
A: ได้, คุณสามารถเปิดไฟล์โครงการใหม่และอ่านคุณสมบัติ `Asn.DELAY` จากการมอบหมายได้

**Q: มีวิธีใดบ้างที่จะตั้งค่าการหน่วงเวลาการปรับระดับให้กับการมอบหมายทั้งหมดพร้อมกัน?**  
A: คุณสามารถวนลูปผ่าน `prj.getResourceAssignments()` แล้วตั้งค่าการหน่วงเวลาสำหรับแต่ละการมอบหมายในลูปได้

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}