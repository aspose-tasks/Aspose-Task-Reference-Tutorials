---
title: สร้างมุมมองโครงการ MS แบบกำหนดเองใน Aspose.Tasks
linktitle: มุมมองที่กำหนดเองใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีสร้างมุมมอง MS Project แบบกำหนดเองได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ Java เพิ่มประสิทธิภาพการจัดการโครงการด้วยมุมมองที่ปรับแต่ง
type: docs
weight: 24
url: /th/java/project-file-operations/custom-views/
---
## การแนะนำ
ในการจัดการโครงการ การปรับแต่งมุมมองสามารถเพิ่มความชัดเจนและประสิทธิภาพของการจัดการงานและทรัพยากรได้อย่างมาก Aspose.Tasks for Java มอบเครื่องมืออันทรงพลังเพื่อสร้างมุมมองแบบกำหนดเองที่ปรับให้เหมาะกับความต้องการเฉพาะของโปรเจ็กต์ ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างมุมมอง MS Project แบบกำหนดเองโดยใช้ Aspose.Tasks สำหรับ Java ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### สภาพแวดล้อมการพัฒนาจาวา
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
### Aspose.Tasks สำหรับ Java
 ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
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
ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
// สร้างโปรเจ็กต์ว่างโดยไม่มีการดู
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
## ขั้นตอนที่ 2: สร้างมุมมอง
```java
// สร้างมุมมองแผนภูมิแกนต์มาตรฐาน
View view = new GanttChartView();
```
## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติมุมมอง
```java
// ตั้งค่าคุณสมบัติมุมมองบางอย่าง
view.setShowInMenu(true); // ระบุว่าจะแสดงมุมมองในเมนูหรือไม่
view.setHighlightFilter(true); // ระบุว่าจะเน้นตัวกรองสำหรับมุมมองหรือไม่
```
## ขั้นตอนที่ 4: ปรับแต่งการตั้งค่ามุมมอง
```java
// ปรับการตั้งค่ามุมมองบางอย่าง
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // กำหนดจำนวนคอลัมน์แรกที่จะพิมพ์ในทุกหน้า
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // ระบุว่าจะพิมพ์ตามจำนวนคอลัมน์แรกที่ระบุในทุกหน้าหรือไม่
```
## ขั้นตอนที่ 5: เพิ่มมุมมองให้กับโครงการ
```java
// เพิ่มมุมมองให้กับโครงการของเรา
project.getViews().add(view);
```
## ขั้นตอนที่ 6: บันทึกโครงการ
```java
// บันทึกโครงการด้วยมุมมองที่สร้างขึ้น
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // ใช้การตั้งค่าสถานะ WriteViewData เพื่อคงการแก้ไขโครงการ Views
project.save(dataDir + "workWithView_output.mpp", options);
```
## ขั้นตอนที่ 7: ตรวจสอบคุณสมบัติมุมมอง
```java
// ตรวจสอบคุณสมบัติของมุมมองที่เพิ่มใหม่
System.out.println("View Uid: " + view.getUid()); // พิมพ์ตัวระบุเฉพาะของมุมมอง
System.out.println("View Screen: " + view.getScreen()); // พิมพ์ประเภทหน้าจอสำหรับมุมมอง
System.out.println("View Type: " + view.getType()); // พิมพ์ประเภทของมุมมอง
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // พิมพ์โครงการหลักของมุมมอง
```
## บทสรุป
มุมมองโครงการ MS แบบกำหนดเองนำเสนอวิธีที่ยืดหยุ่นในการแสดงภาพข้อมูลโครงการตามความต้องการเฉพาะ ด้วย Aspose.Tasks สำหรับ Java การสร้างมุมมองแบบกำหนดเองจะตรงไปตรงมา ช่วยให้ผู้จัดการโครงการปรับปรุงขั้นตอนการทำงานได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถปรับแต่งมุมมองนอกเหนือจากแผนภูมิแกนต์ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ Java มอบความยืดหยุ่นในการปรับแต่งมุมมองประเภทต่างๆ นอกเหนือจากแผนภูมิ Gantt รวมถึงตารางและกราฟ
### คำถามที่ 2: Aspose.Tasks สำหรับ Java เหมาะสำหรับโปรเจ็กต์ขนาดใหญ่หรือไม่
ตอบ: อย่างแน่นอน Aspose.Tasks สำหรับ Java ได้รับการออกแบบมาเพื่อรองรับโปรเจ็กต์ทุกขนาด โดยนำเสนอฟีเจอร์ที่แข็งแกร่งสำหรับการจัดการโปรเจ็กต์ที่มีประสิทธิภาพ
### คำถามที่ 3: Aspose.Tasks สำหรับ Java รองรับการส่งออกมุมมองเป็นรูปแบบที่แตกต่างกันหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับการส่งออกมุมมองเป็นรูปแบบต่างๆ เช่น PDF, XLSX และ HTML เพื่อให้มั่นใจว่าเข้ากันได้กับแพลตฟอร์มที่แตกต่างกัน
### คำถามที่ 4: ฉันสามารถสร้างมุมมองแบบกำหนดเองโดยอัตโนมัติโดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่
ตอบ: แน่นอน Aspose.Tasks for Java มอบ API ที่ครอบคลุมสำหรับระบบอัตโนมัติ ช่วยให้นักพัฒนาสามารถสร้างและจัดการมุมมองแบบกำหนดเองทางโปรแกรมได้ตามต้องการ
### คำถามที่ 5: มีฟอรัมชุมชนสำหรับ Aspose.Tasks สำหรับการสนับสนุน Java หรือไม่
 ตอบ: ได้ คุณสามารถค้นหาความช่วยเหลือและมีส่วนร่วมกับผู้ใช้รายอื่นได้ใน[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสอบถามและการสนทนาที่เกี่ยวข้องกับ Java