---
title: فترات زمنية متكررة لمشروع MS بدون جهد في Aspose.Tasks
linktitle: إدارة الفواصل الزمنية المتكررة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف كيفية إدارة الفواصل الزمنية المتكررة بسهولة في MS Project باستخدام Aspose.Tasks لـ .NET.
weight: 12
url: /ar/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# فترات زمنية متكررة لمشروع MS بدون جهد في Aspose.Tasks

## مقدمة
هل تتطلع إلى إدارة الفواصل الزمنية المتكررة بكفاءة في ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET؟ سيرشدك هذا البرنامج التعليمي الشامل خلال العملية خطوة بخطوة، مما يضمن أنه يمكنك التعامل بسهولة مع الفواصل الزمنية المتكررة في مشاريعك. قبل الغوص في البرنامج التعليمي، دعنا نراجع بعض المتطلبات الأساسية للتأكد من أنك مستعد للبدء.
## المتطلبات الأساسية
قبل متابعة هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. معرفة برمجة C#: مطلوب فهم أساسي للغة برمجة C# وتركيبها.
2. تثبيت Visual Studio: تأكد من تثبيت Visual Studio على نظامك لترميز وتجميع تطبيقات .NET.
3. Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/tasks/net/).

## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي توفرها Aspose.Tasks لمكتبة .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة ونشرحها بالتفصيل.
## الخطوة 1: تهيئة كائن المشروع:
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 هنا، نقوم بتهيئة نسخة جديدة من`Project` فئة عن طريق توفير المسار إلى ملف Microsoft Project.
## الخطوة 2: تعيين تاريخ الحالة:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
تقوم هذه الخطوة بتعيين تاريخ حالة المشروع إلى تاريخ بدايته.
## الخطوة 3: الوصول إلى عرض مخطط جانت:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
يمكننا الوصول إلى عرض مخطط جانت للمشروع.
## الخطوة 4: قراءة خط التقدم:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
تقوم هذه الخطوة باسترداد الفاصل الزمني المتكرر لخطوط التقدم من طريقة عرض مخطط جانت.
## الخطوة 5: عرض معلومات الفاصل الزمني:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
نعرض هنا معلومات حول الفاصل الزمني ورقم الأسبوع الأسبوعي والأيام الأسبوعية.
## الخطوة 6: إعادة تعريف الفاصل الزمني المتكرر:
```csharp
var newInterval = new RecurringInterval();
```
 نقوم بإنشاء مثيل جديد لـ`RecurringInterval` لإعادة تعريف الفاصل الزمني المتكرر.
## الخطوة 7: تحديد خطوط التقدم الشهرية:
```csharp
// تحديد خطوط التقدم الشهرية حسب اليوم.
interval.MonthlyDay = true;
// قم بتعيين عدد اليوم لخطوط التقدم الشهرية.
interval.MonthlyDayDayNumber = 1;
// قم بتعيين عدد الشهر لخطوط التقدم الشهرية.
interval.MonthlyDayMonthNumber = 1;
// قم بتعيين خطوط التقدم حسب اليوم الأول أو الأخير المحدد مسبقًا.
interval.MonthlyFirstLast = true;
// قم بتعيين نوع اليوم الأول أو الأخير من خطوط التقدم الشهرية.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// قم بتعيين عدد الشهر لخطوط التقدم.
interval.MonthlyFirstLastMonthNumber = 1;
```
تقوم هذه الخطوات بتكوين خطوط التقدم الشهرية وفقًا للمعلمات المحددة.
## الخطوة 8: تحديث خطوط التقدم:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
نقوم بتحديث خطوط التقدم في عرض مخطط جانت بالفاصل الزمني المتكرر المحدد حديثًا.
## الخطوة 9: حفظ المشروع بصيغة PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
وأخيرًا، نقوم بحفظ المشروع بالفاصل الزمني المتكرر المحدث كملف PDF.

## خاتمة
في الختام، أصبحت إدارة الفواصل الزمنية المتكررة في ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET أمرًا بسيطًا بفضل الوظائف الشاملة التي توفرها المكتبة. باتباع الدليل التفصيلي الموضح في هذا البرنامج التعليمي، يمكنك التعامل بكفاءة مع الفواصل الزمنية المتكررة في مشاريعك، مما يعزز الإنتاجية والتنظيم.
### الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ .NET مع لغات البرمجة الأخرى؟
نعم، يمكن استخدام Aspose.Tasks لـ .NET مع أي لغة مدعومة لـ .NET مثل C# وVB.NET.
### هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟
 يمكنك الحصول على الدعم من منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ .NET؟
 نعم، يمكنك شراء ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الكاملة لـ Aspose.Tasks لـ .NET؟
 يمكن العثور على الوثائق الكاملة[هنا](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
