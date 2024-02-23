---
title: إدارة مجموعة التقويم في Aspose.Tasks
linktitle: إدارة مجموعة التقويم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة مجموعات التقويم في Aspose.Tasks لـ .NET بكفاءة. قم بإنشاء التقويمات وتعديلها ومعالجتها بسهولة.
type: docs
weight: 11
url: /ar/net/calendar-scheduling/calendar-collection/
---
## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة مجموعات التقويم في Aspose.Tasks لـ .NET. تلعب التقويمات دورًا حاسمًا في إدارة المشاريع، وتحديد أيام العمل والعطلات والاستثناءات. يوفر Aspose.Tasks وظائف قوية للتعامل مع التقويمات داخل مشاريعك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة لتطوير .NET.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية للعمل مع Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## إنشاء تقويم جديد

###  الخطوة 1: تهيئة ملف جديد`Project` object.
```csharp
var project = new Project();
```

### الخطوة 2: إضافة التقويمات إلى مجموعة تقويم المشروع.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### الخطوة 3: قم بالتكرار خلال التقويمات وعرض أسمائهم.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## استبدال التقويم بتقويم جديد

### الخطوة 1: تحميل مشروع موجود.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### الخطوة 2: إزالة التقويم الموجود (إن وجد).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### الخطوة 3: إضافة تقويم جديد.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## الحصول على التقويم بالاسم أو المعرف

### الخطوة 1: تحميل المشروع.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### الخطوة 2: استرداد التقويمات بالاسم أو UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### الخطوة 3: عرض تفاصيل التقويم.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## التكرار على التقاويم

### الخطوة 1: تحميل المشروع.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### الخطوة 2: استرداد عدد التقويمات.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### الخطوة 3: التكرار على مجموعة التقويم وأسماء العرض.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## عمل تقويم قياسي

### الخطوة 1: تهيئة مشروع جديد.
```csharp
var project = new Project();
```

### الخطوة 2: تحديد تقويم جديد وجعله قياسيًا.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### الخطوة 3: احفظ المشروع.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## خاتمة

تعد إدارة مجموعات التقويم في Aspose.Tasks لـ .NET أمرًا ضروريًا لإدارة المشروعات بشكل فعال. باستخدام الوظائف المتوفرة، يمكنك إنشاء التقويمات وتعديلها ومعالجتها بكفاءة وفقًا لمتطلبات مشروعك.

## الأسئلة الشائعة

### س1: هل يمكنني إنشاء أيام عمل مخصصة في Aspose.Tasks؟

A1: نعم، يمكنك إنشاء أيام عمل مخصصة عن طريق إضافة استثناءات إلى التقويمات.

### س2: هل من الممكن استيراد التقويمات من ملفات Microsoft Project؟

ج2: بالتأكيد، يدعم Aspose.Tasks استيراد التقويمات من ملفات Microsoft Project.

### س3: كيف يمكنني إزالة تقويم معين من المشروع؟

ج3: يمكنك إزالة تقويم عن طريق الحصول عليه من المجموعة ثم الاتصال بـ`Remove` طريقة.

### س 4: هل يدعم Aspose.Tasks تصدير التقويمات إلى تنسيقات مختلفة؟

ج4: نعم، يسمح Aspose.Tasks بتصدير التقويمات إلى تنسيقات مختلفة مثل XML وMPP وما إلى ذلك.

### س5: هل يمكنني تخصيص ساعات العمل لأيام محددة في التقويم؟

ج5: بالتأكيد، يمكنك تحديد ساعات العمل للأيام الفردية باستخدام الاستثناءات في التقويم.