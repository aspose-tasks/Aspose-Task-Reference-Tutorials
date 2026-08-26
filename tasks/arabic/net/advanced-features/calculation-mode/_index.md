---
date: 2026-03-24
description: تعلم كيفية ضبط وضع الحساب في Aspose.Tasks لـ .NET، بما يشمل الوضع التلقائي،
  الوضع اليدوي، ووضع عدم الحساب لإدارة تبعيات المهام.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: كيفية تعيين وضع الحساب في Aspose.Tasks لـ .NET
url: /ar/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين وضع الحساب في Aspose.Tasks لـ .NET

## مقدمة

Aspose.Tasks for .NET هي واجهة برمجة تطبيقات قوية تتيح لك العمل مع ملفات Microsoft Project برمجيًا. أحد أهم الإعدادات التي ستواجهها هو **وضع الحساب**، الذي يتحكم في كيفية تحديث تواريخ المهام وجداول المشروع. في هذا البرنامج التعليمي ستتعلم **كيفية تعيين وضع الحساب**، وتستكشف **وضع الحساب التلقائي**، **وضع الحساب اليدوي**، و**وضع الحساب بدون حساب**، وترى كيف تؤثر هذه الخيارات على **إدارة تبعيات المهام**، **إنشاء تاريخ بدء المشروع**، و**ربط علاقات انتهاء‑بدء للمهام**.

## إجابات سريعة
- **ما هو وضع الحساب؟** يحدد ما إذا كانت تواريخ المهام تُعاد حسابها تلقائيًا، يدويًا، أو لا تُعاد حسابها على الإطلاق.  
- **لماذا أستخدم وضع الحساب اليدوي؟** للحصول على تحكم كامل في وقت تحديث الجدول الزمني، وهو مفيد في التحديثات الجماعية.  
- **ما هو الوضع الافتراضي؟** وضع الحساب التلقائي، الذي يُحدّث التواريخ فورًا بعد التغييرات.  
- **هل يمكنني تغيير الوضع أثناء التشغيل؟** نعم—ما عليك سوى تعيين خاصية `CalculationMode` على كائن `Project`.  
- **هل أحتاج إلى ترخيص؟** يتطلب الاستخدام في بيئة الإنتاج ترخيص صالح لـ Aspose.Tasks.

## ما هو “كيفية تعيين الحساب” في Aspose.Tasks؟
تعيين وضع الحساب بسيط كإعطاء قيمة تعداد (enum) لخاصية `Project.CalculationMode`. يوفر التعداد ثلاثة خيارات: `Automatic`، `Manual`، و`None`. يعتمد اختيار الوضع المناسب على سير عملك—سواء كنت تريد تحديثات فورية، معالجة دفعات، أو تحكم كامل.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Visual Studio** – أي إصدار حديث (2019، 2022 أو أحدث).  
2. **Aspose.Tasks for .NET** – قم بتنزيل وتثبيت المكتبة من [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – يجب أن تكون مرتاحًا لإنشاء تطبيقات console واستخدام حزم NuGet.

## استيراد مساحات الأسماء

قبل أن نبدأ العمل مع Aspose.Tasks for .NET، لنقم باستيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System;
```

## كيفية تعيين وضع الحساب

أدناه ستجد أمثلة خطوة بخطوة لكل وضع حساب. لم يتم تعديل كتل الشيفرة عن الأصل؛ تم توسيع الشروحات المحيطة لتوضيح الفكرة.

### تطبيق وضع الحساب التلقائي

الوضع التلقائي يعيد حساب التواريخ فورًا كلما قمت بتعديل المهام أو الروابط.

#### الخطوة 1: إنشاء كائن Project جديد

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### الخطوة 2: تعيين تاريخ بدء المشروع وإضافة المهام

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### الخطوة 3: ربط المهام (إنهاء‑إلى‑بدء)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### الخطوة 4: التحقق من تواريخ إعادة الحساب

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### تطبيق وضع الحساب اليدوي

الوضع اليدوي يعطل التحديثات التلقائية، مما يمنحك فرصة معالجة التغييرات على دفعات قبل فرض إعادة حساب.

#### الخطوة 1: إنشاء كائن Project جديد

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### الخطوة 2: تعيين تاريخ بدء المشروع وإضافة المهام

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### الخطوة 3: التحقق من خصائص المهمة

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### الخطوة 4: ربط المهام والتحقق من التواريخ (بدون إعادة حساب تلقائي)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### تطبيق وضع الحساب بدون حساب

الوضع بدون حساب يعطل جميع الحسابات الداخلية. استخدمه عندما تحتاج فقط إلى قراءة أو تصدير البيانات دون أي تغييرات في الجدول الزمني.

#### الخطوة 1: إنشاء كائن Project جديد

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### الخطوة 2: إضافة مهمة جديدة

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### الخطوة 3: التحقق من خصائص المهمة (بدون معرفات تلقائية)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## المشكلات الشائعة والحلول

| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| التواريخ لا تُحدّث بعد ربط المهام | المشروع في وضع **Manual** أو **None** | عيّن `project.CalculationMode = CalculationMode.Automatic` أو استدعِ `project.Calculate()` يدويًا |
| معرفات المهام تبقى 0 | استخدام وضع **None** يمنع توليد المعرفات | التحّق إلى وضع **Automatic** أو **Manual**، ثم أعد الحساب |
| فشل الربط مع `ArgumentException` | تاريخ بدء السلف لاحق لتاريخ انتهاء المتابع عند استخدام وضع **Manual** دون إعادة حساب | تأكد من صحة تواريخ البدء أو أعد الحساب بعد إضافة الروابط |

## الأسئلة المتكررة

**س1: هل يمكنني تغيير وضع الحساب ديناميكيًا أثناء التشغيل؟**  
ج1: نعم، يمكنك تعديل خاصية `CalculationMode` في أي لحظة من الشيفرة ثم استدعاء `project.Calculate()` إذا كنت بحاجة إلى تحديث فوري.

**س2: هل يدعم Aspose.Tasks صيغ ملفات إدارة مشاريع أخرى غير Microsoft Project؟**  
ج2: يركز Aspose.Tasks أساسًا على صيغ Microsoft Project، لكنه يدعم أيضًا Primavera P6 XML، Primavera DB، وAsta Powerproject XML.

**س3: هل Aspose.Tasks مناسب للمشاريع الصغيرة وعلى مستوى المؤسسات؟**  
ج3: بالتأكيد. تتوسع الواجهة البرمجية من قوائم مهام بسيطة إلى جداول زمنية معقدة متعددة المراحل للمؤسسات.

**س4: هل يمكن دمج Aspose.Tasks مع مكتبات وإطارات .NET أخرى؟**  
ج4: نعم، يمكنك الجمع بين Aspose.Tasks وASP.NET، WPF، Xamarin، أو أي تقنية .NET أخرى لبناء حلول إدارة مشاريع غنية.

**س5: هل هناك منتدى مجتمع أو قناة دعم لمستخدمي Aspose.Tasks؟**  
ج5: نعم، يمكنك زيارة [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع والنقاشات.

---

**آخر تحديث:** 2026-03-24  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}