---
date: 2026-03-21
description: تعلم كيفية تصدير الصورة ومعالجة استثناء BitmapInvalidSizeException عند
  حفظ المشروع كصورة في Aspose.Tasks لـ .NET. يتضمن خطوات حفظ المشروع كصورة وتصدير
  المشروع إلى PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية تصدير الصورة ومعالجة استثناء الحجم غير الصالح
url: /ar/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصدير صورة – معالجة استثناء حجم البت ماب غير صالح في Aspose.Tasks

في هذا البرنامج التعليمي ستتعلم **كيفية تصدير صورة** من ملف Microsoft Project باستخدام Aspose.Tasks لـ .NET، والأهم من ذلك، كيفية التقاط استثناء `BitmapInvalidSizeException` الذي قد يحدث أثناء العملية. تصدير المشروع كصورة هو طلب شائع لتقارير اللوحات، الوثائق، أو ببساطة مشاركة لقطة بصرية لجدول زمني. بنهاية هذا الدليل ستتمكن من **حفظ المشروع كصورة** بشكل موثوق وحتى **تصدير المشروع إلى صيغة PNG** دون حدوث تعطل غير متوقع.

## إجابات سريعة
- **ما هو الاستثناء الذي يمكن أن يحدث عند تصدير صورة؟** `BitmapInvalidSizeException`  
- **ما الصيغة المستخدمة في المثال؟** PNG (`SaveFileFormat.Png`)  
- **هل أحتاج إلى ترخيص خاص؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في بيئة الإنتاج.  
- **هل يمكنني تغيير مقياس الوقت؟** نعم – يمكنك تعيين وحدة مقياس الوقت (دقائق، ساعات، أيام، إلخ).  
- **هل الكود متوافق مع .NET Core؟** بالتأكيد – نفس الـ API يعمل على .NET Framework و .NET Core.

## ما هو استثناء BitmapInvalidSizeException؟
يتم إلقاء `BitmapInvalidSizeException` عندما تكون أبعاد البت ماب المحسوبة للصورة خارج النطاق المدعوم (مثلاً، العرض أو الارتفاع صفر أو يتجاوز الحدود الداخلية). يحدث هذا عادةً عندما ينتج مقياس الوقت أو إعدادات العرض صورة كبيرة جدًا أو صغيرة جدًا.

## لماذا تصدير المشروع كصورة؟
- **تقارير بصرية** – تضمين مخطط جانت في ملفات PDF أو Word أو صفحات الويب.  
- **مشاركة عبر المنصات** – يمكن عرض ملفات PNG على أي جهاز دون الحاجة إلى Microsoft Project.  
- **الأداء** – الصور خفيفة الوزن مقارنة بملفات المشروع الكاملة للمعاينات السريعة.

## المتطلبات المسبقة
1. معرفة أساسية بـ C# وتطوير .NET.  
2. تثبيت Aspose.Tasks لـ .NET (حزمة NuGet `Aspose.Tasks`).  
3. ملف Microsoft Project تجريبي (مثال: `Blank2010.mpp`).  

## استيراد المساحات الاسمية
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## دليل خطوة بخطوة

### الخطوة 1: تهيئة المشروع واختيار العرض
أولاً، أنشئ كائن `Project` واختر العرض الذي تريد تصييره (هنا نستخدم أول عرض مخطط جانت).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### الخطوة 2: تكوين خيارات حفظ الصورة (تصدير المشروع إلى PNG)
حدد صيغة الصورة المطلوبة وأخبر Aspose.Tasks باستخدام مقياس الوقت المحدد في العرض.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### الخطوة 3: تعديل وحدة مقياس الوقت (التحكم في حجم الصورة)
تغيير مقياس الوقت يؤثر على أبعاد البت ماب. في هذا المثال نستخدم **الدقائق** للحفاظ على حجم الصورة معقولًا.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### الخطوة 4: محاولة حفظ المشروع كصورة
هذا السطر ينفذ عملية **حفظ المشروع كصورة** الفعلية.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### الخطوة 5: التقاط ومعالجة استثناء BitmapInvalidSizeException
غلف استدعاء الحفظ داخل كتلة `try / catch` حتى يتمكن تطبيقك من التعامل بأناقة إذا كان حجم البت ماب غير صالح.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|----------|
| لا يزال الاستثناء يُلقى بعد تعديل مقياس الوقت | مقياس الوقت لا يزال ينتج بت ماب كبير جدًا | قلل `view.MiddleTimescaleTier.Count` أو انتقل إلى `TimescaleUnit` أكثر خشونة (مثلاً، ساعات). |
| ملف الإخراج فارغ | مسار ملف غير صحيح أو نقص في أذونات الكتابة | تحقق من أن `DataDir` يشير إلى مجلد قابل للكتابة وأن اسم الملف ينتهي بـ `.png` إذا غيرت الصيغة. |
| جودة الصورة ضعيفة | قد يكون DPI الافتراضي منخفضًا | عيّن `options.DpiX` و `options.DpiY` إلى قيم أعلى (مثلاً، 300). |

## الأسئلة المتكررة

**س: ما الذي يسبب استثناء BitmapInvalidSizeException في Aspose.Tasks؟**  
ج: يحدث عندما تكون أبعاد البت ماب المحسوبة غير صالحة — عادةً لأن مقياس الوقت ينتج صورة كبيرة جدًا أو ذات عرض/ارتفاع صفر.

**س: هل يمكنني تخصيص مقياس الوقت عند تصدير صورة؟**  
ج: نعم. يمكنك تعديل `view.MiddleTimescaleTier.Unit` و `Count` لتناسب احتياجاتك، كما هو موضح في البرنامج التعليمي.

**س: هل يدعم Aspose.Tasks صيغ صور أخرى غير PNG؟**  
ج: بالتأكيد. `SaveFileFormat` يتضمن أيضًا JPEG، BMP، GIF، و TIFF. فقط غيّر قيمة الـ enum في `ImageSaveOptions`.

**س: هل يلزم ترخيص لتصدير الصور في بيئة الإنتاج؟**  
ج: نعم. بينما تعمل المكتبة في وضع التقييم، فإن الترخيص التجاري يزيل قيود التقييم ويوفر الدعم الكامل.

**س: كيف يمكنني تحسين جودة PNG المُصدَّر؟**  
ج: زد إعدادات DPI (`options.DpiX` و `options.DpiY`) أو عدل مقياس الوقت في العرض لإنتاج بت ماب أكبر.

## الخلاصة
باتباع الخطوات أعلاه، أصبحت الآن تعرف **كيفية تصدير صورة** من ملف مشروع، وكيفية **حفظ المشروع كصورة**، وكيفية التعامل بأناقة مع استثناء `BitmapInvalidSizeException`. هذه التقنيات تجعل خطوط تقاريرك أكثر صلابة وتضمن أن تصدير الصور البصرية يعمل بشكل موثوق عبر أحجام ومقاييس وقت مختلفة للمشروع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Tasks 24.12 لـ .NET  
**المؤلف:** Aspose  

---