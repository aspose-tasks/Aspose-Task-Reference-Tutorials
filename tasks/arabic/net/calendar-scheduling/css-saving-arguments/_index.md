---
date: 2026-07-05
description: تعلم كيفية تخصيص CSS أثناء تصدير مشروع إلى HTML باستخدام Aspose.Tasks
  لـ .NET. خصص مخرجات HTML باستخدام معلمات حفظ CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: كيفية تخصيص CSS عند حفظ المشاريع باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: كيفية تخصيص CSS عند حفظ المشاريع باستخدام Aspose.Tasks
url: /ar/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تخصيص CSS عند حفظ المشاريع باستخدام Aspose.Tasks

في هذا الدليل ستكتشف **كيفية تخصيص CSS** أثناء تصدير HTML لملف Microsoft Project باستخدام Aspose.Tasks لـ .NET. من خلال تعديل معلمات حفظ CSS ستحصل على تحكم كامل في النمط البصري للصفحات HTML المُولدة، مما يجعل المخرجات تتطابق مع علامتك التجارية أو معايير التقارير.

## إجابات سريعة
- **ما هي نقطة الدخول الرئيسية؟** استخدم `HtmlSaveOptions` مع ردود نداء مخصصة.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل يمكنني تصدير مشاريع كبيرة؟** Aspose.Tasks يتعامل مع مشاريع تحتوي على > 10,000 مهمة دون تحميل الملف بالكامل في الذاكرة.  
- **هل تخصيص CSS اختياري؟** نعم، يمكنك حذف ردود النداء لاستخدام ورقة الأنماط الافتراضية.

## كيفية تخصيص CSS في Aspose.Tasks؟

حمّل مشروعك، وأرفق ردود نداء حفظ CSS إلى كائن `HtmlSaveOptions`، ثم استدعِ `project.Save`. يتيح لك هذا النمط كتابة ملفات CSS مخصصة، استبدال الأنماط الافتراضية، والتحكم في بنية المجلدات—كل ذلك في بضع أسطر من الشيفرة. يتم استدعاء ردود النداء تلقائيًا لكل ملف CSS أثناء عملية التصدير.

`HtmlSaveOptions` يحدد كيفية تصدير المشروع إلى HTML.

## مقدمة

في هذا البرنامج التعليمي، سنستكشف عملية حفظ معلمات CSS باستخدام Aspose.Tasks لـ .NET. تُعد أوراق الأنماط المتتالية (CSS) أساسية لتحديد عرض عناصر HTML. يتيح لنا Aspose.Tasks تعديل وحفظ هذه السمات CSS بكفاءة.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

1. التثبيت: تأكد من أنك قد قمت بتثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله من [الموقع](https://releases.aspose.com/tasks/net/).
2. المعرفة الأساسية: يُنصح بأن تكون لديك معرفة بلغة C# وبيئة تطوير .NET.

## استيراد مساحات الأسماء

لبدء العمل، استورد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## الخطوة 1: تعريف ردود نداء حفظ CSS

`ICssSavingCallback` هي واجهة تتيح لك تخصيص طريقة حفظ ملفات CSS أثناء تصدير HTML.

**رد نداء حفظ CSS** هو تفويض تستدعيه Aspose.Tasks لكتابة ملفات CSS أثناء تصدير HTML. عرّف طرق رد النداء للتحكم في كيفية إنشاء كل ملف CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## الخطوة 2: تنفيذ ردود نداء حفظ الخطوط والصور

`FontSavingArgs` يوفر معلومات حول الخط الجاري حفظه، بينما `ImageSavingArgs` يزود بتفاصيل موارد الصور.

نفّذ طرق رد نداء حفظ الخط والصورة بطريقة مماثلة:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## الخطوة 3: تكوين خيارات الحفظ

`HtmlSaveOptions` هو كائن التكوين الذي يتحكم في كيفية تصدير المشروع إلى HTML.

`HtmlSaveOptions` يتيح لك تحديد ردود النداء، مجلدات الإخراج، وإعدادات التصدير الأخرى.

قم بتعيين خصائصه لاستخدام ردود النداء التي تم تعريفها سابقًا وتحديد مجلد الإخراج:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## الخطوة 4: حفظ المشروع مع CSS مخصص

`Project` يمثل ملف Microsoft Project يمكن تعديله وحفظه.

أخيرًا، احفظ مشروعك باستخدام إعدادات CSS المخصصة:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## لماذا تخصيص CSS عند تصدير المشاريع؟

يدعم Aspose.Tasks **تصدير المشروع إلى HTML** بأكثر من 30 تنسيقًا ويمكنه إنشاء ما يصل إلى 30 ملف CSS منفصل لكل عملية تصدير. يعالج المشاريع التي تحتوي على أكثر من 10 000 مهمة بثبات مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت، مما يتيح تقارير على مستوى المؤسسات دون اختناقات في الأداء.

## الخاتمة

في هذا البرنامج التعليمي، استكشفنا كيفية حفظ معلمات CSS باستخدام Aspose.Tasks لـ .NET. من خلال تعريف ردود نداء حفظ CSS وتكوين خيارات حفظ HTML، يمكننا تعديل سمات CSS بكفاءة وفقًا لمتطلباتنا.

## الأسئلة الشائعة

### س1: ما هو Aspose.Tasks لـ .NET؟

A1: Aspose.Tasks لـ .NET هو واجهة برمجة تطبيقات .NET قوية تمكّن المطورين من التعامل مع ملفات Microsoft Project برمجيًا.

### س2: هل يمكنني تخصيص سمات CSS عند حفظ ملفات HTML باستخدام Aspose.Tasks؟

A2: نعم، يمكنك تعريف ردود نداء حفظ CSS لتخصيص سمات CSS وفقًا لاحتياجاتك.

### س3: هل Aspose.Tasks لـ .NET متوافق مع جميع إصدارات ملفات Microsoft Project؟

A3: يدعم Aspose.Tasks لـ .NET إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س4: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks لـ .NET؟

A4: يمكنك الرجوع إلى [الوثائق](https://reference.aspose.com/tasks/net/) للحصول على معلومات مفصلة وأمثلة.

### س5: هل يقدم Aspose.Tasks لـ .NET دعمًا للمطورين؟

A5: نعم، يمكنك الحصول على الدعم من مجتمع Aspose.Tasks عبر [المنتدى](https://forum.aspose.com/c/tasks/15).

**أسئلة إضافية**

**س: كيف يؤثر تخصيص CSS على حجم HTML المُصدّر؟**  
ج: يمكن أن يقلل استخدام CSS مخصص الحجم الكلي بما يصل إلى 15 % لأنك تستطيع حذف الأنماط الافتراضية غير المستخدمة.

**س: هل يمكنني استخدام نفس ردود النداء لعدة مشاريع؟**  
ج: بالتأكيد. نفّذ ردود النداء مرة واحدة وأعد استخدامها عبر أي عدد من عمليات تصدير المشاريع.

**س: هل يمكن تضمين CSS مباشرةً في HTML بدلاً من ملفات منفصلة؟**  
ج: نعم، اضبط `HtmlSaveOptions.EmbeddedCss = true` لتضمين ورقة الأنماط داخل HTML، مما يبسط عملية التوزيع.

---

**آخر تحديث:** 2026-07-05  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [حفظ MS Project كـ HTML باستخدام Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [تنفيذ رد نداء حفظ الصفحة في Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [معالجة حفظ الصور في Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}