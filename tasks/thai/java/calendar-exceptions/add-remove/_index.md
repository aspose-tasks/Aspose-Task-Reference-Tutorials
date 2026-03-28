---
date: 2026-01-28
description: เรียนรู้วิธีสร้างข้อยกเว้นปฏิทินด้วย Aspose โดยใช้ Aspose.Tasks สำหรับ
  Java, เพิ่มและลบข้อยกเว้นปฏิทินอย่างมีประสิทธิภาพ, และปรับปรุงการวางแผนโครงการ.
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: สร้างข้อยกเว้นปฏิทิน Aspose สำหรับ Java
url: /th/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Calendar Exception Aspose สำหรับ Java

## Introduction
การกำหนดกำหนดการโครงการอย่างแม่นยำมักพึ่งพาการจัดการ **calendar exceptions**—วันที่ทรัพยากรไม่พร้อมใช้งานหรือกำหนดการทำงานเปลี่ยนแปลง ด้วย **Aspose.Tasks for Java** คุณสามารถ **create calendar exception** objects, เพิ่มเข้าไปในปฏิทินของโครงการ, หรือเอาออกเมื่อไม่ต้องการอีกต่อไป ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด ตั้งแต่การโหลดไฟล์โครงการจนถึงการตรวจสอบข้อยกเว้นที่คุณจัดการ คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่า **create calendar exception aspose** ทำอย่างไรในสภาพแวดล้อม Java

### Quick Answers
- **What does “create calendar exception” mean?** It means defining a date range that deviates from the standard working calendar.  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** A free trial is available; a license is required for production use.  
- **Can I remove an existing exception?** Yes—simply locate it in the calendar’s exception list and delete it.  
- **Is this compatible with Microsoft Project files?** Absolutely; Aspose.Tasks reads and writes all major .mpp versions.

#### Prerequisites
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) ที่ติดตั้งแล้ว
- ไลบรารี Aspose.Tasks for Java ที่เพิ่มเข้าไปใน classpath ของโปรเจกต์
- ความเข้าใจพื้นฐานเกี่ยวกับ Java และคำศัพท์ด้านการจัดการโครงการ

## How to create calendar exception Aspose with Java
ด้านล่างเป็นขั้นตอนแบบละเอียดที่อธิบายวัตถุประสงค์ของแต่ละโค้ดสแนปก่อนที่จะรัน ให้ทำตามลำดับนี้เพื่อให้แน่ใจว่าข้อยกเว้นของปฏิทินถูกจัดการอย่างถูกต้อง

## Import Packages
เริ่มต้นด้วยการนำเข้าคลาสหลักของ Aspose.Tasks ที่ใช้ในการจัดการปฏิทิน

```java
import com.aspose.tasks.*;
```

## Step 1: Load the Project and Access Its Calendar
เราจะโหลดไฟล์ Microsoft Project ที่มีอยู่ (`input.mpp`) และดึงปฏิทินแรกจากคอลเลกชัน คุณสามารถปรับดัชนีได้หากต้องการปฏิทินอื่น

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Step 2: Remove an Existing Exception (If Needed)
บางครั้งปฏิทินอาจมีข้อยกเว้นอยู่แล้วที่คุณต้องการลบ โค้ดสแนปด้านล่างจะตรวจสอบรายการข้อยกเว้นและลบรายการแรกเมื่อมีมากกว่าหนึ่งรายการ

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** Always verify the size of the exception list before removing items to avoid `IndexOutOfBoundsException`.

## Step 3: Create (Add) a New Calendar Exception
ตอนนี้เราจะ **create calendar exception** objects ตัวอย่างนี้กำหนดข้อยกเว้นที่ครอบคลุมวันที่ 1‑3 มกราคม 2009 ปรับวันที่ตามไทม์ไลน์ของโครงการของคุณ

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** Adding exceptions lets you model holidays, maintenance windows, or any non‑working periods directly in the project schedule. This is the core of **create calendar exception aspose** functionality.

## Step 4: Display All Exceptions for Verification
หลังจากเพิ่ม (หรือเอาออก) ข้อยกเว้นแล้ว การพิมพ์รายการทั้งหมดออกมาจะช่วยให้คุณยืนยันว่าปฏิทินสะท้อนการเปลี่ยนแปลงที่ต้องการ

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Common Issues & Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| No output appears | Exceptions list is empty | Ensure you added an exception before iterating. |
| `NullPointerException` on `project` | Incorrect file path | Verify `dataDir` points to a valid `.mpp` file. |
| Dates are off by one day | Time‑zone differences | Use `java.util.Calendar` with explicit time zone or `java.time` API. |

## Frequently Asked Questions

**Q: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?**  
A: Yes. Simply create a new `CalendarException` for each date range and add it to `cal.getExceptions()` inside a loop.

**Q: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project files?**  
A: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up to the latest releases, ensuring seamless integration.

**Q: How can I handle recurring exceptions (e.g., weekly meetings) in project calendars?**  
A: Use the `CalendarException` recurrence properties (`setRecurrencePattern`) to define complex patterns such as daily, weekly, or monthly repeats.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can download a free trial from the [website](https://releases.aspose.com/) to explore all features before purchasing.

**Q: Where can I seek support for any issues or queries related to Aspose.Tasks for Java?**  
A: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/) to ask questions, or contact Aspose support directly.

## Conclusion
การจัดการ calendar exceptions เป็นสิ่งสำคัญสำหรับการกำหนดไทม์ไลน์โครงการและการวางแผนทรัพยากรอย่างเป็นจริง ด้วย **Aspose.Tasks for Java** คุณสามารถ **create calendar exception** objects, เพิ่มเข้าไปในปฏิทินของโครงการใดก็ได้, และลบออกเมื่อไม่จำเป็นอีกต่อไป—ทั้งหมดด้วยเพียงไม่กี่บรรทัดของโค้ด ความสามารถในการ **create calendar exception aspose** นี้ทำให้คุณสร้างตารางงานที่สะท้อนข้อจำกัดในโลกจริงได้อย่างแม่นยำ

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}