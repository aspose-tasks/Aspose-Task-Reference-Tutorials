---
date: 2025-12-23
description: تعلم كيفية إنشاء ملخص MPP وتحديث مؤلف المشروع باستخدام Aspose.Tasks للغة
  Java. قم بتعيين واسترجاع معلومات المشروع بسهولة.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إنشاء ملخص MPP وتحديث مؤلف المشروع باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كتابة ملخص مشروع MPP في Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، سوف **تنشئ ملخص MPP** لملف Microsoft Project وتتعلم كيفية **تحديث تفاصيل مؤلف المشروع** باستخدام مكتبة Aspose.Tasks للغة Java. سواءً كنت تبني أداة لإدارة المشاريع أو تقوم بأتمتة التقارير، فإن التحكم في خصائص الملخص برمجياً يوفر الوقت ويضمن الاتساق عبر مشاريعك.

## إجابات سريعة
- **ماذا يعني “إنشاء ملخص MPP”؟** يعني ذلك ضبط خصائص المشروع عالية المستوى (المؤلف، الإصدار، الكلمات المفتاحية، إلخ) التي تظهر في مربع حوار Project Summary Information في Microsoft Project.  
- **أي مكتبة تتعامل مع ذلك؟** Aspose.Tasks for Java توفر واجهة برمجة تطبيقات سلسة لقراءة وكتابة تلك الخصائص.  
- **هل أحتاج إلى ترخيص؟** يتوفر نسخة تجريبية مجانية، لكن الترخيص التجاري مطلوب للاستخدام في الإنتاج.  
- **هل يمكنني أيضًا تغيير المؤلف بعد حفظ الملف؟** نعم – يمكنك **تحديث مؤلف المشروع** عن طريق استدعاء `project.set(Prj.AUTHOR, "New Author")` ثم إعادة حفظ الملف.  
- **ما صيغ الملفات المدعومة؟** كل من MPP و XML (SaveFileFormat.Xml) مدعومان بالكامل.

## ما هو إنشاء ملخص MPP؟
إنشاء ملخص MPP يتضمن تعبئة بيانات التعريف الخاصة بالمشروع — المؤلف، رقم الإصدار، الكلمات المفتاحية، التعليقات، تاريخ الإنشاء، وتاريخ الطباعة. تُخزن هذه البيانات داخل سجل Project Summary Information وتُعرض في قسم **File → Info** في Microsoft Project.

## لماذا تحديث مؤلف المشروع؟
الحفاظ على صحة معلومات **مؤلف المشروع** أمر أساسي لسجلات التدقيق، التعاون، وإعداد التقارير. عندما يساهم عدة أعضاء في الفريق، قد تحتاج إلى **تحديث مؤلف المشروع** لتعكس أحدث التغييرات أو لتخصيص العمل بشكل صحيح.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. مجموعة تطوير Java (JDK) مثبتة على جهازك.  
2. Aspose.Tasks for Java – قم بتنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو NetBeans.

## استيراد الحزم
أولاً، استورد الحزم الضرورية في فئة Java الخاصة بك:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## الخطوة 1: إعداد المشروع وتعريف معلومات الملخص
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
في الشيفرة أعلاه نقوم **بإنشاء ملخص MPP** لحقول مثل المؤلف، الإصدار، والكلمات المفتاحية. يمكنك أيضًا **تحديث مؤلف المشروع** لاحقًا عن طريق استدعاء `project.set(Prj.AUTHOR, "New Name")`.

## الخطوة 2: حفظ معلومات ملخص المشروع
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
حفظ المشروع يُخزّن جميع بيانات الملخص التي قمت بتعريفها.

## الخطوة 3: قراءة معلومات ملخص المشروع
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
هذا المقتطف يوضح كيفية **قراءة** معلومات الملخص مرة أخرى، مؤكدًا أن عملية **إنشاء ملخص MPP** نجحت.

## المشكلات الشائعة والحلول
- **قيمة فارغة بعد القراءة:** تأكد من أن المشروع تم حفظه بنجاح قبل إعادة تحميله. افحص مسارات الملفات والأذونات.  
- **اختلاف تنسيقات التاريخ:** `project.get(Prj.CREATION_DATE)` يُعيد كائن `java.util.Date`. استخدم `SimpleDateFormat` إذا كنت بحاجة إلى تنسيق عرض مخصص.  
- **عدم تعيين الترخيص:** بدون ترخيص صالح، يعمل Aspose.Tasks في وضع التقييم وقد يضيف علامة مائية. سجِّل ترخيصك مبكرًا في الشيفرة.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.Tasks for Java مع مكتبات Java أخرى؟**  
ج: نعم، يمكن دمج Aspose.Tasks for Java بسلاسة مع مكتبات Java أخرى لتعزيز قدرات إدارة المشروع الخاصة بك.

**س: هل تتوفر نسخة تجريبية من Aspose.Tasks for Java؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: ما مدى تكرار تحديث Aspose.Tasks for Java؟**  
ج: يتم تحديث Aspose.Tasks for Java بانتظام لضمان التوافق مع أحدث إصدارات Java وملفات Microsoft Project.

**س: هل يمكنني تخصيص معلومات ملخص المشروع أكثر؟**  
ج: بالتأكيد، توفر Aspose.Tasks for Java خيارات واسعة لتخصيص معلومات ملخص المشروع وفقًا لمتطلباتك الخاصة.

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

## الخاتمة
في هذا البرنامج التعليمي أظهرنا لك كيفية **إنشاء ملخص MPP**، **تحديث مؤلف المشروع**، والتحقق من تلك التغييرات باستخدام Aspose.Tasks for Java. من خلال أتمتة هذه الخطوات تحصل على سيطرة كاملة على بيانات تعريف المشروع، مما يجعل تطبيقاتك أكثر قوة وتقارير مشروعك أكثر دقة.

---

**آخر تحديث:** 2025-12-23  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}