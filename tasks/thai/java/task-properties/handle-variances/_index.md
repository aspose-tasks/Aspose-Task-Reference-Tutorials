---
date: 2026-02-20
description: เรียนรู้วิธีตั้งค่าวันเริ่มต้นของโครงการและจัดการความเบี่ยงเบนของโครงการโดยใช้
  Aspose.Tasks สำหรับ Java คู่มือนี้ยังแสดงวิธีตั้งระยะเวลาของงานอย่างมีประสิทธิภาพ
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ตั้งค่าวันเริ่มต้นของโครงการและจัดการความแปรผันของงาน Aspose.Tasks
url: /th/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดวันที่เริ่มโครงการและจัดการความแปรผันของงาน Aspose.Tasks

## บทนำ
ในโลกของการจัดการโครงการ, **set project start date** เป็นหนึ่งในขั้นตอนแรกที่คุณทำเพื่อให้กำหนดการของคุณมีพื้นฐานที่มั่นคง Aspose.Tasks for Java ทำให้ขั้นตอนนี้—และการจัดการความแปรผันของงานต่อไป—เป็นเรื่องง่ายและเชื่อถือได้ ในบทเรียนนี้คุณจะได้เรียนรู้วิธีกำหนดวันที่เริ่มโครงการ, กำหนดระยะเวลาของงาน, และจัดการความแปรผันของโครงการอย่างมีประสิทธิภาพ

## คำตอบสั้น
- **วิธีหลักในการกำหนดวันที่เริ่มโครงการคืออะไร?** ใช้ `project.set(Prj.START_DATE, …)` พร้อมกับอ็อบเจ็กต์ `java.util.Calendar`  
- **คลาสใดที่เป็นตัวแทนของ baseline สำหรับการติดตามความแปรผัน?** `BaselineType.Baseline`  
- **ฉันสามารถปรับวันที่เริ่มและสิ้นสุดของงานหลังจากตั้ง baseline แล้วได้หรือไม่?** ได้, เพียงอัปเดต `Tsk.START` และ `Tsk.STOP`  
- **ฉันต้องมีลิขสิทธิ์สำหรับการพัฒนาใช่หรือไม่?** มีลิขสิทธิ์ชั่วคราวสำหรับการประเมินผล  
- **เวอร์ชันของ Aspose.Tasks ที่ทำงานกับโค้ดนี้คือเวอร์ชันใด?** เวอร์ชันล่าสุดของ Aspose.Tasks for Java

## What is **set project start date**?
การกำหนดวันที่เริ่มโครงการหมายถึงการระบุวันในปฏิทินที่ทุกวันที่ของงานจะถูกคำนวณจากนั้น มันมีผลต่อการคำนวณกำหนดการ, การวิเคราะห์เส้นทางวิกฤต, และการสร้าง baseline ทำให้เป็นสิ่งสำคัญสำหรับการจัดการความแปรผันที่แม่นยำ

## Why set project start date and manage variances?
- **ความสามารถในการคาดการณ์:** สร้าง baseline ที่รู้จักได้เพื่อเปรียบเทียบความก้าวหน้าในจริง  
- **ความยืดหยุ่น:** ให้คุณปรับวันที่ของงานแต่ละรายการโดยไม่สูญเสียแผนเดิม  
- **การรายงาน:** ทำให้สามารถสร้างรายงานความแปรผันที่ชัดเจนซึ่งเน้นการล่าช้าหรือการเสร็จเร็วของกำหนดการ  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

- สภาพแวดล้อมการพัฒนา Java – ติดตั้ง JDK และมี IDE หรือเครื่องมือสร้างโปรเจกต์พร้อมใช้งาน  
- ไลบรารี Aspose.Tasks – ดาวน์โหลดไลบรารี **[ที่นี่](https://releases.aspose.com/tasks/java/)**  

## นำเข้าแพ็กเกจ
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์
สร้างอินสแตนซ์ `Project` ใหม่ที่จะเก็บงานทั้งหมดและข้อมูลกำหนดการ

```java
Project project = new Project();
```

## ขั้นตอนที่ 2: เพิ่มงาน
เพิ่มงานภายใต้งานราก (root task) ซึ่งจะเป็นรายการงานที่เราจะปรับในภายหลัง

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## ขั้นตอนที่ 3: กำหนดวันที่เริ่มและระยะเวลา
กำหนดวันที่เริ่มของโครงการและกำหนดระยะเวลาของงาน นี่เป็นการสาธิต **set task duration** ในการปฏิบัติ

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## ขั้นตอนที่ 4: ตั้งค่า Baseline
สร้าง baseline เพื่อให้คุณสามารถเปรียบเทียบวันที่ที่วางแผนกับวันที่จริงในภายหลัง—เป็นสิ่งจำเป็นสำหรับ **manage project variances**

```java
project.setBaseline(BaselineType.Baseline);
```

## ขั้นตอนที่ 5: ปรับวันที่เริ่มและสิ้นสุดของงาน
แก้ไขวันที่เริ่มและสิ้นสุดของงานเพื่อจำลองสถานการณ์ความแปรผัน

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*คุณสามารถปรับเปลี่ยนวันที่และระยะเวลาให้ตรงกับความต้องการเฉพาะของโครงการของคุณได้ตามต้องการ*

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **Baseline ต้องตั้งก่อนการปรับวันที่.** หากคุณเปลี่ยนวันที่ก่อน, baseline จะบันทึกกำหนดการที่เปลี่ยนแปลงแล้วแทนแผนเดิม  
- **เดือนใน Calendar เริ่มจากศูนย์.** จำไว้ว่า `Calendar.FEBRUARY` มีค่าเป็นเดือน 1 ไม่ใช่ 2  
- **หน่วยของระยะเวลา:** `project.getDuration(2)` สร้างระยะเวลาเป็นสองวันโดยค่าเริ่มต้น; ปรับหน่วยหากคุณต้องการเป็นชั่วโมงหรือสัปดาห์  

## สรุป
ด้วยการเชี่ยวชาญวิธี **set project start date**, **set task duration**, และ **manage project variances**, คุณจะได้ควบคุมกำหนดการโครงการของคุณอย่างเต็มที่ด้วย Aspose.Tasks for Java ขั้นตอนข้างต้นให้พื้นฐานที่มั่นคงซึ่งคุณสามารถต่อยอดไปสู่สถานการณ์ที่ซับซ้อนยิ่งขึ้น เช่น โครงการหลายเฟส, การจัดสรรทรัพยากร, และการสร้างรายงานอัตโนมัติ

## คำถามที่พบบ่อย
### Aspose.Tasks เหมาะกับความต้องการการจัดการโครงการทั้งหมดหรือไม่?
Aspose.Tasks เป็นเครื่องมือที่หลากหลายและเหมาะกับความต้องการการจัดการโครงการในหลายรูปแบบ ให้ความยืดหยุ่นและฟีเจอร์ที่แข็งแกร่ง

### ฉันสามารถรวม Aspose.Tasks เข้าในโปรเจกต์ Java ที่มีอยู่ของฉันได้หรือไม่?
ได้, คุณสามารถรวม Aspose.Tasks เข้าในโปรเจกต์ Java ของคุณได้อย่างง่ายดายโดยทำตามเอกสารที่ให้ไว้ **[ที่นี่](https://reference.aspose.com/tasks/java/)**

### มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks หรือไม่?
มี, คุณสามารถรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks **[ที่นี่](https://purchase.aspose.com/temporary-license/)**

### ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?
สำหรับการสนับสนุนและการสนทนา, เยี่ยมชมฟอรั่ม Aspose.Tasks **[ที่นี่](https://forum.aspose.com/c/tasks/15)**

### ฉันสามารถดาวน์โหลด Aspose.Tasks for Java ได้หรือไม่?
ได้, ดาวน์โหลดเวอร์ชันล่าสุดของ Aspose.Tasks for Java **[ที่นี่](https://releases.aspose.com/tasks/java/)**

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-02-20  
**ทดสอบด้วย:** Aspose.Tasks เวอร์ชันล่าสุดสำหรับ Java  
**ผู้เขียน:** Aspose