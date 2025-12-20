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

## Introduction
في هذا الدرس، سنوضح لك **كيفية تصدير PDF** في Aspose.Tasks للـ Java، مع إرشادك خلال عملية حفظ مشروع كملف PDF. باستخدام Aspose.Tasks، يمكنك **تحويل MPP إلى PDF** بكفاءة، مما يضمن التوافق وسهولة المشاركة عبر الفرق وأصحاب المصلحة. دعنا نستعرض الخطوات حتى تتمكن من الحصول بسرعة على PDF قابل للطباعة من أي ملف مشروع.

## Quick Answers
- **ماذا يعني “export PDF” في Aspose.Tasks؟** يعني تحويل ملف مشروع (مثل MPP) إلى مستند PDF يحافظ على التخطيط البصري.  
- **ما إصدار المكتبة المطلوب؟** أي إصدار من Aspose.Tasks للـ Java يدعم `PdfSaveOptions` (يوصى بأحدث إصدار).  
- **هل أحتاج إلى ترخيص لهذا التحويل؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للاستخدام في الإنتاج.  
- **هل يمكنني تخصيص مظهر PDF؟** نعم – يمكنك ضبط مقياس الوقت، الأساطير، وغيرها من `PdfSaveOptions`.  
- **هل التحويل سريع للمشروعات الكبيرة؟** عادةً خلال ثوانٍ؛ الأداء يعتمد على حجم المشروع والخيارات المختارة.

## What is “how to export pdf” in the context of Aspose.Tasks?
تصدير PDF باستخدام Aspose.Tasks يعني أخذ ملف مشروع (مثل `.mpp`، `.xml` أو `.xlsx`) وإنشاء PDF يعكس مخطط جانت، أو عرض استخدام المهام، أو أي تنسيق عرض آخر تقوم بتكوينه. هذا مفيد للتقارير، الوثائق، أو مشاركة عروض للقراءة فقط مع أصحاب المصلحة غير التقنيين.

## Why Export Project Files to PDF?
- **قابلية القراءة العالمية:** يعمل PDF على أي جهاز دون الحاجة إلى برنامج المشروع الأصلي.  
- **عرض احترافي:** الحفاظ على التنسيق، الألوان، والتخطيط لتقارير موجهة للعملاء.  
- **توزيع سهل:** مشاركة عبر البريد الإلكتروني، الإنترانت، أو التخزين السحابي دون القلق بشأن التحكم في الإصدارات.  
- **الامتثال والأرشفة:** PDFs مثالية للتخزين طويل الأجل والامتثال التنظيمي.

## Prerequisites
قبل البدء، تأكد من توفر ما يلي:

1. **Java Development Kit (JDK):** JDK 8 أو أحدث مثبت على جهازك.  
2. **Aspose.Tasks for Java Library:** قم بتحميل المكتبة من الموقع الرسمي [here](https://releases.aspose.com/tasks/java/).  
3. **ملف مشروع:** احصل على ملف مشروع موجود (مثل `HomeMovePlan.mpp`) جاهز للتحويل.

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يقع ملف `.mpp` الخاص بك. هذا يحمل المشروع في الذاكرة حتى تتمكن من تعديل أو تصديره.

### Step 2: Save the Project as PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
السطر أعلاه يقوم بعملية **حفظ المشروع كـ PDF** مباشرة، وينشئ `Project5.pdf` في نفس المجلد.

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Here we demonstrate the use of **pdf save options** to control layout:
- `setFitContent(true)` يجبر المحتوى على ملاءمة عرض الخلية.  
- `setTimescale(Timescale.Months)` يغيّر مقياس الوقت إلى شهور.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` يختار عرض استخدام المهام.

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
إلغاء تمكين الأساطير يمكن أن يجعل PDF أكثر تكثيفًا، خاصةً للمشروعات الكبيرة.

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
هذه الخطوة النهائية تكتب ملف PDF باستخدام الخيارات المخصصة المعرفة أعلاه، مما ينتج وثيقة نظيفة، بمقياس شهري دون أساطير في كل صفحة.

## Common Issues & Tips
- **الملف غير موجود:** تأكد من أن `dataDir` ينتهي بفاصل ملف (`/` أو `\\`) ويشير إلى الدليل الصحيح.  
- **صفحات فارغة:** تحقق من أن `PresentationFormat` المختار يتطابق مع العرض الذي تتوقعه (مثل Gantt أو Task Usage).  
- **الملفات الكبيرة تستغرق وقتًا أطول:** فكر في ضبط `o.setFitContent(false)` للمشروعات الكبيرة جدًا لتقليل وقت المعالجة.

## Frequently Asked Questions

**س: هل Aspose.Tasks متوافق مع جميع إصدارات Java؟**  
ج: نعم، يدعم Aspose.Tasks إصدارات Java بدءًا من JDK 6 وما فوق.

**س: هل يمكنني تخصيص مظهر مخرجات PDF؟**  
ج: بالتأكيد! يوفر Aspose.Tasks العديد من **pdf save options**—مثل مقياس الوقت، إظهار الأساطير، وتنسيق العرض—لتخصيص PDF وفقًا لاحتياجاتك.

**س: هل يدعم Aspose.Tasks صيغ ملفات أخرى للتحويل؟**  
ج: نعم، يمكنك التحويل بين MPP، XML، XLSX، والعديد من الصيغ الأخرى، مما يجعله أداة متعددة الاستخدامات لـ **convert mpp to pdf** والتحويلات الأخرى.

**س: هل توجد نسخة تجريبية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من [here](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟**  
ج: للحصول على الدعم والمساعدة، زر المنتدى الرسمي [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
باتباعك لهذا الدليل، أصبحت الآن تعرف **كيفية تصدير PDF** من أي مشروع Java باستخدام Aspose.Tasks، بدءًا من حفظ سطر واحد بسيط إلى تخصيص متقدم باستخدام `PdfSaveOptions`. استخدم هذه التقنيات لإنتاج PDFs مصقولة وقابلة للمشاركة للتقارير، عروض العملاء، أو لأغراض الأرشفة.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}