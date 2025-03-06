---
title: إتقان خيارات حفظ مشروع MS لـ Aspose.Tasks
linktitle: خيارات الحفظ العامة لـ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعلم كيفية حفظ ملفات MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET. قم بتخصيص خيارات الإخراج بسهولة لمشاريعك.
weight: 17
url: /ar/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان خيارات حفظ مشروع MS لـ Aspose.Tasks

## مقدمة
يوفر Aspose.Tasks for .NET ميزات قوية لمعالجة ملفات Microsoft Project برمجيًا. في هذا البرنامج التعليمي، سوف نتعمق في تعقيدات حفظ ملفات MS Project باستخدام الخيارات المتنوعة التي يوفرها Aspose.Tasks. على وجه التحديد، سنركز على خيارات الحفظ العامة المتاحة لـ Aspose.Tasks، مما يسمح لك بتخصيص المخرجات وفقًا لمتطلباتك المحددة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  تثبيت Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[رابط التحميل](https://releases.aspose.com/tasks/net/).
2. الفهم الأساسي لـ .NET Framework: يعد الإلمام بمفاهيم برمجة .NET مفيدًا.

## استيراد مساحات الأسماء
قبل الغوص في التعليمات البرمجية، تأكد من استيراد مساحات الأسماء الضرورية:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## الخطوة 1: تحميل ملف المشروع
أولاً، تحتاج إلى تحميل ملف MS Project باستخدام Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## الخطوة 2: تحديد خيارات الحفظ
 حدد خيارات الحفظ وفقًا لمتطلباتك. في هذا المثال، نستخدم`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## الخطوة 3: تخصيص أعمدة العرض
يمكنك تخصيص أعمدة العرض مثل مخطط جانت، وعرض الموارد، وعرض الواجبات. فيما يلي كيفية إضافة أعمدة إلى كل منها:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## الخطوة 4: احفظ المشروع بالخيارات
أخيرًا، احفظ المشروع بالخيارات المحددة:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## خاتمة
إن إتقان خيارات حفظ MS Project العامة باستخدام Aspose.Tasks for .NET يمكّنك من تخصيص تنسيق الإخراج بكفاءة وفقًا لاحتياجات مشروعك.
## الأسئلة الشائعة
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات MS Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project، مما يضمن التوافق عبر بيئات مختلفة.
### س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟
 ج: نعم، يمكنك استكشاف Aspose.Tasks من خلال الإصدار التجريبي المجاني المتاح[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks؟
 ج: يمكن الاطلاع على الوثائق التفصيلية[هنا](https://reference.aspose.com/tasks/net/)، وتوفير إرشادات شاملة حول استخدام ميزات Aspose.Tasks.
### س: كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Tasks؟
 ج: التراخيص المؤقتة متاحة لأغراض التقييم[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني طلب الدعم للاستفسارات المتعلقة بـ Aspose.Tasks؟
 ج: يمكنك الانضمام إلى منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15)للحصول على المساعدة من الخبراء وزملائهم المطورين.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
