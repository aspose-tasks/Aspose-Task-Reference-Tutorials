---
date: 2026-02-05
description: เรียนรู้วิธีกำหนดวันทำงานและคำนวณระยะเวลางานโดยการดึงชั่วโมงทำงานจากปฏิทินของ
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
การจัดการปฏิทินโครงการเป็นส่วนสำคัญของการวางแผนโครงการที่ประสบความสำเร็จ ในบทแนะนำนี้คุณจะ **กำหนดวันทำงาน** สำหรับงานใด ๆ และ **ดึงชั่วโมงทำงาน** จากปฏิทิน MS Project ด้วย Aspose.Tasks for Java เมื่อจบคู่มือคุณจะสามารถ **คำนวณระยะเวลางาน**, ปรับแต่งชั่วโมงทำงาน, และ **โหลดไฟล์ MPP** เพื่อดึงข้อมูลที่ต้องการได้อย่างเชื่อถือ คุณยังจะได้เห็นวิธี **อ่านไฟล์ MS Project** โดยไม่ต้องติดตั้ง Microsoft Project ทำให้สามารถทำอัตโนมัติบนแพลตฟอร์มใดก็ได้

## คำตอบอย่างรวดเร็ว
- **“กำหนดวันทำงาน” หมายถึงอะไร?** หมายถึงการระบุว่าค่าในปฏิทินใดบ้างที่ถือเป็นวันทำงานสำหรับงานที่กำหนด  
- **ควรใช้ไลบรารีใด?** Aspose.Tasks for Java มี API ครบวงจรสำหรับทำงานกับไฟล์ MS Project  
- **การทำงานนี้ใช้เวลานานเท่าไหร่?** โดยทั่วไป 10–15 นาทีสำหรับการดึงข้อมูลพื้นฐาน  
- **ต้องมีลิขสิทธิ์หรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถปรับแต่งชั่วโมงทำงานได้หรือไม่?** ได้ – คุณสามารถแก้ไขปฏิทิน, เพิ่มวันหยุด, และกำหนดช่วงเวลาทำงานแบบกำหนดเอง  

## “กำหนดวันทำงาน” คืออะไร?
เมื่อกำหนดงาน ปฏิทินโครงการจะบ่งบอกว่าวันใดเป็นวันทำงานและวันใดเป็นวันหยุด (วันสุดสัปดาห์, วันหยุดราชการ) การกำหนดวันทำงานหมายถึงการสอบถามปฏิทินเพื่อทราบว่าเมื่อใดที่สามารถทำงานได้ ซึ่งเป็นสิ่งจำเป็นสำหรับการคำนวณ **คำนวณระยะเวลางาน** อย่างแม่นยำ

## ทำไมต้องใช้ Aspose.Tasks เพื่อดึงชั่วโมงทำงาน?
- **ไม่ต้องใช้ Microsoft Project** – สามารถอ่านไฟล์ MS Project โดยตรงจากโค้ด Java  
- **รองรับปฏิทินครบวงจร** – รวมถึงปฏิทินเริ่มต้น, ปฏิทินทรัพยากร, และปฏิทินงาน  
- **ประสิทธิภาพสูง** – ประมวลผลโครงการขนาดใหญ่ได้อย่างรวดเร็ว  
- **เอกสารครบถ้วน** – ตัวอย่างและอ้างอิง API มีให้ใช้งานง่าย  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือสูงกว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [here](https://releases.aspose.com/tasks/java/)  
3. ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  

## การนำเข้าแพ็กเกจ
ก่อนอื่นให้นำเข้า namespace หลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## วิธีโหลดไฟล์ MPP ด้วย Aspose.Tasks?
การโหลดไฟล์โครงการเป็นขั้นตอนแรกของการวิเคราะห์ปฏิทินใด ๆ API ช่วยให้คุณ **โหลดไฟล์ MPP** ด้วยบรรทัดโค้ดเดียวโดยไม่ต้องใช้ UI ของ MS Project

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## ดึงข้อมูลงานและปฏิทิน
เลือกงานที่ต้องการวิเคราะห์และรับปฏิทินที่เชื่อมโยงกับงานนั้น นี่คือขั้นตอนที่เราจะ **ดึงชั่วโมงทำงาน** สำหรับงานนั้น:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## กำหนดวันที่เริ่มต้นและสิ้นสุด
ตั้งช่วงเวลาเวลาที่คุณต้องการ **กำหนดวันทำงาน** โดยใช้วันที่เริ่มและสิ้นสุดของงานเพื่อให้ประเมินเฉพาะช่วงที่เกี่ยวข้องเท่านั้น

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## วนลูปผ่านวันที่
วนลูปผ่านแต่ละวันที่อยู่ในระยะเวลาของงาน ลูปนี้จะช่วยให้เราสามารถ **ปรับแต่งชั่วโมงทำงาน** ในภายหลังหากต้องการ:

```java
java.util.Calendar tempDate = calStartDate;
```

## คำนวณระยะเวลา
ในระหว่างการวนลูป เราจะตรวจสอบว่าทุกวันเป็นวันทำงานหรือไม่, รวมชั่วโมงทำงาน, และสุดท้ายคำนวณระยะเวลาของงานเป็นนาที, ชั่วโมง, และวัน ขั้นตอนนี้แสดงวิธี **คำนวณวันทำงาน** และ **คำนวณระยะเวลางาน** อย่างโปรแกรมเมติก

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

## วิธีปรับแต่งชั่วโมงทำงานและวันหยุด
Aspose.Tasks ให้คุณแก้ไขช่วงเวลาทำงานของปฏิทินและเพิ่มข้อยกเว้นเช่นวันหยุด คุณสามารถเรียก `taskCalendar.addWorkingTime()` หรือ `taskCalendar.addException()` เพื่อปรับตารางให้สอดคล้องกับนโยบายขององค์กร ซึ่งเป็นประโยชน์เมื่อตาราง 9‑5 ปกติไม่ตรงกับความเป็นจริง

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **Task returns `null` for calendar** | ตรวจสอบให้แน่ใจว่างานมีการกำหนดปฏิทินไว้; หากไม่มีจะสืบทอดจากปฏิทินเริ่มต้นของโครงการ |
| **Incorrect duration because of holidays** | ยืนยันว่ามีการกำหนดวันหยุดในปฏิทินของงานหรือในปฏิทินฐานของโครงการ |
| **Time zone mismatch** | ใช้ `java.util.TimeZone` เพื่อปรับโซนเวลาของปฏิทินให้ตรงกับระบบของคุณหากจำเป็น |

## คำถามที่พบบ่อย
### Q: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?
A: ได้, Aspose.Tasks for Java ให้การสนับสนุนอย่างครบถ้วนสำหรับการจัดการโครงสร้างโครงการที่ซับซ้อน รวมถึงงาน, ทรัพยากร, และปฏิทิน

### Q: Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?
A: แน่นอน, Aspose.Tasks for Java รองรับหลายเวอร์ชันของ MS Project, ทำให้เข้ากันได้กับสภาพแวดล้อมที่หลากหลาย

### Q: สามารถปรับแต่งชั่วโมงทำงานและวันหยุดในปฏิทินโครงการได้หรือไม่?
A: ได้, คุณสามารถปรับแต่งชั่วโมงทำงานและวันหยุดตามความต้องการของโครงการได้อย่างง่ายดายด้วย API ของ Aspose.Tasks for Java

### Q: Aspose.Tasks for Java มีการสนับสนุนและเอกสารหรือไม่?
A: มี, Aspose.Tasks for Java มีเอกสารที่ครอบคลุมและฟอรั่มสนับสนุนเฉพาะสำหรับช่วยนักพัฒนาใช้คุณลักษณะต่าง ๆ อย่างมีประสิทธิภาพ

### Q: มีรุ่นทดลองของ Aspose.Tasks for Java หรือไม่?
A: มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Tasks for Java ได้จาก [here](https://releases.aspose.com/)

## สรุป
ในคู่มือนี้เราได้สาธิตวิธี **กำหนดวันทำงาน**, **ดึงชั่วโมงทำงาน**, และ **คำนวณระยะเวลางาน** จากปฏิทิน MS Project ด้วย Aspose.Tasks for Java โดยทำตามขั้นตอนที่กล่าวมาข้างต้น คุณสามารถทำอัตโนมัติการวิเคราะห์ตารางเวลา, ปรับแต่งปฏิทิน, และทำให้แผนโครงการของคุณแม่นยำและเป็นปัจจุบันได้ คุณมีเครื่องมือที่จำเป็นเพื่อ **อ่านข้อมูล MS Project**, **โหลดไฟล์ MPP**, และทำการคำนวณระยะเวลาอย่างแม่นยำโดยไม่ต้องพึ่ง Microsoft Project

---

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}