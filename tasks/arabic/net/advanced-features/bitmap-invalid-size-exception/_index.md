---
title: معالجة استثناء الحجم غير الصالح للصورة النقطية في Aspose.Tasks
linktitle: معالجة استثناء الحجم غير الصالح للصورة النقطية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع BitmapInvalidSizeException في Aspose.Tasks لـ .NET عند حفظ المشاريع كصور. برنامج تعليمي شامل مع التوجيه خطوة بخطوة.
weight: 22
url: /ar/net/advanced-features/bitmap-invalid-size-exception/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# معالجة استثناء الحجم غير الصالح للصورة النقطية في Aspose.Tasks

## مقدمة

 في هذا البرنامج التعليمي، سوف نتعمق في التعامل مع`BitmapInvalidSizeException` عند العمل مع Aspose.Tasks لـ .NET. Aspose.Tasks هي مكتبة قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجياً، مما يتيح مهام مثل حفظ المشاريع كصور. ومع ذلك، في بعض الأحيان، عند محاولة حفظ مشروع كصورة، قد نواجه رسالة خطأ`Invalid Size Exception`المتعلقة بالصورة النقطية. يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية اكتشاف هذا الاستثناء والتعامل معه بشكل فعال.

## المتطلبات الأساسية

قبل متابعة هذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. الفهم الأساسي للغة البرمجة C#.
2. تم تثبيت Aspose.Tasks لـ .NET.
3. - الإلمام بالعمل مع ملفات Microsoft Project.

## استيراد مساحات الأسماء

قبل البدء، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## الخطوة 1: تهيئة المشروع وتحديد العرض

 أولاً، قم بتهيئة أ`Project` كائن وتحديد طريقة عرض، مثل`GanttChartView`.

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## الخطوة 2: تحديد خيارات حفظ الصورة

بعد ذلك، حدد خيارات حفظ الصورة، بما في ذلك التنسيق والمقياس الزمني.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## الخطوة 3: تعيين وحدة النطاق الزمني والعدد

اضبط وحدة النطاق الزمني وقم بالعد وفقًا لمتطلباتك. في هذا المثال، قمنا بتعيين المقياس الزمني إلى دقائق.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## الخطوة 4: حفظ المشروع كصورة

حاول حفظ المشروع كصورة باستخدام الخيارات المحددة.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## الخطوة 5: التقاط الاستثناء والتعامل معه

 تنفيذ معالجة الاستثناءات للقبض على`BitmapInvalidSizeException` إذا حدث ذلك أثناء عملية حفظ الصورة.

```csharp
try
{
    // حاول حفظ المشروع كصورة
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // التعامل مع الاستثناء
    Console.WriteLine(ex.Message);
}
```

## خاتمة

 وفي الختام، التعامل مع`BitmapInvalidSizeException` عند حفظ المشاريع كصور في Aspose.Tasks لـ .NET أمر بالغ الأهمية لضمان التنفيذ السلس لتطبيقاتك. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعرف على هذا الاستثناء والتعامل معه بشكل فعال، وبالتالي تعزيز قوة حلول إدارة المشروع لديك.

## الأسئلة الشائعة

### س١: ما أسباب ظهور BitmapInvalidSizeException في Aspose.Tasks؟

A1: يحدث هذا الاستثناء عند محاولة حفظ مشروع كصورة بمعلمات حجم الصورة النقطية غير الصالحة.

### س2: هل يمكنني تخصيص الجدول الزمني عند حفظ المشروع كصورة؟

ج2: نعم، يمكنك ضبط وحدة مقياس الوقت والعد وفقًا لمتطلباتك، كما هو موضح في البرنامج التعليمي.

### س3: أين يمكنني العثور على المزيد من الموارد للعمل مع Aspose.Tasks لـ .NET؟

ج3: يمكنك استكشاف الوثائق ومنتديات الدعم التي تقدمها Aspose.Tasks للحصول على إرشادات ومساعدة شاملة.

### س 4: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟

ج4: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، مما يسمح بإمكانية التشغيل التفاعلي السلس.

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟

ج5: يمكنك الحصول على ترخيص مؤقت لأغراض التقييم من خلال الرابط الموجود في المقالة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
