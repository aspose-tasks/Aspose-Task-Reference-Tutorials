---
title: إدارة مجموعة أنواع اليوم في Aspose.Tasks
linktitle: إدارة مجموعة أنواع اليوم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مجموعات أنواع اليوم بكفاءة في Aspose.Tasks لـ .NET. يمكنك إنشاء استثناءات التقويم وتعديلها ومعالجتها بسهولة.
weight: 28
url: /ar/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة مجموعة أنواع اليوم في Aspose.Tasks

## مقدمة

 يوفر Aspose.Tasks for .NET وظائف قوية لإدارة مجموعات أنواع اليوم، وهو أمر ضروري لتحديد استثناءات التقويم الأسبوعية في تطبيقات إدارة المشاريع. في هذا البرنامج التعليمي، سوف نستكشف كيفية الاستفادة من`DayTypeCollection` الطبقة بكفاءة. 

## المتطلبات الأساسية

قبل أن نبدأ البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# ومفاهيم إطار عمل .NET.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك:

```csharp
using Aspose.Tasks;
using System;


```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة:

## الخطوة 1: تحميل المشروع والوصول إلى التقويم

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

تعمل هذه الخطوة على تهيئة مثيل مشروع جديد واسترداد التقويم بواسطة UID الخاص به.

## الخطوة 2: التكرار من خلال استثناءات التقويم

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

هنا، نقوم بالتكرار خلال كل استثناء في التقويم وطباعة اسمه وأنواع الأيام المرتبطة به.

## الخطوة 3: تعديل استثناءات التقويم

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

توضح هذه الخطوة كيفية تعديل استثناءات التقويم عن طريق إضافة أنواع الأيام أو إزالتها أو تحديثها.

## الخطوة 4: إنشاء استثناءات التقويم الجديدة ومعالجتها

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

في هذه الخطوة الأخيرة، نقوم بإنشاء استثناءات جديدة للتقويم ومعالجتها عن طريق إضافة أنواع الأيام ونسخها.

## خاتمة

 في الختام، تعد إدارة مجموعات أنواع اليوم في Aspose.Tasks لـ .NET أمرًا ضروريًا لتحديد وتعديل استثناءات التقويم الأسبوعية في تطبيقات إدارة المشاريع. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك الاستفادة بشكل فعال من`DayTypeCollection` فئة للتعامل مع عمليات التقويم المختلفة.

## الأسئلة الشائعة

### س١: هل يمكن استخدام Aspose.Tasks لـ .NET لإنشاء مخططات جانت برمجيًا؟

ج1: نعم، يوفر Aspose.Tasks لـ .NET واجهات برمجة التطبيقات لإنشاء مخططات جانت ومعالجتها في تطبيقات .NET.

### س2: هل Aspose.Tasks لـ .NET متوافق مع كل من .NET Core و.NET Framework؟

ج2: نعم، يدعم Aspose.Tasks لـ .NET كلاً من .NET Core و.NET Framework.

### س3: كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟

 ج3: يمكنك الحصول على الدعم من خلال زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) حيث يمكنك طرح الأسئلة والتفاعل مع المستخدمين الآخرين.

### س4: هل يقدم Aspose.Tasks لـ .NET نسخة تجريبية مجانية؟

 ج4: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/).

### س5: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ .NET؟

 ج5: نعم، التراخيص المؤقتة متاحة للشراء من[موقع أسبوز](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
