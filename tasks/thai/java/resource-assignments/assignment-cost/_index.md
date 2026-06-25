---
date: 2026-06-25
description: เรียนรู้วิธีคำนวณ variance และจัดการ assignment costs ด้วย Aspose.Tasks
  สำหรับ Java. คู่มือแบบขั้นตอนที่ครอบคลุม cost variance, budgeted cost work performed,
  และ schedule variance calculation.
keywords:
- how to compute variance
- budgeted cost work performed
- schedule variance calculation
- actual cost of work
- calculate earned value
linktitle: จัดการ Assignment Cost ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to compute variance and manage assignment costs using Aspose.Tasks
    for Java. Step‑by‑step guide covering cost variance, budgeted cost work performed,
    and schedule variance calculation.
  headline: How to Compute Variance with Aspose.Tasks
  type: TechArticle
- description: Learn how to compute variance and manage assignment costs using Aspose.Tasks
    for Java. Step‑by‑step guide covering cost variance, budgeted cost work performed,
    and schedule variance calculation.
  name: How to Compute Variance with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher installed.'
    text: '**Java Development Kit (JDK)** – version 8 or higher installed.'
  - name: '**Aspose.Tasks for Java Library** – download it from the [website](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java Library** – download it from the [website](https://releases.aspose.com/tasks/java/).'
  - name: Basic familiarity with Java syntax and Maven/Gradle project setup.
    text: Basic familiarity with Java syntax and Maven/Gradle project setup.
  type: HowTo
- questions:
  - answer: After iterating through assignments, you can use Aspose.Cells to write
      the values into a spreadsheet, mapping each assignment’s ID to its CV.
    question: How do I export the calculated cost variance to an Excel report?
  - answer: Yes, you can use `project.getResourceAssignments().where(ra -> ra.getResource().getUid()
      == desiredResourceId)` to limit the loop.
    question: Is it possible to filter assignments by a specific resource before calculating
      variance?
  - answer: A negative CV means the actual cost (ACWP) exceeds the earned value (BCWP),
      signaling an overrun that should be investigated.
    question: What does a negative cost variance indicate?
  - answer: Absolutely. Use `ra.set(Asn.COST, new BigDecimal("1500"))` and then call
      `project.save("updated.mpp")`.
    question: Can I update the cost fields programmatically and then save the project?
  - answer: The library stores raw numeric values; you must apply any required conversion
      logic yourself before presentation.
    question: Does Aspose.Tasks automatically handle currency conversion?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีคำนวณ Variance ด้วย Aspose.Tasks
url: /th/java/resource-assignments/assignment-cost/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีคำนวณส่วนเบี่ยงเบนและจัดการค่าใช้จ่ายการมอบหมายด้วย Aspose.Tasks

## บทนำ
ในการจัดการต้นทุนโครงการ, **how to compute variance** เป็นทักษะพื้นฐานที่ช่วยให้คุณเปรียบเทียบสิ่งที่วางแผนไว้กับสิ่งที่ใช้จ่ายจริง โดยการเชี่ยวชาญเรื่องนี้ด้วย **Aspose.Tasks for Java** คุณสามารถอ่านฟิลด์ต้นทุนระดับการมอบหมาย, คำนวณส่วนเบี่ยงเบนต้นทุน, และดึงเมตริกที่เกี่ยวข้องเช่นต้นทุนที่คาดการณ์ของงานที่ทำแล้ว (budgeted cost work performed) และส่วนเบี่ยงเบนตามกำหนดเวลา (schedule variance) คำแนะนำนี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การโหลดไฟล์โครงการจนถึงการตีความผลลัพธ์ เพื่อให้คุณสามารถรักษาโครงการให้อยู่ในงบประมาณและตามกำหนดเวลาได้

## คำตอบอย่างรวดเร็ว
- **“calculate cost variance” หมายถึงอะไร?** มันวัดความแตกต่างระหว่างมูลค่าที่ได้จากงานที่ทำแล้ว (BCWP) กับต้นทุนที่เกิดขึ้นจริง (ACWP) ค่าเป็นบวกบ่งชี้ว่างานอยู่ภายใต้งบประมาณ, ส่วนค่าเป็นลบบ่งชี้ว่ามีการเกินงบประมาณ เมตริกนี้ช่วยผู้จัดการโครงการประเมินผลการเงินและดำเนินการแก้ไขตั้งแต่เนิ่นๆ  
- **API property ใดให้ค่า cost variance?** `Asn.CV` คือ property ของอ็อบเจ็กต์ `ResourceAssignment` ที่ส่งคืนส่วนเบี่ยงเบนต้นทุนที่คำนวณแล้วสำหรับการมอบหมายนั้น ไลบรารีคำนวณค่าโดยอัตโนมัติจากต้นทุนที่คาดการณ์ของงานที่ทำและต้นทุนที่เกิดจริงของการมอบหมาย, ดังนั้นคุณสามารถอ่านค่าได้โดยตรงโดยไม่ต้องคำนวณด้วยตนเอง  
- **ฉันต้องการไลเซนส์เพื่อรันตัวอย่างหรือไม่?** ไลเซนส์ทดลองฟรีเพียงพอสำหรับการคอมไพล์และรันโค้ดตัวอย่าง, ช่วยให้คุณสำรวจ API ได้โดยไม่มีค่าใช้จ่าย อย่างไรก็ตามสำหรับการใช้งานในสภาพแวดล้อมการผลิตหรือการแจกจ่ายแอปพลิเคชันที่ใช้ Aspose.Tasks จำเป็นต้องมีไลเซนส์ที่ซื้อเพื่อยกเลิกข้อจำกัดของรุ่นทดลองและรับการสนับสนุนเต็มรูปแบบ  
- **รูปแบบไฟล์โครงการที่รองรับมีอะไรบ้าง?** Aspose.Tasks for Java สามารถอ่านและเขียนรูปแบบไฟล์โครงการได้หลากหลาย รวมถึง Microsoft Project MPP, XML, MPX, และอื่นๆ เช่น Planner, Primavera, และ CSV มีการรองรับมากกว่า 30 รูปแบบ ทำให้การผสานรวมกับข้อมูลโครงการที่มีอยู่ไม่ว่าจะมาจากระบบใดก็เป็นไปอย่างราบรื่น  
- **ต้องการการกำหนดค่าพิเศษหรือไม่?** ไม่จำเป็นต้องกำหนดค่าพิเศษใดๆ นอกจากการเพิ่ม Aspose.Tasks JAR (หรือ dependency ของ Maven/Gradle) ไปยัง classpath และตรวจสอบให้แน่ใจว่า Java runtime สามารถหาไลบรารีได้ หลังจากนั้นคุณสามารถสร้างอ็อบเจ็กต์ `Project` และเริ่มเข้าถึงข้อมูลการมอบหมายได้ทันที  

## อะไรคือ how to compute variance?
**How to compute variance** คือกระบวนการนำต้นทุนที่คาดการณ์ของงานที่ทำ (BCWP) มาลบด้วยต้นทุนที่เกิดจริงของงานที่ทำ (ACWP) ผลลัพธ์ที่ได้คือส่วนเบี่ยงเบนต้นทุน (CV) ซึ่งบ่งบอกว่างานอยู่ภายใต้งบประมาณหรือเกินงบประมาณ ค่า CV เป็นบวกหมายถึงอยู่ภายใต้งบ, ค่า CV เป็นลบหมายถึงเกินงบ, และขนาดของค่า CV ช่วยในการจัดลำดับความสำคัญของการดำเนินการแก้ไข  

## ทำไมต้องใช้ Aspose.Tasks สำหรับการคำนวณส่วนเบี่ยงเบน?
Aspose.Tasks for Java รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 30 รูปแบบ** และสามารถประมวลผลโครงการที่มี **งานสูงสุด 10,000 งาน** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้ประสิทธิภาพการอ่านเร็วขึ้น **30 %** เมื่อเทียบกับ API ของ Microsoft Project ดั้งเดิม ความสามารถที่วัดได้เหล่านี้ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับการวางกำหนดการระดับองค์กรขนาดใหญ่  

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือสูงกว่า ติดตั้งแล้ว.  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดจาก [website](https://releases.aspose.com/tasks/java/).  
3. ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และการตั้งค่าโครงการ Maven/Gradle.  

## นำเข้าแพ็กเกจ
แรก, ให้นำเข้าคลาสที่จำเป็นในไฟล์ซอร์ส Java ของคุณ:

```java
import com.aspose.tasks.*;
import java.math.BigDecimal;
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
`Project` คืออ็อบเจ็กต์หลักของ Aspose.Tasks ที่แสดงไฟล์ Microsoft Project ในหน่วยความจำ การสร้างอินสแตนซ์จะทำการแยกโครงสร้างไฟล์โดยอัตโนมัติ

สร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ Microsoft Project ที่มีอยู่ของคุณ:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 2: วนลูปผ่านการมอบหมายทรัพยากร
`ResourceAssignment` คือคลาสที่เชื่อมทรัพยากรกับงานและเก็บฟิลด์ที่เกี่ยวกับต้นทุนทั้งหมด วนลูปผ่านแต่ละการมอบหมายเพื่ออ่านค่าที่คุณต้องการสำหรับการคำนวณส่วนเบี่ยงเบน.

```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Assignment cost (total planned cost)
    System.out.println("Assignment Cost: " + ra.get(Asn.COST));
    
    // Actual cost of work performed (ACWP)
    System.out.println("Actual Cost of Work Performed: " + ra.get(Asn.ACWP));
    
    // Cost Variance (CV) – the primary metric we want to calculate
    System.out.println("Cost Variance (CV): " + ra.get(Asn.CV));
    
    // Budgeted Cost of Work Performed (BCWP) – also known as earned value
    System.out.println("Budgeted Cost of Work Performed: " + ra.get(Asn.BCWP));
    
    // Budgeted Cost of Work Scheduled (BCWS)
    System.out.println("Budgeted Cost of Work Scheduled: " + ra.get(Asn.BCWS));
    
    // Schedule Variance (SV) – useful for schedule variance calculation
    System.out.println("Schedule Variance (SV): " + ra.get(Asn.SV));
}
```

### ทำไมฟิลด์เหล่านี้ถึงสำคัญ
- **`Asn.COST`** – ต้นทุนรวมที่คุณวางแผนสำหรับการมอบหมายนี้.  
- **`Asn.ACWP`** – *ต้นทุนจริงของงาน* ที่ทำจนถึงปัจจุบัน.  
- **`Asn.CV`** – ผลลัพธ์ของ **how to compute variance** (`BCWP - ACWP`).  
- **`Asn.BCWP`** – แสดง *ต้นทุนที่คาดการณ์ของงานที่ทำ*, เป็นข้อมูลสำคัญสำหรับการวิเคราะห์มูลค่าได้.  
- **`Asn.SV`** – ช่วยให้คุณทำการคำนวณ *schedule variance* เพื่อดูว่างานล่วงหน้าหรือช้ากว่ากำหนดเวลา.  

## วิธีคำนวณส่วนเบี่ยงเบน?
โหลดแต่ละการมอบหมาย, ดึงค่า `BCWP` และ `ACWP`, แล้วลบ: `CV = BCWP - ACWP`. การคำนวณบรรทัดเดียวนี้ให้ส่วนเบี่ยงเบนต้นทุนของการมอบหมายนั้น ค่า CV เป็นบวกบ่งชี้ว่าคุณอยู่ภายใต้งบประมาณ, ส่วนค่า CV เป็นลบบ่งชี้ว่ามีการเกินงบที่ต้องให้ความสนใจ สำหรับโครงการขนาดใหญ่คุณสามารถคำนวณเป็นชุดเพื่อหลีกเลี่ยงการทำ I/O ซ้ำหลายครั้ง.  

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ค่า Null:** การมอบหมายบางรายการอาจไม่มีข้อมูลต้นทุน. ควรตรวจสอบ `null` ก่อนทำการคำนวณ.  
- **การจัดการสกุลเงิน:** ต้นทุนถูกเก็บเป็น `BigDecimal`. ใช้ `setScale` หากต้องการจำนวนตำแหน่งทศนิยมเฉพาะ.  
- **ประสิทธิภาพ:** สำหรับโครงการขนาดใหญ่มาก, พิจารณาการกรองการมอบหมาย (`project.getResourceAssignments().where(...)`) เพื่อลดภาระการวนลูป.  

## สรุป
ด้วยการใช้ Aspose.Tasks for Java คุณสามารถ **คำนวณส่วนเบี่ยงเบน** ได้อย่างง่ายดาย, ตรวจสอบ *ต้นทุนจริงของงาน* และติดตาม *ต้นทุนที่คาดการณ์ของงานที่ทำ* และ *schedule variance* ระดับข้อมูลนี้ช่วยให้การจัดการต้นทุนโครงการมีประสิทธิภาพมากขึ้นและช่วยให้คุณอยู่ในงบประมาณและตามกำหนดเวลา  

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.Tasks for Java เพื่อคำนวณค่าใช้จ่ายการมอบหมายทรัพยากรแบบไดนามิกได้หรือไม่?
A: ใช่, คุณสามารถคำนวณค่าใช้จ่ายการมอบหมายแบบไดนามิกโดยใช้ Aspose.Tasks for Java API.  
### Q: Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการทั้งหมดหรือไม่?
A: Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการต่างๆ รวมถึง MPP, XML, และ MPX.  
### Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้อย่างไร?
A: คุณสามารถรับการสนับสนุนโดยไปที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) หรือ ติดต่อฝ่ายสนับสนุนของ Aspose โดยตรง.  
### Q: ฉันสามารถลองใช้ Aspose.Tasks for Java ก่อนซื้อได้หรือไม่?
A: ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [website](https://releases.aspose.com/).  
### Q: ฉันต้องการไลเซนส์ชั่วคราวสำหรับการใช้ Aspose.Tasks for Java ในรุ่นทดลองหรือไม่?
A: ไม่, ไม่จำเป็นต้องมีไลเซนส์ชั่วคราวสำหรับการใช้รุ่นทดลอง อย่างไรก็ตามแนะนำให้ใช้ในสภาพแวดล้อมการผลิต.  

## คำถามที่พบบ่อย
**Q: ฉันจะส่งออกส่วนเบี่ยงเบนต้นทุนที่คำนวณแล้วเป็นรายงาน Excel อย่างไร?**  
A: หลังจากวนลูปผ่านการมอบหมาย, คุณสามารถใช้ Aspose.Cells เพื่อเขียนค่าลงในสเปรดชีต, โดยแมป ID ของแต่ละการมอบหมายกับ CV ของมัน.  

**Q: สามารถกรองการมอบหมายตามทรัพยากรเฉพาะก่อนคำนวณส่วนเบี่ยงเบนได้หรือไม่?**  
A: ใช่, คุณสามารถใช้ `project.getResourceAssignments().where(ra -> ra.getResource().getUid() == desiredResourceId)` เพื่อจำกัดลูป.  

**Q: ส่วนเบี่ยงเบนต้นทุนเป็นลบหมายถึงอะไร?**  
A: CV เป็นลบหมายถึงต้นทุนจริง (ACWP) มากกว่ามูลค่าที่ได้ (BCWP), บ่งชี้ว่ามีการเกินงบที่ควรตรวจสอบ.  

**Q: ฉันสามารถอัปเดตฟิลด์ต้นทุนโดยโปรแกรมแล้วบันทึกโครงการได้หรือไม่?**  
A: แน่นอน. ใช้ `ra.set(Asn.COST, new BigDecimal("1500"))` แล้วเรียก `project.save("updated.mpp")`.  

**Q: Aspose.Tasks จัดการการแปลงสกุลเงินโดยอัตโนมัติหรือไม่?**  
A: ไลบรารีเก็บค่าตัวเลขดิบ; คุณต้องทำการแปลงสกุลเงินเองก่อนนำเสนอ.  

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [จัดการงบประมาณการมอบหมาย Java ด้วย Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [จัดการต้นทุนทรัพยากร MS Project ด้วย Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [สร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}