---
title: التكرار حسب الشهر، الأسبوع، اليوم في Aspose.Tasks
linktitle: التكرار حسب الشهر، الأسبوع، اليوم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إعداد عمليات التكرار حسب الشهر والأسبوع واليوم في Aspose.Tasks لـ .NET لأتمتة المهام المتكررة بكفاءة.
type: docs
weight: 26
url: /ar/net/advanced-features/repetition-by-month-week-day/
---
## مقدمة

في مجال تطوير البرمجيات، وخاصة في تطبيقات إدارة المشاريع، تعد القدرة على التعامل مع المهام المتكررة بكفاءة أمرًا بالغ الأهمية. Aspose.Tasks for .NET هي مكتبة قوية مصممة لتبسيط إنشاء وإدارة مهام المشروع، بما في ذلك المهام المتكررة. إحدى هذه الوظائف التي توفرها Aspose.Tasks هي القدرة على إعداد عمليات التكرار حسب الشهر والأسبوع واليوم، مما يضمن تنفيذ المهام في الموعد المحدد دون تدخل يدوي.

## المتطلبات الأساسية

قبل الغوص في تعقيدات إعداد التكرارات حسب الشهر والأسبوع واليوم باستخدام Aspose.Tasks لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:

1. الفهم الأساسي لـ C#: يعد الإلمام بلغة برمجة C# أمرًا ضروريًا لفهم أمثلة التعليمات البرمجية المقدمة وتنفيذها.
   
2.  تثبيت Aspose.Tasks لـ .NET: تأكد من أنك قمت بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET. يمكنك الحصول على المكتبة من[صفحة التحميل](https://releases.aspose.com/tasks/net/).

3. الوصول إلى ملف مشروع ‎.mpp: جهز ملف Microsoft Project (.mpp)، حيث سنستخدمه لتوضيح تنفيذ التكرارات حسب الشهر والأسبوع واليوم.

## استيراد مساحات الأسماء

للبدء في استخدام Aspose.Tasks لـ .NET في تطبيق C# الخاص بك، تحتاج إلى استيراد مساحات الأسماء الضرورية. وإليك كيف يمكنك القيام بذلك:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

فلنقم بتقسيم مقتطف الشفرة المقدم إلى خطوات متعددة لفهم كل جزء بدقة.

## الخطوة 1: تحميل ملف المشروع

```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 تتضمن هذه الخطوة إنشاء مثيل جديد لـ`Project` فئة وتحميل ملف Microsoft Project موجود (`Project1.mpp`) من الدليل المحدد.

## الخطوة 2: تحديد معلمات المهمة المتكررة

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

في هذه الخطوة، نقوم بتحديد المعلمات لمهمة متكررة. نحدد اسم المهمة ومدتها ونمط التكرار (شهريًا) ونطاق التكرار (تنتهي بتاريخ محدد).

## الخطوة 3: إضافة مهمة متكررة إلى المشروع

```csharp
project.RootTask.Children.Add(parameters);
```

هنا، نضيف معلمات المهمة المتكررة المحددة إلى المهمة الجذرية للمشروع.

## الخطوة 4: حفظ ملف المشروع

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

وأخيرا، نقوم بحفظ ملف المشروع المعدل مع المهمة المتكررة المضافة.

## خاتمة

في الختام، يعد إعداد التكرارات حسب الشهر والأسبوع واليوم في Aspose.Tasks لـ .NET عملية مباشرة تمكن المطورين من أتمتة إدارة المهام المتكررة داخل مشاريعهم بكفاءة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات C# الخاصة بك، مما يوفر الوقت والجهد في إدارة المشروع.

## الأسئلة الشائعة

###Q1: هل يمكنني تخصيص نمط التكرار بما يتجاوز الأمثلة المقدمة؟

ج1: نعم، يوفر Aspose.Tasks for .NET خيارات تخصيص شاملة لأنماط التكرار، مما يسمح لك بتخصيصها وفقًا لمتطلباتك المحددة.

###Q2: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟

 ج2: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[صفحة الإصدارات](https://releases.aspose.com/).

###Q3: كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟

 ج3: يمكنك طلب المساعدة والتفاعل مع المجتمع على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).

###Q4: هل التراخيص المؤقتة متاحة لـ Aspose.Tasks لـ .NET؟

 ج4: نعم، يمكنك الحصول على تراخيص مؤقتة من[صفحة الشراء](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.

###Q5: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks لـ .NET؟

 ج5: يمكنك الرجوع إلى التفاصيل[توثيق](https://reference.aspose.com/tasks/net/) متاح على موقع Aspose للحصول على إرشادات متعمقة حول استخدام المكتبة.