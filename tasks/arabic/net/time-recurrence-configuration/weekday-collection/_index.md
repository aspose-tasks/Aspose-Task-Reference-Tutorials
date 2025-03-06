---
title: إتقان أيام الأسبوع في Aspose.Tasks
linktitle: مجموعة من أيام الأسبوع في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف قوة Aspose.Tasks لـ .NET في إدارة أيام الأسبوع دون عناء. قم بتخصيص أيام العمل وإزالة عطلات نهاية الأسبوع وإنشاء تقويمات متخصصة بسهولة.
weight: 11
url: /ar/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان أيام الأسبوع في Aspose.Tasks

## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تسهل المعالجة الفعالة لبيانات إدارة المشروع. في هذا البرنامج التعليمي، سوف نستكشف مجموعة أيام الأسبوع في Aspose.Tasks، مما يتيح لك تخصيص أيام العمل، وإزالة عطلات نهاية الأسبوع، وإنشاء تقويمات متخصصة لتلبية متطلبات مشروعك. سواء كنت مطورًا متمرسًا أو وافدًا جديدًا، سيرشدك هذا الدليل خطوة بخطوة خلال عملية العمل مع أيام الأسبوع في Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  قم بتثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[صفحة تنزيل Aspose.Tasks لـ .NET](https://releases.aspose.com/tasks/net/).
- الإلمام بلغة البرمجة C#.
- بيئة التطوير المتكاملة (IDE) مثل Visual Studio.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## الخطوة 1: إنشاء مثيل المشروع
تهيئة مشروع Aspose.Tasks جديد:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## الخطوة 2: الوصول إلى التقويم
استرداد تقويم المشروع:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## الخطوة 3: تخصيص أيام الأسبوع
مسح أيام الأسبوع الحالية وتعيين أيام العمل الافتراضية:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// أضف أيام الأسبوع الأخرى بالمثل ...
```
## الخطوة 4: إضافة أوقات العمل
إضافة أوقات العمل لأيام محددة من الأسبوع:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## الخطوة 5: عرض معلومات التقويم
تفاصيل تقويم الإخراج إلى وحدة التحكم:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// عرض كل أيام الأسبوع وأوقات العمل...
```
## الخطوة 6: إزالة عطلات نهاية الأسبوع
إزالة يومي السبت والأحد من أيام الأسبوع:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## الخطوة 7: عرض أوقات العمل المحدثة
إخراج أوقات العمل المحدثة بعد إزالة عطلات نهاية الأسبوع:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// عرض كل أيام الأسبوع وأوقات العمل المحدثة...
```
## الخطوة 8: إنشاء تقويم على مدار 24 ساعة
أنشئ تقويمًا على مدار 24 ساعة وانسخ أيام الأسبوع:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا الإمكانات القوية لـ Aspose.Tasks لـ .NET في إدارة أيام الأسبوع ضمن تقويمات المشروع. بدءًا من تخصيص أيام العمل إلى إنشاء تقويمات متخصصة على مدار 24 ساعة، يعمل Aspose.Tasks على تبسيط العملية، مما يوفر المرونة والتحكم في إدارة المشروع.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع لغات البرمجة الأخرى؟
ج: يدعم Aspose.Tasks بشكل أساسي لغات .NET، ولكنه يوفر أيضًا إصدارات لـ Java.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[صفحة إصدارات Aspose.Tasks](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟
 ج: قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع أو فكر في شراء خطة دعم.
### س: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks لـ .NET؟
 ج: راجع[Aspose.Tasks لوثائق .NET](https://reference.aspose.com/tasks/net/) للحصول على معلومات مفصلة.
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ .NET؟
 ج: يمكنك الحصول على ترخيص مؤقت من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
