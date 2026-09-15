---
date: 2026-09-14
description: เรียนรู้วิธีเปลี่ยนรูปแบบสกุลเงินและอ่านคุณสมบัติของสกุลเงินใน Java ด้วย
  Aspose.Tasks. ดึงรหัสสกุลเงิน, ดึงสัญลักษณ์สกุลเงิน, และอัปเดตสกุลเงินของโครงการในไฟล์
  MS Project.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: วิธีเปลี่ยนรูปแบบสกุลเงิน
og_description: เรียนรู้วิธีเปลี่ยนรูปแบบสกุลเงินและอ่านคุณสมบัติของสกุลเงินใน Java
  ด้วย Aspose.Tasks. คู่มือขั้นตอนต่อขั้นตอนสำหรับการดึงรหัสสกุลเงินและอัปเดตสกุลเงินของโครงการ.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: วิธีเปลี่ยนรูปแบบสกุลเงินใน Java ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: วิธีเปลี่ยนรูปแบบสกุลเงินใน Java ด้วย Aspose.Tasks
url: /th/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านคุณสมบัติสกุลเงิน Java ด้วย Aspose.Tasks

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **เปลี่ยนรูปแบบสกุลเงิน** และอ่านคุณสมบัติสกุลเงินในโครงการ Java ที่ใช้ Aspose.Tasks ข้อมูลการเงินที่แม่นยำเป็นสิ่งสำคัญสำหรับทีมระดับหลายชาติ และการเชี่ยวชาญ API เหล่านี้ทำให้คุณสามารถดึงรหัส ISO‑4217, ดึงสัญลักษณ์สกุลเงิน, และอัปเดตการตั้งค่าเงินของโครงการได้โดยไม่ต้องแก้ไขสเปรดชีตด้วยมือ.

## คำตอบอย่างรวดเร็ว
- **อะไรหมายถึง “read currency”** หมายถึงการดึงรหัสสกุลเงิน, สัญลักษณ์, และการตั้งค่าการจัดรูปแบบตัวเลขที่เก็บอยู่ในไฟล์ Project.  
- **ทำไมต้องปรับการตั้งค่าสกุลเงิน?** เพื่อให้รายงานต้นทุนสอดคล้องกับประเพณีภูมิภาคและหลีกเลี่ยงข้อผิดพลาดการแปลง.  
- **ฉันต้องการใบอนุญาตหรือไม่?** ใช่ – จำเป็นต้องมีใบอนุญาต Aspose.Tasks for Java ที่ถูกต้องสำหรับการใช้งานจริง; การทดลองใช้ฟรีทำงานสำหรับการประเมิน.  
- **เวอร์ชัน Project ใดที่รองรับ?** ทั้ง *.mpp* (Project 2007‑2024) และ *.xml* รองรับเต็มรูปแบบ, ครอบคลุมเวอร์ชันไฟล์มากกว่า 20 ปี.  
- **ต้องการการตั้งค่าเพิ่มเติมหรือไม่?** เพียงเพิ่ม Aspose.Tasks for Java JAR ไปยัง classpath และนำเข้าคลาสที่เกี่ยวข้อง.

## อ่านคุณสมบัติสกุลเงิน Java ในโครงการ Aspose.Tasks
ในโลกที่เปลี่ยนแปลงอย่างรวดเร็วของการจัดการโครงการ การดึงรายละเอียดสกุลเงินเป็นสิ่งสำคัญสำหรับการวิเคราะห์ต้นทุนที่แม่นยำ คู่มือเฉพาะของเราที่ชื่อ **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)** จะพาคุณผ่านทุกขั้นตอน — ตั้งแต่การเปิดไฟล์โครงการจนถึงการดึงรหัสสกุลเงิน, สัญลักษณ์, และรูปแบบ โดยการทำตามบทเรียนคุณจะสามารถ:
* ดึงรหัสสกุลเงิน (เช่น USD, EUR) ที่ใช้ทั่วทั้งโครงการ.  
* เข้าถึงสัญลักษณ์สกุลเงินและการตั้งค่าการจัดรูปแบบตัวเลข.  
* ใช้ข้อมูลนี้เพื่อสร้างรายงานต้นทุนที่แปลเป็นภาษาท้องถิ่นหรือป้อนข้อมูลไปยังแดชบอร์ดการเงิน.

การเข้าใจวิธีการอ่านสกุลเงินช่วยให้คุณสามารถตรวจสอบงบประมาณโครงการ, เปรียบเทียบต้นทุนระหว่างภูมิภาค, และรักษาการปฏิบัติตามมาตรฐานการบัญชีได้.

## วิธีดึงรหัสสกุลเงิน java ด้วย Aspose.Tasks
เมธอด `Project.getCurrencyCode()` จะคืนค่าตัวระบุ ISO‑4217 แบบสามตัวอักษรสำหรับหน่วยเงินของโครงการ.

**คำตอบโดยตรง:** เรียก `project.getCurrencyCode()` เพื่อรับรหัสสกุลเงินเช่น **USD** หรือ **EUR**; จากนั้นคุณสามารถเก็บ, บันทึก, หรือส่งค่าดังกล่าวไปยังบริการการเงินภายนอกเพื่อการแปลงค่าได้ การเรียกแบบบรรทัดเดียวนี้ให้ตัวระบุที่เชื่อถือได้ตามมาตรฐานซึ่งทำงานได้กับทุกเวอร์ชันของ Project ที่รองรับ.

เมธอดนี้ให้วิธีที่รวดเร็วในการซิงโครไนซ์ข้อมูลโครงการกับระบบ ERP ที่คาดหวังรหัสมาตรฐาน.

## วิธีปรับรูปแบบสกุลเงิน java ด้วย Aspose.Tasks
การเปลี่ยนการแสดงผลของค่าเงินทำได้ผ่านคุณสมบัติสามอย่างที่ง่าย.
`project.setCurrencySymbol(String)` ตั้งค่าสัญลักษณ์สกุลเงินที่แสดงสำหรับค่าเงิน.  
`project.setCurrencyDecimalSeparator(char)` กำหนดอักขระที่ใช้แยกส่วนจำนวนเต็มจากส่วนเศษ.  
`project.setCurrencyThousandsSeparator(char)` กำหนดอักขระที่ใช้แยกกลุ่มของพัน.

**คำตอบโดยตรง:** ใช้ `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")`, และ `project.setCurrencyThousandsSeparator(".")` เพื่อกำหนดสัญลักษณ์, ตัวคั่นทศนิยม, และตัวคั่นหลักพันตามลำดับ — การทำเช่นนี้จะเปลี่ยนรูปแบบสกุลเงินทั้งหมดในครั้งเดียว การปรับตั้งค่าเหล่านี้รับประกันว่าผู้มีส่วนได้ส่วนเสียทุกคนจะเห็นตัวเลขในรูปแบบที่คุ้นเคย ลดการตีความผิดพลาด.
* `project.setCurrencySymbol("€")` – ตั้งค่าสัญลักษณ์ที่แสดง.  
* `project.setCurrencyDecimalSeparator(",")` – กำหนดตัวคั่นทศนิยม.  
* `project.setCurrencyThousandsSeparator(".")` – กำหนดตัวคั่นหลักพัน.  

## วิธีตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks
เมื่อโครงการย้ายไปยังตลาดใหม่หรือคลายเอนต์ต้องการรูปแบบเงินที่แตกต่าง คุณจะต้องอัปเดตสกุลเงินโดยโปรแกรม.
`project.setCurrencyCode(String)` กำหนดรหัสสกุลเงิน ISO‑4217 สำหรับโครงการ.

**คำตอบโดยตรง:** เรียก `project.setCurrencyCode("GBP")` พร้อมกับ `project.setCurrencySymbol("£")` และตัวคั่นที่เหมาะสม, แล้วบันทึกโครงการ; ไลบรารีจะอัปเดตการตั้งค่าการแสดงผลทั้งหมดในขณะที่รักษาข้อมูลต้นทุนที่มีอยู่ วิธีนี้ให้คุณควบคุมการแสดงผลการเงินของกำหนดการได้อย่างเต็มที่.

คู่มือขั้นตอนต่อขั้นตอนของเราที่ชื่อ **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** อธิบายวิธี:
* กำหนดรหัสสกุลเงินและสัญลักษณ์ใหม่สำหรับโครงการทั้งหมด.  
* ปรับรูปแบบตัวเลข (ตำแหน่งทศนิยม, ตัวคั่นหลักพัน) ให้ตรงกับประเพณีท้องถิ่น.  
* บันทึกไฟล์โครงการที่อัปเดตโดยไม่สูญเสียข้อมูลที่มีอยู่ใด ๆ.

โดยการเชี่ยวชาญวิธีตั้งค่าสกุลเงิน คุณสามารถสลับระหว่าง USD, GBP, JPY หรือสกุลเงินที่รองรับใด ๆ ได้ทันที.

## ทำไมต้องเชี่ยวชาญการจัดการสกุลเงินใน Aspose.Tasks?
การจัดการสกุลเงินที่ถูกต้องช่วยขจัดการตีความผิดพลาดที่มีค่าใช้จ่ายสูงและทำให้การทำงานร่วมกันระดับโลกเป็นไปอย่างราบรื่น.

**คำตอบโดยตรง:** การเชี่ยวชาญการจัดการสกุลเงินทำให้คุณสามารถแสดงต้นทุนในรูปแบบที่ทีมแต่ละทีมใช้เป็นภาษาท้องถิ่น, รับรองการรายงานที่แม่นยำ, ปฏิบัติตามมาตรฐานการบัญชีของแต่ละภูมิภาค, และเปิดใช้งานกระบวนการทำงานการเงินอัตโนมัติ — ประหยัดเวลาหลายชั่วโมงจากการจัดรูปแบบด้วยมือต่อโครงการ.
* **การทำงานร่วมกันระดับโลก:** ทีมจากหลายประเทศสามารถดูต้นทุนในรูปแบบของตนเองได้.  
* **การรายงานที่แม่นยำ:** ป้องกันการปัดเศษหรือข้อผิดพลาดในการแปลงที่อาจส่งผลต่อการจัดทำงบประมาณ.  
* **การปฏิบัติตาม:** ปรับให้สอดคล้องกับมาตรฐานการบัญชีของภูมิภาคและข้อกำหนดของลูกค้า.  
* **อัตโนมัติ:** ลดการแก้ไขด้วยมือโดยการตั้งค่าการจัดการสกุลเงินผ่านโปรแกรมในระหว่างการสร้างโครงการ.

## กรณีการใช้งานจริง
* **โครงการหลายชาติ:** บริษัทก่อสร้างที่จัดการไซต์ในยุโรปและอเมริกาเหนือต้องนำเสนองบประมาณทั้งใน EUR และ USD.  
* **การตรวจสอบการเงิน:** ผู้ตรวจสอบต้องการมุมมองที่ชัดเจนของบริบทสกุลเงินสำหรับแต่ละรายการต้นทุน.  
* **โมเดลการกำหนดราคาแบบไดนามิก:** ผู้ให้บริการ SaaS ปรับค่าธรรมเนียมการสมัครสมาชิกตามสกุลเงินท้องถิ่นของลูกค้า.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
* **ข้อผิดพลาด:** ลืมอัปเดตสัญลักษณ์สกุลเงินหลังจากเปลี่ยนรหัส.  
  **เคล็ดลับ:** ควรตั้งค่ารหัสและสัญลักษณ์พร้อมกันเสมอเพื่อหลีกเลี่ยงการแสดงผลที่ไม่ตรงกัน.  
* **ข้อผิดพลาด:** พึ่งพาภาษาเริ่มต้นของเครื่องที่รันโค้ด.  
  **เคล็ดลับ:** ระบุรูปแบบสกุลเงินที่ต้องการอย่างชัดเจนในโค้ด Aspose.Tasks ของคุณเพื่อให้แน่ใจว่าความสอดคล้องในทุกสภาพแวดล้อม.

## บทเรียนคุณสมบัติสกุลเงิน
### [อ่านคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks](./read-properties/)
เรียนรู้วิธีดึงข้อมูลสกุลเงินจากไฟล์ MS Project ด้วย Aspose.Tasks สำหรับ Java มีคู่มือขั้นตอนต่อขั้นตอนให้.

### [ตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks](./set-properties/)
เรียนรู้วิธีตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks ด้วย Java การจัดการไฟล์ Microsoft Project อย่างง่ายดาย.

## คำถามที่พบบ่อย

**Q: ฉันสามารถเปลี่ยนสกุลเงินหลังจากที่โครงการได้บันทึกแล้วหรือไม่?**  
A: ได้. ใช้ `Project.setCurrencyCode()` และเมธอดที่เกี่ยวข้อง, แล้วบันทึกโครงการอีกครั้ง.

**Q: การเปลี่ยนสกุลเงินส่งผลต่อค่าต้นทุนที่มีอยู่หรือไม่?**  
A: ค่าตัวเลขจะคงเดิม; เพียงรูปแบบการแสดงผล (สัญลักษณ์, ตัวคั่นทศนิยม) ถูกอัปเดต. คุณต้องคำนวณต้นทุนใหม่หากต้องการการแปลงระหว่างสกุลเงิน.

**Q: มีขีดจำกัดจำนวนสกุลเงินที่ฉันสามารถกำหนดได้หรือไม่?**  
A: Aspose.Tasks รองรับรหัสสกุลเงิน ISO‑4217 ใด ๆ ดังนั้นคุณจึงไม่มีขีดจำกัด.

**Q: จะเกิดอะไรขึ้นหากฉันเปิดโครงการที่มีรหัสสกุลเงินที่ไม่รองรับ?**  
A: ไลบรารีจะกลับไปใช้สกุลเงินเริ่มต้น (USD) และบันทึกคำเตือน; คุณสามารถเขียนทับโดยตั้งค่าสกุลเงินที่ต้องการด้วยตนเอง.

**Q: สามารถอ่าน/เขียนคุณสมบัติสกุลเงินในไฟล์ Project XML ได้หรือไม่?**  
A: ได้แน่นอน. API เดียวกันทำงานได้กับรูปแบบ *.mpp* และ *.xml* ทั้งสอง.

---

**อัปเดตล่าสุด:** 2026-09-14  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [คุณสมบัติโครงการ Java – ดึงสัญลักษณ์สกุลเงินจาก MPP ด้วย Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [วิธีดึงสกุลเงินจาก MS Project ด้วย Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [คุณสมบัติโครงการ Java – อ่าน Metadata ด้วย Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}