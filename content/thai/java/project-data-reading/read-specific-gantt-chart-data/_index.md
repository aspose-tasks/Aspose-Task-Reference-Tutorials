---
title: อ่านข้อมูลแผนภูมิแกนต์เฉพาะใน Aspose.Tasks
linktitle: อ่านข้อมูลแผนภูมิแกนต์เฉพาะใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีแยกข้อมูลแผนภูมิ Gantt เฉพาะโดยใช้ Aspose.Tasks สำหรับ Java บทช่วยสอนทีละขั้นตอนสำหรับการผสานรวมเข้ากับแอปพลิเคชัน Java ของคุณอย่างราบรื่น
type: docs
weight: 16
url: /th/java/project-data-reading/read-specific-gantt-chart-data/
---
## การแนะนำ
แผนภูมิแกนต์เป็นเครื่องมืออันล้ำค่าสำหรับการจัดการโครงการ ช่วยให้ผู้ใช้สามารถเห็นภาพงาน ไทม์ไลน์ และการพึ่งพาได้ ด้วย Aspose.Tasks สำหรับ Java นักพัฒนาสามารถดึงข้อมูลเฉพาะจากแผนภูมิแกนต์เพื่อรวมเข้ากับแอปพลิเคชันได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการอ่านข้อมูลแผนภูมิแกนต์ที่เฉพาะเจาะจงทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ตามที่คุณต้องการ ตัวเลือกยอดนิยม ได้แก่ IntelliJ IDEA, Eclipse หรือ NetBeans

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:
```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
เริ่มต้นด้วยการโหลดไฟล์โครงการที่มีข้อมูลแผนภูมิแกนต์ ระบุเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณและระบุชื่อไฟล์
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```
## ขั้นตอนที่ 2: เข้าถึงมุมมองแผนภูมิแกนต์
ดึงข้อมูลมุมมองแผนภูมิแกนต์จากโครงการ เราจะถือว่านี่เป็นมุมมองแรกในรายการ
```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```
## ขั้นตอนที่ 3: แยกคุณสมบัติมุมมอง
ตอนนี้ เราจะแยกคุณสมบัติต่างๆ ของมุมมองแผนภูมิ Gantt แล้วพิมพ์ออกมาเพื่อตรวจสอบ
```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// ดำเนินการต่อคุณสมบัติอื่น ๆ ...
```
## ขั้นตอนที่ 4: แยกสไตล์บาร์
วนซ้ำสไตล์แท่งในมุมมองแผนภูมิ Gantt แล้วพิมพ์รายละเอียด
```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // รายละเอียดแบบแถบพิมพ์...
}
```
## ขั้นตอนที่ 5: แยกเส้นตาราง
ดึงและพิมพ์ข้อมูลเกี่ยวกับเส้นตารางในมุมมองแผนภูมิแกนต์
```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// พิมพ์รายละเอียดเส้นตาราง...
```
## ขั้นตอนที่ 6: แยกลักษณะข้อความ
ดึงและพิมพ์ลักษณะข้อความที่ใช้ในมุมมองแผนภูมิแกนต์
```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // พิมพ์รายละเอียดรูปแบบข้อความ...
}
```
## ขั้นตอนที่ 7: แยกเส้นความคืบหน้า
เข้าถึงและพิมพ์คุณสมบัติของเส้นความคืบหน้าในมุมมองแผนภูมิแกนต์
```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// พิมพ์รายละเอียดความคืบหน้าอื่นๆ...
```
## ขั้นตอนที่ 8: แยกระดับไทม์สเกล
ดึงและพิมพ์ข้อมูลเกี่ยวกับระดับมาตราส่วนเวลาในมุมมองแผนภูมิแกนต์
```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// พิมพ์รายละเอียดของระดับช่วงเวลาอื่นๆ...
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีอ่านข้อมูลแผนภูมิ Gantt ที่เฉพาะเจาะจงโดยใช้ Aspose.Tasks สำหรับ Java เรียบร้อยแล้ว เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถแยกและจัดการข้อมูลแผนภูมิแกนต์ภายในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับไลบรารี Java อื่นๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java ได้รับการออกแบบมาเพื่อผสานรวมกับไลบรารีและเฟรมเวิร์ก Java อื่นๆ ได้อย่างราบรื่น
### ถาม: Aspose.Tasks เหมาะสำหรับโครงการระดับองค์กรขนาดใหญ่หรือไม่
ตอบ: อย่างแน่นอน Aspose.Tasks นำเสนอคุณสมบัติที่แข็งแกร่งและประสิทธิภาพที่ยอดเยี่ยม ทำให้เหมาะสำหรับโครงการทุกขนาด
### ถาม: Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลายรูปแบบหรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP, XML และ MPX
### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์ของแผนภูมิแกนต์ด้วย Aspose.Tasks ได้หรือไม่
ตอบ: แน่นอน Aspose.Tasks มี API มากมายสำหรับปรับแต่งลักษณะแผนภูมิ Gantt ตามความต้องการของคุณ
### ถาม: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
ตอบ: ใช่ Aspose.Tasks ให้การสนับสนุนด้านเทคนิคอย่างครอบคลุมผ่านทางฟอรัมและช่องทางการสนับสนุนเฉพาะ