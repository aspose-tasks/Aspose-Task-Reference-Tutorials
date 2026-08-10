---
date: 2026-04-06
description: تعلم كيفية تغيير نمط الأشرطة وتخصيص ألوانها في Aspose.Tasks لـ .NET لتعزيز
  تصور المشروع.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: شريط التنسيق في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية تغيير تنسيق الشريط في Aspose.Tasks
url: /ar/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تغيير تنسيق الشريط في Aspose.Tasks

## مقدمة

إذا كنت بحاجة إلى **كيفية تغيير مظهر الشريط** في ملف Microsoft Project، فإن Aspose.Tasks لـ .NET يمنحك تحكمًا كاملاً في ألوان الشريط، وأشكاله، وأنماط النص. من خلال تخصيص ألوان الشريط وغيرها من السمات البصرية، يمكنك جعل خطط المشروع أسهل كثيرًا للقراءة وأكثر توافقًا مع هوية مؤسستك. في هذا البرنامج التعليمي سنستعرض مثالًا كاملاً خطوة بخطوة يوضح لك كيفية تغيير تنسيق الشريط، بدءًا من تحميل المشروع وحتى تصديره مع تطبيق القواعد البصرية الجديدة.

## إجابات سريعة
- **ما الذي يمكنني تنسيقه؟** الأشرطة، والمعالم، ونص المهمة في مخططات جانت.  
- **ما الصيغة التي تدعم الأشرطة المنسقة؟** PDF، XLSX، HTML وMPP الأصلي عند حفظه باستخدام `PdfSaveOptions`.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج؛ النسخة التجريبية المجانية تكفي للاختبار.  
- **هل يمكنني تطبيق أنماط متعددة؟** نعم – أضف عددًا من كائنات `BarStyle` حسب الحاجة.  
- **هل هو متوافق مع .NET Core؟** بالتأكيد – يعمل مع .NET Framework و .NET Core/5/6+.

## ما هو تنسيق الشريط في Aspose.Tasks؟

يتيح لك تنسيق الشريط تعريف قواعد بصرية يقوم محرك Aspose.Tasks بتطبيقها عند رسم مخططات جانت. كل قاعدة (**BarStyle**) تستهدف نوع عنصر محدد — مهام، معالم، أو مهام ملخص — وتسمح لك بتعيين الألوان، الأشكال، وحتى نص مخصص.

## لماذا تخصيص ألوان الشريط؟

يساعد تخصيص ألوان الشريط أصحاب المصلحة على التعرف فورًا على المسارات الحرجة، والمهام المتأخرة، أو المعالم. كما يتيح لك مطابقة ألوان الشركة، مما يجعل التقارير تبدو احترافية ومتوافقة مع العلامة التجارية.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Aspose.Tasks for .NET** – قم بتنزيله من [صفحة التحميل](https://releases.aspose.com/tasks/net/).  
2. بيئة تطوير تدعم .NET (Framework 4.6+، .NET Core 3.1+ أو أحدث).  
3. إلمام أساسي بـ C# – الأمثلة تستخدم شفرة بسيطة ومستقلة.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي تحتوي على الفئات التي سنستخدمها:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## الخطوة 1: تحميل المشروع

Load an existing MPP file (or create a new one) so you have a project object to work with:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## الخطوة 2: تكوين خيارات الحفظ

Create a `PdfSaveOptions` instance and initialise the `BarStyles` collection where we’ll store our custom styles:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## الخطوة 3: تعريف نمط الشريط

Now we build a `BarStyle` object and set the properties that control how the bar looks. This is where we **customize bar colors** and shapes:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## الخطوة 4: تخصيص محول النص (اختياري)

If you want to tweak the text that appears on the bar, you can assign a custom converter. The example prefixes task names that don’t already start with “T”:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## الخطوة 5: إضافة نمط الشريط إلى الخيارات

Add the fully configured style to the `BarStyles` collection of the save options:

```csharp
options.BarStyles.Add(style);
```

## الخطوة 6: حفظ المشروع

Finally, export the project. The PDF (or other format) will render the Gantt chart using the bar style we defined:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **لم يتم تطبيق نمط الشريط** | مجموعة `BarStyles` كانت فارغة أو لم تُربط بخيارات الحفظ. | تأكد من إضافة `BarStyle` إلى `options.BarStyles` قبل استدعاء `Save`. |
| **الألوان تبدو مختلفة في PDF** | قد يستخدم عرض PDF ملف تعريف ألوان مختلف. | استخدم قيم `System.Drawing.Color` القياسية أو عرّف ألوان ARGB مخصصة. |
| **محول النص يسبب استثناء مرجع فارغ** | خاصية المهمة `Tsk.Name` فارغة لبعض المهام. | أضف فحصًا للـ null قبل الوصول إلى `task.Get(Tsk.Name)`. |

## الأسئلة المتكررة

### س1: هل يمكنني تطبيق أنماط شريط متعددة على مشروع واحد؟

ج1: نعم، يمكنك تعريف وتطبيق أنماط شريط متعددة على أنواع مختلفة من المهام داخل نفس المشروع.

### س2: هل من الممكن تغيير أنماط الشريط ديناميكيًا أثناء التشغيل؟

ج2: نعم، يمكنك تعديل أنماط الشريط ديناميًا بناءً على شروط معينة أو تفضيلات المستخدم داخل تطبيقك.

### س3: هل يدعم Aspose.Tasks تصدير المشاريع مع أشرطة منسقة إلى صيغ ملفات مختلفة؟

ج3: نعم، يدعم Aspose.Tasks تصدير المشاريع مع أشرطة منسقة إلى صيغ متعددة مثل PDF، XLSX، وHTML.

### س4: هل هناك أنماط شريط مسبقة التعريف متاحة في Aspose.Tasks؟

ج4: بينما يوفر Aspose.Tasks أنماط شريط افتراضية، يمكن للمطورين أيضًا إنشاء أنماط شريط مخصصة تتناسب مع متطلبات مشروعهم.

### س5: هل يمكنني استرجاع وتعديل أنماط الشريط الموجودة داخل مشروع باستخدام API؟

ج5: نعم، يمكنك استرجاع وتعديل أنماط الشريط الموجودة برمجيًا باستخدام Aspose.Tasks لـ .NET API.

## الأسئلة المتداولة

**س: كيف أغير لون الشريط للمهام العادية بدلاً من المعالم؟**  
ج: قم بتعيين `style.ItemType = BarItemType.Task;` ثم عيّن `style.BarColor` إلى اللون `Color` المطلوب.

**س: هل يمكنني استخدام هذا النهج لتنسيق الأشرطة عند التصدير إلى HTML؟**  
ج: نعم. استخدم `HtmlSaveOptions` واملأ مجموعة `BarStyles` الخاصة به بنفس الطريقة.

**س: هل هناك حد لعدد أنماط الشريط التي يمكنني تعريفها؟**  
ج: عمليًا لا؛ يمكنك إضافة عدد ما تشاء حسب الحاجة، لكن ضع في اعتبارك الأداء عند التعامل مع مجموعات كبيرة جدًا.

**س: هل أحتاج إلى استدعاء `project.Calculate()` بعد تغيير الأنماط؟**  
ج: لا، يتم تطبيق الأنماط أثناء عملية الحفظ؛ لا يلزم إعادة الحساب إلا لتغييرات الجدول الزمني.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}