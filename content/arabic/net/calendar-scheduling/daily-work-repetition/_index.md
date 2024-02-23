---
title: تكرار العمل اليومي في Aspose.Tasks
linktitle: تكرار العمل اليومي في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إنشاء مهام متكررة يومية في ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET. تعزيز الإنتاجية والتنظيم دون عناء.
type: docs
weight: 26
url: /ar/net/calendar-scheduling/daily-work-repetition/
---
## مقدمة

Aspose.Tasks for .NET هي مكتبة قوية تمكن المطورين من التعامل مع ملفات Microsoft Project بسهولة. ومن بين ميزاته التي لا تعد ولا تحصى القدرة على التعامل مع المهام المتكررة بكفاءة. في هذا البرنامج التعليمي، سوف نتعمق في وظيفة تكرار العمل اليومي، والتي تسمح بإنشاء المهام التي تتكرر يوميًا داخل المشروع.

## المتطلبات الأساسية

قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بـ C# و.NET Framework.
- تم تثبيت Visual Studio على نظامك.
-  Aspose.Tasks لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- الإلمام بملفات Microsoft Project (.mpp).

## استيراد مساحات الأسماء

قبل أن نبدأ، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

دعنا نقسم المثال المقدم إلى خطوات متعددة:

## الخطوة 1: تحميل ملف المشروع

 أولاً، قم بتحميل ملف المشروع باستخدام ملف`Project` فصل:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## الخطوة 2: تحديد معلمات المهمة المتكررة

تحديد المعلمات للمهمة المتكررة:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## الخطوة 3: تعيين التقويم وتاريخ بدء المهمة

قم بتعيين التقويم وتاريخ البدء للمهمة:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية استخدام Aspose.Tasks لـ .NET لإنشاء مهام متكررة مع تكرار العمل اليومي. باتباع هذه الخطوات، يمكنك إدارة المهام داخل مشاريعك بكفاءة، مما يضمن سير العمل والتنظيم بسلاسة.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص نمط التكرار بشكل أكبر؟

ج1: نعم، يمكنك ضبط المعلمات مثل تاريخ البدء ورقم التكرار والفاصل الزمني للتكرار لتخصيص نمط التكرار وفقًا لمتطلباتك.

### س2: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من Microsoft Project؟

ج2: نعم، يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، مما يضمن التوافق والتكامل السلس.

### س3: كيف يمكنني معالجة الاستثناءات أو التعديلات على المهام المتكررة؟

ج3: يوفر Aspose.Tasks وظائف قوية لإدارة الاستثناءات والتعديلات ضمن المهام المتكررة، مما يسمح بالمرونة والتخصيص.

### س 4: هل يمكنني تصدير المشروع إلى تنسيقات مختلفة؟

ج4: بالتأكيد، يقدم Aspose.Tasks الدعم لتصدير المشاريع إلى تنسيقات مختلفة بما في ذلك PDF وHTML وXML والمزيد، مما يسهل المشاركة والتعاون بسهولة.

### س5: هل يقدم Aspose.Tasks الدعم الفني؟

ج5: نعم، توفر Aspose.Tasks دعمًا فنيًا شاملاً من خلال المنتدى الخاص بها، حيث يمكنك طلب المساعدة وتبادل الخبرات والتفاعل مع المستخدمين الآخرين.