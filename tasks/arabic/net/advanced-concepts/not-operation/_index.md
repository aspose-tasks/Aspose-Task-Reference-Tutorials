---
date: 2026-03-14
description: تعلم كيفية تصفية المهام باستخدام عملية NOT في Aspose.Tasks لـ .NET واكتشف
  كيفية استخدام الفلتر NOT مع تطبيق شرط NOT لاستعلامات المهام المرنة.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: تصفية المهام ليست عملية في Aspose.Tasks
url: /ar/net/advanced-concepts/not-operation/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تصفية المهام باستخدام عملية NOT في Aspose.Tasks

## المقدمة

في هذا البرنامج التعليمي ستتعلم **كيفية تصفية المهام باستخدام عملية NOT** باستخدام Aspose.Tasks لـ .NET. تسمح عملية NOT بعكس شرط الفلتر بحيث يمكنك اختيار كل مهمة **لا** تفي بمعيار معين. هذه القدرة أساسية عندما تحتاج إلى استبعاد عناصر معينة—مثل المهام التي لا تحتوي على قيمة—أو عندما تريد بناء استعلامات معقدة دون كتابة كود إضافي.

## إجابات سريعة
- **ماذا تفعل عملية NOT؟** تعكس شرط الفلتر، وتعيد العناصر التي تفشل الاختبار الأصلي.  
- **لماذا نستخدم عملية تصفية المهام NOT؟** تبسط منطق الاستبعاد وتحافظ على قابلية قراءة الكود.  
- **أي مساحة أسماء توفر الفئة NOT؟** `Aspose.Tasks.Util`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام غير التجريبي.  
- **هل يمكنني دمج NOT مع شروط أخرى؟** بالتأكيد—يمكن دمجه مع `AndCondition`، `OrCondition`، إلخ.

## ما هي عملية تصفية المهام NOT؟
عملية **تصفية المهام NOT** هي نفي منطقي يُطبق على فلتر المهمة. بدلاً من اختيار المهام التي تطابق شرطًا ما، تختار تلك التي *لا* تطابقه. هذا مفيد بشكل خاص عندما تريد تجاهل المهام ذات الحقول الفارغة، أو الحالات المحددة، أو أي سمة أخرى ترغب في استبعادها.

## لماذا نطبق شرط NOT عند تصفية المهام؟
تطبيق **شرط NOT** يقلل الحاجة إلى عدة مرور على بيانات المشروع. يسمح لك بكتابة كود مختصر وقابل للصيانة ويحسن الأداء عن طريق تفويض التقييم إلى محرك Aspose.Tasks المُحسّن.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. Visual Studio: تحتاج إلى تثبيت Visual Studio لتتمكن من متابعة أمثلة الكود.  
2. Aspose.Tasks لـ .NET: قم بتحميل وتثبيت مكتبة Aspose.Tasks لـ .NET من [الموقع](https://releases.aspose.com/tasks/net/).  
3. فهم أساسي للغة C#: الإلمام بلغة البرمجة C# سيساعدك في فهم أمثلة الكود.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية لكودنا:

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

نبدأ بتحميل ملف مشروع يُدعى **Project2.mpp** باستخدام الفئة `Project` المقدمة من Aspose.Tasks. تأكد من وجود ملف المشروع في الدليل المحدد.

## الخطوة 2: جمع مهام المشروع

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

هنا، ننشئ كائن `ChildTasksCollector` لجمع جميع المهام داخل المشروع. ثم نستخدم `TaskUtils.Apply` لتجوال هيكلية مهام المشروع وجمع كل مهمة فرعية.

## الخطوة 3: تعريف شرط الفلتر

```csharp
var filter = new NullCondition();
```

نعرّف شرط الفلتر باستخدام فئة مخصصة تُدعى `NullCondition`. هذا الشرط يختار المهام التي لها قيمة **null**.  

> **نصيحة احترافية:** استبدل `NullCondition` بأي شرط آخر (مثل `EqualsCondition`) لاستهداف سمات مختلفة.

## الخطوة 4: تطبيق عملية NOT

```csharp
var condition = new Not<Task>(filter);
```

نطبق **عملية NOT** على شرط الفلتر باستخدام الفئة `Not<T>` المقدمة من Aspose.Tasks. هذا يعكس الشرط الأصلي، لذا يصبح الفلتر الآن يختار المهام التي **لا** تملك قيمة null. هذه هي جوهر تقنية **كيفية استخدام NOT في الفلتر**.

## الخطوة 5: تصفية المهام

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

نقوم بتصفية المهام المجمعة بناءً على الشرط المطبق باستخدام طريقة مخصصة `Filter`. تستقبل الطريقة مجموعة قابلة للتعداد من المهام وشرط الفلتر، وتعيد قائمة بالمهام التي تحقق **تطبيق شرط NOT**.

## الخطوة 6: معالجة المهام المصفاة

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

أخيرًا، ن iterates عبر المهام المصفاة وننفذ أي عمليات مرغوبة. في هذا المثال، نطبع فقط أسماء المهام إلى وحدة التحكم، لكن يمكنك توسيع هذا الجزء لتحديث الحقول، نقل المهام، أو إنشاء تقارير.

## حالات الاستخدام الشائعة

- **استبعاد المهام المكتملة** عند إنشاء قائمة بالعمل المتبقّي.  
- **العثور على المهام التي تفتقد حقول مخصصة** (مثل عمود “Owner” الذي يكون null).  
- **دمج مع شروط أخرى** لبناء استعلامات متقدمة، مثل “المهام التي ليست null وتملك تاريخ بدء قبل اليوم”.

## استكشاف الأخطاء وإصلاحها & نصائح

| المشكلة | السبب | الحل |
|-------|--------|-----|
| لا تُرجع أي مهام | قد يكون الشرط الأصلي مقيدًا جدًا. | تحقق من منطق الشرط أو جرّب فلتر أبسط مثل `new TrueCondition()`. |
| `NullReferenceException` | مسار `DataDir` غير صحيح. | تأكد من أن `DataDir` يشير إلى المجلد الذي يحتوي على *Project2.mpp*. |
| نتائج غير متوقعة | دمج `Not<T>` مع شروط أخرى بشكل غير صحيح. | استخدم الأقواس: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع أطر .NET أخرى؟**  
ج: نعم، يدعم Aspose.Tasks .NET Core، .NET Standard، والإصدار الكلاسيكي من .NET Framework.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من [الموقع](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟**  
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) لأي استفسارات دعم أو مساعدة تقنية.

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: نعم، يمكنك شراء ترخيص مؤقت من [صفحة الشراء](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks؟**  
ج: يمكنك الوصول إلى الوثائق الكاملة على [صفحة توثيق Aspose.Tasks](https://reference.aspose.com/tasks/net/).

## الخاتمة

من خلال إتقان **عملية تصفية المهام NOT** وتعلم **كيفية استخدام NOT في الفلتر** مع **تطبيق شرط NOT**، ستحصل على تحكم دقيق في اختيار المهام داخل Aspose.Tasks. هذا يمكّنك من كتابة كود أنظف، تجنّب الاستثناءات اليدوية، وبناء أدوات إدارة مشاريع قوية.

---

**آخر تحديث:** 2026-03-14  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}