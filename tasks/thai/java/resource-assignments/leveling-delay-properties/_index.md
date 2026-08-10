---
date: 2026-06-05
description: เรียนรู้วิธีสร้างการมอบหมายทรัพยากรด้วย Aspose.Tasks for Java, เพิ่มทรัพยากรในโครงการ,
  และจัดการ Leveling Delay Properties
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: จัดการ Leveling Delay Properties สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: สร้างการมอบหมายทรัพยากรด้วย Aspose.Tasks for Java
url: /th/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างการมอบหมายทรัพยากรด้วย Aspose.Tasks สำหรับ Java

ในคู่มือฉบับครอบคลุมนี้คุณจะได้เรียนรู้ **วิธีสร้างการมอบหมายทรัพยากร aspotasks** โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะกำลังสร้างเอนจินการจัดตารางแบบกำหนดเอง, ทำการอัตโนมัติการอัปเดตโครงการเป็นจำนวนมาก, หรือเพียงต้องการจัดการไฟล์ Microsoft Project โดยไม่ต้องใช้แอปพลิเคชันบนเดสก์ท็อป การเชี่ยวชาญขั้นตอนเหล่านี้จะทำให้คุณรักษาข้อมูลโครงการให้แม่นยำและควบคุมได้อย่างเต็มที่

## คำตอบด่วน
- **What does “add resource to project” mean?** มันสร้างรายการทรัพยากรใหม่ที่สามารถมอบหมายให้กับงานในภายหลัง  
- **Can I set a leveling delay after assignment?** ใช่, โดยใช้ฟิลด์ `Asn.DELAY` หรือ `Asn.LEVELING_DELAY`  
- **Do I need a license to run this code?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์แบบชำระเงินสำหรับการใช้งานจริง  
- **Which Java version is supported?** Java 8 หรือใหม่กว่า  
- **Is this compatible with all MS Project file formats?** Aspose.Tasks รองรับรูปแบบไฟล์กว่า 12 รูปแบบรวมถึง .MPP, .XML, .XER, .CSV, .PDF, และอื่น ๆ  

## “add resource to project” คืออะไรใน Aspose.Tasks
การเพิ่มทรัพยากรลงในโครงการหมายถึงการสร้างอ็อบเจ็กต์ `Resource` ภายในโมเดล `Project` อ็อบเจ็กต์นี้สามารถเชื่อมต่อกับงานผ่าน `ResourceAssignment` ในภายหลัง ทำให้คุณสามารถติดตามงาน, ค่าใช้จ่าย, และการตั้งค่าการเลเวลลิงได้ การแทรกทรัพยากรจะให้ตัวจัดตารางสิ่งที่สามารถจัดสรรได้ และคุณสามารถสอบถามหรือแก้ไขคุณสมบัติต่าง ๆ เช่น ความพร้อมใช้งาน, อัตรา, และการมอบหมายปฏิทินในภายหลัง

## ทำไมต้องจัดการคุณสมบัติการหน่วงเวลาเลเวลลิง
การหน่วงเวลาเลเวลลิงบอกตัวจัดตารางให้เลื่อนการเริ่มต้นของการมอบหมายที่มีการจัดสรรเกินไป, ทำให้การทำงานกระจายอย่างสม่ำเสมอทั่วไทม์ไลน์ การกำหนดค่าหน่วงเวลานี้ช่วยหลีกเลี่ยงวันที่เริ่มต้นที่ไม่สมจริง, ลดการเตือนการจัดสรรเกิน, และสร้างตารางที่สะท้อนข้อจำกัดของทรัพยากรในโลกจริง การปรับหน่วงเวลาให้คุณควบคุมระดับความยืดหยุ่นที่เครื่องอาจแทรกได้อย่างละเอียด, ช่วยให้คุณทำตามกำหนดเวลาโครงการโดยคำนึงถึงขีดจำกัดของทรัพยากร

## วิธีสร้างการมอบหมายทรัพยากร aspotasks
โหลดอ็อบเจ็กต์ `Project` ของคุณ, เพิ่มงาน, สร้างทรัพยากร, แล้วผูกเข้าด้วยกันด้วย `ResourceAssignment` กระบวนการแบบต้นจนจบนี้ทำให้คุณสามารถสร้างโครงสร้างโครงการเต็มรูปแบบโดยโปรแกรมและควบคุมการหน่วงเวลาเลเวลลิงบนการมอบหมายได้ทันที กระบวนการนี้แสดงการทำงานหลัก: การเริ่มต้นโครงการ, การกำหนดงาน, การสร้างทรัพยากร, การเชื่อมโยงการมอบหมาย, และสุดท้ายการใช้พารามิเตอร์การจัดตารางเช่นการหน่วงเวลาเลเวลลิง

## ข้อกำหนดเบื้องต้น
1. Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งได้จาก [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html)  
2. Aspose.Tasks for Java Library: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จาก [download page](https://releases.aspose.com/tasks/java/)

## นำเข้าแพ็กเกจ
การนำเข้าต่อไปนี้นำเข้าคลาสหลักของ Aspose.Tasks ที่จำเป็นสำหรับการจัดการโครงการ.  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## วิธีสร้างการมอบหมายทรัพยากร aspotasks
โหลดอ็อบเจ็กต์ `Project` ของคุณ, เพิ่มงาน, สร้างทรัพยากร, แล้วผูกเข้าด้วยกันด้วย `ResourceAssignment` กระบวนการแบบต้นจนจบนี้ทำให้คุณสามารถสร้างโครงสร้างโครงการเต็มรูปแบบโดยโปรแกรมและควบคุมการหน่วงเวลาเลเวลลิงบนการมอบหมายได้ทันที กระบวนการนี้แสดงการทำงานหลัก: การเริ่มต้นโครงการ, การกำหนดงาน, การสร้างทรัพยากร, การเชื่อมโยงการมอบหมาย, และสุดท้ายการใช้พารามิเตอร์การจัดตารางเช่นการหน่วงเวลาเลเวลลิง

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Project
คลาส `Project` เป็นคอนเทนเนอร์ระดับบนของ Aspose.Tasks ที่แสดงไฟล์โครงการทั้งหมดในหน่วยความจำ การสร้างอินสแตนซ์ให้คุณมีพื้นฐานที่สะอาดสำหรับการเพิ่มงาน, ทรัพยากร, และการมอบหมาย.  
```java
Project prj = new Project();
```

## ขั้นตอนที่ 2: สร้างงาน
คลาส `Task` แสดงรายการงานเดียวในตารางการจัดตาราง การเพิ่มงานแสดง **how to add task** อย่างโปรแกรมและให้เป้าหมายสำหรับการมอบหมายทรัพยากรที่กำลังจะมาถึง.  
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## ขั้นตอนที่ 3: ตั้งค่าวันที่เริ่มต้นและระยะเวลาของงาน
กำหนดว่างานเริ่มเมื่อใดและใช้เวลานานเท่าใด วันที่เริ่มต้นที่ถูกต้องเป็นสิ่งสำคัญเนื่องจากการคำนวณเลเวลลิงใช้เป็นฐานสำหรับการหน่วงเวลาที่คุณระบุในภายหลัง.  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## ขั้นตอนที่ 4: เพิ่มทรัพยากร
ตอนนี้เราจะ **add resource to project** โดยสร้างรายการ `Resource` ใหม่ คลาส `Resource` แสดงถึงบุคคล, อุปกรณ์, หรือวัสดุที่สามารถมอบหมายให้กับงานได้.  
```java
Resource resource = prj.getResources().add("Resource 1");
```

## ขั้นตอนที่ 5: สร้างการมอบหมายทรัพยากร
`ResourceAssignment` เชื่อมโยง `Task` กับ `Resource` การเชื่อมโยงนี้ทำให้คุณบันทึกงาน, ค่าใช้จ่าย, และรายละเอียดการเลเวลลิงสำหรับทรัพยากรเฉพาะบนงานเฉพาะ.  
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## ขั้นตอนที่ 6: ตั้งค่าการหน่วงเวลาเลเวลลิง
กำหนดค่าการหน่วงเวลาเลเวลลิงสำหรับการมอบหมาย การตั้งค่าเป็นศูนย์หมายถึงไม่มีการหน่วงเวลาเพิ่มเติม, แต่คุณสามารถปรับค่าตามต้องการ ฟิลด์ `Asn.DELAY` เก็บค่าหน่วงเวลาเป็นนาที; `Asn.LEVELING_DELAY` เป็นนามแฝงที่ทำงานเช่นเดียวกัน.  
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## ขั้นตอนที่ 7: แสดงผลลัพธ์
พิมพ์คุณสมบัติสำคัญเพื่อยืนยันว่าทุกอย่างถูกตั้งค่าอย่างถูกต้อง ขั้นตอนนี้ช่วยให้คุณตรวจสอบว่าค่าทรัพยากร, งาน, และการหน่วงเวลาตรงกับที่คาดหวังก่อนบันทึกไฟล์.  
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **Pitfall:** การลืมตั้งค่าวันที่เริ่มต้นของงานอาจทำให้การมอบหมายใช้ค่าเริ่มต้นเป็นวันเริ่มต้นของโครงการ  
- **Tip:** ใช้ `prj.getDuration(value, TimeUnitType.Day)` เพื่อควบคุมความละเอียดของการหน่วงเวลา  
- **Tip:** หลังจากเพิ่มทรัพยากรหลายรายการ, เรียก `prj.updateResourceAssignments()` เพื่อให้ตัวจัดตารางคำนวณการเลเวลลิงใหม่  
- **Pro tip:** สำหรับโครงการขนาดใหญ่ (งานมากกว่า 10,000 งาน) ให้เปิดใช้งาน `prj.setAutoCalculate(false)` ก่อนการอัปเดตเป็นกลุ่ม, แล้วเรียก `prj.calculate()` ครั้งเดียวที่ท้ายเพื่อปรับปรุงประสิทธิภาพ  

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks กับไลบรารี Java อื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks ผสานรวมอย่างราบรื่นกับไลบรารีเช่น Jackson สำหรับการจัดการ JSON หรือ Apache POI สำหรับการดำเนินการสเปรดชีตเพิ่มเติม, ทำให้คุณสร้างโซลูชันการจัดการโครงการที่สมบูรณ์ยิ่งขึ้น  

**Q: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่าง ๆ หรือไม่?**  
A: Aspose.Tasks รองรับรูปแบบไฟล์กว่า 12 รูปแบบรวมถึง .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML, และ .MPP12—ทำให้การแก้ไขแบบรอบต่อรอบเป็นไปอย่างราบรื่นในทุกเวอร์ชันหลักของ Project  

**Q: ฉันสามารถหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้ที่ไหน?**  
A: คุณสามารถหาแหล่งสนับสนุนและการสนทนาชุมชนได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)  

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: ใช่, มีการทดลองใช้ฟรีที่เต็มรูปแบบที่พร้อมใช้งานจาก [releases page](https://releases.aspose.com/)  

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับการประเมินได้อย่างไร?**  
A: ขอรับลิขสิทธิ์ชั่วคราวจาก [temporary license page](https://purchase.aspose.com/temporary-license/) เพื่อใช้งานไลบรารีโดยไม่มีข้อจำกัดการประเมิน  

**อัปเดตล่าสุด:** 2026-06-05  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

## บทเรียนที่เกี่ยวข้อง

- [สร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [จัดการงบประมาณการมอบหมาย Java ด้วย Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [วิธีหยุดการมอบหมายและทำการมอบหมายทรัพยากรต่อใน Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}