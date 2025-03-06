---
title: عرض استخدام الموارد وعرض الورقة في Aspose.Tasks
linktitle: عرض استخدام الموارد وعرض الورقة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية عرض استخدام موارد MS Project وطرق عرض الورقة في Aspose.Tasks لـ Java. اتبع دليلنا خطوة بخطوة لإنشاء تقارير PDF مفصلة دون عناء.
weight: 16
url: /ar/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# عرض استخدام الموارد وعرض الورقة في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Tasks لـ Java لعرض استخدام موارد MS Project وطرق عرض الورقة. Aspose.Tasks هي مكتبة Java قوية تتيح للمطورين العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من تثبيت المتطلبات الأساسية التالية وإعدادها:
1. Java Development Kit (JDK): تأكد من تثبيت Java Development Kit على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من موقع Oracle الإلكتروني.
2.  Aspose.Tasks لـ Java: قم بتنزيل وتثبيت مكتبة Aspose.Tasks لـ Java من[صفحة التحميل](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة لمشروع Java الخاص بك:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## الخطوة 1: اقرأ المشروع المصدر
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
// اقرأ المشروع المصدر
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
في هذه الخطوة، نحدد المسار إلى ملف المشروع المصدر (`ResourceUsageView.mpp` ) واستخدم`Project` الصف لقراءتها.
## الخطوة 2: تحديد خيارات الحفظ باستخدام إعدادات النطاق الزمني المطلوبة
```java
// حدد SaveOptions مع إعدادات TimeScale المطلوبة كأيام
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 وهنا نحدد`SaveOptions` مع المطلوب`TimeScale` إعدادات. في هذا المثال، قمنا بتعيين`TimeScale` إلى أيام.
## الخطوة 3: قم بتعيين تنسيق العرض التقديمي على ResourceUsage
```java
// قم بتعيين تنسيق العرض التقديمي على ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 لقد قمنا بتعيين تنسيق العرض التقديمي على`ResourceUsage`، للإشارة إلى أننا نريد عرض طريقة عرض استخدام الموارد.
## الخطوة 4: احفظ المشروع
```java
// احفظ المشروع
project.save(dataDir + days, options);
```
وأخيراً نقوم بحفظ المشروع بالخيارات المحددة. في هذا المثال، سيتم حفظ ملف الإخراج باسم`result_days.pdf`.
## الخطوة 5: عرض طرق العرض لإعدادات مقياس الوقت الأخرى
كرر الخطوات من 2 إلى 4 لعرض طرق العرض باستخدام إعدادات TimeScale مختلفة (ThirdsOfMonths وMonths).
```java
// اضبط إعدادات الجدول الزمني على ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// احفظ المشروع
project.save(thirds, options);
// اضبط إعدادات الجدول الزمني على الأشهر
options.setTimescale(Timescale.Months);
// احفظ المشروع
project.save(dataDir + months, options);
```
 التأكد من تغيير`Timescale` الإعدادات وفقًا لكل عرض.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية استخدام Aspose.Tasks لـ Java لعرض استخدام موارد MS Project وطرق عرض الورقة. باتباع الخطوات الموضحة أعلاه، يمكنك إنشاء طرق العرض هذه بكفاءة بتنسيق PDF، مما يسهل تصور وتحليل بيانات مشروعك بشكل أفضل.
## الأسئلة الشائعة
### هل يمكن لـ Aspose.Tasks عرض طرق عرض أخرى إلى جانب استخدام الموارد والورقة؟
يدعم Aspose.Tasks عرض طرق عرض متنوعة مثل مخطط جانت، واستخدام المهام، وطرق عرض التقويم، وغيرها.
### هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟
نعم، يدعم Aspose.Tasks نطاقًا واسعًا من تنسيقات ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### هل يمكنني تخصيص مظهر العروض المقدمة باستخدام Aspose.Tasks؟
قطعاً! يوفر Aspose.Tasks خيارات شاملة لتخصيص مظهر وتخطيط طرق العرض المقدمة لتناسب متطلباتك المحددة.
### هل يتطلب Aspose.Tasks تثبيت Microsoft Project على النظام؟
لا، Aspose.Tasks هي مكتبة مستقلة ولا تتطلب تثبيت Microsoft Project لتعمل.
### هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟
 نعم، يمكن لمستخدمي Aspose.Tasks الاستفادة من الدعم الفني من خلال[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
