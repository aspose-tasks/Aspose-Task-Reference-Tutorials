---
title: شريط التصميم في Aspose.Tasks
linktitle: شريط التصميم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تصميم الأشرطة في Aspose.Tasks لـ .NET لتحسين تصور المشروع.
type: docs
weight: 19
url: /ar/net/advanced-features/styling-bar/
---
## مقدمة

تعد أشرطة التصميم في Aspose.Tasks جانبًا أساسيًا لإنشاء خطط مشروع جذابة بصريًا. بفضل المرونة التي توفرها واجهة Aspose.Tasks API، يمكن للمطورين تخصيص جوانب مختلفة من الأشرطة، مثل اللون والشكل ونمط النص، لتحسين تصور المشروع. في هذا البرنامج التعليمي، سوف نستكشف كيفية تصميم الأشرطة باستخدام Aspose.Tasks لـ .NET، مع تقسيم كل مثال إلى خطوات يمكن التحكم فيها.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[صفحة التحميل](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير بدعم .NET Framework.
3. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية للوصول إلى فئات Aspose.Tasks وطرقها:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## الخطوة 1: تحميل المشروع

للبدء، قم بتحميل ملف المشروع باستخدام Aspose.Tasks API:

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## الخطوة 2: تكوين خيارات الحفظ

حدد خيارات الحفظ، مع تحديد أنماط الشريط المراد تطبيقها:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## الخطوة 3: تحديد نمط الشريط

قم بإنشاء نمط شريط جديد وتخصيص خصائصه:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // تعيين نوع عنصر الشريط
style.BarColor = Color.Green; // تعيين لون الشريط
style.BarShape = BarShape.HalfHeight; //ضبط شكل الشريط
style.StartShape = Shape.LeftBracket; // تعيين الشكل في بداية الشريط
style.StartShapeColor = Color.Aqua; // ضبط لون شكل البداية
style.EndShape = Shape.RightBracket; // تعيين الشكل في نهاية الشريط
style.EndShapeColor = Color.Aquamarine; // تحديد لون الشكل النهائي
style.TextStyle = new TextStyle(); // ضبط نمط النص
style.TextStyle.BackgroundColor = Color.Black; // تعيين لون الخلفية للنص
```

## الخطوة 4: تخصيص محول النص

اختياريًا، قم بتخصيص محول النص لتعديل عرض النص:

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

أضف نمط الشريط الذي تم تكوينه إلى خيارات الحفظ:

```csharp
options.BarStyles.Add(style);
```

## الخطوة 6: احفظ المشروع

أخيرًا، احفظ المشروع باستخدام أنماط الشريط المطبقة:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## خاتمة

يوفر تخصيص أنماط الشريط في Aspose.Tasks لـ .NET للمطورين القدرة على إنشاء خطط مشروع جذابة بصريًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تصميم الأشرطة بكفاءة لتلبية متطلبات تصور المشروع المحددة.

## الأسئلة الشائعة

### س1: هل يمكنني تطبيق أنماط شريطية متعددة على مشروع واحد؟

ج1: نعم، يمكنك تحديد أنماط شريطية متعددة وتطبيقها على أنواع مختلفة من المهام داخل نفس المشروع.
   
### س2: هل من الممكن تغيير أنماط الشريط ديناميكيًا أثناء وقت التشغيل؟

ج2: نعم، يمكنك تعديل أنماط الشريط ديناميكيًا استنادًا إلى شروط معينة أو تفضيلات المستخدم داخل التطبيق الخاص بك.
   
### س 3: هل يدعم Aspose.Tasks تصدير المشاريع ذات الأشرطة ذات الأنماط إلى تنسيقات ملفات مختلفة؟

ج3: نعم، يدعم Aspose.Tasks تصدير المشروعات ذات الأشرطة ذات الأنماط إلى تنسيقات مختلفة مثل PDF وXLSX وHTML.
   
### س4: هل تتوفر أنماط شريطية محددة مسبقًا في Aspose.Tasks؟

ج4: بينما يوفر Aspose.Tasks أنماط شريط افتراضية، يمكن للمطورين أيضًا إنشاء أنماط شريط مخصصة مصممة وفقًا لمتطلبات المشروع الخاصة بهم.
   
### س5: هل يمكنني استرداد أنماط الشريط الموجودة وتعديلها داخل مشروع باستخدام واجهة برمجة التطبيقات (API)؟

ج5: نعم، يمكنك استرداد أنماط الشريط الموجودة وتعديلها برمجيًا باستخدام Aspose.Tasks لـ .NET API.