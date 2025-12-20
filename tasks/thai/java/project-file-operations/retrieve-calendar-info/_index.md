---
date: 2025-12-20
description: เรียนรู้วิธีใช้ Aspose.Tasks เพื่อดึงรายละเอียดปฏิทินโครงการจากไฟล์ Microsoft
  Project ด้วย Java คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ด
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีใช้ Aspose.Tasks เพื่อดึงข้อมูลปฏิทินของ MS Project
url: /th/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ Aspose.Tasks เพื่อดึงข้อมูลปฏิทินของ MS Project

## บทนำ
ในบทเรียนนี้, **คุณจะได้ค้นพบวิธีใช้ Aspose.Tasks** เพื่อดึงข้อมูลปฏิทินจากไฟล์ Microsoft Project อย่างโปรแกรมเมติก การเข้าถึงข้อมูลปฏิทินเช่น วันทำงาน, ชั่วโมงทำงาน, และข้อยกเว้นเป็นสิ่งสำคัญเมื่อคุณต้อง **ดึงรายละเอียดปฏิทินของโครงการ** สำหรับการรายงาน, การรวมระบบ, หรือตรรกะการจัดตารางแบบกำหนดเอง มาดำเนินการตามขั้นตอนทีละขั้นตอนกันเถอะ

## คำตอบสั้น
- **ไลบรารีที่ใช้ในบทเรียนนี้คืออะไร?** Aspose.Tasks for Java.  
- **คีย์เวิร์ดหลักที่ครอบคลุมคือ?** *how to use aspose.tasks*.  
- **คุณสามารถดึงอะไรได้บ้าง?** ปฏิทินของโครงการ รวมถึงวันทำงานและชั่วโมงทำงาน.  
- **ต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับคือ?** Java 8 หรือสูงกว่า.

## ทำไมต้องดึงข้อมูลปฏิทินของโครงการ?
ปฏิทินของโครงการกำหนดวันที่ของงาน, การจัดสรรทรัพยากร, และการคำนวณระยะเวลาโดยรวม โดยการดึงข้อมูลนี้คุณสามารถ:
- สร้างรายงานแบบกำหนดเองที่สะท้อนตารางการทำงานจริง.  
- ซิงโครไนซ์ไทม์ไลน์ของ Microsoft Project กับระบบภายนอก (ERP, BI, ฯลฯ).  
- ทำการวิเคราะห์แบบ what‑if โดยการปรับตั้งค่าปฏิทินผ่านโปรแกรม.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java.  
- Java Development Kit (JDK) ที่ติดตั้งบนระบบของคุณ.  
- ไลบรารี Aspose.Tasks for Java. คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).

## นำเข้าชุดแพ็กเกจ
ก่อนอื่น, นำเข้าคลาส Aspose.Tasks ที่จำเป็นเข้าสู่โครงการ Java ของคุณ

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่มีไฟล์ *.mpp* ของคุณ

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยพาธเต็มของโฟลเดอร์ที่มี **project.mpp** อยู่

## ขั้นตอนที่ 2: กำหนดหน่วยเวลา
สร้างค่าสถิตที่ช่วยแปลงการแสดงเวลาแบบภายในให้เป็นชั่วโมงที่มนุษย์อ่านได้

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

ค่านี้ถูกแสดงเป็นไมโครวินาที ซึ่งเป็นวิธีที่ Aspose.Tasks เก็บเวลาภายใน

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ Project
โหลดไฟล์ Microsoft Project เข้าไปในอ็อบเจกต์ `Project`

```java
Project project = new Project(dataDir + "project.mpp");
```

คอนสตรัคเตอร์ `Project` จะทำการพาร์สไฟล์ *.mpp* และทำให้ข้อมูลโครงการทั้งหมด, รวมถึงปฏิทิน, สามารถเข้าถึงได้ผ่าน API

## ขั้นตอนที่ 4: ดึงข้อมูลปฏิทิน
รับคอลเลกชันของปฏิทินที่กำหนดไว้ในโครงการ

```java
CalendarCollection alCals = project.getCalendars();
```

โครงการอาจมีหลายปฏิทิน (มาตรฐาน, ทรัพยากร, และปฏิทินกำหนดเอง) คอลเลกชันนี้ให้คุณเข้าถึงแต่ละปฏิทินได้

## ขั้นตอนที่ 5: วนลูปผ่านปฏิทิน
วนลูปผ่านทุกปฏิทิน, แสดง UID, ชื่อ, และวันทำงานพร้อมชั่วโมงที่สอดคล้องกัน

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

ลูปภายในจะตรวจสอบแต่ละอ็อบเจกต์ `WeekDay` หากวันนั้นถูกกำหนดให้เป็นวันทำงาน จะพิมพ์ประเภทวัน (Monday, Tuesday, …) พร้อมกับชั่วโมงทำงานที่คำนวณได้

## ขั้นตอนที่ 6: แสดงข้อความเสร็จสิ้น
สัญญาณว่ากระบวนการดึงข้อมูลได้เสร็จสิ้น

```java
System.out.println("Process completed Successfully");
```

## สรุป
โดยทำตามขั้นตอนเหล่านี้, **คุณตอนนี้รู้วิธีใช้ Aspose.Tasks เพื่อดึงข้อมูลปฏิทินของโครงการ** จากไฟล์ MS Project ด้วย Java แล้ว คุณสามารถนำตรรกะนี้ไปผสานในแอปพลิเคชันที่ใหญ่ขึ้น, ทำอัตโนมัติการรายงาน, หรือซิงโครไนซ์ตารางกับระบบองค์กรอื่น ๆ

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
ตอบ: ใช่, Aspose.Tasks รองรับหลายแพลตฟอร์มและหลายภาษาโปรแกรม, รวมถึง .NET, C++, Python, และ Java.

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก [here](https://releases.aspose.com/).

**ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร?**  
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**ถาม: ฉันสามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks ได้หรือไม่?**  
ตอบ: ได้, ไลเซนส์ชั่วคราวพร้อมจำหน่ายที่ [here](https://purchase.aspose.com/temporary-license/).

**ถาม: ฉันจะหาเอกสารรายละเอียดสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: คุณสามารถอ้างอิงเอกสารได้ที่ [here](https://reference.aspose.com/tasks/java/).

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}