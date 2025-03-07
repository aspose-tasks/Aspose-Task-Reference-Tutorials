---
title: ข้อมูลแบ่งตามระยะเวลาของงานใน Aspose.Tasks
linktitle: ข้อมูลแบ่งตามระยะเวลาของงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจ Aspose.Tasks สำหรับ Java และการจัดการข้อมูลตามระยะของงานหลัก ดาวน์โหลดไลบรารี เพลิดเพลินกับการทดลองใช้ฟรี และปรับปรุงการติดตามโปรเจ็กต์ของคุณ
weight: 34
url: /th/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ข้อมูลแบ่งตามระยะเวลาของงานใน Aspose.Tasks

## การแนะนำ
ในขอบเขตของการจัดการโครงการ การติดตามข้อมูลตามระยะเวลาของงานอย่างแม่นยำถือเป็นสิ่งสำคัญสำหรับการดำเนินโครงการอย่างมีประสิทธิภาพ Aspose.Tasks สำหรับ Java กลายเป็นเครื่องมือที่มีประสิทธิภาพในการปรับปรุงกระบวนการนี้ โดยนำเสนอคุณสมบัติที่แข็งแกร่งและความยืดหยุ่น บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการใช้ Aspose.Tasks สำหรับ Java เพื่อจัดการข้อมูลตามระยะเวลาของงานอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
-  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks ในโปรเจ็กต์ของคุณ คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/java/).
- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีสำหรับเอกสารโครงการของคุณ
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## ขั้นตอนที่ 1: กำหนดวันที่เริ่มต้นโครงการ
```java
Project project = new Project(dataDir + "project.xml");
// รหัสเพิ่มเติมสำหรับการนำเข้าแพ็คเกจ
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
คำอธิบาย: เตรียมใช้งานวัตถุปฏิทิน กำหนดวันที่เริ่มต้น และนำไปใช้กับโปรเจ็กต์
## ขั้นตอนที่ 2: กำหนดงานและทรัพยากร
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
คำอธิบาย: สร้างงานและทรัพยากร การกำหนดอัตราสำหรับมาตรฐานและค่าล่วงเวลา
## ขั้นตอนที่ 3: กำหนดระยะเวลาของงาน
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
คำอธิบาย: กำหนดระยะเวลาของงาน (เช่น 6 วัน)
## ขั้นตอนที่ 4: กำหนดทรัพยากรให้กับงาน
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
คำอธิบาย: กำหนดทรัพยากรให้กับงาน
## ขั้นตอนที่ 5: กำหนดค่าการกำหนดทรัพยากร
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
คำอธิบาย: ตั้งค่าพารามิเตอร์ เช่น หยุด ดำเนินการต่อ และโครงร่างการทำงานสำหรับการกำหนดทรัพยากร
## ขั้นตอนที่ 6: ตั้งค่าพื้นฐาน
```java
project.setBaseline(BaselineType.Baseline);
```
คำอธิบาย: สร้างพื้นฐานสำหรับโครงการ
## ขั้นตอนที่ 7: อัปเดตความสมบูรณ์ของงาน
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
คำอธิบาย: ระบุเปอร์เซ็นต์ความสำเร็จของงาน
## ขั้นตอนที่ 8: ดึงข้อมูลตามระยะเวลา
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
คำอธิบาย: ดึงข้อมูลตามช่วงเวลาสำหรับงานที่เหลืออยู่ที่ได้รับมอบหมาย
## ขั้นตอนที่ 9: แสดงข้อมูลตามช่วงเวลา
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// รหัสเพิ่มเติมสำหรับการแสดงค่าอื่นๆ
```
คำอธิบาย: ส่งออกและแสดงข้อมูลตามช่วงเวลา
## บทสรุป
การจัดการข้อมูลตามระยะเวลาของงานอย่างมีประสิทธิภาพเป็นสิ่งที่ขาดไม่ได้สำหรับความสำเร็จของโครงการ Aspose.Tasks สำหรับ Java ทำให้กระบวนการนี้ง่ายขึ้น โดยมีชุดฟังก์ชันการทำงานที่ครอบคลุม เมื่อทำตามบทช่วยสอนนี้ คุณจะสามารถผสานรวม Aspose.Tasks เข้ากับโปรเจ็กต์ Java ของคุณได้อย่างราบรื่น ทำให้มั่นใจในการควบคุมไทม์ไลน์ของโปรเจ็กต์และการจัดสรรทรัพยากรได้อย่างแม่นยำ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java ในโปรเจ็กต์ Java ใดๆ ได้หรือไม่
ตอบ: ได้ Aspose.Tasks for Java เข้ากันได้กับโปรเจ็กต์ที่ใช้ Java ใดๆ
### ถาม: ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปราย
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถซื้อ Aspose.Tasks สำหรับ Java ได้[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
