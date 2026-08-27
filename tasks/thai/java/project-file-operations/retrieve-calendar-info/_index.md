---
date: 2026-03-27
description: เรียนรู้วิธีใช้ Aspose และ Aspose.Tasks เพื่อดึงรายละเอียดปฏิทินโครงการจากไฟล์
  Microsoft Project ด้วย Java คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด
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
ในบทแนะนำนี้, **คุณจะได้ค้นพบวิธีใช้ Aspose.Tasks** เพื่อดึงข้อมูลปฏิทินจากไฟล์ Microsoft Project อย่างอัตโนมัติ การเข้าถึงข้อมูลปฏิทินเช่นวันทำงาน, ชั่วโมงทำงาน, และข้อยกเว้นเป็นสิ่งสำคัญเมื่อคุณต้องการ **ดึงข้อมูลปฏิทินของโครงการ** สำหรับการรายงาน, การบูรณาการ, หรือตรรกะการกำหนดเวลาที่กำหนดเอง เราจะเดินผ่านกระบวนการทีละขั้นตอน และคุณจะเห็นอย่างชัดเจน **วิธีใช้ Aspose** เพื่อดึงข้อมูลนี้ออกจากไฟล์ *.mpp*.

## คำตอบสั้น
- **ไลบรารีที่บทแนะนำนี้ใช้คืออะไร?** Aspose.Tasks for Java.  
- **คีย์เวิร์ดหลักที่ครอบคลุมคืออะไร?** *how to use aspose*.  
- **คุณสามารถดึงอะไรได้บ้าง?** ปฏิทินของโครงการ, รวมถึงวันทำงานและชั่วโมงทำงาน.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 หรือสูงกว่า.

## Aspose.Tasks คืออะไรและทำไมต้องใช้?
Aspose.Tasks เป็น API ของ Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถอ่าน, เขียน, และจัดการไฟล์ Microsoft Project ได้โดยไม่ต้องใช้ Microsoft Project เอง ด้วยการใช้ Aspose.Tasks คุณสามารถ **how to extract calendar** ข้อมูล, ทำการคำนวณตารางเวลาอัตโนมัติ, และบูรณาการข้อมูลโครงการกับระบบองค์กรอื่น ๆ — ทั้งหมดจากโค้ด Java แท้

## ทำไมต้องดึงข้อมูลปฏิทินของโครงการ?
ปฏิทินของโครงการกำหนดวันที่ของงาน, การจัดสรรทรัพยากร, และการคำนวณไทม์ไลน์โดยรวม โดยการดึงข้อมูลนี้คุณสามารถ:
- สร้างรายงานกำหนดเองที่สะท้อนตารางการทำงานจริง  
- ซิงโครไนซ์ไทม์ไลน์ของ Microsoft Project กับระบบภายนอก (ERP, BI, ฯลฯ)  
- ทำการวิเคราะห์แบบ what‑if โดยการปรับตั้งค่าปฏิทินผ่านโปรแกรม  
- **ดึงข้อมูลปฏิทินของ MS Project** เพื่อการย้ายไปยังเครื่องมือวางแผนอื่น

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- Java Development Kit (JDK) ติดตั้งบนระบบของคุณ  
- ไลบรารี Aspose.Tasks for Java คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
First, import the necessary Aspose.Tasks classes into your Java project.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
Define the folder that contains your *.mpp* file.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path to the folder where **project.mpp** resides.  
เปลี่ยน `"Your Data Directory"` เป็นเส้นทางเต็มของโฟลเดอร์ที่มี **project.mpp** อยู่

## ขั้นตอนที่ 2: กำหนดหน่วยเวลา
Create constants that help convert the internal time representation to human‑readable hours.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

These values are expressed in microseconds, which is how Aspose.Tasks stores time internally.  
ค่าต่าง ๆ นี้ถูกแสดงเป็นไมโครวินาที ซึ่งเป็นหน่วยที่ Aspose.Tasks ใช้เก็บเวลาโดยภายใน

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ Project
Load the Microsoft Project file into a `Project` object.

```java
Project project = new Project(dataDir + "project.mpp");
```

The `Project` constructor parses the *.mpp* file and makes all project data, including calendars, accessible through the API.  
คอนสตรัคเตอร์ `Project` จะทำการอ่านไฟล์ *.mpp* และทำให้ข้อมูลทั้งหมดของโครงการ, รวมถึงปฏิทิน, สามารถเข้าถึงได้ผ่าน API

## ขั้นตอนที่ 4: ดึงข้อมูลปฏิทิน
Obtain the collection of calendars defined in the project.

```java
CalendarCollection alCals = project.getCalendars();
```

A project can contain multiple calendars (standard, resource, and custom calendars). This collection gives you access to each one.  
โครงการอาจมีหลายปฏิทิน (มาตรฐาน, ทรัพยากร, และปฏิทินที่กำหนดเอง) คอลเลกชันนี้ทำให้คุณเข้าถึงแต่ละปฏิทินได้

## ขั้นตอนที่ 5: วนลูปผ่านปฏิทิน
Loop through every calendar, display its UID, name, and the working days with corresponding hours.

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

The inner loop checks each `WeekDay` object. If the day is marked as working, it prints the day type (Monday, Tuesday, …) together with the calculated working hours.  
ลูปภายในจะตรวจสอบแต่ละอ็อบเจ็กต์ `WeekDay` หากวันนั้นถูกกำหนดให้เป็นวันทำงาน จะพิมพ์ประเภทวัน (Monday, Tuesday, …) พร้อมกับจำนวนชั่วโมงทำงานที่คำนวณได้

## ขั้นตอนที่ 6: แสดงข้อความเสร็จสิ้น
Signal that the extraction process has finished.

```java
System.out.println("Process completed Successfully");
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **No calendars returned** | The project file may not contain any custom calendars. | Verify that the *.mpp* actually defines calendars or open it in Microsoft Project to confirm. |
| **Incorrect working hours** | Time conversion constants are off for a different Project version. | Adjust `OneSec`, `OneMin`, `OneHour` if you work with a newer Aspose.Tasks version that changes the internal time unit. |
| **`NullPointerException` on `cal.getName()`** | Some calendar objects could be null. | Add a null‑check before accessing properties (already demonstrated). |

## คำถามที่พบบ่อย

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks supports multiple platforms and programming languages, including .NET, C++, Python, and Java.  
**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).  
**Q: How can I get support for Aspose.Tasks?**  
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).  
**Q: Can I purchase a temporary license for Aspose.Tasks?**  
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).  
**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).

## สรุป
By following these steps, **you now know how to use Aspose.Tasks to extract project calendar** information from an MS Project file using Java. You can integrate this logic into larger applications, automate reporting, or synchronize schedules with other enterprise systems. Remember, mastering **how to use aspose** opens the door to many advanced project‑management automation scenarios.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}