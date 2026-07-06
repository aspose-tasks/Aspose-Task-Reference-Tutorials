---
date: 2026-02-07
description: เรียนรู้วิธีตั้งค่าปฏิทินโครงการใน Java และจัดการคุณสมบัติปฏิทินของ MS
  Project ด้วย Aspose.Tasks คู่มือขั้นตอนต่อขั้นตอนเพื่อแสดงชั่วโมงทำงานของปฏิทินและปรับแต่งกำหนดการ
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีตั้งปฏิทินโครงการใน Java ด้วย Aspose.Tasks
url: /th/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งปฏิทินโครงการ Java ด้วย Aspose.Tasks

## Introduction
ในบทแนะนำนี้คุณจะได้ค้นพบ **how to set project calendar java** อย่างโปรแกรมโดยใช้ไลบรารี Aspose.Tasks สำหรับ Java การควบคุมคุณสมบัติปฏิทินทำให้คุณสามารถ **display calendar working hours** กำหนดวันทำงานแบบกำหนดเอง และปรับตารางโครงการของคุณให้สอดคล้องกับข้อจำกัดในโลกจริง เราจะเดินผ่านทุกขั้นตอน ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการวนลูปผ่านปฏิทินและอ่านคุณสมบัติของมัน เพื่อให้คุณมั่นใจในการ **manage ms project calendar** ในแอปพลิเคชันของคุณ

## Quick Answers
- **What does “set project calendar” mean?** หมายถึงการสร้างหรืออัปเดตเวลาทำงานของปฏิทิน, ปฏิทินฐาน, และประเภทวันภายในไฟล์ MS Project.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Can I display calendar working hours?** ได้—โดยการอ่านแต่ละ `WeekDay` คุณสามารถแสดงชั่วโมงสำหรับแต่ละประเภทวัน.  
- **Is this compatible with Maven/Gradle?** แน่นอน—เพิ่ม Aspose.Tasks JAR เป็น dependency.

## How to Set Project Calendar Java
ส่วนนี้ตอบตรงกับคีย์เวิร์ดหลักโดยตรง เราจะอธิบายขั้นตอนที่คุณต้องทำเพื่อ **set project calendar java** ปรับค่าปฏิทินวันทำงาน และคำนวณชั่วโมงทำงานแบบ java‑style

## What Is a Project Calendar?
ปฏิทินโครงการกำหนดวันทำงานและชั่วโมงทำงานสำหรับงาน, ทรัพยากร, และไทม์ไลน์ของโครงการโดยรวม ใน MS Project, ปฏิทินสามารถสืบทอดจากปฏิทินฐาน, และแต่ละประเภทวัน (เช่น **Standard**, **Non‑working**) สามารถมีเวลาทำงานของตนเอง การจัดการการตั้งค่าเหล่านี้ด้วยโปรแกรมทำให้สามารถปรับตารางเวลาแบบไดนามิกโดยไม่ต้องแก้ไขด้วยมือ

## Why Manage MS Project Calendar Programmatically?
- **Automation:** ปรับปฏิทินหลายโครงการด้วยสคริปต์เดียว.  
- **Consistency:** บังคับใช้นโยบายเวลาทำงานทั่วองค์กร.  
- **Integration:** ซิงค์ปฏิทินกับระบบภายนอก (HR, ERP).  
- **Visibility:** อย่างรวดเร็ว **display calendar working hours** สำหรับการรายงานหรือดีบัก.  
- **Flexibility:** คุณสามารถ **modify calendar working days** หรือเพิ่มข้อยกเว้นได้ทันที

## Prerequisites
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK) 8+** ติดตั้งและตั้งค่า `JAVA_HOME`.  
- **Aspose.Tasks for Java** ไลบรารีที่ดาวน์โหลดจาก [download page](https://releases.aspose.com/tasks/java/). เพิ่ม JAR ไปยัง classpath ของโปรเจกต์หรือ dependencies ของ Maven/Gradle

## Import Packages
แรกเริ่ม, นำเข้าคลาสหลักของ Aspose.Tasks ที่เราจะใช้ตลอดบทแนะนำ:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
กำหนดโฟลเดอร์ที่เก็บไฟล์โครงการของคุณ. แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
เวลาทำงานแสดงเป็นมิลลิวินาที. การกำหนดค่าคงที่ที่ใช้ซ้ำทำให้โค้ดอ่านง่ายและช่วยให้คุณ **calculate working hours java** อย่างแม่นยำ.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ MS Project XML ที่มีอยู่ (`.xml` หรือ `.mpp`). นี้ทำให้เราสามารถเข้าถึงปฏิทินทั้งหมดที่เก็บในไฟล์.

```java
Project project = new Project(dataDir + "project.xml");
```

## Iterate Through Calendars Java
ตอนนี้เราวนลูปผ่านทุกปฏิทิน, พิมพ์ตัวระบุที่ไม่ซ้ำกัน, ชื่อ, ปฏิทินฐาน, และชั่วโมงทำงานสำหรับแต่ละประเภทวัน. นี้แสดงตัวอย่าง **how to set project calendar java** และยังแสดงวิธี **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars** (บางปฏิทินภายในอาจมีค่า `null` สำหรับชื่อ).  
- **Prints UID and name** – มีประโยชน์สำหรับระบุตัวปฏิทินในภายหลัง.  
- **Shows the base calendar** – หรือ “Self” (ปฏิทินเป็นฐานของตนเอง) หรือชื่อของปฏิทินที่สืบทอด.  
- **Loops through each `WeekDay`** เพื่อคำนวณและแสดงชั่วโมงทำงานรวม (`workingTime` อยู่ในมิลลิวินาที, ดังนั้นเราจะแบ่งด้วย `OneHour`).  

## Common Issues and Solutions
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | ปฏิทินเป็นปฏิทินฐานเอง (`isBaseCalendar()` คืนค่า `true`). | ใช้การตรวจสอบแบบ ternary ตามที่แสดง (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | ไฟล์โครงการใช้หน่วยเวลาอื่น (ticks). | ตรวจสอบรูปแบบไฟล์; Aspose.Tasks ปรับให้เป็นมิลลิวินาที, แต่ต้องแน่ใจว่ากำลังโหลดไฟล์ประเภทที่ถูกต้อง. |
| Unable to locate `project.xml` | พาธ `dataDir` ไม่ถูกต้อง. | ใช้พาธแบบ absolute หรือ `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: Can I modify calendar properties programmatically using Aspose.Tasks?**  
A: ใช่, API ให้การเข้าถึงแบบอ่าน/เขียนเต็มรูปแบบต่อปฏิทิน, ทำให้คุณสามารถเพิ่ม, แก้ไข, หรือ ลบ เวลาทำงาน, ข้อยกเว้น, และความสัมพันธ์ของปฏิทินฐานได้.

**Q: Are there any limitations to calendar customization with Aspose.Tasks?**  
A: ไลบรารีจำลองความสามารถของ Microsoft Project, ดังนั้นคุณสามารถปรับแต่งเกือบทุกด้านของปฏิทิน. เพียงเวอร์ชันไฟล์ Project ที่เก่ามากอาจมีข้อบกพร่องเล็กน้อยเรื่องความเข้ากันได้.

**Q: Can I integrate calendar management into existing Java projects?**  
A: แน่นอน. เพียงเพิ่ม Aspose.Tasks JAR ไปยังเส้นทางการสร้างของคุณและใช้รูปแบบโค้ดเดียวกันที่แสดงในที่นี่.

**Q: Does Aspose.Tasks support other project management functionalities besides calendar management?**  
A: ใช่, มันครอบคลุมงาน, ทรัพยากร, การมอบหมาย, โครงร่าง, baseline, และอื่น ๆ—ทำให้เป็นโซลูชันครบวงจรสำหรับการอัตโนมัติโครงการด้วย Java.

**Q: Is technical support available for developers using Aspose.Tasks?**  
A: ใช่, Aspose มีฟอรั่มเฉพาะ, การสนับสนุนทางอีเมล, และเอกสารที่ครอบคลุมสำหรับผู้ใช้ที่มีลิขสิทธิ์ทั้งหมด.

---

**อัปเดตล่าสุด:** 2026-02-07  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}