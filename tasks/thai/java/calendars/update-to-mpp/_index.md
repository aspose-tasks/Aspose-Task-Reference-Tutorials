---
date: 2026-02-05
description: เรียนรู้วิธีเพิ่มวันหยุดลงในปฏิทิน, กำหนดปฏิทินให้กับโครงการ, และบันทึกไฟล์
  MS Project เป็นรูปแบบ MPP ด้วย Aspose.Tasks for Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: เพิ่มวันหยุดในปฏิทินและบันทึกเป็นไฟล์ MPP ด้วย Aspose.Tasks
url: /th/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มวันหยุดในปฏิทินและบันทึกเป็น MPP ด้วย Aspose.Tasks

## บทนำ

ในการจัดการโครงการสมัยใหม่ คุณมักต้อง **add holidays to calendar** ไฟล์, สร้าง **MS Project calendar**, แล้วแชร์กำหนดการในรูปแบบ MPP ดั้งเดิม ไม่ว่าคุณจะรวมไทม์ไลน์จากหลายแหล่งหรือย้ายข้อมูลเก่า การสร้างปฏิทินโดยโปรแกรมช่วยลดข้อผิดพลาดจากการทำมือและเร่งการส่งมอบได้อย่างมาก คู่มือฉบับนี้จะพาคุณผ่านกระบวนการทั้งหมดของการสร้างปฏิทินใน MS Project, ปรับแต่งด้วยวันหยุด, **assign calendar to project**, และสุดท้าย **convert project to MPP** ด้วย Aspose.Tasks Java API.

## คำตอบสั้น
- **What does this tutorial cover?** เพิ่มวันหยุดในปฏิทิน, กำหนดให้กับโครงการ, และบันทึกผลลัพธ์เป็นไฟล์ MPP ด้วย Aspose.Tasks for Java.  
- **Do I need a license?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Which Java version is required?** Java 8 หรือสูงกว่า (JDK 8+).  
- **Can I customize the calendar?** ใช่ – คุณสามารถเพิ่มเวลาทำงาน, ข้อยกเว้น, และวันหยุด.  
- **How long does implementation take?** ประมาณ 10‑15 นาทีสำหรับปฏิทินพื้นฐาน.  

## “create calendar MS Project” คืออะไร?

การสร้าง calendar MS Project หมายถึงการกำหนดวันทำงาน, ชั่วโมงทำงาน, และข้อยกเว้นโดยโปรแกรมที่ใช้ในการกำหนดการทำงานของงานภายในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks คุณสามารถ **java create project calendar**, แก้ไขและบันทึกการเปลี่ยนแปลงโดยไม่ต้องเปิด UI ของ Microsoft Project.

## ทำไมต้องใช้ Aspose.Tasks สำหรับงานนี้?

- **Full .NET/Java compatibility** – ทำงานบนแพลตฟอร์มใดก็ได้ที่รองรับ Java.  
- **No COM or Office installation needed** – เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์และ **automate schedule generation**.  
- **Rich API** – รองรับคุณสมบัติของปฏิทินทั้งหมด รวมถึงสัปดาห์ทำงานแบบกำหนดเองและวันหยุด.  
- **Direct MPP output** – คุณสามารถ **save project as MPP** โดยไม่ต้องแปลงผ่านขั้นตอนอื่น.  

## ข้อกำหนดเบื้องต้น

1. **Java Development Kit (JDK) 8+** – ตรวจสอบให้แน่ใจว่า `java -version` แสดงผลเป็น 1.8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse หรือโปรแกรมแก้ไขใดก็ได้ที่คุณชอบ.  
4. **Basic Java knowledge** – ความคุ้นเคยกับคลาส, เมธอด, และการทำ I/O ของไฟล์.  

## วิธีเพิ่มวันหยุดในปฏิทิน

ด้านล่างเราจะอธิบายขั้นตอนต่าง ๆ ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการบันทึกไฟล์ MPP สุดท้าย โค้ดบล็อกจะไม่เปลี่ยนแปลงจากบทแนะนำต้นฉบับ; คำอธิบายโดยรอบได้ขยายเพื่อความชัดเจน.

### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น

แรกสุด นำคลาสของ Aspose.Tasks และยูทิลิตี้ของ Java เข้ามาในสโคป.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### ขั้นตอนที่ 2: ตั้งค่าไดเรกทอรีข้อมูล

กำหนดตำแหน่งที่ไฟล์เทมเพลตอินพุตและไฟล์เอาต์พุตจะอยู่ แทนที่ตัวแปรตำแหน่งที่เก็บด้วยพาธจริงบนเครื่องของคุณ

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 3: กำหนดชื่อไฟล์อินพุตและเอาต์พุต

เราจะโหลดไฟล์ MPP ที่มีอยู่ (หรือโครงการเปล่า) แล้วเขียนผลลัพธ์ลงในไฟล์ใหม่

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### ขั้นตอนที่ 4: โหลดโครงการและเพิ่มปฏิทินใหม่

สร้างอินสแตนซ์ `Project` จากไฟล์ต้นฉบับและเพิ่มปฏิทินชื่อ **“Calendar 1”**

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### ขั้นตอนที่ 5: ปรับแต่งปฏิทิน (ทางเลือก)

หากคุณต้องการเวลาทำงานเฉพาะ, วันหยุด, หรือข้อยกเว้น ให้เรียกเมธอดช่วยเหลือของคุณเอง ตัวอย่างใช้ `GetTestCalendar` เป็นตัวแทน

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** คุณสามารถจัดการ `cal1.getWeekDays()` โดยตรงเพื่อกำหนดชั่วโมงทำงานสำหรับแต่ละวันของสัปดาห์, หรือใช้ `cal1.getExceptions()` เพื่อ **add holidays to calendar**.

### ขั้นตอนที่ 6: กำหนดปฏิทินให้กับโครงการ

บอกโครงการให้ใช้ปฏิทินที่สร้างใหม่สำหรับการคำนวณการกำหนดเวลาทั้งหมด

```java
project.set(Prj.CALENDAR, cal1);
```

### ขั้นตอนที่ 7: บันทึกโครงการเป็น MPP

ตอนนี้ **convert project to MPP** โดยบันทึกด้วยตัวเลือก `SaveFileFormat.Mpp`

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### ขั้นตอนที่ 8: ยืนยันการทำงานสำเร็จ

ข้อความคอนโซลง่าย ๆ จะบอกคุณว่ากระบวนการเสร็จสิ้นโดยไม่มีข้อผิดพลาด

```java
System.out.println("Process completed Successfully");
```

## กรณีการใช้งานทั่วไป

- **Automated schedule generation** สำหรับโครงการที่ทำซ้ำ (เช่น สปรินท์รายสัปดาห์).  
- **Migrating legacy CSV or Excel calendars** ไปยังไฟล์ MS Project ที่เต็มรูปแบบ.  
- **Server‑side reporting** ที่บริการเว็บส่งคืนไฟล์ MPP ตามความต้องการ.  

## การแก้ไขปัญหาและข้อผิดพลาดทั่วไป

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่หรือสร้างขึ้นโดยโปรแกรม. |
| ปฏิทินไม่ถูกนำไปใช้กับงาน | งานยังอ้างอิงปฏิทินเริ่มต้น | หลังจากตั้งค่า `Prj.CALENDAR` ให้อัปเดต `Task.CALENDAR` ของแต่ละงานด้วยหากเคยถูกแทนที่ก่อนหน้า. |
| ไฟล์เอาต์พุตมีขนาด 0 KB | ไม่มีสิทธิ์เขียน | รัน JVM ด้วยสิทธิ์ไฟล์ระบบที่เหมาะสมหรือเลือกพาธที่เขียนได้. |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?**  
A: ใช่, Aspose.Tasks for Java รองรับช่วงเวอร์ชันของ MS Project อย่างกว้างขวาง ตั้งแต่ Project 2007 จนถึงรุ่นล่าสุด, ทำให้เข้ากันได้อย่างไม่มีปัญหา.

**Q: ฉันสามารถปรับแต่งปฏิทินตามความต้องการเฉพาะของโครงการได้หรือไม่?**  
A: แน่นอน คุณสามารถกำหนดวันทำงาน, ตั้งสัปดาห์ทำงานแบบกำหนดเอง, เพิ่มวันหยุด, และแม้แต่สร้างหลายปฏิทินในไฟล์โครงการเดียวได้.

**Q: Aspose.Tasks for Java มีการสนับสนุนการแก้ไขปัญหาและความช่วยเหลือหรือไม่?**  
A: มี คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks [ที่นี่](https://forum.aspose.com/c/tasks/15).

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี การทดลองใช้เต็มรูปแบบที่ใช้งานได้ฟรีพร้อมให้ดาวน์โหลด [ที่นี่](https://releases.aspose.com/).

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?**  
A: สามารถขอรับลิขสิทธิ์ชั่วคราวผ่านเว็บไซต์ Aspose [ที่นี่](https://purchase.aspose.com/temporary-license/).

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}