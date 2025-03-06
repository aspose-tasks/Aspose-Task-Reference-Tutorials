---
title: التعامل مع أنماط التكرار الشهرية في Aspose.Tasks
linktitle: التعامل مع أنماط التكرار الشهرية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع أنماط التكرار الشهرية في Aspose.Tasks لـ .NET باستخدام هذا البرنامج التعليمي خطوة بخطوة.
weight: 18
url: /ar/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التعامل مع أنماط التكرار الشهرية في Aspose.Tasks

## مقدمة

Aspose.Tasks for .NET عبارة عن واجهة برمجة تطبيقات قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجيًا. إحدى الوظائف الأساسية التي تقدمها هي القدرة على التعامل مع المهام المتكررة بكفاءة. في هذا البرنامج التعليمي، سوف نتعمق في كيفية التعامل مع أنماط التكرار الشهرية باستخدام Aspose.Tasks، خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت المتطلبات الأساسية التالية:

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

الآن، دعونا نقسم عملية التعامل مع أنماط التكرار الشهرية إلى خطوات متعددة:

## الخطوة 1: تهيئة المشروع

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## الخطوة 2: تعيين معلمات المهمة المتكررة

حدد معلمات المهمة المتكررة، بما في ذلك اسم المهمة ومدتها ونمط التكرار:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## الخطوة 3: إضافة المعلمات إلى المشروع

```csharp
project.RootTask.Children.Add(parameters);
```

## الخطوة 4: احفظ المشروع

احفظ المشروع المعدل بالمهمة المتكررة:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## خاتمة

تعتبر معالجة أنماط التكرار الشهرية في Aspose.Tasks لـ .NET أمرًا مباشرًا وفعالاً. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إنشاء مهام متكررة بفواصل شهرية محددة ونطاقات تكرار.

## الأسئلة الشائعة

### س1: هل Aspose.Tasks متوافق مع كافة إصدارات ملفات Microsoft Project؟

A1: يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك MPP وMPT وXML وMPX.

### س2: هل يمكنني تخصيص نمط التكرار بشكل أكبر؟

ج2: نعم، يوفر Aspose.Tasks خيارات شاملة لتخصيص أنماط التكرار، بما في ذلك اليومية والأسبوعية والشهرية والسنوية.

### س3: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟

 ج3: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من موقع الويب[هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على دعم Aspose.Tasks؟

 ج4: يمكنك طلب المساعدة والمشاركة في المناقشات حول[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).

### س5: أين يمكنني شراء ترخيص Aspose.Tasks؟

 ج5: يمكنك شراء ترخيص Aspose.Tasks من موقع الويب[هنا](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
