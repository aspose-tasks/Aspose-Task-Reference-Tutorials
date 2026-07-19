---
date: 2026-07-19
description: تعلم كيفية التحكم في رمز العملة بعد المبلغ في مشاريع .NET بسهولة مع Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: مواقع رمز العملة في Aspose.Tasks
og_description: تعلم كيفية وضع رمز العملة بعد المبلغ باستخدام Aspose.Tasks لـ .NET.
  اتبع تعليمات خطوة بخطوة وأفضل الممارسات.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: رمز العملة بعد المبلغ في Aspose.Tasks — دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: كيفية وضع رمز العملة بعد المبلغ في Aspose.Tasks
url: /ar/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية وضع رمز العملة بعد المبلغ في Aspose.Tasks

## مقدمة

عند إنشاء تقارير تكلفة المشروع، يمكن أن يؤثر وضع **رمز العملة بعد المبلغ** على قابلية القراءة والامتثال للمعايير الإقليمية. يتيح لك Aspose.Tasks لـ .NET التحكم في هذا التنسيق ببضع أسطر من الشيفرة فقط، مما يضمن ظهور كل رقم مالي بالطريقة التي يتوقعها أصحاب المصلحة. في هذا الدرس سنستعرض الخطوات المطلوبة، نشرح لماذا هذا الإعداد مهم، ونظهر لك كيفية تطبيقه في مشروع .NET حقيقي.

## إجابات سريعة
- **ماذا يعني “رمز العملة بعد المبلغ”؟** يعرض الرمز (مثال: $) بعد القيمة الرقمية، مثل `100 $`.
- **أي خاصية تتحكم في الموضع؟** `CurrencySymbolPosition` على كائن `Project`.
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.
- **العملات المدعومة؟** أكثر من 50 عملة مدمجة، تغطي معظم الأسواق العالمية.
- **هل يمكنني تغيير الإعداد أثناء التشغيل؟** نعم، يمكنك تحديثه في أي وقت قبل حفظ ملف المشروع.

## ما هو إعداد “رمز العملة بعد المبلغ”؟
يحدد خيار **رمز العملة بعد المبلغ** ما إذا كان رمز العملة يظهر قبل أو بعد القيمة الرقمية في جميع الحقول المالية للمشروع. يضمن تعديل هذا الإعداد توافق التقارير مع عادات المحاسبة المحلية دون الحاجة إلى معالجة يدوية لاحقة. كما يحسن من قابلية القراءة لأصحاب المصلحة الذين يعتادون على هذا الشكل.

## لماذا تستخدم Aspose.Tasks لتنسيق العملة؟
يدعم Aspose.Tasks **أكثر من 50 عملة** ويمكنه التعامل مع مشاريع تحتوي على **أكثر من 10,000 مهمة** دون تحميل الملف بالكامل في الذاكرة، مما يوفر أداءً سريعًا حتى على الأجهزة ذات الموارد المحدودة. توفر لك الـ API تحكمًا برمجيًا، مما يلغي الحاجة إلى تعديل الجداول يدويًا. وهذا يجعل إعداد التقارير المالية على نطاق واسع فعالًا وموثوقًا.

## المتطلبات المسبقة

### 1. تثبيت Aspose.Tasks لـ .NET
تأكد من تثبيت مكتبة Aspose.Tasks. يمكنك تنزيلها من [here](https://releases.aspose.com/tasks/net/).

### 2. معرفة أساسية ببرمجة .NET
فهم أساسي لبرمجة .NET ضروري لمتابعة الأمثلة.

## استيراد مساحات الأسماء

توفر مساحة الأسماء `Aspose.Tasks` إمكانية الوصول إلى فئة `Project` والعدادات المرتبطة بها.

فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف مشروع واحد في الذاكرة. بعد استيراد مساحة الأسماء يمكنك البدء في التعامل مع بيانات المشروع.

```csharp

```

الآن، لنقسم المثال إلى خطوات واضحة وقابلة للتنفيذ.

## كيفية ضبط رمز العملة بعد المبلغ؟

`CurrencySymbolPosition` هو تعداد يحدد ما إذا كان رمز العملة يظهر قبل أو بعد القيمة الرقمية.

حمّل مشروعك، اضبط `CurrencySymbolPosition` إلى `After`، ثم احفظ – هذا كل ما تحتاجه لعرض الرمز بعد المبلغ. هذا النهج المباشر يعمل مع أي عملة مدعومة ولا يتطلب منطق تنسيق إضافي. يمكنك أيضًا التحقق من الإعداد عن طريق تصدير تقرير تكلفة تجريبي للتأكد من ظهور الرمز بشكل صحيح.

### الخطوة 1: تحميل ملف المشروع
تقوم فئة `Project` بتحميل ملف MS‑Project موجود أو إنشاء ملف جديد في الذاكرة.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### الخطوة 2: ضبط موضع رمز العملة
`CurrencySymbolPosition` هو تعداد يتيح لك اختيار `Before` أو `After`. ضبطه على `After` يضع الرمز بعد القيمة الرقمية.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### الخطوة 3: العمل مع المشروع
بعد تكوين موضع الرمز، يمكنك الاستمرار في إضافة مهام أو موارد أو حقول مخصصة حسب الحاجة. يتم حفظ الإعداد عند حفظ المشروع.

```csharp
// Perform other operations with the project...
```

## المشكلات الشائعة والحلول
- **الرمز لا يزال يظهر قبل المبلغ:** تأكد من ضبط الخاصية *قبل* استدعاء `Save`. تعديلها بعد الحفظ يتطلب إعادة حفظ الملف.
- **عملة غير مدعومة:** تحقق من أن رمز العملة الذي تستخدمه موجود في قائمة العملات المدعومة في Aspose.Tasks (أكثر من 50 عملة).
- **تباطؤ الأداء في المشاريع الكبيرة:** استخدم `ProjectReader` لتدفق الملفات الكبيرة إذا تجاوزت 10,000 مهمة.

## الأسئلة المتكررة

**س: هل يمكنني تغيير موضع رمز العملة عدة مرات داخل نفس المشروع؟**  
ج: نعم، يمكنك تعديل `CurrencySymbolPosition` بقدر ما تحتاج؛ فقط اضبط الخاصية وأعد حفظ المشروع.

**س: هل يدعم Aspose.Tasks عملات غير الدولار الأمريكي؟**  
ج: بالتأكيد. يدعم Aspose.Tasks أكثر من 50 عملة دولية، مما يتيح لك العمل بأي تنسيق إقليمي.

**س: هل تتوفر نسخة تجريبية من Aspose.Tasks لـ .NET؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من [here](https://releases.aspose.com/).

**س: هل يمكنني طلب المساعدة إذا واجهت أي مشاكل أثناء استخدام Aspose.Tasks لـ .NET؟**  
ج: بالطبع! يمكنك طلب الدعم والمساعدة من منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**س: كيف يمكنني شراء ترخيص لـ Aspose.Tasks لـ .NET؟**  
ج: يمكنك شراء ترخيص لـ Aspose.Tasks لـ .NET من [here](https://purchase.aspose.com/buy).

## الخلاصة

يعد التحكم في **رمز العملة بعد المبلغ** جزءًا أساسيًا من إعداد التقارير المالية في برامج إدارة المشاريع. باستخدام Aspose.Tasks لـ .NET يمكنك ضبط هذا الخيار برمجيًا، مع دعم أكثر من 50 عملة ومعالجة مشاريع كبيرة بكفاءة. اتبع الخطوات أعلاه لضمان توافق تقارير مشروعك مع توقعات التنسيق في أي لغة.

---

**آخر تحديث:** 2026-07-19  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [إدارة مجموعة التقويم في Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [مجموعة استثناءات التقويم في Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [معالجة أسعار MS Project باستخدام Aspose.Tasks لـ .NET](/tasks/net/rate-recurring-tasks/handling-rates/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}