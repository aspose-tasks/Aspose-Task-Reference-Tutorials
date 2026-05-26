---
date: 2026-05-26
description: تعلم كيفية تصدير MPP إلى CSV، حفظ المشروع كقالب، وتحويل MPP إلى نص باستخدام
  Aspose.Tasks for Java.
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: تصدير MPP إلى CSV، نص & قالب باستخدام Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: تصدير MPP إلى CSV، نص & قالب باستخدام Aspose.Tasks Java
url: /ar/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تصدير MPP إلى CSV، نص وقالب باستخدام Aspose.Tasks للـ Java

## مقدمة
في هذا الدرس ستكتشف **كيفية تصدير MPP إلى CSV**، وإنشاء قوالب مشاريع قابلة لإعادة الاستخدام، وتوليد مستخرجات نصية عادية باستخدام مكتبة Aspose.Tasks للـ Java. سواءً كنت تبني خط أنابيب تقارير، أو تقوم بأتمتة إنشاء المشاريع، أو تدمج مع أنظمة أخرى، فإن هذه الخطوات ستحول ملف MPP الخام إلى النتيجة الدقيقة التي تحتاجها—بسرعة ودون الحاجة لتثبيت Microsoft Project.

## إجابات سريعة
- **هل يمكنني تصدير MPP إلى CSV؟** نعم – استدعِ `project.save("output.csv", SaveFileFormat.CSV)`.  
- **كيف يمكنني التصدير إلى نص عادي؟** استخدم `SaveFileFormat.TEXT` مع طريقة `save`.  
- **ماذا يفعل “حفظ المشروع كقالب”?** ينشئ ملف `.mpt` يزيل التواريخ والخطوط الأساسية، ويترك الهيكل فقط.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتقييم؛ الترخيص التجاري يزيل حدود التقييم.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أحدث مدعومة بالكامل.

## ما هو “حفظ المشروع كقالب”؟
يؤدي حفظ المشروع كقالب (`.mpt`) إلى التقاط الهيكل، تسلسل المهام، وتعيينات الموارد مع إزالة تواريخ البدء/الانتهاء الفعلية وبيانات الخطوط الأساسية. يجعل هذا القالب مثاليًا لإعادة استخدام تخطيط مشروع قياسي عبر عدة مشاريع جديدة. يحتفظ بجميع الحقول المخصصة، معدلات التكلفة، وتفاصيل التعيينات، مما يضمن إمكانية تطبيق القالب على أي مشروع جديد دون فقدان الإعدادات الأساسية.

## لماذا نستخدم Aspose.Tasks للـ Java؟
تصدير MPP إلى CSV أو نص أو قالب مباشرة من Java دون الحاجة إلى Microsoft Project. تدعم Aspose.Tasks **أكثر من 20 نسخة من Microsoft Project** (2000‑2024) ويمكنها معالجة ملفات تصل إلى **500 ميغابايت** في وضع توفير الذاكرة، مما يجعلها مثالية لأتمتة الخوادم، خطوط CI، وأدوات متعددة المنصات.

## المتطلبات المسبقة
- تم تثبيت Java Development Kit 8 أو أعلى.  
- تم إضافة مكتبة Aspose.Tasks للـ Java إلى مشروعك – حمّلها من [here](https://releases.aspose.com/tasks/java/).  
- يمكنك أيضًا استكشاف مكتبات Aspose الأخرى على [here](https://releases.aspose.com/).  
- معرفة أساسية بـ Java وتكوين مشروع Maven/Gradle.

## استيراد الحزم
الفئة `Project` هي الكائن الأساسي في Aspose.Tasks الذي يمثل ملف Microsoft Project في الذاكرة. بعد إضافة المكتبة إلى ملف البناء الخاص بك، استورد الفئات المطلوبة:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## حفظ المشروع كـ CSV (تصدير MPP إلى CSV)
يتيح تصدير ملف MPP إلى CSV تغذية بيانات المهام إلى Excel أو Power BI أو أي منصة تحليلات.

### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### الخطوة 2: حفظ كـ CSV
`SaveFileFormat.CSV` يخبر Aspose.Tasks بإخراج المشروع بصيغة CSV.  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## حفظ المشروع كنص (كيفية تصدير النص)
يوفر ملف نص عادي تفريغًا سريعًا وقابلًا للقراءة للبشر للمهام والموارد والتعيينات.

### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### الخطوة 2: حفظ كنص
`SaveFileFormat.TEXT` يوجه المكتبة لإنشاء تمثيل نصي عادي للمشروع.  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## حفظ المشروع كقالب (إنشاء قالب مشروع Java)

### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### الخطوة 2: ضبط خيارات القالب
استخدم `Project.save` مع `SaveFileFormat.MPT` (أو `SaveFileFormat.TEMPLATE`) لإنشاء ملف قالب يزيل التواريخ والخطوط الأساسية.  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### الخطوة 3: حفظ كقالب
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## المشكلات الشائعة والنصائح
- **الملف غير موجود:** تحقق من المسار إلى `YourProject.mpp` أو استخدم مسارًا مطلقًا.  
- **استثناءات الترخيص:** بدون ترخيص صالح تعمل المكتبة في وضع التقييم وقد تضيف علامات مائية. قم بتطبيق الترخيص مبكرًا (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **المشاريع الكبيرة:** للملفات التي تتجاوز 200 MB، زد حجم ذاكرة JVM (`-Xmx2g`) لتجنب `OutOfMemoryError`.  
- **الأداء:** عند تحويل العديد من المشاريع، أعد استخدام كائن `Project` واحد حيثما أمكن لتقليل عبء إنشاء الكائنات.

## الخلاصة
أظهرنا كيفية **تصدير MPP إلى CSV**، **تحويل MPP إلى نص**، و**حفظ المشروع كقالب** باستخدام Aspose.Tasks للـ Java. تتيح لك هذه القدرات أتمتة التقارير، إنشاء هياكل مشاريع موحدة، وتكامل بيانات المشروع مع أي نظام لاحق—دون الحاجة إلى تثبيت Microsoft Project.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks للـ Java التعامل مع مشاريع معقدة ومتعددة المراحل؟**  
ج: نعم، فهو يدعم بالكامل المهام والموارد والتعيينات والخطوط الأساسية والحقول المخصصة عبر جميع إصدارات Project حتى 2024.

**س: هل تتوفر نسخة تجريبية؟**  
ج: بالتأكيد – حمّل نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

**س: أين يمكنني الحصول على مساعدة إذا واجهت مشاكل؟**  
ج: منتدى الدعم الرسمي موجود على [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) حيث يجيب الموظفون وأعضاء المجتمع على الأسئلة.

**س: هل يمكنني الحصول على ترخيص مؤقت لتقييم قصير الأمد؟**  
ج: نعم، اشترِ ترخيصًا مؤقتًا من [here](https://purchase.aspose.com/temporary-license/).

**س: هل يعمل Aspose.Tasks على Linux و macOS؟**  
ج: هو متعدد المنصات بالكامل ويعمل على Windows و macOS و Linux مع أي بيئة تشغيل Java 8+.

---

**آخر تحديث:** 2026-05-26  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (الأحدث)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بصيغة MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [تحميل ملف MPP في Java - إدارة خصائص المشروع باستخدام Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [كيفية تصدير MPP إلى Excel باستخدام Aspose.Tasks للـ Java](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}