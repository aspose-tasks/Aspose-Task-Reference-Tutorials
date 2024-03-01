---
title: نوع الحساب في Aspose.Tasks
linktitle: نوع الحساب في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تخصيص حسابات القيمة في مشاريع .NET باستخدام نوع الحساب في مكتبة Aspose.Tasks.
type: docs
weight: 30
url: /ar/net/advanced-features/calculation-type/
---
## مقدمة

في هذا البرنامج التعليمي، سنستكشف ميزة "نوع الحساب" في Aspose.Tasks لـ .NET. Aspose.Tasks هي مكتبة قوية تمكن مطوري .NET من العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project على أنظمتهم. يتيح لنا نوع الحساب تحديد كيفية حساب القيم للمهام والمهام الموجزة داخل المشروع.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. المعرفة الأساسية بـ C# و.NET Framework.
2. تم تثبيت Visual Studio على نظامك.
3.  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
4.  الوصول إلى Aspose.Tasks لوثائق .NET كمرجع، متاح[هنا](https://reference.aspose.com/tasks/net/).

## استيراد مساحات الأسماء

قبل الغوص في المثال، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System;


```

## الخطوة 1: إنشاء مشروع جديد

أولاً، لنقم بإنشاء كائن مشروع جديد:

```csharp
var project = new Project();
```

## الخطوة 2: إضافة مهمة

الآن، دعونا نضيف مهمة لمشروعنا:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## الخطوة 3: تحديد نوع الحساب للسمة الموسعة

سنقوم بإنشاء تعريف موسع للسمة مع تعيين نوع الحساب على الصيغة:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## الخطوة 4: تحديد نوع الحساب لصفوف الملخص

بعد ذلك، سنقوم بإنشاء تعريف موسع آخر للسمة حيث يتم حساب قيم المهام الموجزة باستخدام نوع متوسط القيمة المحتسبة:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية العمل مع نوع الحساب في Aspose.Tasks لـ .NET. من خلال تحديد أنواع الحساب للسمات الموسعة، يمكننا تخصيص كيفية حساب القيم للمهام والمهام الموجزة داخل المشروع، مما يوفر قدرًا أكبر من المرونة والتحكم.

## الأسئلة الشائعة

### س1: ما هو نوع الحساب في Aspose.Tasks؟

A1: نوع الحساب في Aspose.Tasks يحدد كيفية حساب القيم للمهام والمهام الموجزة داخل المشروع، مما يوفر خيارات مثل الصيغة وقيمة محتسبة.

### س٢: كيف أقوم بتعيين نوع الحساب للسمة الموسعة؟

ج2: يمكنك تعيين نوع الحساب للسمة الموسعة عن طريق تحديد خاصية CalculationType الخاصة بها وفقًا لذلك.

### س3: هل يمكنني تخصيص نوع الحساب لصفوف التلخيص في المشروع؟

ج3: نعم، يتيح لك Aspose.Tasks تحديد نوع الحساب لصفوف التلخيص، مما يتيح لك تخصيص حسابات القيمة بناءً على متطلباتك.

### س4: هل هناك أنواع مختلفة من القيمة المحتسبة متاحة لحسابات المهام الموجزة؟

ج4: نعم، يوفر Aspose.Tasks العديد من أنواع القيمة المحتسبة مثل المتوسط والمجموع والعدد لحساب قيم المهام الموجزة.

### س5: أين يمكنني العثور على المزيد من الموارد على Aspose.Tasks لـ .NET؟

 ج5: يمكنك استكشاف الوثائق ومنتديات دعم المجتمع المتاحة على[Aspose.Tasks لـ .NET](https://reference.aspose.com/tasks/net/) للحصول على التوجيه والمساعدة الشاملة.