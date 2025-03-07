---
title: จัดการต้นทุนงานใน Aspose.Tasks
linktitle: จัดการต้นทุนงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการต้นทุนงานในแอปพลิเคชัน Java โดยใช้ Aspose.Tasks ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการต้นทุนโครงการอย่างมีประสิทธิภาพ
weight: 21
url: /th/java/task-properties/manage-task-cost/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการต้นทุนงานใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่โลกของ Aspose.Tasks สำหรับ Java ไลบรารีอันทรงพลังที่ช่วยให้คุณจัดการต้นทุนงานภายในแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีการใช้ Aspose.Tasks อย่างมีประสิทธิภาพเพื่อจัดการต้นทุนงาน เพื่อให้มั่นใจว่าการจัดการโครงการมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อม Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนระบบของคุณ
2. ไลบรารี Aspose.Tasks: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
เมื่อคุณตั้งค่าสภาพแวดล้อมของคุณและติดตั้งไลบรารี Aspose.Tasks แล้ว คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ รวมบรรทัดต่อไปนี้ในรหัสของคุณ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// นำเข้าคลาส Aspose.Tasks
```
ตอนนี้ เราจะแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อจัดการต้นทุนงานอย่างมีประสิทธิภาพ
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
```java
// กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
String dataDir = "Your Document Directory";
// สร้างโครงการใหม่
Project project = new Project();
```
## ขั้นตอนที่ 2: เพิ่มงานใหม่
```java
// เพิ่มงานใหม่ให้กับงานรูท
Task task = project.getRootTask().getChildren().add("Task");
```
## ขั้นตอนที่ 3: กำหนดต้นทุนงาน
```java
// ตั้งต้นทุนงานเป็น 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```
## ขั้นตอนที่ 4: ดึงข้อมูลงาน
```java
// ดึงและพิมพ์ข้อมูลงาน
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// ดึงข้อมูลและพิมพ์ข้อมูลต้นทุนระดับโครงการ
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อจัดการต้นทุนงานในแอปพลิเคชัน Aspose.Tasks for Java ของคุณอย่างมีประสิทธิภาพ
## บทสรุป
โดยสรุป การเรียนรู้การจัดการต้นทุนงานเป็นสิ่งสำคัญอย่างยิ่งต่อการดำเนินโครงการให้ประสบความสำเร็จ Aspose.Tasks for Java มอบโซลูชันที่แข็งแกร่ง ช่วยให้นักพัฒนาสามารถจัดการต้นทุนได้อย่างแม่นยำ
## คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถเข้าถึงเอกสารได้[ที่นี่](https://reference.aspose.com/tasks/java/).
### ถาม: ฉันจะดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: ดาวน์โหลดห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/java/).
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
