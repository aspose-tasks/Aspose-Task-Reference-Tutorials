---
date: 2025-12-05
description: เรียนรู้วิธีกำหนดวันทำงานและคำนวณระยะเวลางานโดยการดึงชั่วโมงทำงานจากปฏิทิน
  MS Project ด้วย Aspose.Tasks สำหรับ Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: กำหนดวันทำงานและชั่วโมงทำงานด้วย Aspose.Tasks
url: /th/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดวันทำงานและชั่วโมงทำงานด้วย Aspose.Tasks

## บทนำ
การจัดการปฏิทินโครงการเป็นส่วนสำคัญของการวางแผนโครงการที่ประสบความสำเร็จ ในบทแนะนำนี้คุณจะ **กำหนดวันทำงาน** สำหรับงานใด ๆ และ **ดึงชั่วโมงทำงาน** จากปฏิทิน MS Project ด้วย Aspose.Tasks for Java เมื่อจบคู่มือคุณจะสามารถ **คำนวณระยะเวลาของงาน**, ปรับแต่งชั่วโมงทำงาน, และ **โหลดไฟล์ MPP** เพื่อดึงข้อมูลที่ต้องการได้อย่างน่าเชื่อถือ

## คำตอบสั้น
- **“กำหนดวันทำงาน” หมายถึงอะไร?** หมายถึงการระบุว่าตำแหน่งวันที่ในปฏิทินใดบ้างที่ถือว่าเป็นวันทำงานสำหรับงานที่กำหนด  
- **ควรใช้ไลบรารีใด?** Aspose.Tasks for Java มี API ครบวงจรสำหรับทำงานกับไฟล์ MS Project  
- **การดำเนินการใช้เวลานานเท่าไหร่?** โดยทั่วไป 10–15 นาทีสำหรับการดึงข้อมูลพื้นฐาน  
- **ต้องมีไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถปรับแต่งชั่วโมงทำงานได้หรือไม่?** ได้ – คุณสามารถแก้ไขปฏิทิน, เพิ่มวันหยุด, และกำหนดช่วงเวลาทำงานแบบกำหนดเอง

## “กำหนดวันทำงาน” คืออะไร?
เมื่อกำหนดงาน, ปฏิทินโครงการจะระบุว่าวันใดเป็นวันทำงานและวันใดเป็นวันไม่ทำงาน (วันหยุดสุดสัปดาห์, วันหยุดราชการ) การกำหนดวันทำงานหมายถึงการสอบถามปฏิทินนั้นเพื่อทราบว่าเมื่อใดที่สามารถทำงานได้ ซึ่งเป็นสิ่งจำเป็นสำหรับการคำนวณ **คำนวณระยะเวลาของงาน** อย่างแม่นยำ

## ทำไมต้องใช้ Aspose.Tasks เพื่อดึงชั่วโมงทำงาน?
- **ไม่ต้องใช้ Microsoft Project** – ทำงานกับไฟล์ .MPP บนแพลตฟอร์มใดก็ได้  
- **รองรับปฏิทินเต็มรูปแบบ** – รวมถึงปฏิทินเริ่มต้น, ปฏิทินทรัพยากร, และปฏิทินงาน  
- **ประสิทธิภาพสูง** – ประมวลผลโครงการขนาดใหญ่ได้อย่างรวดเร็ว  
- **เอกสารครบถ้วน** – ตัวอย่างและอ้างอิง API มีให้ใช้งานง่าย

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – รุ่น 8 หรือสูงกว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [here](https://releases.aspose.com/tasks/java/)  
3. ความรู้พื้นฐานการเขียนโปรแกรม Java  

## นำเข้าแพ็กเกจ
แรกสุด, นำเข้า namespace หลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## ขั้นตอนที่ 1: โหลดไฟล์ MPP
โหลดไฟล์โครงการของคุณ (ขั้นตอน **load mpp file**) เพื่อให้สามารถทำงานกับปฏิทินได้:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 2: ดึงข้อมูลงานและปฏิทิน
เลือกงานที่ต้องการวิเคราะห์และดึงปฏิทินที่เชื่อมโยงกับงานนั้น นี่คือขั้นตอนที่เราจะ **ดึงชั่วโมงทำงาน** สำหรับงานนั้น:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## ขั้นตอนที่ 3: กำหนดวันที่เริ่มต้นและสิ้นสุด
ตั้งช่วงเวลาที่คุณต้องการ **กำหนดวันทำงาน**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## ขั้นตอนที่ 4: วนลูปผ่านวันที่
วนลูปผ่านแต่ละวันที่อยู่ในระยะเวลาของงาน ลูปนี้จะช่วยให้เราสามารถ **ปรับแต่งชั่วโมงทำงาน** ได้ในภายหลังหากต้องการ:

```java
java.util.Calendar tempDate = calStartDate;
```

## ขั้นตอนที่ 5: คำนวณระยะเวลา
ในระหว่างการวนลูป เราจะตรวจสอบว่าแต่ละวันเป็นวันทำงานหรือไม่, รวมชั่วโมงทำงาน, และสุดท้ายคำนวณระยะเวลาของงานเป็นนาที, ชั่วโมง, และวัน:

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

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **งานคืนค่า `null` สำหรับปฏิทิน** | ตรวจสอบให้แน่ใจว่างานมีการกำหนดปฏิทิน; หากไม่มีจะสืบทอดจากปฏิทินเริ่มต้นของโครงการ |
| **ระยะเวลาไม่ถูกต้องเนื่องจากวันหยุด** | ยืนยันว่ามีการกำหนดวันหยุดในปฏิทินของงานหรือในปฏิทินฐานของโครงการ |
| **ความไม่ตรงกันของโซนเวลา** | ใช้ `java.util.TimeZone` เพื่อปรับโซนเวลาของปฏิทินให้สอดคล้องกับระบบของคุณหากจำเป็น |

## คำถามที่พบบ่อย
### ถ: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?
**ตอบ:** ใช่, Aspose.Tasks for Java ให้การสนับสนุนอย่างครบวงจรสำหรับการจัดการโครงสร้างโครงการที่ซับซ้อน รวมถึงงาน, ทรัพยากร, และปฏิทิน

### ถ: Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?
**ตอบ:** แน่นอน, Aspose.Tasks for Java รองรับหลายเวอร์ชันของ MS Project, ทำให้สามารถใช้งานได้กับสภาพแวดล้อมที่หลากหลาย

### ถ: สามารถปรับแต่งชั่วโมงทำงานและวันหยุดในปฏิทินโครงการได้หรือไม่?
**ตอบ:** ได้, คุณสามารถปรับแต่งชั่วโมงทำงานและวันหยุดตามความต้องการของโครงการได้อย่างง่ายดายโดยใช้ API ของ Aspose.Tasks for Java

### ถ: Aspose.Tasks for Java มีการสนับสนุนและเอกสารหรือไม่?
**ตอบ:** มี, Aspose.Tasks for Java มีเอกสารที่ครอบคลุมและฟอรั่มสนับสนุนเฉพาะเพื่อช่วยนักพัฒนาใช้คุณลักษณะต่าง ๆ อย่างมีประสิทธิภาพ

### ถ: มีรุ่นทดลองของ Aspose.Tasks for Java หรือไม่?
**ตอบ:** มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Tasks for Java ได้จาก [here](https://releases.aspose.com/)

## สรุป
ในคู่มือนี้เราได้สาธิตวิธี **กำหนดวันทำงาน**, **ดึงชั่วโมงทำงาน**, และ **คำนวณระยะเวลาของงาน** จากปฏิทิน MS Project ด้วย Aspose.Tasks for Java โดยทำตามขั้นตอนที่กล่าวมา คุณจะสามารถอัตโนมัติการวิเคราะห์กำหนดเวลา, ปรับแต่งปฏิทิน, และทำให้แผนโครงการของคุณแม่นยำและเป็นปัจจุบันอยู่เสมอ

---

**อัปเดตล่าสุด:** 2025-12-05  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}