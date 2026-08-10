---
date: 2026-04-03
description: تعلم جدولة مهام إدارة المشاريع وكيفية إضافة مهمة متكررة باستخدام Aspose.Tasks
  لـ .NET، بما في ذلك حفظ المشروع كملف MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: التكرار حسب اليوم السنوي في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: جدولة مهام إدارة المشاريع مع تكرار يوم السنة في Aspose.Tasks
url: /ar/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# جدولة مهام إدارة المشاريع مع تكرار يوم السنة في Aspose.Tasks

## مقدمة

Effective **project management task scheduling** is the backbone of any successful project. When tasks repeat on a yearly basis—such as annual audits, maintenance windows, or seasonal reviews—handling those recurrences manually can become error‑prone and time‑consuming. Aspose.Tasks for .NET simplifies this by letting you programmatically define year‑day patterns, so you can focus on what matters most: delivering value. In this tutorial you’ll learn **how to add recurring task** logic based on a specific day of the year and see exactly **how to save project as MPP** for seamless integration with Microsoft Project.

## إجابات سريعة
- **ماذا يعني “تكرار يوم السنة”؟** It schedules a task on a specific day of a specific month each year.  
- **أي فئة API تنشئ التكرار؟** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **هل يمكنني تعيين تاريخ بدء وانتهاء؟** Yes, using `EndByRecurrenceRange`.  
- **ما هو تنسيق الملف الناتج؟** The project is saved as an MPP file (`SaveFileFormat.Mpp`).  
- **هل أحتاج إلى ترخيص للإنتاج؟** A commercial license is required for non‑evaluation use.

## المتطلبات المسبقة

Before diving into the tutorial, ensure that you have the following prerequisites in place:

1. Aspose.Tasks for .NET Library: Download and install the Aspose.Tasks for .NET library from the [الموقع](https://releases.aspose.com/tasks/net/).  
2. Development Environment: Set up a suitable development environment with Visual Studio or any other preferred IDE for .NET development.  
3. Basic Knowledge of C#: Familiarize yourself with C# programming language fundamentals to follow along with the code examples.  
4. Project Management Concepts: Understanding of project management concepts and task scheduling will aid in grasping the tutorial concepts effectively.

## استيراد مساحات الأسماء

Before we begin coding, let's import the necessary namespaces to facilitate our task manipulation using Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Now, let's break down the provided example into multiple steps and elucidate each step in detail.

## كيفية إضافة مهمة متكررة بنمط يوم السنة

### الخطوة 1: تحميل ملف المشروع

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Here, we initialize a new `Project` object and load an existing project file named **Project1.mpp**.

### الخطوة 2: تعريف معلمات المهمة المتكررة

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

In this step, we define parameters for our recurring task. We specify the task name, duration, and recurrence pattern. For yearly recurrence, we use the `YearlyRecurrencePattern` and set the repetition to occur on the **1st day of July** using `ByYearDayRepetition`. Additionally, we define the recurrence range from July 1 2018 to July 1 2019.

### الخطوة 3: إضافة المهمة إلى المشروع

```csharp
project.RootTask.Children.Add(parameters);
```

Here, we add the defined recurring task parameters to the root task of the project.

### الخطوة 4: حفظ المشروع كملف MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finally, we **save the project as an MPP file**, making it ready for opening in Microsoft Project or any compatible viewer.

## لماذا هذا مهم

- **الأتمتة** – Eliminates manual entry of yearly tasks, reducing human error.  
- **الاتساق** – Guarantees that the same day‑month pattern is applied across multiple years.  
- **التكامل** – The resulting MPP file can be shared with stakeholders who rely on Microsoft Project.  

## الأخطاء الشائعة والنصائح

- **دقة DateTime** – Ensure the start time aligns with your project calendar; otherwise, the task may appear offset.  
- **المناطق الزمنية** – The API works with `DateTime` objects; consider UTC conversion if your application spans multiple regions.  
- **فرض الترخيص** – In evaluation mode, the saved MPP may contain a watermark; use a valid license for production.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع أنماط التكرار المعقدة؟**  
ج: Yes, Aspose.Tasks provides comprehensive support for various recurrence patterns, including yearly, monthly, weekly, and daily repetitions.

**س: هل Aspose.Tasks متوافق مع صيغ ملفات المشروع المختلفة؟**  
ج: Absolutely, Aspose.Tasks supports popular project file formats such as MPP, XML, and CSV, ensuring compatibility across different project management tools.

**س: هل يوفر Aspose.Tasks وثائق ودعم للمطورين؟**  
ج: Yes, developers can access extensive documentation and seek assistance from the Aspose.Tasks community forums for any queries or issues they encounter.

**س: هل يمكنني تخصيص خصائص المهمة مثل المدة وتاريخ البدء باستخدام Aspose.Tasks؟**  
ج: Certainly, Aspose.Tasks provides robust APIs to manipulate task properties dynamically, allowing developers to customize durations, start dates, dependencies, and more.

**س: هل Aspose.Tasks مناسب للمشاريع الصغيرة والكبيرة على حد سواء؟**  
ج: Indeed, Aspose.Tasks is designed to cater to the needs of developers working on projects of all scales, from individual tasks to large‑scale enterprise projects.

---

**آخر تحديث:** 2026-04-03  
**تم الاختبار مع:** Aspose.Tasks 24.12 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}