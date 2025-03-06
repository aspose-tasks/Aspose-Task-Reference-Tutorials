---
title: إتقان أيام الأسبوع في Aspose.Tasks لـ .NET
linktitle: تحديد أيام الأسبوع في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف قوة تحديد أيام الأسبوع في Aspose.Tasks .NET. اتبع برنامجنا التعليمي المفصل لإدارة تقاويم المشروع بكفاءة، وتخصيص أوقات العمل، والمزيد.
weight: 10
url: /ar/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان أيام الأسبوع في Aspose.Tasks لـ .NET

## مقدمة
إذا كنت تغوص في عالم إدارة المشاريع باستخدام Aspose.Tasks لـ .NET، فإن فهم أيام الأسبوع ومعالجتها يعد جانبًا بالغ الأهمية. يمكن أن تؤثر إدارة أيام الأسبوع وتخصيصها بكفاءة ضمن تقويم مشروعك بشكل كبير على الجداول الزمنية للمشروع. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحديد أيام الأسبوع باستخدام Aspose.Tasks، وسنقدم لك إرشادات وأمثلة خطوة بخطوة للحصول على وضوح أفضل.
## المتطلبات الأساسية
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي للغة البرمجة C#.
-  تم تثبيت Aspose.Tasks لمكتبة .NET. إذا لم يكن الأمر كذلك، قم بتنزيله من[هنا](https://releases.aspose.com/tasks/net/).
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروعك:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. تحقق من المساواة خلال أيام الأسبوع
```csharp
// دليل المستندات الخاص بك
String DataDir = "Your Document Directory";
// تحميل ملف المشروع
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// الوصول خلال أيام الأسبوع
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// التحقق من المساواة على أساس خصائص مختلفة
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// قم بإضافة بيانات إخراج مماثلة لـ DayWorking، وFromDate، وToDate، وWorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. استنساخ أحد أيام الأسبوع
```csharp
// تحميل ملف المشروع
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// إنشاء نسخة عميقة من أيام الأسبوع
var weekDay2 = weekDay1.Clone();
// خصائص الإخراج لكلا أيام الأسبوع
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// قم بإضافة بيانات إخراج مماثلة لـ DayWorking، وFromDate، وToDate، وWorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. احصل على رمز التجزئة ليوم من أيام الأسبوع
```csharp
// تحميل ملف المشروع
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// خصائص الإخراج لكلا أيام الأسبوع
// قم بإضافة بيانات إخراج مماثلة لـ DayWorking، وFromDate، وToDate، وWorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. قم بإنشاء تقويم جديد مع أيام الأسبوع المحددة
```csharp
// إنشاء مشروع جديد
var project = new Project();
// تحديد التقويم
var calendar = project.Calendars.Add("Calendar1");
// أضف أيام العمل ويوم الاستثناء
// قم بإضافة عبارات إخراج مشابهة لـ FromDate وToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// تحديد أوقات العمل ليوم الجمعة
// قم بإضافة بيانات إخراج مماثلة لـ DayWorking، وFromDate، وToDate، وWorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. قم بتعيين وقت العمل الافتراضي ليوم واحد
```csharp
// إنشاء مشروع جديد
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// أضف أوقات العمل الافتراضية من الاثنين إلى الجمعة
// قم بإضافة بيانات إخراج مماثلة لـ DayWorking، وFromDate، وToDate، وWorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// كرر ذلك أيام الثلاثاء والأربعاء والخميس والجمعة
// تحديد أيام عدم العمل ليومي السبت والأحد
// قم بإضافة بيانات إخراج مماثلة لـ DayWorking، وFromDate، وToDate، وWorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية الجوانب الأساسية لتحديد أيام الأسبوع في Aspose.Tasks لـ .NET. يعد التعامل مع أيام الأسبوع مهارة أساسية لإدارة المشاريع بشكل فعال. قم بتجربة الأمثلة المقدمة، وقم بتخصيصها بما يتناسب مع احتياجات مشروعك، واطلق العنان للإمكانات الكاملة لـ Aspose.Tasks.
## الأسئلة الشائعة
### هل يمكنني تحديد أوقات عمل مخصصة لكل يوم؟
نعم، يمكنك تعيين أوقات عمل مخصصة لأيام محددة من الأسبوع باستخدام الأمثلة المقدمة.
### هل من الممكن إضافة أيام استثناء متعددة إلى التقويم؟
قطعاً. قم بتعديل التعليمات البرمجية في المثال الرابع لتضمين أيام استثناء إضافية.
### كيف يمكنني إزالة يوم محدد من أيام الأسبوع من التقويم؟
استخدم الطرق المناسبة التي توفرها مكتبة Aspose.Tasks لإزالة أيام الأسبوع حسب الحاجة.
### هل التغييرات التي تم إجراؤها على أيام الأسبوع ثابتة في ملف المشروع؟
نعم، أي تعديلات على أيام الأسبوع تنعكس في ملف المشروع عند حفظه.
### هل يمكنني استخدام Aspose.Tasks مع لغات البرمجة الأخرى؟
يدعم Aspose.Tasks العديد من لغات البرمجة، ولكن الأمثلة الواردة هنا مخصصة خصيصًا لـ .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
