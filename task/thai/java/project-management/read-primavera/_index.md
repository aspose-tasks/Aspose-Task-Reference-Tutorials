---
title: อ่าน MS Project จาก Primavera ด้วย Aspose.Tasks สำหรับ Java
linktitle: อ่านโครงการจาก Primavera ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอ่านไฟล์ MS Project จาก Primavera XML ได้อย่างราบรื่นโดยใช้ Aspose.Tasks สำหรับ Java เพิ่มประสิทธิภาพการจัดการโครงการของคุณ
type: docs
weight: 20
url: /th/java/project-management/read-primavera/
---
## การแนะนำ
ในการจัดการโครงการ การทำงานร่วมกันระหว่างแพลตฟอร์มซอฟต์แวร์ที่แตกต่างกันเป็นสิ่งสำคัญสำหรับขั้นตอนการทำงานที่ราบรื่น Aspose.Tasks สำหรับ Java มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการอ่านไฟล์ Microsoft Project จาก Primavera XML บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการอ่านไฟล์ MS Project จาก Primavera โดยใช้ Aspose.Tasks สำหรับ Java ซึ่งช่วยให้คุณสามารถตรวจสอบคุณสมบัติเฉพาะของ Primavera ของงานได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Data Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีข้อมูลของคุณ
## ขั้นตอนที่ 2: อ่านโครงการจาก Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 ให้แน่ใจว่าจะเปลี่ยน`"PrimaveraProject.xml"` ด้วยชื่อจริงของไฟล์ Primavera XML ของคุณ
## ขั้นตอนที่ 3: วนซ้ำงานและรับคุณสมบัติเฉพาะของ Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
โค้ดนี้จะวนซ้ำแต่ละงานในโครงการ โดยพิมพ์คุณสมบัติเฉพาะของ Primavera ที่เกี่ยวข้อง

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีอ่านไฟล์ MS Project จาก Primavera XML โดยใช้ Aspose.Tasks สำหรับ Java ฟังก์ชันการทำงานนี้ช่วยให้สามารถบูรณาการและวิเคราะห์ข้อมูลโครงการบนแพลตฟอร์มต่างๆ ได้อย่างราบรื่น ช่วยเพิ่มประสิทธิภาพการจัดการโครงการโดยรวม
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถแก้ไขคุณสมบัติเฉพาะของ Primavera ของงานโดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks for Java มี API เพื่อแก้ไขคุณสมบัติเฉพาะของ Primavera ของงานตามต้องการ
### ถาม: Aspose.Tasks สำหรับ Java รองรับการอ่านไฟล์โปรเจ็กต์รูปแบบอื่นหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับการอ่านไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP, XML และ Primavera XML
### ถาม: Aspose.Tasks สำหรับ Java เหมาะสำหรับแอปพลิเคชันการจัดการโครงการระดับองค์กรหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ Java นำเสนอฟีเจอร์ที่แข็งแกร่งและความสามารถในการปรับขนาดได้ ทำให้เหมาะสำหรับแอปพลิเคชันการจัดการโครงการระดับองค์กร
### ถาม: ฉันสามารถดึงข้อมูลทรัพยากรจากโปรเจ็กต์ Primavera โดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ Java ช่วยให้คุณสามารถดึงข้อมูลทรัพยากรพร้อมกับรายละเอียดงานจากโปรเจ็กต์ Primavera ได้
### ถาม: ฉันจะขอรับการสนับสนุนหรือเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาเอกสารที่ครอบคลุมและเข้าถึงฟอรัมเพื่อรับการสนับสนุนได้ที่[Aspose.Tasks สำหรับเอกสาร Java](https://reference.aspose.com/tasks/java/) หน้าหนังสือ.