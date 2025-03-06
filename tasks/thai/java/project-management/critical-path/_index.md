---
title: คำนวณเส้นทางโครงการ MS ที่สำคัญใน Aspose.Tasks
linktitle: คำนวณเส้นทางวิกฤติในโครงการ Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีการคำนวณเส้นทางวิกฤติใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java นี่เป็นคำแนะนำทีละขั้นตอนสำหรับการจัดการโครงการที่มีประสิทธิภาพ
weight: 10
url: /th/java/project-management/critical-path/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คำนวณเส้นทางโครงการ MS ที่สำคัญใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการคำนวณเส้นทางวิกฤติใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java เส้นทางวิกฤตเป็นสิ่งจำเป็นสำหรับการจัดการโครงการ เนื่องจากช่วยระบุลำดับของงานที่ต้องทำให้เสร็จตรงเวลา เพื่อให้แน่ใจว่ากำหนดการโดยรวมของโครงการจะไม่ล่าช้า
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในคลาส Java ของคุณ:
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณซึ่งมีไฟล์ MS Project อยู่
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ MS
โหลดไฟล์ MS Project โดยใช้ไลบรารี Aspose.Tasks
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## ขั้นตอนที่ 3: ตั้งค่าโหมดการคำนวณ
ตั้งค่าโหมดการคำนวณเป็นอัตโนมัติเพื่อเปิดใช้งานการคำนวณเส้นทางวิกฤต
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## ขั้นตอนที่ 4: เพิ่มงาน
เพิ่มงานในโครงการของคุณ ในตัวอย่างนี้ เราเพิ่มงานย่อยสามงาน
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## ขั้นตอนที่ 5: สร้างลิงค์งาน
สร้างลิงก์งานเพื่อกำหนดการขึ้นต่อกันระหว่างงาน
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## ขั้นตอนที่ 6: แสดงเส้นทางที่สำคัญ
ดึงข้อมูลและแสดงเส้นทางวิกฤติของโครงการ
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## ขั้นตอนที่ 7: แสดงผล
แสดงข้อความแจ้งว่ากระบวนการเสร็จสมบูรณ์แล้ว
```java
System.out.println("Process completed Successfully");
```

## บทสรุป
การคำนวณเส้นทางวิกฤติใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java มีความสำคัญอย่างยิ่งต่อการจัดการโครงการอย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถระบุลำดับของงานที่มีความสำคัญต่อไทม์ไลน์ของโครงการของคุณได้อย่างแม่นยำ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับไฟล์ MS Project เวอร์ชันใดก็ได้ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับไฟล์ MS Project เวอร์ชันต่างๆ รวมถึงไฟล์ .mpp จาก MS Project 2003 ถึง MS Project 2019
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาการสนับสนุนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ได้ คุณสามารถซื้อใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถซื้อ Aspose.Tasks สำหรับ Java ได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
