---
title: مجموعة فترات التوفر في Aspose.Tasks
linktitle: مجموعة فترات التوفر في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة فترات توفر الموارد في Aspose.Tasks لـ .NET. يرشدك هذا البرنامج التعليمي خطوة بخطوة خلال إضافة فترات التوفر وتحديثها وإزالتها، مما يضمن التخطيط الفعال لموارد المشروع.
type: docs
weight: 18
url: /ar/net/advanced-features/availability-period-collection/
---
## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع مجموعة فترة التوفر لأحد الموارد في Aspose.Tasks لـ .NET. تعد إدارة فترات التوفر أمرًا بالغ الأهمية لإدارة المشروع، مما يسمح لنا بتحديد متى تكون الموارد متاحة للمهام داخل المشروع.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي: الإلمام بـ C# و.NET Framework.

## استيراد مساحات الأسماء

أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية لمشروعنا:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

دعونا نقسم رمز المثال إلى خطوات متعددة ونفهم كل جزء:

## الخطوة 1: تهيئة المشروع والموارد

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

نقوم هنا بتحميل ملف مشروع والحصول على مورد محدد من خلال معرفه.

## الخطوة 2: مسح فترات التوفر الحالية

```csharp
resource.AvailabilityPeriods.Clear();
```

نقوم بمسح أي فترات توفر موجودة مرتبطة بالمورد.

## الخطوة 3: إضافة فترات التوفر

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

نحن نكرر مجموعة من فترات التوفر ونضيفها إلى المورد.

## الخطوة 4: أدخل فترة توافر جديدة

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

نقوم بإنشاء فترة توفر جديدة لعام 2013 وإدراجها في المجموعة.

## الخطوة 5: عرض فترات التوفر

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

نقوم بطباعة عدد وتفاصيل كل فترة توفر مرتبطة بالمورد.

## الخطوة 6: نسخ فترات التوفر إلى مورد آخر

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

نقوم بنسخ فترات التوفر من مورد إلى آخر.

## الخطوة 7: تحديث فترات التوفر وإزالتها

```csharp
// تحديث الوحدات المتاحة لفترة محددة
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// إزالة فترة محددة
otherResource.AvailabilityPeriods.Remove(period2013);
```

نقوم بتحديث الوحدات المتاحة لفترة معينة وإزالة فترات محددة من المجموعة.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية العمل مع مجموعات فترة التوفر في Aspose.Tasks لـ .NET. تعد إدارة توافر الموارد أمرًا ضروريًا لتخطيط المشروع وتنفيذه بشكل فعال.

## الأسئلة الشائعة

### س1: هل يمكنني إضافة حقول مخصصة إلى فترات التوفر؟

ج1: لا، فترات التوفر في Aspose.Tasks لـ .NET لا تدعم الحقول المخصصة.

### س2: هل فترات التوفر مرتبطة بمهام محددة؟

ج2: لا، فترات التوفر مقترنة بالموارد وتحدد متى تكون متاحة للمهام بشكل عام.

### س3: هل يمكنني استيراد فترات التوفر من مصادر خارجية؟

ج3: نعم، يمكنك استيراد فترات التوفر من مصادر بيانات مختلفة باستخدام Aspose.Tasks لـ .NET APIs.

### س 4: كيف يمكنني التعامل مع فترات التوفر المتداخلة؟

A4: لا يوفر Aspose.Tasks لـ .NET آليات مضمنة للتعامل مع الفترات المتداخلة. قد تحتاج إلى تطبيق منطق مخصص لإدارة مثل هذه السيناريوهات.

### س5: هل هناك حد لعدد فترات التوفر التي يمكن أن يتمتع بها المورد؟

ج5: لا يوجد حد محدد مسبقًا لعدد فترات التوفر التي يمكن أن يمتلكها المورد، ولكن قد ينخفض الأداء بعدد كبير من الفترات.