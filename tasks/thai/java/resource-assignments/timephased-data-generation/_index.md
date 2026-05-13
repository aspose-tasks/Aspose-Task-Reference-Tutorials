---
date: 2026-01-10
description: เรียนรู้วิธีเปลี่ยนคอนทัวร์และสร้างข้อมูลตามช่วงเวลาเพื่อการมอบหมายทรัพยากรโดยใช้
  Aspose.Tasks สำหรับ Java เพื่อปรับปรุงประสิทธิภาพการจัดการโครงการ.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีเปลี่ยนคอนทัวร์ใน Aspose.Tasks สำหรับข้อมูลตามช่วงเวลา
url: /th/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเปลี่ยนคอนทัวร์ใน Aspose.Tasks สำหรับข้อมูลแบบ Timephased

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีเปลี่ยนคอนทัวร์** สำหรับการมอบหมายทรัพยากรและสร้างข้อมูลแบบ Timephased ด้วย Aspose.Tasks for Java ข้อมูลแบบ Timephased จะเปิดเผยการกระจายงานตลอดช่วงเวลาโครงการ ช่วยให้คุณปรับกำหนดการให้แม่นยำ สมดุลภาระงาน และตัดสินใจบนพื้นฐานข้อมูล

## คำตอบสั้น
- **คอนทัวร์คืออะไร?** คอนทัวร์ของงานกำหนดว่าความพยายามจะกระจายอย่างไรตลอดระยะเวลาของงาน (เช่น Flat, Turtle, Bell)  
- **ทำไมต้องเปลี่ยนคอนทัวร์?** เพื่อสะท้อนรูปแบบการทำงานที่เป็นจริง เช่น การทำงานหนักในช่วงต้นหรือปลายของโครงการ  
- **ต้องใช้ไลบรารีใด?** Aspose.Tasks for Java (เวอร์ชันล่าสุดใดก็ได้)  
- **ต้องมีลิขสิทธิ์หรือไม่?** ใช่ ต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **สามารถดูผลลัพธ์ในคอนโซลได้หรือไม่?** ตัวอย่างจะพิมพ์วันที่เริ่มต้นและค่าของแต่ละช่วง Timephased

## “วิธีเปลี่ยนคอนทัวร์” คืออะไร?
การเปลี่ยนคอนทัวร์หมายถึงการอัปเดตคุณสมบัติ `WORK_CONTOUR` ของ `ResourceAssignment` Aspose.Tasks รองรับคอนทัวร์ที่กำหนดไว้ล่วงหน้าหลายแบบ (Flat, Turtle, Bell ฯลฯ) ซึ่งมีผลต่อการจัดสรรงานตามเวลา

## ทำไมต้องใช้ Aspose.Tasks เพื่อสร้างข้อมูลแบบ Timephased?
- **รายงานที่แม่นยำ:** ส่งออกการกระจายงานที่แม่นยำสำหรับเครื่องมือรายงาน  
- **การวางแผนสถานการณ์:** ทดสอบคอนทัวร์ต่าง ๆ โดยไม่ต้องแก้ไขกำหนดการต้นฉบับ  
- **อัตโนมัติ:** ผสานรวมกับ pipeline CI เพื่อประเมินสุขภาพโครงการโดยอัตโนมัติ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบว่ามี JDK ติดตั้งบนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก [ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)  
2. Aspose.Tasks for Java Library: คุณต้องมีไลบรารี Aspose.Tasks for Java สามารถดาวน์โหลดได้จาก [เว็บไซต์](https://releases.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
ก่อนอื่น ให้เรานำเข้าแพ็กเกจที่จำเป็นสำหรับทำงานกับ Aspose.Tasks:
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
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 2: รับ Task และ Resource Assignment
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## วิธีเปลี่ยนคอนทัวร์ – Flat (ค่าเริ่มต้น)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **คอนทัวร์ไม่อัปเดต?** ตรวจสอบให้แน่ใจว่าคุณเรียก `firstRA.set(Asn.WORK_CONTOUR, …)` *ก่อน* ดึงข้อมูล Timephased  
- **ค่าที่ได้ไม่คาดคิด?** ยืนยันว่าค่า start และ finish ของงานถูกตั้งค่าอย่างถูกต้องในไฟล์ MPP ต้นฉบับ  
- **เคล็ดลับด้านประสิทธิภาพ:** ใช้ instance ของ `Project` เดียวกันเมื่อตรวจสอบหลายคอนทัวร์ เพื่อลดการอ่าน/เขียนไฟล์ที่ไม่จำเป็น

## คำถามที่พบบ่อย
### สามารถใช้ Aspose.Tasks ร่วมกับไลบรารี Java อื่นได้หรือไม่?
ได้, Aspose.Tasks สามารถผสานรวมกับไลบรารี Java อื่นเพื่อเพิ่มความสามารถในการจัดการโครงการ

### Aspose.Tasks เหมาะกับโครงการระดับองค์กรขนาดใหญ่หรือไม่?
แน่นอน, Aspose.Tasks ถูกออกแบบให้รองรับโครงการทุกขนาด รวมถึงโครงการระดับองค์กรขนาดใหญ่

### Aspose.Tasks รองรับรูปแบบไฟล์โครงการต่าง ๆ หรือไม่?
ใช่, Aspose.Tasks รองรับหลายรูปแบบ เช่น MPP, XML, และ MPX

### สามารถกำหนดคอนทัวร์งานแบบกำหนดเองตามความต้องการของโครงการได้หรือไม่?
ได้, คุณสามารถสร้างคอนทัวร์งานแบบกำหนดเองเพื่อให้ตรงกับความต้องการการกำหนดเวลาเฉพาะ

### มีฟอรั่มชุมชนที่สามารถขอความช่วยเหลือเกี่ยวกับ Aspose.Tasks ได้หรือไม่?
มี, คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนและการสนทนาต่าง ๆ

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบด้วย:** Aspose.Tasks for Java (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}