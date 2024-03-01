---
title: إتقان جمع البيانات على مراحل في Aspose.Tasks
linktitle: جمع البيانات الموزعة على الوقت في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف جمع البيانات الموزعة على الوقت في Aspose.Tasks لـ .NET. دليل خطوة بخطوة والأسئلة الشائعة والمزيد. تعزيز قدرات إدارة المشروع الخاص بك اليوم!
type: docs
weight: 15
url: /ar/net/text-view-configuration/timephased-data-collection/
---
## مقدمة
هل تتطلع إلى الاستفادة من قوة البيانات الموزعة على الوقت في تطبيقات .NET الخاصة بك باستخدام Aspose.Tasks؟ لا مزيد من البحث! سيرشدك هذا الدليل الشامل خلال عملية جمع البيانات الموزعة على الوقت باستخدام Aspose.Tasks لـ .NET، مما يضمن تحقيق أقصى استفادة من هذه المكتبة القوية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[وثائق Aspose.Tasks.NET](https://reference.aspose.com/tasks/net/).
2. بيئة تطوير .NET: تأكد من إعداد بيئة تطوير .NET صالحة للعمل.
3. دليل المستندات الخاص بك: استبدل العنصر النائب "دليل المستندات الخاص بك" في مقتطفات التعليمات البرمجية بالمسار إلى دليل المستند الخاص بك.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. أنشئ مشروعًا وموارد
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. أضف المهام إلى المشروع
```csharp
var task = project.RootTask.Children.Add("Task 1");
// تعيين خصائص المهمة...
var task2 = project.RootTask.Children.Add("Task 2");
// تعيين خصائص المهمة 2...
```
## 3. تخصيص الموارد للمهام
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// تعيين خصائص المهمة...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//تعيين خصائص المهمة 2...
```
## 4. العمل مع البيانات الموزعة على الوقت
```csharp
// تعيين كفاف العمل احيط
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// تحقق مما إذا كان جمع البيانات الموزعة على الوقت للقراءة فقط
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// مسح البيانات الموزعة على الوقت التي تم إنشاؤها
assignment.TimephasedData.Clear();
// إنشاء وإضافة البيانات الموزعة على الوقت
var td = new TimephasedData
{
    // تعيين خصائص البيانات الموزعة على الوقت...
};
assignment.TimephasedData.Add(td);
// إضافة قائمة بالبيانات الموزعة على الوقت
var list = new List<TimephasedData>();
// إضافة المزيد من عناصر البيانات الموزعة على الوقت إلى القائمة...
assignment.TimephasedData.AddRange(list);
// تصفية البيانات الموزعة على الوقت حسب النوع ونطاق التاريخ
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// طباعة البيانات الموزعة على الوقت التي تمت تصفيتها...
```
## 5. التعامل مع البيانات الموزعة على الوقت
```csharp
// قم بإضافة عنصر بيانات خاطئ موزع على الوقت ثم قم بحذفه
var td4 = new TimephasedData
{
    // تعيين خصائص بيانات خاطئة موزعة على الوقت...
};
assignment.TimephasedData.Add(td4);
// حذف عنصر البيانات الخاطئة الموزعة على الوقت
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// التكرار على جميع العناصر الموزعة على الوقت
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // طباعة تفاصيل العنصر الموزعة على الوقت...
}
```
## 6. انسخ البيانات الموزعة على الوقت إلى مهمة أخرى
```csharp
// انسخ البيانات الموزعة على الوقت إلى مهمة أخرى
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// تحويل المجموعة إلى قائمة عادية
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// قم بإزالة عناصر البيانات الموزعة على الوقت واحدًا تلو الآخر
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## خاتمة
في الختام، قدم هذا البرنامج التعليمي شرحًا تفصيليًا لجمع البيانات الموزعة على الوقت باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك دمج هذه الوظيفة بسلاسة في مشاريعك، مما يتيح تتبع الوقت وإدارة الموارد بشكل فعال.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Tasks لـ .NET مع أدوات إدارة المشاريع الأخرى؟
نعم، تم تصميم Aspose.Tasks for .NET للعمل مع أدوات إدارة المشاريع الشائعة ويدعم تنسيقات الملفات المختلفة.
### هل هناك حد لعدد الموارد والمهام التي يمكنني إدارتها باستخدام Aspose.Tasks؟
يتعامل Aspose.Tasks مع المشاريع ذات الأحجام المختلفة، ولا يوجد حد صارم لعدد الموارد والمهام.
### كيف يمكنني الحصول على الدعم لأية مشكلات أو استفسارات تتعلق بـ Aspose.Tasks لـ .NET؟
 للحصول على الدعم، قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للتواصل مع المجتمع والحصول على المساعدة.
### هل يمكنني تجربة Aspose.Tasks لـ .NET قبل شرائه؟
 نعم، يمكنك استكشاف ميزات Aspose.Tasks لـ .NET عن طريق الوصول إلى[تجربة مجانية](https://releases.aspose.com/).
### أين يمكنني شراء ترخيص Aspose.Tasks لـ .NET؟
يمكنك شراء ترخيص Aspose.Tasks لـ .NET[هنا](https://purchase.aspose.com/buy).