---
title: อ่านข้อมูลตามช่วงเวลาสำหรับทรัพยากรใน Aspose.Tasks
linktitle: อ่านข้อมูลตามช่วงเวลาสำหรับทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีแยกข้อมูลตามช่วงเวลาจากทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ Java บทช่วยสอนทีละขั้นตอน
weight: 15
url: /th/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูลตามช่วงเวลาสำหรับทรัพยากรใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการอ่านข้อมูลตามช่วงเวลาสำหรับทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ Java ไลบรารีนี้มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการจัดการไฟล์ Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) และปฏิบัติตามคำแนะนำในการติดตั้ง
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จากไฟล์[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

## แพ็คเกจนำเข้า
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
ขั้นแรก ให้กำหนดไดเร็กทอรีที่มีไฟล์ MS Project ของคุณ
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: อ่านไฟล์เทมเพลตโครงการ MS
ระบุชื่อไฟล์เทมเพลต MS Project ของคุณ
```java
String fileName = "ResourceTimephasedData.mpp";
```
## ขั้นตอนที่ 3: อ่านไฟล์อินพุตเป็นโครงการ
อ่านไฟล์อินพุตโดยใช้ Aspose.Tasks และโหลดเป็นวัตถุ Project
```java
Project project = new Project(dataDir + fileName);
```
## ขั้นตอนที่ 4: รับทรัพยากรด้วย ID
ดึงทรัพยากรที่ต้องการจากโปรเจ็กต์ด้วยตัวระบุเฉพาะ (ID)
```java
Resource resource = project.getResources().getByUid(1);
```
## ขั้นตอนที่ 5: พิมพ์ข้อมูลตามช่วงเวลาสำหรับงานทรัพยากร
พิมพ์ข้อมูลตามช่วงเวลาสำหรับงานทรัพยากร
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## ขั้นตอนที่ 6: พิมพ์ข้อมูลตามช่วงเวลาสำหรับต้นทุนทรัพยากร
พิมพ์ข้อมูลตามช่วงเวลาสำหรับต้นทุนทรัพยากร
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอ่านข้อมูลตามช่วงเวลาสำหรับทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถดึงข้อมูลอันมีค่าจากไฟล์โปรเจ็กต์ของคุณโดยทางโปรแกรมได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการไฟล์โครงการประเภทอื่นนอกเหนือจาก Microsoft Project ได้หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์หลากหลายรูปแบบ รวมถึง MPP, XML และ CSV
### Aspose.Tasks เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ที่แตกต่างกันหรือไม่
ใช่ Aspose.Tasks เข้ากันได้กับ Java IDE และเฟรมเวิร์กหลักๆ ทั้งหมด
### ฉันสามารถจัดการข้อมูลโปรเจ็กต์โดยใช้ Aspose.Tasks ได้หรือไม่
แน่นอนว่า Aspose.Tasks มี API มากมายสำหรับการสร้าง แก้ไข และวิเคราะห์ข้อมูลโปรเจ็กต์
### Aspose.Tasks เหมาะสำหรับโครงการระดับองค์กรหรือไม่
ใช่ Aspose.Tasks ถูกนำมาใช้กันอย่างแพร่หลายในสภาพแวดล้อมขององค์กรเนื่องจากความน่าเชื่อถือและความสามารถในการปรับขยายได้
### ฉันจะรับการสนับสนุนได้ที่ไหนหากฉันประสบปัญหาขณะใช้งาน Aspose.Tasks
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือจากชุมชนและทีมสนับสนุน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
