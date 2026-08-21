---
date: 2026-03-19
description: تعلم كيفية إضافة مورد إلى المشروع وحساب مدة المهمة باستخدام خوارزمية
  الشجرة في Aspose.Tasks، وتعيين الموارد للمهام في .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: إضافة مورد إلى المشروع باستخدام خوارزمية الشجرة في Aspose.Tasks
url: /ar/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مورد إلى المشروع باستخدام خوارزمية الشجرة في Aspose.Tasks

## المقدمة

في هذا البرنامج التعليمي ستكتشف **كيفية إضافة مورد إلى المشروع** باستخدام خوارزمية الشجرة القوية التي توفرها Aspose.Tasks لـ .NET. سنستعرض إنشاء تسلسل هرمي للمهام، حساب مدة المهمة، وتعيين الموارد للمهام—كل ذلك بطريقة واضحة خطوة بخطوة يمكنك نسخها إلى حلّك الخاص.

## إجابات سريعة
- **ماذا تفعل خوارزمية الشجرة؟** إنها تتجول في تسلسل هرمي للمهام لتجميع قيم العمل بكفاءة.  
- **ما العملية الأساسية التي يغطيها هذا الدليل؟** إضافة مورد إلى مشروع وتحديث إجماليات العمل.  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت أو كامل للاستخدام في الإنتاج.  
- **هل يمكنني استخدام هذا مع .NET Core؟** نعم، تدعم Aspose.Tasks كل من .NET Framework و .NET Core.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة لملف مشروع أساسي.

## ما هو “إضافة مورد إلى المشروع” في Aspose.Tasks؟

إضافة مورد إلى مشروع يعني إنشاء كائن `Resource`، وتحديد نوعه (مثل work)، وربطه بواحدة أو أكثر من المهام عبر `ResourceAssignments`. يتيح ذلك للجدول الزمني حساب الجهد، التكلفة، والمدة الكلية للمشروع.

## لماذا نستخدم خوارزمية الشجرة لحساب عمل الموارد؟

تمشي خوارزمية الشجرة شجرة المهام مرة واحدة، وتجمع العمل من المهام الفرعية إلى مهام الملخص الخاصة بها. هذا النهج أكثر كفاءة بكثير من التكرار على كل مهمة على حدة، خاصة في المشاريع الكبيرة ذات الهياكل العميقة. كما يضمن أن قيم عمل الملخص تبقى متزامنة مع المهام التابعة.

## المتطلبات المسبقة

1. **Visual Studio** – أي إصدار حديث (2019، 2022، أو أحدث).  
2. **Aspose.Tasks for .NET** – قم بتنزيله من [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – يجب أن تكون مرتاحًا مع الفئات، الكائنات، و LINQ البسيط.

## استيراد مساحات الأسماء

في مشروع C# الخاص بك، استورد مساحات الأسماء الضرورية للعمل مع وظائف Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

الآن، دعنا نقسم كل مثال إلى خطوات متعددة:

## الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

حمّل ملف المشروع في الذاكرة باستخدام الفئة `Project`.

## الخطوة 2: تعريف تسلسل المهام الهرمي

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

عرّف تسلسل المهام الهرمي عن طريق إضافة مهام أصلية وفرعية.

## الخطوة 3: تعيين خصائص المهمة (بما في ذلك **calculate task duration**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

هنا نقوم **calculate task duration** بتحويل ساعات العمل إلى كائن `Duration` ثم نستنتج تاريخ الانتهاء.

## الخطوة 4: إضافة مورد (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

هذا المقتطف **adds a resource to the project** و **assigns resources to tasks** بحيث يعرف الجدول الزمني من المسؤول عن العمل.

## الخطوة 5: تطبيق خوارزمية الشجرة

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

ابدأ فئة `WorkAccumulator` وطبق خوارزمية الشجرة لجمع العمل المشترك عبر الهرمية.

## الخطوة 6: تحديث عمل المهمة

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

حدّث قيم العمل للمهام بناءً على المعلومات المجمعة.

## المشكلات الشائعة والنصائح

- **إعدادات التقويم مفقودة:** إذا كان تاريخ الانتهاء يبدو غير صحيح، تأكد من تكوين تقويم المشروع بشكل صحيح قبل استدعاء `GetFinishDateByStartAndWork`.  
- **عدم تطابق نوع المورد:** يجب دائمًا ضبط `Rsc.Type` إلى `ResourceType.Work` للموارد القائمة على الجهد؛ وإلا قد تعود عملية تجميع العمل بصفر.  
- **نصيحة احترافية:** بعد تحديث العمل، استدعِ `project.Save("UpdatedProject.mpp")` لحفظ التغييرات.

## الخلاصة

باتباع هذه الخطوات، الآن تعرف كيفية **add resource to project**، **calculate task duration**، و **assign resources to tasks** باستخدام خوارزمية الشجرة في Aspose.Tasks. هذه الطريقة تُبسّط إدارة الهرمية وتحافظ على دقة قيم عمل الملخص بأقل قدر من الشيفرة.

## الأسئلة المتكررة

### س1: ما هو Aspose.Tasks لـ .NET؟

A1: Aspose.Tasks لـ .NET هي واجهة برمجة تطبيقات قوية تسمح للمطورين بالتعامل مع ملفات Microsoft Project برمجيًا باستخدام C#.

### س2: هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟

A2: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من [here](https://releases.aspose.com/).

### س3: أين يمكنني العثور على وثائق Aspose.Tasks لـ .NET؟

A3: يمكنك العثور على الوثائق الخاصة بـ Aspose.Tasks لـ .NET [here](https://reference.aspose.com/tasks/net/).

### س4: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks لـ .NET؟

A4: للحصول على الدعم المتعلق بـ Aspose.Tasks لـ .NET، يمكنك زيارة [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### س5: هل هناك ترخيص مؤقت متاح لأغراض الاختبار؟

A5: نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من [here](https://purchase.aspose.com/temporary-license/).

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا النهج مع ملف مشروع كبير موجود؟**  
A: بالتأكيد. تعمل خوارزمية الشجرة على أي كائن `Project`، بغض النظر عن حجمه.

**س: هل تقوم الخوارزمية أيضًا بتحديث قيم التكلفة؟**  
A: يركز المثال على العمل، لكن يمكنك توسيعه ليشمل التكلفة عن طريق تجميع `Tsk.Cost` بطريقة مشابهة.

**س: ما إصدارات .NET المدعومة؟**  
A: تدعم Aspose.Tasks .NET Framework 4.5+، .NET Core 3.1+، .NET 5+، و .NET 6+.

**س: كيف أتعامل مع موارد متعددة لكل مهمة؟**  
A: أضف كل مورد باستخدام `project.ResourceAssignments.Add(task, resource)`؛ سيقوم المجمع بجمع عملهم تلقائيًا.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}