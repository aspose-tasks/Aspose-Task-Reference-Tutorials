---
title: قم بتكوين خيارات MS Project XLSX في Aspose.Tasks لـ .NET
linktitle: تكوين خيارات XLSX في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين خيارات MS Project XLSX في Aspose.Tasks لـ .NET. قم بتخصيص الأعمدة والتشفير وغير ذلك الكثير بسهولة.
weight: 11
url: /ar/net/file-format-options/configuring-xlsx-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتكوين خيارات MS Project XLSX في Aspose.Tasks لـ .NET

## مقدمة
يعد Microsoft Project (MS Project) أداة قوية لإدارة المشاريع، ويوفر Aspose.Tasks for .NET تكاملًا سلسًا للعمل مع ملفات MS Project برمجيًا. في هذا البرنامج التعليمي، سنتعرف على عملية تكوين خيارات MS Project XLSX باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
### 1. تم تثبيت Aspose.Tasks لـ .NET
 تأكد من تثبيت Aspose.Tasks for .NET في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[صفحة تنزيل Aspose.Tasks لـ .NET](https://releases.aspose.com/tasks/net/).
### 2. الفهم الأساسي لـ C# و.NET Framework
يلزم الإلمام بلغة البرمجة C# وإطار عمل .NET لمتابعة هذا البرنامج التعليمي.
### 3. ملف مشروع مايكروسوفت
احصل على ملف Microsoft Project (MPP) جاهزًا تريد تكوينه وحفظه كملف XLSX.

## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## الخطوة 1: تحميل المشروع
```csharp
var project = new Project("YourProjectFile.mpp");
```
قم بتحميل ملف Microsoft Project الذي تريد تكوينه.
## الخطوة 2: تحديد XlsxOptions
```csharp
var options = new XlsxOptions();
```
 إنشاء مثيل ل`XlsxOptions` لتكوين الإعدادات للحفظ بتنسيق XLSX.
## الخطوة 3: إضافة أعمدة مخطط جانت
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
أضف أعمدة مخطط جانت المطلوبة إلى الخيارات.
## الخطوة 4: إضافة أعمدة عرض الموارد
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
قم بتضمين الأعمدة المطلوبة لعرض الموارد في الخيارات.
## الخطوة 5: إضافة أعمدة عرض المهام
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
أضف الأعمدة المطلوبة لعرض المهمة في الخيارات.
## الخطوة 6: ضبط الترميز
```csharp
options.Encoding = Encoding.Unicode;
```
قم بتعيين الترميز لملف الإخراج.
## الخطوة 7: احفظ المشروع باسم XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
احفظ المشروع بالخيارات التي تم تكوينها كملف XLSX.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تكوين خيارات MS Project XLSX باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك تخصيص تنسيق الإخراج وفقًا لمتطلباتك، مما يعزز المرونة وسهولة الاستخدام لسير عمل إدارة المشروع الخاص بك.
## الأسئلة الشائعة

### س: هل يمكنني تكوين أعمدة مختلفة لمخطط جانت وعرض الموارد وعرض المهام بشكل منفصل؟

ج: نعم، يمكنك تخصيص الأعمدة بشكل مستقل لكل طريقة عرض باستخدام Aspose.Tasks لـ .NET.

### س: هل هناك إصدار تجريبي متاح قبل شراء Aspose.Tasks لـ .NET؟

 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[صفحة إصدارات Aspose.Tasks لـ .NET](https://releases.aspose.com/).

### س: كيف يمكنني الحصول على الدعم إذا واجهت أية مشكلات أو كانت لدي أسئلة أثناء التنفيذ؟

 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة من المجتمع وفريق دعم Aspose.

### س: هل يمكنني إنشاء ملفات XLSX باستخدام Aspose.Tasks لـ .NET على الأنظمة الأساسية التي لا تعمل بنظام Windows؟

ج: تم تصميم Aspose.Tasks for .NET بشكل أساسي لأنظمة Windows الأساسية، ولكن يمكنك استكشاف خيارات التوافق للأنظمة الأساسية الأخرى.

### س: هل هناك أي خيارات ترخيص مؤقتة متاحة لأغراض الاختبار؟

 ج: نعم، يمكنك الحصول على ترخيص مؤقت من[صفحة الترخيص المؤقتة Aspose.Tasks](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
