---
title: حفظ بصيغة PDF في Aspose.Tasks
linktitle: حفظ بصيغة PDF في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحويل ملفات المشروع إلى PDF باستخدام Aspose.Tasks لـ Java. خطوات بسيطة لتحويل فعال.
type: docs
weight: 17
url: /ar/java/project-file-operations/save-as-pdf/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية حفظ المشروع كملف PDF باستخدام Aspose.Tasks لـ Java. باستخدام Aspose.Tasks، يمكنك تحويل ملفات مشروعك بكفاءة إلى تنسيق PDF، مما يضمن التوافق وسهولة المشاركة. دعونا نتعمق في الخطوات:
## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت مكتبة Aspose.Tasks. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tasks/java/).
3. ملف مشروع: قم بإعداد ملف مشروع (على سبيل المثال، HomeMovePlan.mpp) تريد تحويله إلى PDF.

## حزم الاستيراد
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## الخطوة 1: قراءة ملف مشروع الإدخال
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 تأكد من استبدال`"Your Data Directory"` مع المسار إلى دليل البيانات الخاص بك الذي يحتوي على ملف المشروع.
## الخطوة 2: احفظ المشروع بصيغة PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
يقوم مقتطف الكود هذا بحفظ المشروع كملف PDF باسم "Project5.pdf".
## الخطوة 3: ملاءمة المحتويات لحجم الخلية
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
هنا، نقوم بتعيين خيارات لحفظ ملف PDF، بما في ذلك المحتوى الملائم والجدول الزمني وتنسيق العرض التقديمي.
## الخطوة 4: إخفاء الأساطير
```java
o.setLegendOnEachPage(false);
```
تخفي هذه الخطوة وسائل الإيضاح في كل صفحة من صفحات ملف PDF.
## الخطوة 5: احفظ المشروع بالخيارات المطبقة
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
وأخيرًا، يحفظ هذا الكود المشروع مع الخيارات المطبقة على ملف PDF.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.Tasks لـ Java لحفظ مشروع كملف PDF. باتباع هذه الخطوات البسيطة، يمكنك تحويل ملفات مشروعك بكفاءة لمشاركتها وتوزيعها بسهولة.
## الأسئلة الشائعة
### س: هل Aspose.Tasks متوافق مع جميع إصدارات Java؟
ج: نعم، يدعم Aspose.Tasks إصدارات Java بدءًا من JDK 6 وما فوق.
### س: هل يمكنني تخصيص مظهر مخرجات PDF؟
ج: بالتأكيد! يوفر Aspose.Tasks خيارات متنوعة لتخصيص مخرجات PDF وفقًا لمتطلباتك.
### س: هل يدعم Aspose.Tasks تنسيقات الملفات الأخرى للتحويل؟
ج: نعم، يدعم Aspose.Tasks نطاقًا واسعًا من تنسيقات الملفات، بما في ذلك MPP وXML وXLSX والمزيد.
### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 ج: للحصول على الدعم والمساعدة، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).