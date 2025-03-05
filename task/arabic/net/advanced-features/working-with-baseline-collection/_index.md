---
title: العمل مع مجموعة Baseline في Aspose.Tasks
linktitle: العمل مع مجموعة Baseline في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة الخطوط الأساسية في Aspose.Tasks لـ .NET بكفاءة. اتبع برنامجنا التعليمي الشامل للحصول على إرشادات خطوة بخطوة.
type: docs
weight: 20
url: /ar/net/advanced-features/working-with-baseline-collection/
---
## مقدمة

Aspose.Tasks for .NET هي مكتبة قوية تمكن المطورين من العمل مع ملفات Microsoft Project في تطبيقات .NET الخاصة بهم بسلاسة. ومن بين ميزاته العديدة، أنه يوفر دعمًا قويًا لإدارة خطوط الأساس داخل المشاريع. تعتبر خطوط الأساس ضرورية لإدارة المشروع لأنها تسمح لك بمقارنة خطة المشروع الأصلية بالحالة الحالية، مما يتيح تتبع وتحليل تقدم المشروع بشكل أفضل.

## المتطلبات الأساسية

قبل أن نتعمق في العمل مع المجموعات الأساسية في Aspose.Tasks، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: قم بتثبيت Visual Studio IDE على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[رابط التحميل](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: تعرف على لغة البرمجة C#.
4. ملف Microsoft Project: احصل على ملف Microsoft Project (.mpp) جاهزًا لأغراض الاختبار.

## استيراد مساحات الأسماء

لبدء العمل مع المجموعات الأساسية في Aspose.Tasks، تحتاج إلى استيراد مساحات الأسماء التالية:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

الآن، دعونا نقسم كل مثال إلى خطوات متعددة:

## الخطوة 1: تحميل ملف المشروع

أولاً، قم بتحميل ملف Microsoft Project باستخدام Aspose.Tasks:

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## الخطوة 2: الحصول على الموارد

بعد ذلك، قم باسترداد المورد المطلوب من المشروع:

```csharp
var resource = project.Resources.GetByUid(1);
```

## الخطوة 3: عرض المعلومات الأساسية

الآن، قم بعرض معلومات حول الخطوط الأساسية المرتبطة بالمورد:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## الخطوة 4: التكرار من خلال خطوط الأساس

قم بالتكرار خلال كل خط أساسي مرتبط بالمورد وطباعة المعلومات ذات الصلة:

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

## الخطوة 5: إزالة خطوط الأساس

حذف جميع خطوط الأساس المرتبطة بالمورد:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية العمل مع المجموعات الأساسية في Aspose.Tasks لـ .NET. باتباع الدليل التفصيلي خطوة بخطوة، يمكنك بسهولة إدارة الخطوط الأساسية داخل تطبيقات .NET الخاصة بك، مما يسمح بتتبع المشروع وتحليله بشكل فعال.

## الأسئلة الشائعة

### س1: هل يستطيع Aspose.Tasks التعامل مع ملفات المشاريع الكبيرة؟

ج1: نعم، تم تحسين Aspose.Tasks للتعامل مع ملفات المشاريع الكبيرة بكفاءة، مما يضمن الأداء السلس.

### س2: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟

ج2: يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س3: هل يمكنني تخصيص الخطوط الأساسية في Aspose.Tasks؟

ج3: نعم، يمكنك تخصيص الخطوط الأساسية وفقًا لمتطلبات مشروعك باستخدام Aspose.Tasks لـ .NET.

### س 4: هل يقدم Aspose.Tasks الدعم للأنظمة الأساسية السحابية؟

ج4: نعم، يوفر Aspose.Tasks الدعم للتكامل مع الأنظمة الأساسية السحابية الشائعة، مما يوفر المرونة في النشر.

### س5: هل يوجد منتدى مجتمعي لمستخدمي Aspose.Tasks لطلب المساعدة ومشاركة المعرفة؟

 ج5: نعم، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للتواصل مع المجتمع والحصول على المساعدة من الخبراء.