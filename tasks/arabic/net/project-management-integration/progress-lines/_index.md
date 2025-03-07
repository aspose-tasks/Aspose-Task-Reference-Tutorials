---
title: التعامل مع خطوط تقدم مشروع MS باستخدام Aspose.Tasks
linktitle: التعامل مع خطوط التقدم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع خطوط التقدم في ملفات MS Project باستخدام Aspose.Tasks لـ .NET، مما يعزز تصور المشروع وإدارته.
weight: 15
url: /ar/net/project-management-integration/progress-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التعامل مع خطوط تقدم مشروع MS باستخدام Aspose.Tasks

## مقدمة
يعد Microsoft Project (MS Project) أداة قوية لإدارة المشاريع، مما يسمح للمستخدمين بتتبع الجوانب المختلفة لمشاريعهم. إحدى الميزات المهمة لبرنامج MS Project هي القدرة على تصور خطوط التقدم، مما يساعد أصحاب المصلحة على فهم حالة المشروع ومساره. في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع خطوط التقدم في MS Project باستخدام مكتبة Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير NET مفضلة أخرى.
2.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء
للبدء، فلنستورد مساحات الأسماء الضرورية:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
الآن، دعونا نقسم كل خطوة في التعامل مع خطوط التقدم:
## الخطوة 1: تحميل ملف المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 هنا، نقوم بتحميل ملف MS Project`Project2.mpp` وتعيين تاريخ حالته.
## الخطوة 2: تحديد عرض مخطط جانت
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
لقد قمنا بتحويل عرض المشروع إلى طريقة عرض مخطط جانت لمزيد من المعالجة.
## الخطوة 3: تحديد خطوط التقدم
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
نقوم بتهيئة خطوط التقدم لعرض مخطط جانت.
## الخطوة 4: تكوين إعدادات خط التقدم
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
هنا، قمنا بتعيين خصائص مختلفة لخطوط التقدم، مثل لون الخط والنمط والخط وما إلى ذلك.
## الخطوة 5: التحقق من تكوين خطوط التقدم
```csharp
// إعدادات خطوط تقدم الإخراج
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// إخراج إعدادات أخرى...
```
نقوم بإخراج إعدادات خطوط التقدم التي تم تكوينها للتحقق منها.
## الخطوة 6: احفظ ملف المشروع
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
وأخيرا، نقوم بحفظ ملف المشروع المعدل بخطوط التقدم.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع خطوط التقدم في MS Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك تخصيص خطوط التقدم وتصورها بشكل فعال في ملفات MS Project الخاصة بك برمجيًا.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص مظهر خطوط التقدم بشكل أكبر؟
ج: نعم، يمكنك ضبط خصائص مختلفة مثل لون الخط والنمط والخط لتناسب متطلباتك.
### س: هل يدعم Aspose.Tasks ميزات إدارة المشاريع الأخرى؟
ج: نعم، يوفر Aspose.Tasks دعمًا شاملاً لمعالجة الجوانب المختلفة لملفات MS Project، بما في ذلك المهام والموارد والتقويمات.
### س: هل يمكنني دمج Aspose.Tasks مع مكتبات .NET الأخرى؟
ج: بالتأكيد، تم تصميم Aspose.Tasks للتكامل بسلاسة مع مكتبات .NET الأخرى، مما يسمح لك بتحسين تطبيقات إدارة المشروعات الخاصة بك بشكل أكبر.
### س: هل يوجد منتدى مجتمعي لدعم Aspose.Tasks؟
 ج: نعم، يمكنك العثور على موارد مفيدة وطلب المساعدة في منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل يقدم Aspose.Tasks تراخيص مؤقتة لأغراض التقييم؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت للتقييم من[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
