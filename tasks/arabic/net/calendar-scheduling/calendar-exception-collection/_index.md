---
title: مجموعة من استثناءات التقويم في Aspose.Tasks
linktitle: مجموعة من استثناءات التقويم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل بكفاءة مع استثناءات التقويم في مشاريع .NET الخاصة بك باستخدام Aspose.Tasks، مما يضمن جدولة دقيقة وإدارة الموارد.
weight: 13
url: /ar/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# مجموعة من استثناءات التقويم في Aspose.Tasks

## مقدمة

في إدارة المشاريع، تعد الجدولة الدقيقة أمرًا حيويًا لتحقيق النجاح. ومع ذلك، غالبًا ما تتطلب سيناريوهات العالم الحقيقي انحرافات عن الجداول القياسية بسبب العطلات أو المناسبات الخاصة أو عوامل أخرى. يوفر Aspose.Tasks for .NET حلاً قويًا لإدارة مثل هذه الاستثناءات من خلال ميزة مجموعة استثناءات التقويم الخاصة به. سيرشدك هذا البرنامج التعليمي خلال عملية استخدام هذه الوظيفة خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1.  Aspose.Tasks لـ .NET: تأكد من تثبيت المكتبة. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
2. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا في فهم الأمثلة.
3. بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك، مثل Visual Studio أو JetBrains Rider.

## استيراد مساحات الأسماء

قبل أن تبدأ العمل مع Aspose.Tasks لـ .NET، تحتاج إلى استيراد مساحات الأسماء المطلوبة إلى مشروعك. تمكنك هذه الخطوة من الوصول إلى الفئات والأساليب اللازمة لإدارة استثناءات التقويم.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة:

## الخطوة 1: تحميل المشروع واسترداد التقويم

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

في هذه الخطوة، نقوم بتحميل ملف المشروع واسترجاع التقويم المطلوب بواسطة UID الخاص به.

## الخطوة 2: مسح الاستثناءات الموجودة وتعيين التقويم القياسي

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

تقوم هذه الخطوة بمسح أي استثناءات موجودة من التقويم وتعيينه على تكوين قياسي.

## الخطوة 3: تحديد وإضافة استثناء وقت العمل

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

تحدد هذه الخطوة استثناء وقت العمل بتواريخ بدء وانتهاء محددة، بالإضافة إلى أوقات العمل ضمن تلك التواريخ، وتضيفه إلى التقويم.

## الخطوة 4: تحديد وإضافة استثناءات وقت غير العمل

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// أضف المزيد من الاستثناءات إذا لزم الأمر

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

تحدد هذه الخطوة استثناءات أوقات غير أوقات العمل، مثل أيام العطل، وتضيفها إلى التقويم.

## الخطوة 5: عرض استثناءات التقويم

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

تعرض هذه الخطوة استثناءات التقويم المضافة مع تفاصيلها.

## الخطوة 6: إزالة كافة الاستثناءات

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

وأخيرًا، تقوم هذه الخطوة بإزالة كافة الاستثناءات من التقويم.

## خاتمة

تعد إدارة استثناءات التقويم أمرًا بالغ الأهمية لجدولة المشروع بدقة. يعمل Aspose.Tasks for .NET على تبسيط هذه المهمة من خلال توفير مجموعة شاملة من الميزات، بما في ذلك مجموعة استثناءات التقويم. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التعامل بكفاءة مع سيناريوهات الجدولة المختلفة داخل مشاريعك.

## الأسئلة الشائعة

### س1: هل يمكنني إضافة استثناءات متعددة إلى تقويم واحد؟

 ج1: نعم، يمكنك إضافة استثناءات متعددة إلى تقويم باستخدام الخيار`AddRange` طريقة.

### س2: كيف يمكنني التعامل مع الاستثناءات المتكررة، مثل العطلات الأسبوعية؟

ج٢: يمكنك حساب الاستثناءات المتكررة برمجيًا وإضافتها إلى التقويم باستخدام المنطق المخصص.

### س3: هل من الممكن استيراد استثناءات التقويم من مصادر خارجية؟

ج3: نعم، يمكنك قراءة استثناءات التقويم من مصادر خارجية مثل قواعد البيانات أو ملفات CSV ودمجها في مشروعك.

### س 4: ماذا يحدث إذا كانت هناك استثناءات متداخلة في التقويم؟

ج4: يسمح لك Aspose.Tasks for .NET بمعالجة الاستثناءات المتداخلة عن طريق تحديد الأولويات أو حل التعارضات بناءً على متطلبات مشروعك.

### س5: هل يمكنني تخصيص أوقات العمل لكل يوم ضمن استثناء؟

ج5: نعم، يمكنك تحديد أوقات عمل مخصصة للأيام الفردية ضمن استثناء لتلبية احتياجات الجدولة المحددة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
