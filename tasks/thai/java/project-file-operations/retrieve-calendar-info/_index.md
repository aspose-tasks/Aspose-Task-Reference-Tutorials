---
title: ดึงข้อมูลปฏิทินโครงการ MS ใน Aspose.Tasks
linktitle: ดึงข้อมูลปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีดึงข้อมูลปฏิทิน MS Project โดยใช้ Aspose.Tasks สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับการเข้าถึงรายละเอียดปฏิทินโดยทางโปรแกรม
weight: 14
url: /th/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงข้อมูลปฏิทินโครงการ MS ใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีดึงข้อมูลปฏิทินจากไฟล์ Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java Aspose.Tasks มอบฟีเจอร์อันทรงพลังในการจัดการข้อมูลโปรเจ็กต์ รวมถึงการเข้าถึงรายละเอียดปฏิทิน เช่น วันและเวลาทำงาน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Tasks สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
ตอนนี้เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ดีขึ้น
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมพาธไปยังไดเร็กทอรีไฟล์โปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: กำหนดหน่วยเวลา
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
ค่าคงที่เหล่านี้แสดงหน่วยเวลาเป็นไมโครวินาที
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของโครงการ
```java
Project project = new Project(dataDir + "project.mpp");
```
 บรรทัดนี้จะสร้างอินสแตนซ์ของ`Project` คลาสเริ่มต้นด้วยเส้นทางไปยังไฟล์โครงการ (`project.mpp`).
## ขั้นตอนที่ 4: ดึงข้อมูลปฏิทิน
```java
CalendarCollection alCals = project.getCalendars();
```
ที่นี่ เราจะดึงชุดปฏิทินที่มีอยู่ในไฟล์โครงการ
## ขั้นตอนที่ 5: ทำซ้ำผ่านปฏิทิน
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // ข้อมูลปฏิทิน
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // ทำซ้ำผ่านวันธรรมดา
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // เวลาเป็นมิลลิวินาที
            double time = ts / (OneHour); // แปลงเป็นชั่วโมง
            if (wd.getDayWorking()) {
                // แสดงวันและเวลาทำงาน
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
การวนซ้ำนี้จะวนซ้ำแต่ละปฏิทินและพิมพ์ UID ชื่อ และวันทำงานพร้อมชั่วโมงทำงานตามลำดับ
## ขั้นตอนที่ 6: แสดงข้อความเสร็จสิ้น
```java
System.out.println("Process completed Successfully");
```
ในที่สุดข้อความจะปรากฏขึ้นเพื่อระบุถึงความสมบูรณ์ของกระบวนการ
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดึงข้อมูลปฏิทินจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเข้าถึงและจัดการข้อมูลโปรเจ็กต์ในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับหลายแพลตฟอร์มและภาษาการเขียนโปรแกรม รวมถึง .NET, C++, ไพธอน และจาวา
### ถาม: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้หรือไม่
 ตอบ: ได้ มีใบอนุญาตชั่วคราวให้ซื้อได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถดูเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
