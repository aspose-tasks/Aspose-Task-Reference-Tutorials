---
title: صورة حفظ خيارات مشروع MS لـ Aspose.Tasks
linktitle: خيارات حفظ الصورة لـ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية حفظ خيارات MS Project كصور باستخدام Aspose.Tasks لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 11
url: /ar/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# صورة حفظ خيارات مشروع MS لـ Aspose.Tasks


## مقدمة
في عالم تطوير البرمجيات، يعد التعامل مع مهام المشروع بكفاءة أمرًا بالغ الأهمية لإدارة المشروع بنجاح. يوفر Aspose.Tasks for .NET حلاً قويًا للمطورين الذين يعملون مع ملفات Microsoft Project، مما يسمح لهم بمعالجة مهام المشروع وتحويلها وإدارتها بسلاسة داخل تطبيقات .NET الخاصة بهم.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.Tasks لـ .NET لحفظ خيارات MS Project كصور، تأكد من توفر المتطلبات الأساسية التالية:
### 1. قم بتثبيت Aspose.Tasks لـ .NET
للبدء، يجب أن يكون لديك Aspose.Tasks for .NET مثبتًا في بيئة التطوير لديك. يمكنك تحميل المكتبة من[موقع إلكتروني](https://releases.aspose.com/tasks/net/) واتبع تعليمات التثبيت المقدمة.
### 2. الحصول على ترخيص (اختياري)
 بينما يمكن استخدام Aspose.Tasks لـ .NET بدون ترخيص في وضع التقييم، يوصى بالحصول على ترخيص للحصول على الوظائف الكاملة ولإزالة قيود التقييم. يمكنك الحصول على ترخيص من[صفحة الشراء](https://purchase.aspose.com/buy) أو اختر أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لأغراض تجريبية.
### 3. المعرفة الأساسية بتطوير C# و.NET
يعد الفهم الأساسي للغة البرمجة C# وإطار عمل .NET ضروريًا للمتابعة مع الأمثلة ودمج وظائف Aspose.Tasks في تطبيقاتك بشكل فعال.
## استيراد مساحات الأسماء
قبل أن نبدأ في حفظ خيارات MS Project كصور باستخدام Aspose.Tasks لـ .NET، دعونا نتأكد من أننا نستورد مساحات الأسماء الضرورية لمشروعنا C#:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## الخطوة 1: إعداد مسار دليل المستندات
تأكد من أن لديك دليلًا مخصصًا لمستنداتك وقم بتعيين المسار وفقًا لذلك:
```csharp
String DataDir = "Your Document Directory";
```
## الخطوة 2: قم بتحميل ملف MS Project
 تهيئة جديدة`Project` الكائن عن طريق تحميل ملف MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## الخطوة 3: تحديد خيارات حفظ الصورة
 إنشاء مثيل ل`ImageSaveOptions`وحدد الإعدادات المطلوبة:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## الخطوة 4: تحديد الصفحات المراد حفظها
إذا لزم الأمر، حدد الصفحات التي سيتم حفظها. في هذا المثال، نقوم بإضافة الصفحة 2:
```csharp
options.Pages.Add(2);
```
## الخطوة 5: احفظ الصورة
وأخيرًا، احفظ الصفحات المحددة كصورة مع الخيارات المحددة:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## خاتمة
يعمل Aspose.Tasks for .NET على تبسيط عملية العمل مع ملفات MS Project، مما يسمح للمطورين بمعالجة مهام المشروع بسهولة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك حفظ خيارات MS Project بكفاءة كصور داخل تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Tasks لـ .NET بدون ترخيص؟
ج: نعم، يمكنك استخدام Aspose.Tasks لـ .NET بدون ترخيص في وضع التقييم. ومع ذلك، يوصى بالحصول على ترخيص للوظائف الكاملة ولإزالة قيود التقييم.
### س2: كيف يمكنني الحصول على ترخيص مؤقت للاختبار؟
 ج: يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).
### س 3: هل Aspose.Tasks لـ .NET متوافق مع أطر عمل .NET الأخرى؟
ج: نعم، Aspose.Tasks for .NET متوافق مع أطر عمل .NET المختلفة، بما في ذلك .NET Core و.NET Standard.
### س4: هل يمكنني تخصيص خيارات حفظ الصورة بشكل أكبر؟
ج: نعم، يمكنك تخصيص خيارات حفظ الصورة وفقًا لمتطلباتك المحددة، مثل ضبط حجم الصفحة أو الدقة أو تنسيق الإخراج.
### س5: أين يمكنني العثور على دعم Aspose.Tasks لـ .NET؟
 ج: يمكنك العثور على الدعم والمساعدة فيما يتعلق بـ Aspose.Tasks لـ .NET على الموقع[المنتدى](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
