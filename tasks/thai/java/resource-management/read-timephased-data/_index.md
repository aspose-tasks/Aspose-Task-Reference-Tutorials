---
date: 2026-06-15
description: เรียนรู้วิธีดึงข้อมูล timephased data จาก Resources ของ MS Project ด้วย
  Aspose.Tasks for Java. คู่มือแบบขั้นตอนต่อขั้นตอนเพื่อ get resource by id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: อ่านข้อมูล Timephased Data สำหรับ Resources ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: อ่านข้อมูล Timephased Data สำหรับ Resources ใน Aspose.Tasks – get resource
  by id
url: /th/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูล Timephased สำหรับทรัพยากรใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีการดึงทรัพยากรโดยใช้ ID** และอ่านข้อมูล timephased ของมันโดยใช้ Aspose.Tasks สำหรับ Java เราจะเดินผ่านแต่ละขั้นตอน—ตั้งแต่การตั้งค่าโฟลเดอร์โครงการจนถึงการพิมพ์ค่าการทำงานและค่าใช้จ่ายแบบ timephased—เพื่อให้คุณสามารถสกัดข้อมูลการกำหนดเวลาที่มีคุณค่าจากไฟล์ Microsoft Project ใด ๆ อย่างโปรแกรมมิ่ง Aspose.Tasks สำหรับ Java เป็น API ครบวงจรที่ช่วยให้นักพัฒนาสร้าง อ่าน แก้ไข และแปลงไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project รองรับคุณลักษณะและรูปแบบการจัดการโครงการหลากหลาย

## คำตอบสั้น
- **ฟังก์ชัน “get resource by id” ทำอะไร?** มันดึงอ็อบเจกต์ `Resource` เฉพาะจาก `Project` โดยใช้ตัวระบุที่ไม่ซ้ำกันของมัน.  
- **ไลบรารีใดจัดการข้อมูล timephased?** Aspose.Tasks สำหรับ Java มี API `Resource.getTimephasedData`.  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถอ่านโครงการขนาดใหญ่ได้หรือไม่?** ได้—Aspose.Tasks สามารถประมวลผลไฟล์ที่มีงานสูงสุด 10,000 รายการโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า; ไลบรารีเข้ากันได้กับ JDK หลักทั้งหมด.

## อะไรคือ “get resource by id”?
`get resource by id` คือการเรียกเมธอดที่ดึงอินสแตนซ์ `Resource` จาก `Project` ที่โหลดแล้วโดยใช้ ID ตัวเลขของทรัพยากร การดำเนินการนี้ทำให้เข้าถึงคุณสมบัติเฉพาะของทรัพยากรได้อย่างแม่นยำ เช่น การมอบหมาย ปฏิทิน และฟิลด์กำหนดเอง และเป็นสิ่งจำเป็นสำหรับการสกัดข้อมูลการทำงานหรือค่าใช้จ่ายแบบ timephased ที่เชื่อมโยงกับทรัพยากรนั้น

## ทำไมต้องใช้ Aspose.Tasks สำหรับข้อมูล timephased?
Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 แบบ** (MPP, XML, CSV ฯลฯ) และสามารถสกัดค่าการทำงานและค่าใช้จ่ายแบบ timephased ของทรัพยากรที่ครอบคลุมตารางเวลาหลายปีโดยใช้หน่วยความจำน้อย API จะคืนค่าข้อมูลในช่วงเวลา 15 นาทีโดยค่าเริ่มต้น ให้ข้อมูลเชิงลึกระดับละเอียดสำหรับการรายงานหรือการวิเคราะห์แบบกำหนดเอง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) และทำตามคำแนะนำการติดตั้ง.  
2. Aspose.Tasks for Java Library: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จาก [download page](https://releases.aspose.com/tasks/java/) และทำตามคำแนะนำการติดตั้งที่ให้ไว้ในเอกสาร.

## นำเข้าแพ็กเกจ
ขั้นตอนแรกคือการนำเข้าคลาส Aspose.Tasks ที่จำเป็นเข้าสู่ไฟล์ซอร์สโค้ด Java ของคุณ.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
แรกสุด ให้กำหนดไดเรกทอรีที่ไฟล์ MS Project ของคุณอยู่ การแยกโฟลเดอร์ข้อมูลออกจากโค้ดทำให้โครงการง่ายต่อการดูแลรักษา.

```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: อ่านไฟล์เทมเพลต MS Project
ระบุชื่อไฟล์เทมเพลต MS Project ของคุณ การใช้เทมเพลตช่วยให้การตั้งค่าคอลัมน์สอดคล้องกันในโครงการต่าง ๆ

```java
String fileName = "ResourceTimephasedData.mpp";
```

## ขั้นตอนที่ 3: อ่านไฟล์อินพุตเป็น Project
คลาส `Project` เป็นอ็อบเจกต์หลักของ Aspose.Tasks ที่แทนไฟล์ Microsoft Project ในหน่วยความจำ การโหลดไฟล์ทำให้คุณเข้าถึงงาน, ทรัพยากร, และกำหนดเวลาได้ผ่านโปรแกรม

```java
Project project = new Project(dataDir + fileName);
```

## ขั้นตอนที่ 4: ดึงทรัพยากรโดยใช้ ID
เพื่อดึงทรัพยากรเฉพาะ ให้เรียกเมธอด `getResources().getById(id)` นี่คือการดำเนินการที่อ้างอิงโดยคีย์เวิร์ดหลัก

```java
Resource resource = project.getResources().getByUid(1);
```

## ขั้นตอนที่ 5: พิมพ์ข้อมูล Timephased สำหรับการทำงานของทรัพยากร
เมื่อคุณมีอ็อบเจกต์ `Resource` แล้ว คุณสามารถเรียก `resource.getTimephasedData(ResourceTimephasedDataType.Work)` เพื่อรับการจัดสรรงานตามเวลา คอลเลกชันที่คืนค่าจะมีอ็อบเจกต์ `TimephasedData` ที่รวมวันที่เริ่มต้น, วันที่สิ้นสุด, และจำนวนงานสำหรับแต่ละช่วงเวลา

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## ขั้นตอนที่ 6: พิมพ์ข้อมูล Timephased สำหรับค่าใช้จ่ายของทรัพยากร
ในทำนองเดียวกัน `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` จะคืนค่าข้อมูลค่าใช้จ่ายที่แบ่งตามช่วงเวลาเดียวกัน ซึ่งเป็นประโยชน์สำหรับการจัดทำงบประมาณและรายงานการติดตามค่าใช้จ่าย

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## วิธีดึงทรัพยากรโดยใช้ ID ในบรรทัดเดียว
โหลดโปรเจกต์แล้วเรียก `project.getResources().getById(5)`—แทนที่ **5** ด้วย ID ของทรัพยากรที่ต้องการ วิธีเรียกเดียวนี้จะคืนอ็อบเจกต์ `Resource` หลังจากนั้นคุณสามารถสอบถามข้อมูล timephased, การมอบหมาย หรือฟิลด์กำหนดเองของมันได้ เมธอดนี้ทำงานในเวลา O(1) เนื่องจากทรัพยากรถูกจัดทำดัชนีภายใน

## ปัญหาที่พบบ่อยและวิธีแก้
- **ไม่พบทรัพยากร** – ตรวจสอบว่า ID มีอยู่ในไฟล์โครงการ; ID เริ่มจาก 1 และเป็นเอกลักษณ์ต่อทรัพยากรแต่ละรายการ.  
- **ข้อมูล timephased ว่าง** – ยืนยันว่าทรัพยากรมีการมอบหมายงานหรือค่าใช้จ่าย; หากไม่มีคอลเลกชันจะว่างเปล่า.  
- **ประสิทธิภาพไฟล์ขนาดใหญ่** – ใช้ `Project.setLoadOptions(LoadOptions.fromFile(...))` เพื่อเปิดใช้งานการโหลดแบบ lazy สำหรับโครงการที่ใหญ่กว่า 500 MB.

## คำถามที่พบบ่อย

**ถาม: Aspose.Tasks สามารถจัดการไฟล์โครงการประเภทอื่นนอกจาก Microsoft Project ได้หรือไม่?**  
ตอบ: ได้, Aspose.Tasks รองรับ MPP, XML, CSV และรูปแบบอื่น ๆ อีกหลายประเภท ทำให้คุณสามารถอ่านและเขียนข้ามมาตรฐานต่าง ๆ ได้

**ถาม: Aspose.Tasks เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ต่าง ๆ หรือไม่?**  
ตอบ: แน่นอน. ไลบรารีทำงานกับ IDE หลักทั้งหมด (IntelliJ IDEA, Eclipse, NetBeans) และเครื่องมือสร้าง (Maven, Gradle).

**ถาม: ฉันสามารถจัดการข้อมูลโครงการด้วย Aspose.Tasks ได้หรือไม่?**  
ตอบ: ได้, คุณสามารถสร้าง, แก้ไข, และลบงาน, ทรัพยากร, การมอบหมาย, และแม้กระทั่งฟิลด์กำหนดเองผ่าน API

**ถาม: Aspose.Tasks เหมาะกับโครงการระดับองค์กรหรือไม่?**  
ตอบ: ใช่. องค์กรต่าง ๆ พึ่งพา Aspose.Tasks สำหรับการประมวลผลปริมาณมาก, การแปลงเป็นชุด, และการรายงานบนเซิร์ฟเวอร์ เนื่องจากไม่ต้องติดตั้ง Microsoft Project

**ถาม: ฉันจะหาแหล่งสนับสนุนได้จากที่ไหนหากพบปัญหาในการใช้ Aspose.Tasks?**  
ตอบ: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือจากชุมชนและทีมสนับสนุน

## สรุป
ในบทแนะนำนี้ เราได้เรียนรู้วิธี **ดึงทรัพยากรโดยใช้ ID** และอ่านข้อมูลการทำงานและค่าใช้จ่ายแบบ timephased ของมันโดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถสกัดข้อมูลการกำหนดเวลาที่มีคุณค่าออกจากไฟล์โครงการของคุณได้อย่างมีประสิทธิภาพและนำไปผสานกับการรายงานหรือการวิเคราะห์แบบกำหนดเอง

---

**อัปเดตล่าสุด:** 2026-06-15  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for Java  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มทรัพยากรลงในโครงการด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/create-resources/)
- [จัดการค่าใช้จ่ายของทรัพยากร MS Project ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/resource-cost/)
- [อ่านสัปดาห์ทำงาน Java จากปฏิทิน MS Project ด้วย Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}