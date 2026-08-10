---
date: 2026-03-24
description: تعلم كيفية ضبط الحساب في Aspose.Tasks لـ .NET، مع أمثلة لحساب القيم الملخصة،
  وتعريف صيغة الحساب، وتكوين ملخص التجميع.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية تعيين نوع الحساب في Aspose.Tasks
url: /ar/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين نوع الحساب في Aspose.Tasks

## المقدمة

إذا كنت بحاجة إلى **كيفية تعيين قواعد الحساب** للمهام وصفوف الملخص في ملف Microsoft Project، فإن هذا الدليل يوضح لك ذلك باستخدام Aspose.Tasks for .NET. سنستعرض مثالًا كاملًا على **نوع الحساب**، ونظهر كيفية **حساب قيم الملخص**، ونشرح كيفية **تعريف صيغة الحساب** و**تكوين ملخص التجميع** للسمات الموسعة. في النهاية، ستتمكن من إضافة مهمة إلى مشروع، وتعيين منطق حساب مخصص، والتحكم في سلوك التجميع بثقة.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** التحكم في كيفية حساب قيم المهام والملخصات في ملف Project.  
- **أي فئة API تُستخدم؟** `ExtendedAttributeDefinition` مع `CalculationType` و `SummaryRowsCalculationType`.  
- **هل يمكنني استخدام صيغة؟** نعم – عيّن `CalculationType = CalculationType.Formula` وقدم سلسلة الصيغة.  
- **كيف أقوم بتجميع قيم الملخص؟** استخدم `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` وحدد `RollupType` مثل `Average`.  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في بيئة الإنتاج.

## ما هو نوع الحساب وكيفية تعيينه؟

`CalculationType` يخبر Aspose.Tasks كيف يحسب قيمة السمة الموسعة. يمكنك اختيار قيمة ثابتة، أو صيغة، أو ترك المكتبة تقوم بتجميع القيم من المهام الفرعية. تعيين الحساب بشكل صحيح أمر أساسي عندما تريد أن يعكس المشروع قواعد عمل مخصصة دون تحديثات يدوية.

## لماذا نستخدم نوع الحساب لحساب قيم الملخص؟

عند وجود مهام ملخص في المشروع، غالبًا ما تحتاج صفوف الملخص إلى إظهار بيانات مجمعة (مثل التكلفة الكلية، متوسط المدة). من خلال تكوين **حساب قيم الملخص** عبر `SummaryRowsCalculationType` و `RollupType`، يمكن لـ Aspose.Tasks الحفاظ تلقائيًا على هذه التجميعات متزامنة مع تعديل المهام الفردية.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. معرفة أساسية بلغة C# وإطار عمل .NET.  
2. تثبيت Visual Studio (أي نسخة حديثة) على جهازك.  
3. تثبيت مكتبة Aspose.Tasks for .NET – يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/net/).  
4. الوصول إلى وثائق Aspose.Tasks for .NET الرسمية للرجوع إليها، المتاحة [هنا](https://reference.aspose.com/tasks/net/).

## استيراد المساحات الاسمية

قبل الغوص في المثال، تأكد من استيراد المساحات الاسمية اللازمة:

```csharp
using Aspose.Tasks;
using System;
```

## الخطوة 1: إنشاء مشروع جديد

أولاً، نقوم بإنشاء كائن `Project` فارغ سيحمل مهامنا والسمات المخصصة.

```csharp
var project = new Project();
```

## الخطوة 2: إضافة مهمة إلى المشروع

الآن **نضيف بيانات مهمة** بإنشاء مهمة بسيطة، وتعيين تاريخ البدء لها، ومنحها مدة يوم واحد.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## الخطوة 3: تعريف نوع الحساب لسمة موسعة (مثال صيغة)

هنا ننشئ تعريف سمة موسعة تُحسب قيمتها من صيغة. يوضح هذا **مثال نوع الحساب** ويظهر كيفية **تعريف صيغة الحساب**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## الخطوة 4: تعريف نوع الحساب لصفوف الملخص (تكوين ملخص التجميع)

بعد ذلك، ننشئ تعريف سمة موسعة آخر يخبر Aspose.Tasks **بتكوين ملخص التجميع** باستخدام نوع التجميع *Average*. هذه هي الطريقة النموذجية لـ **حساب قيم الملخص** للتكلفة أو العمل أو الحقول المخصصة.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| الصيغة تُعيد `null` | إشارة حقل غير صحيحة في الصيغة | تحقق من اسم الحقل داخل الأقواس (مثال: `[Start]` وليس `[stARt]`). |
| صفوف الملخص تظهر 0 | لم يتم تعيين `SummaryRowsCalculationType` أو تم اختيار `RollupType` غير صحيح | تأكد من `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` واختر `RollupType` مناسب. |
| فشل تحميل المشروع بعد إضافة السمات | عدم توافق بين تعريف السمة واستخدامها في المهمة | أضف تعريف السمة **قبل** تعيينها لأي مهمة. |

## الخلاصة

في هذا الدليل، غطينا **كيفية تعيين قواعد الحساب** في Aspose.Tasks for .NET، بدءًا من إنشاء مهمة بسيطة إلى تعريف أنواع حساب تعتمد على الصيغ أو التجميع. من خلال إتقان هذه الإعدادات، تحصل على تحكم دقيق في **حساب قيم الملخص**، مما يتيح تحليلات مشروع أغنى دون الحاجة إلى جداول بيانات يدوية.

## الأسئلة المتكررة

### س1: ما هو نوع الحساب في Aspose.Tasks؟

ج1: نوع الحساب في Aspose.Tasks يحدد كيفية حساب القيم للمهام والمهام الملخصة داخل المشروع، مع خيارات مثل الصيغة (Formula) والتجميع (Rollup).

### س2: كيف يمكنني تعيين نوع الحساب لسمة موسعة؟

ج2: يمكنك تعيين نوع الحساب لسمة موسعة عن طريق تحديد خاصية `CalculationType` الخاصة بها وفقًا لما تحتاجه.

### س3: هل يمكنني تخصيص نوع الحساب لصفوف الملخص في المشروع؟

ج3: نعم، يتيح لك Aspose.Tasks تحديد نوع الحساب لصفوف الملخص، مما يمكنك من تعديل حساب القيم وفقًا لمتطلباتك.

### س4: هل هناك أنواع تجميع مختلفة متاحة لحسابات مهام الملخص؟

ج4: نعم، يوفر Aspose.Tasks أنواع تجميع متعددة مثل Average و Sum و Count لحساب قيم مهام الملخص.

### س5: أين يمكنني العثور على المزيد من الموارد حول Aspose.Tasks for .NET؟

ج5: يمكنك استكشاف الوثائق ومنتديات الدعم المجتمعي المتاحة على [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) للحصول على إرشادات شاملة ومساعدة.

---

**آخر تحديث:** 2026-03-24  
**تم الاختبار مع:** Aspose.Tasks for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}