---
title: تكوين طرق عرض استخدام موارد مشروع MS في Aspose.Tasks
linktitle: تكوين طرق عرض استخدام الموارد في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين طرق عرض استخدام موارد MS Project باستخدام Aspose.Tasks لـ .NET. تم تضمين دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 15
url: /ar/net/resource-risk-analysis/resource-usage-views/
---
## مقدمة
يعد Microsoft Project (MS Project) أداة قوية لإدارة المشاريع، مما يسمح للمستخدمين بتخطيط مشاريعهم وتنفيذها وتتبعها بكفاءة. يوفر Aspose.Tasks for .NET تكاملًا سلسًا مع ملفات MS Project، مما يمكّن المطورين من معالجة بيانات المشروع برمجيًا. في هذا البرنامج التعليمي، سنستكشف كيفية تكوين طرق عرض استخدام موارد MS Project باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[رابط التحميل](https://releases.aspose.com/tasks/net/).
2. ملف Microsoft Project: لديك ملف Microsoft Project (`.mpp`) تحتوي على بيانات المشروع الذي تريد العمل معه.

## استيراد مساحات الأسماء
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## الخطوة 1: تحميل ملف المشروع
أولاً، قم بتحميل ملف MS Project باستخدام Aspose.Tasks:
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## الخطوة 2: تحديد خيارات الحفظ
حدد خيارات الحفظ التي تحدد إعدادات النطاق الزمني المطلوبة وتنسيق العرض التقديمي:
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## الخطوة 3: احفظ المشروع باستخدام طرق عرض استخدام الموارد
احفظ المشروع باستخدام طرق عرض استخدام الموارد التي تم تكوينها في ملف PDF:
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تكوين طرق عرض استخدام موارد MS Project باستخدام Aspose.Tasks لـ .NET. باتباع الخطوات المقدمة، يمكن للمطورين دمج Aspose.Tasks بسلاسة في تطبيقات .NET الخاصة بهم لمعالجة بيانات المشروع بكفاءة.

## الأسئلة الشائعة
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك .mpp، و.mpt، و.xml، و.mpx.
### س: هل يمكنني تخصيص إعدادات الجدول الزمني وتنسيق العرض التقديمي بشكل أكبر؟
ج: بالتأكيد، يوفر Aspose.Tasks المرونة لتخصيص إعدادات الجدول الزمني وتنسيقات العرض التقديمي وفقًا لمتطلباتك.
### س: هل يدعم Aspose.Tasks تنسيقات الإخراج الأخرى إلى جانب PDF؟
ج: نعم، يدعم Aspose.Tasks مجموعة متنوعة من تنسيقات الإخراج بما في ذلك XLSX وMPP وXML وHTML والمزيد.
### س: هل يوجد مجتمع أو منتدى لدعم Aspose.Tasks؟
 ج: نعم، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لأية استفسارات أو مناقشات أو احتياجات الدعم.
### س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟
 ج: بالطبع، يمكنك استكشاف Aspose.Tasks من خلال الإصدار التجريبي المجاني المتاح[هنا](https://releases.aspose.com/).