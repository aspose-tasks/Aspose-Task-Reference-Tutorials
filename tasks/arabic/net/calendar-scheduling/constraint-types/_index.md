---
title: أنواع القيود في Aspose.Tasks
linktitle: أنواع القيود في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تعيين أنواع القيود في Aspose.Tasks لـ .NET لإدارة جداول المشروع بكفاءة.
weight: 17
url: /ar/net/calendar-scheduling/constraint-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أنواع القيود في Aspose.Tasks

## مقدمة

عند العمل مع إدارة المشاريع في .NET، من الضروري فهم كيفية تطبيق قيود مختلفة على المهام. يوفر Aspose.Tasks for .NET مجموعة شاملة من الأدوات لإدارة قيود المشروع بكفاءة. في هذا البرنامج التعليمي، سوف نتعمق في أنواع القيود المختلفة المتوفرة في Aspose.Tasks وكيفية تنفيذها خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية:

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## الخطوة 1: تحميل ملف المشروع

 ابدأ بتحميل ملف المشروع حيث تريد تعيين القيد. يمكنك استخدام ال`Project` فئة لهذا الغرض:

```csharp
var project = new Project("PathToYourProjectFile");
```

## الخطوة 2: تعيين نوع القيد

بعد ذلك، حدد نوع القيد الذي تريد تطبيقه على مهمة معينة. في هذا المثال، سنقوم بتعيين نوع القيد على أنه "في أقرب وقت ممكن":

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## الخطوة 3: احفظ المشروع

بمجرد تعيين القيد، يمكنك حفظ ملف المشروع. فلنحفظه كملف PDF:

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية تعيين أنواع القيود في Aspose.Tasks لـ .NET. باتباع هذه الخطوات البسيطة، يمكنك إدارة القيود داخل مشاريعك بكفاءة، مما يضمن التنفيذ السلس.

## الأسئلة الشائعة

### س1: ما هي معوقات المشروع؟

A1: قيود المشروع هي قيود أو قيود تؤثر على تاريخ البدء أو الانتهاء لمهمة في جدول المشروع.

### س2: ما عدد أنواع القيود التي يدعمها Aspose.Tasks؟

ج2: يدعم Aspose.Tasks عدة أنواع من القيود، بما في ذلك "في أقرب وقت ممكن" و"في أقرب وقت ممكن" و"الانتهاء قبل ذلك" و"الانتهاء في وقت لاحق" و"يجب أن يبدأ" و"يجب أن ينتهي".

### س3: هل يمكنني تطبيق القيود على مهام متعددة في وقت واحد؟

ج3: نعم، يمكنك تطبيق القيود على مهام متعددة في وقت واحد باستخدام Aspose.Tasks لـ .NET.

### س 4: هل Aspose.Tasks مناسب لكل من المشاريع الصغيرة والكبيرة الحجم؟

ج4: نعم، تم تصميم Aspose.Tasks للتعامل مع المشاريع بكافة أحجامها، بدءًا من المهام الصغيرة وحتى المشاريع كبيرة الحجم.

### س5: أين يمكنني الحصول على الدعم للاستعلامات المتعلقة بـ Aspose.Tasks؟

 ج5: يمكنك الحصول على الدعم لـ Aspose.Tasks من خلال زيارة موقعهم[المنتدى](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
