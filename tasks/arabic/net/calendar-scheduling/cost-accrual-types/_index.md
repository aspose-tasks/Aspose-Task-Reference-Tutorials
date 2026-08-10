---
date: 2026-07-05
description: تعلم كيفية تتبع ميزانية المشروع وإدارة تكاليف المشروع باستخدام Aspose.Tasks
  for .NET. حدد Cost Accrual Types لتتبع التكاليف بدقة.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: تتبع ميزانية المشروع باستخدام Cost Accrual Types في Aspose.Tasks
url: /ar/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تتبع ميزانية المشروع باستخدام أنواع تراكم التكلفة في Aspose.Tasks

## مقدمة

إن **تتبع ميزانية المشروع** بدقة هو العمود الفقري لتسليم المشروع بنجاح. عندما يتم التقاط معلومات التكلفة في اللحظات المناسبة، يمكنك توقع التجاوزات، تعديل الموارد، وإبقاء أصحاب المصلحة على اطلاع. توفر Aspose.Tasks لـ .NET للمطورين تحكمًا دقيقًا في تراكم التكلفة، مما يتيح لك تحديد *متى* يتم تسجيل التكلفة—سواء في بداية العمل، بشكل مستمر، أو فقط عند إكمال العمل. يوضح هذا البرنامج التعليمي المفاهيم، ويظهر كيفية تعيين نوع التراكم، ويستعرض أفضل الممارسات لتتبع الميزانية بشكل موثوق.

## إجابات سريعة
- **ما هو الغرض الأساسي من أنواع تراكم التكلفة؟** إنها تحدد النقطة في دورة حياة المهمة التي يتم فيها الاعتراف بالتكلفة، مما يتيح تتبعًا دقيقًا للميزانية.  
- **أي قيمة تعداد تؤخر التكلفة حتى انتهاء العمل؟** `CostAccrualType.End`.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج.  
- **هل يمكنني تغيير أنواع التراكم للعديد من الموارد في آن واحد؟** نعم—قم بالتكرار عبر مجموعة `Resources` وتعيين النوع المطلوب.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ما هو نوع تراكم التكلفة؟

يخبر **نوع تراكم التكلفة** Aspose.Tasks متى يتم تطبيق تكلفة المورد على ميزانية المشروع. يتم تمثيله بتعداد `CostAccrualType` ويمكن تعيينه لكل مورد أو لكل مهمة. يضمن اختيار النوع الصحيح توافق بيانات التكلفة مع سياسات الفوترة في مؤسستك، سواء كنت تحتاج إلى تسجيل التكاليف في بداية العمل، أو توزيعها على المدة، أو فقط بعد الانتهاء.

## لماذا تتبع ميزانية المشروع باستخدام أنواع تراكم التكلفة؟

يدعم Aspose.Tasks **أربعة** خيارات للتراكم—`Start`، `Prorated`، `Duration`، و `End`—تغطي كامل نطاق سيناريوهات المحاسبة المشروعية النموذجية. يتيح لك اختيار الخيار المناسب مواءمة الاعتراف بالتكلفة مع دورات الفوترة التعاقدية، تقليل التباين في التقارير المالية، وإنشاء بيانات تكلفة تتكامل بسلاسة مع أنظمة ERP، كل ذلك مع الحفاظ على استهلاك الذاكرة منخفضًا للمشاريع الكبيرة.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك المتطلبات المسبقة التالية:

### 1. تثبيت Aspose.Tasks لـ .NET
لبدء العمل، تحتاج إلى تثبيت Aspose.Tasks لـ .NET في بيئة التطوير الخاصة بك. يمكنك تنزيل المكتبة من [صفحة التحميل](https://releases.aspose.com/tasks/net/) واتباع تعليمات التثبيت المقدمة.

### 2. الإلمام بـ .NET Framework
يتطلب معرفة أساسية بإطار عمل .NET ولغة البرمجة C# لمتابعة الأمثلة في هذا البرنامج التعليمي.

## كيفية تعيين نوع تراكم التكلفة لمورد؟

قم بتحميل المشروع، حدد المورد المستهدف، وعيّن `CostAccrualType` المطلوب. النمط المكوّن من سطرين أدناه هو النهج القياسي: إنشاء كائن `Project`، استرجاع المورد بواسطة معرّفه، ثم تعيين `CostAccrualType`. يضمن هذا التسلسل المختصر أنك **تتبع ميزانية المشروع** بدقة من لحظة إضافة المورد.

### الخطوة 1: استيراد المساحات الاسمية
لنبدأ باستيراد المساحات الاسمية اللازمة للوصول إلى وظائف Aspose.Tasks في مشروع .NET الخاص بنا:

```csharp

```

### الخطوة 2: تحميل ملف المشروع
تمثل الفئة `Project` ملف Microsoft Project وتوفر الوصول إلى مهامه، موارده، وغيرها من البيانات.

```csharp
var project = new Project("Project2.mpp");
```

أولاً، نحتاج إلى تحميل ملف المشروع إلى تطبيقنا. نقوم بإنشاء كائن `Project` جديد ونهيئه بمسار ملف المشروع.

### الخطوة 3: الوصول إلى المورد
تحتوي مجموعة `Resources` على جميع الموارد المعرفة في المشروع. تسترجع طريقة `GetById` موردًا بواسطة معرّفه الفريد.

```csharp
var resource = project.Resources.GetById(1);
```

بعد ذلك، نصل إلى المورد الذي نريد تطبيق نوع تراكم التكلفة عليه. نستخدم طريقة `GetById` من مجموعة `Resources` ونمرّر معرّف المورد كمعامل. هذا يوضح **الوصول إلى المورد بواسطة المعرف**، وهو مطلب شائع عند أتمتة تحديثات التكلفة.

### الخطوة 4: تعيين نوع تراكم التكلفة
تقوم طريقة `Set` بتعيين قيمة لحقل المورد.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

هنا، نعيّن نوع تراكم التكلفة للمورد. في هذا المثال، نعيّنه إلى `CostAccrualType.End`، مما يعني أن التكاليف لن تُتراكم حتى يصبح العمل المتبقي صفرًا. اختيار `End` مثالي عندما تريد **تتبع ميزانية المشروع** فقط بعد إكمال المهمة بالكامل.

### الخطوة 5: متابعة العمل مع المشروع
بعد تعيين نوع تراكم التكلفة، يمكنك متابعة العمل مع المشروع حسب الحاجة، وإجراء عمليات إضافية أو حسابات مثل إنشاء تقارير تكلفة، تحديث التعيينات، أو تصدير الملف.

## الأخطاء الشائعة والنصائح الاحترافية
- **نصيحة احترافية:** دائمًا استدعِ `project.Save` بعد تعديل أنواع التراكم لحفظ التغييرات.  
- **عقبة:** تعيين `CostAccrualType.Start` لمورد لا يبدأ العمل أبداً سيؤدي إلى تضخم تقارير الميزانية—تحقق من جداول المهام أولاً.  
- **نصيحة احترافية:** استخدم `project.Resources.ToList()` عندما تحتاج إلى تحديث مجموعة من الموارد دفعة واحدة؛ هذا يتجنب عمليات البحث المتكررة في المجموعة ويحسن الأداء في المشاريع الكبيرة.

## الأسئلة المتكررة

**س: هل يمكنني تغيير نوع تراكم التكلفة لعدة موارد في آن واحد؟**  
ج: نعم، قم بالتكرار عبر `project.Resources` وعيّن `CostAccrualType` المطلوب لكل مورد داخل حلقة `foreach`.

**س: ما هي أنواع تراكم التكلفة المتاحة الأخرى بخلاف `End`؟**  
ج: توفر Aspose.Tasks الأنواع `Start`، `Prorated`، و `Duration`—كل منها يتماشى مع استراتيجية فوترة مختلفة.

**س: كيف يمكنني تحديد نوع تراكم التكلفة الحالي لمورد معين؟**  
ج: استرجع القيمة عبر `resource.Get(TskResource.CostAccrualType)`؛ تُعيد التعداد الذي يمثل الإعداد الحالي.

**س: هل يمكن تطبيق أنواع تراكم تكلفة مختلفة على مهام مختلفة في نفس المشروع؟**  
ج: بالتأكيد. كل من المهام والموارد تعرض خاصية `CostAccrualType`، مما يسمح بتكوين مستقل لكل كيان.

**س: هل يدعم Aspose.Tasks أنواع تراكم تكلفة مخصصة؟**  
ج: لا، المكتبة تدعم حاليًا الأنواع الأربعة المدمجة فقط؛ يجب تنفيذ المنطق المخصص خارجيًا إذا كان مطلوبًا.

---

**آخر تحديث:** 2026-07-05  
**تم الاختبار مع:** Aspose.Tasks 24.8 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [تقويم وجدولة Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [معالجة أسعار مشروع MS باستخدام Aspose.Tasks لـ .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [إدارة موارد مشروع MS بسهولة مع Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}