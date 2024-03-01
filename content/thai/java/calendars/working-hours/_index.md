---
title: รับเวลาทำงานจากปฏิทินโดยใช้ Aspose.Tasks
linktitle: รับเวลาทำงานจากปฏิทินโดยใช้ Aspose.Tasks
second_title: Aspose.Tasks Java API
description: แยกชั่วโมงทำงานออกจากปฏิทิน MS Project ได้อย่างง่ายดายด้วย Aspose.Tasks สำหรับ Java ลดความซับซ้อนของงานการจัดการโครงการ
type: docs
weight: 13
url: /th/java/calendars/working-hours/
---
## การแนะนำ
การจัดการปฏิทินโครงการและการแยกชั่วโมงทำงานเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ Aspose.Tasks for Java มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการดึงข้อมูลชั่วโมงทำงานจากปฏิทิน MS Project ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks สำหรับ Java:
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
เริ่มต้นด้วยการโหลดไฟล์ MS Project ของคุณ:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## ขั้นตอนที่ 2: ดึงข้อมูลงานและปฏิทิน
แยกรายละเอียดงานและปฏิทินออกจากโครงการ:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## ขั้นตอนที่ 3: กำหนดวันที่เริ่มต้นและสิ้นสุด
ตั้งค่าวันที่เริ่มต้นและสิ้นสุดสำหรับงาน:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## ขั้นตอนที่ 4: วนซ้ำตามวันที่
วนซ้ำวันที่ภายในระยะเวลางาน:
```java
java.util.Calendar tempDate = calStartDate;
```
## ขั้นตอนที่ 5: คำนวณระยะเวลา
คำนวณระยะเวลาเป็นนาที ชั่วโมง และวัน:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีดึงข้อมูลชั่วโมงทำงานจากปฏิทิน MS Project โดยใช้ Aspose.Tasks สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการกำหนดการของโครงการได้อย่างมีประสิทธิภาพและคำนวณระยะเวลาของงานได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: ใช่ Aspose.Tasks for Java ให้การสนับสนุนที่ครอบคลุมสำหรับการจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อน รวมถึงงาน ทรัพยากร และปฏิทิน
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับ MS Project เวอร์ชันต่างๆ หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ Java รองรับ MS Project เวอร์ชันต่างๆ มากมาย จึงรับประกันความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ถาม: ฉันสามารถปรับแต่งเวลาทำงานและวันหยุดในปฏิทินโครงการได้หรือไม่
ตอบ: ได้ คุณสามารถปรับแต่งชั่วโมงทำงานและวันหยุดตามความต้องการของโปรเจ็กต์ของคุณได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ Java API
### ถาม: Aspose.Tasks for Java ให้การสนับสนุนและเอกสารประกอบหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java มีเอกสารประกอบที่ครอบคลุมและฟอรัมสนับสนุนเฉพาะเพื่อช่วยให้นักพัฒนาใช้งานคุณสมบัติต่างๆ ได้อย่างมีประสิทธิภาพ
### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึง Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).