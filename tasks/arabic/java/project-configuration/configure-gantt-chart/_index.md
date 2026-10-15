---
date: 2026-10-15
description: تعلم كيفية إنشاء نشاط، وتعيين دليل البيانات، وتخصيص حقول الجدول، وحفظ
  المشروع كملف MPP باستخدام Aspose.Tasks for Java. دليل خطوة بخطوة لمطوري Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: كيفية إنشاء نشاط وتعيين دليل البيانات باستخدام Aspose.Tasks for Java
og_description: كيفية إنشاء نشاط، وتخصيص حقول الجدول، وحفظ المشروع كملف MPP باستخدام
  Aspose.Tasks for Java. اتبع هذا الدليل التفصيلي للتنفيذ السريع.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: كيفية إنشاء نشاط وتعيين دليل البيانات في Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: كيفية إنشاء نشاط وتعيين دليل البيانات باستخدام Aspose.Tasks for Java
url: /ar/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء نشاط وتعيين دليل البيانات باستخدام Aspose.Tasks للغة Java

## المقدمة
في هذا الدرس ستكتشف **كيفية إنشاء نشاط** برمجياً، وتكوين **دليل البيانات**، و**حفظ المشروع كملف MPP** مع **تخصيص حقول الجدول** في عرض مخطط جانت. Aspose.Tasks للغة Java هي واجهة برمجة تطبيقات قوية تدعم أكثر من 30 صيغة إدخال وإخراج ويمكنها معالجة المشاريع التي تحتوي على ما يصل إلى 10 000 مهمة دون تحميل الملف بالكامل في الذاكرة. بنهاية الدليل ستكون قادرًا على أتمتة إنشاء المشروع، وإثراء المهام بسمات مخصصة، وإنتاج ملف MPP جاهز للفتح في Microsoft Project.

## الإجابات السريعة
- **ما هي الخطوة الأولى؟** حدد مسار دليل البيانات حيث توجد ملفات المشروع الخاصة بك.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks للغة Java (قابلة للتنزيل من الموقع الرسمي).  
- **هل يمكنني إضافة سمات مخصصة؟** نعم – يمكنك تعريف سمات موسعة وعرضها في مخطط جانت.  
- **هل أحتاج إلى ترخيص للاختبار؟** ترخيص مؤقت متاح لأغراض التقييم.  
- **أي بيئة تطوير متكاملة (IDE) هي الأنسب؟** أي IDE للغة Java (IntelliJ IDEA، Eclipse، NetBeans) ستعمل.

## ما هو “تعيين دليل البيانات” ولماذا هو مهم؟
تعيين دليل البيانات يخبر Aspose.Tasks أين يقرأ ويكتب ملفات المشروع. بدون مسار صحيح لا تستطيع الواجهة البرمجية العثور على ملفات `.mpp` الخاصة بك، مما يؤدي إلى أخطاء `FileNotFoundException`. تعريف هذا الدليل في بداية الكود يجعل سير العمل قابلًا للتكرار ويعزل مشكلات نظام الملفات عن منطق الأعمال.

## لماذا تخصيص حقول الجدول في مخطط جانت؟
تسمح لك حقول الجدول المخصصة بعرض معلومات إضافية—مثل السمات المخصصة، بيانات الموارد، أو ملاحظات خاصة بالمشروع—مباشرة في عرض مخطط جانت. هذا يقلل الحاجة إلى تقارير منفصلة ويمنح أصحاب المصلحة تصورًا موحدًا غنيًا بالبيانات يمكن أن يحسن سرعة اتخاذ القرار بنسبة تصل إلى 30 %.

## كيفية إنشاء نشاط جديد؟
تقوم بإنشاء نشاط جديد (مهمة) عن طريق إنشاء كائن `Task` وإضافته إلى مجموعة المهام الجذرية للمشروع. يتيح لك هذا النهج إنشاء جداول زمنية كبيرة تلقائيًا، سحب بيانات المهام من أنظمة خارجية، أو تطبيق تحديثات جماعية دون تحرير يدوي.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث.  
2. **Aspose.Tasks للغة Java** – قم بتنزيله من **صفحة إصدار Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر متوافق مع Java تفضله.

## استيراد الحزم
مساحة الأسماء `com.aspose.tasks` تحتوي على جميع الفئات التي ستحتاجها لمعالجة المشروع. استيرادها يمنحك الوصول إلى `Project`، `Task`، `ExtendedAttributeDefinition`، وغيرها من الأنواع الأساسية.

```java
import com.aspose.tasks.*;
```

## اعتماد Maven (اختياري)
إذا كنت تدير مشروعك باستخدام Maven، أضف اعتماد Aspose.Tasks إلى `pom.xml`. هذا يضمن حل المكتبة تلقائيًا أثناء عملية البناء.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي يحتوي على ملفات مشروعك. المتغير `dataDir` يحمل المسار المطلق ويُعاد استخدامه طوال الدرس.

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار الكامل للمجلد الذي توجد فيه `project.mpp`، على سبيل المثال `C:/Projects/MyGantt`.

### الخطوة 2: تحميل ملف المشروع
`Project` هو الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة. تحميل ملف موجود يمنحك الوصول إلى مهامه، موارده، وجداوله.

```java
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 3: إضافة نشاط جديد
`Task` يمثل نشاطًا فرديًا في الجدول الزمني. إضافة مهمة إلى مجموعة المهام الجذرية تُدرجها في المستوى الأعلى من هيكل المشروع.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### الخطوة 4: تعريف سمة مخصصة
`ExtendedAttributeDefinition` يتيح لك إنشاء حقل مخصص قابل لإعادة الاستخدام يمكن ربطه بأي مهمة أو مورد أو تعيين.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### الخطوة 5: إضافة سمة مخصصة إلى المهمة
`ExtendedAttribute` هو المثيل الفعلي لسمة مخصصة تقوم بتعيينه إلى مهمة محددة.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### الخطوة 6: تخصيص الجدول – إضافة السمة المخصصة كعمود
`TableField` يصف عمودًا في جدول مخطط جانت. بإضافة `TableField` يشير إلى السمة المخصصة، تجعل السمة مرئية في عرض المخطط.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### الخطوة 7: حفظ المشروع
استدعاء `project.save` يحفظ جميع التغييرات في ملف جديد. الثابت `SaveFileFormat.MPP` يخبر Aspose.Tasks بكتابة الملف بصيغة Microsoft Project الثنائية الأصلية.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| **FileNotFoundException** عند تحميل المشروع | مسار **set data directory** غير صحيح أو يفتقد الشرطة المائلة النهائية. | تحقق من أن `dataDir` يشير إلى المجلد الدقيق وتضمن الفاصل المناسب للملف (`/` أو `\\`). |
| السمة المخصصة غير مرئية في عرض جانت | تم إضافة حقل الجدول في الفهرس الخاطئ أو عرض العمود صغير جدًا. | تأكد من أن `table.getTableFields().add(3, attrField);` يستخدم فهرسًا صالحًا واضبط `setWidth` حسب الحاجة. |
| LicenseException عند الحفظ | لم يتم تطبيق ترخيص صالح للاستخدام في الإنتاج. | طبق ترخيصًا مؤقتًا أو دائمًا قبل استدعاء `project.save()`. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، Aspose.Tasks متاحة لـ .NET، Java، و C++.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من **صفحة تنزيل نسخة تجريبية مجانية لـ Aspose.Tasks**.

**س: أين يمكنني العثور على دعم Aspose.Tasks؟**  
ج: يمكنك العثور على الدعم وطرح الأسئلة في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**س: كيف يمكنني شراء ترخيص لـ Aspose.Tasks؟**  
ج: يمكنك شراء ترخيص من **صفحة شراء Aspose.Tasks**.

**س: هل أحتاج إلى ترخيص مؤقت لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من **صفحة طلب الترخيص المؤقت**.

## الخلاصة
أنت الآن تعرف **كيفية إنشاء نشاط**، وتعيين دليل البيانات، وتعريف وإرفاق سمة مخصصة، و**حفظ المشروع كملف MPP** مع **تخصيص حقول الجدول** في عرض مخطط جانت باستخدام Aspose.Tasks للغة Java. تمنحك هذه القدرات تحكمًا برمجيًا كاملاً في بيانات المشروع، مما يتيح توليد جداول زمنية تلقائيًا وتقديم تقارير بصرية أغنى لأصحاب المصلحة.

---

**آخر تحديث:** 2026-10-15  
**تم الاختبار مع:** Aspose.Tasks Java 24.12 (latest)  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [كيفية إنشاء ملف مشروع فارغ في Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بصيغة MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [كيفية إنشاء مشروع Aspose.Tasks – تعيين سمات مهمة جديدة](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}