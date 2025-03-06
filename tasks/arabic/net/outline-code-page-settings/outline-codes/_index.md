---
title: إدارة رموز المخطط التفصيلي للمشروع في Aspose.Tasks لـ .NET
linktitle: إدارة رموز المخطط التفصيلي في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعلم كيفية إدارة رموز المخطط التفصيلي لـ MS Project باستخدام Aspose.Tasks لـ .NET. تبسيط تنظيم المشروع دون عناء.
type: docs
weight: 10
url: /ar/net/outline-code-page-settings/outline-codes/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إدارة أكواد المخطط التفصيلي لـ Microsoft Project باستخدام Aspose.Tasks لـ .NET. رموز المخطط التفصيلي هي حقول مخصصة في Microsoft Project تسمح للمستخدمين بتصنيف المهام وتنظيمها وفقًا لمعايير محددة. يعمل Aspose.Tasks على تبسيط عملية قراءة رموز المخطط التفصيلي هذه ومعالجتها برمجيًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[موقع إلكتروني](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير مناسبة لبرمجة .NET، مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا لفهم أمثلة التعليمات البرمجية.

## استيراد مساحات الأسماء
للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. يتيح لك هذا الوصول إلى الفئات والأساليب التي توفرها مكتبة Aspose.Tasks.
1. افتح Visual Studio: قم بتشغيل Visual Studio IDE الخاص بك.
2. إنشاء مشروع جديد: ابدأ مشروع C# جديدًا أو افتح مشروعًا موجودًا حيث تنوي استخدام Aspose.Tasks.
3. إضافة مرجع Aspose.Tasks: انقر بزر الماوس الأيمن على مشروعك في Solution Explorer، وحدد "إدارة حزم NuGet"، وابحث عن "Aspose.Tasks"، وقم بتثبيت الإصدار الأحدث.
4. استيراد مساحة اسم Aspose.Tasks: في الجزء العلوي من ملف C# الخاص بك، أضف ما يلي باستخدام التوجيه:
```csharp
using Aspose.Tasks;
using System;

```
## الخطوة 1: تحديد دليل المستندات
أولاً، قم بتعيين المسار إلى الدليل الذي يحتوي على ملف MS Project الخاص بك.
```csharp
String DataDir = "Your Document Directory";
```
 يستبدل`"Your Document Directory"` مع المسار الفعلي لملف المشروع الخاص بك.
## الخطوة 2: تحميل ملف المشروع
 إنشاء مثيل جديد`Project` الكائن عن طريق تحميل ملف MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
يؤدي هذا إلى تهيئة كائن المشروع بالملف المحدد.
## الخطوة 3: قراءة رموز المخطط التفصيلي
قم بالتكرار خلال كافة المهام في المشروع واسترجاع رموز المخطط التفصيلي الخاصة بها.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
يتكرر مقتطف التعليمات البرمجية هذا خلال كل مهمة، ويتحقق مما إذا كانت تحتوي على رموز مخطط تفصيلي، ويطبع تفاصيل مثل معرف الحقل، ومعرف القيمة، ومعرف القيمة لكل رمز مخطط تفصيلي مرتبط بالمهمة.

## خاتمة
في الختام، يوفر Aspose.Tasks for .NET إمكانات قوية لإدارة رموز المخطط التفصيلي لـ Microsoft Project برمجيًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك قراءة رموز المخطط التفصيلي ومعالجتها بكفاءة في ملفات MS Project باستخدام لغة C#.
## الأسئلة الشائعة
### س: هل يمكنني تعديل رموز المخطط التفصيلي باستخدام Aspose.Tasks؟
ج: نعم، يمكنك تعديل رموز المخطط التفصيلي برمجيًا باستخدام Aspose.Tasks لـ .NET. ما عليك سوى الوصول إلى الرموز التفصيلية للمهام وتحديث قيمها حسب الحاجة.
### س: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟
ج: يدعم Aspose.Tasks مجموعة واسعة من إصدارات Microsoft Project، بما في ذلك 2003 و2007 و2010 و2013 و2016 و2019.
### س: هل يتطلب Aspose.Tasks ترخيصًا للاستخدام التجاري؟
ج: نعم، يلزم وجود ترخيص صالح للاستخدام التجاري لـ Aspose.Tasks. يمكنك الحصول على ترخيص من موقع Aspose.
### س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من الموقع الإلكتروني لتقييم مميزاته وإمكانياته.
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 ج: يمكنك الحصول على الدعم لـ Aspose.Tasks من خلال زيارة المنتدى على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).## إكمال كود المصدر