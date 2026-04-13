---
date: 2026-04-13
description: تعلم كيفية ضبط ساعات العمل وإدارة مجموعات التقويم في Aspose.Tasks لـ
  .NET. استيراد تقويمات Microsoft Project، إزالة تقويم المشروع، والحصول على التقويم
  بالاسم بسهولة.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: إدارة مجموعة التقويم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: تعيين ساعات العمل في مجموعة تقويم Aspose.Tasks
url: /ar/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين ساعات العمل في مجموعة تقويمات Aspose.Tasks

في هذا البرنامج التعليمي، ستتعلم كيفية **تعيين ساعات العمل** وإدارة مجموعات التقويمات باستخدام Aspose.Tasks لـ .NET. تُعرّف التقويمات أيام العمل والعطلات والاستثناءات، لذا فإن إتقانها يتيح لك التحكم بدقة في جداول المشروع. سنظهر لك أيضًا كيفية استيراد التقويمات من Microsoft Project، وإزالة تقويم من مشروع، والحصول على تقويم بالاسم.

## إجابات سريعة
- **ما هو الصنف الأساسي للتقويمات؟** `Project.Calendars` collection.
- **كيف يمكنني تعيين ساعات العمل؟** Create or modify a `Calendar` object and define its `WorkingTime`.
- **هل يمكنني استيراد التقويمات من Microsoft Project؟** Yes – load an MPP file and access its calendars.
- **كيف يمكن إزالة تقويم من مشروع؟** Use `Project.Calendars.Remove(calendar)`.
- **كيف يمكن استرجاع تقويم بالاسم؟** Call `Project.Calendars.GetByName("YourCalendar")`.

## المتطلبات المسبقة

1. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة مع .NET.  
2. Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لـ .NET من [هنا](https://releases.aspose.com/tasks/net/).  
3. فهم أساسي للغة C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء

أولاً، لنقم باستيراد مساحات الأسماء اللازمة للعمل مع Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## إنشاء تقويم جديد

### الخطوة 1: تهيئة كائن `Project` جديد.
```csharp
var project = new Project();
```

### الخطوة 2: إضافة تقويمات إلى مجموعة تقويمات المشروع.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### الخطوة 3: التجول عبر التقويمات وعرض أسمائها.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## كيف يتم تعيين ساعات العمل لتقويم؟

لت **تعيين ساعات العمل**، تقوم بتعديل مجموعة `WorkingTime` لتقويم `Calendar`.  
على سبيل المثال، يمكنك تعريف يوم عمل قياسي من 9 ص إلى 5 م أو إضافة استثناءات مخصصة.  
الكود لهذا هو نفسه الأمثلة المعروضة لاحقًا عندما ننشئ تقويمًا قياسيًا.

## استبدال تقويم بتقويم جديد

### الخطوة 1: تحميل مشروع موجود.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### الخطوة 2: إزالة التقويم الموجود (إذا كان موجودًا).  
هذا يوضح سيناريو **remove calendar project**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### الخطوة 3: إضافة تقويم جديد.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## الحصول على تقويم بالاسم أو المعرف

### الخطوة 1: تحميل المشروع.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### الخطوة 2: استرجاع التقويمات بالاسم أو UID.  
هذا يوضح عملية **get calendar by name**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### الخطوة 3: عرض تفاصيل التقويم.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## التجول عبر التقويمات

### الخطوة 1: تحميل المشروع.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### الخطوة 2: استرجاع عدد التقويمات.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### الخطوة 3: التجول عبر مجموعة التقويمات وعرض الأسماء.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## إنشاء تقويم قياسي

### الخطوة 1: تهيئة مشروع جديد.
```csharp
var project = new Project();
```

### الخطوة 2: تعريف تقويم جديد وجعله قياسيًا.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### الخطوة 3: حفظ المشروع.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول

- **Calendar not found when using `GetByName`** – تأكد من أن الاسم المطابق تمامًا يطابق الحالة المستخدمة عند إضافة التقويم.  
- **Working hours not applied** – بعد تعيين `WorkingTime`، تذكر حفظ المشروع؛ وإلا ستبقى التغييرات في الذاكرة فقط.  
- **Importing calendars from an MPP file fails** – تحقق من أن ملف المصدر هو ملف Microsoft Project صالح وأن لديك أذونات القراءة.

## الأسئلة المتكررة

### س1: هل يمكنني إنشاء أيام عمل مخصصة في Aspose.Tasks؟
ج1: نعم، يمكنك إنشاء أيام عمل مخصصة عن طريق إضافة استثناءات إلى التقويمات.

### س2: هل من الممكن استيراد التقويمات من ملفات Microsoft Project؟
ج2: بالتأكيد، يدعم Aspose.Tasks استيراد التقويمات من ملفات Microsoft Project.

### س3: كيف يمكنني إزالة تقويم محدد من مشروع؟
ج3: يمكنك إزالة تقويم عن طريق الحصول عليه من المجموعة ثم استدعاء طريقة `Remove`.

### س4: هل يدعم Aspose.Tasks تصدير التقويمات إلى صيغ مختلفة؟
ج4: نعم، يتيح Aspose.Tasks تصدير التقويمات إلى صيغ مختلفة مثل XML و MPP وغيرها.

### س5: هل يمكنني تخصيص ساعات العمل لأيام معينة في تقويم؟
ج5: بالتأكيد، يمكنك تحديد ساعات العمل لأيام معينة باستخدام الاستثناءات في التقويم.

## الأسئلة الشائعة

**س: ما هي أفضل طريقة لتعيين تقويم بنظام 24 ساعة؟**  
ج: إنشاء تقويم جديد، مسح إدخالات `WorkingTime` الحالية، وإضافة نطاق `WorkingTime` واحد من 00:00 إلى 24:00 لكل يوم من أيام الأسبوع.

**س: هل يمكنني نسخ تقويم من مشروع إلى آخر؟**  
ج: نعم — قم بتصدير التقويم إلى XML باستخدام `project.Save` ثم استورده إلى مشروع آخر باستخدام `new Project(xmlPath)`.

**س: كيف يمكنني استيراد التقويمات من Microsoft Project برمجيًا؟**  
ج: قم بتحميل ملف MPP باستخدام `new Project("source.mpp")`؛ تصبح التقويمات متاحة عبر `project.Calendars`.

**س: هل هناك حد لعدد التقويمات في مشروع؟**  
ج: عمليًا لا؛ يمكن للمجموعة احتواء عدد غير محدود من التقويمات حسب ما تسمح به الذاكرة، لكن يُفضَّل الحفاظ على القائمة قابلة للإدارة لأداء أفضل.

**س: هل تُحدِّث التغييرات على تقويم تلقائيًا المهام التي تستخدمه؟**  
ج: نعم — المهام المرتبطة بتقويم تعكس أوقات العمل المحدثة بعد حفظ المشروع.

---

**آخر تحديث:** 2026-04-13  
**تم الاختبار مع:** Aspose.Tasks 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}