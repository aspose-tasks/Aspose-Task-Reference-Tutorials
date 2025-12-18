---
date: 2025-12-18
description: เรียนรู้วิธีสร้างมุมมองใน Aspose.Tasks สำหรับ Java รวมถึงวิธีบันทึกมุมมองโครงการและตั้งค่าคุณสมบัติมุมมอง
  เพิ่มประสิทธิภาพการจัดการโครงการด้วยมุมมอง MS Project ที่กำหนดเองตามความต้องการ
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'วิธีสร้างมุมมอง: มุมมอง MS Project แบบกำหนดเองใน Aspose.Tasks'
url: /th/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างมุมมอง: มุมมอง MS Project แบบกำหนดเองใน Aspose.Tasks

## Introduction
หากคุณกำลังมองหา **how to create view** ที่ตรงกับความต้องการการรายงานที่เป็นเอกลักษณ์ของโครงการของคุณ คุณมาถูกที่แล้ว ในการจัดการโครงการ การปรับแต่งมุมมองสามารถเพิ่มความชัดเจนและประสิทธิภาพอย่างมากเมื่อจัดการงานและทรัพยากร **Aspose.Tasks for Java** มอบ API ที่ครบถ้วนให้คุณเพื่อ **add custom view java**‑style solutions ทำให้คุณสามารถปรับแต่งมุมมอง MS Project ได้ตามที่ต้องการ ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทีละขั้นตอน ตั้งแต่การตั้งค่าโครงการจนถึงการบันทึกมุมมองโครงการ

## Quick Answers
- **What is the primary purpose?** เพื่อสร้างและบันทึกมุมมอง MS Project แบบกำหนดเองโดยใช้ Aspose.Tasks for Java.  
- **Which class creates a view?** คลาสที่สร้างมุมมองคือ `GanttChartView` (หรือประเภทมุมมองอื่นๆ).  
- **How do I make the view appear in the menu?** ตั้งค่า `view.setShowInMenu(true)`.  
- **How can I save the view with the project?** ใช้ `MPPSaveOptions` พร้อม `setWriteViewData(true)`.  
- **Do I need a license?** ใช่ จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

## Prerequisites
ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### Java Development Environment
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว.

### Aspose.Tasks for Java
ดาวน์โหลดและติดตั้ง Aspose.Tasks for Java จาก [here](https://releases.aspose.com/tasks/java/).

## Import Packages
ขั้นแรก ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Step 1: Set Up Project
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Step 2: Create View
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Step 3: Customize View Properties *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### How to Show View Menu
การเรียก `view.setShowInMenu(true)` ทำให้มั่นใจว่ามุมมองที่สร้างใหม่จะแสดงใน **view menu** ของ MS Project ให้ผู้ใช้เข้าถึงได้อย่างรวดเร็ว.

## Step 4: Tune View Settings
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Step 5: Add View to Project *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Step 6: Save Project *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Why Saving the Project View Matters
การตั้งค่า `options.setWriteViewData(true)` บอกให้ Aspose.Tasks **save project view** ข้อมูลภายในไฟล์ MPP ทำให้มุมมองที่กำหนดเองคงอยู่ระหว่างเซสชัน.

## Step 7: Check View Properties
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Common Use Cases
- **Stakeholder Reporting:** สร้างมุมมองที่แสดงเฉพาะไมล์สโตนระดับสูงและงานที่สำคัญ.  
- **Resource Allocation:** สร้างมุมมองที่แสดงรายการทรัพยากรพร้อมงานที่มอบหมายเพื่อการตรวจสอบความจุอย่างรวดเร็ว.  
- **Print‑Ready Documents:** ปรับตั้งค่าหน้ากระดาษ (ตามขั้นตอนที่ 4) เพื่อสร้างภาพสแนปช็อตของโครงการที่พร้อมพิมพ์.

## Troubleshooting Tips
- **View Not Appearing in Menu:** ตรวจสอบว่าได้เรียก `view.setShowInMenu(true)` ก่อนทำการบันทึก.  
- **Missing Columns in Printout:** ตรวจสอบว่า `setFirstColumnsCount` ตรงกับคอลัมน์ที่ต้องการและเปิดใช้งาน `setPrintFirstColumnsCountOnAllPages(true)`.  
- **License Exceptions:** หากพบข้อผิดพลาดเกี่ยวกับใบอนุญาต ให้ยืนยันว่าไฟล์ใบอนุญาต Aspose.Tasks ที่ถูกต้องได้ถูกโหลดก่อนสร้างอ็อบเจ็กต์ `Project`.

## Frequently Asked Questions
### Q1: ฉันสามารถปรับแต่งมุมมองนอกเหนือจากแผนภูมิ Gantt ได้หรือไม่?
A: ใช่, Aspose.Tasks for Java มีความยืดหยุ่นในการปรับแต่งประเภทมุมมองต่างๆ นอกเหนือจากแผนภูมิ Gantt รวมถึงตารางและกราฟ.

### Q2: Aspose.Tasks for Java เหมาะกับโครงการขนาดใหญ่หรือไม่?
A: แน่นอน. ไลบรารีนี้ออกแบบมาเพื่อจัดการโครงการทุกขนาด พร้อมประสิทธิภาพและการจัดการหน่วยความจำที่แข็งแกร่ง.

### Q3: Aspose.Tasks for Java รองรับการส่งออกมุมมองเป็นรูปแบบต่างๆ หรือไม่?
A: ใช่, คุณสามารถส่งออกมุมมองเป็น PDF, XLSX, HTML และรูปแบบอื่นๆ เพื่อการแชร์ที่ราบรื่นระหว่างแพลตฟอร์ม.

### Q4: ฉันสามารถทำอัตโนมัติการสร้างมุมมองแบบกำหนดเองด้วย Aspose.Tasks for Java ได้หรือไม่?
A: แน่นอน. API ช่วยให้ทำอัตโนมัติเต็มรูปแบบ สามารถสร้างและจัดการมุมมองแบบกำหนดเองโดยโปรแกรมได้.

### Q5: มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.Tasks for Java หรือไม่?
A: มี, คุณสามารถขอความช่วยเหลือและสนทนากับผู้ใช้คนอื่นได้ใน [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) สำหรับคำถามและการสนทนาที่เกี่ยวกับ Java.

**อัปเดตล่าสุด:** 2025-12-18  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}