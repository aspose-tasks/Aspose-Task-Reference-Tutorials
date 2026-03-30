---
date: 2026-03-16
description: تعلم كيفية تنفيذ رد نداء حفظ الصفحة في Aspose.Tasks لـ .NET، مما يتيح
  معالجة مخصصة لتدفقات إخراج المستند متعدد الصفحات.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: تنفيذ رد النداء لحفظ الصفحة في Aspose.Tasks
url: /ar/net/advanced-concepts/page-saving-callback/
weight: 12
---

**Author:** Aspose -> "المؤلف: Aspose"

Then closing shortcodes.

Then backtop button shortcode.

Make sure to keep all shortcodes unchanged.

Now produce final content with Arabic translations, preserving markdown.

Let's construct final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تنفيذ رد نداء حفظ الصفحة في Aspose.Tasks

## المقدمة

في هذا الدرس، ستتعلم كيفية **تنفيذ رد نداء حفظ الصفحة** في Aspose.Tasks لـ .NET. تتيح لك هذه الميزة القوية توجيه كل صفحة من مستند متعدد الصفحات إلى تدفق تختاره، مما يمنحك سيطرة كاملة على كيفية تخزين الناتج أو معالجته لاحقًا.

## إجابات سريعة
- **ماذا يفعل رد نداء حفظ الصفحة؟** يلتقط كل صفحة مُرسومة في تدفق منفصل بحيث يمكنك التعامل معها بشكل فردي.  
- **ما الصيغة التي يمكنني التصدير إليها؟** أي صيغة يدعمها `ImageSaveOptions`، مثل PNG، JPEG، PDF.  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في الإنتاج.  
- **هل يمكنني استخدام هذا مع .NET Core؟** نعم، يدعم Aspose.Tasks بالكامل .NET Core و .NET 5/6+.  
- **هل رد النداء آمن من حيث الخيوط؟** يعمل رد النداء على نفس الخيط الذي يقوم بالتصيير، لذا تُطبق قواعد الأمان العادية للخلية.

## ما هو **تنفيذ رد نداء حفظ الصفحة**؟
نمط **تنفيذ رد نداء حفظ الصفحة** يتيح لك إدراج منطق مخصص في خط أنابيب الحفظ في Aspose.Tasks. بدلاً من الكتابة مباشرة إلى ملف، تتلقى كائن `Stream` لكل صفحة، مما يسمح لك بتخزينه في الذاكرة، أو رفعه إلى التخزين السحابي، أو تطبيق معالجة إضافية.

## لماذا تصدير المشروع كـ PNG باستخدام رد نداء؟
تصدير المشروع كـ PNG يمنحك صورة نقطية لكل صفحة من مخطط جانت، وهو مثالي للتقارير، البريد الإلكتروني، أو تضمينه في صفحات الويب. باستخدام رد نداء يمكنك الاحتفاظ بكل صفحة في `MemoryStream` منفصل دون إنشاء ملفات مؤقتة على القرص.

## المتطلبات المسبقة

1. **معرفة C#** – إلمام أساسي بالفئات، الواجهات، والتدفقات.  
2. **Aspose.Tasks لـ .NET** – قم بتنزيله وتثبيته من [هنا](https://releases.aspose.com/tasks/net/).  
3. **بيئة التطوير المتكاملة (IDE)** – Visual Studio، Rider، أو أي محرر متوافق مع .NET.

## استيراد مساحات الأسماء

لبدء العمل، استورد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## الخطوة 1: إنشاء كائن Project

حمّل ملف MPP موجود إلى كائن `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## الخطوة 2: تكوين خيارات حفظ الصورة

قم بإعداد `ImageSaveOptions` لإخراج PNG وأرفق رد النداء المخصص:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **نصيحة احترافية:** ضبط `RenderToSinglePage = false` يضمن أن يتم تصيير كل صفحة من مخطط جانت بشكل منفصل، وهو أمر أساسي لكي يتلقى رد النداء تدفقات متميزة.

## الخطوة 3: حفظ المشروع باستخدام رد نداء

استدعِ طريقة `Save`، مع تمرير `Stream.Null` لأن التدفقات الفعلية يتم توفيرها بواسطة رد النداء:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## الخطوة 4: معالجة تدفقات الصفحات المحفوظة

بعد إكمال عملية الحفظ، يحتفظ رد النداء بمجموعة من كائنات `MemoryStream`—واحدة لكل صفحة. يمكنك الآن التكرار عليها:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## الخطوة 5: تنفيذ رد نداء حفظ الصفحة المخصص

أنشئ فئة مغلقة (sealed) تُطبق `IPageSavingCallback`. تلتقط هذه الفئة تدفق كل صفحة وتخزنه في قائمة للاستخدام لاحقًا.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## الأخطاء الشائعة & استكشاف الأخطاء وإصلاحها

| المشكلة | السبب | الحل |
|-------|--------|----------|
| **لا يتم إرجاع أي صفحات** | `RenderToSinglePage` ترك كـ `true`. | اضبط `RenderToSinglePage = false` لتوليد صفحات منفصلة. |
| **التدفقات فارغة** | `KeepStreamOpen` تم ضبطه على `true` دون إغلاقه لاحقًا. | اتركه `false` (الإعداد الافتراضي) ودع رد النداء يغلق التدفقات تلقائيًا. |
| **أخطاء نفاد الذاكرة** | المشروعات الكبيرة جدًا تُنتج العديد من صور PNG عالية الدقة. | عالج التدفقات واحدةً تلو الأخرى أو زد حدود ذاكرة الجهاز الافتراضي. |

## الأسئلة المتكررة

**س1: ما هو رد نداء حفظ الصفحة في Aspose.Tasks؟**  
ج: يتيح لك رد نداء حفظ الصفحة اعتراض عملية الحفظ لكل صفحة من مستند متعدد الصفحات، مع توفير `Stream` مخصص لتلك الصفحة.

**س2: هل يمكنني استخدام صيغ مختلفة لحفظ الصفحات باستخدام هذا الرد؟**  
ج: نعم. بتغيير `SaveFileFormat` يمكنك التصدير إلى PNG، JPEG، PDF، SVG، إلخ.

**س3: هل Aspose.Tasks متوافق مع .NET Core؟**  
ج: بالتأكيد. يدعم Aspose.Tasks .NET Core، .NET 5، و .NET 6.

**س4: كيف يمكنني التعامل مع الأخطاء أثناء عملية حفظ الصفحة؟**  
ج: غلف منطق رد النداء بكتل try/catch وسجّل الاستثناءات. طريقة `OnFinish` مكان جيد للتنظيف النهائي.

**س5: أين يمكنني العثور على مزيد من الموارد والدعم لـ Aspose.Tasks؟**  
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة، الوصول إلى الوثائق [هنا](https://reference.aspose.com/tasks/net/)، أو استكشاف ميزات إضافية وخيارات الترخيص على [موقع Aspose.Tasks](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-03-16  
**تم الاختبار مع:** Aspose.Tasks 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}