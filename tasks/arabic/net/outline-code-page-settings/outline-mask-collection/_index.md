---
title: أقنعة المخطط التفصيلي لمشروع MS Master مع Aspose.Tasks
linktitle: مجموعة من أقنعة المخطط التفصيلي في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع أقنعة المخطط التفصيلي لمجموعة MS Project باستخدام Aspose.Tasks لـ .NET. تعزيز الإنتاجية مع هذا البرنامج التعليمي الشامل.
type: docs
weight: 15
url: /ar/net/outline-code-page-settings/outline-mask-collection/
---
## مقدمة
هل تتطلع إلى الاستفادة من قوة أقنعة المخطط التفصيلي لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET؟ لقد جئت إلى المكان المناسب! في هذا البرنامج التعليمي الشامل، سنرشدك خلال العملية خطوة بخطوة، مما يضمن حصولك على فهم قوي لكيفية التعامل بشكل فعال مع أقنعة المخطط التفصيلي في مشاريعك. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيزودك هذا الدليل بالمعرفة والمهارات اللازمة لتحسين سير عملك.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
### 1. تثبيت Aspose.Tasks لـ .NET
تأكد من تثبيت Aspose.Tasks for .NET في بيئة التطوير الخاصة بك. يمكنك تحميل المكتبة من موقع Aspose[هنا](https://releases.aspose.com/tasks/net/).
### 2. المعرفة الأساسية بـ C# و.NET Framework
تعرف على لغة البرمجة C# و.NET Framework، حيث سيستخدم هذا البرنامج التعليمي كليهما.
### 3. ملف مشروع مايكروسوفت
احصل على ملف Microsoft Project (MPP) جاهزًا لأغراض الاختبار. يمكنك استخدام ملف موجود أو إنشاء ملف جديد للتجربة.
## استيراد مساحات الأسماء
لنبدأ باستيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. تضمن هذه الخطوة أن لديك إمكانية الوصول إلى الفئات والوظائف المطلوبة التي يوفرها Aspose.Tasks لـ .NET.

أضف مساحات الأسماء التالية في بداية ملف التعليمات البرمجية الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
```
الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة ونشرح كل خطوة بالتفصيل:
## الخطوة 1: تهيئة كائن المشروع
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 هنا نقوم بإنشاء نسخة جديدة من`Project` فئة وتحميل ملف Microsoft Project موجود يسمى "OutlineValues2010.mpp".
## الخطوة 2: الوصول إلى رموز المخطط التفصيلي
```csharp
var outline = project.OutlineCodes[0];
```
يمكننا الوصول إلى رموز المخطط التفصيلي من المشروع. رموز المخطط التفصيلي هي حقول مخصصة في Microsoft Project تسمح لك بتصنيف المهام وتنظيمها.
## الخطوة 3: مسح أقنعة المخطط التفصيلي
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
تضمن هذه الخطوة مسح أي أقنعة مخطط تفصيلي موجودة قبل المتابعة.
## الخطوة 4: إنشاء أقنعة المخطط التفصيلي
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
نقوم بإنشاء أقنعة مخطط تفصيلي جديدة ونحدد أنواعها. في هذا المثال، قمنا بإنشاء قناع مخطط تفصيلي صالح وآخر خاطئ.
## الخطوة 5: إدراج الأقنعة وتحريرها
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
هنا، نقوم بإدراج قناع خاطئ في المجموعة وتعديل طول القناع باستخدام الفهرس الخاص به.
## الخطوة 6: إزالة الأقنعة
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
نقوم بإزالة القناع الخاطئ من المجموعة بناءً على فهرسها.
## الخطوة 7: التكرار على الأقنعة
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
تتكرر هذه الحلقة فوق كل قناع مخطط تفصيلي في المجموعة وتطبع خصائصه مثل الطول والمستوى والفاصل والنوع.
## الخطوة 8: نسخ الأقنعة إلى مشروع آخر
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
وأخيرًا، نقوم بنسخ أقنعة المخطط التفصيلي من مشروع إلى آخر، مما يضمن الاتساق عبر المشاريع المختلفة.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية التعامل مع أقنعة المخطط التفصيلي لمجموعة MS Project باستخدام Aspose.Tasks لـ .NET. باتباع هذا البرنامج التعليمي، أنت الآن مجهز بالمهارات اللازمة لإدارة أقنعة المخطط التفصيلي بكفاءة في مشاريعك، مما يؤدي في النهاية إلى تحسين إنتاجيتك وسير العمل.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Tasks لـ .NET مع إصدارات مختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks for .NET إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### س2: هل Aspose.Tasks لـ .NET متوافق مع .NET Core؟
ج: نعم، Aspose.Tasks for .NET متوافق مع .NET Core، مما يسمح لك باستخدامه في التطبيقات عبر الأنظمة الأساسية.
### س3: هل يمكنني تخصيص خصائص أقنعة المخطط التفصيلي وفقًا لمتطلبات مشروعي؟
ج: بالتأكيد! يمكنك تخصيص أقنعة المخطط التفصيلي عن طريق ضبط طولها ومستواها وفاصلها ونوعها لتناسب احتياجات مشروعك المحددة.
### س 4: هل يوفر Aspose.Tasks لـ .NET الوثائق والدعم؟
ج: نعم، يقدم Aspose.Tasks for .NET وثائق شاملة ودعمًا مخصصًا من خلال موقعه على الويب و[المنتديات](https://forum.aspose.com/c/tasks/15).
### س5: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Tasks لـ .NET من موقعهم[موقع إلكتروني](https://releases.aspose.com/tasks/net/). لاستكشاف ميزاته ووظائفه قبل إجراء عملية الشراء.