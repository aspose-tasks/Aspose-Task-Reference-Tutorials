---
title: تكرار التقويم اليومي في Aspose.Tasks
linktitle: تكرار التقويم اليومي في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إنشاء مهام متكررة مع تكرار التقويم اليومي في Aspose.Tasks لـ .NET. تعزيز كفاءة إدارة المشروع دون عناء.
type: docs
weight: 25
url: /ar/net/calendar-scheduling/daily-calendar-repetition/
---
## مقدمة

 يوفر Aspose.Tasks for .NET مجموعة قوية من الأدوات لإدارة المهام والمشاريع برمجيًا. إحدى ميزاته البارزة هي القدرة على التعامل مع تكرارات التقويم اليومي بكفاءة. في هذا البرنامج التعليمي، سوف نستكشف كيفية الاستفادة من`DailyCalendarRepetition` الفصل الدراسي جنبًا إلى جنب مع الفصول الأخرى ذات الصلة لإنشاء مهام متكررة مع التكرار اليومي بناءً على تقويم محدد.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:

1.  التثبيت: تأكد من تثبيت Aspose.Tasks لـ .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).

2. استيراد مساحة الاسم: قم باستيراد مساحات الأسماء الضرورية إلى مشروعك:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## الخطوة 1: تهيئة المشروع

أولاً، نحتاج إلى تحميل مشروع موجود أو إنشاء مشروع جديد للعمل معه:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## الخطوة 2: تحديد التقويم

بعد ذلك، نقوم بإنشاء تقويم مدته 24 ساعة ونربطه بالمشروع:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## الخطوة 3: تعيين معلمات المهمة المتكررة

الآن، لنقم بتعيين المعلمات لمهمتنا المتكررة. نحدد اسمها ومدتها ونمط التكرار والمدى:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## الخطوة 4: تعيين التقويم للمهمة

ربط التقويم المحدد بالمهمة:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## الخطوة 5: إضافة مهمة إلى المشروع

أضف المهمة ذات المعلمات المحددة إلى المشروع:

```csharp
project.RootTask.Children.Add(parameters);
```

## الخطوة 6: احفظ المشروع

أخيرًا، احفظ المشروع مع المهمة المتكررة المضافة:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

لقد نجحت الآن في إنشاء مشروع بمهمة متكررة تم تعيينها للتكرار يوميًا استنادًا إلى تقويم على مدار 24 ساعة باستخدام Aspose.Tasks لـ .NET!

## خاتمة

في هذا البرنامج التعليمي، أوضحنا كيفية استخدام Aspose.Tasks لـ .NET للتعامل مع تكرار التقويم اليومي بكفاءة. باتباع هذه الخطوات، يمكنك دمج المهام المتكررة بسلاسة في مشاريعك، مما يعزز الإنتاجية والتنظيم.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص مدة كل تكرار؟

ج1: نعم، يمكنك ضبط مدة كل تكرار وفقًا لمتطلباتك عن طريق تعديل المعلمات الموجودة في الكود.

### س2: هل يمكن تعيين تقويمات مختلفة لمهام مختلفة ضمن نفس المشروع؟

ج2: بالتأكيد، يسمح لك Aspose.Tasks بتعيين تقويمات محددة للمهام الفردية، مما يوفر مرونة في الجدولة.

### س3: هل يدعم Aspose.Tasks أنماط التكرار الأخرى بخلاف الأنماط اليومية؟

ج3: نعم، يوفر Aspose.Tasks نطاقًا واسعًا من أنماط التكرار مثل الأسبوعية والشهرية والسنوية وما إلى ذلك، مما يلبي احتياجات المشروع المتنوعة.

### س4: هل يمكنني تصور المهام المتكررة التي تم إنشاؤها باستخدام Aspose.Tasks؟

ج4: بالتأكيد، يوفر Aspose.Tasks خيارات تمثيل مرئي لمساعدتك في تحليل المهام المتكررة وتعقبها بفعالية.

### س5: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟

 ج5: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/) لاستكشاف ميزاته قبل إجراء عملية الشراء.