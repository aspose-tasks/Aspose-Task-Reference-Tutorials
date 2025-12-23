---
date: 2025-12-23
description: เรียนรู้วิธีอัปเดตไฟล์ MS Project และกำหนดเวลาใหม่สำหรับงานที่ยังไม่เสร็จโดยใช้
  Aspose.Tasks สำหรับ Java . ดูวิธีบันทึกไฟล์ MS Project XML ด้วยเช่นกัน.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: อัปเดต MS Project และกำหนดเวลาใหม่ของงานด้วย Aspose.Tasks
url: /th/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับปรุง MS Project และกำหนดเวลาใหม่ของงานด้วย Aspose.Tasks

## Introduction
Microsoft Project เป็นเครื่องมือการจัดการโครงการที่ใช้กันอย่างแพร่หลาย ซึ่งช่วยให้ทีมวางแผน, ติดตาม, และส่งมอบงานตรงเวลา เมื่อกำหนดเวลาเปลี่ยนแปลง คุณมักต้อง **update MS Project** ไฟล์โดยอัตโนมัติ—ทำเครื่องหมายว่างานเสร็จ, ย้ายงานที่เหลือ, และรักษา baseline ของโครงการให้แม่นยำ Aspose.Tasks for Java ให้ API ที่สะอาดและปลอดภัยต่อประเภทเพื่อทำสิ่งเหล่านี้โดยไม่ต้องเปิด GUI ในบทเรียนนี้คุณจะได้เห็นวิธีอัปเดตโครงการ, ทำเครื่องหมายว่างานเสร็จถึงวันที่กำหนด, และจากนั้น **how to reschedule MS Project** งานที่ยังค้างอยู่

## Quick Answers
- **What does “update MS Project” mean?** มันทำเครื่องหมายงานเป็นเสร็จถึงวันที่กำหนดและเขียนการเปลี่ยนแปลงกลับไปยังไฟล์  
- **Can I reschedule remaining work automatically?** ได้ — ใช้ `rescheduleUncompletedWorkToStartAfter` เพื่อดันงานที่ยังไม่เสร็จไปข้างหน้า  
- **Which file format is saved?** ตัวอย่างจะบันทึกโครงการเป็น XML (`SaveFileFormat.Xml`)  
- **Do I need a license to run the code?** สามารถใช้เวอร์ชันทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **What Java version is required?** JDK 8 หรือสูงกว่า

## What is “update MS Project” in code?
การอัปเดตโครงการหมายถึงการเปลี่ยนแปลงวันที่, ระยะเวลา, หรือเปอร์เซ็นต์ความสำเร็จของงานโดยโปรแกรมและบันทึกการเปลี่ยนแปลงเหล่านั้น Aspose.Tasks มีเมธอดเช่น `updateProjectWorkAsComplete` ที่ทำการปรับตาม `Date` ที่คุณระบุเป็นอ้างอิง

## Why use Aspose.Tasks for Java to update MS Project?
- **No UI dependency** – สามารถทำการเปลี่ยนแปลงจำนวนมากในหลายไฟล์ได้โดยอัตโนมัติ  
- **High fidelity** – ไลบรารีคงรักษาข้อมูล Project ดั้งเดิมทั้งหมด (ทรัพยากร, ปฏิทิน, ฟิลด์กำหนดเอง)  
- **Cross‑platform** – รันโค้ดเดียวกันบน Windows, Linux หรือ macOS  
- **Save MS Project XML** – สามารถส่งออกโครงการที่อัปเดตเป็นรูปแบบ XML ที่ได้รับการสนับสนุนอย่างกว้างขวางสำหรับเครื่องมือ downstream

## Prerequisites
1. ติดตั้ง Java Development Kit (JDK)  
2. ไลบรารี Aspose.Tasks for Java – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/)  
3. มีความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และแนวคิดเชิงวัตถุ

## Import Packages
ก่อนอื่นให้ import คลาส Aspose.Tasks ที่จำเป็นและยูทิลิตี้ของ Java:

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

## Step 1: Set up the Project
สร้างอินสแตนซ์ `Project` ใหม่, กำหนดงานตัวอย่างบางงาน, ตั้งระยะเวลา, และสร้างความสัมพันธ์ระหว่างงาน จากนั้นบันทึกสถานะเริ่มต้นเพื่อให้คุณเห็นผลก่อน‑และ‑หลัง

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

## Step 2: Update Project Work
ทำเครื่องหมายว่างานเสร็จถึงวันที่กำหนด นี่คือหัวใจของ **update MS Project**—API จะปรับความคืบหน้าและวันที่ของงานโดยอัตโนมัติ

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
หลังจากทำเครื่องหมายงานที่เสร็จแล้ว คุณมักต้องดันงานที่เหลือไปข้างหน้า คำเรียกต่อไปนี้จะย้ายงานที่ยังไม่เสร็จให้เริ่มหลังจากวันที่ตัดสินใจเดียวกัน, ซึ่งเป็น **how to reschedule MS Project** อย่างมีประสิทธิภาพ

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Tasks don’t show updated dates | The project was saved in a different format (e.g., `.mpp`) | Use `SaveFileFormat.Xml` to keep the XML structure intact. |
| `updateProjectWorkAsComplete` appears to do nothing | The reference date is earlier than the project start | Ensure the `Calendar` date is within the project timeline. |
| Rescheduled tasks overlap | No calendar or resource leveling applied | Apply a `Project` calendar or use `Task.setStart` manually after rescheduling. |

## Frequently Asked Questions (Extended)

**Q: Can Aspose.Tasks for Java handle complex project structures?**  
A: Yes, Aspose.Tasks for Java provides robust APIs to manage tasks, dependencies, resources, and other project elements efficiently.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can get a free trial from [here](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Tasks for Java?**  
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries.

**Q: Can I purchase a temporary license for Aspose.Tasks for Java?**  
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find detailed documentation for Aspose.Tasks for Java?**  
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/) for comprehensive guides and API references.

## Conclusion
ในบทเรียนนี้เราได้อธิบายขั้นตอนครบถ้วนของ **updating MS Project** ไฟล์, ทำเครื่องหมายว่างานเสร็จ, และจากนั้น **how to reschedule MS Project** งานที่ยังไม่เสร็จ โดยการบันทึกโครงการเป็น XML คุณจะรักษาความเข้ากันได้กับเครื่องมืออื่นและมีบันทึกการเปลี่ยนแปลงที่ชัดเจน ใช้รูปแบบนี้เพื่ออัตโนมัติการปรับกำหนดเวลาในพอร์ตโฟลิโอขนาดใหญ่, ผสานกับ CI pipelines, หรือสร้างแดชบอร์ดรายงานแบบกำหนดเอง

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}