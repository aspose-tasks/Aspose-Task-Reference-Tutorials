---
date: 2026-02-28
description: เรียนรู้วิธีการรับระยะเวลาเป็นนาที, วัน, ชั่วโมง, สัปดาห์และเดือนโดยใช้
  Aspose.Tasks สำหรับ Java. คู่มือโดยละเอียดพร้อมตัวอย่างโค้ด.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีรับระยะเวลาในหน่วยต่าง ๆ ด้วย Aspose.Tasks
url: /th/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการดึงระยะเวลาในหน่วยต่าง ๆ ด้วย Aspose.Tasks

## Introduction
การเข้าใจ **วิธีการดึงระยะเวลา** ของงานเป็นส่วนสำคัญของกระบวนการจัดการโครงการใด ๆ ไม่ว่าคุณจะต้องการหน่วยเป็นนาทีสำหรับการติดตามแบบละเอียดหรือเดือนสำหรับการวางแผนระดับสูง Aspose.Tasks for Java ทำให้การแปลงหน่วยเป็นเรื่องง่าย ในบทเรียนนี้เราจะพาคุณผ่านขั้นตอนการดึงระยะเวลาของงานในหน่วยนาที, วัน, ชั่วโมง, สัปดาห์, และเดือน พร้อมอธิบายว่าทำไมแต่ละหน่วยจึงมีประโยชน์ในโครงการจริง

## Quick Answers
- **“how to get duration” หมายถึงอะไร?** เป็นกระบวนการดึงช่วงเวลาของงานและแปลงเป็นหน่วยที่คุณต้องการ  
- **เมธอด API ใดทำการแปลง?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`  
- **ต้องมีไลเซนส์เพื่อรันโค้ดหรือไม่?** สามารถใช้เวอร์ชันทดลองฟรีสำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถแปลงเป็นหน่วยกำหนดเองได้หรือไม่?** คุณสามารถเชนการแปลงหรือใช้ `TimeSpan` สำหรับการคำนวณแบบกำหนดเอง  
- **โค้ดนี้เข้ากันได้กับ Java 17 หรือไม่?** ใช่, Aspose.Tasks รองรับ Java 8 และเวอร์ชันใหม่กว่า

## What is “how to get duration” in Aspose.Tasks?
Aspose.Tasks เก็บความยาวของงานเป็นอ็อบเจ็กต์ `Duration` โดยการเรียกเมธอด `convert` พร้อมระบุ `TimeUnitType` (Minute, Hour, Day, Week, Month) คุณสามารถดึงค่าที่อยู่ภายใต้เดียวกันในหน่วยที่ต้องการ ความยืดหยุ่นนี้ช่วยให้คุณสร้างรายงาน, ทำการคำนวณ, หรือส่งข้อมูลไปยังระบบอื่นโดยไม่ต้องคำนวณด้วยมือ

## Why use Aspose.Tasks for duration conversion?
- **Accuracy:** จัดการข้อยกเว้นของปฏิทิน, เวลาทำงาน, และปฏิทินที่ไม่เป็นมาตรฐานโดยอัตโนมัติ  
- **Performance:** การแปลงบรรทัดเดียวหลีกเลี่ยงการวนลูปหรือการพาร์สแบบกำหนดเอง  
- **Portability:** ทำงานเหมือนกันบน Windows, Linux, และ macOS  
- **Integration:** ผสานรวมได้อย่างราบรื่นกับแอปพลิเคชัน Java ที่ใช้ Aspose.Tasks อยู่แล้ว

## Prerequisites
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) ติดตั้งอยู่
- ไลบรารี Aspose.Tasks for Java คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/tasks/java/)
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## Import Packages
ในโปรเจกต์ Java ของคุณ, ให้เพิ่มไลบรารี Aspose.Tasks และเพิ่มคำสั่ง import ต่อไปนี้ที่ส่วนหัวของโค้ด:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
สร้างโปรเจกต์ Java ใหม่ใน IDE ที่คุณชื่นชอบ (IntelliJ, Eclipse, VS Code ฯลฯ) แล้วเพิ่มไฟล์ JAR ของ Aspose.Tasks ลงใน classpath ของโปรเจกต์ เพื่อให้คลาสที่กล่าวมาพร้อมใช้งานในขั้นตอนคอมไพล์

## Step 2: Read Project Template
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

แทนที่ `"Your Document Directory"` ด้วยโฟลเดอร์ที่มีไฟล์ `.xml` หรือ `.mpp` ของโครงการของคุณ

## Step 3: Retrieve a Task
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

เมธอด `getById(1)` จะดึงงานที่มี ID = 1 ปรับค่า ID ตามต้องการเพื่อเข้าถึงงานอื่นในไฟล์ของคุณ

## Step 4: Duration in Minutes – How to get duration in minutes?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

ตัวแปร `mins` ตอนนี้เก็บความยาวของงานในหน่วยนาทีแล้ว

## Step 5: Duration in Days – How to get duration in days?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

ใช้ค่านี้เมื่อคุณต้องการความละเอียดระดับวันสำหรับการรายงานหรือการจัดสรรทรัพยากร

## Step 6: Duration in Hours – How to get duration in hours?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

ชั่วโมงมีประโยชน์สำหรับใบบันทึกเวลา หรือเมื่อคุณต้องการแบ่งวันเป็นกะทำงาน

## Step 7: Duration in Weeks – How to get duration in weeks?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

สัปดาห์มักใช้ในแผนภูมิ Gantt ระดับสูงหรือการวางแผนมิลสโตน

## Step 8: Duration in Months – How to get duration in months?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

ระยะเวลาในระดับเดือนช่วยเมื่อคุณต้องการสอดคล้องระยะโครงการกับรอบงบประมาณ

## Common Issues and Solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `NullPointerException` on `task` | ID ของงานไม่ถูกต้องหรือไม่มีลูก | ตรวจสอบว่า ID ของงานมีอยู่โดยใช้ `project.getRootTask().getChildren()` |
| ค่าที่ได้ไม่คาดคิด (เช่น 0) | โครงการใช้ปฏิทินกำหนดเองที่มีวันทำงานไม่เป็นมาตรฐาน | ตรวจสอบให้แน่ใจว่าปฏิทินของโครงการกำหนดอย่างถูกต้อง หรือใช้ `project.getCalendar()` เพื่อตรวจสอบ |
| การแปลงให้ค่าเป็นสัปดาห์เศษส่วน | สัปดาห์คำนวณตามความยาวสัปดาห์เริ่มต้นของโครงการ (โดยทั่วไป 5 วัน) | คูณด้วย 5 หากต้องการสัปดาห์ตามปฏิทิน, หรือปรับการตั้งค่าปฏิทิน |

## Frequently Asked Questions
### Q: สามารถใช้ Aspose.Tasks for Java กับ IDE ใดก็ได้หรือไม่?
A: ใช่, Aspose.Tasks for Java เข้ากันได้กับทุก Java Integrated Development Environment (IDE)

### Q: จะหาค่า ID ของงานในไฟล์ Microsoft Project ได้อย่างไร?
A: คุณสามารถตรวจสอบไฟล์โครงการด้วยตนเองหรือเรียก `project.getRootTask().getChildren()` แล้ววนลูปเพื่ออ่านค่า `ID` ของแต่ละงาน

### Q: Aspose.Tasks เหมาะกับการจัดการโครงการขนาดใหญ่หรือไม่?
A: แน่นอน, Aspose.Tasks ถูกออกแบบมาเพื่อประมวลผลโครงการที่มีงานและทรัพยากรหลายพันรายการอย่างมีประสิทธิภาพ

### Q: จะหาเอกสารอ้างอิงเพิ่มเติมได้จากที่ไหน?
A: เยี่ยมชม [documentation](https://reference.aspose.com/tasks/java/) เพื่อดู API reference, ตัวอย่างโค้ด, และแนวทางปฏิบัติที่ดีที่สุด

### Q: สามารถทดลองใช้ Aspose.Tasks for Java ก่อนซื้อได้หรือไม่?
A: ได้, คุณสามารถสำรวจ [free trial](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติต่าง ๆ

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}