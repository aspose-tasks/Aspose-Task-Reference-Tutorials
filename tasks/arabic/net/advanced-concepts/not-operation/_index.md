---
title: العمل مع NOT Operation في Aspose.Tasks
linktitle: العمل مع NOT Operation في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية استخدام عملية NOT في Aspose.Tasks لـ .NET لتصفية المهام بشكل فعال. تعزيز قدرات إدارة المشروع الخاص بك الآن.
weight: 20
url: /ar/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# العمل مع NOT Operation في Aspose.Tasks

## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية الاستفادة من عملية NOT في Aspose.Tasks لـ .NET. تسمح لنا عملية NOT بعكس شرط التصفية، مما يمكننا من تحديد العناصر التي لا تلبي معايير محددة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. Visual Studio: أنت بحاجة إلى تثبيت فعال لبرنامج Visual Studio لمتابعة أمثلة التعليمات البرمجية.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[موقع إلكتروني](https://releases.aspose.com/tasks/net/).
3. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا في فهم أمثلة التعليمات البرمجية.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية للتعليمات البرمجية الخاصة بنا:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: إعداد المشروع والمهام

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 نبدأ بتحميل ملف المشروع المسمى "Project2.mpp" باستخدام ملف`Project` الفئة المقدمة من Aspose.Tasks. تأكد من وجود ملف المشروع في الدليل المحدد.

## الخطوة 2: جمع مهام المشروع

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 هنا نقوم بإنشاء`ChildTasksCollector` كائن لجمع كافة المهام داخل المشروع. نستخدم بعد ذلك`TaskUtils.Apply` طريقة لاجتياز التسلسل الهرمي لمهام المشروع وجمع كافة المهام الفرعية.

## الخطوة 3: تحديد حالة الفلتر

```csharp
var filter = new NullCondition();
```

 نحدد شرط التصفية باستخدام فئة مخصصة تسمى`NullCondition`. يحدد هذا الشرط المهام التي لها قيمة فارغة.

## الخطوة 4: تطبيق عدم التشغيل

```csharp
var condition = new Not<Task>(filter);
```

 نطبق عملية NOT على حالة الفلتر باستخدام`Not<T>`الفئة المقدمة من Aspose.Tasks. سيؤدي هذا إلى عكس حالة عامل التصفية، وتحديد المهام التي لا تحتوي على قيمة فارغة.

## الخطوة 5: تصفية المهام

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 نقوم بتصفية المهام المجمعة بناءً على الحالة المطبقة باستخدام خيار مخصص`Filter` طريقة. تأخذ هذه الطريقة مجموعة لا حصر لها من المهام وشرط التصفية كمعلمات إدخال، وتقوم بإرجاع قائمة بالمهام التي تستوفي الشرط.

## الخطوة 6: معالجة المهام التي تمت تصفيتها

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // العمل مع خصائص أخرى...
}
```

وأخيرًا، نكرر المهام التي تمت تصفيتها وننفذ أي عمليات مطلوبة. في هذا المثال، نقوم ببساطة بطباعة أسماء المهام إلى وحدة التحكم.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع عملية NOT في Aspose.Tasks لـ .NET. من خلال عكس شروط التصفية، يمكننا اختيار العناصر التي لا تلبي معايير محددة بشكل انتقائي، مما يعزز مرونتنا في معالجة المهام داخل المشاريع.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Tasks مع أطر عمل .NET أخرى؟

ج: نعم، يدعم Aspose.Tasks أطر عمل .NET المتنوعة، بما في ذلك .NET Core و.NET Standard و.NET Framework.

### س2: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟

 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع إلكتروني](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على دعم Aspose.Tasks؟

 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لأية استفسارات الدعم أو المساعدة الفنية.

### س4: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟

 ج: نعم، يمكنك شراء ترخيص مؤقت من[صفحة الشراء](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks؟

 ج: يمكنك الوصول إلى الوثائق الكاملة على[صفحة وثائق Aspose.Tasks](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
