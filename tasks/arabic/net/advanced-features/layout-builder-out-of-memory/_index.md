---
date: 2026-03-24
description: تعلم معالجة الذاكرة خارجها وكيفية حفظ صورة المشروع باستخدام Aspose.Tasks
  Layout Builder في .NET. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: معالجة نفاد الذاكرة باستخدام Aspose.Tasks Layout Builder (C#)
url: /ar/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# معالجة نفاد الذاكرة باستخدام Aspose.Tasks Layout Builder

## المقدمة

معالجة نفاد الذاكرة جزء حاسم في بناء تطبيقات .NET موثوقة تتعامل مع ملفات مشاريع كبيرة. عند إنشاء تصورات باستخدام Aspose.Tasks Layout Builder، قد تواجه استثناءات متعلقة بالذاكرة بسرعة، خاصةً في مخططات جانت المعقدة. في هذا الدرس سنرشدك إلى كيفية **معالجة استثناءات الذاكرة**، **تخصيص عرض جانت**، و**حفظ صورة المشروع** بأمان، بحيث يبقى تطبيقك مستجيبًا حتى مع جداول زمنية ضخمة.

## إجابات سريعة
- **ما هي معالجة نفاد الذاكرة؟** إدارة استخدام الذاكرة والتقاط الأخطاء من نوع `OutOfMemoryException` عند معالجة بيانات كبيرة.
- **أي API يساعد؟** Aspose.Tasks Layout Builder لـ .NET.
- **سيناريو شائع؟** تصيير مخطط جانت عالي الدقة إلى PNG.
- **المتطلب الأساسي؟** .NET (Framework 4.5+ أو .NET 6) مع تثبيت Aspose.Tasks.
- **كيف يتم التقاط الأخطاء؟** استخدم كتل `try…catch` لالتقاط `ApsLayoutBuilderOutOfMemoryException` والاستثناءات ذات الصلة.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

1. **أساسيات C#** – يجب أن تكون مرتاحًا مع بنية C# القياسية.
2. **Aspose.Tasks لـ .NET** مثبت. إذا لم تقم بإضافته بعد، قم بتحميله من [here](https://releases.aspose.com/tasks/net/).
3. **بيئة تطوير** مثل Visual Studio (أو VS Code مع امتداد C#) لتجميع وتشغيل العينة.

## استيراد المساحات الاسمية

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## دليل خطوة بخطوة

### الخطوة 1: تحميل المشروع

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

هذا السطر يحمل **Blank2010.mpp** في كائن `Project`، مهيئًا إياه للتصور.

### الخطوة 2: تخصيص عرض مخطط جانت

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

هنا نقوم **بتخصيص عرض جانت** عن طريق تعديل مستويات مقياس الوقت الوسطى والسفلية. تعديل هذه المستويات يقلل كمية البيانات التي تُصوَّر دفعة واحدة، مما يساعد على تخفيف ضغط الذاكرة.

### الخطوة 3: تكوين خيارات حفظ الصورة

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` يخبر Aspose.Tasks كيف يصوِّر المخطط. نختار PNG كصيغة إخراج ونربط مقياس الوقت بالعرض الذي خصصناه للتو.

### الخطوة 4: حفظ المشروع كصورة

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

استدعاء `Save` **يحفظ صورة المشروع** باستخدام الخيارات المحددة أعلاه. إذا كان المشروع كبيرًا جدًا، فإن هذه هي النقطة التي من المرجح أن يظهر فيها شرط نفاد الذاكرة.

### الخطوة 5: معالجة الاستثناءات

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

من خلال التقاط `ApsLayoutBuilderOutOfMemoryException` يمكنك **معالجة استثناء الذاكرة** بسلاسة، مع تقديم رسالة واضحة بدلاً من تعطل التطبيق. الكتلة الثانية تتعامل مع مشكلات حجم البت ماب التي قد تظهر أيضًا عند تصيير مخططات ضخمة.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **OutOfMemoryException** | تصيير صورة عالية الدقة يستهلك ذاكرة RAM أكثر مما يمكن للعملية تخصيصه. | قلل أبعاد الصورة، بسط مستويات مقياس الوقت، أو قسّم المخطط إلى عدة صور. |
| **BitmapInvalidSizeException** | حجم البت ماب المطلوب يتجاوز الحد الأقصى للمنصة. | حدّ العرض/الارتفاع في `ImageSaveOptions` أو صوِّر على أجزاء. |
| **بطء الأداء** | ملفات المشاريع الكبيرة تتطلب معالجة مكثفة. | فعّل `project.Set(Prj.SaveToCache, true)` قبل التصيير، أو استخدم خيط خلفي. |

## الأسئلة المتكررة

### س1: ما هو Aspose.Tasks لـ .NET؟

ج1: Aspose.Tasks لـ .NET هو API قوي يتيح للمطورين تعديل ملفات Microsoft Project برمجيًا في تطبيقات .NET.

### س2: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟

ج2: يمكنك الحصول على ترخيص مؤقت لـ Aspose.Tasks بزيارة [this link](https://purchase.aspose.com/temporary-license/).

### س3: هل Aspose.Tasks مناسب لمعالجة ملفات مشاريع كبيرة؟

ج3: نعم، يوفر Aspose.Tasks ميزات وتحسينات لمعالجة ملفات مشاريع كبيرة بكفاءة، لكن لا يزال من الضروري مراعاة استراتيجيات إدارة الذاكرة.

### س4: هل يمكنني تخصيص مظهر مخططات جانت باستخدام Aspose.Tasks؟

ج4: بالتأكيد! يوفر Aspose.Tasks إمكانيات واسعة لتخصيص مظهر وتخطيط مخططات جانت وفقًا لمتطلباتك.

### س5: أين يمكنني العثور على مزيد من المساعدة والدعم لـ Aspose.Tasks؟

ج5: يمكنك العثور على مزيد من المساعدة والدعم، بالإضافة إلى التفاعل مع المجتمع، على [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## أسئلة شائعة أخرى

**س: كيف يمكنني تقليل استهلاك الذاكرة عند حفظ صورة المشروع؟**  
ج: خفّض دقة الصورة، حدّ نطاق مقياس الوقت، أو احفظ المخطط في عدة أجزاء أصغر.

**س: هل يمكن بث الصورة مباشرةً إلى استجابة ويب؟**  
ج: نعم، يمكنك استخدام `project.Save(stream, options)` وكتابة الـ stream إلى استجابة HTTP.

**س: هل يدعم Aspose.Tasks .NET Core و .NET 5/6؟**  
ج: المكتبة متوافقة بالكامل مع .NET Core، .NET 5، و .NET 6.

**س: ماذا أفعل إذا استمر ظهور خطأ نفاد الذاكرة بعد التحسين؟**  
ج: فكر في معالجة المشروع على جهاز بذاكرة RAM أكبر أو نقل عملية التصيير إلى خدمة خلفية.

**س: هل يمكنني تصدير مخطط جانت إلى صيغ غير PNG؟**  
ج: نعم، يدعم `ImageSaveOptions` صيغ JPEG، BMP، و TIFF بالإضافة إلى PNG.

---

**آخر تحديث:** 2026-03-24  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}