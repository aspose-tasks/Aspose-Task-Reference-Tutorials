---
date: 2026-04-06
description: تعلم كيفية حذف جميع الخطوط الأساسية وإدارة مجموعات الخطوط الأساسية في
  Aspose.Tasks لـ .NET مع أمثلة برمجية خطوة بخطوة.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: حذف جميع الخطوط الأساسية باستخدام مجموعة الخطوط الأساسية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: حذف جميع الخطوط الأساسية باستخدام مجموعة الخطوط الأساسية في Aspose.Tasks
url: /ar/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حذف جميع الخطوط الأساسية باستخدام مجموعة Baseline من Aspose.Tasks

## مقدمة

تتيح لك Aspose.Tasks for .NET التلاعب بملفات Microsoft Project مباشرةً من تطبيقات .NET الخاصة بك. واحدة من أقوى الميزات هي القدرة على **حذف جميع الخطوط الأساسية** لمورد ما، وهو أمر أساسي عندما تحتاج إلى إعادة ضبط بيانات تتبع المشروع أو بدء فترة خط أساسي جديدة. في هذا البرنامج التعليمي سنستعرض العملية بالكامل — من تحميل ملف المشروع إلى إزالة كل خط أساسي مرتبط بمورد محدد — باستخدام شروحات واضحة ومحادثة وكود C# جاهز للتنفيذ.

## إجابات سريعة
- **ما الذي يفعله “حذف جميع الخطوط الأساسية”?** يزيل كل سجل خط أساسي مخزن للموارد المحددة، مما يمسح بيانات التكلفة والعمل التاريخية.  
- **لماذا قد أحتاج إلى ذلك؟** لإعادة ضبط التتبع بعد تغيير كبير في المشروع أو عندما تصبح الخطوط الأساسية الأصلية غير ذات صلة.  
- **أي مكتبة توفر هذه القدرة؟** Aspose.Tasks for .NET.  
- **هل أحتاج إلى ترخيص؟** يتطلب الاستخدام في الإنتاج ترخيص صالح لـ Aspose.Tasks؛ يتوفر إصدار تجريبي مجاني.  
- **هل الكود متوافق مع .NET 6+؟** نعم، تعمل الواجهة البرمجية مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6.

## ما هو الخط الأساسي ولماذا حذف جميع الخطوط الأساسية؟

الخط الأساسي يلتقط الخطة الأصلية للتكلفة والعمل والجدول الزمني في نقطة زمنية محددة. خلال عمر المشروع قد تنشئ عدة خطوط أساسية (Baseline 1، Baseline 2، إلخ) لمقارنة التقدم الفعلي مع لقطات تخطيطية مختلفة. ومع ذلك، هناك سيناريوهات — مثل إعادة تحديد نطاق المشروع أو بدء جديد — حيث يصبح الاحتفاظ بهذه الخطوط الأساسية التاريخية مربكًا. حذف جميع الخطوط الأساسية يمنحك صفحة نظيفة، مما يسمح لك بتعيين خطوط أساسية جديدة تعكس الواقع الحالي.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من وجود ما يلي:

1. **Visual Studio** – أي إصدار حديث (Community أو Professional أو Enterprise).  
2. **Aspose.Tasks for .NET** – قم بتنزيله من [download link](https://releases.aspose.com/tasks/net/).  
3. **معرفة أساسية بـ C#** – يجب أن تكون مرتاحًا مع المتغيرات، الحلقات، وإخراج الكونسول.  
4. **ملف Microsoft Project** (`.mpp`) – سيتم استخدام ملف عينة اسمه *WorkWithBaselineCollection.mpp* في الأمثلة.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء الضرورية حتى يعرف المترجم أين يجد الفئات التي سنستخدمها.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## الخطوة 1: تحميل ملف المشروع

نبدأ بتحميل ملف مشروع موجود. عدل `DataDir` لتشير إلى المجلد الذي يحتوي على ملف `.mpp` الخاص بك.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## الخطوة 2: الحصول على المورد المستهدف

للتوضيح، نستخرج المورد الذي له UID = 1. في سيناريو واقعي ستحدد المورد بالاسم أو معرف آخر.

```csharp
var resource = project.Resources.GetByUid(1);
```

## الخطوة 3: عرض معلومات الخط الأساسي الموجودة

قبل حذف أي شيء، من المفيد رؤية الخطوط الأساسية المرفقة بالمورد حاليًا. هذا يمنحك الثقة أنك تزيل البيانات الصحيحة.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## الخطوة 4: التكرار عبر جميع الخطوط الأساسية

هنا نمر على كل خط أساسي، نطبع مقاييس رئيسية مثل التكلفة، العمل، والقيمة المكتسبة (BCWP/BCWS). هذه الخطوة اختيارية لكنها مفيدة للتسجيل أو المراجعة.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## حذف جميع الخطوط الأساسية

الآن نقوم بالإجراء الأساسي: **حذف جميع الخطوط الأساسية** للمورد المحدد. أولاً نقوم بنسخ المجموعة إلى قائمة لتجنب تعديل المجموعة أثناء التكرار، ثم نزيل كل خط أساسي على حدة.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

بعد تشغيل هذا المقطع، سيكون `resource.Baselines.Count` مساويًا لـ `0`، مما يؤكد أن جميع سجلات الخط الأساسي قد تم مسحها.

## المشكلات الشائعة والنصائح

- **NullReferenceException** – تأكد من أن ملف المشروع يحتوي فعليًا على المورد المستهدف؛ وإلا سيعيد `GetByUid` قيمة `null`.  
- **Licensing** – بدون ترخيص Aspose.Tasks صالح ستظهر علامة مائية في الناتج وستكون الوظائف محدودة.  
- **Performance** – للمشاريع الكبيرة جدًا، فكر في التكرار باستخدام `Parallel.ForEach` لتسريع عملية الإزالة، لكن تذكر أن المجموعة الأساسية غير آمنة للاستخدام المتعدد الخيوط.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع ملفات مشروع كبيرة؟**  
ج: نعم، تم تحسين Aspose.Tasks للأداء ويمكنه معالجة ملفات `.mpp` متعددة الجيجابايت بكفاءة.

**س: هل المكتبة متوافقة مع جميع إصدارات Microsoft Project؟**  
ج: تدعم Aspose.Tasks Project 2000 حتى Project 2024، بما يشمل صيغ `.mpp` القديمة والملفات القائمة على XML الحديثة.

**س: هل يمكنني تخصيص الخطوط الأساسية قبل حذفها؟**  
ج: بالتأكيد. يمكنك قراءة أو تعديل أي خاصية للخط الأساسي (التكلفة، العمل، التواريخ) قبل اتخاذ قرار الحذف.

**س: هل تعمل Aspose.Tasks على منصات السحابة؟**  
ج: نعم، تعمل الواجهة البرمجية على أي بيئة متوافقة مع .NET، بما في ذلك Azure App Service، AWS Lambda (عبر .NET Core)، وحاويات Docker.

**س: أين يمكنني طلب المساعدة من المجتمع؟**  
ج: زر [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) للتواصل مع مطورين آخرين وفريق Aspose.

## الخلاصة

في هذا الدليل أظهرنا كيفية **حذف جميع الخطوط الأساسية** من مورد باستخدام Aspose.Tasks for .NET. باتباع الكود خطوة بخطوة، يمكنك إعادة ضبط بيانات الخط الأساسي، الحفاظ على نظافة تتبع المشروع، وتحضير جدولك الزمني لدورة تخطيط جديدة. لا تتردد في تجربة إنشاء خطوط أساسية جديدة بعد الحذف لترى كيف تقوم المكتبة بتحديث ملف المشروع.

---

**آخر تحديث:** 2026-04-06  
**تم الاختبار مع:** Aspose.Tasks 24.12 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}