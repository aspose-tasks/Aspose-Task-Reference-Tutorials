---
date: 2026-10-15
description: تعرف على كيفية إضافة خاصية مخصصة وإدارة خصائص المشروع المخصصة في Aspose.Tasks
  لـ .NET، مما يعزز التحكم في بيانات التعريف الخاصة بمشروعك.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: إدارة مجموعة خصائص المشروع المخصصة في Aspose.Tasks
og_description: أضف خاصية مخصصة إلى ملفات مشروعك باستخدام Aspose.Tasks لـ .NET. يوضح
  لك هذا الدليل كيفية إدارة الخصائص المخصصة، قراءتها، وإضافة قيم منطقية أو نصية بكفاءة.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: إضافة خاصية مخصصة باستخدام Aspose.Tasks .NET API للمشروعات
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: كيفية إضافة خاصية مخصصة في Aspose.Tasks لـ .NET
url: /ar/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة خاصية مخصصة في Aspose.Tasks لـ .NET

## مقدمة

يدعم إضافة الخاصية المخصصة تخزين بيانات تعريفية خاصة بالمشروع لا تغطيها الحقول المدمجة. في هذا الدرس ستتعلم كيفية **add custom property**، قراءتها مرة أخرى، وإدارة مجموعة الخصائص المخصصة بالكامل باستخدام Aspose.Tasks لـ .NET. في النهاية ستكون قادرًا على تخصيص ملفات المشروع بقيم Boolean و DateTime و Double و String التي تتوافق مع قواعد عملك.

## إجابات سريعة
- **هل يمكنني إضافة خاصية مخصصة من نوع Boolean؟** نعم – استخدم `CustomPropertyType.Boolean`.
- **كم عدد أنواع الخصائص المخصصة المدعومة؟** أربعة: Boolean، DateTime، Double، String.
- **هل مجموعة الخصائص المخصصة للقراءة فقط؟** يمكن أن تكون للقراءة فقط إذا تم تحميل المشروع من مصدر للقراءة فقط.
- **هل أحتاج إلى ترخيص لاستخدام هذه الميزة؟** ترخيص مؤقت يعمل للتقييم؛ ترخيص كامل مطلوب للإنتاج.
- **ما إصدارات .NET المتوافقة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هي الخاصية المخصصة؟

الخاصية المخصصة هي حقل بيانات تعريفية يُعرّفه المستخدم وتُرفق بكائن Project. يتيح لك تخزين معلومات إضافية مثل “Risk Level”، “Customer ID”، أو أي علم Boolean غير مغطى بالحقول القياسية في MS‑Project.

## لماذا إضافة خاصية مخصصة في Aspose.Tasks؟

يدعم Aspose.Tasks **أكثر من 50 صيغة إدخال وإخراج** ويمكنه التعامل مع مشاريع تحتوي على **ما يصل إلى 10,000 مهمة** دون تحميل الملف بالكامل إلى الذاكرة. يتيح إضافة الخصائص المخصصة دمج البيانات الحيوية للأعمال مباشرةً في ملف المشروع، مما يلغي الحاجة إلى قواعد بيانات خارجية ويضمن أن البيانات تنتقل مع المشروع.

## المتطلبات المسبقة

- Visual Studio (أي إصدار حديث) مثبت على محطة العمل الخاصة بك.  
- Aspose.Tasks for .NET – قم بتنزيله من [download link](https://releases.aspose.com/tasks/net/).  
- إلمام أساسي بصياغة C# وبنية مشروع .NET.

## استيراد مساحات الأسماء

مساحات الأسماء التالية تمنحك الوصول إلى نموذج المشروع الأساسي وواجهات برمجة تطبيقات الخصائص المخصصة.

```csharp
using Aspose.Tasks;
using System;


```

## كيفية إضافة خاصية مخصصة في Aspose.Tasks؟

لإضافة خاصية مخصصة، قم أولاً بتحميل المشروع، ثم أنشئ كائن `CustomProperty`، حدد اسمه، نوعه، وقيمته، وأخيرًا أضفه إلى مجموعة `CustomProperties` الخاصة بالمشروع. هذه العملية تدمج البيانات التعريفية مباشرةً في ملف المشروع، ويتم حفظ التغييرات عند استدعاء `project.Save(...)`.  
`CustomProperty` يمثل حقلًا واحدًا يُعرّفه المستخدم ومرفقًا بالمشروع.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### الخطوة 1: تهيئة المشروع

`Project` هو الفئة الأساسية التي تمثل ملف مشروع في Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### الخطوة 2: التحقق من جاهزية مجموعة الخصائص المخصصة

`CustomProperties` هي المجموعة التي تحتفظ بجميع كائنات الخصائص المخصصة للمشروع.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### الخطوة 3: إضافة خصائص مخصصة

طريقة `Add` تُدرج خاصية مخصصة جديدة في مجموعة المشروع.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### الخطوة 4: الوصول إلى الخصائص المخصصة

مجموعة `CustomProperties` تُطبق IEnumerable، مما يسمح بالتكرار على كل `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### الخطوة 5: استرجاع قيمة خاصية مخصصة

طريقة `Get` تُعيد قيمة الخاصية المخصصة بناءً على اسمها.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### الخطوة 6: التكرار على أسماء الخصائص المخصصة

خاصية `Names` تُوفر قائمة بجميع أسماء الخصائص المخصصة في المجموعة.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### الخطوة 7: إزالة أو مسح الخصائص المخصصة

طريقة `Remove` تحذف خاصية معينة، بينما `Clear` تُفرغ المجموعة بالكامل.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## المشكلات الشائعة واستكشاف الأخطاء

- **مجموعة للقراءة فقط** – إذا أعادت `project.CustomProperties.IsReadOnly` القيمة `true`، تأكد من أن ملف المصدر ليس مفتوحًا بوصول قراءة حصري أو انسخه إلى موقع قابل للكتابة قبل التعديل.  
- **عدم تطابق النوع** – تعيين قيمة لا تتطابق مع `CustomPropertyType` المعلن يسبب استثناء `ArgumentException`. يجب دائمًا تعيين `Value` بعد تعريف `Type` الصحيح.  
- **حفظ التغييرات** – بعد إضافة أو إزالة الخصائص، استدعِ `project.Save("output.mpp")` لتثبيت التعديلات؛ وإلا ستبقى التغييرات في الذاكرة فقط.

## الأسئلة المتكررة

**س: هل يمكنني إضافة خصائص مخصصة من أي نوع بيانات إلى مشروعي باستخدام Aspose.Tasks لـ .NET؟**  
A: نعم، يمكنك إضافة خصائص مخصصة تدعم الأنواع Boolean و DateTime و Double و String.

**س: هل من الممكن التكرار على أسماء الخصائص المخصصة في Aspose.Tasks لـ .NET؟**  
A: بالتأكيد، يمكنك التكرار على أسماء الخصائص المخصصة باستخدام الخاصية `Names`.

**س: كيف يمكنني إزالة خاصية مخصصة معينة من مشروعي؟**  
A: يمكنك إزالة خاصية مخصصة بواسطة اسمها باستخدام طريقة `Remove`.

**س: هل يوفر Aspose.Tasks لـ .NET دعمًا للتراخيص المؤقتة؟**  
A: نعم، يمكنك الحصول على ترخيص مؤقت من موقع Aspose للتقييم.

**س: أين يمكنني العثور على الدعم أو المساعدة الإضافية بخصوص Aspose.Tasks لـ .NET؟**  
A: يمكنك زيارة منتدى Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) لأي استفسارات أو مساعدة.

---

**آخر تحديث:** 2026-10-15  
**تم الاختبار مع:** Aspose.Tasks 24.11 for .NET  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [كيفية قراءة خصائص المشروع المدمجة باستخدام Aspose.Tasks لـ .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [إدارة مجموعة سمات MS Project في Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [أنواع الحقول المخصصة في Aspose.Tasks – التقويم والجدولة](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}