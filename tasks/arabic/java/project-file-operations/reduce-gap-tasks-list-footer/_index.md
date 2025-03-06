---
title: تقليل الفجوة بين قائمة المهام والتذييل في Aspose.Tasks
linktitle: تقليل الفجوة بين قائمة المهام والتذييل في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تقليل الفجوة بين قوائم مهام MS Project والتذييلات باستخدام Aspose.Tasks لـ Java. تحسين تخطيط وثيقة المشروع دون عناء.
weight: 10
url: /ar/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقليل الفجوة بين قائمة المهام والتذييل في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في تقليل الفجوة بين قائمة المهام والتذييل في ملفات Microsoft Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، ستتمكن من تحسين تخطيط مستندات مشروعك دون عناء.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java وتضمينها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
قبل الغوص في جزء البرمجة، دعونا نستورد الحزم الضرورية:
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
## الخطوة 1: قم بتوفير المسار إلى دليل البيانات الخاص بك
```java
String dataDir = "Your Data Directory";
```
 تأكد من استبدال`"Your Data Directory"` مع المسار إلى دليل البيانات الفعلي الخاص بك حيث يوجد ملف Microsoft Project الخاص بك (`HomeMovePlan.mpp` في هذا المثال) يقع.
## الخطوة 2: اقرأ ملف MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 يقرأ هذا السطر من التعليمات البرمجية ملف Microsoft Project المسمى`HomeMovePlan.mpp`.
## الخطوة 3: قم بتعيين ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 قم بتكوين خيارات حفظ الصورة، الإعداد`ReduceFooterGap` ل`true` لتقليل الفجوة بين قائمة المهام والتذييل.
## الخطوة 4: حفظ كصورة
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
احفظ المشروع كصورة مع الخيارات التي تم تكوينها.
## الخطوة 5: قم بتعيين خيارات PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 حدد خيارات حفظ PDF، مع التأكد من ضبطها`ReduceFooterGap` ل`true`.
## الخطوة 6: احفظ بصيغة PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
احفظ المشروع كملف PDF مع الخيارات التي تم تكوينها.
## الخطوة 7: قم بتعيين HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // تم ضبطه على صحيح
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 تحديد خيارات حفظ HTML، الإعداد`ReduceFooterGap` ل`true`.
## الخطوة 8: احفظ بتنسيق HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
احفظ المشروع كملف HTML مع الخيارات التي تم تكوينها.

## خاتمة
في الختام، يعد تقليل الفجوة بين قائمة المهام والتذييل في ملفات Microsoft Project عملية مباشرة مع Aspose.Tasks لـ Java. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحسين تخطيط مستندات مشروعك بكفاءة.

## الأسئلة الشائعة

### س: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟

ج: يدعم Aspose.Tasks تنسيقات Microsoft Project 2003-2019، مما يضمن التوافق عبر الإصدارات المختلفة.

### س: هل يمكنني تخصيص مظهر التذييل في مستندات مشروعي؟

ج: نعم، يوفر Aspose.Tasks خيارات شاملة لتخصيص مظهر التذييلات، بما في ذلك تقليل الفجوات وضبط موضع المحتوى.

### س: هل يدعم Aspose.Tasks حفظ المشاريع بتنسيقات أخرى غير PNG وPDF وHTML؟

ج: نعم، يدعم Aspose.Tasks نطاقًا واسعًا من التنسيقات، بما في ذلك XLSX وXML وMPP وغيرها.

### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟

 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).

### س: أين يمكنني الحصول على الدعم إذا واجهت أية مشكلات أثناء استخدام Aspose.Tasks؟

 ج: يمكنك الحصول على المساعدة من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
