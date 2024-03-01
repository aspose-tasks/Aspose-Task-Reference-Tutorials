---
title: สร้างข้อมูลตามช่วงเวลาใน Aspose.Tasks
linktitle: สร้างข้อมูลตามช่วงเวลาสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีสร้างข้อมูลตามช่วงเวลาสำหรับการมอบหมายทรัพยากรโดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงประสิทธิภาพการจัดการโครงการด้วยคำแนะนำที่ครอบคลุมนี้
type: docs
weight: 24
url: /th/java/resource-assignments/timephased-data-generation/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการสร้างข้อมูลตามช่วงเวลาสำหรับการกำหนดทรัพยากรโดยใช้ Aspose.Tasks สำหรับ Java ข้อมูลตามช่วงเวลาจะให้ข้อมูลเชิงลึกอันมีค่าเกี่ยวกับวิธีการจัดสรรทรัพยากรในช่วงเวลาหนึ่งภายในโครงการ ช่วยให้ผู้จัดการโครงการตัดสินใจได้อย่างมีข้อมูล
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks สำหรับไลบรารี Java: คุณต้องมี Aspose.Tasks สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## ขั้นตอนที่ 1: อ่านไฟล์ MPP ต้นฉบับ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
// อ่านไฟล์ MPP ต้นฉบับ
Project project = new Project(dataDir + "project.mpp");
```
## ขั้นตอนที่ 2: รับการมอบหมายงานและทรัพยากร
```java
// รับงานแรกของโครงการ
Task task = project.getRootTask().getChildren().getById(1);
// รับการมอบหมายทรัพยากรครั้งแรกของโครงการ
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## ขั้นตอนที่ 3: สร้างข้อมูลตามช่วงเวลาด้วย Flat Contour
```java
// เส้นชั้นความสูงแบบเรียบเป็นเส้นชั้นความสูงเริ่มต้น
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 4: เปลี่ยน Contour เป็น Turtle
```java
// เปลี่ยนรูปร่างเป็นเต่า
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 5: เปลี่ยน Contour เป็น BackLoaded
```java
// เปลี่ยนรูปร่างเป็น BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 6: เปลี่ยน Contour เป็น FrontLoaded
```java
// เปลี่ยนรูปร่างเป็น FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 7: เปลี่ยน Contour เป็น Bell
```java
// เปลี่ยนรูปร่างเป็นเบลล์
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 8: เปลี่ยน Contour เป็น EarlyPeak
```java
// เปลี่ยนรูปร่างเป็น EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 9: เปลี่ยน Contour เป็น LatePeak
```java
// เปลี่ยนรูปร่างเป็น LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## ขั้นตอนที่ 10: เปลี่ยน Contour เป็น DoublePeak
```java
// เปลี่ยนรูปร่างเป็น DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีการสร้างข้อมูลตามช่วงเวลาสำหรับการกำหนดทรัพยากรโดยใช้ Aspose.Tasks สำหรับ Java การทำความเข้าใจโครงร่างการทำงานที่แตกต่างกันสามารถช่วยให้ผู้จัดการโครงการจัดการการจัดสรรทรัพยากรและการจัดกำหนดการในโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks กับไลบรารี Java อื่นได้หรือไม่
ใช่ Aspose.Tasks สามารถรวมเข้ากับไลบรารี Java อื่นๆ เพื่อเพิ่มความสามารถในการจัดการโปรเจ็กต์ได้
### Aspose.Tasks เหมาะสำหรับโครงการระดับองค์กรขนาดใหญ่หรือไม่
แน่นอนว่า Aspose.Tasks ได้รับการออกแบบมาเพื่อรองรับโครงการทุกขนาด รวมถึงโครงการระดับองค์กรขนาดใหญ่ด้วย
### Aspose.Tasks ให้การสนับสนุนรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันหรือไม่
ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP, XML และ MPX
### ฉันสามารถปรับแต่งรูปทรงการทำงานตามความต้องการของโปรเจ็กต์ของฉันได้หรือไม่
ใช่ Aspose.Tasks อนุญาตให้ผู้ใช้กำหนดโครงร่างการทำงานแบบกำหนดเองเพื่อให้เหมาะกับความต้องการเฉพาะของโครงการ
### มีฟอรัมชุมชนที่ฉันสามารถขอความช่วยเหลือเกี่ยวกับ Aspose.Tasks ได้หรือไม่
 ใช่ คุณสามารถเยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปราย