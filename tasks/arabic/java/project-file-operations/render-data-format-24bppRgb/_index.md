---
date: 2026-03-21
description: تعلم كيفية تحسين جودة الصورة عن طريق حفظ المشروع كصورة 24bppRgb وتغيير
  دقة الصورة في Java باستخدام Aspose.Tasks. يوضح هذا الدليل أيضًا كيفية حفظ صيغ صور
  المشروع.
linktitle: Increase Image Quality – Save Project Image (24bppRgb)
second_title: Aspose.Tasks Java API
title: زيادة جودة الصورة – حفظ صورة المشروع (24bppRgb)
url: /ar/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# زيادة جودة الصورة – حفظ صورة المشروع (24bppRgb) باستخدام Aspose.Tasks

## Introduction
في هذا البرنامج التعليمي ستتعلم كيفية **زيادة جودة الصورة** عن طريق حفظ المشروع كصورة باستخدام تنسيق البكسل 24bppRgb مع Aspose.Tasks for Java. تحويل بيانات MS Project إلى صورة مفيد عندما تحتاج إلى مشاركة لقطة بصرية لجدول زمني، أو تضمين مخطط زمني في تقرير، أو إنشاء صور مصغرة لبوابة المشروع. سنوضح لك أيضًا كيفية **تغيير دقة الصورة java** بحيث يلبي الناتج متطلبات الجودة الدقيقة الخاصة بك.

## Quick Answers
- **هل يمكنني تحويل مشروع إلى صورة؟** نعم، يتيح لك Aspose.Tasks حفظ المشروع كملف TIFF أو PNG أو JPEG، إلخ.  
- **أي تنسيق بكسل يمنح أفضل عمق لوني؟** `Format24bppRgb` يوفر صورًا بألوان حقيقية (24‑بت).  
- **كيف أضبط دقة الصورة؟** استخدم `setHorizontalResolution` و `setVerticalResolution` على `ImageSaveOptions`.  
- **هل أحتاج إلى ترخيص للاستخدام الإنتاجي؟** يلزم الحصول على ترخيص تجاري للاستخدام غير التجريبي.  
- **هل هذا متوافق مع جميع إصدارات Java؟** يعمل مع Java 8 وما فوق.

## What is “save project image”?
حفظ المشروع كصورة يحول التمثيل البصري لملف Microsoft Project (`.mpp`) إلى تنسيق نقطي (مثل TIFF). يمكن عرض الملف الناتج في المتصفحات، أو إدراجه في المستندات، أو طباعته دون الحاجة إلى تطبيق Project الأصلي.

## Why use the 24bppRgb format to **increase image quality**?
تنسيق البكسل 24bppRgb يخزن كل بكسل بـ 8 بت للون الأحمر والأخضر والأزرق، مما يوفر جودة ألوان حقيقية دون قناة ألفا. هذا مثالي للتقارير ذات الوضوح العالي حيث تكون دقة الألوان مهمة، مع الحفاظ على حجم الملف معقولًا مقارنةً بتنسيقات 32‑بت.

## Common Use Cases
- **حفظ صورة مخطط جانت** لوحات معلومات حالة المشروع.  
- **إنشاء صورة مصغرة للمشروع** لألواح المعاينة في بوابات الويب.  
- **تخصيص دقة صورة المشروع** للإخراج للطباعة أو الشاشات عالية الـ DPI.  
- **حفظ صورة المشروع** بتنسيقات مختلفة (TIFF، PNG، JPEG) للتوثيق.

## Prerequisites
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – JDK 8 أو أحدث مثبت على جهازك.  
2. **Aspose.Tasks for Java** – قم بتنزيله وتثبيته من [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – الإلمام بتركيب Java وإعداد المشروع سيساعدك على متابعة مقتطفات الشيفرة.

## Import Packages
أولاً، استورد الفئات المطلوبة من Aspose.Tasks إلى مشروع Java الخاص بك:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يوجد ملف `.mpp` الخاص بك.

### Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
تقرأ هذه السطر ملف Microsoft Project (`project.mpp`) وتُنشئ كائن `Project` يمكن لـ Aspose.Tasks التعامل معه.

### Step 3: Configure Image Save Options
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
هنا نحدد تنسيق الإخراج إلى TIFF، ونحدد دقة **72 dpi** (يمكنك تغيير هذه القيم لتناسب احتياجاتك – هذا هو المكان الذي تقوم فيه بـ **تغيير دقة الصورة java**)، ونختار تنسيق البكسل 24bppRgb للحصول على إخراج بألوان حقيقية.

### Step 4: Save Project Data as Image
```java
project.save(dataDir + "resFile.tif", options);
```
طريقة `save` تكتب الصورة المُعالجة إلى `resFile.tif` باستخدام الخيارات المحددة أعلاه.

## Common Issues and Solutions
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **إخراج صورة فارغة** | قد يكون عرض المشروع فارغًا. | استدعِ `project.setDefaultView(ViewType.Gantt);` قبل الحفظ. |
| **صورة منخفضة الجودة** | تم ضبط الدقة منخفضة جدًا. | زيادة `setHorizontalResolution` و `setVerticalResolution` (مثلاً 150 dpi). |
| **تنسيق بكسل غير مدعوم** | استخدام نسخة قديمة من Aspose.Tasks. | الترقية إلى أحدث إصدار من Aspose.Tasks for Java. |

## Conclusion
أنت الآن تعرف كيفية **زيادة جودة الصورة** عن طريق حفظ المشروع كصورة بتنسيق 24bppRgb وضبط الدقة باستخدام Aspose.Tasks for Java. يتيح لك هذا النهج إنشاء تمثيلات بصرية واضحة ودقيقة الألوان لجدول مواعيد مشروعك للمشاركة أو التقارير أو الأغراض الأرشيفية.

## Frequently Asked Questions

**س: هل يمكنني تحويل بيانات المشروع إلى تنسيقات صورة أخرى؟**  
ج: نعم، يدعم Aspose.Tasks تحويل بيانات المشروع إلى تنسيقات صورة مختلفة مثل PNG، JPEG، BMP، إلخ.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من MS Project؟**  
ج: نعم، يدعم Aspose.Tasks إصدارات متعددة من MS Project بما في ذلك 2003، 2007، 2010، 2013، و2016.

**س: هل يمكنني تخصيص الدقة وتنسيق البكسل للصورة المُعالجة؟**  
ج: نعم، يمكنك تخصيص الدقة وتنسيق البكسل وفقًا لمتطلباتك باستخدام Aspose.Tasks.

**س: هل يتطلب Aspose.Tasks ترخيصًا للاستخدام التجاري؟**  
ج: نعم، تحتاج إلى شراء ترخيص للاستخدام التجاري لـ Aspose.Tasks. يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من [here](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم Aspose.Tasks؟**  
ج: يمكنك الحصول على دعم Aspose.Tasks من خلال [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}