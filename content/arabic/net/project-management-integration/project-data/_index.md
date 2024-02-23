---
title: إتقان بيانات المشروع باستخدام Aspose.Tasks
linktitle: العمل مع بيانات المشروع في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع بيانات Microsoft Project باستخدام Aspose.Tasks في .NET. قم بإنشاء المهام وإضافة الموارد وحفظ المشاريع بسهولة.
type: docs
weight: 16
url: /ar/net/project-management-integration/project-data/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع بيانات Microsoft Project باستخدام مكتبة Aspose.Tasks لـ .NET. يوفر Aspose.Tasks ميزات قوية لمعالجة ملفات المشروع، بما في ذلك إنشاء المهام وإضافة الموارد وتعيين الخصائص وحفظ المشاريع بتنسيقات مختلفة.
## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك ما يلي:
1.  تثبيت مكتبة Aspose.Tasks: قم بتنزيل وتثبيت مكتبة Aspose.Tasks من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير .NET.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء
قبل العمل مع Aspose.Tasks، قم باستيراد مساحات الأسماء الضرورية إلى مشروعك:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## الخطوة 1: تهيئة كائن المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project();
```
 يقوم هذا السطر بتهيئة مثيل جديد لـ`Project` فئة، والتي تمثل ملف Microsoft Project.
## الخطوة 2: تعيين خصائص المشروع
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
توضح هذه السطور كيفية تعيين خصائص المشروع مثل تنسيق العمل ووضع إنشاء المهام.
## الخطوة 3: إضافة المهام
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
هنا، تتم إضافة مهمة جديدة تسمى "المهمة 1" إلى المهمة الجذرية للمشروع.
## الخطوة 4: تحديد خصائص المهمة
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
تقوم هذه الأسطر بتعيين تاريخ البدء والمدة وتاريخ الانتهاء لـ "المهمة 1".
## الخطوة 5: إضافة الموارد
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
يوضح هذا الجزء كيفية إضافة مورد عمل إلى المشروع.
## الخطوة 6: تعيين الموارد للمهام
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
توضح هذه السطور كيفية تعيين مورد العمل المضاف مسبقًا إلى "المهمة 1" مع تواريخ البدء والعمل والانتهاء المحددة.
## الخطوة 7: حفظ المشروع
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
وأخيرًا، يتم حفظ المشروع بتنسيق ملف Microsoft Project XML.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية العمل مع بيانات Microsoft Project باستخدام مكتبة Aspose.Tasks في .NET. باتباع الدليل خطوة بخطوة، يمكنك التعامل مع ملفات المشروع وإضافة المهام والموارد وتعيين الموارد للمهام وحفظ المشاريع بتنسيقات مختلفة.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟
ج: نعم، يوفر Aspose.Tasks دعمًا شاملاً لهياكل المشاريع المعقدة، مما يسمح لك بإدارة المهام والموارد والواجبات بكفاءة.
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من Microsoft Project؟
ج: يدعم Aspose.Tasks نطاقًا واسعًا من إصدارات Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.
### س: هل يمكنني دمج Aspose.Tasks مع مكتبات .NET الأخرى؟
ج: بالتأكيد، يتكامل Aspose.Tasks بسلاسة مع مكتبات .NET الأخرى، مما يوفر المرونة في مشاريع التطوير الخاصة بك.
### س: هل يقدم Aspose.Tasks الدعم لخوارزميات جدولة المشروع؟
ج: نعم، يتضمن Aspose.Tasks خوارزميات جدولة متقدمة لمساعدتك على تحسين الجداول الزمنية للمشروع واستخدام الموارد.
### س: هل يوجد منتدى مجتمعي لمستخدمي Aspose.Tasks؟
 ج: نعم، يمكنك العثور على موارد مفيدة والتفاعل مع مستخدمي Aspose.Tasks الآخرين على الموقع[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).