---
date: 2026-05-20
description: تعلم كيفية تصدير المشروع إلى PDF، وتقليل الفجوة في التذييل، وحفظ المشروع
  كصورة باستخدام Aspose.Tasks for Java. قم بتحسين تخطيط MS Project الخاص بك بسهولة.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: تصدير المشروع إلى PDF وتقليل الفجوة بين قائمة المهام وتذييل الصفحة في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: تصدير المشروع إلى PDF وتقليل الفجوة بين قائمة المهام وتذييل الصفحة في Aspose.Tasks
url: /ar/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تصدير المشروع إلى PDF وتقليل الفجوة بين قائمة المهام وتذييل الصفحة في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي ستكتشف **كيفية تصدير المشروع إلى PDF** مع تقليل المسافة غير المرغوب فيها بين قائمة المهام وتذييل الصفحة في ملفات Microsoft Project. في نهاية الدليل ستكون قادرًا على إنشاء ملفات PDF نظيفة، وصور PNG، وصفحات HTML بتصميم مدمج باستخدام Aspose.Tasks for Java. دعنا نتبع العملية خطوة بخطوة، وسترى لماذا هذا مهم للتقارير المهنية.

## إجابات سريعة
- **ماذا يعني “export project to PDF”؟** إنه يحول ملف MPP إلى مستند PDF مع الحفاظ على المهام، الجداول الزمنية، والتنسيق.  
- **لماذا تقليل الفجوة في التذييل؟** فجوة أصغر تخلق تقارير أكثر تماسكًا ومظهرًا مهنيًا، خاصةً للوثائق المطبوعة أو المعروضة على الويب.  
- **هل يمكنني أيضًا حفظ المشروع كصورة؟** نعم – يدعم Aspose.Tasks صيغ PNG و JPEG وغيرها من صيغ الصور.  
- **هل أحتاج إلى ترخيص خاص؟** يتوفر نسخة تجريبية مجانية؛ يتطلب الترخيص التجاري للاستخدام في الإنتاج.  
- **ما إصدار Java المطلوب؟** Java 8 أو أعلى يعمل مع مكتبة Aspose.Tasks الحالية.  

## ما هو “export project to PDF”؟
تحويل المشروع إلى PDF يحول بنية MPP الداخلية إلى مستند محمول يمكن فتحه على أي جهاز دون الحاجة إلى Microsoft Project. هذا مثالي لمشاركة تقارير الحالة، وتحديثات أصحاب المصلحة، أو أرشفة خطط المشروع. إنه يحافظ على التخطيط الأصلي، الألوان، وتسلسل المهام، مما يضمن أن يبدو ملف PDF مطابقًا للملف الأصلي.

## لماذا تقليل الفجوة في التذييل؟
يمكن أن تضيف الفجوة الافتراضية في التذييل مساحة بيضاء غير ضرورية، مما يسبب مشاكل في التقسيم إلى صفحات ومظهر غير متوازن. يقلل تقليل الفجوة من استهلاك المحتوى للصفحة بشكل فعال، مما يجعل ملف PDF أو الصورة النهائي أكثر قابلية للقراءة. كما أن التصميم الأكثر تماسكًا يقلل من عدد الصفحات الإجمالي، مما قد يخفض تكاليف الطباعة ويحسن التنقل على الشاشة.

## كيف تقلل الفجوة بين قائمة المهام وتذييل الصفحة؟
`setReduceFooterGap` هي خاصية منطقية تتحكم في مسافة التذييل أثناء التصدير.  
توفر Aspose.Tasks خيار `setReduceFooterGap(true)` لعمليات حفظ الصور وPDF وHTML. تمكين هذه العلامة يخبر المحرك بضغط المسافة بين صف المهمة الأخير وتذييل الصفحة. عندما يتم تعيينها إلى true، يقوم المُعالج تلقائيًا بقص الهوامش دون قطع أي بيانات مهمة، مما ينتج تخطيط صفحة أنظف.

## حفظ المشروع كصورة باستخدام Aspose.Tasks
`ImageSaveOptions` يضبط كيفية تحويل المشروع إلى ملف صورة.  
تتيح لك فئة `ImageSaveOptions` تصدير لقطة جدول زمني كملف PNG أو JPEG أو BMP. عندما تقوم أيضًا بتمكين `setReduceFooterGap(true)`، تعكس الصورة المولدة تخطيط PDF المدمج، مما يمنحك تصورًا نظيفًا للعروض التقديمية أو لوحات التحكم.

## تصدير مشروع Java إلى PDF
الأقسام التالية تستعرض سير عمل كامل **java project export**، بدءًا من تحميل ملف MPP وحتى حفظه بثلاث صيغ مختلفة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك المتطلبات التالية:
1. مجموعة تطوير جافا (JDK) – الإصدار 8 أو أحدث.  
2. مكتبة Aspose.Tasks for Java – قم بتنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
قبل الغوص في جزء الترميز، دعنا نستورد الحزم اللازمة:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## الخطوة 1: توفير المسار إلى دليل البيانات الخاص بك
تأكد من استبدال `"Your Data Directory"` بالمسار إلى دليل البيانات الفعلي حيث يوجد ملف Microsoft Project الخاص بك (`HomeMovePlan.mpp` في هذا المثال).
```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: قراءة ملف MPP
هذا السطر من الشيفرة يقرأ ملف Microsoft Project المسمى `HomeMovePlan.mpp`.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## الخطوة 3: تعيين ImageSaveOptions (حفظ المشروع كصورة)
`ImageSaveOptions` يضبط كيفية تحويل المشروع إلى ملف صورة.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
قم بتكوين خيارات حفظ الصورة، مع تعيين `ReduceFooterGap` إلى `true` لتقليل الفجوة بين قائمة المهام والتذييل.

## الخطوة 4: حفظ كصورة
احفظ المشروع كصورة باستخدام الخيارات المكوَّنة.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```

## الخطوة 5: تعيين PdfSaveOptions (تصدير المشروع إلى PDF)
`PdfSaveOptions` يحدد الإعدادات لتصدير المشروع إلى صيغة PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
حدد خيارات حفظ PDF، مع التأكد من تعيين `ReduceFooterGap` إلى `true`.

## الخطوة 6: حفظ كـ PDF
احفظ المشروع كملف PDF باستخدام الخيارات المكوَّنة.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```

## الخطوة 7: تعيين HtmlSaveOptions
`HtmlSaveOptions` يتحكم في تحويل المشروع إلى HTML، بما في ذلك خيارات الأنماط والتخطيط.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
حدد خيارات حفظ HTML، مع تعيين `ReduceFooterGap` إلى `true`.

## الخطوة 8: حفظ كـ HTML
احفظ المشروع كملف HTML باستخدام الخيارات المكوَّنة.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```

## حالات الاستخدام الشائعة والنصائح
- **تقارير أصحاب المصلحة:** تصدير إلى PDF مع تقليل الفجوة في التذييل للحفاظ على التقارير مختصرة وصديقة للطباعة.  
- **لقطات لوحة التحكم:** استخدم تصدير الصورة عندما تحتاج إلى تصور سريع لـ Power BI أو Confluence.  
- **النشر على الويب:** تصدير HTML يحافظ على التفاعلية ويمكن دمجه مباشرةً في بوابات الإنترانت.  
- **نصيحة احترافية:** للمشاريع الكبيرة جدًا، زد `Resolution` في `ImageSaveOptions` إلى 300 dpi للحفاظ على الوضوح مع الاستفادة من تقليل الفجوة.

## الأسئلة المتكررة (إضافية)

**Q:** كيف يؤثر تقليل الفجوة في التذييل على التقسيم إلى صفحات؟  
A: يقلل من المساحة الفارغة في أسفل كل صفحة، مما يسمح بملء المزيد من المهام في صفحة واحدة وتقليل عدد الصفحات الإجمالي.

**Q:** هل يمكنني تطبيق إعداد تقليل الفجوة على صفحة واحدة فقط؟  
A: نعم، عن طريق تعيين `setRenderToSinglePage(true)` في `ImageSaveOptions` يمكنك التحكم في التقسيم إلى صفحات مع الاستمرار في تقليل الفجوة.

**Q:** هل خيار `setReduceFooterGap` متاح لتنسيقات إخراج أخرى؟  
A: حاليًا يدعم PNG وPDF وHTML. بالنسبة للتنسيقات الأخرى قد تحتاج إلى تعديل التخطيط يدويًا.

**Q:** ماذا لو كان مشروعي يحتوي على حقول مخصصة—هل يتم حفظها؟  
A: جميع الحقول المخصصة تُحفظ أثناء التصدير؛ تعديلات التخطيط تؤثر فقط على المسافات، وليس على البيانات.

**Q:** هل المكتبة تتعامل مع المشاريع الكبيرة بكفاءة؟  
A: تقوم Aspose.Tasks ببث البيانات ويمكنها معالجة ملفات MPP التي تتضمن مئات الصفحات دون تحميل الملف بالكامل في الذاكرة؛ ومع ذلك، احرص على تخصيص مساحة كافية من الذاكرة عند تصدير الصور عالية الدقة.

**آخر تحديث:** 2026-05-20  
**تم الاختبار مع:** Aspose.Tasks 24.11 for Java  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [حفظ المشروع كصورة – تنسيق 24bppRgb مع Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [حفظ المشروع كقالب، CSV، ونص مع Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بصيغة MPP مع Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}