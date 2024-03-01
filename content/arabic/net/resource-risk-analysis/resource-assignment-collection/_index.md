---
title: مجموعة تعيينات الموارد في Aspose.Tasks
linktitle: مجموعة تعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة تعيينات الموارد في Microsoft Project باستخدام Aspose.Tasks لـ .NET. برنامج تعليمي خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 12
url: /ar/net/resource-risk-analysis/resource-assignment-collection/
---
## مقدمة
مرحبًا بك في هذا البرنامج التعليمي الشامل حول إدارة تعيينات الموارد في Microsoft Project باستخدام Aspose.Tasks لـ .NET. في هذا البرنامج التعليمي، سوف نتعمق في العملية خطوة بخطوة، مما يضمن أن لديك فهمًا قويًا لكيفية التعامل مع تعيينات الموارد بكفاءة. سواء كنت مطورًا متمرسًا أو بدأت للتو، فسيرشدك هذا الدليل إلى كل ما تحتاج إلى معرفته.
## المتطلبات الأساسية
قبل أن نتعمق في الكود، تأكد من أن لديك الإعداد التالي:
1.  تثبيت Aspose.Tasks لـ .NET: تأكد من تثبيت Aspose.Tasks لـ .NET في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. المعرفة الأساسية بـ C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا للغة البرمجة C#.
3. ملف Microsoft Project: احصل على ملف Microsoft Project جاهزًا لأغراض الاختبار. إذا لم يكن لديك واحد، يمكنك إنشاء ملف عينة.

## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## الخطوة 1: تحميل ملف المشروع
ابدأ بتحميل ملف Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## الخطوة 2: إضافة المهمة والموارد
الآن، دعونا نضيف مهمة وموردًا إلى المشروع:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## الخطوة 3: تعيين المورد للمهمة
بعد ذلك، سنقوم بتعيين المورد للمهمة:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## الخطوة 4: العمل مع أنواع المهام المختلفة
يمكنك أيضًا العمل مع المهام التي تتضمن وحدات أو تكاليف:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// قم بتعيين خصائص المهام ذات الوحدات والتكاليف بشكل مشابه كما هو موضح في الخطوة 3
```
## الخطوة 5: طباعة المهام
طباعة المهام الخاصة بالمشروع:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // طباعة تفاصيل المهمة
}
```
## الخطوة 6: استرداد التعيين عن طريق UID
يمكنك استرداد المهام عن طريق UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## الخطوة 7: التحقق من حالة القراءة فقط
تحقق مما إذا كانت مجموعة تعيين الموارد للقراءة فقط:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## الخطوة 8: تحويل المجموعة إلى القائمة والتكرار
تحويل المجموعة إلى قائمة وتكرارها:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## خاتمة
تهانينا! لقد تعلمت كيفية إدارة تعيينات الموارد في Microsoft Project باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك التعامل مع المهام والموارد بكفاءة، مما يجعل إدارة المشروع أمرًا سهلاً.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ .NET مع إصدارات مختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks for .NET إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### س: هل هناك إصدار تجريبي متاح قبل شراء Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم إذا واجهت أية مشكلات أثناء استخدام Aspose.Tasks لـ .NET؟
 ج: يمكنك طلب الدعم من منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل يمكنني استخدام تراخيص مؤقتة لـ Aspose.Tasks لـ .NET؟
 ج: نعم، التراخيص المؤقتة متاحة لأغراض التقييم. يمكنك الحصول على واحدة من[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني شراء ترخيص كامل لـ Aspose.Tasks لـ .NET؟
 ج: يمكنك شراء ترخيص كامل من متجر Aspose عبر الإنترنت[هنا](https://purchase.aspose.com/buy).