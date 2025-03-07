---
title: การกำหนดเวลางานพื้นฐานใน Aspose.Tasks
linktitle: การกำหนดเวลางานพื้นฐานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีกำหนดเวลางานพื้นฐานอย่างมีประสิทธิภาพด้วย Aspose.Tasks for Java ปรับปรุงกระบวนการจัดการโครงการของคุณได้อย่างง่ายดาย
weight: 10
url: /th/java/task-baselines/baseline-task-scheduling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดเวลางานพื้นฐานใน Aspose.Tasks

## การแนะนำ
การจัดการเส้นฐานของงานเป็นส่วนสำคัญของการจัดการโครงการ ทำให้คุณสามารถเปรียบเทียบความคืบหน้าที่วางแผนไว้กับความคืบหน้าจริงได้อย่างแม่นยำ ในบทช่วยสอนนี้ เราจะสำรวจวิธีดำเนินการกำหนดเวลางานพื้นฐานโดยใช้ Aspose.Tasks สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะพร้อมที่จะปรับปรุงกระบวนการจัดการโครงการของคุณอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### สภาพแวดล้อมการพัฒนาจาวา
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จากไฟล์[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks สำหรับไลบรารี Java
 ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/) และรวมไว้ในโปรเจ็กต์ Java ของคุณ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```
ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: สร้างอินสแตนซ์โปรเจ็กต์ใหม่
```java
Project project = new Project();
```
## ขั้นตอนที่ 2: กำหนดงานและตั้งค่าพื้นฐาน
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## ขั้นตอนที่ 3: เข้าถึงข้อมูลพื้นฐาน
```java
TaskBaseline baseline = task.getBaselines().get(0);
```
## ขั้นตอนที่ 4: แสดงระยะเวลาพื้นฐาน
```java
System.out.println(baseline.getDuration().toString());
```
## ขั้นตอนที่ 5: แสดงวันที่เริ่มต้นพื้นฐาน
```java
System.out.println("Baseline Start: " + baseline.getStart());
```
## ขั้นตอนที่ 6: แสดงวันที่เสร็จสิ้นพื้นฐาน
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถใช้ Aspose.Tasks สำหรับ Java ในการจัดการพื้นฐานงานภายในโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพ
## บทสรุป
โดยสรุป การเรียนรู้การจัดกำหนดการงานพื้นฐานเป็นสิ่งจำเป็นสำหรับการจัดการโครงการที่แม่นยำ ด้วย Aspose.Tasks สำหรับ Java คุณสามารถจัดการงานพื้นฐานได้อย่างง่ายดาย และรับประกันความสอดคล้องระหว่างความคืบหน้าที่วางแผนไว้และความคืบหน้าจริง ซึ่งนำไปสู่ผลลัพธ์ของโครงการที่ประสบความสำเร็จ
## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ Java สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java มอบความสามารถที่แข็งแกร่งในการจัดการโปรเจ็กต์ที่มีความซับซ้อนหลากหลายอย่างมีประสิทธิภาพ
### Aspose.Tasks สำหรับ Java เข้ากันได้กับไลบรารี Java อื่น ๆ หรือไม่
แน่นอนว่า Aspose.Tasks สำหรับ Java ทำงานร่วมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น ช่วยเพิ่มขีดความสามารถในการจัดการโครงการของคุณ
### ฉันสามารถปรับแต่งพื้นฐานงานโดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่
แน่นอนว่า Aspose.Tasks for Java มีฟังก์ชันการทำงานที่ครอบคลุมเพื่อปรับแต่งและจัดการพื้นฐานงานตามความต้องการของโปรเจ็กต์ของคุณ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึง Aspose.Tasks for Java รุ่นทดลองใช้ฟรีได้จาก[หน้าปล่อย](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ คุณสามารถไปที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
