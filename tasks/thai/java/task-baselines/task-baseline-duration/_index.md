---
title: การจัดการระยะเวลาพื้นฐานงานใน Aspose.Tasks
linktitle: การจัดการระยะเวลาพื้นฐานงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการงานพื้นฐานอย่างมีประสิทธิภาพใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนตลอดกระบวนการ
type: docs
weight: 12
url: /th/java/task-baselines/task-baseline-duration/
---
## การแนะนำ
การจัดการงานพื้นฐานใน MS Project เป็นสิ่งสำคัญสำหรับการวางแผนและการติดตามโครงการ ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการระยะเวลาพื้นฐานของงานอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  ไลบรารี Aspose.Tasks: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์โปรเจ็กต์
เริ่มต้นอินสแตนซ์โครงการใหม่โดยใช้รหัสต่อไปนี้:
```java
Project project = new Project();
```
## ขั้นตอนที่ 2: สร้างงานพื้นฐาน
สร้างงานใหม่และตั้งค่าพื้นฐานโดยใช้รหัสต่อไปนี้:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## ขั้นตอนที่ 3: แสดงข้อมูลพื้นฐานของงาน
ดึงและแสดงข้อมูลพื้นฐานของงาน เช่น ระยะเวลา วันที่เริ่มต้น วันที่เสร็จสิ้น และอื่นๆ:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## ขั้นตอนที่ 4: ตรวจสอบข้อมูลพื้นฐานระหว่างกาลและต้นทุนคงที่
ตรวจสอบว่าข้อมูลพื้นฐานเป็นข้อมูลพื้นฐานระหว่างกาลหรือไม่ และดึงข้อมูลต้นทุนคงที่ที่เกี่ยวข้อง:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## ขั้นตอนที่ 5: พิมพ์ข้อมูลตามช่วงเวลา
พิมพ์ข้อมูลตามช่วงเวลาที่เกี่ยวข้องกับงานพื้นฐาน:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการระยะเวลาพื้นฐานของงานใน MS Project ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java

## บทสรุป
การจัดการเส้นฐานของงานถือเป็นสิ่งสำคัญสำหรับการจัดการโครงการ ทำให้คุณสามารถติดตามการเบี่ยงเบนไปจากกำหนดการที่วางแผนไว้ได้ ด้วย Aspose.Tasks สำหรับ Java กระบวนการนี้จะมีความคล่องตัวและมีประสิทธิภาพ ทำให้สามารถควบคุมและส่งมอบโปรเจ็กต์ได้ดียิ่งขึ้น
## คำถามที่พบบ่อย
### พื้นฐานงานใน MS Project คืออะไร
ข้อมูลพื้นฐานของงานใน MS Project คือภาพรวมของกำหนดการที่วางแผนไว้เบื้องต้นสำหรับงาน รวมถึงวันที่เริ่มต้น วันที่เสร็จสิ้น และระยะเวลา
### เหตุใดการจัดการพื้นฐานงานจึงมีความสำคัญ
การจัดการเส้นฐานงานช่วยในการเปรียบเทียบกำหนดการที่วางแผนไว้กับความคืบหน้าที่แท้จริงของโครงการ ช่วยให้ติดตามและตัดสินใจได้ดีขึ้น
### ฉันสามารถแก้ไขงานพื้นฐานเมื่อตั้งค่าแล้วได้หรือไม่
ได้ คุณสามารถแก้ไขงานพื้นฐานใน MS Project เพื่อให้สะท้อนถึงการเปลี่ยนแปลงในแผนโครงการได้ อย่างไรก็ตาม จำเป็นต้องบันทึกความเบี่ยงเบนไปจากเส้นฐานเดิม
### Aspose.Tasks รองรับฟังก์ชันการจัดการโครงการอื่นๆ หรือไม่
ใช่ Aspose.Tasks นำเสนอคุณสมบัติที่หลากหลายสำหรับการจัดการโครงการ รวมถึงการกำหนดเวลางาน การจัดสรรทรัพยากร และการสร้างแผนภูมิแกนต์
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนสำหรับ Aspose.Tasks ได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)ซึ่งคุณสามารถถามคำถามและโต้ตอบกับผู้ใช้รายอื่นได้