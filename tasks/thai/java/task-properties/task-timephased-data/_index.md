---
date: 2026-02-28
description: เรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อจัดการข้อมูลเวลาแบบขั้นตอนของงาน
  ดาวน์โหลดไลบรารี ทดลองใช้งานฟรี และทำให้การติดตามโครงการเป็นระบบง่ายขึ้น
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีใช้ Aspose.Tasks เพื่อจัดการข้อมูลการทำงานตามช่วงเวลา (Java)
url: /th/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ Aspose.Tasks สำหรับข้อมูลแบบ Timephased ของงาน

## Introduction
หากคุณกำลังมองหา **วิธีใช้ Aspose** เพื่อควบคุมกำหนดการโครงการของคุณอย่างแน่นหนา คุณมาถูกที่แล้ว การติดตามข้อมูลแบบ timephased ของงานอย่างแม่นยำเป็นรากฐานของการจัดการโครงการที่ประสบความสำเร็จ และ Aspose.Tasks for Java ให้เครื่องมือที่คุณต้องการเพื่อทำกระบวนการนี้อัตโนมัติ ในบทแนะนำนี้เราจะเดินผ่านตัวอย่างครบวงจรจากต้นจนจบที่แสดงวิธีใช้ Aspose.Tasks เพื่อสร้างโครงการ กำหนดทรัพยากร ตั้ง baseline และสุดท้ายดึงและแสดงข้อมูลแบบ timephased

## Quick Answers
- **ข้อมูลแบบ “timephased” หมายถึงอะไร?** เป็นข้อมูลที่แยกตามช่วงเวลา (วัน, สัปดาห์, เดือน) ที่แสดงปริมาณงาน, ค่าใช้จ่าย หรืองานที่เหลืออยู่ตลอดระยะเวลาโครงการ  
- **ไลบรารีใดที่ให้ความสามารถนี้?** Aspose.Tasks for Java.  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** การทดลองใช้งานฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **ต้องใช้ Java เวอร์ชันใด?** Java 8 หรือสูงกว่า  
- **ฉันสามารถส่งออกผลลัพธ์ไปยัง Excel ได้หรือไม่?** ได้ – คุณสามารถวนลูปคอลเลกชัน `TimephasedData` และเขียนค่าไปยังรูปแบบใดก็ได้ที่ต้องการ  

## What is Task Timephased Data?
ข้อมูลแบบ timephased ของงานแสดงปริมาณงาน (หรือค่าใช้จ่าย) ที่กำหนดไว้สำหรับงานในแต่ละช่วงเวลาของปฏิทินโครงการ มันช่วยให้คุณเห็นการกระจายงาน, ตรวจจับการจัดสรรเกิน, และเปรียบเทียบแผนกับความคืบหน้าจริง

## Why Use Aspose.Tasks to Manage Timephased Data?
- **Full control** – สร้าง, แก้ไข, และสอบถามข้อมูลแบบ timephased ผ่านโปรแกรมโดยไม่ต้องเปิด Microsoft Project  
- **Cross‑platform** – ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java  
- **No COM dependencies** – เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์  
- **Rich API** – รองรับ baseline, work contour, และ custom fields โดยตรง  

## Prerequisites
ก่อนจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

- **Java Development Environment** – ติดตั้ง JDK 8+ และกำหนดค่า `JAVA_HOME`  
- **Aspose.Tasks for Java Library** – ดาวน์โหลดและรวมไลบรารี Aspose.Tasks ในโครงการของคุณ คุณสามารถหาไลบรารีได้จาก [here](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – โฟลเดอร์บนเครื่องของคุณที่ไฟล์โครงการตัวอย่าง (`project.xml`) จะถูกอ่านและเขียน  

## Import Packages
ในโครงการ Java ของคุณ, ให้นำเข้าคลาส Aspose.Tasks ที่จำเป็น:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* เราสร้างอินสแตนซ์ `Project`, เริ่มต้น `Calendar` ไปยังวันที่เริ่มต้นที่ต้องการ, และกำหนดให้กับ property `START_DATE` ของโครงการ  

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* งานใหม่ชื่อ **Task** ถูกเพิ่มภายใต้งานราก เรายังสร้างทรัพยากรชื่อ **Rsc** และตั้งอัตรามาตรฐานและอัตรา overtime  

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* งานนี้ถูกกำหนดระยะเวลาเป็น **6 days**  

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* ทรัพยากรที่กำหนดไว้ก่อนหน้านี้ถูกเชื่อมโยงกับงานผ่าน `ResourceAssignment`  

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* เราตั้งค่าวันที่หยุดและวันที่เริ่มใหม่ของการมอบหมาย (ใช้ค่า placeholder) และใช้ work contour แบบ **Back‑Loaded** ซึ่งทำให้มีงานมากขึ้นที่ส่วนท้ายของการมอบหมาย  

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* การบันทึก baseline ทำให้คุณสามารถเปรียบเทียบค่าที่วางแผนกับค่าจริงในภายหลัง  

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* งานนี้ถูกทำเครื่องหมายว่า **50 % complete**, ซึ่งจะมีผลต่อการคำนวณงานที่เหลืออยู่  

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* การเรียกนี้ดึง **remaining work** ของการมอบหมาย, แยกตามช่วงเวลาของโครงการ  

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* เราเพียงพิมพ์จำนวนรายการ timephased และค่าของรายการแรก ในสถานการณ์จริงคุณจะวนลูปรายการและส่งออกข้อมูลไปยังรายงานหรือ UI  

## Common Issues and Solutions
- **NullPointerException on `getTimephasedData`** – ตรวจสอบให้แน่ใจว่าได้ตั้งค่าวันที่ `START` และ `FINISH` ของการมอบหมายก่อนเรียกเมธอด  
- **Incorrect work contour** – ตรวจสอบว่า `WorkContourType` ที่เลือกตรงกับกลยุทธ์การกำหนดเวลา; `BackLoaded` เป็นเพียงหนึ่งในหลายตัวเลือก  
- **Baseline not reflecting changes** – จำไว้ว่าต้องเรียก `project.setBaseline` *หลังจาก* ที่คุณได้กำหนดงาน, ทรัพยากร, และการมอบหมายแล้ว  

## Frequently Asked Questions
### Q: ฉันสามารถใช้ Aspose.Tasks for Java ในโครงการ Java ใดก็ได้หรือไม่?
A: ใช่, Aspose.Tasks for Java เข้ากันได้กับโครงการที่ใช้ Java ใดก็ได้  

### Q: ฉันสามารถหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
A: เยี่ยมชม [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนและการสนทนา  

### Q: มีการทดลองใช้งานฟรีสำหรับ Aspose.Tasks for Java หรือไม่?
A: มี, คุณสามารถสำรวจการทดลองใช้งานฟรีได้ [here](https://releases.aspose.com/).  

### Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?
A: คุณสามารถรับลิขสิทธิ์ชั่วคราวได้ [here](https://purchase.aspose.com/temporary-license/).  

### Q: ฉันสามารถซื้อ Aspose.Tasks for Java ได้จากที่ไหน?
A: คุณสามารถซื้อ Aspose.Tasks for Java ได้ [here](https://purchase.aspose.com/buy).  

---

**อัปเดตล่าสุด:** 2026-02-28  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}