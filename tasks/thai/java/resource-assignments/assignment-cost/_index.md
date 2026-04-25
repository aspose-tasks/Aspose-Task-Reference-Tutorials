---
date: 2026-01-02
description: เรียนรู้วิธีคำนวณส่วนต่างต้นทุนและดำเนินการจัดการต้นทุนโครงการด้วย Aspose.Tasks
  สำหรับ Java คู่มือแบบขั้นตอนต่อขั้นตอนสำหรับการจัดการค่าใช้จ่ายของการมอบหมาย งานที่ทำตามงบประมาณต้นทุน
  และการคำนวณส่วนต่างกำหนดเวลา
linktitle: Handle Assignment Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีคำนวณส่วนต่างต้นทุนและจัดการค่าใช้จ่ายของการมอบหมายด้วย Aspose.Tasks
url: /th/java/resource-assignments/assignment-cost/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีคำนวณ Cost Variance และจัดการค่าใช้จ่ายของ Assignment ด้วย Aspose.Tasks

## Introduction
การคำนวณ Cost Variance อย่างมีประสิทธิภาพเป็นรากฐานของการจัดการค่าใช้จ่ายโครงการที่มั่นคง ไม่ว่าคุณจะติดตามทีมขนาดเล็กหรือโครงการระดับองค์กรใหญ่ การรู้ความแตกต่างระหว่างค่าใช้จ่ายที่วางแผนและค่าใช้จ่ายจริงช่วยให้คุณตัดสินใจได้อย่างมีข้อมูลตั้งแต่เนิ่นๆ ในบทเรียนนี้เราจะพาคุณผ่านการใช้ Aspose.Tasks for Java เพื่ออ่านค่าใช้จ่ายของ assignment, คำนวณ Cost Variance, และตรวจสอบเมตริกที่เกี่ยวข้องเช่น budgeted cost work performed และการคำนวณ schedule variance

## Quick Answers
- **“calculate cost variance” หมายถึงอะไร?** มันวัดความแตกต่างระหว่าง earned value ของงานที่ทำกับค่าใช้จ่ายจริงของมัน.  
- **คุณสมบัติ API ใดให้ค่า cost variance?** `Asn.CV` on a `ResourceAssignment` object.  
- **ฉันต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** การทดลองใช้ฟรีสามารถใช้งานเพื่อประเมินได้; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **รูปแบบไฟล์โครงการที่รองรับมีอะไรบ้าง?** MPP, XML, MPX and many others.  
- **ต้องการการกำหนดค่าพิเศษหรือไม่?** เพียงแค่เพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยัง classpath ของคุณและโหลดไฟล์โครงการ.

## Prerequisites
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือสูงกว่า ติดตั้งแล้ว.  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดจาก [website](https://releases.aspose.com/tasks/java/).  
3. ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และการตั้งค่าโครงการ Maven/Gradle.

## Import Packages
แรก, ให้นำเข้าคลาสที่จำเป็นในไฟล์ซอร์ส Java ของคุณ:

```java
import com.aspose.tasks.*;
import java.math.BigDecimal;
```

## Step 1: Load the Project File
สร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ Microsoft Project ที่มีอยู่ของคุณ:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Step 2: Iterate Through Resource Assignments
ตอนนี้เราจะวนลูปผ่านทุก `ResourceAssignment` เพื่ออ่านฟิลด์ที่เกี่ยวกับค่าใช้จ่ายและ **calculate cost variance**. สิ่งนี้ยังแสดงวิธีดึง *actual cost of work* และ *budgeted cost work performed*.

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

### Why These Fields Matter
ทำไมฟิลด์เหล่านี้ถึงสำคัญ

- **`Asn.COST`** – ค่าใช้จ่ายรวมที่คุณวางแผนสำหรับ assignment.  
- **`Asn.ACWP`** – *Actual cost of work* ที่ทำจนถึงปัจจุบัน.  
- **`Asn.CV`** – ผลลัพธ์ของ **calculate cost variance** (`BCWP - ACWP`).  
- **`Asn.BCWP`** – แสดง *budgeted cost work performed*, เป็นข้อมูลสำคัญสำหรับการวิเคราะห์ earned‑value.  
- **`Asn.SV`** – ช่วยให้คุณทำ *schedule variance calculation* เพื่อตรวจสอบว่างานล่วงหน้าหรือช้ากว่ากำหนด.

## Common Pitfalls & Tips
- **Null values:** บาง assignment อาจไม่มีข้อมูลค่าใช้จ่าย. ควรตรวจสอบ `null` ก่อนทำการคำนวณ.  
- **Currency handling:** ค่าใช้จ่ายถูกจัดเก็บเป็น `BigDecimal`. ใช้ `setScale` หากต้องการจำนวนตำแหน่งทศนิยมเฉพาะ.  
- **Performance:** สำหรับโครงการขนาดใหญ่มาก, พิจารณาการกรอง assignment (`project.getResourceAssignments().where(...)`) เพื่อลดภาระการวนลูป.

## Conclusion
ด้วยการใช้ Aspose.Tasks for Java คุณสามารถ **calculate cost variance** ได้อย่างง่ายดาย, ตรวจสอบ *actual cost of work*, และเฝ้าดู *budgeted cost work performed* และ *schedule variance*. ระดับของข้อมูลเชิงลึกนี้ทำให้การจัดการค่าใช้จ่ายโครงการฉลาดขึ้นและช่วยให้คุณอยู่ในงบประมาณและตามกำหนดเวลา.

## FAQ's
### Q: ฉันสามารถใช้ Aspose.Tasks for Java เพื่อคำนวณค่าใช้จ่ายของ resource assignment แบบไดนามิกได้หรือไม่?
A: ใช่, คุณสามารถคำนวณค่าใช้จ่ายของ assignment แบบไดนามิกโดยใช้ Aspose.Tasks for Java API.  
### Q: Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการทั้งหมดหรือไม่?
A: Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการต่างๆ รวมถึง MPP, XML, และ MPX.  
### Q: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้อย่างไร?
A: คุณสามารถรับการสนับสนุนโดยไปที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) หรือ ติดต่อฝ่ายสนับสนุนของ Aspose โดยตรง.  
### Q: ฉันสามารถลองใช้ Aspose.Tasks for Java ก่อนซื้อได้หรือไม่?
A: ใช่, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [website](https://releases.aspose.com/).  
### Q: ฉันต้องการไลเซนส์ชั่วคราวสำหรับการใช้ Aspose.Tasks for Java ในช่วงทดลองหรือไม่?
A: ไม่, ไม่จำเป็นต้องมีไลเซนส์ชั่วคราวสำหรับการใช้งานทดลอง. อย่างไรก็ตามแนะนำให้ใช้สำหรับสภาพแวดล้อมการผลิต.

## Frequently Asked Questions

**Q: ฉันจะส่งออก Cost Variance ที่คำนวณแล้วไปยังรายงาน Excel อย่างไร?**  
A: หลังจากวนลูปผ่าน assignments, คุณสามารถใช้ Aspose.Cells เพื่อเขียนค่าลงในสเปรดชีต, โดยแมป ID ของแต่ละ assignment ไปยัง CV ของมัน.

**Q: สามารถกรอง assignments ตาม resource เฉพาะก่อนคำนวณ variance ได้หรือไม่?**  
A: ใช่, คุณสามารถใช้ `project.getResourceAssignments().where(ra -> ra.getResource().getUid() == desiredResourceId)` เพื่อจำกัดลูป.

**Q: CV ที่เป็นค่าลบหมายถึงอะไร?**  
A: CV ที่เป็นค่าลบหมายถึงค่าใช้จ่ายจริง (ACWP) มากกว่ามูลค่าได้ (BCWP), บ่งชี้ว่ามีการเกินงบที่ควรตรวจสอบ.

**Q: ฉันสามารถอัปเดตฟิลด์ค่าใช้จ่ายโดยโปรแกรมและจากนั้นบันทึกโครงการได้หรือไม่?**  
A: แน่นอน. ใช้ `ra.set(Asn.COST, new BigDecimal("1500"))` แล้วเรียก `project.save("updated.mpp")`.

**Q: Aspose.Tasks จะจัดการการแปลงสกุลเงินโดยอัตโนมัติหรือไม่?**  
A: ไลบรารีเก็บค่าตัวเลขดิบ; คุณต้องทำการแปลงสกุลเงินที่จำเป็นด้วยตนเองก่อนการแสดงผล.

---

**อัปเดตล่าสุด:** 2026-01-02  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}