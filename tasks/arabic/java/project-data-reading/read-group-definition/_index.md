---
date: 2026-10-26
description: كيفية قراءة بيانات تعريف المجموعة باستخدام Aspose.Tasks for Java. استخراج
  تجميع المهام، المعايير، والتنسيق من ملفات Microsoft Project لأتمتة التقارير والهجرة.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: قراءة بيانات تعريف المجموعة في Aspose.Tasks
og_description: كيفية قراءة بيانات تعريف المجموعة باستخدام Aspose.Tasks for Java.
  استخراج تجميع المهام، المعايير، والتنسيق من ملفات Microsoft Project لأتمتة التقارير
  والهجرة.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: كيفية قراءة بيانات تعريف المجموعة باستخدام Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: كيفية قراءة بيانات تعريف المجموعة باستخدام Aspose.Tasks for Java
url: /ar/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة بيانات تعريف المجموعة في Aspose.Tasks for Java

## مقدمة
Aspose.Tasks for Java يتيح لك الوصول إلى ملفات Microsoft Project وتعديلها وتحليلها برمجياً. في هذا الدرس ستتعلم **كيفية قراءة تعريف المجموعة** من ملف `.mpp`، واستخراج اسم كل مجموعة، ومعاييرها، وتنسيقها البصري، ثم استخدام هذه المعلومات لإنشاء تقارير مخصصة أو نقل الإعدادات إلى مشاريع أخرى. إتقان هذه القدرة يمكنك من أتمتة إعداد التقارير، والتحقق من بنية المشاريع، وتبسيط سير العمل القائم على البيانات.

## إجابات سريعة
- **ماذا يعني “قراءة تعريف المجموعة”؟** يعني استخراج قواعد التجميع (الاسم، المعايير، الألوان، الخطوط) التي يستخدمها Microsoft Project لتنظيم المهام.  
- **ما المكتبة التي أحتاجها؟** Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يتطلب الترخيص التجاري للإنتاج.  
- **ما هي بيئات التطوير المتوافقة؟** أي بيئة تطوير Java مثل IntelliJ IDEA أو Eclipse.  
- **كم سطر كود مطلوب؟** أقل من 30 سطرًا من كود Java لتحميل المشروع وعرض تفاصيل المجموعة.

## كيفية قراءة بيانات تعريف المجموعة
حمّل المشروع، عدّ مجموعاته، وتفحص معايير كل مجموعة. الجواب المباشر هو: **إنشاء كائن `Project`، استدعاء `project.getTaskGroups()`، وتكرار المجموعة لقراءة الأسماء، المعايير، الخطوط، والألوان.** الأقسام التالية تقسم العملية إلى خطوات واضحة، كل منها يرافقه عنصر نائب لكود قصير تستبدله بالمقتطف الفعلي من وثائق Aspose.Tasks.

## ما هو تعريف قراءة المجموعة؟
يشير تعريف قراءة المجموعة إلى استخراج قواعد التجميع (الاسم، المعايير، التنسيق) التي يطبقها Microsoft Project لترتيب المهام. هذه القواعد تخبر التطبيق كيف يجمع المهام حسب الحالة أو الأولوية أو الحقول المخصصة، وتشمل سمات بصرية مثل نمط الخط ولون الخلية.

## لماذا قراءة بيانات تعريف المجموعة؟
تسمح لك قراءة بيانات تعريف المجموعة **بأتمتة إنشاء التقارير**، **نقل منطق التجميع** إلى مشاريع أخرى، و**التحقق من وجود المجموعات المطلوبة** قبل التحديثات الجماعية. يمكن لـ Aspose.Tasks for Java معالجة مشاريع تحتوي على **أكثر من 10,000 مهمة** دون تحميل الملف بالكامل إلى الذاكرة، مما يتيح عمليات دفعة عالية الأداء. بالإضافة إلى ذلك، يمكنك استخراج ألوان الخطوط، الأنماط، واتجاهات الفرز لإعادة إنشاء التخطيط البصري الدقيق في لوحات التحكم المخصصة.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود:

1. **Java Development Kit (JDK) 8+** – أي نسخة حديثة تعمل.  
2. **Aspose.Tasks for Java** – حمّل أحدث JAR من [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير Java** – IntelliJ IDEA، Eclipse، أو أي محرر تفضله.  

> **نصيحة احترافية:** استخدم Maven أو Gradle لإدارة تبعية Aspose.Tasks؛ هذا يتجنب التعامل اليدوي مع ملفات JAR.

## استيراد الحزم
`Project` هو الفئة الأساسية التي تمثل ملف Microsoft Project في Aspose.Tasks for Java.  

```java
import com.aspose.tasks.*;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات الخاص بك
حدد المجلد الذي يحتوي على ملف `.mpp` الذي تريد فحصه. استخدام `java.nio.file.Paths` يضمن معالجة مسارات مستقلة عن النظام.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بالإشارة إلى ملف `.mpp` الخاص بك. يقرأ المُنشئ رأس الملف ويبني نموذجًا في الذاكرة.

```java
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 3: استرجاع عدد مجموعات المهام
اطبع العدد الإجمالي لمجموعات المهام المعرفة في المشروع. هذه الفحص السريع يؤكد أن الملف يحتوي فعليًا على معلومات تجميع.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### الخطوة 4: استرجاع معلومات مجموعة مهام محددة
احصل على مجموعة معينة (الفهرس 1 في هذا المثال) واعرض اسمها وعدد المعايير التي تحتويها. يمكن لكل مجموعة أن تحتوي على معايير متعددة تحدد كيفية تجميع المهام.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### الخطوة 5: استرجاع معلومات معيار المجموعة
كل مجموعة يمكن أن يكون لها معيار واحد أو أكثر. المقتطف أدناه يستخرج تفاصيل مثل الحقل المستخدم للتجميع، وضع التجميع، لون الخلية، والنمط.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### الخطوة 6: التحقق من المجموعة الأصلية
أحيانًا يكون المعيار تابعًا لمجموعة أصلية. هذا الفحص يؤكد العلاقة ويمنع مشاكل المؤشر الفارغ عند التنقل في الهيكلية.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### الخطوة 7: استرجاع معلومات خط المعيار
يمكن لمعايير المجموعة أن تحتوي على تنسيق خط مخصص. الكود التالي يطبع عائلة الخط، الحجم، النمط، واتجاه الفرز، مما يسمح لك بإعادة إنشاء المظهر الدقيق في واجهتك الخاصة.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|---------|------------|------|
| **`NullPointerException` on `criterion.getParentGroup()`** | قد لا يكون للمعيار مجموعة أصلية. | أضف فحصًا للـ null قبل الوصول إلى الأصل. |
| **File not found** | مسار `dataDir` غير صحيح أو اسم الملف مكتوب بخطأ. | استخدم `Paths.get(dataDir, "project.mpp").toAbsolutePath()` وتأكد من وجود الملف. |
| **License not set** | يعمل Aspose في وضع التقييم وقد يقتطع المخرجات. | سجّل الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` قبل تحميل المشروع. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java لتعديل ملفات المشروع؟**  
ج: نعم، المكتبة توفر إمكانيات قراءة/كتابة كاملة لتنسيقات Microsoft Project، مما يسمح لك بإضافة مهام، تغيير الموارد، وتحديث تعريفات المجموعات برمجياً.

**س: هل Aspose.Tasks for Java متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: يدعم تنسيقات MPP، XML، CSV، وغيرها من تنسيقات Project الشائعة عبر الإصدارات من Project 2000 حتى أحدث إصدار 2024.

**س: كيف يجب أن أتعامل مع الأخطاء أثناء العمل مع Aspose.Tasks for Java؟**  
ج: غلف عمليات الملفات بكتل `try‑catch` والتقط `TasksException` للحصول على معلومات خطأ مفصلة؛ افحص `getMessage()` للاستدلال على السبب.

**س: هل يقدم Aspose.Tasks for Java تصديرًا إلى صيغ أخرى؟**  
ج: بالتأكيد – يمكنك التصدير إلى PDF، XLSX، HTML، وأكثر باستخدام واجهات التصدير المخصصة في المكتبة.

**س: أين يمكنني العثور على موارد إضافية ودعم؟**  
ج: زر [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) للحصول على مراجع API و[منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للمساعدة المجتمعية.

## الخلاصة
في هذا الدرس استعرضنا **كيفية قراءة بيانات تعريف المجموعة** من ملف Microsoft Project باستخدام Aspose.Tasks for Java. من خلال تحميل كائن `Project`، عدّ `TaskGroupCollection`، وتفحص معايير كل مجموعة، خطوطها، وألوانها، يمكنك بناء خطوط تقارير آلية، نقل قواعد التجميع، أو التحقق من بنية المشاريع بثقة. نفس النهج يتوسع إلى مشاريع كبيرة تحتوي على آلاف المهام مع الحفاظ على استهلاك منخفض للذاكرة.

---

**Last Updated:** 2026-10-26  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## الدروس ذات الصلة

- [كيفية قراءة معلومات المشروع من Microsoft Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [كيفية الحصول على حقول الجدول وقراءة بيانات الجدول في Aspose.Tasks](/tasks/java/project-data-reading/read-table-data/)
- [قراءة مخطط جانت java – استخراج بيانات جانت محددة](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}