---
title: إتقان أوقات العمل في Aspose.Tasks
linktitle: مجموعة من أوقات العمل في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف قوة Aspose.Tasks لـ .NET في إدارة الجداول الزمنية للمشروع بكفاءة. قم بتخصيص التقويمات وضبط أوقات العمل وتبسيط مشاريعك بسهولة.
weight: 14
url: /ar/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان أوقات العمل في Aspose.Tasks

## مقدمة
هل تتطلع إلى إتقان فن إدارة أوقات العمل في Aspose.Tasks لـ .NET؟ لا مزيد من البحث! في هذا الدليل التفصيلي، سنتعمق في تعقيدات جمع وقت العمل باستخدام Aspose.Tasks، مما يمكّنك من التعامل بكفاءة مع التقويمات المخصصة وتبسيط الجداول الزمنية لمشروعك.
## المتطلبات الأساسية
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[صفحة إصدار Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- بيئة العمل: قم بإعداد بيئة تطوير مناسبة، ويفضل استخدام IDE متوافق مع .NET.
## استيراد مساحات الأسماء
في مشروعك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
الآن، دعونا نقسم البرنامج التعليمي إلى خطوات متعددة، مما يضمن تجربة تعليمية سلسة.
## الخطوة 1: إنشاء تقويم مخصص
ابدأ بإنشاء مشروع جديد وإضافة تقويم مخصص إليه:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## الخطوة 2: تحديد أيام العمل
قم بإعداد أيام العمل الافتراضية من الاثنين إلى الجمعة:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## الخطوة 3: تكوين أوقات العمل يوم السبت
تحديد أوقات العمل ليوم السبت:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## الخطوة 4: طباعة فترات العمل يوم السبت
اطبع أوقات العمل المكوّنة ليوم السبت:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## الخطوة 5: تكوين أوقات العمل يوم الأحد
تحديد أوقات العمل ليوم الأحد:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## الخطوة 6: طباعة فترات العمل يوم الأحد
اطبع أوقات العمل المكوّنة ليوم الأحد:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## الخطوة 7: إضافة أيام مخصصة إلى التقويم
قم بتضمين يومي السبت والأحد اللذين تم تكوينهما في التقويم:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## الخطوة 8: اجتياز أوقات العمل
اجتياز أوقات العمل وعرضها لكل يوم في التقويم:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
الآن بعد أن استعرضت الخطوات بنجاح، أصبحت جاهزًا لتسخير قوة Aspose.Tasks لـ .NET في إدارة أوقات العمل بفعالية.
## خاتمة
إن إتقان مجموعة أوقات العمل في Aspose.Tasks يمكّنك من تخصيص تقويمات المشروع، مما يضمن جدولة دقيقة واستخدام الموارد بكفاءة. انغمس في مشاريعك بثقة، متسلحًا بالمعرفة المكتسبة من هذا الدليل الشامل.
## أسئلة مكررة
### هل Aspose.Tasks مناسب لإدارة المشاريع واسعة النطاق؟
نعم، تم تصميم Aspose.Tasks للتعامل مع المشاريع ذات الأحجام المختلفة، وتوفير ميزات قوية لإدارة المشاريع بكفاءة.
### هل يمكنني دمج Aspose.Tasks مع مكتبات .NET الأخرى؟
بالتأكيد! يتكامل Aspose.Tasks بسلاسة مع مكتبات .NET الأخرى، مما يعزز تعدد استخداماتها وتوافقها.
### كم مرة يتم تحديث Aspose.Tasks؟
 يتم تحديث Aspose.Tasks بانتظام لدمج الميزات الجديدة والتحسينات وتحسينات التوافق. افحص ال[صفحة الإصدار](https://releases.aspose.com/tasks/net/) للحصول على آخر التحديثات.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 نعم، يمكنك استكشاف Aspose.Tasks من خلال النسخة التجريبية المجانية من خلال زيارة الموقع[هذا الرابط](https://releases.aspose.com/).
### أين يمكنني طلب الدعم لـ Aspose.Tasks؟
 لأية استفسارات أو مساعدة، قم بزيارة[منتدى دعم Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
