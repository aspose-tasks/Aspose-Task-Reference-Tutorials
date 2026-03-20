---
date: 2025-12-17
description: تعلم كيفية حفظ المشروع كصورة وتغيير دقة الصورة في جافا باستخدام Aspose.Tasks
  for Java. يوضح هذا الدليل خطوة بخطوة عملية عرض بيانات MS Project بتنسيق 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: حفظ المشروع كصورة – تنسيق 24bppRgb باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ المشروع كصورة – تنسيق 24bppRgb باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم كيفية **حفظ المشروع كصورة** باستخدام تنسيق البكسل 24bppRgb مع Aspose.Tasks للغة Java. تحويل بيانات MS Project إلى صورة مفيد عندما تحتاج إلى مشاركة لقطة بصرية لجدول زمني، أو تضمين خط زمني في تقرير، أو إنشاء صور مصغرة لبورتال المشروع. سنوضح لك أيضًا كيفية **تغيير دقة الصورة java** لتلبية متطلبات الجودة الخاصة بك.

## إجابات سريعة
- **هل يمكنني تحويل مشروع إلى صورة؟** نعم، يتيح لك Aspose.Tasks حفظ المشروع كملف TIFF أو PNG أو JPEG وغيرها.  
- **أي تنسيق بكسل يوفر أفضل عمق للون؟** `Format24bppRgb` يوفر صورًا ذات ألوان حقيقية (24‑بت).  
- **كيف أضبط دقة الصورة؟** استخدم `setHorizontalResolution` و `setVerticalResolution` على `ImageSaveOptions`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب الترخيص التجاري للاستخدام غير التجريبي.  
- **هل هذا متوافق مع جميع إصدارات Java؟** يعمل مع Java 8 وما بعدها.

## ما هو “حفظ المشروع كصورة”؟
حفظول التمثيل البصري لملف Microsoft Project (`.mpp`) إلى تنسيق نقطي (مثل TIFF). يمكن عرض الملف الناتج في المتصفحات، إدراجه في المستندات، أو طباعته دون الحاجة إلى تطبيق Project الأصلي.

## لماذا نستخدم تنسيق 24bppRgb؟
تنسيق البكسل 24bppRgb يخزن كل بكسل بـ 8 بت للون الأحمر، الأخضر، والأزرق، مما يقدم جودة ألوان حقيقية دون قناة ألفا. هذا مثالي للتقارير ذات الوضوح العالي حيث تكون دقة الألوان مهمة، مع الحفاظ على حجم الملف معقولًا مقارنةً بالتنسيقات 32‑بت.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير جافا (JDK)** – JDK 8 أو أحدث مثبت على جهازك.  
2. **Aspose.Tasks للغة Java** – قم بتنزيله وتثبيته من [هنا](https://releases.aspose.com/tasks/java/).  
3. **معرفة أساسية بجافا** – الإلمام بصياغة جافا وإعداد المشروع سيساعدك على متابعة مقتطفات الشيفرة.

## استيراد الحزم
أولاً، استورد الفئات المطلوبة من Aspose.Tasks إلى مشروع جافا الخاص بك:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## دليل خطوة بخطوة

### الخطوة 1: تعريف مسار البيانات
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يوجد ملف `.mpp` الخاص بك.

### الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
تقوم هذه السطر بقراءة ملف Microsoft Project (`project.mpp`) وإنشاء كائن `Project` يمكن لـ Aspose.Tasks التعامل معه.

### الخطوة 3: تكوين خيارات حفظ الصورة
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
هنا نحدد تنسيق الإخراج إلى TIFF، ونحدد دقة **72 dpi** (يمكنك تغيير هذه القيم لتناسب احتياجاتك – هذا هو المكان الذي **تغير فيه دقة الصورة java**)، ونختار تنسيق البكسل 24bppRgb لإنتاج ألوان حقيقية.

### الخطوة 4: حفظ بيانات المشروع كصورة
```java
project.save(dataDir + "resFile.tif", options);
```
طريقة `save` تكتب الصورة المرسومة إلى `resFile.tif` باستخدام الخيارات المحددة أعلاه.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **صورة فارغة** | قد يكون عرض المشروع فارغًا. | استدعِ `project.setDefaultView(ViewType.Gantt);` قبل الحفظ. |
| **صورة منخفضة الجودة** | تم ضبط الدقة منخفضة جدًا. | زيادة `setHorizontalResolution` و `setVerticalResolution` (مثلاً 150 dpi). |
| **تنسيق بكسل غير مدعوم** | استخدام نسخة أقدم من Aspose.Tasks. | الترقية إلى أحدث إصدار من Aspose.Tasks للغة Java. |

## الخاتمة
الآن تعرف كيف **تحفظ المشروع كصورة** باستخدام تنسيق 24bppRgb وتضبط الدقة باستخدام Aspose.Tasks للغة Java. يتيح لك هذا النهج إنشاء تمثيلات بصرية واضحة ودقيقة الألوان لجدول مشروعك للمشاركة، التقارير، أو الأرشفة.

## الأسئلة المتكررة
### س: هل يمكنني تحويل بيانات المشروع إلى تنسيقات صورة أخرى؟
ج: نعم، يدعم Aspose.Tasks تحويل بيانات المشروع إلى تنسيقات صورة مختلفة مثل PNG، JPEG، BMP، وغيرها.  
### س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من MS Project؟
ج: نعم، يدعم Aspose.Tasks عدة إصدارات من MS Project بما فيها 2003، 2007، 2010، 2013، و2016.  
### س: هل يمكنني تخصيص دقة الصورة وتنسيق البكسل؟
ج: نعم، يمكنك تخصيص الدقة وتنسيق البكسل وفقًا لمتطلباتك باستخدام Aspose.Tasks.  
### س: هل يتطلب Aspose.Tasks ترخيصًا للاستخدام التجاري؟
ج: نعم، تحتاج إلى شراء ترخيص للاستخدام التجاري من Aspose.Tasks. يمكنك الحصول على ترخيص مؤقت للاختبار من [هنا](https://purchase.aspose.com/temporary-license/).  
### س: أين يمكنني الحصول على دعم لـ Aspose.Tasks؟
ج: يمكنك الحصول على الدعم من خلال [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2025-12-17  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}