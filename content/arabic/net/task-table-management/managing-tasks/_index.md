---
title: إدارة المهام في Aspose.Tasks
linktitle: إدارة المهام في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف الدليل الشامل حول إدارة المهام باستخدام Aspose.Tasks لـ .NET. تعلم كيفية إضافة الأجزاء المقسمة وعرضها ونقلها والحصول على/تعيين الخصائص والمزيد.
type: docs
weight: 15
url: /ar/net/task-table-management/managing-tasks/
---
## مقدمة
إذا كنت مطور .NET وتتطلع إلى إدارة المهام داخل مشاريعك بكفاءة، فإن Aspose.Tasks for .NET يوفر حلاً قويًا. سيرشدك هذا البرنامج التعليمي عبر الجوانب المختلفة لإدارة المهام باستخدام Aspose.Tasks، ويقدم إرشادات خطوة بخطوة وأمثلة على التعليمات البرمجية. سواء كنت تضيف مهام، أو تعرض أجزاء مقسمة، أو تنقل المهام ضمن نفس الأصل، أو تحصل على/تعيين خصائص المهمة، أو تتكرر تعيينات المهام، أو تقرأ الخطوط الأساسية للمهام، أو تحذف المهام، فإن هذا الدليل يوفر لك كل ما تحتاجه.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لمكتبة .NET: تأكد من تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
2. دليل المستندات: قم بإعداد دليل حيث سيتم تخزين مستندات مشروعك.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء الضرورية للعمل مع Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. إضافة مهمة إلى المشروع
```csharp
// إنشاء مشروع جديد
var project = new Project();
// أضف مهمة
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// احفظ المشروع
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. عرض أجزاء المهمة المقسمة
```csharp
// قم بتحميل مشروع بمهام مقسمة
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//الوصول إلى مهمة
var task = project.RootTask.Children.GetById(4);
// عرض الأجزاء المقسمة
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. نقل مهمة تحت نفس الوالد
```csharp
try
{
    // تحميل المشروع
    var project = new Project(DataDir + "MoveTask.mpp");
    // انقل المهام ذات المعرف 5 قبل المهمة ذات المعرف 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // احفظ المشروع المعدل
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. الحصول على/تعيين خصائص المهمة
```csharp
// إنشاء مشروع جديد
var project = new Project();
// إضافة مهمة وتعيين الخصائص
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// جمع وعرض خصائص المهمة
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. التكرار على تعيينات المهمة
```csharp
// تحميل مشروع مع المهام
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// جمع وعرض مهام المهام
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. قراءة الخطوط الأساسية للمهمة
```csharp
// إنشاء مشروع جديد
var project = new Project();
// أضف مهمة وقم بتعيين خط الأساس
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// عرض مدة خط الأساس للمهمة
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. حذف مهمة
```csharp
// إنشاء مشروع جديد
var project = new Project();
// أضف مهمة
var task = project.RootTask.Children.Add("Task");
// عرض عدد المهام قبل وبعد الحذف
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// احذف المهمة
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## خاتمة
تعد إدارة المهام في Aspose.Tasks لـ .NET عملية سلسة مع الأمثلة المقدمة. سواء كنت مطورًا متمرسًا أو بدأت للتو، فإن دمج هذه التقنيات سيعزز قدرات إدارة مشروعك.
## أسئلة مكررة
### س: هل Aspose.Tasks متوافق مع جميع أطر عمل .NET؟
ج: نعم، يدعم Aspose.Tasks أطر عمل .NET المختلفة، مما يضمن التوافق مع بيئة التطوير لديك.
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟
 ج: يمكنك الحصول على ترخيص مؤقت لمدة 30 يومًا من[هنا](https://purchase.aspose.com/temporary-license/).
### س: هل هناك أي قيود عند العمل مع المهام المقسمة في Aspose.Tasks؟
 ج: تعد المهام المقسمة ميزة قوية، ويمكن العثور على وثائق مفصلة[هنا](https://reference.aspose.com/tasks/net/).
### س: هل يمكنني تخصيص خصائص المهمة بما يتجاوز ما هو موضح في الأمثلة؟
ج: بالتأكيد! يوفر Aspose.Tasks خيارات تخصيص واسعة النطاق لخصائص المهمة. تحقق من الوثائق لمزيد من التفاصيل.
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 ج: قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.