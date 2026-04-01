---
date: 2026-04-01
description: تعلم كيفية تعيين التكرار في Aspose.Tasks لـ .NET، وإضافة مهمة متكررة
  وأتمتة المهام المتكررة حسب الشهر والأسبوع واليوم.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: التكرار حسب الشهر والأسبوع واليوم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية تعيين التكرار في Aspose.Tasks (شهر، أسبوع، يوم)
url: /ar/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيف تضبط التكرار في Aspose.Tasks (شهر، أسبوع، يوم)

## مقدمة

إذا كنت بحاجة إلى **كيفية ضبط التكرار** للمهام في مشروع، فإن Aspose.Tasks for .NET يوفر لك طريقة نظيفة برمجية لإضافة تعريفات مهام متكررة تعمل شهريًا أو أسبوعيًا أو يوميًا. في هذا الدرس سنستعرض مثالًا واقعيًا يوضح لك كيفية **إضافة مهمة متكررة**، **أتمتة المهام المتكررة**، وإدارتها مباشرةً من كود C#. في النهاية، ستكون جاهزًا لدمج هذه القدرة في أي حل للجدولة أو إدارة المشاريع.

## إجابات سريعة
- **ماذا يعني “recurrence” في Aspose.Tasks؟** يحدد نمطًا (يوميًا، أسبوعيًا، شهريًا) يقوم تلقائيًا بإنشاء نسخ من المهمة على مدى نطاق تاريخي.  
- **ما هي الطريقة الأساسية التي تنشئ التكرار؟** `RecurringTaskParameters` مع `RecurrencePattern` محدد.  
- **هل أحتاج إلى ترخيص لتشغيل هذا الكود؟** النسخة التجريبية تعمل للتقييم؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني جدولة مهام أسبوعية بدلاً من شهرية؟** نعم – استبدل `MonthlyRecurrencePattern` بـ `WeeklyRecurrencePattern`.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6 وما بعدها.

## ما هو التكرار في Aspose.Tasks؟

التكرار هو مجموعة من القواعد التي تخبر Aspose.Tasks بإنشاء نسخ من المهمة على فترات منتظمة — يوميًا، أسبوعيًا، أو شهريًا — دون الحاجة إلى تكرارها يدويًا. هذه الميزة أساسية للمشاريع التي تحتوي على أنشطة روتينية مثل اجتماعات الحالة، التفتيشات، أو أعمال الصيانة.

## لماذا نستخدم ميزات التكرار؟

- **توفير الوقت:** لا حاجة لنسخ‑لصق المهام يدويًا.  
- **تقليل الأخطاء:** المكتبة تضمن تواريخ ومدد زمنية متسقة.  
- **المرونة:** دمج الأنماط (مثال: “الأحد الأول من كل شهرين”).  
- **الأتمتة:** مثالية لإنشاء الجداول في خطوط CI أو أدوات التقارير.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

1. **فهم أساسي للغة C#** – ستكتب بضع أسطر من كود C#.  
2. **تثبيت Aspose.Tasks for .NET** – احصل عليه من [صفحة التحميل](https://releases.aspose.com/tasks/net/).  
3. **ملف مشروع .mpp** – سنستخدم `Project1.mpp` كملف المصدر.

## استيراد مساحات الأسماء

لبدء، استورد مساحات الأسماء المطلوبة من Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### الخطوة 1: تحميل ملف المشروع

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

ننشئ كائن `Project` يشير إلى ملف Microsoft Project موجود.

### الخطوة 2: تعريف معلمات المهمة المتكررة

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

هنا نقوم **بإنشاء معلمات مهمة متكررة**:

- **TaskName** – اسم المهمة المُنشأة.  
- **Duration** – مدة كل تكرار.  
- **RecurrencePattern** – نمط شهري يتكرر كل 2 شهر في الأحد الأول.  
- **RecurrenceRange** – تاريخ البداية والنهاية اللذين يحددان الجدول.

### الخطوة 3: إضافة المهمة المتكررة إلى المشروع

```csharp
project.RootTask.Children.Add(parameters);
```

هذا السطر **يضيف المهمة المتكررة** إلى جذر هيكل المشروع.

### الخطوة 4: حفظ المشروع المحدث

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

يتم حفظ المشروع كملف `.mpp` جديد يحتوي الآن على الجدول الآلي.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **المهمة غير ظاهرة** | نطاق التكرار خارج تواريخ المشروع. | تحقق من أن قيم `Start` و `Finish` ضمن تقويم المشروع. |
| **يوم الأسبوع خاطئ** | عدم تطابق تعداد `WeekDay`. | استخدم `DayOfWeek.Monday` … `DayOfWeek.Sunday` حسب الحاجة. |
| **استثناء الترخيص** | التشغيل بدون ترخيص صالح في بيئة الإنتاج. | طبق ترخيصًا مؤقتًا أو كاملًا قبل الحفظ. |

## الأسئلة المتكررة

### س1: هل يمكنني تخصيص نمط التكرار بما يتجاوز الأمثلة المقدمة؟

ج1: نعم، يوفر Aspose.Tasks for .NET خيارات تخصيص واسعة لنماذج التكرار، مما يتيح لك تعديلها وفقًا لمتطلباتك الخاصة.

### س2: هل تتوفر نسخة تجريبية من Aspose.Tasks for .NET؟

ج2: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks for .NET من [صفحة الإصدارات](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks for .NET؟

ج3: يمكنك طلب المساعدة والتفاعل مع المجتمع على [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### س4: هل تتوفر تراخيص مؤقتة لـ Aspose.Tasks for .NET؟

ج4: نعم، يمكنك الحصول على تراخيص مؤقتة من [صفحة الشراء](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.

### س5: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks for .NET؟

ج5: يمكنك الرجوع إلى [الوثائق](https://reference.aspose.com/tasks/net/) التفصيلية المتاحة على موقع Aspose للحصول على إرشادات متعمقة حول استخدام المكتبة.

---

**آخر تحديث:** 2026-04-01  
**تم الاختبار مع:** Aspose.Tasks 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}