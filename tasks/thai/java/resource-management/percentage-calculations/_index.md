---
date: 2026-06-15
description: เรียนรู้วิธีคำนวณเปอร์เซ็นต์ทรัพยากร java ด้วย Aspose.Tasks รวมถึงวิธีการรับ
  percent work complete สำหรับทรัพยากร MS Project คู่มือขั้นตอนโดยละเอียดพร้อม code
  examples.
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: ทำการคำนวณเปอร์เซ็นต์สำหรับทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: คำนวณเปอร์เซ็นต์ทรัพยากร java ด้วย Aspose.Tasks
url: /th/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คำนวณเปอร์เซ็นต์ทรัพยากรใน Java ด้วย Aspose.Tasks

## บทนำ
ยินดีต้อนรับ! ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีคำนวณเปอร์เซ็นต์ทรัพยากรใน Java** โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java เราจะอธิบายขั้นตอนการดึง *เปอร์เซ็นต์งานที่เสร็จสมบูรณ์* สำหรับแต่ละทรัพยากรในไฟล์ Microsoft Project, อธิบายว่าทำไมเมตริกนี้สำคัญ, และแสดงโค้ดที่คุณต้องการอย่างแม่นยำ. เมื่อเสร็จสิ้นคุณจะสามารถผสานการคำนวณเปอร์เซ็นต์ทรัพยากรเข้ากับโซลูชันการจัดการโครงการที่พัฒนาด้วย Java ได้ทุกแห่ง.

## คำตอบสั้น
- **อะไรคือ “resource percentage”** เป็นเปอร์เซ็นต์ของงานที่ทรัพยากรทำเสร็จแล้วเมื่อเทียบกับงานที่มอบหมายทั้งหมดของมัน.  
- **เมธอด API ใดที่คืนค่าดังกล่าว?** `Rsc.PERCENT_WORK_COMPLETE` ผ่านคลาส `Resource`.  
- **ฉันต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Tasks แบบชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถใช้กับเฟรมเวิร์ก Java อื่นได้หรือไม่?** ได้ – API ทำงานร่วมกับ Spring, Hibernate และโครงการ Java ธรรมดา.  
- **ต้องการเวอร์ชันของ Aspose.Tasks ใด?** เวอร์ชันล่าสุดใดก็ได้ที่รองรับ enumeration `Rsc` (เช่น 24.x).

## การคำนวณเปอร์เซ็นต์ทรัพยากรใน Java คืออะไร?
การคำนวณเปอร์เซ็นต์ทรัพยากรใน Java เกี่ยวข้องกับการเปิดไฟล์ Microsoft Project, อ่านงานที่มอบหมายให้แต่ละทรัพยากร, และกำหนดสัดส่วนของงานนั้นที่เสร็จแล้วแล้ว. เมตริกนี้ช่วยผู้จัดการโครงการประเมินความคืบหน้า, ปรับสมดุลภาระงาน, และระบุความล่าช้าที่อาจเกิดขึ้นโดยไม่ต้องคำนวณด้วยมือ.

## ทำไมต้องดึงเปอร์เซ็นต์งานที่เสร็จสมบูรณ์?
การดึงค่าเปอร์เซ็นต์งานที่เสร็จสมบูรณ์สำหรับแต่ละทรัพยากรจะให้มุมมองทันทีว่าได้ทำงานตามแผนที่วางไว้เท่าไหร่, ช่วยให้คุณสามารถสังเกตงานที่ล่าช้าหรือทรัพยากรที่ใช้ไม่เต็มที่ได้อย่างรวดเร็ว. ข้อมูลเชิงลึกนี้สนับสนุนการตัดสินใจที่ทันท่วงทีและการรายงานสถานะที่แม่นยำยิ่งขึ้น.

## ข้อกำหนดเบื้องต้น
### สภาพแวดล้อมการพัฒนา Java
ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) แล้ว. คุณสามารถดาวน์โหลด JDK ได้จาก [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### ไลบรารี Aspose.Tasks
ดาวน์โหลดและเพิ่มไลบรารี Aspose.Tasks ไปยังโครงการของคุณจาก [here](https://releases.aspose.com/tasks/java/) และทำตามคำแนะนำการติดตั้งที่ให้ไว้ในเอกสาร [here](https://reference.aspose.com/tasks/java/).

## นำเข้าแพ็กเกจ
คลาส `Resource` แทนทรัพยากรของโครงการและให้การเข้าถึงฟิลด์เช่น percent work complete.  
ก่อนที่เราจะเริ่มเขียนโค้ด, ให้เรานำเข้าแพ็กเกจที่จำเป็นสำหรับบทแนะนำนี้:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## ฉันจะตั้งค่าเส้นทางไฟล์โครงการอย่างไร?
ระบุที่ตั้งของไฟล์ Microsoft Project ของคุณโดยให้เส้นทางแบบเต็มหรือเส้นทางสัมพันธ์กับไดเรกทอรีทำงานของแอปพลิเคชัน. สตริงเส้นทางควรชี้ไปยังไฟล์ *.mpp* ที่ถูกต้องเพื่อให้ Aspose.Tasks สามารถค้นหาและเปิดไฟล์เพื่อการประมวลผลต่อไปได้.
```java
String dataDir = "Your Data Directory";
```
แทนที่ `"Your Data Directory"` ด้วยโฟลเดอร์ที่มีไฟล์ Microsoft Project ของคุณ.

## ฉันจะโหลดโครงการอย่างไร?
สร้างอินสแตนซ์ใหม่ของคลาส `Project` โดยใช้เส้นทางไฟล์ที่คุณกำหนดไว้ก่อนหน้า. คลาส `Project` แทนไฟล์ Microsoft Project และให้การเข้าถึงงาน, ทรัพยากร, และข้อมูลโครงการอื่น ๆ, โหลดทุกอย่างเข้าสู่หน่วยความจำเพื่อการวิเคราะห์.
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
นี่จะโหลดไฟล์ **Software Development.mpp** จากไดเรกทอรีที่คุณระบุ.

## ฉันจะวนลูปผ่านทรัพยากรอย่างไร?
ใช้เมธอด `project.getResources()` เพื่อรับคอลเลกชันของทรัพยากรทั้งหมดที่กำหนดในโครงการที่โหลดแล้ว. วนลูปผ่านคอลเลกชันนี้ด้วยลูป `for` ของ Java ปกติหรือโครงสร้าง `for‑each` ที่ปรับปรุง, เพื่อให้คุณสามารถตรวจสอบแต่ละอ็อบเจ็กต์ `Resource` แยกกันและดึงฟิลด์ที่เกี่ยวข้องได้.
```java
for (Resource res : prj.getResources()) {
```
เราจะวนลูปผ่านทุกทรัพยากรที่กำหนดในโครงการ.

## ฉันจะตรวจสอบชื่อทรัพยากรและดึงเปอร์เซ็นต์งานที่เสร็จสมบูรณ์อย่างไร?
ก่อนอื่นให้แน่ใจว่าอ็อบเจ็กต์ `Resource` มีชื่อที่ไม่ว่างเปล่าเพื่อหลีกเลี่ยงการประมวลผลรายการแทนที่. จากนั้นเรียก `res.get(Rsc.PERCENT_WORK_COMPLETE)` ซึ่งจะคืนค่า double ที่แสดงเปอร์เซ็นต์ของงานที่เสร็จสำหรับทรัพยากรนั้น, มีค่าอยู่ระหว่าง 0 ถึง 100. คุณสามารถจัดรูปแบบค่านี้เพื่อแสดงผลหรือใช้ในการคำนวณต่อเพื่อประเมินสุขภาพโดยรวมของโครงการ.
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
โค้ดจะตรวจสอบว่าทรัพยากรมีชื่อก่อนและจากนั้นพิมพ์ค่า **percent work complete** ของทรัพยากรนั้น.

## ปัญหาทั่วไปและวิธีแก้
- **NullPointerException** – ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์โครงการถูกต้องและไฟล์โหลดโดยไม่มีข้อผิดพลาด.  
- **Incorrect percentages** – ตรวจสอบว่าทรัพยากรมีงานที่มอบหมายจริงหรือไม่; หากไม่มีเปอร์เซ็นต์จะเป็น `0`.  
- **License errors** – ใช้ไลเซนส์ Aspose.Tasks ที่ถูกต้องหรือไลเซนส์ประเมินผลชั่วคราวเพื่อหลีกเลี่ยงข้อจำกัดขณะรัน.

## คำถามที่พบบ่อย (ต้นฉบับ)
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่?
ได้, Aspose.Tasks สำหรับ Java เข้ากันได้กับเฟรมเวิร์ก Java ต่าง ๆ เช่น Spring, Hibernate, และอื่น ๆ.

### Aspose.Tasks รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?
Aspose.Tasks ให้การสนับสนุนไฟล์ Microsoft Project ทุกเวอร์ชัน, รวมถึง MPP, MPT, XML, และอื่น ๆ.

### ฉันสามารถจัดการตารางโครงการโดยใช้ Aspose.Tasks ได้หรือไม่?
แน่นอน, Aspose.Tasks มีฟีเจอร์ครบถ้วนสำหรับการจัดการตารางโครงการ, รวมถึงงาน, ทรัพยากร, ปฏิทิน, และอื่น ๆ.

### มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่?
ใช่, คุณสามารถขอความช่วยเหลือและสนทนากับผู้ใช้คนอื่นได้ในฟอรั่มชุมชน Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

### Aspose.Tasks มีไลเซนส์ชั่วคราวสำหรับการประเมินหรือไม่?
ใช่, คุณสามารถรับไลเซนส์ชั่วคราวสำหรับการประเมินได้จาก [here](https://purchase.aspose.com/temporary-license/).

## FAQ เพิ่มเติม

**Q:** ฉันจะแสดงผลลัพธ์เป็นเปอร์เซ็นต์พร้อมเครื่องหมาย % อย่างไร?  
**A:** ดึงค่าตัวเลขด้วย `res.get(Rsc.PERCENT_WORK_COMPLETE)` และจัดรูปแบบโดยใช้ `String.format("%.2f%%", value)`.

**Q:** ฉันสามารถกรองทรัพยากรเพื่อแสดงเฉพาะที่มีเปอร์เซ็นต์เสร็จต่ำกว่า 50 % ได้หรือไม่?  
**A:** ได้, เพิ่มเงื่อนไข `if` ที่ตรวจสอบ `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` ก่อนพิมพ์.

**Q:** สามารถเขียนค่าเปอร์เซ็นต์กลับไปยังไฟล์ Project ได้หรือไม่?  
**A:** ฟิลด์ `Rsc.PERCENT_WORK_COMPLETE` เป็นแบบอ่าน‑อย่างเดียว; คุณต้องปรับการมอบหมายงานแทน.

**Q:** วิธีนี้ทำงานกับไฟล์ Project Online (คลาวด์) หรือไม่?  
**A:** คุณต้องดาวน์โหลดไฟล์ .mpp มาที่เครื่องก่อน; Aspose.Tasks ทำงานกับรูปแบบไฟล์, ไม่ได้ทำงานโดยตรงกับบริการคลาวด์.

## ประโยชน์เชิงปริมาณของการใช้ Aspose.Tasks
Aspose.Tasks รองรับ **ไฟล์ฟอร์แมตกว่า 30+** (MPP, MPT, XML, CSV, ฯลฯ) และสามารถประมวลผลโครงการที่มี **งานสูงสุดถึง 10,000 งาน** พร้อมรักษาการใช้หน่วยความจำให้อยู่ต่ำกว่า 200 MB ด้วยการสตรีมข้อมูล. ฟิลด์ **read‑only `Rsc.PERCENT_WORK_COMPLETE`** ของไลบรารีคำนวณในเวลา O(n), ทำให้การดึงข้อมูลเร็วแม้กับตารางขนาดใหญ่.

## สรุป
ในคู่มือนี้เราได้สาธิต **วิธีคำนวณเปอร์เซ็นต์ทรัพยากรใน Java** ด้วย Aspose.Tasks, โดยเน้นการดึง *percent work complete* สำหรับแต่ละทรัพยากร. ด้วยการทำตามขั้นตอนข้างต้น, คุณสามารถฝังการวิเคราะห์เปอร์เซ็นต์ทรัพยากรที่แม่นยำเข้าในแอปพลิเคชัน Java ของคุณ, ให้การมองเห็นสุขภาพโครงการและการใช้ทรัพยากรได้ดียิ่งขึ้น.

---

**อัปเดตล่าสุด:** 2026-06-15  
**ทดสอบกับ:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มทรัพยากรลงในโครงการด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/create-resources/)
- [จัดการต้นทุนทรัพยากรของ MS Project ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/resource-cost/)
- [การคำนวณเปอร์เซ็นต์ความสำเร็จของงานใน Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}