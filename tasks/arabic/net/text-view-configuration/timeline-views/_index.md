---
title: إتقان طرق عرض الجداول الزمنية للمشروع في Aspose.Tasks
linktitle: تخصيص طرق عرض الجدول الزمني في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: إتقان Aspose.Tasks لـ .NET في تخصيص طرق عرض المخطط الزمني. قم بتحسين إدارة مشروعك من خلال جداول زمنية جذابة بصريًا ومصممة خصيصًا لتلبية احتياجات مشروعك.
weight: 13
url: /ar/net/text-view-configuration/timeline-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان طرق عرض الجداول الزمنية للمشروع في Aspose.Tasks

## مقدمة
يعد إنشاء عروض جدول زمني جذابة وغنية بالمعلومات أمرًا بالغ الأهمية لإدارة المشروع بشكل فعال. يوفر Aspose.Tasks for .NET حلاً قويًا لتخصيص طرق عرض المخطط الزمني، مما يسمح لك بتخصيص عرض المهام وفقًا للاحتياجات المحددة لمشروعك. في هذا الدليل التفصيلي، سنستكشف كيفية استخدام Aspose.Tasks لإنشاء طرق عرض المخطط الزمني وتخصيصها بسهولة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة C# و.NET.
-  تم تثبيت Aspose.Tasks لمكتبة .NET. إذا لم يكن الأمر كذلك، قم بتنزيله[هنا](https://releases.aspose.com/tasks/net/).
- بيئة تطوير متكاملة (IDE) مثل Visual Studio.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## الخطوة 1: تهيئة عرض المشروع والمخطط الزمني
ابدأ بتهيئة مشروع جديد وعرض الجدول الزمني:
```csharp
var project = new Project();
var view = new TimelineView();
```
## الخطوة 2: تعيين خصائص عرض المخطط الزمني
قم بتخصيص عرض المخطط الزمني عن طريق تعيين خصائص مختلفة:
```csharp
view.DateFormat = DateFormat.DateDddDd;
view.DisplayOverlapped = true;
view.ShowPanZoom = true;
view.ShowTimescale = true;
view.ShowToday = true;
view.TextLinesCount = 2;
```
## الخطوة 3: عرض المخطط الزمني وعرض التفاصيل
استرداد المعلومات حول عرض المخطط الزمني:
```csharp
Console.WriteLine("Show Dates: " + view.ShowDates);
```
## الخطوة 4: إضافة عرض إلى المشروع
أضف عرض المخطط الزمني المخصص للمشروع:
```csharp
project.Views.Add(view);
```
## الخطوة 5: إضافة بيانات الاختبار إلى المشروع
قم بملء المشروع بالمهام النموذجية:
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task1.Set(Tsk.Duration, task1.ParentProject.GetDuration(24, TimeUnitType.Hour));
var task2 = project.RootTask.Children.Add("Task 2");
task2.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task2.Set(Tsk.Duration, task1.ParentProject.GetDuration(40, TimeUnitType.Hour));
```
## الخطوة 6: احفظ المشروع بصيغة PDF
احفظ المشروع باستخدام عرض المخطط الزمني المخصص كملف PDF:
```csharp
project.Save("Your Document Directory/SetTimeScaleCount_out.pdf", SaveFileFormat.Pdf);
```
## خاتمة
تهانينا! لقد نجحت في تخصيص طرق عرض المخطط الزمني باستخدام Aspose.Tasks لـ .NET. تعمل هذه المكتبة القوية على تبسيط عملية إنشاء جداول زمنية جذابة بصريًا للمشروع، مما يعزز قدرات إدارة المشروع لديك.
## الأسئلة الشائعة
### هل Aspose.Tasks متوافق مع أطر عمل .NET الأخرى؟
نعم، يدعم Aspose.Tasks أطر عمل .NET المختلفة، مما يضمن التوافق مع بيئة التطوير لديك.
### هل يمكنني تخصيص مظهر المهام الفردية في عرض المخطط الزمني؟
قطعاً! يوفر Aspose.Tasks المرونة لتخصيص مظهر كل مهمة في عرض المخطط الزمني.
### أين يمكنني العثور على موارد ودعم إضافيين لـ Aspose.Tasks؟
 قم بزيارة[Aspose.Tasks الوثائق](https://reference.aspose.com/tasks/net/)للحصول على أدلة شاملة و[منتدى الدعم](https://forum.aspose.com/c/tasks/15) للمساعدة.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
