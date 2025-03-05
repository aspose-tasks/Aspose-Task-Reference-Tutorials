---
title: التعامل مع حفظ الصور في Aspose.Tasks
linktitle: التعامل مع حفظ الصور في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع حفظ الصور في Aspose.Tasks لـ .NET باستخدام إرشادات خطوة بخطوة. يمكنك دمج وظيفة حفظ الصور بسهولة في تطبيقات .NET الخاصة بك.
type: docs
weight: 10
url: /ar/net/advanced-concepts/image-saving/
---
## مقدمة

في هذا البرنامج التعليمي، سوف نتعمق في عملية التعامل مع حفظ الصور في Aspose.Tasks لـ .NET. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات قوية تمكن المطورين من معالجة ملفات Microsoft Project برمجيًا. إحدى المهام الشائعة عند العمل مع ملفات المشروع هي الحاجة إلى حفظ الصور، والتي يمكن أن تتضمن مخططات أو رسوم بيانية أو عناصر مرئية أخرى. سنقوم بتقسيم العملية خطوة بخطوة، مما يضمن الوضوح والفهم طوال الوقت.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية إلى مشروعنا:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## الخطوة 1: إنشاء كائن المشروع

ابدأ بإنشاء كائن Project من ملف Microsoft Project الخاص بك:

```csharp
var project = new Project("Project1.mpp");
```

## الخطوة 2: تحديد خيارات الحفظ

حدد خيارات الحفظ لمشروعك، مع تحديد الصفحات والإعدادات الأخرى:

```csharp
var options = GetSaveOptions(1);
```

## الخطوة 3: احفظ المشروع بتنسيق HTML

احفظ المشروع بتنسيق HTML بالخيارات المحددة:

```csharp
project.Save("document_out.html", options);
```

## الخطوة 4: تنفيذ رد الاتصال لحفظ الصور

قم بتطبيق واجهة ImageSavingCallback للتعامل مع حفظ الصور:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // منطق حفظ الصورة يذهب هنا
    }
}
```

## الخطوة 5: حفظ الصور في الدليل المحدد

ضمن طريقة ImageSaving، حدد المنطق لحفظ الصور في الدليل المطلوب:

```csharp
if (args.FileName.EndsWith("png"))
{
    // حفظ الموارد المتداخلة
}
else
{
    // حفظ الموارد العادية
}
```

## الخطوة 6: تحديد خيارات الحفظ

حدد خيارات الحفظ، بما في ذلك عمليات الاسترجاعات لـ CSS والخطوط والصور:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // حدد خيارات الحفظ هنا
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## خاتمة

في الختام، تتضمن معالجة حفظ الصور في Aspose.Tasks لـ .NET تحديد خيارات الحفظ وتنفيذ عمليات الاسترجاعات لإدارة عملية الحفظ بفعالية. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج وظيفة حفظ الصور بسلاسة في تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س 1: هل يمكنني استخدام Aspose.Tasks لمعالجة ملفات المشروع بتنسيقات أخرى إلى جانب HTML؟

ج1: نعم، يدعم Aspose.Tasks التنسيقات المختلفة مثل PDF وXLSX وMPP.

### س2: هل يوفر Aspose.Tasks الدعم لتكامل التخزين السحابي؟

ج2: نعم، يقدم Aspose.Tasks واجهات برمجة التطبيقات للعمل مع خدمات التخزين السحابية الشائعة مثل Amazon S3 وGoogle Drive.

### س3: هل Aspose.Tasks متوافق مع .NET Core؟

ج3: نعم، Aspose.Tasks متوافق مع .NET Core، مما يسمح لك بتطوير التطبيقات عبر الأنظمة الأساسية.

### س4: هل يمكنني تخصيص مظهر الصور المحفوظة؟

ج4: نعم، يمكنك تخصيص مظهر الصور المحفوظة عن طريق تعديل منطق حفظ الصورة ضمن أساليب رد الاتصال.

### س5: هل يقدم Aspose.Tasks إصدارات تجريبية لأغراض التقييم؟

 ج5: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).