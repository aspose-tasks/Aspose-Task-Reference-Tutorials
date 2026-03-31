---
date: 2026-03-19
description: تعرّف على كيفية استخدام عامل AND في جميع الشروط مع Aspose.Tasks لـ .NET
  لتصفية مهام المشروع بكفاءة.
linktitle: Using AND Operator in All Conditions with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية استخدام عامل AND في جميع الشروط مع Aspose.Tasks
url: /ar/net/advanced-features/and-operator-all-conditions/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخدام عامل AND في جميع الشروط مع Aspose.Tasks

## المقدمة

هل تبحث عن تبسيط مهام إدارة المشاريع بكفاءة؟ باستخدام Aspose.Tasks لـ .NET، يمكنك الاستفادة من وظائف قوية للتعامل مع بيانات المشروع بفعالية. إحدى هذه الميزات هي القدرة على **استخدام عامل AND** في جميع الشروط، مما يتيح لك تصفية المهام بناءً على معايير متعددة في آن واحد. في هذا الدرس، سنرشدك خطوة بخطوة إلى تنفيذ هذه الميزة، حتى تتمكن من **كيفية تصفية المهام** بسرعة وموثوقية.

## إجابات سريعة
- **ماذا يفعل عامل AND؟** يجمع بين عدة شروط تصفية بحيث تُرجع فقط المهام التي تفي *بجميع* المعايير.  
- **أي مكتبة توفر هذه الميزة؟** Aspose.Tasks لـ .NET.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **هل يمكنني تحميل ملف MPP؟** نعم – استخدم الفئة `Project` لتحميل ملف *.mpp*.  
- **هل يمكن تصفية مهام الملخص؟** بالتأكيد، عبر إضافة `SummaryCondition` إلى قائمة الشروط.

## ما هي ميزة “use and operator”؟
تتيح لك قدرة **use and operator** ربط عدة تطبيقات `ICondition<T>` باستخدام `AndAllCondition<T>`. تُعيد الفلترة الناتجة فقط تلك المهام التي تُحقق *كل* شرط تحدده.

## لماذا تطبيق شروط متعددة؟
تطبيق شروط متعددة (مثلاً “المهمة ليست فارغة” **و** “المهمة هي مهمة ملخص”) يمنحك تحكمًا دقيقًا في البيانات التي تتعامل معها. هذا مفيد بشكل خاص عندما تحتاج إلى **إنشاء منطق تصفية مخصص** لجدولات مشاريع معقدة أو لتوليد تقارير تركز على مجموعات مهام محددة.

## المتطلبات المسبقة

قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:

1. **معرفة أساسية بـ C#** – الإلمام بلغة البرمجة C# سيكون مفيدًا.  
2. **مكتبة Aspose.Tasks لـ .NET** – قم بتحميل وتثبيت مكتبة Aspose.Tasks لـ .NET من [here](https://releases.aspose.com/tasks/net/).  
3. **بيئة تطوير متكاملة (IDE)** – احرص على وجود IDE مثل Visual Studio مثبت على نظامك لتسهيل كتابة الشيفرة.  

## استيراد المساحات الاسمية

أولاً، تحتاج إلى استيراد المساحات الاسمية الضرورية للوصول إلى الفئات والطرق المطلوبة.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

الآن، لنقسم المثال إلى خطوات متعددة لفهم العملية بوضوح.

## الخطوة 1: تحميل ملف المشروع (load mpp file)

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

حمّل ملف المشروع باستخدام مُنشئ الفئة `Project`، مع تحديد مسار الملف. تُظهر هذه الخطوة معالجة **load mpp file**.

## الخطوة 2: جمع جميع مهام المشروع

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

استخدم الفئة `ChildTasksCollector` لجمع جميع المهام داخل المشروع.

## الخطوة 3: تعريف شروط الفلترة

```csharp
var conditions = new List<ICondition<Task>>
{
    new NotNullCondition(),
    new SummaryCondition()
};
```

أنشئ قائمة من الشروط لتصفية المهام. في هذا المثال، نقوم بتصفية المهام التي تكون **غير فارغة** وتكون **مهام ملخص** – مثال على **filter summary tasks**.

## الخطوة 4: تطبيق عامل AND على الشروط (apply multiple conditions)

```csharp
var joinedCondition = new AndAllCondition<Task>(conditions);
```

اجمع الشروط باستخدام الفئة `AndAllCondition`، مطبقًا **use and operator** على جميع الشروط.

## الخطوة 5: تصفية المهام

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

طبق الشرط المدمج على المهام المجمعة لتصفيةها وفقًا لذلك. تُظهر هذه الخطوة **كيفية تصفية المهام** باستخدام شرط مركب.

## الخطوة 6: معالجة المهام المصفاة

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));
    // Perform operations with filtered tasks
}
```

قم بالتكرار عبر المهام المصفاة وأجرِ العمليات المطلوبة.

## المشكلات الشائعة والحلول

- **قائمة الشروط فارغة** – تأكد من إضافة على الأقل `ICondition<T>` قبل إنشاء `AndAllCondition<T>`.  
- **عدم إرجاع أي مهام** – تحقق من أن الشروط التي أضفتها تتطابق فعليًا مع مهام مشروعك (مثلاً قد تكون تصفي مهام ملخص بينما لا توجد أي منها).  
- **الملف غير موجود** – أعد فحص مسار `DataDir` واسم ملف *.mpp*.

## الأسئلة المتكررة

**س: هل يمكنني تطبيق شروط إضافية غير تلك المعروضة في المثال؟**  
ج: نعم، يمكنك تعريف وتطبيق أي شروط مخصصة بناءً على متطلبات مشروعك.

**س: هل Aspose.Tasks لـ .NET متوافق مع صيغ ملفات مشروع مختلفة؟**  
ج: نعم، يدعم Aspose.Tasks صيغ ملفات مشروع متعددة مثل MPP و XML و CSV.

**س: هل يقدم Aspose.Tasks دعمًا لخوارزميات جدولة المشاريع المعقدة؟**  
ج: بالتأكيد، يوفر Aspose.Tasks ميزات متقدمة لإدارة جداول المشاريع، بما في ذلك تحليل المسار الحرج وتخصيص الموارد.

**س: هل يمكن دمج Aspose.Tasks مع أطر عمل أو مكتبات .NET أخرى؟**  
ج: نعم، يمكنك دمج Aspose.Tasks بسلاسة مع أطر عمل أو مكتبات .NET أخرى لتعزيز الوظائف.

**س: هل هناك منتدى مجتمع أو قناة دعم لمستخدمي Aspose.Tasks؟**  
ج: نعم، يمكنك الوصول إلى منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15) لأي استفسارات أو مساعدة.

## الخاتمة

في الختام، يتيح لك استخدام **use and operator** في جميع الشروط مع Aspose.Tasks لـ .NET تصفية مهام المشروع بفعالية بناءً على معايير متعددة في آن واحد. باتباع الدليل خطوة بخطوة المقدم في هذا الدرس، يمكنك دمج هذه الميزة بسلاسة في سير عمل إدارة المشاريع الخاص بك، مما يعزز الإنتاجية والتنظيم.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-19  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

---