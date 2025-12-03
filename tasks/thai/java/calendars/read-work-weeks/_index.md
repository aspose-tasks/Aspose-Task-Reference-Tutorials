---
date: 2025-12-03
description: เรียนรู้วิธีอ่านสัปดาห์ทำงานใน Java จากปฏิทิน Microsoft Project ด้วย
  Aspose.Tasks. ปฏิบัติตามคู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ดเต็ม.
language: th
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: อ่านสัปดาห์ทำงาน Java จากปฏิทิน MS Project ด้วย Aspose.Tasks
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านสัปดาห์ทำงาน Java จากปฏิทิน MS Project ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะ **อ่านสัปดาห์ทำงาน Java** จากปฏิทิน Microsoft Project โดยใช้ไลบรารี Aspose.Tasks ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงาน, ซิงโครไนซ์ตารางเวลา, หรืออัตโนมัติการสกัดข้อมูลโครงการ การเข้าถึงคำนิยามสัปดาห์ทำงานแบบโปรแกรมจะช่วยประหยัดเวลามนุษย์เป็นจำนวนมาก เราจะอธิบายขั้นตอนการตั้งค่า, แสดงโค้ดที่ใช้ดึงรายละเอียดสัปดาห์ทำงาน, และอธิบายแต่ละขั้นตอนเพื่อให้คุณสามารถปรับใช้กับโครงการของคุณเองได้

## คำตอบสั้น
- **“read work weeks java” หมายถึงอะไร?** หมายถึงการสกัดคำนิยามสัปดาห์ทำงานจากไฟล์ Project ด้วยโค้ด Java  
- **ไลบรารีที่ต้องใช้คืออะไร?** Aspose.Tasks for Java (มีรุ่นทดลองฟรี)  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับรูปแบบไฟล์อะไรบ้าง?** รองรับทั้งไฟล์ *.mpp* และไฟล์ Project XML  
- **ใช้เวลาติดตั้งเท่าไหร่?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีหลังจากตั้งค่าไลบรารีแล้ว  

## อะไรคือ “read work weeks java”?
การอ่านสัปดาห์ทำงานใน Java หมายถึงการใช้ Aspose.Tasks API เพื่อเข้าถึง `WorkWeekCollection` ของอ็อบเจ็กต์ปฏิทินภายในไฟล์ Microsoft Project แต่ละ `WorkWeek` จะมีวันที่เริ่ม/สิ้นสุดและคำนิยามเวลาทำงานประจำวันที่กำหนดว่าทรัพยากรจะถูกจัดตารางอย่างไร

## ทำไมต้องอ่านสัปดาห์ทำงาน java จากปฏิทิน Microsoft Project?
- **อัตโนมัติ:** กำจัดการคัดลอก‑วางข้อมูลตารางด้วยมือ  
- **การรวมระบบ:** ส่งข้อมูลสัปดาห์ทำงานไปยัง ERP, HR, หรือระบบรายงานแบบกำหนดเอง  
- **ความสอดคล้อง:** ทำให้เครื่องมือทั้งหมดที่ต่อมาปฏิบัติตามกฎปฏิทินเดียวกันที่กำหนดในไฟล์ Project  

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มเขียนโค้ด โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [ดาวน์โหลด Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)  
3. ไฟล์ **Project ตัวอย่าง** (`ReadWorkWeeksInformation.mpp`) ที่วางไว้ในโฟลเดอร์ที่ทราบตำแหน่ง  

## นำเข้าแพ็กเกจ
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูลของคุณ
กำหนดโฟลเดอร์ที่เก็บไฟล์ `.mpp` แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ:

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ Project และเข้าถึงปฏิทิน
สร้างอ็อบเจ็กต์ `Project` เลือกปฏิทินที่ต้องการ (โดย UID) และดึง `WorkWeekCollection` ของมันออกมา:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **เคล็ดลับ:** หากคุณไม่แน่ใจว่า UID ของปฏิทินคืออะไร คุณสามารถวนลูปผ่าน `project.getCalendars()` และพิมพ์ชื่อและ UID ของแต่ละปฏิทินได้  

## ขั้นตอนที่ 3: วนลูปผ่านสัปดาห์ทำงาน
ทำลูปผ่านแต่ละ `WorkWeek` เพื่อแสดงชื่อ, วันที่เริ่ม/สิ้นสุด, และเวลาทำงานประจำวัน:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**สิ่งที่คุณจะเห็น:** คอนโซลจะแสดงป้ายกำกับของแต่ละสัปดาห์ทำงาน (เช่น “Standard”), ช่วงวันที่มีผลบังคับใช้, และคุณสามารถเจาะลึกไปยังชั่วโมงทำงานที่กำหนดสำหรับแต่ละวันได้  

## ปัญหาทั่วไปและวิธีแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `NullPointerException` เมื่อเข้าถึง `calendar` | UID ไม่ถูกต้องหรือปฏิทินไม่มีอยู่ | ตรวจสอบ UID ด้วย `project.getCalendars().size()` และแสดงรายการปฏิทินที่มีก่อน |
| ไม่มีผลลัพธ์สำหรับสัปดาห์ทำงาน | ปฏิทินที่เลือกไม่มีสัปดาห์ทำงานแบบกำหนดเอง (ใช้ค่าเริ่มต้น) | ใช้ปฏิทินเริ่มต้น (`project.getDefaultCalendar()`) หรือสร้างสัปดาห์ทำงานด้วยโปรแกรม |
| รูปแบบวันที่ดูแปลก | `System.out.println` ใช้รูปแบบเริ่มต้นของ `java.util.Date` | ใช้ `SimpleDateFormat` เพื่อกำหนดรูปแบบวันที่ตามต้องการ |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถแก้ไขข้อมูลสัปดาห์ทำงานโดยใช้ Aspose.Tasks for Java ได้หรือไม่?**  
ตอบ: ได้. API มีเมธอดเช่น `addWorkWeek()`, `removeWorkWeek()`, และตัวตั้งค่าคุณสมบัติเพื่อเปลี่ยนชื่อ, วันที่, และเวลาทำงาน  

**ถาม: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่าง ๆ หรือไม่?**  
ตอบ: รองรับแน่นอน. รองรับไฟล์ MPP ตั้งแต่ Project 98 จนถึงเวอร์ชันล่าสุด รวมถึงไฟล์ Project XML  

**ถาม: ฉันสามารถรวม Aspose.Tasks กับเฟรมเวิร์ก Java อื่น ๆ ได้หรือไม่?**  
ตอบ: ได้. ไลบรารีเป็น Java แท้ ๆ จึงสามารถใช้ร่วมกับ Spring, Jakarta EE หรือเฟรมเวิร์กอื่นใดได้  

**ถาม: มีรุ่นทดลองของ Aspose.Tasks หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรี 30‑วันจากเว็บไซต์อย่างเป็นทางการ: [รุ่นทดลอง Aspose.Tasks](https://releases.aspose.com/)  

**ถาม: จะหาการสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: ชุมชนฟอรั่มของ Aspose เป็นแหล่งที่ดีที่สุด: [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)  

## สรุป
คุณได้เรียนรู้ **read work weeks java** ด้วย Aspose.Tasks แล้ว ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถดึงคำนิยามสัปดาห์ทำงานจากปฏิทิน MS Project ใด ๆ ได้แบบโปรแกรม, นำข้อมูลนั้นเข้าสู่แอปพลิเคชันของคุณ, และอัตโนมัติการทำงานที่เกี่ยวกับตารางเวลา อย่าลังเลที่จะทดลองสร้างหรืออัปเดตสัปดาห์ทำงาน – Aspose.Tasks ทำให้เรื่องนี้ง่ายดาย  

---

**อัปเดตล่าสุด:** 2025-12-03  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}