---
title: تكوين أوقات العمل في Aspose.Tasks
linktitle: تكوين أوقات العمل في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تحسين جدولة المشروع في .NET باستخدام Aspose.Tasks. قم بتكوين أوقات العمل دون عناء لإدارة الموارد بدقة. قم بتنزيل المكتبة الآن!
type: docs
weight: 13
url: /ar/net/time-recurrence-configuration/working-times/
---
## مقدمة
في إدارة المشاريع، يعد التحكم الدقيق في أوقات العمل أمرًا بالغ الأهمية للجدولة الدقيقة وتخصيص الموارد. يوفر Aspose.Tasks for .NET حلاً قويًا للتعامل مع معلومات وقت العمل ضمن مشاريعك. سيرشدك هذا البرنامج التعليمي خلال عملية تكوين أوقات العمل باستخدام Aspose.Tasks في بيئة .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- الفهم الأساسي للغة البرمجة C#.
-  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- إعداد Visual Studio أو أي بيئة تطوير مفضلة لـ C#.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## الخطوة 1: إنشاء التقويم
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
هنا، نبدأ مشروعًا جديدًا وننشئ تقويمًا باسم "MyCalendar" استنادًا إلى التقويم القياسي. سيتم استخدام هذا التقويم لتحديد أوقات عمل محددة.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## الخطوة 2: عرض معلومات أسبوع العمل
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
تقوم هذه الخطوة بطباعة إجمالي عدد أيام العمل في التقويم المحدد.
## الخطوة 3: تفاصيل أوقات العمل
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
في هذا الجزء، نقوم بالتكرار خلال كل يوم من أيام الأسبوع، وطباعة نوع اليوم وأوقات العمل المرتبطة به. يمكنك تخصيص أوقات العمل لكل يوم من أيام الأسبوع وفقًا لمتطلبات مشروعك.
## خاتمة
يضمن تكوين أوقات العمل بشكل فعال في Aspose.Tasks لـ .NET التخطيط الدقيق للمشروع وإدارة الموارد. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك دمج تعديلات وقت العمل بسلاسة في سير عمل مشروعك.
## أسئلة مكررة
### هل Aspose.Tasks مناسب لإدارة المشاريع واسعة النطاق؟
نعم، تم تصميم Aspose.Tasks للتعامل مع المشاريع ذات الأحجام المختلفة، وتقديم ميزات قوية لإدارة المشاريع بكفاءة.
### هل يمكنني تحديد أوقات عمل مختلفة لأعضاء الفريق المختلفين؟
قطعاً. يمكنك تخصيص أوقات العمل على أساس كل مورد، مما يسمح بجداول زمنية فردية.
### هل يدعم Aspose.Tasks التكامل مع أدوات إدارة المشاريع الأخرى؟
نعم، Aspose.Tasks يسهل التكامل مع أدوات إدارة المشاريع المختلفة، مما يعزز إمكانية التشغيل البيني.
### هل من الممكن استيراد/تصدير بيانات المشروع بتنسيقات مختلفة؟
يدعم Aspose.Tasks تنسيقات ملفات متعددة، مما يتيح عمليات الاستيراد/التصدير السلسة لبيانات المشروع.
### ما مدى تكرار إصدار تحديثات Aspose.Tasks؟
يتم إصدار التحديثات بانتظام لضمان التوافق مع أحدث التقنيات ومعالجة تعليقات المستخدمين.