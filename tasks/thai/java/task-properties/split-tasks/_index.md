---
title: แยกงานใน Aspose.Tasks
linktitle: แยกงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: การจัดการงานระดับปรมาจารย์ใน Java ด้วย Aspose.Tasks! เรียนรู้วิธีแบ่งงานอย่างมีประสิทธิภาพเพื่อปรับไทม์ไลน์ของโครงการให้เหมาะสม ดาวน์โหลดเดี๋ยวนี้!
weight: 29
url: /th/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แยกงานใน Aspose.Tasks

## การแนะนำ
คุณกำลังดิ้นรนกับการจัดการงานในโปรเจ็กต์ Java ของคุณหรือไม่? Aspose.Tasks for Java มอบโซลูชันอันทรงพลังสำหรับการแบ่งงานอย่างมีประสิทธิภาพ และเพิ่มขีดความสามารถในการจัดการโครงการ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการแบ่งงานโดยใช้ Aspose.Tasks สำหรับ Java ซึ่งช่วยให้คุณปรับไทม์ไลน์โปรเจ็กต์และการจัดสรรทรัพยากรให้เหมาะสม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  Aspose.Tasks สำหรับไลบรารี Java ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[Aspose.Tasks สำหรับเอกสาร Java](https://reference.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## ขั้นตอนที่ 1: สร้างโครงการใหม่
เริ่มต้นด้วยการสร้างโปรเจ็กต์ใหม่โดยใช้ไลบรารี Aspose.Tasks:
```java
// สร้างโครงการใหม่
Project splitTaskProject = new Project();
```
## ขั้นตอนที่ 2: ตั้งค่าปฏิทินโครงการ
ตั้งค่าปฏิทินของโครงการเพื่อสร้างไทม์ไลน์:
```java
// รับปฏิทินมาตรฐาน
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// ตั้งค่าปฏิทินของโครงการ
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (ต่อจากตัวอย่าง)
```
## ขั้นตอนที่ 3: เพิ่มงานรูท
เพิ่มงานรูทให้กับโปรเจ็กต์ของคุณ:
```java
// งานรูท
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## ขั้นตอนที่ 4: เพิ่มงานใหม่เพื่อแยก
เพิ่มงานใหม่ในโครงการของคุณที่คุณต้องการแยก:
```java
// เพิ่มงานใหม่
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## ขั้นตอนที่ 5: สร้างการมอบหมายทรัพยากร
สร้างการมอบหมายทรัพยากรใหม่สำหรับงาน:
```java
// สร้างการมอบหมายทรัพยากรใหม่
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## ขั้นตอนที่ 6: สร้างข้อมูลตามช่วงเวลา
สร้างข้อมูลตามระยะเวลาของการมอบหมายทรัพยากร:
```java
// สร้างข้อมูลตามระยะเวลาการมอบหมายทรัพยากร
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## ขั้นตอนที่ 7: แบ่งงาน
แบ่งงานออกเป็นหลายส่วน:
```java
// แบ่งงานออกเป็น 3 ส่วน
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (ต่อจากตัวอย่าง)
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแบ่งงานโดยใช้ Aspose.Tasks สำหรับ Java เรียบร้อยแล้ว ไลบรารีอันทรงพลังนี้ช่วยลดความยุ่งยากในการจัดการงานในโปรเจ็กต์ Java โดยมอบโซลูชั่นที่มีประสิทธิภาพสำหรับการปรับไทม์ไลน์ของโปรเจ็กต์และการจัดสรรทรัพยากรให้เหมาะสม
## คำถามที่พบบ่อย
### ฉันสามารถแบ่งงานที่มีระยะเวลาต่างกันได้หรือไม่
ได้ คุณสามารถปรับระยะเวลาของงานได้ตามความต้องการของโครงการ
### Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java เวอร์ชันทั้งหมดหรือไม่
Aspose.Tasks for Java ได้รับการออกแบบมาให้ทำงานร่วมกับ Java เวอร์ชันต่างๆ ได้อย่างราบรื่น จึงมั่นใจได้ถึงความเข้ากันได้
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java ได้ฟรีหรือไม่
Aspose.Tasks for Java ให้ทดลองใช้ฟรี ช่วยให้คุณสามารถสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 เยี่ยมชม[Aspose.Tasks สำหรับฟอรัมสนับสนุน Java](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือและเชื่อมต่อกับชุมชน
### ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบและประเมินผล
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
