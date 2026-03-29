---
date: 2026-03-05
description: تعلم كيفية حفظ الصور، وإنشاء HTML يحتوي على صور، وتخصيص تصدير الصور باستخدام
  Aspose.Tasks لـ .NET. دليل خطوة بخطوة لحفظ المشروع كملف HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: كيفية حفظ الصور باستخدام Aspose.Tasks لـ .NET
url: /ar/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية حفظ الصور باستخدام Aspose.Tasks لـ .NET

## المقدمة

في هذا الدرس ستكتشف **كيفية حفظ الصور** من ملفات Microsoft Project باستخدام Aspose.Tasks API لـ .NET. سواء كنت بحاجة إلى تضمين المخططات في التقارير، أو إنشاء صفحات HTML تحتوي على مرئيات المشروع، أو ببساطة تصدير الموارد التخطيطية، فإن الخطوات أدناه ستوجهك خلال العملية بالكامل — من إعداد كائن المشروع إلى تخصيص ردود استدعاء تصدير الصورة.

## إجابات سريعة
- **ماذا يعني “كيفية حفظ الصور” في Aspose.Tasks؟**  
  يشير إلى استخدام واجهة `IImageSavingCallback` للتحكم في مكان وكيفية كتابة الموارد البصرية إلى القرص.
- **هل يمكنني حفظ مشروع كملف HTML مع صور مدمجة؟**  
  نعم، باستخدام `HtmlSaveOptions` مع ردود استدعاء حفظ الصور يمكنك **حفظ المشروع كملف HTML** يتضمن جميع الصور المولدة.
- **هل أحتاج إلى ترخيص لتصدير الصور؟**  
  ترخيص تجريبي مؤقت يعمل للاختبار؛ يلزم ترخيص كامل للاستخدام في الإنتاج.
- **ما إصدارات .NET المدعومة؟**  
  يدعم Aspose.Tasks لـ .NET .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.
- **هل يمكن تخصيص تصدير الصورة (الصيغة، المجلد، التسمية)؟**  
  بالتأكيد – توفر لك ردود الاستدعاء التحكم الكامل في اسم الملف، الصيغة، والوجهة.

## ما هو “كيفية حفظ الصور” في سياق Aspose.Tasks؟

يعني حفظ الصور استخراج العناصر البصرية (المخططات، أشرطة جانت، رسومات الموارد) من ملف Project وكتابتها إلى ملفات صورة (PNG، JPEG، إلخ). توفر Aspose.Tasks آلية رد استدعاء مرنة تتيح لك تحديد الموقع الدقيق، نمط التسمية، وحتى صيغة الصورة.

## لماذا تستخدم Aspose.Tasks لحفظ الصور؟

- **تحكم برمجي كامل** – لا حاجة لتفاعل يدوي مع واجهة المستخدم.  
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS عبر .NET Core.  
- **عرض عالي الدقة** – تحتفظ الصور بنفس جودة عرض Project الأصلي.  
- **توليد HTML سهل** – دمج `HtmlSaveOptions` مع ردود استدعاء الصور لت **توليد HTML مع صور** تلقائيًا.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. تثبيت Visual Studio على جهاز التطوير الخاص بك.  
2. تحميل Aspose.Tasks لـ .NET من [here](https://releases.aspose.com/tasks/net/).  
3. إلمام أساسي بـ C# وبنية مشروع .NET.

## استيراد النطاقات (Namespaces)

أولاً، استورد النطاقات المطلوبة إلى ملف المصدر الخاص بك:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## الخطوة 1: إنشاء كائن Project

حمّل ملف Microsoft Project الذي تريد العمل معه:

```csharp
var project = new Project("Project1.mpp");
```

## الخطوة 2: تعريف خيارات الحفظ

أنشئ خيارات حفظ HTML التي ستحتوي أيضًا على ردود استدعاء حفظ الصور الخاصة بنا:

```csharp
var options = GetSaveOptions(1);
```

## الخطوة 3: حفظ المشروع كملف HTML (save project as html)

الآن صدّر المشروع إلى ملف HTML. الصور المشار إليها في HTML سيتم توليدها بواسطة رد الاستدعاء الذي سنعرفه لاحقًا:

```csharp
project.Save("document_out.html", options);
```

## الخطوة 4: تنفيذ رد استدعاء حفظ الصورة (تخصيص تصدير الصورة)

نفّذ واجهة `IImageSavingCallback`. هنا يمكنك **تخصيص سلوك تصدير الصورة**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## الخطوة 5: حفظ الصور في الدليل المحدد

داخل طريقة `ImageSaving`، قرّر أين يجب تخزين كل صورة. المثال أدناه يميز موارد PNG عن الصيغ الأخرى:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## الخطوة 6: تحديد خيارات الحفظ (بما في ذلك ردود الاستدعاء)

قم بربط ردود الاستدعاء للخطوط، CSS، والصور. هذا يضمن معالجة كل عنصر بصري بشكل متسق:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| عدم ظهور الصور في HTML المُولَّد | عدم تعيين رد الاستدعاء مسار ملف صالح | تأكد من أن `args.Path` يشير إلى مجلد قابل للكتابة واضبط `args.ImageStream` بشكل صحيح. |
| حفظ ملفات PNG بامتداد غير صحيح | منطق الشرط يتحقق فقط من لاحقة “png” | استخدم `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` لاكتشاف أكثر موثوقية. |
| مراجع HTML مكسورة بعد نقل الملفات | تغيرت المسارات النسبية بعد نقل مجلد الإخراج | احتفظ بمجلدات HTML والصور معًا أو حدّث `options.ImageFolder` وفقًا لذلك. |

## الخاتمة

باتباع هذه الخطوات الآن تعرف **كيفية حفظ الصور** من ملف Project، **حفظ المشروع كملف HTML**، و**تخصيص تصدير الصورة** لتتناسب مع بنية مجلدات تطبيقك. تتيح لك هذه الطريقة **توليد HTML مع صور** يمكن دمجها في التقارير، بوابات الوثائق، أو لوحات التحكم على الويب بسلاسة.

## الأسئلة المتكررة

**س1: هل يمكنني استخدام Aspose.Tasks لمعالجة ملفات المشروع بصيغ أخرى غير HTML؟**  
ج1: نعم، يدعم Aspose.Tasks صيغًا متعددة مثل PDF وXLSX وMPP.

**س2: هل توفر Aspose.Tasks دعمًا لتكامل التخزين السحابي؟**  
ج2: نعم، تقدم Aspose.Tasks واجهات برمجة تطبيقات للعمل مع خدمات التخزين السحابي الشهيرة مثل Amazon S3 وGoogle Drive.

**س3: هل Aspose.Tasks متوافق مع .NET Core؟**  
ج3: نعم، Aspose.Tasks متوافق مع .NET Core، مما يتيح لك تطوير تطبيقات متعددة المنصات.

**س4: هل يمكنني تخصيص مظهر الصور المحفوظة؟**  
ج4: نعم، يمكنك تخصيص مظهر الصور المحفوظة عن طريق تعديل منطق حفظ الصورة داخل طرق رد الاستدعاء.

**س5: هل تقدم Aspose.Tasks إصدارات تجريبية لأغراض التقييم؟**  
ج5: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من [here](https://releases.aspose.com/).

**آخر تحديث:** 2026-03-05  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}