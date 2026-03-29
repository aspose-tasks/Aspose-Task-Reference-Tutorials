---
date: 2026-03-29
description: เรียนรู้วิธีตั้งคีย์เวิร์ดและตั้งค่าวันที่สร้างในโครงการ MPP ด้วย Aspose.Tasks
  for Java คู่มือแบบทีละขั้นตอนพร้อมตัวอย่างโค้ด
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีตั้งคีย์เวิร์ดในสรุปโครงการ MPP ด้วย Aspose.Tasks
url: /th/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งคีย์เวิร์ดในสรุปโครงการ MPP ด้วย Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีตั้งคีย์เวิร์ด** และข้อมูลสรุปอื่น ๆ สำหรับไฟล์โครงการ MPP โดยใช้ Aspose.Tasks for Java ไม่ว่าคุณต้องการฝังรายละเอียดผู้เขียน, หมายเลขการแก้ไข, หรือวันที่สร้างแบบกำหนดเอง คู่มือนี้จะพาคุณผ่านขั้นตอนที่แน่นอน พร้อมโค้ดที่พร้อมรัน เมื่อเสร็จสิ้นคุณจะสามารถตั้งคีย์เวิร์ด, ตั้งวันที่สร้าง java, และดึงข้อมูลกลับจากไฟล์ได้

## คำตอบด่วน
- **ไลบรารีที่ใช้คืออะไร?** Aspose.Tasks for Java  
- **วัตถุประสงค์หลักคืออะไร?** Set keywords, author info, and creation date in an MPP file  
- **มีขั้นตอนโค้ดกี่ขั้นตอน?** Three simple code blocks (initialize, save, read)  
- **ฉันต้องการไลเซนส์หรือไม่?** A free trial works for development; a commercial license is required for production  
- **เวอร์ชัน Java ที่รองรับ?** Java 8 and higher  

## “วิธีตั้งคีย์เวิร์ด” ในไฟล์ MPP คืออะไร?
Keywords เป็นฟิลด์เมตาดาต้าที่เก็บอยู่ในไฟล์ Microsoft Project (MPP). พวกมันช่วยจัดประเภทโครงการ, ทำให้การค้นหาเร็วขึ้น, และให้ข้อมูลเชิงบริบทสำหรับเครื่องมือที่ต่อมา. Aspose.Tasks เปิดเผย property `Prj.KEYWORDS` ทำให้การเขียนหรืออัปเดตค่าดังกล่าวโดยโปรแกรมเป็นเรื่องง่าย.

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่อตั้งคีย์เวิร์ดและวันที่สร้าง?
* **Full .MPP compatibility** – works with all Project 2007‑2023 formats.  
* **No COM or Office installation required** – pure Java, perfect for server‑side environments.  
* **Rich API** – besides keywords you can set author, revision, comments, and dates in a single call.  
* **Performance‑optimized** – fast read/write even for large project files.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – JDK 8 หรือใหม่กว่า ติดตั้งแล้ว.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans หรือโปรแกรมแก้ไขใด ๆ ที่คุณต้องการ.

## นำเข้าแพ็กเกจ
ก่อนแรกให้ import คลาสที่คุณต้องการใช้ การ import เหล่านี้จะทำให้คุณเข้าถึงอ็อบเจ็กต์ `Project`, enumeration `Prj` สำหรับฟิลด์สรุป, และ enum `SaveFileFormat` สำหรับการบันทึก.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และกำหนดข้อมูลสรุป
สร้างอินสแตนซ์ `Project` แล้วใช้เมธอด `set` เพื่อเขียนเมตาดาต้าที่ต้องการ สังเกตว่าเราตั้ง **set the keywords** และ **set creation date java** ด้วยอ็อบเจ็กต์ `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## ขั้นตอนที่ 2: บันทึกข้อมูลสรุปของโปรเจกต์
หลังจากกรอกฟิลด์แล้ว ให้บันทึกการเปลี่ยนแปลง ที่นี่เราบันทึกโปรเจกต์เป็น XML เพื่อการตรวจสอบที่ง่าย แต่คุณก็สามารถบันทึกกลับเป็น MPP ได้เช่นกัน.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## ขั้นตอนที่ 3: อ่านข้อมูลสรุปของโปรเจกต์
เพื่อยืนยันว่าเมตาดาต้าถูกเขียนอย่างถูกต้อง ให้โหลดไฟล์ใหม่และอ่านแต่ละ property กลับมา ขั้นตอนนี้แสดงให้เห็นว่า **how to set keywords** ทำงานจากต้นจนจบจริง ๆ.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | Calendar ไม่ได้ถูกตั้งค่าก่อนการบันทึก. | ตรวจสอบให้แน่ใจว่าคุณเรียก `project.set(Prj.CREATION_DATE, cal.getTime())` ก่อน `save()`. |
| **Keywords not appearing in Microsoft Project UI** | ไฟล์ถูกบันทึกเป็น XML แล้วเปิดโดยตรงใน Project. | บันทึกกลับเป็น MPP (`SaveFileFormat.MPP`) หรือเปิด XML ผ่าน *Import* ใน Project. |
| **Date values shifted by timezone** | Java `Date` มีข้อมูลโซนเวลา. | ใช้ `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` หากต้องการวันที่แบบ UTC. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks for Java ร่วมกับไลบรารี Java อื่น ๆ ได้หรือไม่?**  
A: ได้, Aspose.Tasks for Java สามารถผสานรวมกับไลบรารี Java อื่น ๆ ได้อย่างราบรื่นเพื่อเพิ่มความสามารถในการจัดการโครงการของคุณ.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: ได้, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [here](https://releases.aspose.com/).

**Q: Aspose.Tasks for Java มีการอัปเดตบ่อยแค่ไหน?**  
A: Aspose.Tasks for Java มีการอัปเดตอย่างสม่ำเสมอเพื่อให้เข้ากันได้กับเวอร์ชันล่าสุดของ Java และไฟล์ Microsoft Project.

**Q: ฉันสามารถปรับแต่งข้อมูลสรุปของโปรเจกต์เพิ่มเติมได้หรือไม่?**  
A: แน่นอน, Aspose.Tasks for Java มีตัวเลือกมากมายสำหรับการปรับแต่งข้อมูลสรุปของโปรเจกต์ตามความต้องการเฉพาะของคุณ.

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**อัปเดตล่าสุด:** 2026-03-29  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}