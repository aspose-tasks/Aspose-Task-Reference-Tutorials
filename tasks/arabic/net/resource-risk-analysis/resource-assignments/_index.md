---
title: التعامل مع تعيينات موارد مشروع MS في Aspose.Tasks
linktitle: التعامل مع تعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية التعامل مع تعيينات موارد MS Project بكفاءة باستخدام Aspose.Tasks لـ .NET. يوفر هذا الشامل إرشادات خطوة بخطوة للمطورين.
weight: 11
url: /ar/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التعامل مع تعيينات موارد مشروع MS في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في كيفية التعامل مع تعيينات موارد Microsoft Project بكفاءة باستخدام Aspose.Tasks لـ .NET. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجياً. باتباع هذه الخطوات، ستتعلم كيفية إدارة تعيينات الموارد بشكل فعال داخل تطبيقات .NET الخاصة بك.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.Tasks في مشروع .NET الخاص بك. هذا يتضمن:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
لنقم الآن بتقسيم المثال المقدم إلى خطوات متعددة للحصول على فهم شامل لكيفية التعامل مع تعيينات موارد MS Project باستخدام Aspose.Tasks.
## الخطوة 1: إعداد إعدادات المشروع والتقويم
للبدء، قم بإنشاء نسخة جديدة من المشروع وقم بإعداد إعدادات تقويم المشروع:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## الخطوة 2: إضافة مهمة إلى المشروع
بعد ذلك، قم بإضافة مهمة جديدة إلى المهمة الجذرية للمشروع:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## الخطوة 3: إنشاء تعيين الموارد وإنشاء البيانات الموزعة على الوقت
الآن، قم بإنشاء تعيين مورد جديد للمهمة وقم بإنشاء بيانات موزعة على الوقت:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## الخطوة 4: تقسيم المهمة
قم بتقسيم المهمة إلى أجزاء متعددة من خلال توفير تاريخي البدء والانتهاء:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## الخطوة 5: تحديد محيط العمل
قم بتعيين نوع مخطط العمل للمهمة:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## الخطوة 6: احفظ المشروع
وأخيرا، احفظ ملف المشروع مع التغييرات التي تم إجراؤها:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## خاتمة
في الختام، تعد معالجة تعيينات موارد Microsoft Project باستخدام Aspose.Tasks لـ .NET عملية مباشرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك إدارة تعيينات الموارد بكفاءة داخل تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يستطيع Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟
نعم، يوفر Aspose.Tasks وظائف شاملة للتعامل مع هياكل المشاريع المعقدة بكفاءة.
### هل Aspose.Tasks متوافق مع الإصدارات المختلفة من Microsoft Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.
### هل يمكنني تخصيص تعيينات الموارد بناءً على متطلبات محددة؟
بالتأكيد، يقدم Aspose.Tasks خيارات تخصيص واسعة النطاق لتعيينات الموارد لتلبية احتياجات المشروع المحددة.
### هل يدعم Aspose.Tasks تصدير بيانات المشروع إلى تنسيقات أخرى؟
نعم، يسمح Aspose.Tasks بتصدير بيانات المشروع إلى تنسيقات مختلفة مثل XML وPDF وHTML وغيرها.
### هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟
نعم، يوفر Aspose دعمًا فنيًا مخصصًا من خلال المنتدى الخاص به والقنوات الأخرى لمساعدة المستخدمين في الرد على أي استفسارات أو مشكلات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
