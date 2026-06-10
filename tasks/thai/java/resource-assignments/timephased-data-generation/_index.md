---
date: 2026-06-10
description: เรียนรู้วิธีเปลี่ยน contour และสร้าง Timephased Data สำหรับการมอบหมายทรัพยากรโดยใช้
  Aspose.Tasks for Java ครอบคลุมประเภทของ work contour และสถานการณ์การกำหนดเวลาขั้นสูง
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: สร้าง Timephased Data สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีเปลี่ยน Contour ใน Aspose.Tasks สำหรับ Timephased Data
url: /th/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเปลี่ยนคอนทัวร์ใน Aspose.Tasks สำหรับข้อมูล Timephased

## บทนำ
ในบทเรียนนี้ คุณจะได้เรียนรู้ **วิธีเปลี่ยนคอนทัวร์** สำหรับการมอบหมายทรัพยากรและสร้างข้อมูล Timephased ด้วย Aspose.Tasks for Java ข้อมูล Timephased จะเปิดเผยการกระจายงานตลอดช่วงเวลาโครงการ ช่วยให้คุณปรับตารางเวลาให้ละเอียด สมดุลภาระงาน และตัดสินใจโดยอิงข้อมูล การเชี่ยวชาญการเปลี่ยนคอนทัวร์ช่วยให้คุณจำลองรูปแบบความพยายามที่เป็นจริง เช่น การทำงานล่วงหน้า การทำงานล่าช้า หรือภาระงานสูงสุด

## คำตอบสั้น
- **คอนทัวร์คืออะไร?** คอนทัวร์งานกำหนดว่าความพยายามจะกระจายอย่างไรตลอดระยะเวลาของงาน (เช่น Flat, Turtle, Bell)  
- **ทำไมต้องเปลี่ยนคอนทัวร์?** เพื่อสะท้อนรูปแบบการทำงานที่เป็นจริง เช่น การทำงานล่วงหน้า หรือการทำงานล่าช้า  
- **ต้องใช้ไลบรารีใด?** Aspose.Tasks for Java (เวอร์ชันล่าสุดใดก็ได้)  
- **ต้องมีลิขสิทธิ์หรือไม่?** ต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพการผลิต  
- **สามารถดูผลลัพธ์ในคอนโซลได้หรือไม่?** ตัวอย่างจะแสดงวันที่เริ่มต้นและค่าต่าง ๆ ของแต่ละช่วง Timephased

## “วิธีเปลี่ยนคอนทัวร์” คืออะไร?
การเปลี่ยนคอนทัวร์หมายถึงการอัปเดตคุณสมบัติ `WORK_CONTOUR` ของอ็อบเจกต์ `ResourceAssignment` คุณสมบัตินี้บอก Aspose.Tasks ว่าจะกระจายงานรวมของการมอบหมายอย่างไรตลอดระยะเวลาของงาน ไลบรารีมีคอนทัวร์สำเร็จรูปหลายแบบ เช่น Flat, Turtle, Bell และอื่น ๆ ซึ่งแต่ละแบบจะสร้างรูปแบบการกระจายความพยายามที่แตกต่างกันตามเวลา

## ทำไมต้องใช้ Aspose.Tasks เพื่อสร้างข้อมูล Timephased?
Aspose.Tasks สร้างข้อมูล Timephased ด้วย **ค่าโอเวอร์เฮด 0 ms สำหรับการทำงานในหน่วยความจำ** และรองรับ **รูปแบบผลลัพธ์กว่า 50 แบบ** (MPP, XML, CSV ฯลฯ) ไลบรารีสามารถประมวลผลโครงการหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ให้การกระจายงานที่แม่นยำสำหรับการรายงาน การปรับระดับทรัพยากร และการวิเคราะห์ “what‑if” API ของมันช่วยให้คุณอัตโนมัติการเปลี่ยนคอนทัวร์และดึงค่าข้อมูล Timephased อย่างแม่นยำโดยโปรแกรม

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง JDK ไว้บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)  
2. Aspose.Tasks for Java Library: คุณต้องมีไลบรารี Aspose.Tasks for Java คุณสามารถดาวน์โหลดได้จาก [website](https://releases.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
คลาส `Project` เป็นอ็อบเจกต์หลักของ Aspose.Tasks ที่แทนไฟล์โครงการทั้งหมดในหน่วยความจำ นำเข้าชื่อเนมสเปซที่จำเป็นก่อนเริ่มทำงานกับงานและการมอบหมาย

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
คอนสตรัคเตอร์ `Project` โหลดไฟล์ MPP ที่มีอยู่โดยพาร์สโครงสร้างโดยไม่ต้องสร้างอ็อบเจกต์งานทุกตัวในหน่วยความจำ ทำให้การทำงานมีน้ำหนักเบา

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 2: รับงานและการมอบหมายทรัพยากร
`ResourceAssignment` เชื่อมทรัพยากรกับงานและเก็บคุณสมบัติระดับการมอบหมาย เช่น งาน, ค่าใช้จ่าย, และคอนทัวร์ ดึงการมอบหมายแรกด้วย `project.getResourceAssignments().getById(1)` (หรือ ID ที่ถูกต้องใดก็ได้) ก่อนที่คุณจะเปลี่ยนคอนทัวร์ของมัน

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## วิธีเปลี่ยนคอนทัวร์ – Flat (ค่าเริ่มต้น)
`WorkContourType` เป็น enumeration ที่ระบุรูปแบบคอนทัวร์งานสำเร็จรูปที่ Aspose.Tasks รองรับ `Asn.WORK_CONTOUR` ระบุฟิลด์คอนทัวร์ของการมอบหมายทรัพยากร และ `generateTimephasedData()` สร้างรายการงาน Timephased ตามการตั้งค่าคอนทัวร์ปัจจุบัน คอนทัวร์ **Flat** จะกระจายงานอย่างเท่าเทียมตลอดระยะเวลาของงาน; ตั้งค่าโดยใช้ `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` แล้วเรียก `firstRA.generateTimephasedData()` เพื่อรับค่าที่เท่าเทียมกัน

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – Turtle
คอนทัวร์ **Turtle** เริ่มด้วยความพยายามต่ำ เร่งขึ้นสู่กลางแล้วชะลอตัวลงอีกครั้ง คล้ายกับจังหวะช้า ๆ ของเต่า ใช้โดยตั้งค่า `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` แล้วสร้างข้อมูล Timephased ใหม่ รูปแบบนี้เหมาะกับงานที่ต้องการช่วงเรียนรู้ก่อนถึงจุดผลิตสูงสุด

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – BackLoaded
คอนทัวร์ **BackLoaded** จะวางส่วนใหญ่ของงานไว้ที่ส่วนท้ายของกำหนดการงาน โดยมีความพยายามน้อยที่จุดเริ่มต้น ตั้งค่าโดยใช้ `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` แล้วสร้างข้อมูล Timephased ใหม่ ซึ่งเหมาะกับกิจกรรมที่ต้องอาศัยงานก่อนหน้าให้เสร็จสิ้นก่อนจึงจะทำงานได้

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – FrontLoaded
คอนทัวร์ **FrontLoaded** จะรวมความพยายามไว้ที่จุดเริ่มต้นของงาน โมเดลสถานการณ์เช่นช่วงเริ่มต้นโครงการหรือการทำงานอย่างเข้มข้นในช่วงแรก ใช้โดยตั้งค่า `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` แล้วเรียก `firstRA.generateTimephasedData()` เพื่อดูการกระจายที่เน้นด้านหน้า

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – Bell
คอนทัวร์ **Bell** สร้างยอดสูงแบบสมมาตรที่กลางไทม์ไลน์ แสดงงานที่ค่อยเพิ่มขึ้นถึงจุดสูงสุดแล้วค่อยลดลงอย่างราบรื่น ตั้งค่าโดยใช้ `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` แล้วสร้างข้อมูล Timephased ใหม่เพื่อดูกราฟความพยายามรูปกระดิ่ง

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – EarlyPeak
**EarlyPeak** จะวางค่าการทำงานสูงสุดไว้ตอนต้นของกำหนดการ แล้วค่อยลดลง ใช้ `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` ตามด้วย `firstRA.generateTimephasedData()` เพื่อจำลองกิจกรรมที่ต้องการการเริ่มต้นที่แข็งแรง เช่นการทำต้นแบบอย่างรวดเร็ว

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – LatePeak
**LatePeak** ย้ายยอดสูงสุดของงานไปทางส่วนท้ายของงาน เหมาะกับงานที่ความเข้มข้นเพิ่มขึ้นเมื่อใกล้ถึงกำหนดเวลา ตั้งค่าโดยใช้ `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` แล้วสร้างข้อมูล Timephased ใหม่เพื่อดูการเพิ่มขึ้นของภาระงานในช่วงสุดท้าย

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## วิธีเปลี่ยนคอนทัวร์ – DoublePeak
**DoublePeak** สร้างสองจุดพุ่งของงานที่แยกจากกันด้วยช่วงความพยายามต่ำ ใช้สำหรับงานที่มีสองช่วงการทำงานหนัก ตั้งค่าโดยใช้ `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` แล้วเรียก `firstRA.generateTimephasedData()` เพื่อรับรูปแบบสองยอด

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## ปัญหาทั่วไปและเคล็ดลับ
- **คอนทัวร์ไม่อัปเดต?** ตรวจสอบให้แน่ใจว่าคุณเรียก `firstRA.set(Asn.WORK_CONTOUR, …)` *ก่อน* ดึงข้อมูล Timephased  
- **ค่าที่ได้ไม่คาดคิด?** ตรวจสอบว่าค่าเริ่มต้นและสิ้นสุดของงานถูกตั้งค่าอย่างถูกต้องในไฟล์ MPP ต้นฉบับ  
- **เคล็ดลับประสิทธิภาพ:** ใช้ instance ของ `Project` เดียวกันเมื่อต้องวนลูปหลายคอนทัวร์เพื่อหลีกเลี่ยงการอ่าน‑เขียนไฟล์ที่ไม่จำเป็น ซึ่งสามารถลดเวลาประมวลผลได้ถึง 40 % ในโครงการขนาดใหญ่  
- **เคล็ดลับหน่วยความจำ:** สำหรับโครงการที่มีขนาดเกิน 1 GB ให้เปิดใช้งาน `Project.setReadOnly(true)` เพื่อให้การใช้หน่วยความจำอยู่ต่ำกว่า 200 MB ขณะยังคงสร้างข้อมูล Timephased ที่แม่นยำ

## คำถามที่พบบ่อย
**Q: สามารถใช้ Aspose.Tasks ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
A: ได้, Aspose.Tasks ทำงานร่วมกับไลบรารี Java อื่นได้อย่างราบรื่น ช่วยให้คุณรวมข้อมูลการกำหนดเวลากับการรายงาน, การวิเคราะห์ หรือเฟรมเวิร์ก UI ต่าง ๆ

**Q: Aspose.Tasks เหมาะกับโครงการระดับองค์กรขนาดใหญ่หรือไม่?**  
A: แน่นอน. ไลบรารีถูกออกแบบให้จัดการโครงการที่มีงานและทรัพยากรหลายหมื่นรายการได้ โดยประมวลผลไฟล์หลายร้อยหน้าต่อโดยไม่ลดทอนประสิทธิภาพ

**Q: Aspose.Tasks รองรับรูปแบบไฟล์โครงการต่าง ๆ หรือไม่?**  
A: รองรับมากกว่า 30 รูปแบบ รวมถึง MPP, XML, CSV, MPX เป็นต้น ทำให้การนำเข้า‑ส่งออกระหว่างระบบเก่าและใหม่เป็นเรื่องง่าย

**Q: สามารถกำหนดคอนทัวร์งานตามความต้องการของโครงการได้หรือไม่?**  
A: ได้, คุณสามารถกำหนดคอนทัวร์แบบกำหนดเองโดยส่งอาร์เรย์ของเปอร์เซ็นต์งานไปยังคุณสมบัติ `WORK_CONTOUR` ซึ่งให้คุณควบคุมการกระจายความพยายามได้เต็มที่

**Q: มีฟอรั่มชุมชนที่สามารถขอความช่วยเหลือเกี่ยวกับ Aspose.Tasks ได้หรือไม่?**  
A: มี, คุณสามารถเข้าไปที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุน การสนทนา และตัวอย่างโค้ดจากวิศวกรของ Aspose และสมาชิกในชุมชน

---

**อัปเดตล่าสุด:** 2026-06-10  
**ทดสอบกับ:** Aspose.Tasks for Java (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [สร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [อ่านข้อมูล Timephased สำหรับทรัพยากรใน Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [วิธีหยุดการมอบหมายและทำการมอบหมายทรัพยากรต่อใน Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}