---
date: 2026-04-09
description: تعلم كيفية ضبط التقويم القياسي وإدارة عطلات المشروع في مشاريع .NET الخاصة
  بك باستخدام Aspose.Tasks للحصول على جدولة دقيقة.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: تعيين التقويم القياسي ومعالجة الاستثناءات في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: تعيين التقويم القياسي ومعالجة الاستثناءات في Aspose.Tasks
url: /ar/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين التقويم القياسي ومعالجة الاستثناءات في Aspose.Tasks

## مقدمة

التخطيط الدقيق هو العمود الفقري لأي مشروع ناجح، وغالبًا ما تحتاج الخطط الواقعية إلى الانحراف عن تقويم العمل الافتراضي بسبب العطلات أو الفعاليات الخاصة أو الإغلاقات غير المتوقعة. تجعل Aspose.Tasks لـ .NET من السهل **تعيين التقويم القياسي** ثم إضافة استثناءات مخصصة فوقه. في هذا الدرس ستتعلم كيفية تحميل تقويم المشروع، تعيين تقويم قياسي، وإدارة عطلات المشروع من خلال ميزة مجموعة استثناءات التقويم.

## إجابات سريعة
- **ما الذي يفعله “set standard calendar”?** يعيد ضبط التقويم إلى وقت العمل الافتراضي (من 9 ص إلى 5 م، من الإثنين إلى الجمعة) قبل إضافة الاستثناءات المخصصة.  
- **ما الطريقة التي تمسح الاستثناءات الموجودة؟** `Calendar.Exceptions.Clear()` يزيل جميع الاستثناءات المعرفة مسبقًا.  
- **كيف يمكنني إضافة عطلة؟** أنشئ `CalendarException` مع `DayWorking = false` وأضفه إلى المجموعة.  
- **هل أحتاج إلى إعادة تحميل المشروع بعد التغييرات؟** لا، يتم تطبيق التغييرات مباشرة على كائن `Project` الموجود في الذاكرة.  
- **ما المكتبات المطلوبة؟** Aspose.Tasks لـ .NET (أي نسخة .NET مدعومة) ومساحات الأسماء `System`.

## المتطلبات المسبقة

1. **Aspose.Tasks لـ .NET** – قم بتنزيله [هنا](https://releases.aspose.com/tasks/net/).  
2. معرفة أساسية بـ **C#** – ستكتب بعض المقاطع القصيرة.  
3. بيئة تطوير مثل **Visual Studio** أو **JetBrains Rider**.

## استيراد مساحات الأسماء

تمنحك توجيهات `using` هذه الوصول إلى الفئات المطلوبة لتعامل مع التقويم.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## ما هو استثناء التقويم؟

*استثناء التقويم* يمثل فترة يتم فيها تعديل جدول العمل العادي – على سبيل المثال، عطلة على مستوى الشركة أو جدول عمل إضافي مؤقت. بإضافة استثناءات إلى التقويم يمكنك نمذجة القيود الواقعية دون تغيير التقويم الأساسي.

## كيفية تعيين التقويم القياسي في Aspose.Tasks

الخطوة الأولى هي تحميل ملف المشروع واسترجاع التقويم الذي تريد العمل معه.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### الخطوة 1: مسح الاستثناءات الموجودة وإعادة تعيين إلى تقويم قياسي

قبل إضافة قواعد جديدة، من الممارسات الجيدة مسح أي استثناءات قديمة و**تعيين التقويم القياسي**. هذا يضمن أساسًا نظيفًا.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### الخطوة 2: تعريف استثناء وقت العمل

أحيانًا تحتاج إلى إنشاء جدول مؤقت (مثلاً، ساعات ممتدة لإطلاق منتج). يحدد المقتطف التالي استثناء وقت عمل يمتد لعدة أيام ويتضمن فترتين عمل يوميتين.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### الخطوة 3: إضافة استثناءات وقت غير العمل (العطلات)

لـ **إدارة عطلات المشروع**، أنشئ استثناءات حيث تكون `DayWorking` مساوية لـ `false`. المثال أدناه يضيف كتلة عطلة لمدة يومين.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### الخطوة 4: عرض استثناءات التقويم (التحقق)

بعد إضافة الاستثناءات، غالبًا ما ترغب في التحقق من تسجيلها بشكل صحيح. الحلقة التالية تطبع تفاصيل كل استثناء إلى وحدة التحكم.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### الخطوة 5: إزالة جميع الاستثناءات (تنظيف)

إذا كنت بحاجة إلى إرجاع التقويم إلى حالته الأصلية، يمكنك إزالة كل استثناء برمجيًا.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| عدم ظهور الاستثناءات بعد الحفظ | لم يتم حفظ المشروع بعد التعديلات | استدعِ `project.Save("output.mpp")` بعد إجراء التغييرات. |
| تسبب الاستثناءات المتداخلة ساعات عمل غير متوقعة | Aspose.Tasks يستخدم آخر استثناء مضاف للفترات المتداخلة | رتّب استدعاءات `Add` بعناية أو اضبط الأولويات يدويًا. |
| `MakeStandardCalendar` يعيد تعيين أوقات العمل المخصصة | يقوم عمدًا بمسح الأوقات المخصصة؛ أعد إضافتها بعد الاستدعاء إذا لزم الأمر. | أضف كائنات `WorkingTime` المخصصة بعد استدعاء `MakeStandardCalendar`. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة استثناءات متعددة إلى تقويم واحد؟**  
ج: نعم، يمكنك إضافة استثناءات متعددة إلى تقويم باستخدام طريقة `AddRange`.

**س: كيف يمكنني التعامل مع الاستثناءات المتكررة، مثل العطلات الأسبوعية؟**  
ج: يمكنك حساب الاستثناءات المتكررة برمجيًا وإضافتها إلى التقويم باستخدام منطق مخصص.

**س: هل من الممكن استيراد استثناءات التقويم من مصادر خارجية؟**  
ج: نعم، يمكنك قراءة استثناءات التقويم من مصادر خارجية مثل قواعد البيانات أو ملفات CSV ودمجها في مشروعك.

**س: ماذا يحدث إذا كانت هناك استثناءات متداخلة في التقويم؟**  
ج: يسمح Aspose.Tasks لـ .NET بالتعامل مع الاستثناءات المتداخلة عبر تعريف الأولويات أو حل النزاعات بناءً على متطلبات مشروعك.

**س: هل يمكنني تخصيص أوقات العمل لكل يوم داخل استثناء؟**  
ج: نعم، يمكنك تحديد أوقات عمل مخصصة لأيام معينة داخل استثناء لتلبية احتياجات الجدولة المحددة.

## الخلاصة

من خلال **تعيين التقويم القياسي** أولاً ثم إضافة استثناءات مخصصة، تحصل على تحكم كامل في جدولة المشروع، مما يجعل من السهل **إدارة عطلات المشروع** وأي جداول زمنية خاصة أخرى. توفر مجموعة استثناءات التقويم في Aspose.Tasks طريقة برمجية نظيفة لنمذجة التقويمات الواقعية مباشرة داخل تطبيقات .NET الخاصة بك.

---

**آخر تحديث:** 2026-04-09  
**تم الاختبار مع:** Aspose.Tasks 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}