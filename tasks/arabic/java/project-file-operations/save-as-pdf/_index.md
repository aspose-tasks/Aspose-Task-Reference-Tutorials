---
date: 2025-12-20
description: تعلم كيفية تصدير PDF في Aspose.Tasks للغة Java، دليل بسيط لتحويل ملفات
  MPP إلى PDF وحفظ ملفات مشروعك بكفاءة.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تصدير PDF في Aspose.Tasks – حفظ كملف PDF
url: /ar/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصدير PDF في Aspose.Tasks – حفظ كـ PDF

## مقدمة
في هذا الدرس، سنوضح لك **كيفية تصدير PDF** في Aspose.Tasks للـ Java، مع إرشادك من خلال عملية حفظ مشروع كملف PDF. باستخدام Aspose.Tasks، يمكنك **تحويل MPP إلى PDF** فعال، مما يتميز بالتوافق مع المشاركة عبر الفرق بين الشركاء. متابعة الخطوات التالية حتى يتم الحصول بسرعة على ملف PDF قابل للطباعة من أي ملف مشروع.

## إجابات سريعة
- **ماذا يعني “export PDF” في Aspose.Tasks؟** يعني تحويل ملف المشروع (مثلMPP) إلى مستند PDF يحافظ على التخطيط البصري.
- **ما الإصدار الرسمي؟** أي إصدار من Aspose.Tasks للـ Java يدعم `PdfSaveOptions` (أحدث الإصدارات).
- **هل أحتاج إلى ترخيص هذا التحويل؟** النسخة التجريبية لتعويض للطوير؛ مطلوب ترخيص تجاري للاستخدام في الإنتاج.
- **هل يمكنني تخصيص مظهر PDF؟** نعم – يمكنك ضبط مقياس الوقت، والأساطير، وغيرها من `PdfSaveOptions`.
- **هل يتغير بشكل سريع للإعلانات الجديدة؟** خلال فترة وجيزة؛ الأداء الموثوق على حجم المشروع والخيارات.

## ما هي "كيفية تصدير pdf" في سياق Aspose.Tasks؟
تصدير PDF باستخدام Aspose.Tasks يعني أخذ ملف المشروع (مثل`.mpp`،`.xml` أو`.xlsx`) تأكيد PDF يعكس مخطط جانت، أو استخدام النواة، أو أي تنسيق عرض آخر تقوم بتكوينه. هذا مفيد للتقارير، الوثائق، أو عروض مفيدة للقراءة فقط مع البيانات العلمية غير التقنية.

## لماذا تصدير ملفات المشروع إلى PDF؟
- **قابلة للقراءة باللغة الألمانية:** تعمل بصيغة PDF على أي جهاز دون الحاجة إلى برنامج المشروع الأصلي.
- **عرض رئيسي:** يوفر العديد من الوظائف والتخطيط للتقارير المتخصصة.
- **توزيع سهل:** مشاركة عبر البريد الإلكتروني، الإنترانت، أو التخزين السحابي دون القلق والتحكم في الاختلافات.
- **الا جديد والأرشفة:** ملفات PDF الجديدة للتخزين لفترة طويلة وتغيير التغيير.

## المتطلبات الأساسية
قبل، تأكد من ضرورة ما يلي:

1. **Java Development Kit (JDK):** JDK8 أو تثبيت على جهازك.
2. **Aspose.Tasks for Java Library:** تم تحميل المكتبة من الموقع الرسمي[هنا](https://releases.aspose.com/tasks/java/).
3. **ملف المشروع:** احصل على ملف المشروع الموجود (مثل`HomeMovePlan.mpp`) جاهز للتحويل.

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

### الخطوة 1: قراءة ملف المشروع المدخل
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يقع ملف `.mpp` الخاص بك. هذا يحمل المشروع في الذاكرة حتى تتمكن من تعديل أو تصديره.

### الخطوة 2: حفظ المشروع كملف PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
السطر أعلاه يقوم بعملية **حفظ المشروع كـ PDF** مباشرة، وينشئ `Project5.pdf` في نفس المجلد.

### الخطوة 3: ملاءمة المحتوى لحجم الخلية (خيارات حفظ PDF المتقدمة)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
فيما يلي شرح لكيفية استخدام **خيارات حفظ PDF** للتحكم في التخطيط:
- `setFitContent(true)` يجبر المحتوى على ملاءمة عرض الخلية.  
- `setTimescale(Timescale.Months)` يغيّر مقياس الوقت إلى شهور.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` يختار عرض استخدام المهام.

### الخطوة 4: إخفاء مفاتيح الخريطة (إخراج أنظف)
```java
o.setLegendOnEachPage(false);
```
إلغاء تمكين الأساطير يمكن أن يجعل PDF أكثر تكثيفًا، خاصةً للمشروعات الكبيرة.

### الخطوة 5: حفظ المشروع مع تطبيق الخيارات
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
هذه الخطوة النهائية تكتب ملف PDF باستخدام الخيارات المخصصة المعرفة أعلاه، مما ينتج وثيقة نظيفة، بمقياس شهري دون أساطير في كل صفحة.

## المشكلات والنصائح الشائعة
- **الملف غير موجود:** تأكد من أن `dataDir` يستأنف بفاصل الملف (`/` أو `\\`) تأكد من الدليل الصحيح.
- **الصفحات المخصصة:** تأكد من أن `PresentationFormat` المختار يتطابق مع العرض الذي تتوقعه (مثل Gantt أو Task Use).
- **الملفات الكبيرة خلال فترة أطول:** فكر في ضبط `o.setFitContent(false)` إعلانات كبيرة جدًا لوقت العمل الرئيسي.

## الأسئلة المتداولة

**س: هل Aspose.Tasks متوافق مع جميع إصدارات Java؟**
ج: نعم، يدعم Aspose.Tasks إصدارات Java المتعددة من JDK6 وما فوق.

**س: هل يمكنني تخصيص مظهر مخرج PDF؟**
ج: مؤكد! يوفر Aspose.Tasks العديد من **pdf save options**—مثل مقياس الوقت، وإظهار الأساطير، وتنسيق العرض — لتخصيص PDF وفقًا لاحتياجاتك.

**س: هل يدعم Aspose.Tasks صيغ ملفات أخرى للتحويل؟**
ج: نعم، يمكنك التحويل بين MPP، XML، XLSX، والعديد من الصيغ الأخرى، مما يجعل أداة متعددة الاستخدامات لـ **تحويل mpp إلى pdf** والتحويلات الأخرى.

**س: هل يمكن العثور على نسخة أساسية لـ Aspose.Tasks؟**
ج: نعم، يمكنك الحصول على نسخة مجانية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟**
ج: للحصول على الدليل الدائم، زر المنتدى الرسمي[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## خاتمة
باتباعك لهذا الدليل، أصبحت الآن تعرف **كيفية تصدير PDF** من أي مشروع Java باستخدام Aspose.Tasks، بدءًا من حفظ سطر واحد بسيط إلى تخصيص متقدم باستخدام `PdfSaveOptions`. استخدم هذه التقنيات لإنتاج PDFs مصقولة وقابلة للمشاركة للتقارير، عروض العملاء، أو لأغراض الأرشفة.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}