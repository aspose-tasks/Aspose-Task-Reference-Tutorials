---
date: 2026-06-30
description: تعلم كيفية تعيين نوع القيد C# باستخدام Aspose.Tasks لـ .NET لإدارة جداول
  المشاريع بفعالية وتطبيق قيود متعددة.
keywords:
- set constraint type c#
- how to apply multiple constraints
- load project file c#
linktitle: أنواع القيود في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  headline: Set Constraint Type C# with Aspose.Tasks
  type: TechArticle
- description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  name: Set Constraint Type C# with Aspose.Tasks
  steps:
  - name: Visual Studio installed on your workstation.
    text: Visual Studio installed on your workstation.
  - name: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
    text: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
  - name: Basic knowledge of C# programming.
    text: Basic knowledge of C# programming.
  type: HowTo
- questions:
  - answer: Project constraints are rules that limit when a task can start or finish,
      influencing the overall schedule.
    question: What are project constraints?
  - answer: Aspose.Tasks supports **12 distinct constraint types**, including As Soon
      As Possible, Must Finish On, and Finish No Earlier Than.
    question: How many types of constraints does Aspose.Tasks support?
  - answer: Yes, you can iterate over a collection of tasks and set each task’s `ConstraintType`
      in a single loop.
    question: Can I apply constraints to multiple tasks simultaneously?
  - answer: Absolutely—Aspose.Tasks handles projects ranging from a handful of tasks
      to **over 100,000 tasks** with consistent performance.
    question: Is Aspose.Tasks suitable for both small and large‑scale projects?
  - answer: You can get support by visiting their [forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: تعيين نوع القيد C# باستخدام Aspose.Tasks
url: /ar/net/calendar-scheduling/constraint-types/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين نوع القيد C# باستخدام Aspose.Tasks

عندما تحتاج إلى **تعيين نوع القيد C#** في جدول مشروع، توفر لك Aspose.Tasks لـ .NET طريقة نظيفة برمجية للتحكم في تواريخ المهام. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة — تحميل مشروع، تطبيق قيد، وحفظ النتيجة — حتى تتمكن من إدارة الجداول البسيطة والمعقدة بثقة.

## إجابات سريعة
- **ماذا يفعل “تعيين نوع القيد C#”?** يassign قاعدة جدولة (مثل As Soon As Possible) لمهمة، محدداً كيفية حساب تواريخها.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج.  
- **هل يمكنني تطبيق قيود متعددة في آن واحد؟** يمكنك التكرار عبر المهام وتعيين قيم `ConstraintType` مختلفة في تمريرة واحدة.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **من أين أحصل على المكتبة؟** حمّلها من الموقع الرسمي لـ Aspose (انظر المتطلبات المسبقة).

## ما هو تعيين نوع القيد C#؟
تعيين نوع القيد في C# يعني إسناد قيمة من تعداد `ConstraintType` إلى خاصية `ConstraintType` للمهمة. هذا يخبر محرك الجدولة ما إذا كانت المهمة يجب أن تبدأ بأسرع وقت ممكن، أو تنتهي بحلول تاريخ معين، أو تتبع أي قاعدة أخرى معرفة بواسطة القيد.

## لماذا نستخدم أنواع القيود في جدولة المشروع؟
تدعم Aspose.Tasks **أكثر من 30 نوعًا من القيود** ويمكنها معالجة مشاريع تحتوي على **حتى 100,000 مهمة** دون تأثير ملحوظ على الأداء. يتيح لك استخدام القيود فرض قواعد الأعمال — مثل “يجب البدء في تاريخ محدد” أو “الانتهاء ليس بعد الموعد النهائي” — مباشرةً في الشيفرة، مما يلغي التعديلات اليدوية.

## المتطلبات المسبقة

1. تثبيت Visual Studio على جهاز العمل الخاص بك.  
2. مكتبة Aspose.Tasks لـ .NET – حمّلها من [هنا](https://releases.aspose.com/tasks/net/).  
3. معرفة أساسية ببرمجة C#.

## استيراد مساحات الأسماء

توفر لك مساحات الأسماء التالية الوصول إلى واجهة برمجة التطبيقات الأساسية للجدولة:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
```

*فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project في الذاكرة.*  

## كيفية تحميل ملف مشروع في C#؟
فئة `Project` تمثل ملف Microsoft Project في الذاكرة، مما يتيح لك قراءة وتعديل محتوياته دون قفل الملف الأصلي. حمّل مشروعك الحالي (أو أنشئ مشروعًا جديدًا) بتمرير مسار الملف إلى المُنشئ، الذي يقوم بتحليل بيانات .mpp ويجهز نموذج الكائن للعمليات اللاحقة.

## الخطوة 1: تحميل ملف المشروع

```csharp
var project = new Project("PathToYourProjectFile");
```

## كيفية تعيين نوع قيد لمهمة في C#؟
يحدد تعداد `ConstraintType` القيود الجدولة الممكنة التي يمكن تطبيقها على مهمة. استخدم هذا التعداد لتحديد القاعدة التي تحتاجها، ثم اسندها إلى خاصية `ConstraintType` للمهمة. هذه السطر الواحد هو جوهر عملية تعيين نوع القيد C#، حيث يوجه المجدول حول كيفية حساب تواريخ البدء والانتهاء.

## الخطوة 2: تعيين نوع القيد

بعد ذلك، حدد نوع القيد الذي تريد تطبيقه على مهمة معينة. في هذا المثال، سنعين نوع القيد كـ **As Soon As Possible**:

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## كيفية حفظ المشروع بعد تعيين القيود؟
طريقة `Save` تكتب بيانات المشروع إلى ملف بالتنسيق المحدد، مثل PDF أو XML. بعد تطبيق القيد، استدعِ هذه الطريقة مع `SaveOptions` المناسبة لإنشاء ملف الإخراج. تسجل هذه العملية جميع التغييرات، بما في ذلك معلومات القيد، مما يضمن أن الجدول المحفوظ يعكس قواعد المهمة المحدثة.

## الخطوة 3: حفظ المشروع

بعد تعيين القيد، يمكنك حفظ ملف المشروع. لنحفظه كملف PDF:

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## المشكلات الشائعة والحلول

- **القيد غير مطبق:** تأكد من تعديل كائن `Task` الصحيح (تحقق من `Task.Id`).  
- **تواريخ غير متوقعة بعد الحفظ:** تحقق من أن تقويم المشروع يتطابق مع أيام العمل والعطلات المقصودة.  
- **تباطؤ الأداء في الملفات الكبيرة:** استخدم `Project.Set(LoadOptions.DisableCache, true)` لتقليل استهلاك الذاكرة عند العمل على مشاريع ضخمة جدًا.

## الأسئلة المتكررة

**س: ما هي قيود المشروع؟**  
ج: قيود المشروع هي قواعد تحدد متى يمكن للمهمة أن تبدأ أو تنتهي، مما يؤثر على الجدول الزمني العام.

**س: كم عدد أنواع القيود التي تدعمها Aspose.Tasks؟**  
ج: تدعم Aspose.Tasks **12 نوعًا مميزًا من القيود**، بما في ذلك As Soon As Possible، Must Finish On، و Finish No Earlier Than.

**س: هل يمكنني تطبيق القيود على مهام متعددة في آن واحد؟**  
ج: نعم، يمكنك التكرار عبر مجموعة من المهام وتعيين `ConstraintType` لكل مهمة في حلقة واحدة.

**س: هل Aspose.Tasks مناسبة للمشاريع الصغيرة والكبيرة على حد سواء؟**  
ج: بالتأكيد — تتعامل Aspose.Tasks مع مشاريع تتراوح من عدد قليل من المهام إلى **أكثر من 100,000 مهمة** بأداء ثابت.

**س: أين يمكنني الحصول على دعم للاستفسارات المتعلقة بـ Aspose.Tasks؟**  
ج: يمكنك الحصول على الدعم بزيارة [المنتدى](https://forum.aspose.com/c/tasks/15).

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## دروس ذات صلة

- [تقويم وجدولة Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [تكوين أنواع تاريخ بدء المهمة في Aspose.Tasks](/tasks/net/task-table-management/task-start-date-types/)
- [استخراج معلومات ملف MS Project في Aspose.Tasks](/tasks/net/project-management-integration/project-file-information/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}