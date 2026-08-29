---
date: 2026-03-29
description: เรียนรู้วิธีจัดกำหนดการใหม่สำหรับงานที่ยังไม่เสร็จ, ปรับปรุงงานโครงการ,
  และบันทึกไฟล์ MS Project เป็น XML ด้วย Aspose.Tasks สำหรับ Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: กำหนดเวลางานที่ยังไม่เสร็จและอัปเดตไฟล์ MS Project ด้วย Aspose.Tasks
url: /th/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดเวลางานที่ยังไม่เสร็จและอัปเดตไฟล์ MS Project ด้วย Aspose.Tasks

## บทนำ
Microsoft Project เป็นเครื่องมือการจัดการโครงการที่ใช้กันอย่างแพร่หลายซึ่งช่วยให้ทีมวางแผนงาน จัดสรรทรัพยากร และติดตามกำหนดเวลา Aspose.Tasks สำหรับ Java มอบ API ที่ครบถ้วนให้กับนักพัฒนาเพื่อจัดการไฟล์ Microsoft Project อย่างโปรแกรมเมติก ในบทเรียนนี้ คุณจะได้เรียนรู้วิธี **อัปเดตงานของโครงการ**, **กำหนดเวลางานที่ยังไม่เสร็จ**, และ **บันทึกไฟล์ MS Project** ในรูปแบบ XML โดยใช้ Aspose.Tasks สำหรับ Java

## คำตอบสั้น
- **“กำหนดเวลางานที่ยังไม่เสร็จ” หมายความว่าอะไร?** มันจะย้ายงานที่เหลือของแต่ละงานให้เริ่มหลังจากวันที่เลือกไว้ โดยส่วนที่ทำเสร็จแล้วจะไม่ถูกเปลี่ยนแปลง  
- **เมธอดใดที่ทำเครื่องหมายว่างานเสร็จแล้ว?** `project.updateProjectWorkAsComplete(date, false)`  
- **ฉันจะบันทึกการเปลี่ยนแปลงอย่างไร?** Use `project.save(<path>, SaveFileFormat.Xml)`  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์  
- **เวอร์ชัน Java ใดที่รองรับ?** Java 8 และรุ่นต่อมาถูกสนับสนุนเต็มที่  

## “กำหนดเวลางานที่ยังไม่เสร็จ” คืออะไร?
การกำหนดเวลางานที่ยังไม่เสร็จจะปรับวันที่เริ่มของงานทั้งหมดที่ยังไม่เสร็จสมบูรณ์ให้เริ่มหลังจากวันที่กำหนดเป็นเกณฑ์ ซึ่งเป็นประโยชน์เมื่อไทม์ไลน์ของโครงการต้องเปลี่ยนแปลงเนื่องจากความล่าช้าหรือการเปลี่ยนแปลงขอบเขต

## ทำไมต้องใช้ Aspose.Tasks เพื่ออัปเดตงานของโครงการและกำหนดเวลางานใหม่?
- **Fine‑grained control:** ตั้งเปอร์เซ็นต์การเสร็จสมบูรณ์ของงานและวันที่โดยตรง  
- **No UI required:** ทำการอัปเดตเป็นกลุ่มโดยอัตโนมัติในหลายไฟล์โครงการ  
- **Cross‑platform:** ทำงานบนระบบใดก็ได้ที่รัน Java  
- **Preserves data integrity:** การพึ่งพา, ข้อจำกัดและทรัพยากรทั้งหมดจะคงความสอดคล้อง  

## ข้อกำหนดเบื้องต้น
1. Java Development Kit (JDK) ที่ติดตั้งบนระบบของคุณ  
2. ไลบรารี Aspose.Tasks สำหรับ Java คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/)  
3. ความเข้าใจพื้นฐานของภาษาโปรแกรม Java  

## นำเข้าแพ็กเกจ
ก่อนอื่น ให้นำเข้าแพ็กเกจที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์
สร้างอ็อบเจกต์ `Project` ใหม่ กำหนดงาน ตั้งระยะเวลา และสร้างความสัมพันธ์ระหว่างงาน ซึ่งจะเป็นโครงสร้างพื้นฐานของโครงการที่เราจะอัปเดตและกำหนดเวลาใหม่ภายหลัง
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## ขั้นตอนที่ 2: อัปเดตงานของโครงการ
ทำเครื่องหมายว่างานเสร็จสมบูรณ์จนถึงวันที่ระบุ ขั้นตอนนี้แสดงการทำงาน **update project work** ซึ่งมักเป็นการกระทำแรกก่อนการกำหนดเวลาใหม่
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## ขั้นตอนที่ 3: กำหนดเวลางานที่ยังไม่เสร็จใหม่
ตอนนี้เราจะย้ายงานที่เหลือ (ยังไม่เสร็จ) ให้เริ่มหลังจากวันที่กำหนดเป็นเกณฑ์เดียวกัน ซึ่งเป็นฟังก์ชันหลักของ **reschedule uncompleted work**
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## สรุป
ในบทเรียนนี้ เราได้ครอบคลุมวิธี **อัปเดตงานของโครงการ**, **กำหนดเวลางานที่ยังไม่เสร็จ**, และ **บันทึกไฟล์ MS Project** เป็น XML โดยใช้ Aspose.Tasks สำหรับ Java ความสามารถเหล่านี้จำเป็นเมื่อไทม์ไลน์ของโครงการต้องปรับตามความคืบหน้าจริงหรือความเปลี่ยนแปลงของลำดับความสำคัญทางธุรกิจ

## คำถามที่พบบ่อย
### Q: Aspose.Tasks สำหรับ Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?
A: ใช่, Aspose.Tasks สำหรับ Java มี API ที่แข็งแกร่งเพื่อจัดการงาน, ความสัมพันธ์, ทรัพยากร และองค์ประกอบอื่น ๆ ของโครงการอย่างมีประสิทธิภาพ  
### Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks สำหรับ Java หรือไม่?
A: ใช่, คุณสามารถรับเวอร์ชันทดลองฟรีได้จาก [here](https://releases.aspose.com/)  
### Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร?
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือหรือสอบถามได้  
### Q: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?
A: ใช่, ใบอนุญาตชั่วคราวมีให้ซื้อได้ที่ [here](https://purchase.aspose.com/temporary-license/)  
### Q: ฉันจะหาเอกสารรายละเอียดสำหรับ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?
A: คุณสามารถอ้างอิงเอกสารได้ที่ [here](https://reference.aspose.com/tasks/java/) สำหรับคู่มือและอ้างอิง API อย่างครบถ้วน  

## คำถามเพิ่มเติมที่พบบ่อย

**Q: ฉันจะทำให้ไฟล์ที่บันทึกเข้ากันได้กับเวอร์ชันเก่าของ Microsoft Project ได้อย่างไร?**  
A: Save the project using `SaveFileFormat.Xml`; XML is widely supported across Project versions.  

**Q: ฉันสามารถกำหนดเวลางานใหม่เฉพาะบางส่วนของงานแทนที่จะเป็นทั้งโครงการได้หรือไม่?**  
A: Yes, you can iterate over specific tasks and call `task.setStart(date)` after calculating the new start date.  

**Q: สิ่งที่เกิดขึ้นกับการจัดสรรทรัพยากรเมื่อฉันกำหนดเวลางานที่ยังไม่เสร็จใหม่คืออะไร?**  
A: Resource assignments are automatically shifted to match the new task start dates, preserving allocation logic.  

**Q: สามารถยกเลิกการกำหนดเวลางานใหม่ได้โดยโปรแกรมหรือไม่?**  
A: You can reload the original project file (or a backup) to revert any changes.  

**Q: Aspose.Tasks รองรับการบันทึกเป็นรูปแบบอื่นเช่น .mpp หรือไม่?**  
A: Absolutely. Use `SaveFileFormat.MPP` to save in the native Microsoft Project format.  

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}