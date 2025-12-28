---
date: 2025-12-28
description: เรียนรู้วิธีการอ่านไฟล์ XML ของ Primavera ไปยัง MS Project ด้วย Aspose.Tasks
  for Java เพื่อให้การแลกเปลี่ยนข้อมูลเป็นไปอย่างราบรื่นและการจัดการโครงการดีขึ้น
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่านไฟล์ XML ของ Primavera ไปยัง MS Project ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่าน MS Project จาก Primavera ด้วย Aspose.Tasks for Java

## บทนำ
ในการจัดการโครงการสมัยใหม่ การย้ายข้อมูลระหว่างเครื่องมือโดยไม่สูญเสียรายละเอียดเป็นสิ่งสำคัญ บทเรียนนี้จะแสดงให้คุณ **วิธีอ่านไฟล์ primavera xml** และนำเข้าไปยัง Microsoft Project ด้วย Aspose.Tasks for Java เมื่อเสร็จแล้ว คุณจะสามารถดึงคุณสมบัติงานเฉพาะของ Primavera ออกมา ทำให้การวิเคราะห์ข้ามแพลตฟอร์มเป็นเรื่องง่ายและมีประสิทธิภาพ

## คำตอบอย่างรวดเร็ว
- **Aspose.Tasks for Java ทำอะไรได้บ้าง?** มันสามารถอ่านและเขียนไฟล์โครงการหลายรูปแบบ รวมถึง Primavera XML และ Microsoft Project (MPP)  
- **ต้องใช้ไลเซนส์หรือไม่?** มีรุ่นทดลองฟรีสำหรับการประเมินผล; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมจริง  
- **รองรับเวอร์ชัน Java ใด?** ต้องใช้ Java 8 หรือสูงกว่า  
- **สามารถอ่านรูปแบบอื่นนอกจาก Primavera XML ได้หรือไม่?** ได้, Aspose.Tasks รองรับ MPP, XML และรูปแบบอื่น ๆ อีกมากมาย  
- **วิธีนี้เหมาะกับโครงการระดับองค์กรขนาดใหญ่หรือไม่?** แน่นอน—Aspose.Tasks ถูกออกแบบมาสำหรับสถานการณ์ระดับองค์กรที่ต้องการประสิทธิภาพสูง

## Primavera XML คืออะไร?
การอ่าน Primavera XML หมายถึงการแยกวิเคราะห์ไฟล์ XML ที่ส่งออกจาก Oracle Primavera P6 เพื่อดึงข้อมูลกำหนดการโครงการ—งาน, ระยะเวลา, ทรัพยากร, และคุณสมบัติเฉพาะของ Primavera—เพื่อให้เครื่องมืออื่น ๆ เช่น Microsoft Project สามารถนำไปใช้ได้

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่ออ่าน Primavera XML?
- **ความสมบูรณ์แบบเต็มรูปแบบ:** คุณสมบัติเฉพาะของ Primavera ทั้งหมดจะถูกเก็บรักษาไว้  
- **ไม่มีการพึ่งพาไลบรารีภายนอก:** เป็นไลบรารี Java แท้ ๆ ไม่ต้องติดตั้ง Primavera หรือ MS Project  
- **ขยายขนาดได้:** จัดการโครงการขนาดใหญ่ที่มีงานหลายพันรายการได้อย่างมีประสิทธิภาพ  
- **ข้ามแพลตฟอร์ม:** ทำงานบน Windows, Linux, และ macOS

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. **Java Development Kit (JDK)** – ติดตั้ง Java 8 หรือใหม่กว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/)  
3. ไฟล์ Primavera XML (เช่น `PrimaveraProject.xml`) ที่ต้องการอ่าน

## วิธีอ่านไฟล์โครงการด้วย Java และ Aspose.Tasks?
ต่อไปนี้เป็นคำแนะนำแบบขั้นตอนที่พาคุณผ่านกระบวนการทั้งหมด

### นำเข้าแพ็กเกจ
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์ข้อมูล
```java
String dataDir = "Your Data Directory";
```
เปลี่ยน `"Your Data Directory"` ให้เป็นเส้นทางเต็มที่ไฟล์ Primavera XML ของคุณอยู่

### ขั้นตอนที่ 2: อ่านโครงการจาก Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
อัปเดต `"PrimaveraProject.xml"` ให้เป็นชื่อไฟล์ที่คุณส่งออกจาก Primavera จริง

### ขั้นตอนที่ 3: วนลูปผ่านงานและดึงคุณสมบัติเฉพาะของ Primavera
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
ลูปนี้จะแสดงรายละเอียดเฉพาะของแต่ละงาน เช่น Activity ID, ลำดับ WBS, ประเภทระยะเวลา, การแยกค่าใช้จ่าย ฯลฯ

## ปัญหาที่พบบ่อยและวิธีแก้
- **ข้อผิดพลาดไฟล์ไม่พบ:** ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) และชื่อไฟล์ XML ถูกต้อง  
- **คุณสมบัติ Primavera หาย:** ตรวจสอบว่าไฟล์ XML ถูกส่งออกพร้อมฟิลด์ที่ต้องการ; เวอร์ชัน Primavera เก่าบางรุ่นอาจไม่รวมคุณสมบัติบางอย่าง  
- **ประสิทธิภาพเมื่อไฟล์ใหญ่:** พิจารณาเพิ่มขนาด heap ของ JVM (`-Xmx2g` หรือมากกว่า) สำหรับโครงการที่มีงานหลายหมื่นรายการ

## คำถามที่พบบ่อย
### Q: สามารถแก้ไขคุณสมบัติเฉพาะของงาน Primavera ด้วย Aspose.Tasks for Java ได้หรือไม่?
A: ได้, Aspose.Tasks for Java มี API ให้แก้ไขคุณสมบัติเฉพาะของงาน Primavera ตามต้องการ

### Q: Aspose.Tasks for Java รองรับการอ่านรูปแบบไฟล์โครงการอื่น ๆ หรือไม่?
A: ได้, Aspose.Tasks for Java รองรับการอ่านไฟล์โครงการหลายรูปแบบรวมถึง MPP, XML, และ Primavera XML

### Q: Aspose.Tasks for Java เหมาะกับแอปพลิเคชันการจัดการโครงการระดับองค์กรหรือไม่?
A: แน่นอน, Aspose.Tasks for Java มีฟีเจอร์และความสามารถในการขยายขนาดที่ทำให้เหมาะกับการใช้งานระดับองค์กร

### Q: สามารถดึงข้อมูลทรัพยากรจากโครงการ Primavera ด้วย Aspose.Tasks for Java ได้หรือไม่?
A: ได้, Aspose.Tasks for Java สามารถดึงข้อมูลทรัพยากรร่วมกับรายละเอียดงานจากโครงการ Primavera

### Q: จะหาเอกสารหรือการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
A: คุณสามารถดูเอกสารฉบับเต็มและเข้าถึงฟอรั่มสนับสนุนได้ที่หน้า [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)

## สรุป
คุณได้เรียนรู้ **วิธีอ่านไฟล์ primavera xml** และดึงข้อมูลงานละเอียดเข้าสู่แอปพลิเคชัน Java ด้วย Aspose.Tasks ความสามารถนี้ช่วยเชื่อมช่องว่างระหว่าง Primavera และ Microsoft Project ให้คุณมองเห็นข้อมูลข้ามแพลตฟอร์มได้อย่างครบถ้วนและเพิ่มประสิทธิภาพการจัดการโครงการโดยรวม

---

**อัปเดตล่าสุด:** 2025-12-28  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}