---
date: 2026-06-15
description: تعلم كيفية تحويل mpp إلى pdf وعرض Resource Usage و Sheet باستخدام Aspose.Tasks
  for Java. اتبع دليلنا خطوة بخطوة لتعيين timescale وإنشاء تقارير PDF مفصلة بسهولة.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: تحويل MPP إلى PDF وعرض Resource Usage View – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: تحويل MPP إلى PDF وعرض Resource Usage View – Aspose.Tasks
url: /ar/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل MPP إلى PDF وعرض استخدام الموارد – Aspose.Tasks

في هذا البرنامج التعليمي ستتعلم **كيفية تحويل mpp إلى pdf** مع عرض استخدام الموارد وورقة العرض لملف Microsoft Project. يزيل استخدام Aspose.Tasks for Java الحاجة إلى Microsoft Project على الخادم، مما يوفر لك طريقة سريعة وموثوقة لإنشاء تقارير PDF من ملفات MPP. سنوضح لك أيضًا **كيفية ضبط مقياس الوقت** بحيث يتطابق الناتج مع متطلبات التقارير الخاصة بك.

## إجابات سريعة
- **ما الذي يفعله Aspose.Tasks؟** يقرأ ويعدل ويحول ملفات Microsoft Project (MPP) دون الحاجة إلى تثبيت MS Project.  
- **هل يمكنني تحويل MPP إلى PDF بسطر واحد من الكود؟** نعم – قم بتحميل المشروع، اضبط SaveOptions، واستدعِ `save`.  
- **ما هي مقاييس الوقت المدعومة؟** الأيام، ThirdsOfMonths، والشهور.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم ترخيص تجاري للنشر غير التجريبي.  
- **هل المكتبة متوافقة مع Java 8+؟** بالتأكيد – تدعم Java 8 والإصدارات الأحدث.

## ما هو تحويل mpp إلى pdf؟
*Convert mpp to pdf* يشير إلى عملية أخذ ملف Microsoft Project (.mpp) وإنشاء نسخة بصيغة Portable Document Format (PDF) تعيد بدقة جداول المشروع، جدوله، مخططاته، وتخصيصات الموارد. يمكن مشاركة PDF الناتج بسهولة، طباعته، وأرشفته دون الحاجة إلى تثبيت Microsoft Project على جهاز المستلم.

## لماذا تحويل المشروع إلى PDF باستخدام Aspose.Tasks؟
يدعم Aspose.Tasks **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنه عرض مشاريع مئات الصفحات دون تحميل الملف بالكامل إلى الذاكرة، مما يقلل استهلاك RAM بنسبة تصل إلى 70 ٪. يحتفظ إخراج PDF بالجداول، المخططات، وتخصيصات الموارد، مما يجعله مثاليًا لتوزيع المعلومات على أصحاب المصلحة والأرشفة.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – Java 8 أو أحدث مثبت على جهازك.  
2. **Aspose.Tasks for Java** – قم بتنزيل أحدث ملف JAR من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  

## كيفية تحويل mpp إلى pdf باستخدام Aspose.Tasks for Java؟
حمّل ملف MPP المصدر، اضبط مقياس الوقت المطلوب، عيّن تنسيق العرض إلى **ResourceUsage**، واحفظ النتيجة كملف PDF. يتطلب هذا التدفق من البداية إلى النهاية عددًا قليلًا من استدعاءات API ويعمل في أقل من ثانية لأحجام المشاريع النموذجية.

### الخطوة 1: قراءة المشروع المصدر
فئة `Project` تمثل ملف Microsoft Project محملاً في الذاكرة، وتوفر الوصول إلى بياناته وبنيته.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### الخطوة 2: تعريف SaveOptions مع إعدادات TimeScale المطلوبة
`SaveOptions` يحدد كيفية حفظ المشروع، مما يتيح لك تحديد إعدادات خاصة بالتنسيق مثل مقياس الوقت.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### الخطوة 3: تعيين تنسيق العرض إلى ResourceUsage
`PresentationFormat` يحدد أي عرض من Project (مثل ResourceUsage) يتم عرضه في المستند الناتج.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### الخطوة 4: حفظ المشروع كملف PDF
`project.save` يكتب المشروع إلى ملف باستخدام `SaveOptions` المقدمة، وينتج ملف PDF النهائي.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### الخطوة 5: عرض المشاهد لإعدادات TimeScale أخرى
كرر الخطوات السابقة، مع تغيير قيمة `TimeScale` لعرض مشاهد مقياس الوقت الإضافية.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### الخطوة 6: اختياري – تحويل مشاريع متعددة دفعة واحدة
إذا كنت بحاجة إلى **تحويل مشروع إلى pdf** للعديد من الملفات، ضع المنطق أعلاه داخل حلقة تتكرر على دليل يحتوي على ملفات *.mpp*. يتيح هذا النهج **حفظ ملفات ms project pdf** دفعة واحدة مع أقل تغييرات في الكود. الكود التالي يوضح مثالًا كاملاً لتحويل ملف MPP إلى PDF بالإعدادات المطلوبة.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## المشكلات الشائعة والحلول
- **خطوط مفقودة في PDF** – تأكد من تثبيت الخطوط المطلوبة على الخادم أو دمجها عبر `PdfSaveOptions`.  
- **ملفات المشاريع الكبيرة تسبب OutOfMemoryError** – استخدم `LoadOptions.setLoadAllResources(false)` لتحميل الموارد عند الحاجة.  
- **عرض مقياس الوقت غير صحيح** – تحقق من أن `options.setTimeScale(TimeScale.Days)` (أو أي قيمة أخرى) يتطابق مع الدقة المطلوبة.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks عرض مشاهد أخرى غير Resource Usage و Sheet؟**  
**ج:** نعم، يدعم أيضًا مخطط Gantt، Task Usage، Calendar، والعديد من المشاهد الإضافية.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
**ج:** بالتأكيد – يتعامل مع صيغ MPP، MPT، وXML من Project 2000 حتى Project 2021.

**س: هل يمكنني تخصيص مظهر المشاهد المعروضة؟**  
**ج:** نعم، يمكنك تعديل الألوان، الخطوط، وتخطيطات الأعمدة عبر `PdfSaveOptions` و `PresentationOptions`.

**س: هل يتطلب Aspose.Tasks تثبيت Microsoft Project؟**  
**ج:** لا، إنها مكتبة مستقلة وتعمل على أي بيئة متوافقة مع Java.

**س: أين يمكنني الحصول على الدعم الفني؟**  
**ج:** الدعم متاح عبر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**آخر تحديث:** 2026-06-15  
**تم الاختبار مع:** Aspose.Tasks 24.12 for Java  
**المؤلف:** Aspose

## دروس ذات صلة

- [عرض استخدام الموارد وورقة العرض في Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [كيفية تصدير PDF في Aspose.Tasks – حفظ كـ PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [كيفية إنشاء ملفات MPP باستخدام Aspose.Tasks for Java](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}