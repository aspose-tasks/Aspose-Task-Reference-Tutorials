---
title: อ่านสัปดาห์การทำงานจากปฏิทินโครงการ MS ด้วย Aspose.Tasks
linktitle: อ่านสัปดาห์การทำงานจากปฏิทินด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอ่านสัปดาห์ทำงานจากปฏิทิน MS Project โดยใช้ Aspose.Tasks สำหรับ Java รับคำแนะนำทีละขั้นตอนในบทช่วยสอนที่ครอบคลุมนี้
weight: 15
url: /th/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านสัปดาห์การทำงานจากปฏิทินโครงการ MS ด้วย Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ Aspose.Tasks สำหรับ Java เพื่ออ่านข้อมูลสัปดาห์ทำงานจากปฏิทิน Microsoft Project Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้คุณจัดการและจัดการเอกสาร Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นใช้งานโค้ดของเรา:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูลของคุณ
ตั้งค่าเส้นทางไดเร็กทอรีที่มีไฟล์ MS Project ของคุณ:
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของโครงการและปฏิทินการเข้าถึง
สร้างอินสแตนซ์ใหม่ของคลาส Project และเข้าถึงคอลเลกชันปฏิทินและสัปดาห์ทำงาน:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## ขั้นตอนที่ 3: ทำซ้ำตลอดสัปดาห์การทำงาน
วนซ้ำการรวบรวมสัปดาห์การทำงานและแสดงข้อมูล:
```java
for (WorkWeek workWeek : collection) {
    // แสดงชื่อสัปดาห์การทำงาน วันที่เริ่มต้นและวันที่สิ้นสุด
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // เข้าถึงวันต่อสัปดาห์และเวลาทำงาน
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // ประมวลผลเวลาทำงานเพิ่มเติมหากจำเป็น
    }
}
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอ่านข้อมูลสัปดาห์ทำงานจากปฏิทิน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java ไลบรารีอันทรงพลังนี้ช่วยให้จัดการไฟล์โปรเจ็กต์ได้อย่างราบรื่น ช่วยให้นักพัฒนาทำงานต่างๆ โดยอัตโนมัติได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถแก้ไขข้อมูลสัปดาห์ทำงานโดยใช้ Aspose.Tasks for Java ได้หรือไม่
ใช่ Aspose.Tasks มี API เพื่อแก้ไข เพิ่ม หรือลบสัปดาห์ทำงานและข้อมูลที่เกี่ยวข้อง
### Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP และ XML
### ฉันสามารถรวม Aspose.Tasks เข้ากับเฟรมเวิร์ก Java อื่นได้หรือไม่
แน่นอนว่า Aspose.Tasks สามารถรวมเข้ากับเฟรมเวิร์กและไลบรารี Java อื่นๆ ได้อย่างราบรื่นเพื่อการทำงานที่ได้รับการปรับปรุง
### มี Aspose.Tasks รุ่นทดลองใช้งานหรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Tasks เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือได้ที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
