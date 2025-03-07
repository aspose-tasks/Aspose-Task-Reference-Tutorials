---
title: التكرار حسب الشهر واليوم في Aspose.Tasks
linktitle: التكرار حسب الشهر واليوم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة المهام المتكررة في مشاريع .NET باستخدام Aspose.Tasks. دليل خطوة بخطوة للتعامل مع التكرار حسب الشهر واليوم.
weight: 25
url: /ar/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التكرار حسب الشهر واليوم في Aspose.Tasks

## مقدمة

في مجال تطوير .NET، يمثل Aspose.Tasks أداة قوية لإدارة مهام المشروع وجداوله الزمنية. فهو يوفر عددًا كبيرًا من الوظائف لتبسيط سير عمل إدارة المشروع، بما في ذلك التعامل مع المهام المتكررة. يعد التكرار حسب الشهر واليوم متطلبًا شائعًا في جدولة المشروع، ويوفر Aspose.Tasks دعمًا قويًا لهذا السيناريو.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# ضروري لفهم المفاهيم التي تمت مناقشتها في هذا البرنامج التعليمي.
2. تثبيت Aspose.Tasks لـ .NET: تأكد من تثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
3. بيئة التطوير المتكاملة (IDE): قم بتثبيت بيئة تطوير متكاملة مثل Visual Studio على نظامك لتسهيل عملية البرمجة.

## استيراد مساحات الأسماء

في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

لنقم بتقسيم مثال التعليمات البرمجية المقدم إلى تنسيق دليل خطوة بخطوة:

## الخطوة 1: تحميل ملف المشروع

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 يقوم هذا السطر من التعليمات البرمجية بتهيئة مثيل جديد لـ`Project` فئة، تحميل ملف المشروع المسمى "Project1.mpp".

## الخطوة 2: تحديد معلمات المهمة المتكررة

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

يحدد هذا القسم معلمات المهمة المتكررة، بما في ذلك اسمها ومدتها ونمط التكرار ونطاق التكرار.

## الخطوة 3: إضافة مهمة إلى المشروع

```csharp
project.RootTask.Children.Add(parameters);
```

هنا، نضيف معلمات المهمة المتكررة إلى المشروع.

## الخطوة 4: حفظ ملف المشروع

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

وأخيرًا، يتم حفظ المشروع المعدل مع المهمة المتكررة المضافة.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية التعامل مع التكرار حسب الشهر واليوم في Aspose.Tasks لـ .NET. باتباع الخطوات المتوفرة، يمكنك إدارة المهام المتكررة بكفاءة ضمن جداول مشروعك.

## الأسئلة الشائعة

### س1: هل Aspose.Tasks متوافق مع كافة إصدارات .NET؟

ج1: يدعم Aspose.Tasks إصدارات مختلفة من إطار عمل .NET، مما يضمن التوافق عبر بيئات مختلفة.

### س2: هل يمكنني تخصيص نمط التكرار بشكل أكبر؟

ج2: نعم، يوفر Aspose.Tasks خيارات تخصيص واسعة النطاق لتحديد أنماط التكرار وفقًا لمتطلبات المشروع المحددة.

### س3: هل يوفر Aspose.Tasks الدعم لوظائف إدارة المشروع الأخرى؟

ج3: بالتأكيد، يقدم Aspose.Tasks نطاقًا واسعًا من الميزات لإدارة المشاريع، بما في ذلك تعقب المهام وتخصيص الموارد وإنشاء مخطط جانت.

### س4: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks؟

 ج4: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من[هنا](https://releases.aspose.com/) لاستكشاف إمكانيات Aspose.Tasks قبل اتخاذ قرار الشراء.

### س5: أين يمكنني طلب المساعدة إذا واجهت مشكلات أو كانت لدي استفسارات؟

 ج5: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لطلب الدعم من المجتمع أو فريق Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
