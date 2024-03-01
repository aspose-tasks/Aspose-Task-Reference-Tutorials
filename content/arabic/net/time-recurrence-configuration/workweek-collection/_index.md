---
title: تخصيص أسابيع العمل في Aspose.Tasks
linktitle: مجموعة من أسابيع العمل في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تخصيص أسابيع العمل في Aspose.Tasks لـ .NET. دليل خطوة بخطوة لإنشاء تقاويم المشروع المخصصة. التحميل الان!
type: docs
weight: 17
url: /ar/net/time-recurrence-configuration/workweek-collection/
---
## مقدمة
مرحبًا بك في برنامجنا التعليمي حول إنشاء أسبوع عمل مخصص باستخدام Aspose.Tasks لـ .NET! في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية تحديد أسبوع عمل مخصص لتقويم في مشروعك. Aspose.Tasks هي مكتبة قوية تمكن المطورين من العمل بكفاءة مع مستندات Microsoft Project في تطبيقات .NET الخاصة بهم.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Visual Studio: تأكد من تثبيت Visual Studio على جهازك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Tasks. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## الخطوة 1: إنشاء المشروع والتقويم
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## الخطوة 2: تحديد أسبوع عمل مخصص
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## الخطوة 3: تحديد أيام العمل
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## الخطوة 4: عرض معلومات أسابيع العمل
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
يمكّنك هذا الدليل الشامل من إنشاء أسابيع عمل مخصصة وإدارتها بكفاءة باستخدام Aspose.Tasks لـ .NET.
## خاتمة
في الختام، يوفر Aspose.Tasks for .NET حلاً قويًا للتعامل مع تقويمات المشروع مع أسابيع العمل المخصصة. باتباع هذا البرنامج التعليمي، تعلمت كيفية إنشاء وعرض معلومات حول أسابيع العمل المخصصة في مشروعك.
## الأسئلة الشائعة
### هل يمكنني الحصول على عدة أسابيع عمل مخصصة في مشروع واحد؟
نعم، يمكنك إضافة عدة أسابيع عمل مخصصة إلى تقويم المشروع.
### كيف يمكنني تعديل أسابيع العمل الحالية؟
 استخدم المقدمة`WorkWeek`خصائص وطرق تعديل أسابيع العمل الحالية.
### هل Aspose.Tasks متوافق مع .NET Core؟
نعم، Aspose.Tasks يدعم .NET Core.
### هل يمكنني تصدير المشروع بأسابيع عمل مخصصة إلى تنسيق ملف Microsoft Project؟
بالتأكيد، يتيح لك Aspose.Tasks حفظ مشروعك بتنسيقات مختلفة، بما في ذلك Microsoft Project.
### أين يمكنني طلب الدعم للاستفسارات المتعلقة بـ Aspose.Tasks؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) عن أي دعم أو مساعدة.