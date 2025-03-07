---
title: التعامل مع استثناءات التقويم في Aspose.Tasks
linktitle: التعامل مع استثناءات التقويم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة استثناءات التقويم في Aspose.Tasks لـ .NET من خلال البرامج التعليمية والأمثلة خطوة بخطوة.
weight: 12
url: /ar/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التعامل مع استثناءات التقويم في Aspose.Tasks

## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة استثناءات التقويم في Aspose.Tasks باستخدام إطار عمل .NET. تسمح لنا استثناءات التقويم بتحديد تواريخ أو فترات خاصة في تقويم المشروع حيث يتم تغيير جدول العمل العادي، مثل العطلات أو الإغلاق المؤقت. سنغطي الطرق المختلفة للتعامل مع استثناءات التقويم خطوة بخطوة، باستخدام Aspose.Tasks لـ .NET.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على نظامك.
- تمت إضافة Aspose.Tasks لمكتبة .NET إلى مشروعك.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية لمشروعنا:

```csharp
using Aspose.Tasks;
using System;


```

## الخطوة 1: حذف استثناء التقويم

لحذف استثناء التقويم، اتبع الخطوات التالية:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // عرض معلومات التقويم
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // إزالة الاستثناء الأول
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## الخطوة 2: الحصول على وقت العمل لاستثناء التقويم

لاسترداد وقت العمل لاستثناء التقويم، اتبع الخطوات التالية:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // عرض معلومات التقويم والاستثناءات
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // الحصول على وقت العمل وعرض التفاصيل
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## الخطوة 3: تحديد استثناءات التقويم

لإضافة أو إزالة استثناءات التقويم، اتبع الخطوات التالية:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // إنشاء استثناء تقويم جديد
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // تعيين تفاصيل الاستثناء
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // تحقق مما إذا كان التاريخ استثناءً
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // أضف الاستثناء إلى التقويم
    calendar.Exceptions.Add(exception);

    // إزالة الاستثناء إذا كان موجودا
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // إضافة استثناء جديد
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // استثناءات الطباعة
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## خاتمة

في هذه المقالة، قمنا بتغطية الجوانب المختلفة للتعامل مع استثناءات التقويم في Aspose.Tasks لـ .NET. من خلال اتباع الخطوات المقدمة، يمكنك إدارة الاستثناءات بشكل فعال في جداول مشروعك، مما يضمن التمثيل الدقيق لساعات العمل والمناسبات الخاصة.

## الأسئلة الشائعة

### س1: هل يمكنني إضافة استثناءات متعددة إلى تقويم واحد؟

ج1: نعم، يمكنك إضافة استثناءات متعددة إلى تقويم لاستيعاب تواريخ أو فترات خاصة مختلفة.

### س2: كيف يمكنني التحقق مما إذا كان تاريخ معين يمثل استثناءً؟

 ج2: يمكنك استخدام`CheckException()` طريقة للتحقق مما إذا كان تاريخ معين يقع ضمن الاستثناء.

### س3: هل من الممكن إزالة استثناء موجود من التقويم؟

 ج3: نعم، يمكنك إزالة الاستثناءات عن طريق الوصول إلى ملف`Exceptions` جمع التقويم واستخدام`Remove()` طريقة.

### س٤: ما هي أنواع استثناءات التقويم المدعومة؟

ج4: يدعم Aspose.Tasks أنواعًا مختلفة من الاستثناءات، بما في ذلك الاستثناءات اليومية والأسبوعية والشهرية والسنوية، مما يوفر المرونة في تعريف قواعد الاستثناء.

### س5: هل يمكنني تخصيص ساعات العمل لتواريخ استثناء محددة؟

ج5: نعم، يمكنك تحديد أوقات عمل مخصصة لتواريخ الاستثناءات الفردية باستخدام الطرق المناسبة التي يوفرها Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
