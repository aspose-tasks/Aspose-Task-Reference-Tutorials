---
date: 2026-03-27
description: تعلم كيفية حفظ المشروع كملف PDF باستخدام Aspose.Tasks للغة Java، دليل
  بسيط لتحويل MPP إلى PDF وتصدير ملفات المشروع بكفاءة.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية حفظ المشروع كملف PDF باستخدام Aspose.Tasks – دليل التصدير
url: /ar/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيف تحفظ المشروع كملف PDF باستخدام Aspose.Tasks – دليل التصدير

## المقدمة
في هذا البرنامج التعليمي، ستكتشف **كيفية حفظ المشروع كملف pdf** باستخدام Aspose.Tasks for Java. سنرشدك خطوة بخطوة من التحويل بسطر واحد إلى تخصيص PDF متقدم، بحيث يمكنك تحويل أي ملف MPP (أو أي صيغة مدعومة أخرى) إلى مستند PDF مصقول وقابل للمشاركة. سواء كنت بحاجة إلى تقرير قابل للطباعة بسرعة أو مخطط جانت مُنسق بالكامل، ستقودك هذه الخطوات إلى النتيجة بسرعة.

## إجابات سريعة
- **ماذا يعني “تصدير PDF” في Aspose.Tasks؟** يعني تحويل ملف مشروع (مثل MPP) إلى مستند PDF يحافظ على التخطيط البصري.  
- **ما هو إصدار المكتبة المطلوب؟** أي إصدار من Aspose.Tasks for Java يدعم `PdfSaveOptions` (يفضل أحدث إصدار).  
- **هل أحتاج إلى ترخيص لهذا التحويل؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للاستخدام في الإنتاج.  
- **هل يمكنني تخصيص مظهر PDF؟** نعم – يمكنك ضبط مقياس الوقت، الأساطير، وغيرها من `PdfSaveOptions`.  
- **هل التحويل سريع للمشروعات الكبيرة؟** عادةً ثوانٍ؛ تعتمد السرعة على حجم المشروع والخيارات المختارة.

## ما معنى “حفظ المشروع كملف pdf” في سياق Aspose.Tasks؟
حفظ المشروع كملف PDF باستخدام Aspose.Tasks يعني أخذ ملف مشروع (مثل `.mpp`، `.xml` أو `.xlsx`) وإنشاء PDF يعكس مخطط جانت، أو عرض استخدام المهام، أو أي تنسيق عرض آخر تقوم بتكوينه. هذا مفيد للتقارير، الوثائق، أو مشاركة عروض للقراءة فقط مع أصحاب المصلحة غير التقنيين.

## لماذا تصدير مخطط جانت إلى PDF؟
- **قابلية القراءة العالمية:** يمكن فتح ملفات PDF على أي جهاز دون الحاجة إلى برنامج المشروع الأصلي.  
- **عرض احترافي:** الحفاظ على الألوان، الخطوط، والتخطيط لتقارير موجهة للعملاء.  
- **سهولة التوزيع:** مشاركة عبر البريد الإلكتروني، الإنترانت، أو التخزين السحابي دون القلق بشأن التحكم في الإصدارات.  
- **الامتثال والأرشفة:** PDF مثالي للتخزين طويل الأمد والامتثال التنظيمي.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

1. **مجموعة تطوير جافا (JDK):** JDK 8 أو أحدث مثبت على جهازك.  
2. **مكتبة Aspose.Tasks for Java:** حمّل المكتبة من الموقع الرسمي [هنا](https://releases.aspose.com/tasks/java/).  
3. **ملف مشروع:** احصل على ملف مشروع موجود (مثل `HomeMovePlan.mpp`) جاهز للتحويل.

## استيراد الحزم
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## دليل خطوة بخطوة

### الخطوة 1: قراءة ملف المشروع الإدخالي
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يقع ملف `.mpp` الخاص بك. هذا يحمل المشروع في الذاكرة لتتمكن من معالجته أو تصديره.

### الخطوة 2: حفظ المشروع كملف PDF (تحويل أساسي)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
السطر أعلاه ينفذ عملية **حفظ المشروع كملف pdf** بسيطة، وينشئ `Project5.pdf` في نفس المجلد.

### الخطوة 3: ملاءمة المحتوى لحجم الخلية (خيارات حفظ PDF متقدمة)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
هنا نوضح استخدام **pdf save options** للتحكم في التخطيط:
- `setFitContent(true)` يجبر المحتوى على ملاءمة عرض الخلية.  
- `setTimescale(Timescale.Months)` يغيّر مقياس الوقت إلى الأشهر.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` يحدد عرض استخدام المهام.

### الخطوة 4: إخفاء الأساطير (مخرجات أنظف)
```java
o.setLegendOnEachPage(false);
```
إلغاء تمكين الأساطير يمكن أن يجعل PDF أكثر تجميعًا، خاصةً للمشروعات الكبيرة.

### الخطوة 5: حفظ المشروع مع الخيارات المطبقة
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
هذه الخطوة النهائية تكتب ملف PDF باستخدام الخيارات المخصصة المعرفة أعلاه، منتجة مستندًا نظيفًا بمقياس شهري دون أساطير في كل صفحة.

## تصدير مخطط جانت إلى PDF – تنسيق مخصص
إذا رغبت في تصدير مخطط جانت فقط بمظهر محدد، اضبط `PresentationFormat` إلى `GanttChart` وعدّل الخيارات الإضافية مثل `setBarColor` أو `setShowCriticalTasks`. يتيح لك هذا **export gantt chart to pdf** مع تحكم كامل في العناصر البصرية.

## المشكلات الشائعة والنصائح
- **الملف غير موجود:** تأكد من أن `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) ويشير إلى الدليل الصحيح.  
- **صفحات فارغة:** تحقق من أن `PresentationFormat` المختار يتطابق مع العرض الذي تتوقعه (مثل Gantt أو Task Usage).  
- **الملفات الكبيرة تستغرق وقتًا أطول:** فكر في ضبط `o.setFitContent(false)` للمشروعات الضخمة لتقليل زمن المعالجة.  

## الأسئلة المتكررة

**س: هل Aspose.Tasks متوافق مع جميع إصدارات جافا؟**  
ج: نعم، يدعم Aspose.Tasks إصدارات جافا بدءًا من JDK 6 وما فوق.

**س: هل يمكنني تخصيص مظهر مخرجات PDF؟**  
ج: بالتأكيد! يوفر Aspose.Tasks العديد من **pdf save options**—مثل مقياس الوقت، إظهار الأساطير، وتنسيق العرض—لتكييف PDF وفقًا لاحتياجاتك.

**س: هل يدعم Aspose.Tasks صيغ ملفات أخرى للتحويل؟**  
ج: نعم، يمكنك التحويل بين MPP، XML، XLSX، والعديد من الصيغ الأخرى، مما يجعله أداة متعددة الاستخدامات لـ **convert mpp to pdf** وتحويلات أخرى.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟**  
ج: للحصول على الدعم والمساعدة، زر المنتدى الرسمي لـ [Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## الخاتمة
باتباعك لهذا الدليل، أصبحت الآن تعرف **كيفية حفظ المشروع كملف pdf** من أي مشروع جافا باستخدام Aspose.Tasks، بدءًا من حفظ سطر واحد بسيط إلى تخصيص متقدم باستخدام `PdfSaveOptions`. استخدم هذه التقنيات لإنتاج ملفات PDF مصقولة وقابلة للمشاركة للتقارير، عروض العملاء، أو الأرشفة.

---

**آخر تحديث:** 2026-03-27  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}