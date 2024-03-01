---
title: تعيين معلمات المهام المتكررة في Aspose.Tasks
linktitle: تعيين معلمات المهام المتكررة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تعيين معلمات المهام المتكررة في Microsoft Project باستخدام Aspose.Tasks لـ .NET. برنامج تعليمي شامل مع دليل خطوة بخطوة.
type: docs
weight: 14
url: /ar/net/rate-recurring-tasks/recurring-task-parameters/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إعداد معلمات المهام المتكررة لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. الفهم الأساسي للغة البرمجة C#.
2. تثبيت Visual Studio أو أي C# IDE آخر.
3. تم تثبيت Aspose.Tasks لمكتبة .NET والإشارة إليها في مشروعك.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
using Aspose.Tasks;
using System;

```
## الخطوة 1: تحديد دليل المستندات
```csharp
String DataDir = "Your Document Directory";
```
 يستبدل`"Your Document Directory"` مع المسار إلى دليل المستندات الخاص بك.
## الخطوة 2: تحميل ملف المشروع
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 يقوم هذا السطر من التعليمات البرمجية بتحميل ملف Microsoft Project في ملف`project` عامل.
## الخطوة 3: تحديد معلمات المهمة المتكررة
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
هنا، يمكنك تحديد معلمات المهمة المتكررة مثل اسم المهمة، والمدة، ونمط التكرار، ونطاق التكرار، وما إذا كان سيتم تجاهل تقويم المورد.
## الخطوة 4: تعيين التقويم للمهمة المتكررة
```csharp
parameters.SetCalendar(project, "Standard");
```
تقوم هذه الخطوة بتعيين التقويم للمهمة المتكررة. في هذا المثال، يقوم بتعيين التقويم إلى "قياسي".
## الخطوة 5: إضافة المعلمات إلى المشروع
```csharp
project.RootTask.Children.Add(parameters);
```
وأخيرًا، قم بإضافة المعلمات إلى المهمة الجذرية للمشروع.

## خاتمة
لقد أوضحنا في هذا البرنامج التعليمي كيفية تعيين معلمات المهام المتكررة لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك إدارة المهام المتكررة في مشاريعك بكفاءة.
## الأسئلة الشائعة
### هل يمكنني تخصيص نمط التكرار بشكل أكبر؟
نعم، يوفر Aspose.Tasks أنماط وخيارات تكرارية متنوعة للتخصيص وفقًا لمتطلبات مشروعك.
### هل هناك نسخة تجريبية متاحة قبل الشراء؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks[موقع إلكتروني](https://purchase.aspose.com/buy) لتقييم مميزات المكتبة.
### هل يدعم Aspose.Tasks تنسيقات ملفات المشروع الأخرى؟
نعم، يدعم Aspose.Tasks العديد من تنسيقات ملفات المشروع بما في ذلك MPP وXML وXLSX والمزيد.
### هل يمكنني الحصول على الدعم إذا واجهت أي مشاكل أثناء التنفيذ؟
نعم، يمكنك زيارة منتدى Aspose.Tasks للحصول على المساعدة من المجتمع أو الاتصال بالدعم للحصول على مساعدة مباشرة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟
 يمكنك الحصول على ترخيص مؤقت من[موقع إلكتروني](https://purchase.aspose.com/temporary-license/) لأغراض تجريبية.