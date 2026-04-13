---
date: 2026-04-13
description: تعلم كيفية حذف استثناء التقويم في Aspose.Tasks لـ .NET والتحقق من تاريخ
  الاستثناء أثناء إدارة جدولة تقويم ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: حذف استثناء التقويم باستخدام Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: حذف استثناء التقويم باستخدام Aspose.Tasks
url: /ar/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حذف استثناء التقويم باستخدام Aspose.Tasks

## المقدمة

في هذا البرنامج التعليمي، ستتعلم كيفية **حذف استثناء التقويم** وإدارة استثناءات التقويم الأخرى في Aspose.Tasks باستخدام إطار عمل .NET. تسمح لك استثناءات التقويم بنمذجة العطلات، الإغلاقات المؤقتة، أو أي فترات خاصة حيث يتغير جدول العمل العادي. فهم كيفية إضافة، استعلام، وإزالة هذه الاستثناءات أمر أساسي لجدولة المشاريع بدقة، خاصةً عند العمل مع سيناريوهات **جدولة تقويم ASP.NET**.

## إجابات سريعة
- **ما هي الطريقة الأساسية لإزالة استثناء؟** استخدم طريقة `Delete()` على كائن `CalendarException`.  
- **أي فئة تتحقق من تاريخ مقابل استثناء؟** `CalendarException.CheckException()` — مفيدة لـ **التحقق من تاريخ الاستثناء**.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في بيئة الإنتاج.  
- **هل يمكنني إضافة استثناءات متعددة إلى تقويم واحد؟** بالتأكيد؛ مجموعة `Exceptions` تدعم العديد من الإدخالات.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هو استثناء التقويم؟

تمثل **استثناء التقويم** انحرافًا عن التقويم العملي العادي — فكر فيه كقاعدة تقول “في هذه التواريخ، ساعات العمل مختلفة أو لا توجد ساعات على الإطلاق”. في Aspose.Tasks، يمكن لكل استثناء أن يمتلك أوقات عمل خاصة به، نمط تكرار، وعلامات تشير إلى ما إذا كان اليوم عمليًا.

## لماذا إدارة استثناءات التقويم في جدولة تقويم ASP.NET؟

- **جداول زمنية دقيقة:** تحترم المشاريع تلقائيًا العطلات والإغلاقات الخاصة، مما يمنع المواعيد النهائية غير الواقعية.  
- **المرونة:** يمكنك تعريف أنماط يومية، أسبوعية، شهرية، أو سنوية، لتطابق تقاويم الأعمال الواقعية.  
- **الأتمتة:** يسمح التحقق البرمجي من تاريخ الاستثناء بإنشاء منطق جدولة ديناميكي في تطبيقات ASP.NET.

## المتطلبات المسبقة

- معرفة أساسية ببرمجة C#.  
- Visual Studio (أي نسخة حديثة).  
- مكتبة Aspose.Tasks لـ .NET مضافة إلى مشروعك (عبر NuGet أو مرجع يدوي).  

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي ستحتاجها:

```csharp
using Aspose.Tasks;
using System;
```

## الخطوة 1: حذف استثناء التقويم

إزالة استثناء غير مرغوب فيه أمر بسيط. الكود التالي يقوم بتحميل مشروع، اختيار أول تقويم، عرض معلومات أساسية، حذف الاستثناء الأول، ثم إظهار العدد المحدث.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **نصيحة احترافية:** تحقق دائمًا من وجود فهرس الاستثناء قبل استدعاء `Delete()` لتجنب `IndexOutOfRangeException`.

## الخطوة 2: الحصول على وقت العمل لاستثناء التقويم

إذا كنت بحاجة إلى فحص ساعات العمل المعرفة لاستثناء ما، استخدم `GetWorkingTime()`. يوضح هذا المثال أيضًا كيفية **التحقق من تاريخ الاستثناء** باستخدام `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## الخطوة 3: تعريف استثناءات التقويم

فيما يلي شرح كامل يوضح كيفية **إضافة**، **التحقق**، و**إزالة** استثناءات التقويم. لاحظ استخدام `CheckException` لـ **التحقق من تاريخ الاستثناء** لوقت محدد.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## المشكلات الشائعة والنصائح

| المشكلة | السبب | الحل |
|-------|--------|----------|
| **`IndexOutOfRangeException` عند الحذف** | محاولة حذف استثناء غير موجود. | تحقق من أن `calendar.Exceptions.Count` > الفهرس قبل استدعاء `Delete()`. |
| **أوقات عمل غير صحيحة** | عدم تعيين `DayWorking` أو `WorkingTimes` بشكل صحيح. | استخدم `exception.WorkingTimes.Add(new WorkingTime(...))` لتحديد فترات صريحة. |
| **عدم التعرف على الاستثناء** | `CheckException` يُعيد `false` لأن التاريخ يقع خارج النطاق المحدد. | تحقق مرة أخرى من `FromDate`/`ToDate` و`Type` (يومي، أسبوعي، إلخ). |

## الأسئلة المتكررة

**س: هل يمكنني إضافة استثناءات متعددة إلى تقويم واحد؟**  
**ج:** نعم، يمكنك إضافة عدد غير محدود من الاستثناءات لتمثيل العطلات، فترات الصيانة، أو أي قواعد جدولة خاصة.

**س: كيف يمكنني **التحقق من تاريخ الاستثناء** ليوم معين؟**  
**ج:** استخدم طريقة `CheckException(DateTime date)` على كائن `CalendarException`. تُعيد `true` إذا كان التاريخ المحدد يقع ضمن نطاق الاستثناء.

**س: هل يمكن إزالة استثناء موجود من تقويم؟**  
**ج:** بالتأكيد. يمكنك الوصول إلى مجموعة `Exceptions` واستدعاء `Remove()` أو تنفيذ `Delete()` على كائن `CalendarException` المحدد.

**س: ما هي أنواع استثناءات التقويم المدعومة؟**  
**ج:** يدعم Aspose.Tasks أنواع الاستثناء اليومي، الأسبوعي، الشهري، والسنوي، مما يمنحك مرونة لنمذجة أي نمط تكرار تقريبًا.

**س: هل يمكن تخصيص ساعات العمل لتواريخ استثناء معينة؟**  
**ج:** نعم. بعد إنشاء الاستثناء، قم بملء مجموعة `WorkingTimes` بكائنات `WorkingTime` التي تحدد أوقات البدء والانتهاء لهذا اليوم.

## الخاتمة

لقد استعرضنا دورة الحياة الكاملة لعمليات **حذف استثناء التقويم**، من فحص الاستثناءات الموجودة إلى إضافة استثناءات جديدة والتحقق من التواريخ. إتقان هذه التقنيات يضمن أن جداول مشاريعك تحترم التقويمات الواقعية، مما يجعل تنفيذات جدولة التقويم في ASP.NET قوية وموثوقة.

---

**آخر تحديث:** 2026-04-13  
**تم الاختبار مع:** Aspose.Tasks for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}