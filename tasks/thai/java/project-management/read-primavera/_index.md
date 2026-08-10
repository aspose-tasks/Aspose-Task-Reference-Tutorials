---
date: 2026-04-24
description: เรียนรู้วิธีใช้ Aspose.Tasks Java เพื่อนำเข้า Primavera XML ไปยัง MS
  Project เพื่อให้การแลกเปลี่ยนข้อมูลเป็นไปอย่างราบรื่นและการจัดการโครงการดีขึ้น
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: อ่านโครงการจาก Primavera ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – อ่านไฟล์ XML ของ Primavera ไปยัง MS Project
url: /th/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่าน MS Project จาก Primavera ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในโลกการจัดการโครงการที่เคลื่อนที่อย่างรวดเร็วในวันนี้ คุณมักต้องย้ายกำหนดการระหว่าง Primavera P6 และ Microsoft Project โดยไม่สูญเสียรายละเอียดใด ๆ คู่มือฉบับนี้แสดง **วิธีอ่านไฟล์ Primavera XML** และนำเข้าไปยัง MS Project ด้วย **aspose tasks java** เมื่อจบคู่มือคุณจะสามารถดึงคุณสมบัติงานที่เฉพาะของ Primavera ไปยังแอปพลิเคชัน Java ได้ ทำให้คุณมีแหล่งข้อมูลเดียวสำหรับการวิเคราะห์ รายงาน หรือการทำอัตโนมัติต่อไป

## คำตอบอย่างรวดเร็ว
- **Aspose.Tasks for Java ทำอะไร?** มันอ่านและเขียนรูปแบบไฟล์โครงการหลายประเภท รวมถึง Primavera XML และ Microsoft Project (MPP).  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีสามารถใช้เพื่อประเมินผลได้; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **รองรับเวอร์ชัน Java ใด?** จำเป็นต้องใช้ Java 8 หรือสูงกว่า.  
- **สามารถนำเข้ารูปแบบอื่น ๆ นอกจาก Primavera XML ได้หรือไม่?** ได้, aspose tasks java ยังรองรับ MPP, XML, และรูปแบบอื่น ๆ อีกมาก.  
- **วิธีนี้เหมาะกับโครงการระดับองค์กรขนาดใหญ่หรือไม่?** แน่นอน—Aspose.Tasks ถูกออกแบบมาสำหรับสถานการณ์ที่ต้องการประสิทธิภาพสูงและระดับองค์กร.  

## aspose tasks java – การอ่าน Primavera XML
การอ่าน Primavera XML หมายถึงการแยกวิเคราะห์ไฟล์ XML ที่ส่งออกจาก Oracle Primavera P6 เพื่อดึงข้อมูลกำหนดการโครงการ เช่น งาน, ระยะเวลา, ทรัพยากร, และคุณลักษณะเฉพาะของ Primavera เพื่อให้สามารถนำไปใช้กับเครื่องมืออื่น ๆ เช่น Microsoft Project.

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java เพื่ออ่าน Primavera XML?
- **ความสมบูรณ์แบบเต็มรูปแบบ:** คุณสมบัติเฉพาะของ Primavera ทั้งหมดจะถูกเก็บรักษา.  
- **ไม่มีการพึ่งพาภายนอก:** ไลบรารี Java แท้ ๆ ไม่ต้องติดตั้ง Primavera หรือ MS Project.  
- **ขยายได้:** จัดการโครงการขนาดใหญ่ที่มีงานหลายพันรายการได้อย่างมีประสิทธิภาพ.  
- **ข้ามแพลตฟอร์ม:** ทำงานบน Windows, Linux, และ macOS.  

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. **Java Development Kit (JDK)** – ติดตั้ง Java 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/java/).  
3. ไฟล์ Primavera XML (เช่น `PrimaveraProject.xml`) ที่คุณต้องการอ่าน.  

## วิธีอ่านไฟล์โครงการ java ด้วย Aspose.Tasks?
ด้านล่างเป็นคู่มือขั้นตอนต่อขั้นตอนที่พาคุณผ่านกระบวนการทั้งหมด.

### นำเข้าแพ็กเกจ
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มที่ไฟล์ Primavera XML ของคุณอยู่.

### ขั้นตอนที่ 2: อ่านโครงการจาก Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
อัปเดต `"PrimaveraProject.xml"` ด้วยชื่อไฟล์จริงของการส่งออก Primavera ของคุณ.

### ขั้นตอนที่ 3: วนผ่านงานและดึงคุณสมบัติที่เฉพาะของ Primavera
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
ลูปนี้จะแสดงรายละเอียดเฉพาะของ Primavera สำหรับแต่ละงาน เช่น Activity ID, ลำดับ WBS, ประเภทระยะเวลา, การแยกค่าใช้จ่าย, และอื่น ๆ.

## ปัญหาทั่วไปและวิธีแก้
- **ข้อผิดพลาดไฟล์ไม่พบ:** ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) และชื่อไฟล์ XML ถูกต้อง.  
- **คุณสมบัติ Primavera ขาดหาย:** ตรวจสอบว่า XML ถูกส่งออกพร้อมฟิลด์ที่จำเป็นทั้งหมด; รุ่น Primavera เก่าบางรุ่นอาจละเว้นบางคุณลักษณะ.  
- **ประสิทธิภาพกับไฟล์ขนาดใหญ่:** พิจารณาเพิ่มขนาด heap ของ JVM (`-Xmx2g` หรือสูงกว่า) สำหรับโครงการที่มีงานหลายหมื่นรายการ.  

## คำถามที่พบบ่อย
### Q: ฉันสามารถแก้ไขคุณสมบัติเฉพาะของ Primavera สำหรับงานโดยใช้ Aspose.Tasks for Java ได้หรือไม่?
A: ได้, Aspose.Tasks for Java มี API เพื่อแก้ไขคุณสมบัติเฉพาะของ Primavera สำหรับงานตามความต้องการ.

### Q: Aspose.Tasks for Java รองรับการอ่านรูปแบบไฟล์โครงการอื่น ๆ หรือไม่?
A: ได้, Aspose.Tasks for Java รองรับการอ่านรูปแบบไฟล์โครงการต่าง ๆ รวมถึง MPP, XML, และ Primavera XML.

### Q: Aspose.Tasks for Java เหมาะกับแอปพลิเคชันการจัดการโครงการระดับองค์กรหรือไม่?
A: แน่นอน, Aspose.Tasks for Java มีคุณลักษณะที่แข็งแกร่งและสามารถขยายได้ ทำให้เหมาะกับแอปพลิเคชันการจัดการโครงการระดับองค์กร.

### Q: ฉันสามารถดึงข้อมูลทรัพยากรจากโครงการ Primavera ด้วย Aspose.Tasks for Java ได้หรือไม่?
A: ได้, Aspose.Tasks for Java อนุญาตให้คุณดึงข้อมูลทรัพยากรร่วมกับรายละเอียดงานจากโครงการ Primavera.

### Q: ฉันจะหาเอกสารหรือการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
A: คุณสามารถค้นหาเอกสารฉบับเต็มและเข้าถึงฟอรั่มสนับสนุนได้ที่หน้า [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).  

## สรุป
คุณได้เรียนรู้ **วิธีอ่านไฟล์ primavera xml** และดึงข้อมูลงานอย่างละเอียดเข้าสู่แอปพลิเคชัน Java ด้วย **aspose tasks java** ความสามารถนี้เชื่อมช่องว่างระหว่าง Primavera และ Microsoft Project ให้คุณมองเห็นข้อมูลครบถ้วนข้ามแพลตฟอร์มและเพิ่มประสิทธิภาพการจัดการโครงการโดยรวม

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}