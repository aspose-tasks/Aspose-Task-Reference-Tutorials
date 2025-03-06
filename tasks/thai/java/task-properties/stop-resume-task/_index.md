---
title: หยุดและทำงานต่อใน Aspose.Tasks
linktitle: หยุดและทำงานต่อใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจพลังของ Aspose.Tasks สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนเกี่ยวกับการหยุดและทำงานต่อ เพิ่มประสิทธิภาพการบริหารจัดการโครงการได้อย่างลงตัว!
weight: 30
url: /th/java/task-properties/stop-resume-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# หยุดและทำงานต่อใน Aspose.Tasks

## การแนะนำ
ในขอบเขตของการพัฒนา Java การจัดการงานอย่างมีประสิทธิภาพเป็นส่วนสำคัญของการดำเนินโครงการ Aspose.Tasks สำหรับ Java มอบโซลูชันที่มีประสิทธิภาพสำหรับการจัดการงานด้วยคุณสมบัติอันทรงพลัง ในบทช่วยสอนนี้ เราจะเจาะลึกถึงฟังก์ชันเฉพาะอย่างหนึ่ง นั่นคือ การหยุดและทำงานต่อ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถรวมคุณสมบัตินี้เข้ากับโปรเจ็กต์ Java ของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Tasks สำหรับไลบรารี Java ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ของคุณ คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ในการเริ่มต้นกระบวนการ ตรวจสอบให้แน่ใจว่าได้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## ขั้นตอนที่ 1: การเริ่มต้น
 เริ่มต้นด้วยการเริ่มต้นโครงการของคุณและสร้าง`ChildTasksCollector` ตัวอย่างเพื่อรวบรวมงานทั้งหมด
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## ขั้นตอนที่ 2: กำหนดวันที่ขั้นต่ำ
กำหนดวันที่ขั้นต่ำเพื่อกรองงานที่จำเป็นต้องหยุดหรือดำเนินการต่อ
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## ขั้นตอนที่ 3: หยุดและทำงานต่อ
ทำซ้ำงานต่างๆ ตรวจสอบและพิมพ์วันที่หยุดและดำเนินการต่อ
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
ทำซ้ำขั้นตอนเหล่านี้ในโปรเจ็กต์ Java ของคุณเพื่อรวมฟังก์ชันการหยุดและดำเนินการต่อโดยใช้ Aspose.Tasks สำหรับ Java ได้อย่างราบรื่น
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการหยุดและทำงานต่อโดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณจะสามารถเพิ่มความสามารถในการจัดการโครงการและปรับปรุงการดำเนินงานได้
## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ Java เหมาะสำหรับโปรเจ็กต์ขนาดใหญ่หรือไม่
อย่างแน่นอน! Aspose.Tasks สำหรับ Java ได้รับการออกแบบมาเพื่อรองรับโปรเจ็กต์ที่มีขนาดแตกต่างกัน ทำให้มั่นใจได้ถึงประสิทธิภาพและความน่าเชื่อถือ
### ฉันสามารถปรับแต่งวันที่เพื่อหยุดและทำงานต่อได้หรือไม่
ใช่ ตัวอย่างที่ให้มามีความยืดหยุ่นในการกำหนดวันที่ขั้นต่ำตามความต้องการของโครงการของคุณ
### ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### มี Aspose.Tasks สำหรับ Java รุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึง[ทดลองฟรี](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติก่อนตัดสินใจซื้อ
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
