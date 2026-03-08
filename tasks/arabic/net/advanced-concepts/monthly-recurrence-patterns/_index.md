---
date: 2026-03-08
description: تعلم كيفية إنشاء مهمة متكررة شهرية في Aspose.Tasks لـ .NET من خلال هذا
  الدليل خطوة بخطوة.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية إنشاء مهمة متكررة شهرية في Aspose.Tasks
url: /ar/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مهمة متكررة شهرية باستخدام Aspose.Tasks

## المقدمة

يتيح لك Aspose.Tasks لـ .NET تعديل ملفات Microsoft Project برمجيًا، وإحدى أكثر الاحتياجات الواقعية شيوعًا هي **إنشاء جداول مهام متكررة شهرية**. سواءً كنت تبني أداة تتبع مشاريع، أو تقوم بأتمتة تخصيص الموارد، أو توليد عناصر صيانة متكررة، فإن هذا الدليل سيقودك خطوة بخطوة لإضافة نمط تكرار شهري إلى مهمة.

في الأقسام التالية ستتعرف على كيفية إعداد المشروع، تعريف معلمات التكرار، وأخيرًا حفظ الملف المحدث — كل ذلك مع شروحات واضحة ونصائح عملية.

## إجابات سريعة
- **ماذا يعني “مهمة متكررة شهرية”؟** مهمة تتكرر وفق نمط يوم‑أو‑أسبوع محدد كل شهر.  
- **أي فئة API تتعامل مع التكرار؟** `RecurringTaskParameters` مع `MonthlyRecurrencePattern`.  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **هل يمكنني تغيير الفاصل الزمني؟** نعم – اضبط `RepetitionInterval` على عدد الأشهر بين التكرارات.  
- **ما صيغ الملفات المدعومة؟** يمكن تحميل وحفظ ملفات Project بصيغة `.mpp` و `.xml`.

## ما هو نمط التكرار الشهري؟

نمط التكرار الشهري يخبر Microsoft Project (و Aspose.Tasks) بمدى تكرار المهمة كل شهر. يمكنك تحديد يوم ثابت من الشهر (مثلاً اليوم الأول) أو موقع نسبي (مثلاً الجمعة الأخيرة). تقوم API بترجمة هذه القواعد إلى بنية ملف Project الأساسية.

## لماذا نستخدم Aspose.Tasks لهذا؟

- **تحكم كامل** – لا قيود واجهة مستخدم؛ يمكنك تعريف كل جانب من النمط في الكود.  
- **متعدد المنصات** – يعمل على .NET Framework، .NET Core، و .NET 5/6+.  
- **لا حاجة لوجود Microsoft Project** – يمكنك إنشاء أو تعديل الملفات على خادم أو في خط أنابيب CI.  

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

- .NET 6 (أو .NET 5/Framework 4.7+) مثبتة.  
- حزمة NuGet الخاصة بـ Aspose.Tasks لـ .NET مضافة إلى مشروعك.  
- ملف Project تجريبي (`Project1.mpp`) موجود في مجلد معروف (`DataDir`).  

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية المطلوبة للعمل مع المهام وحفظ المشاريع:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## الخطوة 1: تهيئة المشروع

أنشئ كائن `Project` يشير إلى ملف `.mpp` الحالي. يقوم هذا بتحميل الملف إلى الذاكرة لتتمكن من تعديله.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **نصيحة احترافية:** إذا لم يكن الملف موجودًا، سيقوم Aspose.Tasks بإنشاء مشروع فارغ جديد تلقائيًا.

## الخطوة 2: ضبط معلمات المهمة المتكررة

عرّف تفاصيل المهمة المتكررة، بما في ذلك الاسم، المدة، والنمط الشهري الذي تريد تطبيقه.

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

- `DayPosition = 1` يعني أن المهمة تحدث في **اليوم الأول** من الشهر.  
- `RepetitionInterval = 2` يجعل المهمة تتكرر **كل شهرين**.  
- `Start` و `Finish` يحددان النافذة العامة التي يكون فيها التكرار فعالًا.

## الخطوة 3: إضافة المعلمات إلى المشروع

أرفق كائن `RecurringTaskParameters` إلى مجموعة الأطفال في المهمة الجذرية. هذا ينشئ فعليًا المهمة المتكررة في هيكل المشروع.

```csharp
project.RootTask.Children.Add(parameters);
```

## الخطوة 4: حفظ المشروع

احفظ التغييرات عن طريق حفظ المشروع إلى ملف جديد. يمكنك اختيار أي صيغة مدعومة؛ هنا نستخدم الصيغة الأصلية `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

بعد تشغيل الكود، افتح الملف الناتج في Microsoft Project لترى المهمة المتكررة الشهرية التي أنشأتها.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|--------|-------|------|
| المهمة لا تظهر بعد الحفظ | المشروع غير محدث في الواجهة | أعد فتح الملف أو استدعِ `project.UpdateTaskLinks()` قبل الحفظ. |
| تاريخ البدء غير صحيح | `Start` محدد ليوم عطلة نهاية الأسبوع | استخدم `DateTime` يقع في يوم عمل أو عدل التقويم. |
| تم تجاهل فاصل التكرار | استخدام `ByMonthDayRepetition` مع `DayPosition` = 0 | تأكد من أن `DayPosition` بين 1‑31. |

## الخاتمة

باتباع هذه الخطوات أصبحت الآن تعرف كيف **تنشئ جداول مهام متكررة شهرية** باستخدام Aspose.Tasks لـ .NET. تمنحك API تحكمًا دقيقًا في فواصل التكرار، نطاقات البدء/الانتهاء، ونمط اليوم المحدد، مما يتيح لك أتمتة سيناريوهات تخطيط المشاريع المعقدة.

## الأسئلة المتكررة

### س1: هل Aspose.Tasks متوافق مع جميع إصدارات ملفات Microsoft Project؟

ج1: يدعم Aspose.Tasks إصدارات متعددة من ملفات Microsoft Project، بما في ذلك MPP، MPT، XML، و MPX.

### س2: هل يمكنني تخصيص نمط التكرار أكثر؟

ج2: نعم، يوفر Aspose.Tasks خيارات واسعة لتخصيص أنماط التكرار، بما في ذلك اليومية، الأسبوعية، الشهرية، والسنوية.

### س3: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟

ج3: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من الموقع [هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟

ج4: يمكنك طلب المساعدة والمشاركة في المناقشات على [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### س5: أين يمكنني شراء ترخيص لـ Aspose.Tasks؟

ج5: يمكنك شراء ترخيص لـ Aspose.Tasks من الموقع [هنا](https://purchase.aspose.com/buy).

## الأسئلة الشائعة

**س: هل يمكنني استخدام هذا الكود في تطبيق .NET Core؟**  
ج: بالتأكيد. يدعم Aspose.Tasks لـ .NET بالكامل .NET Core 3.1 والإصدارات الأحدث.

**س: كيف أغير التكرار إلى “آخر يوم عمل في الشهر”؟**  
ج: استخدم `ByMonthDayRepetition` مع `DayPosition = -1` (القيم السالبة تُحسب من نهاية الشهر) واضبط `WeekDay` وفقًا لذلك.

**س: ماذا يحدث إذا تجاوز نطاق التكرار تقويم المشروع؟**  
ج: تحترم API تقويم المشروع؛ فإن الوقوع في أيام غير عمل يتم إما تخطيه أو نقله بناءً على إعدادات التقويم.

**س: هل يمكن حذف حدوث محدد من مهمة متكررة؟**  
ج: نعم. بعد إضافة المهمة المتكررة، يمكنك استرجاع الوقائع الفردية عبر `Task.GetOccurrences()` وحذف ما لا تحتاجه.

**س: هل يتعامل Aspose.Tasks مع اختلافات المناطق الزمنية تلقائيًا؟**  
ج: تخزن المكتبة التواريخ بتوقيت UTC؛ يمكنك التحويل إلى الوقت المحلي باستخدام طرق `DateTime` القياسية في .NET إذا لزم الأمر.

---

**آخر تحديث:** 2026-03-08  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}