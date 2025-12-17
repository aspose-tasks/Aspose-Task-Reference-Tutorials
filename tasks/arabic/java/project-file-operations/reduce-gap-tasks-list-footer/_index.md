---
date: 2025-12-17
description: تعلم كيفية تصدير المشروع إلى PDF، وتقليل الفجوة في التذييل، وحفظ المشروع
  كصورة باستخدام Aspose.Tasks للغة Java. قم بتحسين تخطيط MS Project بسهولة.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
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
في هذا الدرس ستكتشف **كيفية تصدير المشروع إلى PDF** مع تقليل المسافة غير المرغوب فيها بين قائمة المهام وتذييل الصفحة في ملفات Microsoft Project. في نهاية الدليل ستتمكن من إنشاء ملفات PDF نظيفة، وصور PNG، وصفحات HTML بتصميم مدمج باستخدام Aspose.Tasks للغة Java. دعنا نتبع العملية خطوة بخطوة.

## إجابات سريعة  
- **ماذا يعني “تصدير المشروع إلى PDF”؟** يحول ملف MPP إلى مستند PDF مع الحفاظ على المهام والجداول الزمنية والتنسيق.  
- **لماذا تقليل فجوة التذييل؟** الفجوة الأصغر تُنتج تقارير أكثر تماسكًا ومظهرًا احترافيًا، خاصةً للوثائق المطبوعة أو المعروضة على الويب.  
- **هل يمكنني أيضًا حفظ المشروع كصورة؟** نعم – يدعم Aspose.Tasks صيغ PNG و JPEG وغيرها من صيغ الصور.  
- **هل أحتاج إلى ترخيص خاص؟** نسخة تجريبية مجانية متاحة؛ يلزم الحصول على ترخيص تجاري للاستخدام الإنتاجي.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى تعمل مع مكتبة Aspose.Tasks الحالية.

## ما هو “تصدير المشروع إلى PDF”؟  
تحويل المشروع إلى PDF يغيّر بنية MPP الداخلية إلى مستند محمول يمكن فتحه على أي جهاز دون الحاجة إلى Microsoft Project. هذا مثالي لمشاركة تقارير الحالة، وتحديثات أصحاب المصلحة، أو أرشفة خطط المشروع.

## لماذا تقليل فجوة التذييل؟  
فجوة التذييل الافتراضية قد تضيف مساحة بيضاء غير ضرورية، مما يسبب مشاكل في التقسيم إلى صفحات ومظهر غير متوازن. تقليل الفجوة يضمن أن المحتوى يستخدم الصفحة بكفاءة، مما يجعل ملف PDF أو الصورة النهائية أكثر قابلية للقراءة.

## كيفية تقليل الفجوة بين قائمة المهام وتذييل الصفحة؟  
يوفر Aspose.Tasks خيار `setReduceFooterGap(true)` لعمليات حفظ الصور، PDF، وHTML. تمكين هذا العلم يُخبر المحرك بضغط المسافة بين صف المهمة الأخير وتذييل الصفحة.

## حفظ المشروع كصورة باستخدام Aspose.Tasks  
إذا كنت بحاجة إلى لقطة بصرية لجدولك الزمني، يمكنك **حفظ المشروع كصورة** (PNG) مع تطبيق نفس إعدادات تقليل الفجوة.

## تصدير مشروع Java إلى PDF  
الأقسام التالية تستعرض سير عمل كامل **لتصدير مشروع Java**، بدءًا من تحميل ملف MPP وحتى حفظه بثلاث صيغ مختلفة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. مجموعة تطوير Java (JDK) – الإصدار 8 أو أحدث.  
2. مكتبة Aspose.Tasks للغة Java – قم بتنزيلها من [here](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
قبل الغوص في جزء البرمجة، لنستورد الحزم الضرورية:
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
```java
String dataDir = "Your Data Directory";
```
تأكد من استبدال `"Your Data Directory"` بالمسار إلى دليل البيانات الفعلي حيث يقع ملف Microsoft Project الخاص بك (`HomeMovePlan.mpp` في هذا المثال).

## الخطوة 2: قراءة ملف MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
هذا السطر من الشيفرة يقرأ ملف Microsoft Project المسمى `HomeMovePlan.mpp`.

## الخطوة 3: تعيين ImageSaveOptions (حفظ المشروع كصورة)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
قم بتكوين خيارات حفظ الصورة، واضبط `ReduceFooterGap` على `true` لتقليل الفجوة بين قائمة المهام وتذييل الصفحة.

## الخطوة 4: حفظ كصورة
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
احفظ المشروع كصورة باستخدام الخيارات المُكوَّنة.

## الخطوة 5: تعيين PdfSaveOptions (تصدير المشروع إلى PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
حدد خيارات حفظ PDF، مع التأكد من ضبط `ReduceFooterGap` على `true`.

## الخطوة 6: حفظ كملف PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
احفظ المشروع كملف PDF باستخدام الخيارات المُكوَّنة.

## الخطوة 7: تعيين HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
حدد خيارات حفظ HTML، واضبط `ReduceFooterGap` على `true`.

## الخطوة 8: حفظ كملف HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
احفظ المشروع كملف HTML باستخدام الخيارات المُكوَّنة.

## الخلاصة  
في الختام، تقليل الفجوة بين قائمة المهام وتذييل الصفحة في ملفات Microsoft Project عملية بسيطة باستخدام Aspose.Tasks للغة Java. باتباع الخطوات الموضحة في هذا الدرس، يمكنك بسهولة **تصدير المشروع إلى PDF**، حفظه كصورة، أو إنشاء HTML مع الحفاظ على تخطيط مدمج واحترافي.

## الأسئلة المتكررة

### س: هل Aspose.Tasks متوافق مع جميع إصدارات Microsoft Project؟
ج: يدعم Aspose.Tasks صيغ Microsoft Project من 2003 إلى 2019، مما يضمن التوافق عبر الإصدارات المختلفة.

### س: هل يمكنني تخصيص مظهر التذييل في مستندات مشروعي؟
ج: نعم، يوفر Aspose.Tasks خيارات واسعة لتخصيص مظهر التذييلات، بما في ذلك تقليل الفجوات وضبط موضع المحتوى.

### س: هل يدعم Aspose.Tasks حفظ المشاريع بصيغ غير PNG و PDF و HTML؟
ج: نعم، يدعم Aspose.Tasks مجموعة واسعة من الصيغ، بما في ذلك XLSX و XML و MPP وغيرها.

### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من [here](https://releases.aspose.com/).

### س: أين يمكنني الحصول على الدعم إذا واجهت أي مشكلات أثناء استخدام Aspose.Tasks؟
ج: يمكنك الحصول على المساعدة من منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## الأسئلة المتكررة (إضافية)

**س: كيف يؤثر تقليل فجوة التذييل على التقسيم إلى صفحات؟**  
ج: يقلل من المساحة الفارغة في أسفل كل صفحة، مما يسمح بوجود المزيد من المهام في صفحة واحدة وتقليل عدد الصفحات الإجمالي.

**س: هل يمكنني تطبيق إعداد تقليل الفجوة على صفحة واحدة فقط؟**  
ج: نعم، عن طريق ضبط `setRenderToSinglePage(true)` في `ImageSaveOptions` يمكنك التحكم في التقسيم إلى صفحات مع الاستمرار في تقليل الفجوة.

**س: هل خيار `setReduceFooterGap` متاح لصيغ إخراج أخرى؟**  
ج: حاليًا يدعم هذا الخيار تصدير PNG و PDF و HTML. بالنسبة للصيغ الأخرى قد تحتاج إلى تعديل التخطيط يدويًا.

**س: ماذا لو كان مشروعي يحتوي على حقول مخصصة—هل يتم الحفاظ عليها؟**  
ج: جميع الحقول المخصصة تُحفظ أثناء التصدير؛ تعديلات التخطيط تؤثر فقط على المسافات، وليس على البيانات.

**س: هل تتعامل المكتبة مع المشاريع الكبيرة بكفاءة؟**  
ج: يقوم Aspose.Tasks ببث البيانات ويمكنه معالجة ملفات MPP الكبيرة؛ ومع ذلك، تأكد من توفر ذاكرة كافية عند التصدير إلى صور عالية الدقة.

---

**آخر تحديث:** 2025-12-17  
**تم الاختبار مع:** Aspose.Tasks 24.11 للغة Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}