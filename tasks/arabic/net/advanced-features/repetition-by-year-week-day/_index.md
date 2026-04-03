---
date: 2026-04-03
description: تعلم كيفية استخدام Aspose.Tasks لإضافة مهمة متكررة إلى المشروع وحفظ المشروع
  بصيغة MPP. يوضح هذا الدليل ميزة التكرار حسب السنة والأسبوع واليوم خطوة بخطوة.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: التكرار حسب السنة والأسبوع واليوم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية استخدام Aspose.Tasks – التكرار حسب السنة، الأسبوع، اليوم
url: /ar/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التكرار حسب السنة الأسبوع اليوم في Aspose.Tasks

## مقدمة

عندما تحتاج إلى **how to use Aspose.Tasks** للتعامل مع جداول متكررة معقدة، توفر المكتبة تحكمًا دقيقًا في الأنماط السنوية. في هذا البرنامج التعليمي سنستعرض إنشاء مهمة تتكرر في يوم أسبوع محدد من شهر معين، على مدار عدة سنوات. في النهاية ستكون قادرًا على **add recurring task project** وإدخالها و**save project as MPP** ببضع أسطر من C#.

## إجابات سريعة
- **What does “Repetition by Year Week Day” mean?** يعني أنه يكرر مهمة في يوم أسبوع مختار (مثلاً أول أحد) من شهر معين كل سنة.  
- **Which .NET versions are supported?** جميع إصدارات .NET Framework الحديثة و .NET Core/5/6.  
- **Do I need a license to run the code?** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **Can I change the recurrence range?** نعم – يمكنك تحديد تاريخ بدء، تاريخ انتهاء، أو عدد ثابت من التكرارات.  
- **Is the output an MPP file?** بالتأكيد – يتم حفظ المشروع كملف MPP جاهز لبرنامج Microsoft Project.

## ما هي ميزة “Repetition by Year Week Day”؟
تتيح لك الميزة تعريف تكرار سنوي يستهدف **day of the week** معين (مثلاً Sunday) و**position** داخل الشهر (الأول، الثاني، الأخير، إلخ). هذه الميزة مثالية للمهام مثل المراجعات ربع السنوية، التدقيقات السنوية، أو أي حدث يتبع إيقاعًا قائمًا على التقويم.

## لماذا تستخدم Aspose.Tasks للمهام المتكررة؟
- **Precision** – تحكم كامل في الشهور، أيام الأسبوع، والمواضع الترتيبية.  
- **Compatibility** – يولد ملفات MPP أصلية تُفتح بلا مشاكل في Microsoft Project.  
- **No COM interop** – API .NET نقي، لا حاجة لتثبيت Office.  
- **Scalability** – يعمل للمشاريع الصغيرة وجداول المستوى المؤسسي على حد سواء.

## المتطلبات المسبقة

1. **Basic .NET knowledge** – الإلمام بـ C# ومفاهيم البرمجة الكائنية.  
2. **Aspose.Tasks for .NET** – قم بتنزيله من [download link](https://releases.aspose.com/tasks/net/) وأضف الـ DLL إلى مشروعك.  
3. **Access to the official docs** – تحتوي [documentation](https://reference.aspose.com/tasks/net/) على تفاصيل شاملة لجميع الفئات.  
4. **A development IDE** – Visual Studio أو Rider أو أي محرر .NET متوافق.

الآن بعد أن أصبحت جاهزًا، دعنا نرى التنفيذ.

## كيفية استخدام Aspose.Tasks للمهام المتكررة

### استيراد المساحات الاسمية الضرورية

أولاً، استورد المساحات الاسمية المطلوبة لتتمكن من العمل مع المشاريع، المهام، وخيارات الحفظ.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### الخطوة 1: تهيئة المشروع ومعلمات المهمة

أنشئ كائن `Project` جديد، ثم عرّف كائن `RecurringTaskParameters` الذي يصف نمط التكرار.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** عدّل `Month` و `WeekDay` و `Position` لتتناسب مع جدولك الواقعي.

### الخطوة 2: إضافة المعلمات إلى المشروع

أدر تعريف المهمة المتكررة في جذر المشروع.

```csharp
project.RootTask.Children.Add(parameters);
```

### الخطوة 3: حفظ المشروع كملف MPP

أخيرًا، احفظ المشروع كملف MPP حتى يمكن فتحه في Microsoft Project أو أي عارض متوافق.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> يوضح هذا **save project as mpp** في سطر واحد من الشيفرة.

## المشكلات الشائعة والحلول

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| لا تظهر أي مهام بعد فتح ملف MPP | تواريخ نطاق التكرار خارج تقويم المشروع | تحقق من أن تواريخ `Start` و `Finish` تقع ضمن وقت عمل المشروع |
| استثناء `ArgumentNullException` عند `Add` | `parameters` فارغ أو غير مهيأ بالكامل | تأكد من تعيين جميع الخصائص المطلوبة (TaskName, Duration, RecurrencePattern) |
| تم اختيار يوم أسبوع خاطئ | عدم تطابق قيمة تعداد `WeekDay` | استخدم `DayOfWeek.Monday` … `DayOfWeek.Sunday` حسب الحاجة |

## الأسئلة المتكررة

**س: هل يمكنني تخصيص نمط التكرار بما يتجاوز المثال المقدم؟**  
ج: نعم، تتيح لك Aspose.Tasks دمج `MonthlyRecurrencePattern` و `WeeklyRecurrencePattern` أو حتى كائنات `RecurrenceRange` مخصصة لتناسب أي جدول.

**س: هل Aspose.Tasks for .NET متوافق مع برامج إدارة المشاريع الأخرى؟**  
ج: بالتأكيد – المكتبة تقرأ وتكتب صيغ MPP و XML و Primavera، مما يتيح تبادل بيانات سلس.

**س: كيف يمكنني التعامل مع الاستثناءات أو تعديل المهام المتكررة؟**  
ج: استخدم الفئة `ExceptionTask` لإنشاء استثناءات لتكرارات معينة، أو حرّر `RecurringTaskParameters` وأعد حفظ المشروع.

**س: هل تدعم Aspose.Tasks الحلول السحابية؟**  
ج: نعم، يمكنك تشغيل الـ API في Azure Functions أو AWS Lambda أو أي خدمة سحابية متوافقة مع .NET.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for .NET؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks for .NET عبر [website](https://releases.aspose.com/)، مما يتيح لك استكشاف ميزاته قبل اتخاذ قرار الشراء.

**س: كيف أضيف مهمة متكررة إلى مشروع موجود دون الكتابة فوق البيانات الأخرى؟**  
ج: حمّل المشروع الموجود باستخدام `new Project("Existing.mpp")`، أضف `RecurringTaskParameters` إلى `RootTask.Children`، ثم احفظ الملف باستخدام `Save`.

## الخاتمة

من خلال إتقان **how to use Aspose.Tasks** لسيناريو **Repetition by Year Week Day**، ستحصل على القدرة على **add recurring task project** التي تتوافق تمامًا مع التقويمات الواقعية و**save project as MPP** لتعاون سلس. دمج هذه الشيفرات في حلولك الخاصة لتعزيز دقة الجدولة وتقليل الجهد اليدوي.

---

**آخر تحديث:** 2026-04-03  
**تم الاختبار مع:** Aspose.Tasks 24.12 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}