---
title: عرض بيانات مشروع MS بتنسيق 24bppRgb في Aspose.Tasks
linktitle: عرض البيانات بتنسيق 24bppRgb في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية عرض بيانات MS Project كصور في Java باستخدام Aspose.Tasks. اتبع البرنامج التعليمي خطوة بخطوة لتحقيق التكامل السلس.
weight: 11
url: /ar/java/project-file-operations/render-data-format-24bppRgb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# عرض بيانات مشروع MS بتنسيق 24bppRgb في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض البيانات بتنسيق MS Project 24bppRgb باستخدام Aspose.Tasks لـ Java. يمكن أن يكون عرض بيانات المشروع في تنسيق صورة مفيدًا لأغراض متعددة مثل مشاركة تقدم المشروع بشكل مرئي أو إنشاء التقارير.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وتثبيته من[هنا](https://releases.aspose.com/tasks/java/).
3. المعرفة الأساسية ببرمجة Java: سيكون الإلمام بلغة برمجة Java مفيدًا لفهم أمثلة التعليمات البرمجية وتنفيذها.

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

دعنا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تحديد دليل البيانات
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
```
في هذه الخطوة، يمكنك تحديد الدليل الذي توجد به بيانات مشروعك. يستبدل`"Your Data Directory"` مع المسار الفعلي إلى دليل البيانات الخاص بك.
## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
هنا نقوم بتحميل ملف MS Project (`project.mpp` ) باستخدام Aspose.Tasks وتخزينه في ملف`project` هدف.
## الخطوة 3: تكوين خيارات حفظ الصورة
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
تتضمن هذه الخطوة تكوين الخيارات لحفظ بيانات المشروع كصورة. نحدد تنسيق الصورة (TIFF)، والدقة الأفقية والرأسية، وتنسيق البكسل (24bppRgb).
## الخطوة 4: حفظ بيانات المشروع كصورة
```java
project.save(dataDir + "resFile.tif", options);
```
وأخيرا، نقوم بحفظ بيانات المشروع كملف صورة (`resFile.tif`) بالخيارات المحددة.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية عرض بيانات المشروع بتنسيق MS Project 24bppRgb باستخدام Aspose.Tasks لـ Java. باتباع الخطوات المقدمة، يمكنك بسهولة تحويل بيانات مشروعك إلى تنسيق صورة لأغراض مختلفة.
## الأسئلة الشائعة
### س: هل يمكنني تقديم بيانات المشروع بتنسيقات صور أخرى؟
ج: نعم، يدعم Aspose.Tasks عرض بيانات المشروع في تنسيقات صور مختلفة مثل PNG وJPEG وBMP وما إلى ذلك.
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من MS Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات متعددة من MS Project بما في ذلك 2003 و2007 و2010 و2013 و2016.
### س: هل يمكنني تخصيص الدقة وتنسيق البكسل للصورة المعروضة؟
ج: نعم، يمكنك تخصيص الدقة وتنسيق البكسل وفقًا لمتطلباتك باستخدام Aspose.Tasks.
### س: هل يتطلب Aspose.Tasks ترخيصًا للاستخدام التجاري؟
 ج: نعم، أنت بحاجة إلى شراء ترخيص للاستخدام التجاري لـ Aspose.Tasks. يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 ج: يمكنك الحصول على الدعم لـ Aspose.Tasks من[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
