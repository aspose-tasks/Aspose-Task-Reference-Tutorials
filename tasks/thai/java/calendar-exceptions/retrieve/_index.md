---
date: 2025-11-29
description: เรียนรู้วิธีดึงข้อยกเว้นของปฏิทินจาก MS Project ด้วย Aspose.Tasks สำหรับ
  Java บทเรียน Aspose.Tasks Java นี้ให้ตัวอย่างโค้ดแบบขั้นตอนต่อขั้นตอน
language: th
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial
second_title: Aspose.Tasks Java API
title: ดึงข้อยกเว้นของปฏิทินด้วย Aspose.Tasks – บทเรียน Java ของ asp tasks
url: /java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงข้อมูล Calendar Exceptions ด้วย Aspose.Tasks – asp tasks java tutorial

## Introduction
ใน **asp tasks java tutorial** นี้ คุณจะได้เรียนรู้วิธีดึง Calendar Exceptions จากไฟล์ Microsoft Project ด้วยไลบรารี Aspose.Tasks สำหรับ Java Calendar exceptions แสดงช่วงเวลาที่ไม่ทำงาน เช่น วันหยุดหรือกฎเวลาทำงานที่กำหนดเอง และการอ่านข้อมูลเหล่านี้ด้วยโปรแกรมเป็นสิ่งสำคัญสำหรับการปรับระดับทรัพยากร การรายงาน และตรรกะการกำหนดเวลาที่กำหนดเอง เราจะอธิบายขั้นตอนทั้งหมดอย่างละเอียด เพื่อให้คุณสามารถนำความสามารถนี้ไปผสานในแอปพลิเคชัน Java ของคุณได้อย่างมั่นใจ

## Quick Answers
- **What does this tutorial cover?** การดึง Calendar Exceptions จากไฟล์ MPP ด้วย Aspose.Tasks สำหรับ Java.  
- **How long does implementation take?** ประมาณ 10‑15 นาทีสำหรับการตั้งค่าเบื้องต้น.  
- **Prerequisites?** JDK, Aspose.Tasks สำหรับ Java, และ IDE (IntelliJ IDEA หรือ Eclipse).  
- **Do I need a license?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **Supported Project versions?** ทุกรูปแบบหลักของ MS Project (MPP, MPT, XML).

## What is asp tasks java tutorial?
**asp tasks java tutorial** คือคำอธิบายวิธีใช้ Aspose.Tasks API ภายในโครงการ Java โดยให้โค้ดตัวอย่างที่ชัดเจน คำอธิบายแนวปฏิบัติที่ดีที่สุด และสถานการณ์จริง เพื่อให้ผู้พัฒนาสามารถจัดการไฟล์ Project ได้โดยไม่ต้องติดตั้ง Microsoft Project

## Why retrieve calendar exceptions?
การเข้าใจ Calendar Exceptions ช่วยให้คุณ:
- สร้างไทม์ไลน์โครงการที่แม่นยำโดยคำนึงถึงวันหยุดและตารางทำงานที่กำหนดเอง
- สร้างเครื่องมือรายงานที่เน้นวันไม่ทำงาน
- ซิงโครไนซ์ปฏิทิน Project กับระบบภายนอก (เช่น ERP, HR)

## Prerequisites
ก่อนเริ่มทำตามขั้นตอน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

1. **Java Development Kit (JDK)** – ตรวจสอบว่าติดตั้ง JDK 8 หรือใหม่กว่า
2. **Aspose.Tasks for Java** – ดาวน์โหลดและติดตั้ง Aspose.Tasks for Java จาก [here](https://releases.aspose.com/tasks/java/)
3. **Integrated Development Environment (IDE)** – คุณสามารถใช้ IDE ใดก็ได้ที่คุณชอบ เช่น IntelliJ IDEA หรือ Eclipse

## Import Packages
ก่อนอื่นคุณต้องนำเข้าแพ็กเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **Pro tip:** ใช้เส้นทางแบบ absolute หรือเส้นทางที่สัมพันธ์กับโฟลเดอร์ resources ของโปรเจกต์เพื่อหลีกเลี่ยง `FileNotFoundException`

## Step 2: Load MS Project File
```java
Project project = new Project(dataDir + "project.mpp");
```

บรรทัดนี้จะสร้างอ็อบเจ็กต์ `Project` ใหม่โดยโหลดไฟล์ MS Project ที่ระบุด้วยเส้นทาง

## Step 3: Retrieve Calendar Exceptions
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

ที่นี่เราจะวนลูปผ่านแต่ละปฏิทินในโครงการ แล้ววนลูปผ่านแต่ละ Calendar Exception ภายในปฏิทินนั้น เราจะพิมพ์วันที่เริ่มต้นและสิ้นสุดของแต่ละ Exception

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **No output printed** | Project file does not contain any calendar exceptions. | Verify the calendar in MS Project has defined exceptions (e.g., holidays). |
| **`NullPointerException`** | `dataDir` path is incorrect or file not found. | Double‑check the directory path and ensure `project.mpp` exists. |
| **Time zone mismatch** | Dates are displayed in UTC. | Use `calExc.getFromDate().toLocalDateTime()` to convert to local time if needed. |

## Frequently Asked Questions
### Can Aspose.Tasks handle different versions of MS Project files?
Yes, Aspose.Tasks supports various versions of MS Project files, including MPP, MPT, and XML formats.

### Is there a free trial available for Aspose.Tasks?
Yes, you can download a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).

### Where can I find documentation for Aspose.Tasks for Java?
You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).

### How can I get support for Aspose.Tasks?
You can get support from the community forum [here](https://forum.aspose.com/c/tasks/15).

### Is there an option for temporary licenses for Aspose.Tasks?
Yes, you can obtain temporary licenses from [here](https://purchase.aspose.com/temporary-license/).

**Additional Q&A**

**Q:** *Can I modify calendar exceptions after retrieving them?*  
**A:** Absolutely. Use `CalendarException.setFromDate()` and `setToDate()` to adjust dates, then save the project with `project.save(...)`.

**Q:** *Does Aspose.Tasks preserve custom fields on calendars?*  
**A:** Yes, all custom fields and extended attributes are retained when loading and saving the project.

## Conclusion
ใน **asp tasks java tutorial** นี้ เราได้เรียนรู้วิธีดึง Calendar Exceptions จาก MS Project ด้วย Aspose.Tasks สำหรับ Java โดยทำตามขั้นตอนง่าย ๆ นี้ คุณสามารถผสานฟังก์ชันนี้เข้าไปในแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น เพิ่มคุณสมบัติการกำหนดเวลาที่ลึกซึ้งและการวิเคราะห์โครงการที่แม่นยำยิ่งขึ้น

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}