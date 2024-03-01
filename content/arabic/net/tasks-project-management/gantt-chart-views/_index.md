---
title: إتقان طرق عرض مخطط جانت في Aspose.Tasks
linktitle: طرق عرض مخطط جانت في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تخصيص طرق عرض مخطط جانت في ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET. دليل خطوة بخطوة لإدارة المشاريع بكفاءة.
type: docs
weight: 22
url: /ar/net/tasks-project-management/gantt-chart-views/
---
## مقدمة
تعد مخططات جانت أدوات قوية تستخدم في إدارة المشاريع لتصور المهام والجداول الزمنية والتبعيات. يوفر Aspose.Tasks for .NET إمكانات قوية للعمل مع طرق عرض مخططات جانت في ملفات Microsoft Project. في هذا البرنامج التعليمي، سوف نستكشف كيفية استخدام Aspose.Tasks لمعالجة طرق عرض مخطط جانت، وتخصيص مظهرها، وحفظها كملفات PDF.
## المتطلبات الأساسية
قبل المتابعة، تأكد من توفر المتطلبات الأساسية التالية:
### 1. تثبيت Aspose.Tasks لـ .NET
 تأكد من تثبيت Aspose.Tasks لـ .NET. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/tasks/net/) واتبع تعليمات التثبيت المتوفرة في الوثائق[هنا](https://reference.aspose.com/tasks/net/).
### 2. ملف مشروع مايكروسوفت
تحضير ملف Microsoft Project (`Project2.mpp`) الذي ستستخدمه للتعامل مع طرق عرض مخطط جانت.
### 3. المعرفة الأساسية بـ C# و.NET Framework
يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا للغة البرمجة C# وإطار عمل .NET.
## استيراد مساحات الأسماء
قبل أن تبدأ العمل مع طرق عرض مخطط جانت في Aspose.Tasks، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك. وإليك كيف يمكنك القيام بذلك:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

دعنا نقسم رمز المثال المقدم إلى خطوات متعددة ونشرح كل خطوة بالتفصيل:
## الخطوة 1: تحميل ملف المشروع
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
تتضمن هذه الخطوة تحميل ملف Microsoft Project (`Project2.mpp` ) في مثيل`Project` فصل.
## الخطوة 2: تعيين تاريخ الحالة
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
هنا، قمنا بتعيين تاريخ حالة المشروع على تاريخ بدايته.
## الخطوة 3: الوصول إلى عرض مخطط جانت
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
يمكننا الوصول إلى عرض مخطط جانت من المشروع. يسمح Aspose.Tasks بالوصول إلى طرق العرض مثل مخطط جانت ومخطط الشبكة واستخدام المهام.
## الخطوة 4: تخصيص عرض مخطط جانت
الآن، دعونا نخصص الجوانب المختلفة لعرض مخطط جانت:
### ضبط تقريب الشريط
```csharp
view.BarRounding = false;
```
يؤدي هذا إلى تحديد ما إذا كانت الأشرطة الموجودة على مخطط جانت سيتم تقريبها إلى أقرب يوم.
### ضبط حجم الشريط
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
يحدد هذا ارتفاع أشرطة جانت في المخطط.
### إخفاء أشرطة التجميع
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
يحدد ما إذا كان سيتم إخفاء أشرطة القيمة المحتسبة عند توسيع المهام الموجزة.
### ضبط لون وقت غير العمل
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
يحدد اللون لوقت عدم العمل على مخطط جانت.
### نشمر أشرطة جانت
```csharp
view.RollUpGanttBars = true;
```
يحدد ما إذا كان يجب إظهار الأشرطة الموجودة في مخطط جانت أم لا.
### عرض انقسامات الشريط
```csharp
view.ShowBarSplits = true;
```
تحديد ما إذا كان يجب إظهار تقسيمات المهام في مخطط جانت.
### عرض الرسومات
```csharp
view.ShowDrawings = true;
```
يحدد ما إذا كان يجب إظهار الرسومات الموجودة في مخطط جانت.
### النسبة المئوية لحجم الجدول الزمني
```csharp
view.TimescaleSizePercentage = 10;
```
يقوم بتعيين نسبة مئوية لضبط التباعد بين الوحدات في طبقة مقياس الوقت.
## الخطوة 5: حفظ عرض مخطط جانت بصيغة PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
وأخيرًا، نقوم بحفظ عرض مخطط جانت المخصص كملف PDF.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية العمل مع طرق عرض مخطط جانت في Aspose.Tasks لـ .NET. باتباع الخطوات المتوفرة، يمكنك التعامل مع مخططات جانت وتخصيصها بكفاءة وفقًا لمتطلبات مشروعك.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص مظهر أشرطة مخطط جانت بشكل أكبر؟
ج: نعم، يوفر Aspose.Tasks خيارات شاملة لتخصيص مظهر أشرطة مخطط جانت، بما في ذلك الألوان والأشكال والأحجام.
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### س: هل يمكنني تصدير طرق عرض مخطط جانت إلى تنسيقات أخرى غير PDF؟
ج: بالتأكيد، يدعم Aspose.Tasks تصدير طرق عرض مخطط جانت إلى تنسيقات متعددة، بما في ذلك PNG وJPEG وXPS.
### س: هل يقدم Aspose.Tasks الدعم لخوارزميات جدولة المشاريع المعقدة؟
ج: نعم، يوفر Aspose.Tasks خوارزميات جدولة متقدمة للتعامل مع جداول المشاريع المعقدة بشكل فعال.
### س: هل يوجد منتدى مجتمعي حيث يمكنني طلب المساعدة أو مشاركة تجاربي مع Aspose.Tasks؟
 ج: نعم، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للتواصل مع المستخدمين الآخرين وطرح الأسئلة وإيجاد حلول لاستفساراتك.