---
date: 2026-02-05
description: เรียนรู้วิธีอ่าน workweeks ของ Java จากปฏิทิน Microsoft Project ด้วย
  Aspose.Tasks. ทำตามคู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ดเต็มรูปแบบ.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่าน Workweeks ใน Java จากปฏิทิน MS Project ด้วย Aspose.Tasks
url: /th/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการอ่าน Workweeks Java จากปฏิทิน MS Project ด้วย Aspose.Tasks

## บทนำ
ในบทเรียนนี้คุณจะ **เรียนรู้วิธีการอ่าน workweeks Java** จากปฏิทิน Microsoft Project ด้วยไลบรารี Aspose.Tasks ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงาน, ซิงโครไนซ์ตารางเวลา, หรืออัตโนมัติการสกัดข้อมูลโครงการ การเข้าถึงคำนิยาม work‑week อย่างโปรแกรมเมติกจะช่วยประหยัดเวลามนุษย์เป็นจำนวนมาก เราจะอธิบายขั้นตอนการตั้งค่า, แสดงโค้ดที่ใช้ดึงรายละเอียด work‑week, และอธิบายแต่ละขั้นตอนเพื่อให้คุณสามารถปรับใช้กับโครงการของคุณเองได้

## คำตอบสั้น
- **“read workweeks java” หมายถึงอะไร?** หมายถึงการสกัดคำนิยาม work‑week จากไฟล์ Project ด้วยโค้ด Java  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks for Java (มีเวอร์ชันทดลองฟรี)  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** เวอร์ชันทดลองใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับรูปแบบไฟล์อะไรบ้าง?** รองรับไฟล์ *.mpp* และไฟล์ Project XML ทั้งสองประเภท  
- **ใช้เวลาติดตั้งและใช้งานเท่าไหร่?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีหลังจากตั้งค่าไลบรารีเรียบร้อย

## วิธีการอ่าน Workweeks Java จากปฏิทิน Microsoft Project
การอ่าน work weeks ด้วย Java หมายถึงการใช้ Aspose.Tasks API เพื่อเข้าถึง `WorkWeekCollection` ของอ็อบเจ็กต์ปฏิทินภายในไฟล์ Microsoft Project แต่ละ `WorkWeek` จะมีข้อมูลวันที่เริ่มต้น/สิ้นสุดและคำนิยามเวลาทำงานประจำวันที่กำหนดวิธีการจัดสรรทรัพยากร

## ทำไมต้องอ่าน workweeks Java จากปฏิทิน Microsoft Project?
- **Automation:** ลดการคัดลอก‑วางข้อมูลตารางด้วยมือ  
- **Integration:** ส่งข้อมูล work‑week ไปยัง ERP, HR, หรือระบบรายงานแบบกำหนดเอง  
- **Consistency:** ทำให้เครื่องมือทั้งหมดที่ต่อมาปฏิบัติตามกฎปฏิทินเดียวกันที่กำหนดในไฟล์ Project

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)  
3. ไฟล์ **Project ตัวอย่าง** (`ReadWorkWeeksInformation.mpp`) ที่วางไว้ในโฟลเดอร์ที่ทราบตำแหน่ง

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นสำหรับการทำงานกับปฏิทินและ work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์ข้อมูลของคุณ
กำหนดโฟลเดอร์ที่เก็บไฟล์ `.mpp` แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ:

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์ Project และเข้าถึงปฏิทิน
สร้างอ็อบเจ็กต์ `Project` เลือกปฏิทินที่ต้องการ (โดย UID) และรับ `WorkWeekCollection` ของมัน:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **เคล็ดลับ:** หากคุณไม่แน่ใจว่า UID ของปฏิทินคืออะไร สามารถวนลูป `project.getCalendars()` แล้วพิมพ์ชื่อและ UID ของแต่ละปฏิทินออกมา

## ขั้นตอนที่ 3: วนลูปผ่าน Work Weeks
ทำการวนลูปแต่ละ `WorkWeek` เพื่อแสดงชื่อ, วันที่เริ่มต้น/สิ้นสุด, และเวลาทำงานประจำวัน:

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

**สิ่งที่คุณจะเห็น:** คอนโซลจะแสดงป้ายกำกับของแต่ละ work‑week (เช่น “Standard”), ช่วงวันที่มีผลบังคับใช้, และคุณสามารถเจาะลึกเวลาทำงานของแต่ละวันได้

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `NullPointerException` เมื่อเข้าถึง `calendar` | UID ไม่ถูกต้องหรือปฏิทินไม่มีอยู่ | ตรวจสอบ UID ด้วย `project.getCalendars().size()` และแสดงรายการปฏิทินที่มีก่อน |
| ไม่มีผลลัพธ์สำหรับ work weeks | ปฏิทินที่เลือกไม่มี work weeks กำหนดเอง (ใช้ค่าเริ่มต้น) | ใช้ปฏิทินเริ่มต้น (`project.getDefaultCalendar()`) หรือสร้าง work week ด้วยโปรแกรม |
| รูปแบบวันที่แสดงแปลก | `System.out.println` ใช้รูปแบบ `java.util.Date` เริ่มต้น | ใช้ `SimpleDateFormat` เพื่อจัดรูปแบบวันที่ตามต้องการ |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถแก้ไขข้อมูล work weeks ด้วย Aspose.Tasks for Java ได้หรือไม่?**  
ตอบ: ได้. API มีเมธอดเช่น `addWorkWeek()`, `removeWorkWeek()`, และตัวตั้งค่าคุณสมบัติเพื่อเปลี่ยนชื่อ, วันที่, และเวลาทำงาน

**ถาม: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันใดบ้าง?**  
ตอบ: รองรับไฟล์ MPP ตั้งแต่ Project 98 จนถึงเวอร์ชันล่าสุด รวมถึงไฟล์ Project XML

**ถาม: ฉันสามารถผสาน Aspose.Tasks กับเฟรมเวิร์ก Java อื่นได้หรือไม่?**  
ตอบ: ได้. ไลบรารีเป็น Java แท้ จึงสามารถใช้ร่วมกับ Spring, Jakarta EE หรือเฟรมเวิร์กอื่นใดได้

**ถาม: มีเวอร์ชันทดลองของ Aspose.Tasks หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรี 30 วันจากเว็บไซต์อย่างเป็นทางการ: [Aspose.Tasks trial](https://releases.aspose.com/)

**ถาม: จะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: ฟอรั่มชุมชนของ Aspose เป็นที่ดีที่สุด: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

## สรุป
คุณได้เรียนรู้ **วิธีการอ่าน workweeks Java** ด้วย Aspose.Tasks แล้ว ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถดึงคำนิยาม work‑week จากปฏิทิน MS Project ใด ๆ ได้โดยอัตโนมัติ, นำข้อมูลไปใช้ในแอปพลิเคชันของคุณ, และทำให้กระบวนการทำงานที่เกี่ยวกับตารางเวลามีความอัตโนมัติมากขึ้น อย่าลังเลที่จะทดลองสร้างหรืออัปเดต work weeks – Aspose.Tasks ทำให้เรื่องนี้ง่ายดาย

---

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}