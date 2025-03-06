---
title: العمل مع فترات التوفر في Aspose.Tasks
linktitle: العمل مع فترات التوفر في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة فترات توفر الموارد بكفاءة باستخدام Aspose.Tasks لـ .NET. يوفر هذا البرنامج التعليمي دليلاً خطوة بخطوة للتعامل مع فترات التوفر في مشاريع .NET الخاصة بك.
weight: 17
url: /ar/net/advanced-features/working-with-availability-periods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# العمل مع فترات التوفر في Aspose.Tasks

## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية التعامل مع فترات التوفر في Aspose.Tasks لـ .NET. تعتبر فترات التوفر ضرورية لإدارة الموارد بكفاءة في سيناريوهات إدارة المشروع. سنرشدك خلال العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير متكاملة أخرى مفضلة لتطوير .NET.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لبرمجة C#: الإلمام بأساسيات لغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء

قبل الغوص في التعليمات البرمجية، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

دعونا نقسم رمز المثال إلى خطوات متعددة:

## الخطوة 1: إنشاء مثيل مشروع جديد

```csharp
var project = new Project();
```

يقوم هذا السطر بتهيئة مثيل جديد لفئة Project، والذي يمثل مشروعًا في Aspose.Tasks.

## الخطوة 2: إضافة مورد

```csharp
var resource = project.Resources.Add("Work Resource");
```

هنا، نضيف موردًا جديدًا إلى المشروع باسم "مورد العمل".

## الخطوة 3: تحديد فترات التوفر

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 نحن نسمي`GetPeriods()` طريقة لاسترداد مجموعة من فترات التوفر.

## الخطوة 4: إضافة فترات التوفر إلى المورد

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

نقوم بالتكرار من خلال جمع فترات التوفر التي تم الحصول عليها في الخطوة السابقة وإضافتها إلى المورد.

## الخطوة 5: عرض تفاصيل فترة التوفر

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

أخيرًا، نقوم بمراجعة فترات التوفر المرتبطة بالمورد وطباعة تفاصيلها، بما في ذلك تاريخ البدء وتاريخ الانتهاء والوحدات المتاحة.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع فترات التوفر في Aspose.Tasks لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك إدارة توفر الموارد بكفاءة في تطبيقات إدارة المشروعات الخاصة بك.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Tasks لـ .NET في المشاريع التجارية؟

 A1: نعم، يمكن استخدام Aspose.Tasks لـ .NET في المشاريع التجارية. يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy).

### س2: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟

ج٢: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET[هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على وثائق Aspose.Tasks لـ .NET؟

 ج3: يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/tasks/net/).

### س٤: كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟

 ج4: يمكنك الحصول على الدعم من منتدى المجتمع[هنا](https://forum.aspose.com/c/tasks/15).

### س5: هل تقدمون تراخيص مؤقتة لـ Aspose.Tasks لـ .NET؟

 ج5: نعم، تتوفر تراخيص مؤقتة[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
