---
title: อัตราการอ่านและเขียนสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
linktitle: อัตราการอ่านและเขียนสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการระดับอัตราการมอบหมายทรัพยากรอย่างมีประสิทธิภาพใน Aspose.Tasks for Java ด้วยบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 20
url: /th/java/resource-assignments/read-write-rate-scale/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการจัดการระดับอัตราการมอบหมายทรัพยากรโดยใช้ Aspose.Tasks สำหรับ Java ซึ่งเป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถจัดการการตั้งค่าระดับอัตราสำหรับการกำหนดทรัพยากรในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับฟังก์ชัน Aspose.Tasks 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการตั้งค่าโปรเจ็กต์ Java ของคุณและรวมไลบรารี Aspose.Tasks ในการขึ้นต่อกันของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
โหลดไฟล์โครงการที่คุณต้องการใช้งานลงในแอปพลิเคชัน Java ของคุณ
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## ขั้นตอนที่ 3: เพิ่มงาน
เพิ่มงานใหม่ในโครงการของคุณ
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## ขั้นตอนที่ 4: กำหนดทรัพยากร
กำหนดทรัพยากรวัสดุและไม่ใช่วัสดุ และระบุประเภท
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## ขั้นตอนที่ 5: กำหนดทรัพยากรให้กับงาน
มอบหมายทรัพยากรที่กำหนดไว้ก่อนหน้านี้ให้กับงานพร้อมกับประเภทระดับอัตรา
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## ขั้นตอนที่ 6: บันทึกโครงการ
บันทึกโครงการด้วยการกำหนดทรัพยากรที่แก้ไข
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## ขั้นตอนที่ 7: ดึงข้อมูลการมอบหมายทรัพยากร
โหลดโปรเจ็กต์ที่บันทึกไว้ซ้ำและเรียกข้อมูลการกำหนดทรัพยากรเพื่อตรวจสอบการตั้งค่าระดับอัตรา
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## บทสรุป
การจัดการระดับอัตราการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java เป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถจัดการการตั้งค่าระดับอัตราสำหรับการกำหนดทรัพยากรในแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับ Java IDE ใด ๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE หลักทั้งหมด รวมถึง IntelliJ IDEA, Eclipse และ NetBeans
### คำถามที่ 2: Aspose.Tasks รองรับไฟล์รูปแบบอื่นนอกเหนือจาก MPP หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์รูปแบบต่างๆ รวมถึง MPP, XML และ HTML
### คำถามที่ 3: Aspose.Tasks เหมาะสำหรับการจัดการโครงการระดับองค์กรหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks นำเสนอฟีเจอร์ที่ครอบคลุมสำหรับการจัดการโปรเจ็กต์ทุกขนาด ทำให้เหมาะสำหรับการจัดการโปรเจ็กต์ระดับองค์กร
### คำถามที่ 4: ฉันสามารถปรับแต่งการมอบหมายทรัพยากรให้เกินกว่าระดับอัตราได้หรือไม่
ตอบ: ใช่ Aspose.Tasks มอบความสามารถที่ครอบคลุมในการปรับแต่งการมอบหมายทรัพยากร รวมถึงการปรับต้นทุน งาน และระยะเวลา
### คำถามที่ 5: มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ตอบ: ได้ คุณสามารถค้นหาการสนับสนุนและโต้ตอบกับผู้ใช้รายอื่นได้ในฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).