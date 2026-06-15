---
date: 2026-06-15
description: เรียนรู้วิธีจัดการต้นทุนในไฟล์ MS Project ด้วย Aspose.Tasks for Java
  รวมถึงวิธีโหลดไฟล์ MPP และอ่านต้นทุนจริงของงานและกำหนดการต้นทุนที่คาดการณ์ไว้
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: จัดการต้นทุนทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีจัดการต้นทุนใน MS Project ด้วย Aspose.Tasks for Java
url: /th/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีจัดการต้นทุนใน MS Project ด้วย Aspose.Tasks for Java

## บทนำ

การจัดการงบประมาณของโครงการเป็นหน้าที่หลักของผู้จัดการโครงการทุกคน, และ **วิธีจัดการต้นทุน** อย่างมีประสิทธิภาพสามารถทำให้โครงการประสบความสำเร็จหรือไม่สำเร็จได้ Aspose.Tasks for Java ให้คุณควบคุมไฟล์ Microsoft Project ด้วยโปรแกรม, ทำให้คุณสามารถอ่านและอัปเดตข้อมูลต้นทุนของทรัพยากรโดยไม่ต้องเปิดไฟล์ .mpp ด้วยตนเอง ในบทเรียนนี้คุณจะเห็นขั้นตอนแบบทีละขั้นตอนว่าต้องโหลดไฟล์ MPP อย่างไร, ตรวจสอบ actual cost work, และดึง budgeted cost schedule สำหรับแต่ละทรัพยากร

## คำตอบสั้น
- **Aspose.Tasks for Java ทำอะไร?** มันอ่านและเขียนไฟล์ Microsoft Project (.mpp) โดยไม่ต้องติดตั้ง Microsoft Project.  
- **ฉันจะโหลดไฟล์ MPP อย่างไร?** ใช้ `new Project("path/to/file.mpp")` – API จะทำการแยกไฟล์ในหน่วยความจำ.  
- **ฟิลด์ต้นทุนใดบ้างที่มี?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) และ Budgeted Cost of Work Performed (BCWP).  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** ใบอนุญาตชั่วคราวฟรีใช้ได้สำหรับการทดสอบ; ต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 และรุ่นต่อไป, รวมถึง Java 17 LTS.

## วิธีจัดการต้นทุนใน MS Project?

โหลดโครงการของคุณด้วย `new Project("yourFile.mpp")`, จากนั้นวนลูปผ่านแต่ละอ็อบเจกต์ `Resource` เพื่ออ่านคุณสมบัติเกี่ยวกับต้นทุนเช่น ACWP, BCWS, และ BCWP. Aspose.Tasks จะทำการแปลงค่าต้นทุนภายในให้เป็นสกุลเงินของโครงการโดยอัตโนมัติ, ดังนั้นคุณสามารถแสดงหรือเก็บค่าเหล่านี้โดยตรง วิธีนี้ช่วยขจัดการคำนวณด้วยสเปรดชีตด้วยตนเองและรับประกันความสอดคล้องของข้อมูลในรายงานโครงการทั้งหมด.

## ข้อกำหนดเบื้องต้น

1. ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
2. ไลบรารี Aspose.Tasks for Java ถูกเพิ่มในโครงการของคุณ (Maven/Gradle หรือ JAR แบบแมนนวล).  
3. การเข้าถึงไฟล์ Microsoft Project (`.mpp`) ที่คุณต้องการวิเคราะห์.  

## นำเข้าแพ็กเกจ

คลาส `Project` และ `Resource` เป็นจุดเริ่มต้นสำหรับการทำงานกับข้อมูลโครงการ.

คลาส `Project` เป็นอ็อบเจกต์ระดับบนของ Aspose.Tasks ที่แสดงไฟล์ Microsoft Project เดียวในหน่วยความจำ.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล

แรกสุด, ระบุโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ของคุณ. เส้นทางนี้สามารถเป็นแบบเต็มหรือแบบสัมพันธ์กับไดเรกทอรีทำงานของแอปพลิเคชันของคุณ.  
```text
```java
String dataDir = "Your Data Directory";
```
```

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project

`Project` โหลดไฟล์และสร้างโมเดลอ็อบเจกต์ที่คุณสามารถสอบถามได้. API จะทำการแยกไฟล์โดยไม่ต้องติดตั้ง Microsoft Project, รองรับรูปแบบอินพุตกว่า 30 แบบ.  
```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## ขั้นตอนที่ 3: วนลูปผ่านทรัพยากร

อ็อบเจกต์ `Resource` แทนคน, อุปกรณ์, หรือวัสดุที่ใช้จ่ายงบประมาณ. คุณสามารถวนลูปผ่านคอลเลกชัน `project.getResources()` เพื่อเข้าถึงแต่ละรายการ.  
```text
```java
for (Resource res : prj.getResources()) {
```
```

## ขั้นตอนที่ 4: ตรวจสอบชื่อทรัพยากรและต้นทุน

สำหรับแต่ละทรัพยากร, ตรวจสอบว่าชื่อถูกกำหนดแล้ว, จากนั้นอ่านฟิลด์ต้นทุน. เมธอด `getActualCost()` คืนค่า **actual cost work** (ACWP), ส่วน `getBudgetedCost()` ให้คุณ **budgeted cost schedule** (BCWS/BCWP).  
```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่อโหลดไฟล์ MPP?

Aspose.Tasks รองรับ **ไฟล์รูปแบบกว่า 30** (รวมถึง `.mpp`, `.xml`, และ `.xlsx`) และสามารถประมวลผลโครงการที่มี **งานสูงสุด 10,000 งาน** โดยใช้หน่วยความจำน้อยกว่า 200 MB. ไลบรารีทำการคำนวณทั้งหมดบนเซิร์ฟเวอร์, ขจัดความจำเป็นในการมีสำเนา Microsoft Project ที่มีลิขสิทธิ์.

## ปัญหาทั่วไปและวิธีแก้

- **ชื่อทรัพยากรเป็น Null:** ไฟล์เก่าบางไฟล์มีทรัพยากรตัวแทน. ควรตรวจสอบ `resource.getName() != null` ก่อนเข้าถึงคุณสมบัติต้นทุนเสมอ.  
- **ไฟล์ขนาดใหญ่ทำให้ความดันหน่วยความจำ:** LoadOptions เป็นคลาสการกำหนดค่าที่ให้คุณระบุว่าข้อมูลโครงการใดที่จะโหลด. ใช้ `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` เพื่อโหลดเฉพาะข้อมูลที่ต้องการ, แล้วเปิดใช้งานต่อไปหากจำเป็น.  
- **ความไม่ตรงกันของสกุลเงิน:** API เคารพการตั้งค่าสกุลเงินของโครงการ; คุณสามารถแทนที่ได้ด้วย `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` หากต้องการ. CostRateTableType แสดงตารางอัตราต้นทุนต่าง ๆ ที่สามารถนำไปใช้กับงาน.

## คำถามที่พบบ่อย

**Q: Aspose.Tasks for Java สามารถจัดการโครงสร้างโครงการที่ซับซ้อนได้หรือไม่?**  
A: ใช่, รองรับงานสรุปแบบซ้อนกัน, ปฏิทินทรัพยากรหลายชุด, และฟิลด์กำหนดเองในทุกเวอร์ชันของ Project ที่รองรับอย่างเต็มที่.

**Q: ไลบรารีเข้ากันได้กับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project หรือไม่?**  
A: แน่นอน. Aspose.Tasks อ่านและเขียนไฟล์จาก Microsoft Project 2000 จนถึงรูปแบบล่าสุดของปี 2023.

**Q: ฉันสามารถรวม Aspose.Tasks for Java กับไลบรารี Java อื่น ๆ ได้หรือไม่?**  
A: ได้, API คืนค่าอ็อบเจกต์ Java มาตรฐาน, ทำให้สามารถรวมกับเฟรมเวิร์กการบันทึก, เครื่องมือ ORM, หรือไลบรารีการรายงานได้อย่างราบรื่น.

**Q: Aspose.Tasks for Java มีการสนับสนุนลูกค้าหรือไม่?**  
A: Aspose มีการสนับสนุนผ่านฟอรั่มเฉพาะ, เอกสารละเอียด, และการช่วยเหลือทางอีเมลที่ตอบสนองสำหรับผู้ใช้ที่มีลิขสิทธิ์.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: คุณสามารถดาวน์โหลดใบอนุญาตทดลองใช้ 30 วันจากเว็บไซต์ Aspose เพื่อสำรวจคุณสมบัติทั้งหมดโดยไม่มีค่าใช้จ่าย.

---

**อัปเดตล่าสุด:** 2026-06-15  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีคำนวณความแปรผันของต้นทุนและจัดการต้นทุนการมอบหมายด้วย Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [การจัดการงบประมาณ งาน และต้นทุนสำหรับงานใน Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [เพิ่มทรัพยากรลงในโครงการด้วย Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}