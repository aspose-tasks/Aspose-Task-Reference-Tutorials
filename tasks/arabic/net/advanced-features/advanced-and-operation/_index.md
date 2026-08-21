---
date: 2026-03-16
description: تعلم كيفية دمج عدة شروط وتصفية مهام المشروع باستخدام عملية AND المتقدمة
  في Aspose.Tasks لـ .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية دمج عدة شروط باستخدام عملية AND المتقدمة في Aspose.Tasks
url: /ar/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# العملية المتقدمة AND في Aspose.Tasks

## المقدمة

في هذا الدرس ستكتشف **كيفية دمج عدة شروط** باستخدام *العملية المتقدمة AND* في Aspose.Tasks لـ .NET. بحلول نهاية الدليل ستكون قادرًا على **تصفية مهام المشروع** بناءً على عدة معايير—وهو أمر أساسي عندما تحتاج إلى **كيفية تصفية المهام** مثل عناصر الملخص، الإدخالات غير الفارغة، أو العلامات المخصصة في تمريرة واحدة.

## إجابات سريعة
- **ماذا تفعل العملية المتقدمة AND؟** تقوم بدمج شرطين أو أكثر لتصفية بحيث يتم إرجاع المهام التي تستوفي *جميع* المعايير.  
- **أي فئة تجمع الشروط؟** `Util.And<T>` (متاحة كـ `And<T>` في الـ API).  
- **هل أحتاج إلى ترخيص خاص؟** يلزم وجود ترخيص Aspose.Tasks عادي للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **هل يمكنني ربط أكثر من شرطين؟** نعم—`And<T>` تقبل أي عدد من الشروط.  
- **ما نسخة .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.

## ما معنى “دمج عدة شروط” في Aspose.Tasks؟

دمج عدة شروط يعني إنشاء فلتر مركب يقيم كل مهمة مقابل عدة قواعد في آن واحد. هذا النهج أكثر كفاءة بكثير من تكرار قائمة المهام عدة مرات لأن المكتبة تطبق المنطق في تمريرة واحدة.

## لماذا نستخدم العملية المتقدمة AND؟

- **الأداء:** يقلل عدد المرور على مجموعة المهام.  
- **قابلية القراءة:** يحافظ على منطق الفلتر بصيغة إعلانية وسهلة الصيانة.  
- **المرونة:** يمكنك خلط الشروط المدمجة (مثل `SummaryCondition`) مع الدوال المخصصة.  

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

1. معرفة أساسية ببرمجة C#.  
2. تثبيت Aspose.Tasks لـ .NET. إذا لم تقم بتحميله بعد، احصل عليه **[هنا](https://releases.aspose.com/tasks/net/)**.  
3. بيئة تطوير متكاملة مثل Visual Studio (أي نسخة تعمل).  

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي توفر نموذج المهمة وفئات الأدوات:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## الخطوة 1: تهيئة المشروع وجمع المهام

سنقوم بإنشاء كائن `Project` واستخدام `ChildTasksCollector` لجمع كل مهمة في الملف. هذا يوضح **كيفية استخدام المجمع** لاسترجاع قائمة مسطحة من المهام.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## الخطوة 2: تعريف شروط الفلترة

هنا نعرّف الشروط الفردية التي نريد تطبيقها. في هذا المثال **نقوم بتصفية مهام الملخص** وأيضًا نتأكد من أن كائن المهمة غير فارغ.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## الخطوة 3: دمج الشروط باستخدام عملية AND

الآن **ندمج عدة شروط** باستخدام فئة `And<T>`. هذا هو جوهر **العملية المتقدمة AND**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## الخطوة 4: تطبيق الشرط وتصفية المهام

مع جاهزية الشرط المركب، نستدعي `Filter` لـ **تصفية مهام المشروع** بناءً على المنطق المدمج.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## الخطوة 5: إخراج المهام المصفاة

أخيرًا، نعرض المهام التي استوفت **جميع** الشروط. يمكنك استبدال استدعاءات `Console.WriteLine` بأي معالجة مخصصة تحتاجها.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## المشكلات الشائعة والحلول

| المشكلة | لماذا يحدث | الحل السريع |
|-------|----------------|-----------|
| `Filter` method غير موجود | غياب `using Aspose.Tasks.Util;` | تأكد من استيراد مساحة الأسماء Util (انظر استيراد مساحات الأسماء). |
| لم يتم إرجاع أي مهام | الشروط صارمة جدًا (مثلاً تصفية مهام الملخص عندما لا توجد أي منها) | تحقق من أن المشروع يحتوي فعليًا على مهام ملخص أو عدل الشروط. |
| NullReferenceException | `coll.Tasks` يحتوي على إدخالات فارغة | `NotNullCondition` يحمي بالفعل من ذلك؛ احتفظ به في سلسلة AND. |

## الأسئلة المتكررة

### س1: ما هو Aspose.Tasks لـ .NET؟

**ج:** Aspose.Tasks لـ .NET هي واجهة برمجة تطبيقات قوية تتيح للمطورين تعديل ملفات Microsoft Project برمجيًا في تطبيقات .NET.

### س2: هل يمكنني تطبيق أكثر من شرطين باستخدام Util.And؟

**ج:** نعم، يمكن استخدام Util.And لدمج أي عدد من الشروط لإنشاء معايير تصفية معقدة.

### س3: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks لـ .NET؟

**ج:** نعم، يمكنك تنزيل نسخة تجريبية مجانية من **[هنا](https://releases.aspose.com/)**.

### س4: أين يمكنني العثور على وثائق Aspose.Tasks لـ .NET؟

**ج:** يمكنك العثور على الوثائق **[هنا](https://reference.aspose.com/tasks/net/)**.

### س5: كيف يمكنني الحصول على دعم لـ Aspose.Tasks لـ .NET؟

**ج:** يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks **[هنا](https://forum.aspose.com/c/tasks/15)**.

**أسئلة وإجابات إضافية**

**س: كيف أقوم بتصفية المهام حسب قيم الحقول المخصصة؟**  
**ج:** أنشئ `CustomFieldCondition` (أو نفّذ `ICondition<Task>`) وأضفه إلى سلسلة `And<T>`.

**س: هل يمكنني استخدام نفس النهج لتصفية الموارد؟**  
**ج:** نعم—استبدل `Task` بـ `Resource` واستخدم فئات الشروط المقابلة.

## الخلاصة

باتباع الخطوات أعلاه، أصبحت الآن تعرف **كيفية دمج عدة شروط** باستخدام **العملية المتقدمة AND** في Aspose.Tasks لـ .NET. تتيح لك هذه التقنية **تصفية مهام المشروع** بفعالية، سواء كنت تستهدف عناصر الملخص، الإدخالات غير الفارغة، أو أي معايير مخصصة تحددها.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}