---
date: 2026-07-19
description: تعرف على كيفية إضافة أنواع الحقول المخصصة في Aspose.Tasks لـ .NET مع
  كود خطوة بخطوة، المتطلبات، والأسئلة المتكررة.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: أنواع الحقول المخصصة في Aspose.Tasks
og_description: تعرف على كيفية إضافة أنواع الحقول المخصصة في Aspose.Tasks لـ .NET.
  اتبع هذا الدليل خطوة بخطوة لإنشاء وتعريف واستخدام السمات الموسعة بكفاءة.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: كيفية إضافة أنواع الحقول المخصصة في Aspose.Tasks لـ .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: كيفية إضافة أنواع الحقول المخصصة في Aspose.Tasks لـ .NET
url: /ar/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة أنواع الحقول المخصصة في Aspose.Tasks

## مقدمة

في هذا البرنامج التعليمي ستكتشف **كيفية إضافة حقل مخصص** إلى ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET. تتيح لك الحقول المخصصة تخزين معلومات إضافية—مثل درجات المخاطر، رموز الأقسام، أو ملاحظات مخصصة—مباشرةً على المهام أو الموارد أو المشروع نفسه. سنستعرض العملية بالكامل، بدءًا من إعداد البيئة إلى تعريف الحقل، إضافته، والتحقق من حقل نصي مخصص.

## إجابات سريعة
- **ما هو الحقل المخصص؟** عمود معرف من قبل المستخدم يمكنه احتواء نص، أرقام، تواريخ، أو علامات على المهام/الموارد.  
- **أي فئة تعرف الحقل المخصص؟** `ExtendedAttributeDefinition`.  
- **هل يمكنني إضافة حقل مخصص إلى مشروع موجود؟** نعم—قم بتحميل المشروع، إنشاء التعريف، ثم إضافته إلى المجموعة.  
- **هل أحتاج إلى ترخيص لـ Aspose.Tasks؟** الترخيص مطلوب للإنتاج؛ نسخة تجريبية مجانية تكفي للتقييم.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ما هو “كيفية إضافة حقل مخصص” في Aspose.Tasks؟
**كيفية إضافة حقل مخصص** تشير إلى عملية إنشاء `ExtendedAttributeDefinition` وربطه بمجموعة `ExtendedAttributes` الخاصة بالمشروع. يتيح لك ذلك تخزين بيانات وصفية إضافية ليست جزءًا من مخطط المشروع القياسي. يمكن استخدامها للمهام أو الموارد أو المشروع نفسه، مما يسمح لك بجمع معلومات مثل مستويات المخاطر، رموز الأقسام، أو ملاحظات مخصصة غير متوفرة في الحقول الافتراضية.

## لماذا نستخدم الحقول المخصصة في إدارة المشاريع؟
يدعم Aspose.Tasks **أكثر من 50 نوعًا مدمجًا من السمات الموسعة** ويسمح لك بتعريف **أي عدد من الحقول المخصصة** دون التأثير بشكل كبير على حجم الملف. باستخدام الحقول المخصصة يمكنك:  
تظهر هذه الحقول كأعمدة إضافية في Microsoft Project ويمكن الإشارة إليها في الصيغ، التقارير، والفلاتر. يتم تخزينها داخل ملف المشروع وتنتقل معه، مما يضمن أن أي أدوات لاحقة تحتفظ بالبيانات المخصصة.

## المتطلبات المسبقة

### 1. تثبيت Visual Studio
تأكد من أن Visual Studio (2019 أو أحدث) مثبت على جهازك. يمكنك تنزيله من موقع Microsoft.

### 2. Aspose.Tasks لـ .NET
أضف حزمة Aspose.Tasks NuGet إلى مشروعك. قم بتنزيل أحدث نسخة من [here](https://releases.aspose.com/tasks/net/).

### 3. معرفة أساسية بـ C#
يجب أن تكون مرتاحًا مع صياغة C#، الفئات، وبنية مشروع .NET.

## استيراد مساحات الأسماء

توجد الفئات `Project` و `ExtendedAttributeDefinition` والعدادات المرتبطة بها في مساحة الأسماء `Aspose.Tasks`. استوردها في أعلى ملفك:

توفر مساحة الأسماء `Aspose.Tasks` جميع الأنواع الأساسية للتعامل مع ملفات Microsoft Project.

```csharp

```

## كيفية إضافة حقل مخصص إلى مشروع؟

قم بتحميل المشروع الموجود، إنشاء تعريف حقل مخصص، وإضافته إلى مجموعة السمات الموسعة للمشروع—كل ذلك في ثلاث خطوات مختصرة. يعمل هذا النمط للمهام، الموارد، والمشروع نفسه، ويضمن حفظ الحقل المخصص عند حفظ الملف.

### الخطوة 1: إنشاء كائن Project
`Project` هو الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Project واحد في الذاكرة. إنشاءه يحمل الملف ويمنحك الوصول إلى المهام، الموارد، والسمات الموسعة.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### الخطوة 2: تعريف الحقل المخصص
`ExtendedAttributeDefinition` يصف عمودًا جديدًا. في هذا المثال ننشئ حقلًا مخصصًا من نوع **Text** للمهام ونعطيه الاسم المستعار “MyText”. قيمة تعداد `ExtendedAttributeTask.Text1` تخبر Aspose.Tasks أين يتم تخزين القيمة.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### الخطوة 3: إضافة تعريف الحقل المخصص إلى المشروع
تحتوي مجموعة `ExtendedAttributes` الخاصة بالمشروع على جميع تعريفات الحقول المخصصة. إضافة التعريف يجعلها متاحة لكل مهمة في المشروع.

```csharp
project.ExtendedAttributes.Add(definition);
```

## المشكلات الشائعة والحلول
- **الحقول لا تظهر في واجهة MS Project** – تأكد من ضبط خاصية `Alias`؛ يعرض MS Project الاسم المستعار كعنوان العمود.  
- **الحفظ يسبب استثناءً** – تحقق من أن ملف المشروع ليس للقراءة فقط وأن لديك ترخيصًا صالحًا.  
- **قيمة الحقول المخصصة تُفقد بعد إعادة التحميل** – تأكد من استدعاء `project.Save("output.mpp")` بعد تعيين القيم للمهام.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع أطر .NET الأخرى؟**  
ج: نعم، Aspose.Tasks يعمل مع .NET Framework و .NET Core و .NET 5/6/7.

**س: هل Aspose.Tasks مناسب لتطبيقات على مستوى المؤسسات؟**  
ج: بالتأكيد. يدعم معالجة المشاريع التي تحتوي على **حتى 10,000 مهمة** ويمكن تشغيله في بيئات خوادم متعددة الخيوط.

**س: هل يدعم Aspose.Tasks صيغ ملفات مشروع متعددة؟**  
ج: نعم—Aspose.Tasks يقرأ ويكتب صيغ MPP و XML و HTML و CSV، ويغطي **جميع إصدارات Microsoft Project الرئيسية**.

**س: هل يمكنني تعديل بيانات الموارد باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك إضافة، تحديث، وحذف الموارد، وكذلك تعيين حقول مخصصة لها.

**س: هل هناك منتدى مجتمع لمستخدمي Aspose.Tasks؟**  
ج: نعم، يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للتفاعل مع المستخدمين الآخرين والحصول على الدعم من فريق Aspose.

---

**آخر تحديث:** 2026-07-19  
**تم الاختبار مع:** Aspose.Tasks 24.12 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إتقان تعريفات السمات الموسعة في MS Project باستخدام Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [التعامل مع السمات الموسعة في MS Project باستخدام Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [مساعد الحقول لتكامل MS Project في Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}