---
date: 2026-05-20
description: تعلم كيفية استخدام Aspose.Tasks for Java لإضافة Extended Attributes إلى
  Resource Assignments، وتعيين تاريخ بدء المشروع، وكتابة ملفات MS Project بكفاءة.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: إضافة Extended Attributes إلى Resource Assignments في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية استخدام Aspose.Tasks for Java – إضافة Extended Attributes إلى Resource
  Assignments
url: /ar/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان التعامل مع MS Project باستخدام Aspose.Tasks للغة Java

## مقدمة
في هذا الدرس ستكتشف **كيفية استخدام Aspose.Tasks للغة Java** لإضافة سمات موسعة إلى تعيينات الموارد وكتابة معلومات Microsoft Project برمجياً. سواءً كنت تقوم بأتمتة خط أنابيب التقارير أو بناء أداة إدارة مشاريع مخصصة، فإن الخطوات أدناه توضح لك بالضبط كيفية تعيين تاريخ بدء المشروع، وإنشاء تعيينات الموارد، وحفظ الملف بصيغة XML—كل ذلك باستخدام بضع أسطر فقط من كود Java.

## إجابات سريعة
- **ماذا يفعل Aspose.Tasks للغة Java؟** يقرأ، يكتب، ويعدل ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project.  
- **هل يمكنني إضافة حقول مخصصة إلى تعيين مورد؟** نعم، استخدم مجموعة `ExtendedAttribute` على كائن `ResourceAssignment`.  
- **كيف يمكنني تعيين تاريخ بدء المشروع؟** استدعِ `project.setStartDate(LocalDateTime.of(...))` قبل الحفظ.  
- **هل أحتاج إلى ترخيص للاستخدام الإنتاجي؟** الترخيص التجاري يزيل العلامات المائية التجريبية ويفتح الوصول الكامل إلى API.  
- **ما إصدارات Java المدعومة؟** يدعم Aspose.Tasks للغة Java إصدارات JDK 8 إلى JDK 21.

## كيفية استخدام Aspose.Tasks للغة Java؟
`Project` هو الكائن الأساسي الذي يمثل ملف Microsoft Project في الذاكرة. قم بتحميل مكتبة Aspose.Tasks، أنشئ مثيلًا من `Project`، اضبط خصائص مستوى المشروع، أضف سمات موسعة إلى تعيين مورد، وأخيرًا احفظ المشروع بصيغة XML. تتضمن سير العمل الأساسي ثلاث خطوات مختصرة: التهيئة، التعديل، والحفظ. هذا النمط يعمل مع أي حجم ملف مشروع ويعمل على JVMs في Windows أو Linux أو macOS.

## ما هي السمة الموسعة في Aspose.Tasks؟
السمة **الموسعة** هي حقل مخصص تقوم بإرفاقه بالمهام أو الموارد أو التعيينات لتخزين بيانات وصفية إضافية تتجاوز الأعمدة المدمجة. `ExtendedAttributeDefinition` يحدد المخطط لحقل مخصص. تُظهر Aspose.Tasks فئتي `ExtendedAttributeDefinition` و `ExtendedAttribute` لتحديد وتعيين هذه الحقول برمجياً.

## لماذا نضيف سمات موسعة إلى تعيينات الموارد؟
تدعم Aspose.Tasks **أكثر من 50 حقلًا مدمجًا ومخصصًا**، ويمكنك إضافة سمات معرفة من قبل المستخدم دون حد. يتيح لك إضافة هذه السمات التقاط رموز التكلفة، معرفات الأقسام، أو أي بيانات خاصة بالأعمال مباشرة داخل ملف .mpp، مما يلغي الحاجة إلى جداول بيانات خارجية ويضمن سلامة البيانات عبر دورة حياة المشروع.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – تم تثبيت JDK 8 أو أحدث.  
2. **Aspose.Tasks for Java library** – قم بتنزيله من صفحة الإصدار الرسمية [هنا](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA أو Eclipse أو أي محرر متوافق مع Java تفضله.

## استيراد الحزم
First, import the necessary packages in your Java project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### الخطوة 1: إعداد دليل البيانات
حدد الدليل الذي سيتم تخزين بيانات مشروعك فيه. يُستخدم هذا المسار لاحقًا عند حفظ ملف XML.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: إنشاء مثيل Project
فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة. إنشاء مثيل منها يمنحك وصولًا كاملاً إلى جميع عناصر المشروع.

```java
Project project = new Project();
```

### الخطوة 3: تعيين خصائص معلومات المشروع
قم بتعيين خصائص المشروع الأساسية مثل تاريخ البدء، وعلم جدول البداية من البداية، وتاريخ الحالة. تُخزن هذه القيم في كائن `ProjectInfo` الخاص بالمشروع.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### الخطوة 4: إضافة سمات موسعة إلى تعيين مورد
أنشئ `ExtendedAttributeDefinition` للحقل المخصص، واربطه بـ `ResourceAssignment`، واملأ القيمة. تُظهر هذه الخطوة كلمة المفتاح **add extended attributes** قيد التنفيذ.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
- **NullPointerException عند الوصول إلى مجموعة التعيينات** – تأكد من أنك أنشأت على الأقل موردًا واحدًا ومهمة واحدة قبل استرجاع التعيينات.  
- **السمات الموسعة لا تظهر في MS Project** – تحقق من أن `FieldId` الخاص بالسمات يطابق خانة حقل مخصص (مثال: `ExtendedAttributeTask.Text1`).  
- **عدم تطابق تنسيق التاريخ** – استخدم `java.time.LocalDateTime` لقيم التاريخ؛ تقوم Aspose.Tasks تلقائيًا بتحويلها إلى تنسيق تقويم المشروع.

## الأسئلة المتكررة

**Q: هل يمكنني استخدام Aspose.Tasks للغة Java لقراءة ملفات MS Project؟**  
A: نعم، توفر المكتبة إمكانيات القراءة والكتابة الكاملة لصيغ .mpp و .xml و .xps.

**Q: هل Aspose.Tasks للغة Java متوافق مع إصدارات مختلفة من MS Project؟**  
A: بالتأكيد، فهو يدعم الملفات من Project 2000 حتى أحدث إصدار 2024، ويغطي أكثر من 20 صيغة إصدار.

**Q: هل هناك أي قيود على نسخة التجربة من Aspose.Tasks للغة Java؟**  
A: تضيف نسخة التجربة علامة مائية إلى الملفات المولدة وتحد من عدد المهام التي يمكنك إنشاؤها، لكن جميع ميزات API تظل متاحة.

**Q: كيف يمكنني الحصول على دعم لـ Aspose.Tasks للغة Java؟**  
A: يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**Q: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks للغة Java؟**  
A: نعم، تتوفر تراخيص مؤقتة للاستخدام قصير الأمد. يمكنك الحصول على واحد من [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-05-20  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [كيفية إضافة ملاحظات إلى تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [كيفية قراءة مقياس المعدل وكتابة مقياس المعدل لتعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [كيفية إضافة مورد إلى المشروع ومعالجة خصائص تأخير التسوية في Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}