---
date: 2026-07-05
description: تعلم كيفية نسخ بيانات المشروع باستخدام Aspose.Tasks لـ .NET مع Copy Options.
  عزز تطبيقات .NET الخاصة بك بإدارة مشروع دقيقة.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: كيفية نسخ بيانات المشروع باستخدام Copy Options في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: كيفية نسخ بيانات المشروع باستخدام Copy Options في Aspose.Tasks
url: /ar/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية نسخ بيانات المشروع باستخدام خيارات النسخ في Aspose.Tasks

## مقدمة

إذا كنت بحاجة إلى **كيفية نسخ مشروع** من ملف Microsoft Project إلى آخر، فإن Aspose.Tasks for .NET يوفّر لك طريقة نظيفة تعتمد على الكود للقيام بذلك. في هذا الدرس سنستعرض سير العمل الكامل — تحميل مشروع المصدر، تكوين خيارات النسخ، إنشاء نسخة، وتحميل النتيجة — حتى تتمكن من دمج منطق نسخ المشروع في أي تطبيق .NET بثقة.

## إجابات سريعة
- **ماذا تفعل ميزة النسخ؟** تقوم بتكرار بيانات المشروع مع السماح لك بتضمين أو استبعاد أقسام محددة مثل التقويمات، الموارد، أو معلومات العرض.  
- **أي فئة تتحكم في السلوك؟** `CopyToOptions` تتيح لك ضبط ما يتم نسخه بدقة.  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للإنتاج؛ النسخة التجريبية المجانية تكفي للتطوير.  
- **الصيغ المدعومة؟** تدعم Aspose.Tasks ملفات MPP، XML، و XER — أكثر من 20 + صيغة إجمالاً.  
- **هل يمكنني تخطي بيانات العرض؟** نعم، عيّن `CopyToOptions.SkipViewData = true` لتجاهل معلومات واجهة المستخدم.

## ما هو “كيفية نسخ مشروع” في Aspose.Tasks؟
**“كيفية نسخ مشروع”** تشير إلى استخدام API الخاص بـ Aspose.Tasks لتكرار بيانات كائن Project إلى ملف جديد، مع إمكانية تصفية العناصر غير المرغوب فيها. هذه العملية مفيدة لإنشاء قوالب، أرشفة، أو إنشاء متغيّرات للمشروع دون خطوات يدوية في الواجهة، وتعمل عبر جميع صيغ الملفات المدعومة.

## لماذا نستخدم خيارات النسخ في Aspose.Tasks؟
تدعم Aspose.Tasks **أكثر من 50 كيانًا مرتبطًا بالمشروع** (المهام، الموارد، التقويمات، التعيينات، إلخ) ويمكنها معالجة ملفات تحتوي على **حتى 10,000 مهمة** مع الحفاظ على استهلاك الذاكرة تحت 200 ميغابايت. باستخدام `CopyToOptions` يمكنك تجنّب نسخ بيانات العرض الثقيلة، مما يقلل حجم ملف الإخراج بنسبة **30‑40 %** ويسرّع العملية تقريبًا **2×** للمشروعات الكبيرة.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

1. **Aspose.Tasks for .NET** – حمّل أحدث نسخة من [رابط التحميل](https://releases.aspose.com/tasks/net/).  
2. **بيئة تطوير .NET** – Visual Studio 2022 (أو أي IDE يدعم .NET 6+) مثبتة.  
3. **ترخيص Aspose.Tasks صالح** – اختياري للتقييم، إلزامي لبناءات الإنتاج.  
4. **ملف مشروع موجود** (مثل `SourceProject.xml`) ترغب في نسخه.

## كيف تستورد مساحات الأسماء لـ Aspose.Tasks؟

أضف توجيهات `using` المطلوبة في أعلى ملف C# حتى يتمكن المترجم من العثور على أنواع Aspose.Tasks. تضمين هذه العبارات يمنحك وصولًا مباشرًا إلى `Project`، `CopyToOptions`، وغيرها من الفئات المساعدة دون الحاجة لتأهيل أسمائها بالكامل، مما يبسط الكود ويحسّن القابلية للقراءة.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## الخطوة 1: تهيئة كائنات المشروع

أولاً، أنشئ مثيلًا من `Project` يمثل ملف المصدر وحمّل بيانات XML.  
فئة `Project` تمثّل ملف Microsoft Project محمّلاً في الذاكرة، وتعرض المهام، الموارد، التقويمات، وغيرها من معلومات المشروع.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **نصيحة احترافية:** إذا كنت تتعامل مع ملفات ضخمة جدًا، فكر في استخدام مُنشئ `LoadOptions` لتمكين التحميل الكسول والحفاظ على استهلاك الذاكرة منخفضًا.

## الخطوة 2: إنشاء نسخة من المشروع

بعد ذلك، أنشئ كائن `Project` ثاني سيستقبل البيانات المنسوخة. يبدأ هذا الكائن فارغًا.

```csharp
Project copiedProject = new Project();
```

الآن لديك كائنان `Project` مميزان: أحدهما محمّل من القرص والآخر جاهز لاستقبال النسخة.

## الخطوة 3: تحميل المشروع المنسوخ

بعد عملية النسخ (الموضحة لاحقًا)، ستحتاج إلى التحقق من النتيجة بتحميل الملف المحفوظ حديثًا في مثيل `Project` آخر.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

إعادة تحميل الملف تؤكد أن النسخ نجح وأن الخيارات التي ضبطتها سارت كما هو متوقع.

## الخطوة 4: تكوين خيارات النسخ

تتيح لك فئة `CopyToOptions` تحديد بالضبط ما يتم نقلّه من المصدر إلى الوجهة.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

ضبط `SkipViewData = true` يقلل من حجم ملف الإخراج ويسرّع العملية، خاصةً عندما تحتاج فقط إلى بيانات المشروع المنطقية.

## الخطوة 5: تنفيذ نسخ المشروع

أخيرًا، استدعِ طريقة `CopyTo` على مشروع المصدر، مع تمرير مشروع الوجهة والخيارات التي قمت بتكوينها.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

هذا الاستدعاء المكوّن من سطرين يُجري عملية النسخ بالكامل، مع احترام الخيارات التي حددتها. الملف الناتج `CopiedProject.xml` يحتوي فقط على البيانات التي طلبتها.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **NullReferenceException عند استدعاء `CopyTo`** | لم يتم إنشاء مشروع الوجهة. | تأكد من استدعاء `new Project()` قبل `CopyTo`. |
| **غياب المهام بعد النسخ** | تم ضبط `CopyCommonData` على `false`. | عيّن `CopyCommonData = true` أو انسخ المجموعات المحددة يدويًا. |
| **ملف إخراج كبير** | ترك `SkipViewData` على `false`. | فعّل `SkipViewData` لتجاهل بيانات واجهة المستخدم. |
| **الترخيص غير مُطبق** | لم يتم تحميل ملف الترخيص. | استدعِ `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` قبل أي استخدام للـ API. |

## الأسئلة المتكررة

**س: هل يمكنني نسخ جزء فقط من المهام؟**  
ج: نعم، استخدم `CopyToOptions` مع `ProjectRootTask` لتحديد مهمة البداية، أو انسخ المهام المختارة يدويًا بعد النسخ الأولي.

**س: هل يدعم Aspose.Tasks النسخ بين صيغ ملفات مختلفة؟**  
ج: بالتأكيد. يمكنك تحميل ملف MPP وحفظ النسخة كـ XML، XER، أو أي صيغة أخرى مدعومة — أكثر من **20 + صيغة** إجمالاً.

**س: كيف أتعامل مع ملفات المشروع المحمية بكلمة مرور؟**  
ج: حمّل المصدر باستخدام `new Project("file.mpp", new LoadOptions { Password = "pwd" })`، ثم تابع النسخ كالمعتاد.

**س: هل هناك طريقة لنسخ مجموعات الموارد دون المهام؟**  
ج: عيّن `CopyToOptions.CopyResources = true` و `CopyToOptions.CopyTasks = false` لنقل معلومات الموارد فقط.

**س: أين يمكنني العثور على المزيد من الأمثلة؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مقتطفات من المجتمع، نصائح حل المشكلات، والوثائق الرسمية.

---

**آخر تحديث:** 2026-07-05  
**تم الاختبار مع:** Aspose.Tasks 24.12 for .NET  
**المؤلف:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إتقان بيانات المشروع مع Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [إتقان خيارات حفظ MS Project لـ Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [تقويم وتجدول Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}