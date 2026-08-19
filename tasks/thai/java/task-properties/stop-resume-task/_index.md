---
date: 2026-02-26
description: เรียนรู้วิธีการทำให้ทำงานต่อและหยุดงานใน Aspose.Tasks สำหรับ Java รวมถึงการกรองงานตามวันที่เพื่อการควบคุมโครงการที่แม่นยำ
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีดำเนินการต่องานและหยุดงานใน Aspose.Tasks
url: /th/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีทำต่องานและหยุดงานใน Aspose.Tasks

## บทนำ
หากคุณกำลังสร้างโซลูชันการจัดการโครงการด้วย Java คุณมักจะต้อง **หยุดชั่วคราว** งานหนึ่งแล้ว **ดำเนินต่อ** ภายหลัง Aspose.Tasks for Java ทำให้เรื่องนี้ง่ายขึ้นด้วยคุณสมบัติในตัวสำหรับการหยุดและทำต่อ งาน ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีทำต่องาน** และ **วิธีหยุดงาน** ด้วยโปรแกรม และยังจะได้เห็นวิธี **กรองงานตามวันที่** เพื่อให้คุณทำงานเฉพาะรายการที่เกี่ยวข้องในตารางเวลา

## คำตอบสั้น
- **อะไรหมายถึง “stop” สำหรับงาน?** มันกำหนดวันที่หยุด ทำให้การทำงานหยุดชั่วคราวหลังจากจุดนั้น  
- **ฉันจะทำต่องานที่หยุดได้อย่างไร?** โดยกำหนดวันที่ทำต่อที่อยู่หลังจากวันที่หยุด  
- **ฉันสามารถจำกัดการทำงานให้อยู่ในช่วงวันที่ได้หรือไม่?** ใช่ – ใช้วันที่ขั้นต่ำเพื่อกรองงาน  
- **ต้องใช้เวอร์ชันของไลบรารีใด?** เวอร์ชันล่าสุดของ Aspose.Tasks for Java (API ยังคงเสถียร)  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้ทดสอบได้; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  

## อะไรคือ “วิธีทำต่องาน” ใน Aspose.Tasks?
การทำต่องานหมายถึงการกำหนดวันที่ **RESUME** ให้กับอ็อบเจ็กต์ `Task` อย่างง่าย เมื่อเอนจินโครงการประมวลผลตารางเวลา งานจะดำเนินต่อจากวันที่นั้นต่อไป ซึ่งเป็นประโยชน์อย่างยิ่งสำหรับการจัดการการหยุดชะงัก เช่น การไม่มีทรัพยากรหรือการพึ่งพาภายนอก  

## ทำไมต้องใช้คุณสมบัติหยุด/ทำต่อ?
- **ควบคุมไทม์ไลน์:** หยุดงานชั่วคราวโดยไม่ต้องลบงาน  
- **การรายงานที่แม่นยำ:** แสดงวันที่เริ่ม/สิ้นสุดที่เป็นจริงในแผนภูมิ Gantt  
- **อัตโนมัติง่าย:** ผสานกับตัวกรองวันที่เพื่ออัปเดตหลายงานพร้อมกัน  

## ข้อกำหนดเบื้องต้น
- ความเข้าใจพื้นฐาน Java อย่างมั่นคง  
- ติดตั้ง JDK บนเครื่องของคุณ  
- ไลบรารี Aspose.Tasks for Java เพิ่มลงในโปรเจกต์ของคุณ (ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/java/))  

## นำเข้าแพ็กเกจ
ขั้นแรก นำคลาสที่จำเป็นเข้ามาในสโคปเพื่อให้คุณสามารถทำงานกับโปรเจกต์และงานได้  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## ขั้นตอนที่ 1: เริ่มต้น Project และ Collector
สร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ MPP ของคุณและตั้งค่า `ChildTasksCollector` เพื่อรวบรวมทุกงานในโครงสร้างลำดับชั้น  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## ขั้นตอนที่ 2: กำหนดวันที่ขั้นต่ำสำหรับการกรอง
หากคุณต้องการทำงานเฉพาะกับงานที่มีวันที่หยุดหรือทำต่อที่มีความหมาย ให้กำหนด **วันที่ขั้นต่ำ** นี่คือหัวใจของเทคนิค *กรองงานตามวันที่*  

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## ขั้นตอนที่ 3: วนลูป ตรวจสอบ และแสดงค่าการหยุด/ทำต่อ
ตอนนี้ให้วนลูปผ่านงานที่รวบรวมไว้ ใช้ตรรกะ **วิธีหยุดงาน** และพิมพ์วันที่ โค้ดนี้ยังแสดง **วิธีทำต่องาน** โดยอ่านคุณสมบัติ `RESUME`  

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

> **เคล็ดลับมืออาชีพ:** แทนที่การเรียก `System.out.println` ด้วยตรรกะของคุณเอง (เช่น การอัปเดตวันที่, การบันทึกลงไฟล์, หรือการแก้ไขอ็อบเจ็กต์งาน) เพื่อ *หยุด* หรือ *ทำต่อ* งานตามที่ต้องการ  

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | งานไม่มีการตั้งค่าวันที่หยุด | ตรวจสอบว่าเป็น `null` ก่อนเรียก `.before(minDate)` |
| Dates appear as `NA` even after setting | วันที่ขั้นต่ำใหม่เกินไป | ใช้ `minDate` ที่เก่ากว่า หรือเอาตัวกรองออก |
| Changes not reflected in the saved MPP | โปรเจกต์ไม่ได้บันทึกหลังการแก้ไข | เรียก `project.save("output.mpp");` หลังจากอัปเดตงาน |

## คำถามที่พบบ่อย

### Aspose.Tasks for Java เหมาะกับโครงการขนาดใหญ่หรือไม่?
แน่นอน! Aspose.Tasks for Java ถูกออกแบบมาเพื่อจัดการโครงการทุกขนาด ให้ประสิทธิภาพและความน่าเชื่อถือ  

### ฉันสามารถกำหนดวันที่สำหรับการหยุดและทำต่องานได้หรือไม่?
ได้ ตัวอย่างที่ให้มาช่วยให้คุณกำหนดวันที่ขั้นต่ำตามความต้องการของโครงการ  

### ฉันจะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
เยี่ยมชม [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา  

### มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
มี คุณสามารถเข้าถึง [free trial](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติก่อนตัดสินใจซื้อ  

### ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?
คุณสามารถรับลิขสิทธิ์ชั่วคราว [here](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบ  

**คำถามเพิ่มเติม**

**ถาม: ฉันจะตั้งวันที่หยุดใหม่สำหรับงานอย่างไร?**  
ตอบ: ใช้ `tsk.set(Tsk.STOP, new Date(...));` แล้วบันทึกโปรเจกต์  

**ถาม: ฉันสามารถกรองงานโดยช่วงเฉพาะแทนการใช้แค่วันที่ขั้นต่ำได้หรือไม่?**  
ตอบ: ได้—เปรียบเทียบทั้ง `before` และ `after` กับวันที่เริ่มและสิ้นสุดของคุณ  

**ถาม: API จะคำนวณตารางเวลาใหม่โดยอัตโนมัติหลังจากเปลี่ยนวันที่หยุด/ทำต่อหรือไม่?**  
ตอบ: หลังจากแก้ไขวันที่ ให้เรียก `project.calculateCriticalPath();` เพื่อรีเฟรชตารางเวลา  

## สรุป
ในคู่มือนี้ เราได้อธิบาย **วิธีทำต่องาน** และ **วิธีหยุดงาน** ด้วย Aspose.Tasks for Java พร้อมวิธีการที่เป็นประโยชน์ในการ **กรองงานตามวันที่** การนำโค้ดเหล่านี้ไปใช้ในแอปพลิเคชันของคุณ จะทำให้คุณควบคุมไทม์ไลน์ของโครงการได้อย่างละเอียดและสามารถอัตโนมัติการปรับตารางเวลาได้อย่างมั่นใจ  

---

**อัปเดตล่าสุด:** 2026-02-26  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}