---
title: وسيطات حفظ CSS في Aspose.Tasks
linktitle: وسيطات حفظ CSS في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية حفظ وسيطات CSS في Aspose.Tasks لـ .NET لتخصيص مخرجات HTML. تحسين العرض التقديمي باستخدام إعدادات CSS المخصصة.
weight: 20
url: /ar/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# وسيطات حفظ CSS في Aspose.Tasks

## مقدمة

في هذا البرنامج التعليمي، سوف نتعمق في عملية حفظ وسائط CSS باستخدام Aspose.Tasks لـ .NET. تعتبر أوراق الأنماط المتتالية (CSS) ضرورية لتحديد عرض عناصر HTML. يسمح لنا Aspose.Tasks بمعالجة سمات CSS هذه وحفظها بكفاءة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  التثبيت: تأكد من تثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/tasks/net/).

2. المعرفة الأساسية: يوصى بالإلمام ببيئة التطوير C# و.NET.

## استيراد مساحات الأسماء

للبدء، قم باستيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## الخطوة 1: تحديد عمليات الاسترجاعات لحفظ CSS

أولاً، نحدد طرق رد الاتصال لحفظ CSS للتعامل مع حفظ ملفات CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // قم بتنفيذ منطق حفظ CSS الخاص بك هنا
    }
}
```

## الخطوة 2: تنفيذ عمليات الاسترجاعات لحفظ الخط والصور

بعد ذلك، قم بتنفيذ أساليب رد الاتصال الخاصة بحفظ الخط والصورة بالمثل:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // قم بتنفيذ منطق حفظ الخط الخاص بك هنا
}

public void ImageSaving(ImageSavingArgs args)
{
    // قم بتنفيذ منطق حفظ الصور الخاص بك هنا
}
```

## الخطوة 3: تكوين خيارات الحفظ

الآن، قم بتكوين خيارات حفظ HTML للاستفادة من عمليات الاسترجاعات المطبقة:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //تكوين خيارات حفظ HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## الخطوة 4: احفظ المشروع باستخدام CSS المخصص

وأخيرًا، احفظ مشروعك باستخدام إعدادات CSS المخصصة:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية حفظ وسيطات CSS باستخدام Aspose.Tasks لـ .NET. من خلال تحديد عمليات الاسترجاعات الخاصة بحفظ CSS وتكوين خيارات حفظ HTML، يمكننا التعامل بكفاءة مع سمات CSS وفقًا لمتطلباتنا.

## الأسئلة الشائعة

### س1: ما هو Aspose.Tasks لـ .NET؟

ج1: يعد Aspose.Tasks for .NET واجهة برمجة تطبيقات .NET قوية تمكن المطورين من العمل مع ملفات Microsoft Project برمجيًا.

### س2: هل يمكنني تخصيص سمات CSS عند حفظ ملفات HTML باستخدام Aspose.Tasks؟

ج2: نعم، يمكنك تحديد عمليات الاسترجاعات لحفظ CSS لتخصيص سمات CSS وفقًا لاحتياجاتك.

### س 3: هل Aspose.Tasks لـ .NET متوافق مع كافة إصدارات ملفات Microsoft Project؟

ج3: يدعم Aspose.Tasks for .NET إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س4: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks لـ .NET؟

ج4: يمكنك الرجوع إلى[توثيق](https://reference.aspose.com/tasks/net/) للحصول على معلومات وأمثلة مفصلة.

### س5: هل يقدم Aspose.Tasks لـ .NET الدعم للمطورين؟

 ج5: نعم، يمكنك الحصول على الدعم من مجتمع Aspose.Tasks من خلال[المنتدى](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
