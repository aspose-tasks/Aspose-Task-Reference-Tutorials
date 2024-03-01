---
title: قم بتكوين إعدادات صفحة مشروع MS باستخدام Aspose.Tasks
linktitle: تكوين إعدادات الصفحة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين إعدادات صفحة MS Project باستخدام Aspose.Tasks لـ .NET. قم بتخصيص الاتجاه والحجم والمزيد بخطوات بسيطة.
type: docs
weight: 20
url: /ar/net/outline-code-page-settings/page-settings/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية تكوين إعدادات صفحة Microsoft Project باستخدام Aspose.Tasks لـ .NET. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجيًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لـ .NET: تأكد من تثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير باستخدام Visual Studio أو أي بيئة تطوير متكاملة أخرى مفضلة لتطوير .NET.

## استيراد مساحات الأسماء
للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروعك. توفر مساحات الأسماء هذه إمكانية الوصول إلى فئات Aspose.Tasks والأساليب المطلوبة لمعالجة ملفات MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## الخطوة 1: تحميل ملف المشروع
أولاً، تحتاج إلى تحميل ملف MS Project الذي تريد تكوين إعدادات الصفحة له.
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## الخطوة 2: الوصول إلى إعدادات الصفحة
بعد ذلك، ستصل إلى إعدادات الصفحة لملف المشروع.
```csharp
// احصل على الإعدادات
var settings = project.DefaultView.PageInfo.PageSettings;
```
## الخطوة 3: تكوين إعدادات الصفحة
الآن، لنقم بتكوين خصائص مختلفة لإعدادات الصفحة وفقًا لمتطلباتك.
```csharp
// ضبط اتجاه الصفحة على الوضع العمودي
settings.IsPortrait = true;
// قم بتعيين عدد الصفحات بالعرض المراد طباعتها
settings.PagesInWidth = 5;
// قم بتعيين عدد الصفحات في الارتفاع المراد طباعتها
settings.PagesInHeight = 7;
// قم بتعيين النسبة المئوية للحجم الطبيعي لضبط الطباعة عليه
settings.PercentOfNormalSize = 200;
// ضبط حجم الورق
settings.PaperSize = PrinterPaperSize.PaperB4;
// تعيين رقم الصفحة الأولى للطباعة
settings.FirstPageNumber = 3;
```
## الخطوة 4: احفظ ملف المشروع
وأخيرًا، احفظ ملف المشروع بإعدادات الصفحة المحدثة.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تكوين إعدادات صفحة Microsoft Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة تخصيص اتجاه الصفحة وحجمها وخيارات الطباعة الأخرى وفقًا لمتطلباتك.

## الأسئلة الشائعة
### س: هل يمكنني تكوين إعدادات الصفحة لملفات MS Project المتعددة في وقت واحد؟
ج: نعم، يمكنك تكرار ملفات المشروع المتعددة وتطبيق إعدادات الصفحة نفسها على كل منها.
### س: هل من الممكن إعادة إعدادات الصفحة إلى الوضع الافتراضي؟
ج: بالتأكيد، يمكنك ببساطة حذف خطوات التكوين أو إعادة ضبط الإعدادات على قيمها الافتراضية.
### س: هل هناك أي قيود على أحجام الورق المدعومة؟
ج: يدعم Aspose.Tasks نطاقًا واسعًا من أحجام الورق، بما في ذلك الأحجام القياسية والمخصصة.
### س: هل يمكنني أتمتة عملية تكوين إعدادات الصفحة؟
ج: بالتأكيد، يمكنك دمج هذه الوظيفة في سير عمل التطبيق الخاص بك لأتمتة تكوين إعدادات الصفحة.
### س: هل يقدم Aspose.Tasks الدعم لتنسيقات الملفات المختلفة إلى جانب .mpp؟
ج: نعم، يدعم Aspose.Tasks تنسيقات ملفات متنوعة مثل XML وMPT وHTML وغيرها.